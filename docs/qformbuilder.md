# QFormBuilder Class Reference

## [[QtDesigner](index.htm) module]

该QFormBuilder类用于在运行时动态地构建用户界面的UI文件。[More...](#details)

继承[QAbstractFormBuilder](qabstractformbuilder.html)。

### Methods

*   `__init__ (self)`
*   `addPluginPath (self, QString pluginPath)`
*   `clearPluginPaths (self)`
*   `list-of-QDesignerCustomWidgetInterface customWidgets (self)`
*   `QStringList pluginPaths (self)`
*   `setPluginPath (self, QStringList pluginPaths)`

* * *

## Detailed Description

该QFormBuilder类用于在运行时动态地构建用户界面的UI文件。

该QFormBuilder类提供了一种机制，在运行时动态地创建用户界面的基础上，以创建UI文件_Qt Designer_。例如：

```
         MyForm.MyForm([QWidget](qwidget.html) *parent)
             : [QWidget](qwidget.html)(parent)
         {
             QFormBuilder builder;
             [QFile](qfile.html) file(":/forms/myWidget.ui");
             file.open([QFile](qfile.html).ReadOnly);
             [QWidget](qwidget.html) *myWidget = builder.load(&file, this);
             file.close();

             [QVBoxLayout](qvboxlayout.html) *layout = new [QVBoxLayout](qvboxlayout.html);
             layout->addWidget(myWidget);
             setLayout(layout);
         }

```

通过包括在该示例的资源的用户界面（`myForm.qrc`） ，我们保证这将是目前的例子运行时：

```
     <!DOCTYPE RCC><RCC version="1.0">
     <qresource prefix="/forms">
        <file>mywidget.ui</file>
     </qresource>
     </RCC>

```

QFormBuilder扩展[QAbstractFormBuilder](qabstractformbuilder.html)与一些用来支持自定义窗口小部件插件功能的基类：

*   [pluginPaths](qformbuilder.html#pluginPaths)() returns the list of paths that the form builder searches when loading custom widget plugins.
*   [addPluginPath](qformbuilder.html#addPluginPath)() allows additional paths to be registered with the form builder.
*   [setPluginPath](qformbuilder.html#setPluginPath)() is used to replace the existing list of paths with a list obtained from some other source.
*   [clearPluginPaths](qformbuilder.html#clearPluginPaths)() removes all paths registered with the form builder.
*   [customWidgets](qformbuilder.html#customWidgets)() returns a list of interfaces to plugins that can be used to create new instances of registered custom widgets.

该QFormBuilder类通常由定制组件和应用程序嵌入_Qt Designer_。需要动态生成用户界面在运行时独立应用程序使用[QUiLoader](index.htm)类，在发现[QtUiTools](index.htm)模块。

* * *

## Method Documentation

```
QFormBuilder.__init__ (self)
```

构造一个新的表单生成器。

```
QFormBuilder.addPluginPath (self, QString pluginPath)
```

通过添加指定一个新的插件路径_pluginPath_以将由表单生成器加载一个自定义的widget插件时，被搜索的路径列表。

**See also** [setPluginPath](qformbuilder.html#setPluginPath)（）和[clearPluginPaths](qformbuilder.html#clearPluginPaths)（ ） 。

```
QFormBuilder.clearPluginPaths (self)
```

清除表单生成器使用搜索自定义的widget插件路径的列表。

**See also** [pluginPaths](qformbuilder.html#pluginPaths)（ ） 。

```
list-of-QDesignerCustomWidgetInterface QFormBuilder.customWidgets (self)
```

返回的可用插件的列表。

```
QStringList QFormBuilder.pluginPaths (self)
```

返回的路径表单生成器搜索插件列表中。

**See also** [addPluginPath](qformbuilder.html#addPluginPath)（ ） 。

```
QFormBuilder.setPluginPath (self, QStringList pluginPaths)
```

的插件路径列表中设置由指定的列表_pluginPaths_。

**See also** [addPluginPath](qformbuilder.html#addPluginPath)（ ） 。