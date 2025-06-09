
### Flow Control
if
```dart
if (num == 0){
	print("Zero");
} else if (num == 1){
	print("One");
} else {
	print("Unkown")
}
```

Switch Case
```dart
int number = 0;

switch(number) {
	case 0:
		print("zero");
		break;
	case 1:
		print("One");
		break;
	default:
		print("Unknown");
}
```

Loop
There are 5 loop types in dart:
```dart
// standard for loop
for (var i = 1; i <= 10; ++i) {
	print(i); //1,2,3,4,5,6,6,7,8,9,10
}

// for in loop
var numbers = [1,2,3];
for (var n in numbers){
	print(n); //1,2,3
}

// for each loop
// it takes another function as a parameter
void printNum(n){
	print(n)
}
numbers.forEach( printNum ); //1,2,3
numbers.forEach( (n) => print(n) ); //1,2,3


// while loop
int num = 5;
while(num > 0) {
	print(num);
	num -= 1;
}

// do while
do{
	print(num);
	num -= 1;
} while (num >0);
```
