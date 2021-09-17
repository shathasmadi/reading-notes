# Read 41 : Intent Filters

## Allowing Other Apps to Start Your Activity 
- If your app can perform an action that might be useful from another app, your app should be prepared to respond to action requests by specifying the appropriate intent filter in your activity.

`To allow other apps to start your activity, you need to add an <intent-filter> element in your manifest file for the corresponding <activity> element.`


### Add an Intent Filter
**Action / data / Category**

### Handle the Intent in Your Activity

```
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    setContentView(R.layout.main);

    // Get the intent that started this activity
    Intent intent = getIntent();
    Uri data = intent.getData();

    // Figure out what to do based on the intent type
    if (intent.getType().indexOf("image/") != -1) {
        // Handle intents with image data ...
    } else if (intent.getType().equals("text/plain")) {
        // Handle intents with text ...
    }
}
```

### Return a Result

```
// Create intent to deliver some kind of result data
Intent result = new Intent("com.example.RESULT_ACTION", Uri.parse("content://result_uri"));
setResult(Activity.RESULT_OK, result);
finish();
```
- You must always specify a result code; `RESULT_OK or RESULT_CANCELED`. 

