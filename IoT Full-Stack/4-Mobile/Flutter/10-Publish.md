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

## Releasing For iOS
- Set up certificates and provisioning profiles in Xcode.
	- You need Development and distribution
	- Create a certificate signing request (CSR)
		- Open Keychain Access
		- Go to Certificate Assistant
		- Select "Request a certificate from a Certificate Authority"
		- Follow the prompts to generate your CSR file.
	- Generate certificates
		- Login to your Apple Developer account
		- Navigate to "Certificates, Identifiers, and Profiles"
		- Use your CSR to create development and distribution certificates.
		- Add certificate to your key chain
	- Generate a provisioning profile
		- Select the APP ID
		- Choose your certificates
		- Install the profile into Xcode.
- Authenticates identity and ensures app are signed.

- App Store Connect
	- Manage your app's presence on the App Store
	- Create an App Record to define your app's identity
	- Archive your app in Xcode and upload it to App Store Connect

## Releasing for Android
- App Signing
	- Play app sigining service (allows google to manage your key)
	- Or Keystore file: (Configure a keystore file in your app)
- Generate appbundle (APP)
``` bash
flutter build appbundle --release
```
AAB vs APK
- Android App Bundle (APP)
	- Google's preferred format for App distribution.
	- Google play generate APK's for your device from it.
	- Improves installation times
- Android Package Kit (APK)
	- The traditional app packaging format.
	- Less practical than APP
	- Results in larger file sizes.

- Google play Console:
	- Helps manage your app
	- Guides the app submission process
	- Sets up metadata
	- Configures distribution and pricing
	- Offers performance tracking and testing.
	- Manages updates, in-app purchases, and user behavior.
- Google Analytics
	- Integrate Google analytics to monitor user behavior
	- Leverage Firebase Analytics for seamless integration.
		- Adding Firebase to your project
		- Go to Firebase Console
		- Create a new project
		- Follow instructions to add firebase to your app
		- Add firebase_analytics to pubspec.yaml
	- It provides:
		- User demographics (User's location, gender, and interests)
		- Behavior flow (How user navigate your app, screen visited)
		- Real-time data (How user interact with your app)
		- Conversion tracking (Signup, purchases, and other call to action.)