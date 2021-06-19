# Read: Class 11 Authentication

## [What is OAuth](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)

1. What is OAuth?
    - OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential

1. Give an example of what using OAuth would look like.
    -  when you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s logon. You then click on the button linked to the other website, the other website authenticates you.

1. How does OAuth work? What are the steps that it takes to authenticate the user?
    - The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.

    - The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.

    - The first site gives this token and secret to the initiating user’s client software.

    - The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).

    - If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.

    - The user approves (or their software silently approves) a particular transaction type at the first website.

    - The user is given an approved access token (notice it’s no longer a request token).

    - The user gives the approved access token to the first website.

    - The first website gives the access token to the second website as proof of authentication on behalf of the user.

    - The second website lets the first website access their site on behalf of the user.

    - The user sees a successfully completed transaction occurring.

    - OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. In fact, many authentication systems, notably Kerberos, work similarly. What is special about OAuth is its ability to work across the web and its wide adoption. It succeeded with adoption rates where previous attempts failed (for various reasons).


1. What is OpenID?
    - OpenID is about authentication, OpenID is for humans logging into machines.

## [Authorization and Authentication flows](https://auth0.com/docs/flows)

1. What is the difference between authorization and authentication?
    - authentication is the process of verifying who a user is, while authorization is the process of verifying what they have access to.

1. What is Authorization Code Flow?
    - exchanges an Authorization Code for a token.

1. What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
    - The PKCE-enhanced Authorization Code Flow introduces a secret created by the calling application that can be verified by the authorization server; this secret is called the Code Verifier. Additionally, the calling app creates a transform value of the Code Verifier called the Code Challenge and sends this value over HTTPS to retrieve an Authorization Code. 

1. What is Implicit Flow with Form Post?
    - Implicit Flow with Form Post flow uses OIDC to implement web sign-in that is very similar to the way SAML and WS-Federation operates. The web app requests and obtains tokens through the front channel, without the need for secrets or extra backend calls. With this method, you don’t need to obtain, maintain, use, and protect a secret in your application.

1. What is Client Credentials Flow?
    - Client Credentials Flow pass along their Client ID and Client Secret to authenticate themselves and get a token.

1. What is Device Authorization Flow?
    - Device Authorization Flow pass along their Client ID to initiate the authorization process and get a token.
    -  the device asks the user to go to a link on their computer or smartphone and authorize the device. This avoids a poor user experience for devices that do not have an easy way to enter text.

1. What is Resource Owner Password Flow?
    - requests that users provide credentials (username and password), typically using an interactive form. Because credentials are sent to the backend and can be stored for future use before being exchanged for an Access Token, it is imperative that the application is absolutely trusted with this information.

