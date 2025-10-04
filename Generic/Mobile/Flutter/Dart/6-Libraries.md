## dart:core
It is automatically imported. (imported by default)
- Provides essential building block for coding
- Handles basic data types, collections, and utility functions.

``` dart
void main() {
	String greeting = 'Hello, Dart';
	int number = 42;
	List<String> fruits = ['Apple', 'Banana', 'Cherry'];
	Map<String, int> scores = {'Alice': 90, 'Bob': 85};

	print(greeting);
	print(number);
	print(fruits);
	print(scores);
}
```

## dart:math
- Cosine and Sine functions
- pi and e constants
- Random number generation
- Probability-based and statistical calculations

``` dart
import 'dart:math'
const double e = 2.718;

void main() {
	double angel = pi / 4;
	Random random = Random();
	int randomNumber = random.nextInt(100);
}
```

## dart:async
- Creates asynchronous code including stream and future classes.
- Helps perform multiple tasks involve delays without blocking other operaitons.
- `Futures` are values are accessible in the future.
	- Essential for asynchronous operations like fetching online data or carrying out lengthy computations.
- `Await` keyword pauses execution until the Future completes.
- `Streams` Are a series of asynchronous events that manage data flows from users or servers, you can subscribe to stream and react to individual events.

``` dart
import 'dart:async';

void main () async {
	Futures<String> fetchData() async {
		await Future.delayed(Duration(seconds: 2));
		return 'Data fetched!';
	}

	String data = await fetchData();
	print(data);
}
```

## dart:convert
- Provides converters for UTF-8 and JSON
- Helps apps communicate with APIs
- Connects Dart objects with external systems

``` dart
import 'dart:convert';
String jsonString = '{"name": "Alice", "Age": 30}';
Map<String, dynamic> user = jsonDecode(jsonString);

Map<String, dynamic> newUser = {'name': 'Bob', 'age': 25};
String newJsonString = jsonEncode(newUser);
```


## Http Package
- contains high level classes and functions
- simplifies HTTP connections
- Downloads or transfers data
- Interacts with RESTful APIs

``` dart
import 'package:http/http.dart' as http
void main() async {
	var url = Uri.parse('https://amrtarek.dev/json/posts/1');
	var response = await http.get(url);
	
	if (response.statusCode = 200) {
		print('Response data: ${response.body}');
	} else {
		print('Request failed with status: ${response.statusCode});
	}
}
```

## intl package
- Provides localization and internationalization support
- Helps apps adapt to different regions.

``` dart
import 'package:intl/intl.dart';

void main() {
	var now = DateTime.now();
	var formatter = DateFormat('yyyy-MM-dd');
	String formattedDate = formatter.format(now);
	print('Formatted date: $formattedDate');
}
```

## path package
- Provides splitting, joining and normalizing
- Manipulates files and directory paths.

``` dart
import 'package:path/path.dart';

void main() {
	var fullpath = p.join('directory', 'file.txt');
	print('Full path: $fullPath');
}
```

## custom package
- encapsulates reusable code
- Boosts maintainability and modularity

Creating a library file
``` dart
library math_utils;

int add(int a, int b) {
	return a + b;
}

int subtract(int a, int b) {
 return a - b;
}

double divide(double a, double b) {
	if (b == 0) {
		throw ArgumentError('Cannot divide by zero');
	}
	return a / b;
}
```

using the library file

``` dart
import math_utils.dart;

void main() {
	int sum = add(10, 5);
	print('Sum: $sum');
}
```