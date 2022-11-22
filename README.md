# @khantsithu/expo-settings

It is a native module developed in accordance with the official Expo tutorial and tested with Expo Modules API 1.0: JSI & Fabric native modules with idiomatic Swift & Kotlin API..

[Expo Tutorial: Creating a native module](https://docs.expo.dev/modules/native-module-tutorial/)


### Add the package to your npm dependencies

npm
```
npm install @khantsithu/expo-settings
```
or

Yarn
```
yarn add @khantsithu/expo-settings
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

You must install expo-modules if they are not already installed.

```sh
npx install-expo-modules
```

and

```sh
cd ios
pod install
```

### Usage and Example Code
```tsx
import * as Settings from 'expo-settings';
import * as React from 'react';
import { Button, Text, View } from 'react-native';

export default function App() {
  const [theme, setTheme] = React.useState<string>(Settings.getTheme());

  React.useEffect(() => {
    const subscription = Settings.addThemeListener(({ theme: newTheme }) => {
      setTheme(newTheme);
    });
   
    return () => subscription.remove();
  }, [setTheme]);

  // Toggle between dark and light theme
  const nextTheme = theme === 'dark' ? 'light' : 'dark';

  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Text>Theme: {Settings.getTheme()}</Text>
      <Button title={`Set theme to ${nextTheme}`} onPress={() => Settings.setTheme(nextTheme)} />
    </View>
  );
}
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