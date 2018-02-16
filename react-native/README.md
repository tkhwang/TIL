# React Native

## Android

```
> SDK location not found. Define location with sdk.dir in the local.properties file or with an ANDROID_HOME environment variable.
```

[React Native android build failed. SDK location not found - Stack Overflow](https://stackoverflow.com/questions/32634352/react-native-android-build-failed-sdk-location-not-found)

- Create a file called local.properties with this line:

```
sdk.dir = /Users/USERNAME/Library/Android/sdk
```

