# Read 31 : Espresso

### Packages

 * espresso-core - Contains core and basic View matchers, actions, and assertions. See Basics and Recipes.
 * espresso-web - Contains resources for WebView support.
 * espresso-idling-resource - Espresso's mechanism for synchronization with background jobs.
 * espresso-contrib - External contributions that contain DatePicker, RecyclerView and Drawer actions, accessibility checks, and CountingIdlingResource.
 * espresso-intents - Extension to validate and stub intents for hermetic testing.
 * espresso-remote - Location of Espresso's multi-process functionality.

***


### Record UI interactions
* To start recording a test with Espresso Test Recorder, proceed as follows:**

1. Click Run > Record Espresso Test.
2. In the Select Deployment Target window, choose the device on which you want to record the test. If necessary, create a new Android Virtual Device. Click OK.
3. Espresso Test Recorder triggers a build of your project, and the app must install and launch before Espresso Test Recorder allows you to interact with it. The Record Your Test window appears after the app launches, and since you have not interacted with the device yet, the main panel reads "No events recorded yet." Interact with your device to start logging events such as "tap" and "type" actions.

***

### Add assertions to verify UI elements
- Assertions verify the existence or contents of a View element through three main types:**

1. text is: Checks the text content of the selected View element
2. exists: Checks that the View element is present in the current View hierarchy visible on the screen
3. does not exist: Checks that the View element is not present in the current View hierarchy

***

### Run an Espresso test locally

* To run an Espresso test, use the Project window on the left side of the Android Studio IDE:

   1. Open the desired app module folder and navigate to the test you want to run. The test’s location depends on the location of your instrumentation test root and the package name of the launched activity. The following examples demonstrate where a test would save for the Notes testing app:
       - If you are using the Android view within the window, navigate to java > com.example.username.appname (androidTest).
       - If you are using the Project view inside the window, navigate to src > androidTest > java > com.example.username.appname within the module folder.
   2. Right-click on the test and click Run ‘testName.’
       - Alternatively, you can open the test file and right-click on the generated test class or method. Read more about how to run tests on the Test Your App page.
   3. In the Select Deployment Target window, choose the device on which you want to run the test. If necessary, create a new Android Virtual Device. Click OK.
