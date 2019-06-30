# QAbstractFormBuilder Class Reference

## [[QtDesigner](index.htm) module]

该QAbstractFormBuilder类为创建用户界面在运行时类的默认实现。[More...](#details)

通过继承[QFormBuilder](qformbuilder.html)。

### Methods

*   `__init__ (self)`
*   `QWidget load (self, QIODevice device, QWidget parent = None)`
*   `save (self, QIODevice dev, QWidget widget)`
*   `setWorkingDirectory (self, QDir directory)`
*   `QDir workingDirectory (self)`

* * *

## Detailed Description

该QAbstractFormBuilder类为创建用户界面在运行时类的默认实现。

QAbstractFormBuilder提供了一个标准接口，并从用户界面文件形式构造一个缺省的实现。它不适合直接实例化。使用[QFormBuilder](qformbuilder.html)类在运行时从UI文件创建用户界面。例如：

```
         MyForm.MyForm([QWidget](qwidget.html) *parent)
             : [QWidget](qwidget.html)(parent)
         {
             [QFormBuilder](qformbuilder.html) builder;
             [QFile](qfile.html) file(":/forms/myWidget.ui");
             file.open([QFile](qfile.html).ReadOnly);
             [QWidget](qwidget.html) *myWidget = builder.load(&file, this);
             file.close();

             [QVBoxLayout](qvboxlayout.html) *layout = new [QVBoxLayout](qvboxlayout.html);
             layout->addWidget(myWidget);
             setLayout(layout);
         }

```

要复盖表单生成器的行为，子类QAbstractFormBuilder的某些方面并重新实现相关的虚函数：

*   [load](qabstractformbuilder.html#load)() handles reading of UI format files from arbitrary QIODevices, and construction of widgets from the XML data that they contain.
*   [save](qabstractformbuilder.html#save)() handles saving of widget details in UI format to arbitrary QIODevices.
*   [workingDirectory](qabstractformbuilder.html#workingDirectory)() and [setWorkingDirectory](qabstractformbuilder.html#setWorkingDirectory)() control the directory in which forms are held. The form builder looks for other resources on paths relative to this directory.

该[QFormBuilder](qformbuilder.html)类通常由定制组件和嵌入应用_Qt Designer_。需要动态生成用户界面在运行时独立应用程序使用[QUiLoader](index.htm)在发现[QtUiTools](index.htm)模块。

* * *

## Method Documentation

```
QAbstractFormBuilder.__init__ (self)
```

构造一个新的表单生成器。

```
QWidget QAbstractFormBuilder.load (self, QIODevice device, QWidget parent = None)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

加载窗口小部件的XML表示从给定的_device_，并构造一个新的部件以指定的_parent_。

](qwidget.html)

[**See also**](qwidget.html) [save](qabstractformbuilder.html#save)（ ） 。

```
QAbstractFormBuilder.save (self, QIODevice dev, QWidget widget)
```

保存给定的XML表示形式_widget_到指定的_device_在标准的UI文件格式。

**See also** [load](qabstractformbuilder.html#load)（ ） 。

```
QAbstractFormBuilder.setWorkingDirectory (self, QDir directory)
```

设置表单生成器的当前工作目录到指定的_directory_。

**See also** [workingDirectory](qabstractformbuilder.html#workingDirectory)（ ） 。

```
QDir QAbstractFormBuilder.workingDirectory (self)
```

[

返回表单生成器的当前工作目录。

](qdir.html)

[**See also**](qdir.html) [setWorkingDirectory](qabstractformbuilder.html#setWorkingDirectory)（ ） 。