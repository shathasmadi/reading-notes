# Read: 17 - Spring Authorization

### Spring Boot and OAuth2

1. creating new project: create a Spring Boot application, which can be done in a number of ways. The easiest is to go to https://start.spring.io and generate an empty project (choosing the "Web" dependency as a starting point).

2. Add a Home Page: In your new project, create index.html in the src/main/resources/static folder.\

3. Securing the Application with GitHub and Spring Security: To make the application secure, you can simply add Spring Security as a dependency. Since you’re wanting to do a "social" login (delegate to GitHub), you should include the Spring Security OAuth 2.0 Client starter.

4. Add a New GitHub App: To use GitHub’s OAuth 2.0 authentication system for login, you must first Add a new GitHub app.
Select "New OAuth App" and then the "Register a new OAuth application" page is presented. Enter an app name and description. Then, enter your app’s home page, which should be http://localhost:8080, in this case. Finally, indicate the Authorization callback URL as http://localhost:8080/login/oauth2/code/github and click Register Application.

5. Add a Welcome Page: 
* Conditional Content on the Home Page: To render content on the condition that the user is authenticated, you have the option of either server-side or client-side rendering.
* Making the Home Page Public: There’s one final change you’ll need to make. This app will now work fine and authenticate as before, but it’s still going to redirect before showing the page. To make the link visible, we also need to switch off the security on the home page by extending WebSecurityConfigurerAdapter.

6. Add a Logout Button:
* Client Side Changes: in the "authenticated" section of the UI, we add the button, and then we provide the logout() function that it refers to in the JavaScript.
* Adding a Logout Endpoint.

