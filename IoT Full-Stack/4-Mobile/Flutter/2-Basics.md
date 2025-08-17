
## Prepare the env
After getting the Flutter SDK
you can use this command to enable web developing

``` shell
# if you have a working project
flutter config --enable-web
# will add the web support
```

To check for the available devices
``` shell
flutter devices
```

To check for the flutter environment
``` shell
flutter doctor
```

## Create a project
```bash
flutter create <project_name>
```

## Build and Debug
In vscode select the emulator from bottom right, and then press f5 button

```bash
# Clean
flutter clean
# get the packages
flutter pub get
# Run
flutter run
# To build it to specifi platform
flutter create --platform ios .
flutter create --platform web .
```
### Hello world
The minimal Flutter app simply calls the [`runApp()`](https://api.flutter.dev/flutter/widgets/runApp.html) function with a widget:

```dart
import 'package:flutter/material.dart';

void main() {
	runApp(const MyApp());
}

class MyApp extends StatelessWidget {
	const MyApp({super.key});

	@override
	Widget build(BuildContext context) {
		return const MaterialApp(
			home: home(),
		);
	}
}
```

## Flutter Design
Flutter uses material package to draw the widgets:
Design( look & feel ):
- Android widgets (Material widgets)
- IOS widgets (Cupertina widgets)

## Widgets types:
- Stateless
- Stateful
These are the main building blocks to any widgets that flutter provide.
### Stateless widgets 
- Only widget
it can not change its state during the running of the app, which means that the widget can not re-drawn while the app is in action

to create one `stl` and press tab in vscode

```dart
import "package:flutter/material.dart"; 

class SignInPage extends StatelessWidget {
	const SignInPage({super.key});
	
	@override
	Widget build(BuildContext context) {
		return const Placeholder();
	}
}
```

every widget has a build function which is responsible for building the UI of the widget
### Stateful widgets
- Widget + state
The stateful widgets has a mutable state which can redrawn while the app is running


## Flutter PLC
Flutter project lift cycle

### Planning
- Clarify Objectives
- Identify target audience
- List features
- Create wireframes

### Designing
- User Experience
- User Interface
- Sketch screen connections
- Visualize app flow
- App interface
- Arrange pre-built widgets
- Create beautiful screens
- Customize unique widgets

### Flutter environment
- Install flutter SDK (flutter.dev)
- IDE (VScode, Android studio)

### Development
1. Dart coding
2. Build UI by widgets
	1. Statless
	2. Statefull
	3. UI Widgets
3. Implement features
	1. Core features
	2. APIs and local storage
	3. Handle user inputs
	4. user Flutter and Dart packages
4. Testing and debugging
	1. unit testing
	2. widget testing
	3. Integration testing
5. Optimization
	1. Reduce app size
	2. Enhance performace
	3. Ensure compatibility
6. Deployment
	1. IOS and Play store


## Sources

[Flutter Basics by a REAL Project](https://www.youtube.com/watch?v=D4nhaszNW4o)
[Flutter Node Auth Tutorial - Email Password Login/Sign Up](https://www.youtube.com/watch?v=EuP3xycjiM4)
[FULL Food Delivery App w/ Backend • Flutter Tutorial](https://www.youtube.com/watch?v=rHIFJo4IbOE)
