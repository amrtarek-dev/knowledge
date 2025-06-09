# Variables
Dart supports static and dynamic type definition,
by default all variables assigned to `null` value

### Data types
- Primitives
	- int
	- double
	- String
	- bool
	- dynamic
- Collection
	- List
	- Set
	- Map
	

Primitives
```dart
int amount1 = 100;
var amount2 = 200;
print('Amount1: $amount1 | Amount2: $amount2 \n');

double damount1 = 100.11;
var damount2 = 200.22;
print('dAmount1: $damount1 | dAmount2: $damount2 \n');

String name1 = 'Amr';
var name2 = 'Tarek';
print('Amount1: $amount1 | Amount2: $amount2 \n');

bool isItTrue1 = true;
var itItTrue2 = false;
print('isItTrue1: $isItTrue1 | itItTrue2: $itItTrue2 \n');

dynamic weakVariable = 100;
print('weakVariable 1 : $weakVariable \n');
weakVariable = 'Dart Programming';
print('weakVariable 2 : $weakVariable \n');
```

Collection
```dart
// List (Arrays), it is a class (It can have mixed types or single types)
// Dynamic type (Mixed)
List data = ['Amr', 'Tarek', 30];
print(data[0]); // Amr
print(data[1]); // Tarek
print(data.length); // 3

List <String> name = ['Amr', 'Tarek']; // only strings are allowed
name[1] = 'hello';
print(namep[1]); // hello

// to make it immutable you can use const keyword
List <String> name = const ['Amr', 'Tarek']; // only strings are allowed
name[1] = 'hello'; // Error

// By default object is copy by refernce
List <String> names = ['Amr', 'Tarek'];
var names2 = names;
print(names2[1]); // Tarek
names[1] = 'test'; // update the original one and the new one will update too.
print(names2[1]); // test

// To copy by value use [...]
var names2 = [...names];


// Set (Uniqe)
var halogens = {'flourine', 'chlorine', 'fluorine'};
print(halogens.length); // 2 (becuse it deletes the duplication)
// HashSet
var halogens = <String>{};
// or 
Set <String> names = {};  // CompactLinkedHashSet<String>

// Map (dictionary)
var gifts = {
	'first': 'Mug',
	'second': 'T-shirt'
};
var gifts = {1:'Mug', 2:'T-shirt'}

var gifts = Map();
gifts['first'] = 'Mango';

```

### Type Conversion
- strings type
	- single quote 
	- double quote
	- row string
	- multiline string
```dart
var s1 = 'test';
var s2 = "test";
var s3 = r'test \n will be printed as it is';
var s4 = ''' multi
line''';
var s5 = """ another multi
line string """;
```

- type conversion
	- You have to use the `parse` method of the type object
```dart
// String -> int
var one = int.parse('1');
assert(one == 1);

// int -> String
String oneString = 1.toString();
assert(oneString == '1');

// String -> double
var oneFloat = double.parse('1.1');
assert(oneFloat == 1.1)

// double -> String
String piString = 3.14159.toStringAsFixed(2);
assert(piString == '3.14');
```

- constant variables
```dart
const aConstNum = 0;
const aConstBool = true;
const aConstString = 'string';
```
