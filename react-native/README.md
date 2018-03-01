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

아래와 같이 `ANDROID_HOME` 을 정의해두는 것이 더욱 편리.

[React Native android build failed. SDK location not found - Stack Overflow](https://stackoverflow.com/questions/32634352/react-native-android-build-failed-sdk-location-not-found)

```bash
export ANDROID_HOME=/Users/<username>/Library/Android/sdk/
export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
```