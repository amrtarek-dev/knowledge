Flutter widgets are built using a modern framework that takes inspiration from [React](https://react.dev/).
https://docs.flutter.dev/ui

Widgets helps display data and capture user input.
It is the fundamental components of hierarchical widget tree.

Types of widgets:
- **Stateless**: Immutable, do not store any state
	- Text, Icon, RaisedButton
- **Stateful**: Maintains and manages state over time
	- Checkbox, Radio, Slider

## Basic widgets
It build the core structure of an app.
- Text: `Text('Hello. Flutter!')`
- Image: `Image.network('https://example.com/image.png')`
- Icon: `Icon(Icons.star)`
- ElevatedButton: Elevated for a raised look
	- `ElevatedButton(onPressed:() {}, child: Text('Press Me'),)`
## Layout widgets
Help arrange other widgets on the screen by defining the structure and positions of the widgets.
- Column: Vertical arrangement (Stack widgets on top of one another)
	- `Column(children: <Widget>[Text('First'), Text('Second'),) ])`
- Row: Horizontal arrangement (Widgets side by side)
	- `Row(children: <Widget>[Text('First'), Text('Second'),) ])`
- Container: Groups and styles other widgets with padding, margins, borders, and so on..
	- `Container(padding: EdgeInsets.all(16.0), color: Colors.blue, child: Text('This is inside a container'),)`
- Stack: Overlaps on top of each other
	- `Stack(children: <Widget>[
	  Container(color: Color.blue, width: 100, height: 100),
	  Container(color: Color.red, width: 50, height: 50),
	  ],)`

## Input widgets
Receive user inputs such as text fields, radio buttons, and switches.
- TextField: Allows users to enter text
	- `TextField(decoration: InputDecoration(lableText: 'Enter Your name'),)`
- Checkbox: Allow multiple options selection
	- `Checkbox(value: true, onChanged: (bool? value) {},)`
- Radio: Allows single option selection
	- `Radio(value: 1, groupValue: selectValue, onChanged: (int? value) {}, )`
- Switch: Toggle between on/off states
	- `Switch(value: true, onChanged: (bool value) {},)`


Form
- Wrap TextField widgets in a Form
- Use Validators for the inputs
	- Validators are functions that return an error message string if the input is invalid or null if it is valid.
## Button widgets
Interactive elements that users can tap to trigger actions.
- ElevatedButton
- TextButton
- IconButton
- OutlinedButton
`ElevatedButton(onPressed:() {}, child: Text('Press Me'),)`

## List widgets
Display scrollable lists of items
- ListView: Display a list of widgets
	- `ListView(children: <Widget>[
	  ListTitle(leading: Icon(Icons.map), title: Text('Map'),),
	  ListTitle(leading: Icon(Icons.phone), title: Text('Phone'),),
	  ])`


> Adhere to material design guidelines
> Ensure layouts adapt to all screens
> Break large widgets into smaller chunks


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

- `import` statement is used to include the Flutter material library that provides built-in widgets to design the user interface.
- The `main` function is the entry point for every Dart application.
- `runApp` takes the provided widget (`MyApp`) and makes it the root of the
- `MyApp` is a custom widget that extends `StatelessWidget`, which is used when the widget doesn't manage any state of its own.
- `const` constructor is used here to indicate that `MyApp` is immutable.
- `build` method describes how to display the widget in the app.
- The `context` parameter provides information about the location of this widget in the widget tree.
- `MaterialApp` is a convenience widget that wraps several commonly used widgets to design a material app.
- `Scaffold` provides a framework that implements the basic material design layout structure of the visual interface.
- `AppBar` is a material design app bar that can be used to give the app a consistent look and feel at the top of the screen.
- `title` is a property to add text to the app bar.
- `Column` is a layout widget that arranges its children in a vertical direction.
- `children` property takes a list of widgets to display.
- `Text` widgets display text on the screen.

## SCAFFOLD
Scaffold widget is a class in flutter which provide many widgets like:
- AppBar
- Drawer
- Floating Action Button
- Bottom Navigation Bar
- Snack Bar
- .....
So Scaffold will expand or occupy the whole device screen, it will provide the framework to implement the basic material design layout of the application.

## Responsive UI
- Grid widget for photo grid
Flex widgets like
- Row
- Column widget for task list

For child:
- Sized box is fixed
- Expanded and Containers are dynamic.

Orientation: (Portrait/Landscape)
- use Media query to detect the orientation.