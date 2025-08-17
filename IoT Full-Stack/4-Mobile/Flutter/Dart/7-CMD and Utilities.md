It can help you to run tests, and manage dependencies efficiently.

## Dart tools
- Dart SDK
- Dart command
- Pub tool
- Dart Devtools

### Dart SDK
- Developing toolchain
	- Fast incremental compilation
	- stateful hot reload
- Production toolchain
	- Fastest native output
	- Smallest runtime
It is a collection of tools and libraries that includes:
- Dart VM
- Dart core libraries
- Dart command line tools

### Dart command `dart`

It is a versatile tool for:
- Running Dart programs
- Managing packages
- Performing development tasks

``` shell
dart pub install http
dart run <script>
dart analyze -v
dart format
dart create my_project
```

### Pub tool
It is the dart package manager
- Manage dependencies
- Publish packages

Which edit the pubspec.yaml file

``` shell
dart pub add http
dart pub get
dart pub upgrade
```

and you can publish your repo by using

``` shell
dart pub publish
```

### Dart dev tools
It is a suite of performance and debugging tools, relevant for Dart and Flutter applications
- Provides a web-based interface to helps analyze and optimize your code.

Features:
- Performance profiling
	- Monitior application in real-time
	- Identify bottlenecks
	- Optimize code
	- Provide details insights into CPU and memory usage.
- Memory analysis
	- Inspect memory usage
	- Help detect memory leaks
	- Optimize memory consumption
	- Track allocations
	- Analyze memory graphs
	- Take snapshots to compare memory states.
- Widget instpector 
	- provides a visual representation of the widget tree
	- Simplifies the process of understanding and debugging UI

## Third-party tools
- Shell scripting
- Makefiles
- Continuous integration (CI)

