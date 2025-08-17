
It is a reusable block of code that perform a specific task
function is an object of class Function

## User defined functions
```dart
//return_type function_name(function_argument){
// body 
//}

void showOutput(var msg){
	print(msg);
}

dynamic square(var number){
	return number * number;
}

// Short formula for function by (arrow function) =>
dynamic square(var number) => number * number;

// Anonymous function (function whithout name) (Lamda)
var list = ['apples', 'bananas'];
list.forEach( (item) {print(item);} ); // forEach takes a function

// There is 2 arguments types
dynamic sum(var num1, var num2) => num1 + num2;
// Positional parameter
print(sum(1,2)); // 3
// Named parameter
print(sum(num2:2, num1:1)); //3


// Optional Parameter by name {}
// it should always called by name
dynamic sum(var num1, {var num2}) => num1 + (num2 ?? 0);
dynamic sum(var num1, {var num2 = 0}) => num1 + num2;
print(sum(1, num2: 2)); // 3
print(sum(1)); // 1

// Optional Parameter by postion []
dynamic sum(var num1, var num2]) => num1 + (num2 ?? 0);
print(sum(1,2)); // 3
print(sum(1)); // 1
```

## Special functions

Main is a special function that dart search for it to start the app
``` dart
void main() {

}
```


### Arrow functions
for short functions
``` dart
int square(int x) => x * x;
```


### Anonymous functions
- Ideal for short operations.
- Offers flexibility in various scenarios
- Promotes clean code for complex programs.

``` dart
void main() {
	var list = ['apples', 'bananas', 'oranges'];
	list.forEach((item) {print(item)});
}
```

## Function parameters 
- Providing default values
- Naming specific arguments

there are 4 types of parameters:
- Required
- Optional
- Named
- Default

#### Required (by default)
Must be provided when calling the function
- positional

``` dart
int multiply(int a, int b) {
	return a * b;
}
```

### Optional `[]`

- Either positional or named
- Omit some arguments when calling a function
If the optional parameters are not passed they will be `null`
``` dart
Stirng fullname (String firstName, [String? middleName, String? lastName]) {
	return '$firstName ${middleName ?? ''} ${lastName ?? ''}';
}
```
> `??` are called null coalescing operator, is used to provide a default empty string if middle name or last name are null (it used to return the value of lift if it is not null otherwise return the value on the right) 


### Named `{}`
- Specified using curl braces
- Required or default values
``` dart
void greet({required String name, String greeting = 'Hello'}) {
	print('$greeting, $name!');
}

void main() {
	greet(name: 'Alice'); // Hello, ALice!
	greet(name: 'Bob', greeting: 'Hi'); // Hi, Bob!
}
```

## Methods
Methods are functions that are associated with an object. 
They are defined within a class and can operate on instances of that class. methods are used to perform actions on the data contained within the objects.

``` dart
List<String> fruits = ['Apple', 'Banana', 'Cherry'];
fruits.add('Data');
fruits.remove('Banana');
bool hasApple = fruits.contains('Apple');
```

## CLosures and Lexical scope
Allows functions to capture and store references to variables.
Variables remain accessible to the function

``` dart
Function makeAdder(int addBy) {
	return (int i) => addBy + i;
}

void main() {
	var add2 = makeAdder(2);
	var add5 = makeAdder(5);
	print(add2(3)); // Output: 5
	print(add5(3)); // Output: 8
}
```