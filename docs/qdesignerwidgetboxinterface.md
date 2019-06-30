# QDesignerWidgetBoxInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerWidgetBoxInterface类允许您控制的Qt Designer的控件框中的内容。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `QString fileName (self)`
*   `bool load (self)`
*   `bool save (self)`
*   `setFileName (self, QString file_name)`

* * *

## Detailed Description

该QDesignerWidgetBoxInterface类允许您控制的Qt Designer的控件框中的内容。

QDesignerWidgetBoxInterface包含通常用于操纵的内容的功能的集合_Qt Designer_的小工具盒。

_Qt Designer_使用一个XML文件来填充它的部件框。该文件的名称是widget框的属性之一，你可以使用它获取的[fileName](qdesignerwidgetboxinterface.html#fileName)（）函数。

QDesignerWidgetBoxInterface还提供了[save](qdesignerwidgetboxinterface.html#save)（ ）函数用来保存小工具框中的内容由小工具框中的文件名属性中指定的文件中。如果您已经通过删除一个widget到小部件中，不调用所做的更改到窗口小部件中，例如[save](qdesignerwidgetboxinterface.html#save)（ ）函数，原来的内容，可以由一个简单的调用恢复[load](qdesignerwidgetboxinterface.html#load)（ ）函数：

```
         QDesignerWidgetBoxInterface *widgetBox = 0:
         widgetBox = formEditor->widgetBox();

         widgetBox->load();

```

该QDesignerWidgetBoxInterface类不适合直接实例化。您可以使用检索界面的Qt Designer的控件箱[QDesignerFormEditorInterface.widgetBox](qdesignerformeditorinterface.html#widgetBox)（）函数。一个指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。当实现一个自定义的widget插件，你必须在子类[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)暴露你的插件_Qt Designer_。

如果你想保存更改，并同时保留原来的内容，您可以使用[save](qdesignerwidgetboxinterface.html#save)（）函数的结合[setFileName](qdesignerwidgetboxinterface.html#setFileName)（ ）函数将更改保存到另一个文件。记得先保存原文件的名称：

```
         [QString](qstring.html) originalFile = widgetBox->fileName();

         widgetBox->setFileName("myWidgetBox.xml");
         widgetBox->save();

```

然后，你可以通过重新设置文件名与原始文件，并调用恢复小工具盒的原始内容[load](qdesignerwidgetboxinterface.html#load)（）：

```
         widgetBox->setFileName(originalFile);
         widgetBox->load();

```

以类似的方式，您可以在以后使用您的自定义XML文件：

```
         if (widgetBox->filename() != "myWidgetBox.xml") {
             widgetBox->setFileName("myWidgetBox.xml");
             widgetBox->load();
         }

```

* * *

## Method Documentation

```
QDesignerWidgetBoxInterface.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个小部件盒接口与给定的_parent_和在指定的窗口_flags_。

```
QString QDesignerWidgetBoxInterface.fileName (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回XML文件的名称_Qt Designer_目前使用填充其部件框。

**See also** [setFileName](qdesignerwidgetboxinterface.html#setFileName)（ ） 。

```
bool QDesignerWidgetBoxInterface.load (self)
```

这种方法是抽象的，应在任何子类中重新实现。

填充_Qt Designer_的小工具盒通过加载（或重新加载）当前指定的XML文件。返回True如果成功加载该文件，否则为False 。

**See also** [setFileName](qdesignerwidgetboxinterface.html#setFileName)（ ） 。

```
bool QDesignerWidgetBoxInterface.save (self)
```

这种方法是抽象的，应在任何子类中重新实现。

保存的内容_Qt Designer_在指定的文件中的小工具盒[fileName](qdesignerwidgetboxinterface.html#fileName)（）函数。返回True如果内容保存成功，否则为False 。

**See also** [fileName](qdesignerwidgetboxinterface.html#fileName)（）和[setFileName](qdesignerwidgetboxinterface.html#setFileName)（ ） 。

```
QDesignerWidgetBoxInterface.setFileName (self, QString file_name)
```

这种方法是抽象的，应在任何子类中重新实现。

设置XML文件_Qt Designer_将用于填充其部件中，以_fileName_。你必须调用[load](qdesignerwidgetboxinterface.html#load)（）来更新使用新的XML文件的小工具盒。

**See also** [fileName](qdesignerwidgetboxinterface.html#fileName)（）和[load](qdesignerwidgetboxinterface.html#load)（ ） 。