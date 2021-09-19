# Read 42: Location

- **With the Google Play services location APIs:**
    - Your app can request the last known location of the user's device. 

- **The fused location provider** -> is one of the location APIs in Google Play services. that provides a simple API and optimizes the device's use of battery power.

- So, How to make a single request for the location of a device using the **getLastLocation()** method in the fused location provider??

## 1. Set up Google Play services

Download and install the Google Play services component via the SDK Manager and add the library to your project. 


## Specify app permissions


## Create location services client

In your activity's **onCreate()** method, create an instance of the Fused Location Provider Client as the following:

```
private FusedLocationProviderClient fusedLocationClient;

// ..

@Override
protected void onCreate(Bundle savedInstanceState) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);
}
```

## Get the last known location

- To request the last known location, call the `getLastLocation()` method. 

```
fusedLocationClient.getLastLocation()
        .addOnSuccessListener(this, new OnSuccessListener<Location>() {
            @Override
            public void onSuccess(Location location) {
                // Got last known location. In some rare situations this can be null.
                if (location != null) {
                    // Logic to handle location object
                }
            }
        });
```

- The location object may be null in the following situations:
1. Location is turned off in the device settings, because disabling location also clears the cache.

2. The device never recorded its location, like a new device or a device that has been restored to factory settings.

3. Google Play services on the device has restarted.


## Choose the best location estimate

The `FusedLocationProviderClient` provides several methods to retrieve device location information, you can use any of them:
1. `getLastLocation()` gets a location estimate more quickly and minimizes battery usage.

2. `getCurrentLocation()` gets a fresher, more accurate location.

- If your app calls `requestLocationUpdates()`, your app can sometimes consume large amounts of power if location isn't available, or if the request isn't stopped correctly after obtaining a fresh location.

