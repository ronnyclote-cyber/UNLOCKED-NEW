# UNLOCKED mobile prototype

This companion contains generated Android and iOS native projects, bundled local game assets, and Capacitor 8.5.2 dependencies pinned in package.json and pnpm-lock.yaml. The website and mobile package share the same answer-and-play game logic.

## Current status

Native project creation and web-asset synchronization are complete. No APK, Android App Bundle, IPA, signed release, native simulator or physical-device test is included. Xcode / Apple developer tools are unavailable in the creation environment, so iOS compilation could not be verified. Android compilation also remains unverified.

## Build locally

Install a supported Node.js runtime, pnpm, Xcode for iOS, and Android Studio with its required JDK and SDK for Android. Consult the current Capacitor environment requirements: https://capacitorjs.com/docs/getting-started/environment-setup

From this folder:

```sh
pnpm install --frozen-lockfile
pnpm sync
pnpm open:android
pnpm open:ios
```

Use Android Studio or Xcode to select a device, compile and test. Change the placeholder app identifier `com.example.unlocked` to an identifier owned by the publisher before signing or store submission. Register the identifier in the native projects too.

When updating the product, replace the www files with the current browser prototype's dist files, then run `pnpm sync`.

## Game flow

Both players must privately answer the same question before making a move. Reveal the answer pair only after both turns. Count the first four pairs: at least three identical answers makes the connection eligible. Both players must then privately say yes to reveal profiles and open chat. No game win or score overrides consent. A 2/4 result keeps chat locked.

The demo partner and messages are simulated; all data is held in memory. Native packaging does not add live accounts, networking, server-side eligibility enforcement, storage or moderation.

## Before store submission

Replace simulated partners with authenticated real users and authoritative server-managed turns, private answer storage and unlock checks. Add account deletion, age assurance, real reporting/blocking and moderation. Add release icons, accurate privacy disclosures, signing, device and assistive-technology testing. Follow current Apple and Google store requirements. A generated project is not a guarantee of review approval.

Capacitor documentation: https://capacitorjs.com/docs
Apple review: https://developer.apple.com/app-store/review/guidelines/
