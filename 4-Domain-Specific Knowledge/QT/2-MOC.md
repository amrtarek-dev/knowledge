Qt **MOC** (Meta-Object Compiler) is a code generator tool provided by the Qt framework.

It processes Qt-specific extensions to C++ to enable features like **signals and slots**, **dynamic properties**, **runtime type information**, and **object introspection**.

## How it works
``` cpp
class MyClass : public QObject {
    Q_OBJECT // Mandatory for MOC processing

public:
    explicit MyClass(QObject *parent = nullptr);

signals:
    void mySignal();

public slots:
    void mySlot();
};
```
When you define a class with the `Q_OBJECT` macro, the MOC processes the header file of the class.
- It generates a `.moc` file containing the necessary meta-object code.
- The generated code is compiled along with your application.
- **qmake**: Automatically includes the MOC step when the `Q_OBJECT` macro is detected in your source files.
- **CMake**: Modern Qt projects using CMake handle MOC generation using the `AUTOMOC` feature.

## Generated Code
The MOC-generated file includes:
- Code to register signals, slots, and properties.
- Implementation of methods for Qt's runtime mechanisms.


Standard C++ does not natively support dynamic features like signals and slots or runtime property systems.

MOC bridges this gap by extending C++ in a way that integrates seamlessly with the language.

## Q_OBJECT
There are 2 things:
- Q_OBJECT Macro
- QObject class

QObject is the base class that Qt use to add different features support like (Signal and slots)
Q_OBJECT is the way that QT insert the Meta-Object system.

### QObject class
https://doc.qt.io/qt-6/qobject.html
this is the core class that you need to be added to use the rest of features for Qt.


### Q_OBJECT macro
https://doc.qt.io/qt-6/qobject.html#Q_OBJECT
It  must appear in the private section of a class definition that declares its own signals and slots or that uses other services provided by Qt's meta-object system


## Meta-object system
https://doc.qt.io/qt-6/metaobjects.html
Qt's meta-object system provides the signals and slots mechanism for inter-object communication, run-time type information, and the dynamic property system.

The meta-object system is based on three things:
1. the **QObject** class provides a base class for objects that can take advantage of the meta-object system.
2. the **Q_OBJECT** macro inside the private section of the class declaration is used to enable meta-object features, such as dynamic properties, signals and slots.
3. the **Meta-Object Compiler (MOC)** supplies each QObject subclass with the necessary code to implements meta-object features.