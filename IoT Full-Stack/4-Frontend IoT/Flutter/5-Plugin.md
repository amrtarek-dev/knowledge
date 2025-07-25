It provide access to device and platform-specific functionalities.

Bridge the flutter code and the underlying platform code, to use of native features like Camera, GPS, and local storage.

- Allow reusing code for standard functionalities
- Offer consistent API across both iOS and Android.
- Community support

Examples:
- http
	- For Making HTTP requests
- shared_preferences
	- For storing simple data persistently
- firebase_core
- SQLite
- google_maps_flutter


### How to use plugins

1. Finding plugin
Flutter plugins in pub.dev, the official Dart package repository
2. Add it
Add the plugin to the pubspec.yaml file 
``` shell
flutter pub add url_launcher
```
3. Use it
To use the plugin you have to import it like
``` dart
import 'package:url_launcher/url_launcher.dart'
```


## Create a plugin
Using the CMD

``` shell
flutter create --template=plugin my_plugin
```

Then make the platform specific code by navigating to iOS and Android in the my_plugin directory

Then implement the **platform channels** to communicate between dart and native code

The after testing you can publish the plugin to pub.dev


## Managing plugin compatibility

- Version constraints
- Dependency conflicts
- Multiple platforms


Version constraints:
Ensure compatibility with the Flutter and Dart versions, by specify version constrains in the pubspec.yaml file.

Dependency conflicts
Flutter dependency resolver finds a compatible version automatically, if it fails you must manually resolve this conflicts by specifying exact version or updating dependencies.

Multiple platforms
Always test your plugin on devices or emulators to be sure it is working correctly.

``` dart
import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;
import 'dart:convert';
import 'post_model.dart';

Future<List<Post>> fetchPosts() async {
  final response = await http.get(Uri.parse('https://jsonplaceholder.typicode.com/posts'));
  if (response.statusCode == 200) {
    List jsonResponse = json.decode(response.body);
    return jsonResponse.map((post) => Post.fromJson(post)).toList();
  } else {
    throw Exception('Failed to load posts');
  }
}

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter API Lab',
      home: const PostList(),
    );
  }
}

class PostList extends StatefulWidget {
  const PostList({super.key});

  @override
  _PostListState createState() => _PostListState();
}

class _PostListState extends State<PostList> {
  late Future<List<Post>> futurePosts;

  @override
  void initState() {
    super.initState();
    futurePosts = fetchPosts();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('API Data'),
      ),
      body: FutureBuilder<List<Post>>(
        future: futurePosts,
        builder: (context, snapshot) {
          if (snapshot.connectionState == ConnectionState.waiting) {
            return const Center(child: CircularProgressIndicator());
          } else if (snapshot.hasError) {
            return Center(child: Text('Error: ${snapshot.error}'));
          } else if (snapshot.hasData) {
            return ListView.builder(
              itemCount: snapshot.data!.length,
              itemBuilder: (context, index) {
                return ListTile(
                  title: Text(snapshot.data![index].title),
                  subtitle: Text(snapshot.data![index].body),
                );
              },
            );
          } else {
            return const Center(child: Text('No data available'));
          }
        },
      ),
    );
  }
}
```

- `void main()`: The main entry point of the Flutter app. Calls `runApp(MyApp())` to start the application with the `MyApp` widget.
- `runApp(const MyApp())`: Creates and attaches `MyApp` to the screen, which sets up the basic app structure.
- `class MyApp extends StatelessWidget`: The root widget of the app. It doesn't change state; it simply defines the app's structure.
    - `MaterialApp`: Provides the core app features and sets the `home` to `PostList`, which is the main screen where data will be displayed.
- `class PostList extends StatefulWidget`: A stateful widget that allows dynamic content. Here, it is used to display data fetched from an API.
    - `@override _PostListState createState()`: Creates the mutable state for `PostList` to manage data fetching and display.
- `class _PostListState extends State<PostList>`: Manages the state for `PostList`.
    - `futurePosts = fetchPosts()`: Initiates the API call to fetch posts when the widget is initialized.
    - `FutureBuilder<List<Post>>`: Reacts to the future (`futurePosts`) and rebuilds the UI depending on the state of the data fetching (loading, error, or success).
        - Shows a loading indicator (`CircularProgressIndicator`) while waiting.
        - Displays an error message if the API call fails.
        - Uses `ListView.builder` to dynamically generate a scrollable list of posts when data is successfully fetched.

## Native Features
Provided functionalities from the operating system:
- Camera
- GPS
- File systems
- Sensors

Add camera plugin
``` shell
flutter pub add camera
```
Then you need to request permission to access the camera for Android and iOS.


### Shared_preferences plugin

``` shell
flutter pub add shared_preference
```

``` dart
import 'package:flutter/material.dart';
import 'package:shared_preferences/shared_preferences.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatefulWidget {
  const MyApp({super.key});

  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  TextEditingController _controller = TextEditingController();
  String _storedValue = '';

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Plugin Lab',
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Explore Plugins in Flutter'),
        ),
        body: Padding(
          padding: const EdgeInsets.all(16.0),
          child: Column(
            children: [
           TextField(
             controller: _controller,
             decoration: const InputDecoration(labelText: 'Enter some text'),
           ),
           const SizedBox(height: 16), // Adds space between TextField and Save button
           ElevatedButton(
             onPressed: _saveData,
             child: const Text('Save Data'),
           ),
           const SizedBox(height: 16), // Adds space between Save and Load button
           ElevatedButton(
             onPressed: _loadData,
             child: const Text('Load Data'),
           ),
           const SizedBox(height: 16), // Adds space between Load button and Text
           Text('Stored Value: $_storedValue'),
         ],
          ),
        ),
      ),
    );
  }

  void _saveData() async {
    SharedPreferences prefs = await SharedPreferences.getInstance();
    await prefs.setString('myKey', _controller.text);
  }

  void _loadData() async {
    SharedPreferences prefs = await SharedPreferences.getInstance();
    setState(() {
      _storedValue = prefs.getString('myKey') ?? 'No Data';
    });
  }
}
```