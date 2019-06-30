# QDeclarativeExtensionPlugin Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeExtensionPlugin类提供了一个抽象基自定义QML扩展插件。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `initializeEngine (self, QDeclarativeEngine engine, str uri)`
*   `registerTypes (self, str uri)`

* * *

## Detailed Description

该QDeclarativeExtensionPlugin类提供了一个抽象基自定义QML扩展插件。

QDeclarativeExtensionPlugin是一个插件接口，使得它可以创建能够动态地加载到QML应用QML扩展。这些扩展允许自定义的QML类型被提供给QML引擎。

写一个QML扩展插件：

*   Subclass QDeclarativeExtensionPlugin, implement [registerTypes](qdeclarativeextensionplugin.html#registerTypes)() method to register types using [qmlRegisterType](qdeclarativeengine.html#qmlRegisterType)(), and export the class using the [Q_EXPORT_PLUGIN2](index.htm#Q_EXPORT_PLUGIN2)() macro
*   Write an appropriate project file for the plugin
*   Create a [qmldir file](index.htm#writing-a-qmldir-file) to describe the plugin

QML扩展插件可用于提供任何特定应用程序或库类插件。图书馆插件应该限制自己注册的类型，因为任何操作引擎的根上下文可能会导致在库用户的代码冲突或其他问题。

### An example

假设有一个新`TimeModel`C + +类应该提供一个新的QML元素。它提供了在当前时间通过`hour`和`minute`属性，像这样：

```
 class TimeModel : public [QObject](qobject.html)
 {
     Q_OBJECT
     Q_PROPERTY(int hour READ hour NOTIFY timeChanged)
     Q_PROPERTY(int minute READ minute NOTIFY timeChanged)
     ...

```

为了使这个类可以作为一个QML类型，创建一个插件，注册这个类型与特定的[module](index.htm#qml-modules) using [qmlRegisterType](qdeclarativeengine.html#qmlRegisterType)（ ） 。在这个例子中的插件模块将被命名为`com.nokia.TimeExample`（如在下面进一步在项目文件中定义）。

```
 class QExampleQmlPlugin : public QDeclarativeExtensionPlugin
 {
     Q_OBJECT
 public:
     void registerTypes(const char *uri)
     {
         Q_ASSERT(uri == QLatin1String("com.nokia.TimeExample"));
         qmlRegisterType<TimeModel>(uri, 1, 0, "Time");
     }
 };

 Q_EXPORT_PLUGIN2(qmlqtimeexampleplugin, QExampleQmlPlugin);

```

这将注册`TimeModel`级与1.0版本的插件库，作为所谓的QML类型`Time`。该Q_ASSERT语句确保该模块是通过使用这个插件的任何QML组件正确导入。

项目文件中的项目定义为一个插件库，并指定它应该被内置到`com/nokia/TimeExample`目录：

```
 TEMPLATE = lib
 CONFIG += qt plugin
 QT += declarative

 DESTDIR = com/nokia/TimeExample
 TARGET = qmlqtimeexampleplugin
 ...

```

最后，一个[qmldir file](index.htm#writing-a-qmldir-file)是需要在`com/nokia/TimeExample`目录描述插件。此目录包含一个`Clock.qml`应该与插件捆绑在一起，因此它需要在指定的文件`qmldir`文件：

```
 Clock 1.0 Clock.qml
 plugin qmlqtimeexampleplugin

```

一旦项目建成并安装新的`Time`元素可以使用一个导入的任何QML组件`com.nokia.TimeExample`模块：

```
 import com.nokia.TimeExample 1.0 // import types from the plugin

 Clock { // this class is defined in QML (com/nokia/TimeExample/Clock.qml)

     Time { // this class is defined in C++ (plugin.cpp)
         id: time
     }

     hours: time.hour
     minutes: time.minute
 }

```

完整的源代码是可用[plugins example](index.htm)。

该[Tutorial: Writing QML extensions with C++](index.htm)还包含有关创建QML插件一章。

* * *

## Method Documentation

```
QDeclarativeExtensionPlugin.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个QML扩展插件与给定_parent_。

注意，此构造是由自动调用[Q_EXPORT_PLUGIN2](index.htm#Q_EXPORT_PLUGIN2)（）宏，所以没有必要显式地调用它。

```
QDeclarativeExtensionPlugin.initializeEngine (self, QDeclarativeEngine engine, str uri)
```

初始化扩展从_uri_使用_engine_。在这里，一个应用程序的插件可能，例如，暴露一些数据或对象，以QML ，作为发动机的根上下文上下文属性。

```
QDeclarativeExtensionPlugin.registerTypes (self, str uri)
```

这种方法是抽象的，应在任何子类中重新实现。

寄存器的QML类型在给定的_uri_。子类应该实现这个调用[qmlRegisterType](qdeclarativeengine.html#qmlRegisterType)（）为这是由扩展插件提供的所有类型。

该_uri_是一个标识符的基础上扩展的插件库的名称和路径由QML引擎生成的插件。