# Read: 27 - Intents, Activities, and SharedPreferences

## [Android Tasks and the Back Stack](https://developer.android.com/guide/components/activities/tasks-and-back-stack)

- **A task** is a collection of activities that users interact with when performing a certain job. 

- The activities are arranged in a stack—the back stack—in the order in which each activity is opened. 

- For example,
 an email app might have one activity to show a list of new messages.
  When the user selects a message, a new activity opens to view that message.
   This new activity is added to the back stack.
    If the user presses the Back button, that new activity is finished and popped off the stack.


When apps are running simultaneously in a multi-windowed environment, supported in Android 7.0 (API level 24) and higher,
 the system manages tasks separately for each window; each window may have multiple tasks.


When the current activity starts another, the new activity is pushed on the top of the stack and takes focus.
 The previous activity remains in the stack, but is stopped. When an activity stops, the system retains the current state of its user interface.
  When the user presses the Back button, the current activity is popped from the top of the stack ( destroyed) and the previous activity resumes (the previous state of its UI is restored).
   

  

If the user continues to press Back, then each activity in the stack is popped off to reveal the previous one, until the user returns to the Home screen (or to whichever activity was running when the task began). When all activities are removed from the stack, the task no longer exists.
 

### To summarize the default behavior for activities and tasks:

- When Activity A starts Activity B, Activity A is stopped, but the system retains its state (such as scroll position and text entered into forms).
 If the user presses the Back button while in Activity B, Activity A resumes with its state restored.

- When the user leaves a task by pressing the Home button, the current activity is stopped and its task goes into the background.
 The system retains the state of every activity in the task.
  If the user later resumes the task by selecting the launcher icon that began the task, the task comes to the foreground and resumes the activity at the top of the stack.
  
- If the user presses the Back button, the current activity is popped from the stack and destroyed. The previous activity in the stack is resume.

- Activities can be instantiated multiple times, even from other tasks.

---

You can use attributes in the `<activity>` manifest element and with flags in the intent that you pass to `startActivity()`.

###  `<activity>` attributes you can use are:

- `taskAffinity`
- `launchMode`
- `allowTaskReparenting`
- `clearTaskOnLaunch`
- `alwaysRetainTaskState`
- `finishOnTaskLaunch`

#### And the principal intent flags you can use are:

- `FLAG_ACTIVITY_NEW_TASK`
- `FLAG_ACTIVITY_CLEAR_TOP`
- `FLAG_ACTIVITY_SINGLE_TOP`

### Defining launch modes,ways :

1. **Using the manifest file**
When you declare an activity in your manifest file, you can specify how the activity should associate with tasks when it starts.

2. **Using Intent flags**
When you call startActivity(), you can include a flag in the Intent that declares how (or whether) the new activity should associate with the current task.


## [Android SharedPreferences](https://developer.android.com/training/data-storage/shared-preferences)

- **Shared Preferences:** Is to Save data as key-value pairs. 


### You can create a new shared preference file or access an existing one by calling one of these methods:

- **getSharedPreferences()** — Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.

- **getPreferences()** — Use this from an Activity if you need to use only one shared preference file for the activity. 

```
Context context = getActivity();
SharedPreferences sharedPref = context.getSharedPreferences(
        getString(R.string.preference_file_key), Context.MODE_PRIVATE);
```


- Alternatively, if you need just one shared preference file for your activity, you can use the getPreferences() method:

`SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);`

- **getDefaultSharedPreferences()*** to get the default shared preference file for your entire app.



Pass the keys and values you want to write with methods such as putInt() and putString(). Then call apply() or commit() to save the changes. For example:

```
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
SharedPreferences.Editor editor = sharedPref.edit();
editor.putInt(getString(R.string.saved_high_score_key), newHighScore);
editor.apply();
```

- **apply()** changes the in-memory SharedPreferences object immediately but writes the updates to disk asynchronously. Alternatively, you can use commit() to write the data to disk synchronously. 


- To retrieve values from a shared preferences file, call methods such as getInt() and getString(), providing the key for the value you want, and optionally a default value to return if the key isn't present. For example:


```
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
int defaultValue = getResources().getInteger(R.integer.saved_high_score_default_key);
int highScore = sharedPref.getInt(getString(R.string.saved_high_score_key), defaultValue);
```