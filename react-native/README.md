# React Native

## 구분 

- Expo : Pure javascript 로서 native mode 사용하지 않아서 개발이 편함.
- `create-react-native-app` 
  - Default 는 expo
  - `eject` 하면 `react-native CLI` 와 같이 native android, iOS 파일 분리하여 빌드할 수 있음.
- `react-native CLI`



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

## Common

### Class 내의 method function execute

[javascript - How to call method inside the same class in ReactJS? - Stack Overflow](https://stackoverflow.com/questions/38081154/how-to-call-method-inside-the-same-class-in-reactjs)

```javascript
export default class LoginCard extends React.Component {
    constructor(props) {
        super(props);
        this.handleLoginBtnClicked = this.handleLoginBtnClicked.bind(this);
        this.checkInputValidation = this.checkInputValidation.bind(this);
    }

    //This is the method handleLoginBtnClicked
    handleLoginBtnClicked() {
        ...
    }

    //This is the method checkInputValidation 
    checkInputValidation() {
        ...
    }

    ...
    ..
    .
}
```


## Android


### CRNA ejected profile android build error

[BUILD FAILED - Task 'installDebug' not found in root project 'android'. · Issue #608 · react-community/create-react-native-app](https://github.com/react-community/create-react-native-app/issues/608)

i have hacked node_modules/react-native/local-cli/runAndroid/runAndroid.js with

```
    } else {
      gradleArgs.push('installDevDebug');
    }
```

so it runs in installDevDebug instead of installDebug.


### App 실행 시 권한 부족 Error

[Android - java.lang.SecurityException: Permission Denial: starting Intent - Stack Overflow](https://stackoverflow.com/questions/19829507/android-java-lang-securityexception-permission-denial-starting-intent)

```
BUILD SUCCESSFUL

Total time: 33.902 secs
Running /Users/tkhwang/Library/Android/sdk//platform-tools/adb -s ce0917198d1420280c7e reverse tcp:8081 tcp:8081
Starting the app on ce0917198d1420280c7e (/Users/tkhwang/Library/Android/sdk//platform-tools/adb -s ce0917198d1420280c7e shell am start -n host.exp.exponent/host.exp.exponent.MainActivity)...
Starting: Intent { cmp=host.exp.exponent/.MainActivity launchParam=MultiScreenLaunchParams { mDisplayId=0 mBaseDisplayId=0 mFlags=0 } }
java.lang.SecurityException: Permission Denial: starting Intent { flg=0x10000000 cmp=host.exp.exponent/.MainActivity launchParam=MultiScreenLaunchParams { mDisplayId=0 mBaseDisplayId=0 mFlags=0 } } from null (pid=11236, uid=2000) not exported from uid 10218
        at android.os.Parcel.readException(Parcel.java:1704)
        at android.os.Parcel.readException(Parcel.java:1654)
        at android.app.ActivityManagerProxy.startActivityAsUser(ActivityManagerNative.java:3626)
        at com.android.commands.am.Am.runStart(Am.java:663)
        at com.android.commands.am.Am.onRun(Am.java:392)
        at com.android.internal.os.BaseCommand.run(BaseCommand.java:51)
        at com.android.commands.am.Am.main(Am.java:125)
        at com.android.internal.os.RuntimeInit.nativeFinishInit(Native Method)
        at com.android.internal.os.RuntimeInit.main(RuntimeInit.java:315)
```




