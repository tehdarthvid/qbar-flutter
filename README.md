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

1. [done] install Flutter toolchain for Android [[journey]](#installing-the-flutter-toolchain)
1. [done] create, build, run on Android phone, and play around with basic app
1. [done] implement Basic Specs via any means
1. [ongoing] add camera zooming functionality

## The Journal

### Installing The Flutter Toolchain

#### Steps That Got Things Going:

1. [install dart](https://dart.dev/get-dart)
   1. `brew tap dart-lang/dart`
   1. `brew install dart`
1. [install Flutter](https://flutter.dev/docs/get-started/install)
   1. `git clone https://github.com/flutter/flutter.git -b stable`  
      Because I didn't want to install from the zip.
   1. add `flutter/bin` to `$PATH`  
      `export PATH="$PATH:[PATH_TO_FLUTTER_GIT_DIRECTORY]/flutter/bin"`
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
   1. it installs the Android SDK
   1. it also installs haxm
   1. check if a patch is available
1. check `./tools/bin/sdkmanager` from Android Studio SDK folder  
   _This part has a story and a lesson! [See below](#missing-a-big-yellow-box)._
   1. if `flutter doctor` can't find `sdkmanager`, check "Android SDK Tools (obsolete)" See ["Warning" box](https://flutter.dev/docs/get-started/install/macos#install-android-studio).
1. accept Android license
   1. `flutter doctor --android-licenses`

#### Missing a Big Yellow Box

I have no prior experience to any form of mobile app development. It was easy enough to get started on [Expo](https://expo.io/), but I really wanted to try Flutter. Got guidance from [How to install Flutter on macOS using homebrew and asdf](https://dev.to/0xdonut/how-to-install-flutter-on-macos-using-homebrew-and-asdf-3loa), but not everything worked as is.

The experience will likely change over time, but right now you _really_ have to pay attention to warning labels or you'll go though some very avoidable pain when installing the toolchain on MacOS Catalina 10.15.3 during April Fools', 2020.

Most items were just time consuming due to downloads and building, bur rather straightforward. The headache came when `flutter doctor` couldn't find `sdkmanager`, which one would assume should be part of the Android Studio installation. [Well, it was, but not quite](https://knowyourmeme.com/memes/well-yes-but-actually-no). So I checked what Android Studio installed, since it installed a bunch of things already, including the Android SDK. One would assume an item labelled "Android SDK Command-line Tools (latest)" or "Andorid SDK Build-Tools" would also include the needed `sdkmanager`, but they weren't. I tried customizing the various paths on the env vars, Android Studio, and Flutter config, to no avail. I also tried installing the standalone sdkmanager, which didn't work either.

Eventually stumbled on [this](https://stackoverflow.com/questions/60467477/android-sdk-tools-option-is-missing-from-sdk-manager-in-android-studio-3-6-1), which prompted me to install the "Android SDK Tools (obsolete)" version, which is hidden unless you uncheck "Hide Obsolete Packages". This, and using Java 8 (which was noted [here](https://dev.to/0xdonut/how-to-install-flutter-on-macos-using-homebrew-and-asdf-3loa)), got things working.

Looking at the Flutter [MacOS installation instructions](https://flutter.dev/docs/get-started/install/macos) again just to see _why_ I had to go through all that agony, I somehow glossed over the [_big, friggin', "Warning" box_](https://flutter.dev/docs/get-started/install/macos#install-android-studio) that describes how to avoid exactly the Penrose Stairs I just went through!  
(°ㅂ°╬)... (ʘдʘ╬)!!!

Perhaps the real solution was I shouldn't have tried doing all this on April Fools'! ┐(￣ヘ￣ )┌
