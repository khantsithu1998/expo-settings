# @khantsithu/expo-settings

[![npm version](https://badge.fury.io/js/expo-settings.svg)](http://badge.fury.io/js/expo-settings.svg)
[![npm total downloads](https://img.shields.io/npm/dt/expo-settings.svg)](https://img.shields.io/npm/dt/expo-settings.svg)
[![npm monthly downloads](https://img.shields.io/npm/dm/expo-settings.svg)](https://img.shields.io/npm/dm/react-native-jsi-device-info.svg)
[![npm weekly downloads](https://img.shields.io/npm/dw/expo-settings.svg)](https://img.shields.io/npm/dw/expo-settings.svg)

It is a native module developed in accordance with the official Expo tutorial and tested with Expo Modules API 1.0: JSI & Fabric native modules with idiomatic Swift & Kotlin API..

[Expo Tutorial: Creating a native module](https://docs.expo.dev/modules/native-module-tutorial/)


### Add the package to your npm dependencies

```
npm install @khantsithu/expo-settings
```

### Configure for Expo

Expo-Settings likely requires Expo SDK 46+.

```sh
expo install expo-build-properties
```
Add the `expo-build-properties` plugin to your `app.json`/`app.config.js`,
setting the deployment target to `13.0` (or higher):

```js
export default {
  plugins: [
    [
      "expo-build-properties",
      {
        ios: {
          deploymentTarget: "13.0",
        },
      },
    ],
  ],
};
```

Then, you'll need to rebuild your dev client. Expo-Settings will not work in Expo Go.

```sh
npx expo prebuild --clean
npx expo run:ios
```
### Configure for Plain React Native

```sh
pod install
```



## Contribute

```sh
yarn build
cd example
npx expo run:ios # do this again whenever you change native code
```

You can edit the iOS files in `ios/`, and then update the JS accordingly in
`src`.

## Thanks
Special thanks to [Fernando Rojo](https://twitter.com/FernandoTheRojo) for the Twitter thread, as well as the Expo Team for developing the Expo Modules API.

Expo Modules made this so easy to build, and all with Swift and Kotlin