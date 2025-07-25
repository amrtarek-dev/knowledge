You should use local storage for the web-client operations and local access.
- Shared preferences
- SQLite
- Hive

### Shared_preference
Different types of local storage:
- Shared Preferences (Android)
- NSUserDefaults(iOS)
For saving simple data like Key-value pairs.

Serves as browser-based local storage for:
- User setting
- App configurations

### SQLite
For more complex save use SQLite
SQLite is a powerful database solution that helps developers manage complex data structures.
> Use Room for more control and features

### Hive
Hive is a lightweight, NoSQL database implemented with dart (built-in)
- Support fast read and write operations
- Compatibil with mobile and desktop apps

### Files
Direct files management allows to read and write files.
- ideal for downloading, saving, and retrieving media.
- Offers maximum control over file handling
- Demands careful attention for : file paths, storage permissions.

## Web client storage
Use IndexedDB to manage client-side web solution


## CRUD operations
They are a set of functions to manage data:
- Create
- Read
- Update
- Delete

``` dart
// Saving data
prefs.setInt('counter', 10);
// Retrieveing data
int counter = prefs.getInt('counter') ?? 0;
// Deleting data
prefs.remove('counter');
```

### Serialization and deserialization
Using JSON format for encoding and decoding

``` dart
import 'dart:convert';

Map userMap = jsonDecode(jsonString);
var user = User.fromJson(userMap);
```

### Integrating with state management

``` dart
class UserProvider with ChangeNotifier {
	User _user;
	User get user => _user;

	void loadUser() {
		String userJson = storage.getItem('user');
		_user = User.fromjson(jsonDecode(userJson));
		notifyListeners();
	}
}
```


## Examples

``` dart
// file: lib/student_model.dart
class Student {
  final int id;
  final String firstName;
  final String lastName;
  final int age;
  final String major;

  Student({this.id, required this.firstName, required this.lastName, required this.age, required this.major});

  factory Student.fromJson(Map<String, dynamic> json) {
    return Student(
      id: json['id'],
      firstName: json['firstName'],
      lastName: json['lastName'],
      age: json['age'],
      major: json['major'],
    );
  }

  Map<String, dynamic> toJson() {
    return {
      'id': id,
      'firstName': firstName,
      'lastName': lastName,
      'age': age,
      'major': major,
    };
  }
}
```

- `class Student`: Defines a class named `Student`.
- `final`: Fields are immutable.
- `factory Student.fromJson`: A factory constructor for creating a `Student` instance from a map.
- `Map<String, dynamic> toJson()`: A method to convert a `Student` instance to a map.


involves creating a provider for managing the state of student data in your app. The provider will include functions to add, remove, and update students.

``` dart
// file: lib/student_provider.dart
import 'package:flutter/material.dart';
import 'student_model.dart';

class StudentProvider with ChangeNotifier {
  List<Student> _students = [];

  List<Student> get students => _students;

  void addStudent(Student student) {
    _students.add(student);
    notifyListeners();
  }

  void removeStudent(int id) {
    _students.removeWhere((student) => student.id == id);
    notifyListeners();
  }

  void updateStudent(Student updatedStudent) {
    var index = _students.indexWhere((student) => student.id == updatedStudent.id);
    if (index != -1) {
      _students[index] = updatedStudent;
      notifyListeners();
    }
  }
}
```

- `class StudentProvider with ChangeNotifier`: A class to manage the list of students.
- `notifyListeners()`: Notifies listeners about changes to rebuild the UI.
- Methods to add, remove, and update student data in the provider's list.

involves creating a screen to add or edit student details. You will implement form fields to capture student information.

