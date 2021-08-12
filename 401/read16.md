# Read:16 - Spring Authentication

## [Spring Security overview](https://spring.io/guides/topicals/spring-security-architecture/)

### Authentication and Access Control

1. Spring Security has an architecture that is designed to separate authentication from authorization and has strategies and extension points for both.
1. Authentication

   - An `AuthenticationManager` can do one of 3 things in its authenticate() method:
     - Return an Authentication (normally with authenticated=true) if it can verify that the input represents a valid principal.
     - Throw an AuthenticationException if it believes that the input represents an invalid principal.
     - Return null if it cannot decide.
   - An `AuthenticationProvider` is a bit like an `AuthenticationManager`, but it has an extra method to allow the caller to query whether it supports a given Authentication type
   - An AuthenticationManager hierarchy using ProviderManager
   

1. Customizing Authentication Managers

   - The most commonly used helper is the `AuthenticationManagerBuilder`: for setting up in-memory, JDBC, or LDAP user details or for adding a custom `UserDetailsService`
   - In a Spring Boot application, you can `@Autowired` the global one into another bean, but you cannot do that with the local one unless you explicitly expose it yourself.
   - Spring Boot provides a default global `AuthenticationManager` (with only one user) unless you pre-empt it by providing your own bean of type `AuthenticationManager`

1. Authorization or Access Control

   - the core strategy for authorization is `AccessDecisionManager`
   - An `AccessDecisionVoter` considers an `Authentication` (representing a principal) and a secure `Object`, which has been decorated with `ConfigAttributes`
   - `Object` represents anything that a user might want to access (a web resource or a method in a Java class are the two most common cases).
   - Most people use the default `AccessDecisionManager`, which is `AffirmativeBased` (if any voters return affirmatively, access is granted).

1. Web Security

   - Spring Security in the web tier (for UIs and HTTP back ends) is based on Servlet Filters
   
   - a filter can veto the rest of the chain if it wants to handle the request itself. A filter can also modify the request or the response used in the downstream filters and servlet
   - The order of the filter chain is very important, and Spring Boot manages it through two mechanisms
     1. @Beans of type Filter can have an @Order or implement Ordered, and they can be part of a FilterRegistrationBean that itself has an order as part of its API.
   - A vanilla Spring Boot application with no custom security configuration has a several (call it n) filter chains, where usually n=6.

1. Creating and Customizing Filter Chains
1. Request Matching for Dispatch and Authorization

   - A security filter chain (or, equivalently, a WebSecurityConfigurerAdapter) has a request matcher that is used to decide whether to apply it to an HTTP request.
   - One of the easiest mistakes to make when configuring Spring Security is to forget that these matchers apply to different processes. One is a request matcher for the whole filter chain, and the other is only to choose the access rule to apply.

1. Combining Application Security Rules with Actuator Rules

   - If you want your application security rules to apply to the actuator endpoints, you can add a filter chain that is ordered earlier than the actuator one and that has a request matcher that includes all actuator endpoints.

1. Method Security
   - @PreAuthorize and @PostAuthorize, which let you write expressions containing references to method parameters and return values, respectively.

### Working with Threads

1. Spring Security is fundamentally thread-bound, because it needs to make the current authenticated principal available to a wide variety of downstream consumers.

1. If you need access to the currently authenticated user in a web endpoint, you can use a method parameter in a @RequestMapping, as follows:

```java
@RequestMapping("/foo")
public String foo(@AuthenticationPrincipal User user) {
  ... 
}
```

1. Processing Secure Methods Asynchronously
   - Since the SecurityContext is thread-bound, if you want to do any background processing that calls secure methods (for example, with @Async), you need to ensure that the context is propagated.

## [Spring Auth cheat sheet](https://github.com/codefellows/seattle-java-401d2/blob/master/SpringAuthCheatSheet.md)

1. Step 1: set up a user model and repo
2. Step 2: create a controller for that model
3. Step 3: UserDetailsServiceImpl implements UserDetailsService
4. Step 4: ApplicationUser implements UserDetails
5. Step 5: WebSecurityConfig extends WebSecurityConfigurerAdapter
6. Step 6: registration page
7. Step 7: login page
