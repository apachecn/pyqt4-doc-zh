# QAbstractFileEngineHandler Class Reference

## [[QtCore](index.htm) module]

该QAbstractFileEngineHandler类提供了一种方法来注册自定义文件引擎与应用程序。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QAbstractFileEngineHandler)`
*   `QAbstractFileEngine create (self, QString fileName)`

* * *

## Detailed Description

该QAbstractFileEngineHandler类提供了一种方法来注册自定义文件引擎与应用程序。

QAbstractFileEngineHandler是一个工厂，用于创建[QAbstractFileEngine](qabstractfileengine.html)对象（文件引擎），其中在内部使用[QFile](qfile.html)，[QFileInfo](qfileinfo.html)和[QDir](qdir.html)与文件和目录工作时。

当你打开一个文件， Qt的由传递文件名选择一个合适的文件引擎[QFile](qfile.html) or [QDir](qdir.html)通过注册的文件引擎处理程序的内部列表。第一个处理程序，以识别文件名用于创建引擎。 Qt提供内部文件的发动机与常规文件和资源的工作，但你也可以注册你自己的[QAbstractFileEngine](qabstractfileengine.html)子类。

要安装应用程序特定的文件引擎，你继承QAbstractFileEngineHandler和重新实现[create](qabstractfileenginehandler.html#create)（ ） 。当你实例化处理程序（例如，通过对栈或堆上创建一个实例） ，它会自动与Qt注册。 （最新注册的处理程序的优先级高于现有的处理程序。 ）

例如：

```
 class ZipEngineHandler : public QAbstractFileEngineHandler
 {
 public:
     [QAbstractFileEngine](qabstractfileengine.html) *create(const [QString](qstring.html) &fileName) const;
 };

 [QAbstractFileEngine](qabstractfileengine.html) *ZipEngineHandler.create(const [QString](qstring.html) &fileName) const
 {
     // ZipEngineHandler returns a ZipEngine for all .zip files
     return fileName.toLower().endsWith(".zip") ? new ZipEngine(fileName) : 0;
 }

 int main(int argc, char **argv)
 {
     [QApplication](qapplication.html) app(argc, argv);

     ZipEngineHandler engine;

     MainWindow window;
     window.show();

     return app.exec();
 }

```

当处理程序被破坏，它会自动在Qt中删除。

最常用的方法注册一个处理程序来创建一个实例作为应用程序的启动阶段的一部分。另外，也可以对文件引擎的处理程序的范围限制到感兴趣的特定区域（例如，需要自定义文件引擎的特殊文件对话框）。通过创建一个内部的局部范围的处理程序，可以精确地控制在你的引擎将不会令人不安的文件操作可以应用在你的应用程序的其他部分的面积。

* * *

## Method Documentation

```
QAbstractFileEngineHandler.__init__ (self)
```

构造一个文件处理程序，并使用Qt注册它。一旦创建了这个处理程序的[create](qabstractfileenginehandler.html#create)（）函数将所用的任何路径被称为（连同所有其它的处理程序） 。最近创建的处理程序，识别给定的路径（即返回[QAbstractFileEngine](qabstractfileengine.html)）被用于新的路径。

**See also** [create](qabstractfileenginehandler.html#create)（ ） 。

```
QAbstractFileEngineHandler.__init__ (self, QAbstractFileEngineHandler)
```

```
QAbstractFileEngine QAbstractFileEngineHandler.create (self, QString fileName)
```

[

这种方法是抽象的，应在任何子类中重新实现。

创建一个文件引擎文件_fileName_。返回0，如果这个文件处理程序无法处理_fileName_。

例如：

](qabstractfileengine.html)

```
 QAbstractSocketEngine *ZipEngineHandler.create(constQString &fileName) const
 {
     // ZipEngineHandler returns a ZipEngine for all .zip files
     return fileName.toLower().endsWith(".zip") ? new ZipEngine(fileName) : 0;
 }

```

**See also** [QAbstractFileEngine.create](qabstractfileengine.html#create)（ ） 。