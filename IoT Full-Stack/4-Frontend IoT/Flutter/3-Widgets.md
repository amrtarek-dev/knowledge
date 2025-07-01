Flutter widgets are built using a modern framework that takes inspiration from [React](https://react.dev/).

https://docs.flutter.dev/ui


``` dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Hello World Web',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Hello World Web App'),
        ),
        body: Center(
          child: Text(
            'Hello World',
            style: TextStyle(fontSize: 24),
          ),
        ),
      ),
    );
  }
}
```

Every UI in the flutter is a widgets

- **MaterialApp**: Wraps the entire app and provides material design styling.
- **Scaffold**: Provides a basic structure, including an `AppBar` and a `Body`.
- **AppBar**: Displays the title of the application.
- **Center**: Aligns the "Hello World" text to the center of the screen.
- **Text**: Displays the "Hello World" message with a font size of 24.
## SCAFFOLD
Scaffold widget is a class in flutter which provide many widgets like:
- AppBar
- Drawer
- Floating Action Button
- Bottom Navigation Bar
- Snack Bar
- .....
So Scaffold will expand or occupy the whole device screen, it will provide the framework to implement the basic material design layout of the application.