``` dart
// file: lib/edit_student_screen.dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'student_model.dart';
import 'student_provider.dart';

class EditStudentScreen extends StatefulWidget {
  final Student? student;

  const EditStudentScreen({Key? key, this.student}) : super(key: key);

  @override
  _EditStudentScreenState createState() => _EditStudentScreenState();
}

class _EditStudentScreenState extends State<EditStudentScreen> {
  final TextEditingController _firstNameController = TextEditingController();
  final TextEditingController _lastNameController = TextEditingController();
  final TextEditingController _ageController = TextEditingController();
  final TextEditingController _majorController = TextEditingController();

  @override
  void initState() {
    super.initState();
    if (widget.student != null) {
      _firstNameController.text = widget.student!.firstName;
      _lastNameController.text = widget.student!.lastName;
      _ageController.text = widget.student!.age.toString();
      _majorController.text = widget.student!.major;
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.student == null ? 'Add Student' : 'Edit Student'),
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: <Widget>[
            TextField(
              controller: _firstNameController,
              decoration: InputDecoration(labelText: 'First Name'),
            ),
            TextField(
              controller: _lastNameController,
              decoration: InputDecoration(labelText: 'Last Name'),
            ),
            TextField(
              controller: _ageController,
              keyboardType: TextInputType.number,
              decoration: InputDecoration(labelText: 'Age'),
            ),
            TextField(
              controller: _majorController,
              decoration: InputDecoration(labelText: 'Major'),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: () => _saveStudent(context),
              child: Text('Save Student'),
            ),
          ],
        ),
      ),
    );
  }

  void _saveStudent(BuildContext context) {
    final student = Student(
      id: widget.student?.id ?? DateTime.now().millisecondsSinceEpoch,
      firstName: _firstNameController.text,
      lastName: _lastNameController.text,
      age: int.parse(_ageController.text),
      major: _majorController.text,
    );
    if (widget.student == null) {
      Provider.of<StudentProvider>(context, listen: false).addStudent(student);
    } else {
      Provider.of<StudentProvider>(context, listen: false).updateStudent(student);
    }
    Navigator.pop(context);
  }

  @override
  void dispose() {
    _firstNameController.dispose();
    _lastNameController.dispose();
    _ageController.dispose();
    _majorController.dispose();
    super.dispose();
  }
}
```

develop the home screen that lists all students. Each student's information will be displayed, and you can navigate to the edit screen by tapping on a student.

``` dart
// file: lib/home_screen.dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'student_model.dart';
import 'student_provider.dart';
import 'edit_student_screen.dart';

class HomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Student List'),
      ),
      body: Consumer<StudentProvider>(
        builder: (context, provider, child) {
          return ListView.builder(
            itemCount: provider.students.length,
            itemBuilder: (context, index) {
              final student = provider.students[index];
              return ListTile(
                title: Text('${student.firstName} ${student.lastName}'),
                subtitle: Text('Age: ${student.age} - Major: ${student.major}'),
                onTap: () {
                  Navigator.push(
                    context,
                    MaterialPageRoute(
                      builder: (context) => EditStudentScreen(student: student),
                    ),
                  );
                },
              );
            },
          );
        },
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          Navigator.push(
            context,
            MaterialPageRoute(
              builder: (context) => EditStudentScreen(),
            ),
          );
        },
        child: Icon(Icons.add),
        tooltip: 'Add Student',
      ),
    );
  }
}
```

- Uses `Consumer<StudentProvider>` to listen to student list updates
- Implements a `ListView.builder` to render each student as a list item
- Defines a floating action button to navigate to the `EditStudentScreen` for adding a new student
  
Add local storage to the project
``` shell
flutter pub add localstorage
```

``` dart
import 'package:localstorage/localstorage.dart';

Future<void> main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await initLocalStorage();
  runApp(MyApp(localStorage: localStorage));
}

class MyApp extends StatelessWidget {
  final LocalStorage localStorage;

  const MyApp({Key? key, required this.localStorage}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    // Wrap the MaterialApp with the ChangeNotifierProvider
    return ChangeNotifierProvider<StudentProvider>(
      create: (_) => StudentProvider(storage: localStorage),
      child: MaterialApp(
        title: 'Student Management App',
        home: HomeScreen(), // Assuming HomeScreen leads to EditStudentScreen
      ),
    );
  }
}
```

### Change the provider to work with local storage instead of memory

Add a function to load students from local storage:
``` dart
  void _loadStudentsFromStorage() async {
    var data = storage.getItem('students');
    if (data != null) {
      _students = List<Student>.from((jsonDecode(data) as List)
          .map((item) => Student.fromMap(item as Map<String, dynamic>)));
      notifyListeners();
    }
  }


  void _saveToStorage() {
    storage.setItem('students',
        jsonEncode(_students.map((student) => student.toMap()).toList()));
  }


void addStudent(Student student) {
    _students.add(student);
    _saveToStorage();
    notifyListeners();
  }

  void deleteStudent(int id) {
    _students.removeWhere((element) => element.id == id);
    _saveToStorage();
    notifyListeners();
  }

  void updateStudent(Student student) {
    var index = _students.indexWhere((element) => element.id == student.id);
    if (index != -1) {
      _students[index] = student;
      _saveToStorage();
      notifyListeners();
    }
  }
```