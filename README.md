# Expo Linking.getInitialURL() returns null on Android

This repository demonstrates a bug in Expo's `Linking` API where `Linking.getInitialURL()` returns `null` on Android, even when a deep link is used to launch the app. This makes it challenging to reliably handle deep links in Android applications built with Expo.

## Problem
The issue lies in the inconsistency of `Linking.getInitialURL()`. In certain situations, especially when the app is launched via a deep link, it inexplicably returns `null`, preventing the app from processing the intended deep link.

## Solution
The provided solution addresses this issue by using a more robust and reliable approach to handling deep links that considers potential delays and ensures proper retrieval of the initial URL. It is essential to handle the `null` return value gracefully to prevent unexpected app behavior. More importantly, it uses a more reliable mechanism for processing the initial URL in a delayed way. 

## How to Reproduce
1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the app on an Android device or emulator.
4. Attempt to open a deep link to the app. Observe that the `getInitialURL` method may return null.
5. Switch to the `FixedDeepLinkHandling.js` and re-run the app. Observe the better handling of this scenario.