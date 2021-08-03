# Read 9 WRRC and Java

## [High-level HTTP](https://dev.to/dangolant/things-i-brushed-up-on-this-week-the-http-request-lifecycle-)

- I learned about:

### The HTTP Request Lifecycle

#### Step 1: Local Processing:

1. Your browser extracts the "scheme"/protocol
1. host (www.example.com), and optional port number, resource path, and query strings
1. The browser will then look through its own cache of recently requested URLs, the operating system’s cache of recent queries, your router’s cache, and your DNS cache.

#### Step 2: Resolve an IP

1. If the cache lookup fails, your browser fires off a DNS request using UDP3. The DNS request contains the preconfigured IP for your DNS server and your return IP in its header.
1. Your request will now have to travel many network devices to reach its target DNS server.
1. Once your request arrives at your configured DNS server, the server looks for the address associated with the requested hostname. If it finds one, it sends a response. If, on the other hand, the DNS server you have targeted cannot locate the given hostname, it passes the request along to another DNS server it is configured to defer to. This happens recursively until the address is found, or an "authoritative" nameserver is hit.
1. If the response makes it back (remember, with UDP there’s no guarantee!), the requesting client now has a target IP. It will also have received a piece of information as part of the answer that will let it know how long the returned answer can be cached for.

#### Step 3: Establish a TCP Connection

1. One of the key differences between TCP and UDP is that TCP ensures delivery and ordered data transmission.
1. TCP connections are opened using what’s known as a three-way handshake. The server must already be "listening" on a port, performing a passive open, after which the client can initiate an active open.
1. full duplex communication: bidirectional, concurrent communication along the connection

#### Step 4: Send an HTTP Request

1. The request is made up of a "request line", request header, and a body.
   - Two consecutive <CR><LF> pairs indicate the end of the header section
   - The only mandatory field in an HTTP request is HOST, which contains the domain and port that the request is being sent to (domain.com:8080), although in some cases the port can be omitted.
   - common standard HTTP header fields include Origin, Accept, Accept-Encoding
1. Once the HTTP request is sent using TCPs magic sequence number powers, the server can ensure it receives the whole request, in the correct order.
1. Once the server receives the request, processes it, and finds the resource being requested, it generates an HTTP response.
1. Once the response is generated, the server responds to the request. At the TCP layer, the client receives the first data packet, the first byte of which should contain the HTTP response header.

#### Step 5: Tearing Down and Cleaning Up

1. Once the response has been fully delivered, the client sends a FIN packet at the TCP level, to which the server responds with an ACK, and then generally sends a FIN of its own, which the client responds to with its own ACK signal.
1. The client then waits for a brief timeout, during which it cannot accept new connections, to prevent delayed packets from previous connections arriving during subsequent activities on the port. This four way handshake12 signals the end of the TCP connection.
1. At this point, your browser begins processing what it has received.

## [Java HTTP Request example](https://www.baeldung.com/java-http-request)

- I learned about:

### HttpUrlConnection

1. The HttpUrlConnection class allows us to perform basic HTTP requests without the use of any additional libraries
1. The disadvantages of using this method are that the code can be more cumbersome than other HTTP libraries and that it does not provide more advanced functionalities such as dedicated methods for adding headers or authentication.

### Creating a Request

1. We can create an HttpUrlConnection instance using the openConnection() method of the URL class.
1. The HttpUrlConnection class is used for all types of requests by setting the requestMethod attribute to one of the values: GET, POST, HEAD, OPTIONS, PUT, DELETE, TRACE.

### Adding Request Parameters

1. set the doOutput property to true, then write a String of the form param1=value¶m2=value to the OutputStream of the HttpUrlConnection instance

```java
Map<String, String> parameters = new HashMap<>();
parameters.put("param1", "val");

con.setDoOutput(true);
DataOutputStream out = new DataOutputStream(con.getOutputStream());
out.writeBytes(ParameterStringBuilder.getParamsString(parameters));
out.flush();
out.close();
```

### Setting Request Headers

1. Adding headers to a request can be achieved by using the setRequestProperty() method

```java
con.setRequestProperty("Content-Type", "application/json");
```

2. To read the value of a header from a connection, we can use the getHeaderField() method

```java
String contentType = con.getHeaderField("Content-Type");
```

### Configuring Timeouts

1. HttpUrlConnection class allows setting the connect and read timeouts. These values define the interval of time to wait for the connection to the server to be established or data to be available for reading.

```java
con.setConnectTimeout(5000);
con.setReadTimeout(5000);
```

### Handling Cookies

1. to read the cookies from a response, we can retrieve the value of the Set-Cookie header and parse it to a list of HttpCookie objects:

```java
String cookiesHeader = con.getHeaderField("Set-Cookie");
List<HttpCookie> cookies = HttpCookie.parse(cookiesHeader);
```

2. add the cookies to the cookie store:

```java
cookies.forEach(cookie -> cookieManager.getCookieStore().add(null, cookie));
```

3. add the cookies to the request, we need to set the Cookie header, after closing and reopening the connection:

```java
con.disconnect();
con = (HttpURLConnection) url.openConnection();

con.setRequestProperty("Cookie",
  StringUtils.join(cookieManager.getCookieStore().getCookies(), ";"));
```

### Handling Redirects

1. We can enable or disable automatically following redirects for a specific connection by using the setInstanceFollowRedirects() method with true or false parameter:

```java
con.setInstanceFollowRedirects(false);
```

2. By default, the behavior is enabled

### Reading the Response

1. Reading the response of the request can be done by parsing the InputStream of the HttpUrlConnection instance.

1. To execute the request, we can use the getResponseCode(), connect(), getInputStream() or getOutputStream() methods:

```java
int status = con.getResponseCode();
```

Finally, let's read the response of the request and place it in a content String:

```java
BufferedReader in = new BufferedReader(
  new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer content = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    content.append(inputLine);
}
in.close();
con.disconnect(); //close the connection
```

### Reading the Response on Failed Requests

1. we can consume the stream provided by HttpUrlConnection.getErrorStream().

```java
int status = con.getResponseCode();

Reader streamReader = null;

if (status > 299) {
    streamReader = new InputStreamReader(con.getErrorStream());
} else {
    streamReader = new InputStreamReader(con.getInputStream());
}
```

### Building the Full Response

1. we can build it using some of the methods that the HttpUrlConnection instance offers

```java
public class FullResponseBuilder {
    public static String getFullResponse(HttpURLConnection con) throws IOException {
        StringBuilder fullResponseBuilder = new StringBuilder();

        // read status and message

        // read headers

        // read response content

        return fullResponseBuilder.toString();
    }
}

//First, let's add the response status information:
fullResponseBuilder.append(con.getResponseCode())
  .append(" ")
  .append(con.getResponseMessage())
  .append("\n");

//Next, we'll get the headers using getHeaderFields()

con.getHeaderFields().entrySet().stream()
  .filter(entry -> entry.getKey() != null)
  .forEach(entry -> {
      fullResponseBuilder.append(entry.getKey()).append(": ");
      List headerValues = entry.getValue();
      Iterator it = headerValues.iterator();
      if (it.hasNext()) {
          fullResponseBuilder.append(it.next());
          while (it.hasNext()) {
              fullResponseBuilder.append(", ").append(it.next());
          }
      }
      fullResponseBuilder.append("\n");
});


