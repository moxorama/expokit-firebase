## ExpoKit + react-native-firebase integration

### SDK 33

The main problem is that ExpoKit contains firebase libraries, and you should
specify exactly the same versions as ExpoKit uses to avoid 'jar hell'.

All library versions are crafted and I sharing result for everyone.

**I didn't execute `react-native link react-native-firebase`***

**package.json**
"react-native-firebase": "5.4.0"

**android/app/build.gradle**

- firebase-core version from ExpoKit
```
implementation "com.google.android.gms:play-services-base:16.1.0"
implementation "com.google.firebase:firebase-core:16.0.3"
```

**android/build.gradle**

- Gradle version the same as ExpoKit uses

```
classpath 'com.android.tools.build:gradle:3.3.2'
classpath 'com.google.gms:google-services:4.2.0'
```

**Podfile**

```
pod 'Firebase/Core','6.3.0'
pod 'GoogleIDFASupport', '~> 3.14.0'
```



Commits

- iOS: https://github.com/moxorama/expokit-firebase/commit/0d9199dac4178bda3a15e672e804b2dccdb2fcd7
- Android: https://github.com/moxorama/expokit-firebase/commit/b251aa02915f145ffeb80348ad42d2940421e56b
