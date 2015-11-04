# cordova-plugin-media

Variant of cordova-plugin-media with audio focus management.
    
## Installation

    cordova plugin add https://github.com/FmeuMan/cordova-plugin-media

## Supported Platforms with audio focus

- Android
- iOS

## Media.requestFocus
Request audio focus.

    Media.requestFocus(options, successCallback);
# Parameters
 * __successCallback__ - _function(boolean)_ : called when focus request is granted or refused. The boolean parameter will be set to true of false if focus is granted or not.
 * __options__ - _{focusMode: string}_ :
    * __focusMode = 'gain'__: give full focus to the application, muting other apps (default mode on ios)
    * __focusMode = 'mix'__ : play the sounds while other apps can play sounds too (default mode on android)
    * __focusMode = 'duck'__ : lower volume of other apps

## Media.releaseFocus
Release audio focus if any

    Media.releaseFocus();

__NOTE__ : Other app may not resume playing sounds depending on how their audio focus management if implemented. This is specialy true for full focus ('gain' focusMode).

## media.play
Starts or resumes playing an audio file.

    media.play(options);
# Parameters
 * __options__ - _{focusMode: string, autoReleaseFocus: boolean}_ :
    * __focusMode__ : same as _Media.requestFocus_
    * __autoReleaseFocus__ : automaticaly release focus after media play

### iOS Quirks
Focus is released on _media.release()_
