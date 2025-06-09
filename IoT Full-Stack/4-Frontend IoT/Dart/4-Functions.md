
### Functions
function is an object of class Function


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
