# Read 43 : Kinesis & Analytics

* The Analytics category enables you to collect analytics data for your App. The Analytics category comes with built-in support for Amazon Pinpoint and Amazon Kinesis (Kinesis support is currently only available in the Amplify JavaScript library).

### Set up Analytics backend
 * Run the following command in your project's root folder. The CLI will prompt configuration options for the Analytics category such as Amazon Pinpoint resource name and analytics event settings.
```amplify add analytics```

* To deploy your backend, run:
```
amplify push
```

### Install Amplify Libraries
* Add these lines in `dependencies`

``` 
   implementation 'com.amplifyframework:aws-analytics-pinpoint:1.24.0'
    implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'
```

### Initialize Amplify Analytics

```
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.addPlugin(new AWSPinpointAnalyticsPlugin(this));
```

#### Your class will look like this:

```
public class MyAmplifyApp extends Application {
    @Override
    public void onCreate() {
        super.onCreate();

        try {
            // Add these lines to add the AWSCognitoAuthPlugin and AWSPinpointAnalyticsPlugin plugins
            Amplify.addPlugin(new AWSCognitoAuthPlugin());
            Amplify.addPlugin(new AWSPinpointAnalyticsPlugin(this));
            Amplify.configure(getApplicationContext());

            Log.i("MyAmplifyApp", "Initialized Amplify");
        } catch (AmplifyException error) {
            Log.e("MyAmplifyApp", "Could not initialize Amplify", error);
        }
    }
}
```

### Record events

To record an event, create an AnalyticsEvent and call Amplify.Analytics.recordEvent() to send it:

```
AnalyticsEvent event = AnalyticsEvent.builder()
    .name("PasswordReset")
    .addProperty("Channel", "SMS")
    .addProperty("Successful", true)
    .addProperty("ProcessDuration", 792)
    .addProperty("UserAge", 120.3)
    .build();

Amplify.Analytics.recordEvent(event);
```

### View Analytics console

```amplify console analytics```

### Flush events

```
{
    "UserAgent": "aws-amplify-cli/2.0",
    "Version": "1.0",
    "analytics": {
        "plugins": {
            "awsPinpointAnalyticsPlugin": {
                "pinpointAnalytics": {
                    "appId": "AppID",
                    "region": "Region"
                },
                "pinpointTargeting": {
                    "region": "Region"
                },
                "autoFlushEventsInterval": 10000
            }
        }
    }
}
```

### Global Properties
You can register global properties which will be sent along with all invocations of Amplify.Analytics.recordEvent.
```
Amplify.Analytics.registerGlobalProperties(
    AnalyticsProperties.builder()
        .add("AppStyle", "DarkMode")
        .build());
```

### Disable Analytics

```Amplify.Analytics.disable();```

### Enable Analytics

```Amplify.Analytics.enable();```

