# React Native

## [react-community/create-react-native-app: Create a React Native app on any OS with no build config.](https://github.com/react-community/create-react-native-app)

```
  yarn start
    Starts the development server so you can open your app in the Expo
    app on your phone.

  yarn run ios
    (Mac only, requires Xcode)
    Starts the development server and loads your app in an iOS simulator.

  yarn run android
    (Requires Android build tools)
    Starts the development server and loads your app on a connected Android
    device or emulator.

  yarn test
    Starts the test runner.

  yarn run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!
```    

## `react-native run-android`

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

## Clear React Native Cache

[React Native Clear Cache](https://gist.github.com/jarretmoses/c2e4786fd342b3444f3bc6beff32098d)

```bash
$ watchman watch-del-all && rm -rf $TMPDIR/react-* && rm -rf node_modules/ && npm cache clean && npm install && npm start -- --reset-cache
```
