You need to:
- Proper lableling
- Packaging
- Security checks
- Updating versions
- Configuring permissions
- Testing

## Versioning
Version in flutter you can set it:
- Version number : pubspec.yaml file
- Version format : major.minor.patch+build

## App icons and splash screens
package help customize app icons and splash screens
- App icon :`flutter_launcher_icons`
- Splash screens: `flutter_native_splash`

For App icon:
add this to the `pubspec.yaml` file
``` yaml
dev_dependencies:
  flutter_launcher_icons: ^0.9.2
flutter_icons:
  android: true
  ios: true
  image_path: "assets/icon/icon.png"
```
Then run this command in shell
``` shell
flutter pub run flutter_launcher_icons:main
```

For splash screen
``` bash
flutter pub run flutter_native_splash:create
```

## App permissions
help in
- Transparency
- User security

In Android `AndroidManifest.xml` file
in iOS `Info.plist` file

## Signing the app
It is ensuring a reliable source

For Android
- Generate Keystore file
- Configure in build.gradle file

For iOS
- Managed by Xcode

## Obfuscation
it helps in making code harder to read and reverse-engieer

For Android
``` shell
flutter build apk --release --obfuscate --split-debug-info=/<directory>
```

For iOS
- Set up flags in Xcode

## Testing
Testing and debugging help run the app smoothly and without crashes.

- unit tests
``` shell
flutter test
```

- Integration testing
``` shell
Firebase test lab
```

## Release version
For Android:
``` shell
flutter build apk -release
```

For iOS
``` shell
flutter build appbundle -release
```

## Submitting to App stores

For Android
- use Google Play console
For iOS
- use app store connect