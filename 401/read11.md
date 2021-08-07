# Read: 11 - Spring
 <!-- هو مبدأ او نموذج معماري architectural pattern يستخدم للتعامل مع واجهات المستخدم في تطبيقات -->
## [Spring App Basics](https://spring.io/guides/gs/serving-web-content/)
### Getting starting with spring:
1. [git clone](https://github.com/spring-guides/gs-serving-web-content.git)
2. cd gs-serving-web-content/initial
3. Jump ahead to [Create a Web Controller](https://spring.io/guides/gs/serving-web-content/#initial).
- When you finish, you can check your results against the code in gs-serving-web-content/complete
### Starting with Spring Initializr
- If you use Gradle, visit the [Spring Initializr](https://start.spring.io/) to generate a new project with the required dependencies (Spring Web, Thymeleaf, and Spring Boot DevTools).
### Spring Boot Devtools
To speed up this refresh cycle, *Spring Boot* offers with a handy module known as **spring-boot-devtools**. Spring Boot Devtools:
- Enables hot swapping(replace without rebooting the system).
- Switches template engines to disable caching.
- Enables LiveReload to automatically refresh the browser.
-others
### Run the Application
- @Configuration: Tags the class as a source of bean definitions for the application context.
### Test the Application
- Provide a name query string parameter by visiting http://localhost:8080/greeting?name=User.
- The **index.html** resource is special because, if it exists, it is used as a "`welcome page,"serving-web-content/ which means it is served up as the root resource (that is, at `http://localhost:8080/
- When you restart the application, you will see the HTML at http://localhost:8080/.
----
## [Spring MVC and Thymeleaf - how to access data from templates](https://www.thymeleaf.org/doc/articles/springmvcaccessdata.html)
- **@Controller classes** are responsible for preparing a model map with data and selecting a view to be rendered.
- in the case of Thymeleaf, it is transformed into a Thymeleaf context object.
### 1. Spring model attributes
Spring MVC calls the pieces of data that can be accessed during the execution of views model attributes. The equivalent term in Thymeleaf language is context variables.
- There are several ways of adding model attributes to a view in Spring MV:
1. Add attribute to Model via its **addAttribute** method:
```
@RequestMapping(value = "message", method = RequestMethod.GET)
        public String messages(Model model) {
            model.addAttribute("messages", messageRepository.findAll());
            return "message/list";
        }
```
2. Return ModelAndView with model attributes included:
```
 @RequestMapping(value = "message", method = RequestMethod.GET)
        public ModelAndView messages() {
            ModelAndView mav = new ModelAndView("message/list");
            mav.addObject("messages", messageRepository.findAll());
            return mav;
        }
```
3. Expose common attributes via methods annotated with @ModelAttribute:
```
 @ModelAttribute("messages")
        public List<Message> messages() {
            return messageRepository.findAll();
        }
```
-  in all these cases the messages attribute is added to the model and it will be available in Thymeleaf views.
- In Thymeleaf, these model attributes can be accessed with the following syntax: **{attributeName}**.
### 2. Request parameters
- Request parameters are passed from the client to server, Like :
`https://example.com/query?q=Thymeleaf+Is+Great!`
If we have @Controller that sends a redirect with a request parameter:
```
@Controller
        public class SomeController {
            @RequestMapping("/")
            public String redirect() {
                return "redirect:/query?q=Thymeleaf+Is+Great!";
            }
        }
```
- we use the `param` to access `q` parameter, using brackets syntax:
`<p th:text="${param.q[0] + ' ' + param.q[1]}" th:unless="${param.q == null}">Test</p>`
- another way, using the special `#request` object:
`<p th:text="${#request.getParameter('q')}" th:unless="${#request.getParameter('q') == null}">Test</p>`
---
- we can add `mySessionAttribute` to session, Or by using `#session`, that gives us direct access to the *javax.servlet.http.HttpSession object*.
---
### 4. ServletContext attributes
- The ServletContext attributes are shared between requests and sessions.
- and to access it we can use, `#servletContext`.
---
### 5. Spring beans
Thymeleaf allows accessing beans registered at the Spring Application Context with the `@beanName` syntax:
    `<div th:text="${@urlService.getApplicationUrl()}">...</div>`
*@urlService refers to a Spring Bean registered at your context*.