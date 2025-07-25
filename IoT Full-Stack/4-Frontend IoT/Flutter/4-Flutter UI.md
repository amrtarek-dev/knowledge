
## Styles
Styles change the appearance of widgets
`TextStyle`
``` dart
Text(
'Hello, Flutter!',
style: TextStyle(
    fontSize: 24,
    fontWeight: FontWeight.bold,
    color: Colors.blue,
  ),
),
```

#### Theme
Themes help apply consistent style across multiple widgets.
To use the Theme you have to define the `ThemeData` class

``` dart
theme: ThemeData(
  primarySwatch: Colors.blue,
  textTheme: TextTheme(
    bodyText2: TextStyle(
      fontSize: 18,
      color: Colors.black87
      ),
    ),
),
```



## User Interaction
- Input widgets
- Gesture detectors

Widgets like 
- buttons interact by the onPressed function
- TextField -> TextEditingController -> InputDecoration (Appearance)

Gestures like:
- swipes
- taps,
- long presses

can be detected by:
- GestureDetector
- InkWell
- Dismissible
Which provide callbacks for different types of gesture


## Navigation
Navigation Components
3 types of navigation

Navigation is the process of moving between different screens or pages.

- Built-in elements:
	- Navigator (widget that manages a stack of pages)
	- Drawer widgets (slide in menu for navigation)

### Navigation types
1. Stack navigation
2. Tab navigation
3. Drawer navigation

Stack Navigation
Similar to a stack of cards, 
- Transitions between pages or screens by stacking
- new screens push current screens to the stack
- Top screen is removed when going back
> Good for Linear flow

``` dart
Navigator.push(
context, 
MaterialPageRoute(builder:(context) => ProductDetailScreen(Product: product)),
);
```

Tab navigation:
Enabling users to switch between different sections or views swiftly without losing their current content.

- Using TabBar, TabBarView

Drawer navigation
The side menu slides out from the side of the screen


## Routing
Defines the best navigation between screens
- Each screen is a route stop

Flutter provide 2 routing:
- CupertinoPageRoute (IOS UX)
- MaterialPageRoute (Android UX)

There are 2 methods to defining routes:
1. named route
2. Direct route
### Named route

Which provide a centralised and structured navigation approach by naming each route.
Which serve as a unique identifiers, and offer better code readability and simplified navigation.

``` dart
void main() {
  runapp(MaterialApp(
    initialRoue: '/',
    routes: {
      '/': (context) => HomeScreen(),
      '/second': (context) => ScondScreen(),
    },
  ));
}
```
And to navigate to the second screen

``` dart
Navigator.pushNamed(context, '/second');
```

## Direct route

To push screen
``` dart
Navigator.push(
  context,
MaterialPageRoute(builder: (context) => SecondScreen())
);
```
To get back from screen
``` dart
Navigator.pop(context);
```


Another way to route is replacing the current screen with another one rather than pushing it to the stack.

``` dart
Navigator.pushReplacement(
  context,
  MaterialPageRoute(builder:(context) => NewScreen()),
);
```