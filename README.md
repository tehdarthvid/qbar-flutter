# qbar_flutter

Flutter study via a QR/barcode scanner mobile app.

## Specs

### Basic

1. Scan QR codes
1. Scan barcodes
1. diplay the results
1. copy results to clipboard

### Additional

1. [researching] zoom camera

## The Journey

1. [done] install Flutter toolchain for Android
1. [done] create, build, run on Android phone, and play around with basic app
1. [done] implement Basic Specs via any means
1. [ongoing] add camera zooming functionality

## The Journal

### Installing The Flutter Toolchain

No prior experience to any form of mobile app development. It was easy enough to get started on [Expo](https://expo.io/), but I really wanted to try Flutter. It was wrong to expect the same ease in setting up the toolchain. :/ This was more trouble than it should be.

Got guidance from [How to install Flutter on macOS using homebrew and asdf](https://dev.to/0xdonut/how-to-install-flutter-on-macos-using-homebrew-and-asdf-3loa), but not everything worked as is.

Steps That Got Things Going:

1. [install dart](https://dart.dev/get-dart)
   1. `brew tap dart-lang/dart`
   1. `brew install dart`
1. [install Flutter](https://flutter.dev/docs/get-started/install)
   1. `git clone https://github.com/flutter/flutter.git -b stable`
      Because I didn't want to install from the zip.
   1. `export PATH="$HOME/<flutter cloned>/flutter/bin:$PATH"`
1. check installation status
   1. `flutter doctor`
      This was quite helpful in isolating what else is needed.
1. install Java 8
   The latest version of Java (14 as of writing) doesn't work.
   1. `brew cask install homebrew/cask-versions/adoptopenjdk8`
1. [install Android Studio](https://developer.android.com/studio/install)
   1. `brew cask install android-studio`
      Because I prefer things installed via Homebrew.
   1. Android Studio will download and install a bunch of stuff
   1. it also installs haxm
   1. check if a patch is available
1. check `./tools/bin/sdkmanager` from Android Studio SDK folder
   1. if `flutter doctor` can't find `sdkmanager`, check Android SDK Tools (obsolete)
1. accept Android license
   1. `flutter doctor --android-licenses`

The experience will likely change over time, but here's my experience trying to install the toolchain MacOS Catalina 10.15.3 during April Fools' 2020. (Perhaps the real solution was I shouldn't have tried doing it on April Fools'? ┐(￣ヘ￣ )┌)
