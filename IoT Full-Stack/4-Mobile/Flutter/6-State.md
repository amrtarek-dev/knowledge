State Management is a core concept in any interactive application that:
- Ensure a seamless user experience
- Keep data consistent
- Provides optimal performance

### What is state
It is mainly data, representing information which is used to create UI to represent the current state.
So if the data changed Flutter refreshing the UI to align with the new state.

there are 2 types of states in flutter:
1. Ephemeral state
	- Temp state (managed within a single widget)
	- Checkbox, Radio, ...
2. App state
	- A state needs to be shared across multiple parts of an application.
### Why using State
- To separate business logic from the UI
	- To manage a large codebase
- To optimize performance to its fullest potential
	- to avoid relying on setState() for every small widget update.

## State management techniques
`setState()`
The simplest way is using `setState()` which will rebuild the full UI in case of change.
- Available in StatefulWidget

``` dart
class Counter extends StatefulWidget {
	@override
	_CounterState createState() => _CounterState();
}

class _CounterState extends State<Counter> {
	int _conunter = 0;

	void _incrementCounter() {
		setState(() {
			_counter++;
		});
	}

	@override
	Widget build(BuildContext context){
		return Scaffold(
			appBar: AppBar(title: Text('Counter')),
			body: Center(
				child: Column(
					mainAxisAlignment: MainAxisAlignment.center,
					children: <Widget>[],
				),
			),
		);
	}
}
```

`InheritedWidget`
It is used for more complex state management.
- Allows passing data down the widget tree and reacts to changes.


``` dart
class MyInheritedWidget extends InheritedWidget {
	final int data;
	MyInheritedWidget({required this.data, required Widget child}) : super(child: child);

	@override
	bool updateShouldNotify(covariant MyInheritedWidget oldWidget) {
		return oldWidget.data != data;
	}

	static MyInheritedWidget? of (BuildContext context) {
		return context.dependOnInheritedWidgetofExactType<MyInheritedWidget>();
	}
}
```