# Read 36 : Cognito

## [Amplify and Cognito](https://docs.amplify.aws/lib/auth/getting-started/)

- The Amplify Auth category provides an interface for authenticating a user. 



### Getting started

`amplify add auth`

```
? Do you want to use the default authentication and security configuration?
    `Default configuration`
? How do you want users to be able to sign in?
    `Username`
? Do you want to configure advanced settings?
    `No, I am done.`v
```

`amplify push`

- **Install Amplify Libraries**

```
dependencies {
    implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'
}
```

### Initialize Amplify Auth
- Add the Auth plugin before calling Amplify.configure. Update the code you added in Prerequisites:
```java // Add this line, to include the Auth plugin. Amplify.addPlugin(new AWSCognitoAuthPlugin()); Amplify.configure(getApplicationContext()); ```



### Links to check

- [Sign in](https://docs.amplify.aws/lib/auth/signin/q/platform/android/#multi-factor-authentication)
- [Sign in with web UI](https://docs.amplify.aws/lib/auth/signin_web_ui/q/platform/android)
- [Social sign in with web UI](https://docs.amplify.aws/lib/auth/social_signin_web_ui/q/platform/android/)