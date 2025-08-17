
### Operators
Mathematical
```dart
// Mathematical
int num = 10 + 22;
num = num % 5; // reminder
// unary
num += 2;
num *= 2;
```

Conditions
```dart
// relational  ==, !=, >=, <=
if (num = 0){
	print("Zero");
}
// Ternart
int x = 100;
var result = x % 2 == 0 ? 'Even' : 'Odd';
print(result); // Even

// is operation
if (x is int){
	print("Integer");
}
```

Logical
```dart
// And &&
// OR ||
// Not !
if (num > 200 && num < 210){
	print("Num is between 200 and 210");
}
```

Null
```dart
// Null Aware operator
// (?.), (??), (??=)

var n;
int number;
number = n?.num; // number will equal null if the n is null
number = n?.num ?? 0; // if the n is null make default value 0
number ??= 100; // assign 100 incase it was null
```
