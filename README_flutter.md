# Flutter

# New Project
## First we check the installation status
```bash
# check system
flutter doctor

# fix issues
dart fix --dry-run
dart fix --apply
```

## Create project
```
flutter create <project name>

# maybe add go_router
flutter pub add go_router
```
## Rnnig flutter apps
### Install packages
```
flutter pub get
### Visual Studio shortcots
```bash
CMD + Shift + P  -> Flutter new project -> Apllication

#### FORMATING life safer
shift + options + F -> Format

# refactor (light bulb)
Command + .

```
pubspec.yaml -> basic pack specs
analysis_options.yaml  -> how strict flutter should be in the coding

### Opening simulator
```bash
# for ios
open -a simulator
```

## Firebase
## Videos docs
[You tube Cloud Firestore - Get to know](https://www.youtube.com/playlist?list=PLl-K7zZEsYLluG5MCVEzXAQ7ACZBCuZgZ)
## Install flutter
The flutter pub command will modity the pubspec.yaml
```
# for firebase
flutter pub add firebase_core
flutter pub add firebase_auth
flutter pub add cloud_firestore
flutter pub add provider
flutter pub add firebase_ui_auth
```
### Friebase cli

[firebase cli](https://firebase.google.com/docs/cli#install-cli-mac-linux)
```bash
# install firedart via dart
dart pub global activate flutterfire_clil

# install firebase tools
curl -sL https://firebase.tools | bash

# login
firebase login

# see projects
firebase projects:list

```
dart pub global activate flutterfire_cli

## Widgets
Every widget defines a `build()` method that's automatically called every time the widget's circumstances change so that the widget is always up to date.


## Classes
sliver-workshop : flutter.dev/go/sliver-workshop
https://www.youtube.com/watch?v=YY-_yrZdjGc
