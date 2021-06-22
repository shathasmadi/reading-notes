![img](https://www.dorusomcutean.com/wp-content/uploads/2020/03/crud.jpg)

## Status Codes Based On REST Methods
1. 100’s =
 These are informational status codes; they usually tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client.
2. 200’s =
hese are the success codes. They tell the client that its request was accepted. In case of asynchronous processing of a request (202), this doesn’t mean the request was successfully processed only that it met all validation requirements at the time of sending.



3. 300’s =
These are redirection codes. They tell the client that the resource they are requesting isn’t available at the expected location anymore. This can have multiple reasons, be temporary or permanent, but the client has to issue a request to the new location.


4. 400’s =
These are the client error codes. They are all about invalid requests a client sent to a server. There are several causes to this, timeouts, wrong URI, missing authentication, etc. A client is sending incorrect input and should confirm the input parameters are correct before retrying the request.


5. 500’s =
These are the server error codes. Often they indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server. 

### what  is a status code 202?
The HTTP 201 Created success status response code indicates that the request has succeeded and has led to the creation of a resource. 

### what  is a status code 308?
08 Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore. It’s helpful when we have multiple endpoints for one resource, but don’t want to implement reading from all of them.

### what  code would you use if an update didn’t return data to a client?
204 No Content 
### what  code would you use if a resource used to exist but no longer does?
307 Temporary Redirect
### what  is the ‘Forbidden’ status code?
The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource

### Why do we need to pull our MongoDB database string out of our server and put it into our .env?
for security
### what is middleware?
Middleware is software that provides common services and capabilities to applications outside of what’s offered by the operating system. Data management, application services, messaging, authentication, and API management are all commonly handled by middleware.
### what does app.use(express.json()) do?
express. json() is a method inbuilt in express to recognize the incoming Request Object as a JSON Object. This method is called as a middleware in your application using the code: app. ... urlencoded() is a method inbuilt in express to recognize the incoming Request Object as strings or arrays
### what does the /:id mean in a route?

The Route ID is a number which uniquely identifies the route. The name or title of a route is NOT unique. So if you want to refer to a specific route to mention a problem in an email, you better provide the Route ID.

### what is the difference beween PUT and PATCH?
The main difference between the PUT and PATCH method is that the PUT method uses the request URI to supply a modified version of the requested resource which replaces the original version of the resource, whereas the PATCH method supplies a set of instructions to modify the resource
### How do you make a defalut value in a schema?
`const Distribution = new Schema({`
   ` temporalCoverage: {`
       ` startDate: {type: Date, default: Date.now},`
      `  endDate: {type: Date, default: Date.now}`
  `  },`
  `  distributionText: String`
`});`
### what does a 500 error status code mean?
The HyperText Transfer Protocol (HTTP) 500 Internal Server Error server error response code indicates that the server encountered an unexpected condition that prevented it from fulfilling the request. This error response is a generic "catch-all" response.
### what is the difference between a status 200 and a status 201?
201: means successfully created an object.

200: means everything was successful but which make the 201 more spicific to say that you created something so when we are using the post route we always want to make sure to send 201 when we are successful instead 200.s a result, a resource has been created (for example a new page).