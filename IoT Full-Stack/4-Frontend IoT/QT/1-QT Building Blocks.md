
- Core
	- Webkit
	- Multimedia
	- Scripting
	- XML
- GUI
	- QML
	- Database
	- QT Quick
	- Networking
- Unit Testing

## Core Component
It provides a lot of functionality including file I/O, event handling, multiple thread support, and one of the core design tools of Qt, the Signals and Slot mechanism.

## Qt UI
There are 4 ways to build a GUI by QT:
- Qt Widgets
- Qt Quick
- Qt Graphics
- Qt Web kit

### Qt Widgets

**When to Use**: Ideal for building traditional desktop applications with a native look and feel, such as file managers, text editors, or system utilities.

- **Why**: Qt Widgets provide a mature, stable, and feature-rich environment for developing applications with a classic desktop GUI layout. It integrates closely with the operating system to deliver native performance and appearance.
- **Key Features**:
    - Standard UI components like buttons, labels, and text boxes.
    - Good for detailed, non-animated UIs.
    - Fine control over widget-based layouts.
    - Native styling on multiple platforms.

### Qt Quick

**When to Use**: Best for modern, dynamic UIs, especially in mobile apps, embedded systems, and touch-based interfaces.

- **Why**: Qt Quick allows for fluid, animated, and responsive user interfaces, often required for mobile and embedded applications where touch and gestures are central. It uses QML (Qt Modeling Language), a declarative language, for rapid UI development.
- **Key Features**:
    - Fast, GPU-accelerated rendering.
    - Designed for modern, animated UIs.
    - Supports touch gestures and animations.
    - Declarative syntax (QML) for easy and fast UI design.
    - Great for mobile and IoT devices.

### Qt Graphics (Graphics View Framework)

**When to Use**: For custom 2D graphics, interactive scenes, or when you need fine control over graphic rendering in desktop applications (e.g., games, simulation, or data visualization).

- **Why**: The Qt Graphics View Framework allows you to build and manage large 2D scenes with thousands of objects. It supports zooming, panning, and custom rendering of items.
- **Key Features**:
    - 2D rendering for custom shapes, images, and animations.
    - Manageable interactive scenes (e.g., graph editors, games).
    - High-performance rendering with hardware acceleration.

### Qt WebKit (or Qt WebEngine)

**When to Use**: If your application needs to display or interact with web content, such as embedding a web browser, displaying online documentation, or building hybrid applications.

- **Why**: Qt WebKit (or the newer **Qt WebEngine**) provides a full-featured web rendering engine inside Qt apps, allowing you to display HTML, CSS, and JavaScript content seamlessly within your interface.
- **Key Features**:
    - Embed web content inside a native Qt application.
    - Support for HTML5, CSS3, and JavaScript.
    - Suitable for hybrid applications that combine native UI and web-based content.

### Summary:

- **Qt Widgets**: Use for traditional desktop apps with detailed, native-looking UIs.
- **Qt Quick**: Use for modern, dynamic, and animated UIs, especially in mobile and embedded environments.
- **Qt Graphics**: Use for custom 2D graphical interfaces, game-like scenes, or interactive data visualizations.
- **Qt WebKit (WebEngine)**: Use when you need to embed web content or build hybrid applications with web technologies.


| **Module**            | **When and Why to Use**                                                                                                                                 | **Key Features**                                                                                      |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| **Qt Widgets**         | Use for traditional desktop apps with a native look & feel (e.g., file managers, text editors) to build stable, feature-rich UIs with fine control.      | - Standard UI components (buttons, labels, etc.) <br> - Native styling <br> - Detailed, non-animated UIs |
| **Qt Quick**           | Use for modern, dynamic, and touch-based UIs (mobile apps, embedded systems) to create fluid, animated interfaces with fast development using QML.        | - GPU-accelerated rendering <br> - Touch gestures and animations <br> - Declarative syntax (QML)        |
| **Qt Graphics**        | Use for custom 2D graphics or interactive scenes (e.g., simulation, data visualization) to control 2D rendering with hardware acceleration.               | - Custom shapes and image rendering <br> - Manage interactive 2D scenes <br> - Zooming/panning support  |
| **Qt WebKit (WebEngine)** | Use when embedding web content (hybrid apps, online docs) to display HTML, CSS, and JavaScript with a full web rendering engine inside the application. | - Embed web content <br> - HTML5, CSS3, and JavaScript support <br> - Ideal for hybrid apps             |

## Qt Creator
Qt Creator is a powerful integrated development environment (IDE) designed specifically for creating applications with the Qt application framework. It supports C++, QML, and Python development and is widely used for building cross-platform software, including desktop and mobile applications.

Key features of Qt Creator include:

1. **Cross-platform support**: Develop applications for Windows, macOS, Linux, Android, and iOS from a single codebase.
2. **Code editor**: It comes with advanced code completion, syntax highlighting, and navigation tools to help you write and manage code efficiently.
3. **Form designer**: Create user interfaces visually with a drag-and-drop UI designer, which can generate the corresponding QML or C++ code.
4. **Debugger**: Integrated debugging tools that allow you to inspect and interact with running applications.
5. **Version control integration**: Built-in support for Git, Subversion, and other version control systems.
6. **Project management**: Manage complex projects with support for CMake, qmake, and other build systems.

