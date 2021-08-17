# Real time messaging with websockets

- **WebSocket** is a thin, lightweight layer above TCP. This makes it suitable for using `subprotocols` to embed messages.
- **STOMP** is a subprotocol operating on top of the lower-level WebSocket.

- **Gradle dependencies**:

```
dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-websocket'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
    implementation 'org.webjars:webjars-locator-core'
    implementation 'org.webjars:sockjs-client:1.0.2'
    implementation 'org.webjars:stomp-websocket:2.3.3'
    implementation 'org.webjars:bootstrap:3.3.7'
    implementation 'org.webjars:jquery:3.1.1-1'
}
```

## Create a Resource Representation Class

- The service will accept messages that contain a name in a STOMP message whose body is a JSON object.ex:

```
{
    "name": "Fred"
}
```

- Create java class with getname() method.

- Create java class with getContent() method.

- **Create a Message-handling Controller**:

```
@Controller
public class GreetingController {


  @MessageMapping("/hello")
  @SendTo("/topic/greetings")
  public Greeting greeting(HelloMessage message) throws Exception {
    Thread.sleep(1000); // simulated delay
    return new Greeting("Hello, " + HtmlUtils.htmlEscape(message.getName()) + "!");
  }

}
```

- **Configure Spring for STOMP messaging**:

```

@Configuration
@EnableWebSocketMessageBroker
public class WebSocketConfig implements WebSocketMessageBrokerConfigurer {

  @Override
  public void configureMessageBroker(MessageBrokerRegistry config) {
    config.enableSimpleBroker("/topic");
    config.setApplicationDestinationPrefixes("/app");
  }

  @Override
  public void registerStompEndpoints(StompEndpointRegistry registry) {
    registry.addEndpoint("/gs-guide-websocket").withSockJS();
  }

}
```

`@EnableWebSocketMessageBroker` enables WebSocket message handling, backed by a message broker.

- **Create a Browser Client**:
The html file will import, SockJS and STOMP javascript libraries that will be used to communicate with our server through STOMP over websocket. as shown:

```
 <script src="/webjars/sockjs-client/sockjs.min.js"></script>
    <script src="/webjars/stomp-websocket/stomp.min.js"></script>
```





