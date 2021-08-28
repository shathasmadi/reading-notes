# Read: 26 - Android Fundamentals

Android apps can be written by:
1. Kotlin 
2. Java
3. C++

#### The Android SDK tools compile your code along with any data and resource files into an APK or an Android App Bundle.

### Android package:  
an archive file with an .apk suffix, contains the contents of an Android app that are required at runtime and it is the file that Android-powered devices use to install the app.

### Android App Bundle:
an archive file with an .aab suffix, contains the contents of an Android app project including some additional metadata that is not required at runtime. An AAB is a publishing format and is not installable on Android devices, it defers APK generation and signing to a later stage.

Each Android app lives in its own security sandbox, protected by the following Android security features:

* The Android operating system is a multi-user Linux system in which each app is a different user.
* By default, the system assigns each app a unique Linux user ID (the ID is used only by the system and is unknown to the app). The system sets permissions for all the files in an app so that only the user ID assigned to that app can access them.
* Each process has its own virtual machine (VM), so an app's code runs in isolation from other apps.
* By default, every app runs in its own Linux process. The Android system starts the process when any of the app's components need to be executed, and then shuts down the process when it's no longer needed or when the system must recover memory for other apps.

The Android system implements the principle of least privilege. That is, each app, by default, has access only to the components that it requires to do its work and no more. This creates a very secure environment in which an app cannot access parts of the system for which it is not given permission. However, there are ways for an app to share data with other apps and for an app to access system services:

* It's possible to arrange for two apps to share the same Linux user ID, in which case they are able to access each other's files. To conserve system resources, apps with the same user ID can also arrange to run in the same Linux process and share the same VM. The apps must also be signed with the same certificate.

* An app can request permission to access device data such as the device's location, camera, and Bluetooth connection. The user has to explicitly grant these permissions. For more information, see Working with System Permissions.

The rest of this document introduces the following concepts:

* The core framework components that define your app.
* The manifest file in which you declare the components and the required device features for your app.
* Resources that are separate from the app code and that allow your app to gracefully optimize its behavior for a variety of device configurations.

App components are the essential building blocks of an Android app. Each component is an entry point through which the system or a user can enter your app. Some components depend on others.

There are four different types of app components:

1. Activities: An activity is the entry point for interacting with the user. It represents a single screen with a user interface.
2. Services: A service is a general-purpose entry point for keeping an app running in the background for all kinds of reasons. It is a component that runs in the background to perform long-running operations or to perform work for remote processes. A service does not provide a user interface. 
3. Broadcast receivers: A broadcast receiver is a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements. Because broadcast receivers are another well-defined entry into the app, the system can deliver broadcasts even to apps that aren't currently running.
4. Content providers: A content provider manages a shared set of app data that you can store in the file system, in a SQLite database, on the web, or on any other persistent storage location that your app can access. Through the content provider, other apps can query or modify the data if the content provider allows it. 

Each type serves a distinct purpose and has a distinct lifecycle that defines how the component is created and destroyed. The following sections describe the four types of app components.

Three of the four component types—activities, services, and broadcast receivers—are activated by an asynchronous message called an intent.




