# expo-firebase-instance-id

`expo-firebase-instance-id` provides access to the instance ID, and Push Token.

[**Full documentation**](https://rnfirebase.io/docs/master/iid/reference/iid)

## Installation

First, you need to install the package from `npm` registry.

`npm install expo-firebase-instance-id` or `yarn add expo-firebase-instance-id`

#### iOS

If you're using Cocoapods, add the dependency to your `Podfile`:

```ruby
pod 'EXFirebaseInstanceID', path: '../node_modules/expo-firebase-instance-id/ios'
```

and run `pod install`.

#### Android

1.  Append the following lines to `android/settings.gradle`:

    ```gradle
    include ':expo-firebase-instance-id'
    project(':expo-firebase-instance-id').projectDir = new File(rootProject.projectDir, '../node_modules/expo-firebase-instance-id/android')
    ```

    and if not already included

    ```gradle
    include ':expo-core'
    project(':expo-core').projectDir = new File(rootProject.projectDir, '../node_modules/expo-core/android')

    include ':expo-firebase-app'
    project(':expo-firebase-app').projectDir = new File(rootProject.projectDir, '../node_modules/expo-firebase-app/android')
    ```

2.  Insert the following lines inside the dependencies block in `android/app/build.gradle`:
    ```gradle
    compile project(':expo-firebase-instance-id')
    ```
    and if not already included
    ```gradle
    compile project(':expo-core')
    compile project(':expo-firebase-app')
    ```
3.  [Now follow the setup instructions in the docs.](https://rnfirebase.io/docs/master/iid/android)

## Usage

```javascript
import React from 'react';
import { View } from 'react-native';
import firebase from 'expo-firebase-app';
// Include the module before using it.
import 'expo-firebase-instance-id';
// API can be accessed with: firebase.iid();

export default class DemoView extends React.Component {
  async componentDidMount() {
    // ... initialize firebase app

    const token = await firebase.iid().getToken();
  }
  render() {
    return <View />;
  }
}
```
