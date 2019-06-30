# QDesignerFormWindowInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerFormWindowInterface类允许你查询和操作出现在Qt Designer中的工作空间形式的窗口。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `class **[Feature](index.htm)**`
*   `enum FeatureFlag { EditFeature, GridFeature, TabOrderFeature, DefaultFeature }`

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `QDir absoluteDir (self)`
*   `addResourceFile (self, QString path)`
*   `QString author (self)`
*   `clearSelection (self, bool update = True)`
*   `QString comment (self)`
*   `QString contents (self)`
*   `QDesignerFormEditorInterface core (self)`
*   `QDesignerFormWindowCursorInterface cursor (self)`
*   `emitSelectionChanged (self)`
*   `QString exportMacro (self)`
*   `Feature features (self)`
*   `QString fileName (self)`
*   `QPoint grid (self)`
*   `bool hasFeature (self, Feature f)`
*   `QStringList includeHints (self)`
*   `bool isDirty (self)`
*   `bool isManaged (self, QWidget widget)`
*   `(int margin, int spacing) layoutDefault (self)`
*   `(QString margin, QString spacing) layoutFunction (self)`
*   `QWidget mainContainer (self)`
*   `manageWidget (self, QWidget widget)`
*   `QString pixmapFunction (self)`
*   `removeResourceFile (self, QString path)`
*   `QStringList resourceFiles (self)`
*   `selectWidget (self, QWidget widget, bool select = True)`
*   `setAuthor (self, QString author)`
*   `setComment (self, QString comment)`
*   `setContents (self, QIODevice dev)`
*   `setContents (self, QString contents)`
*   `setDirty (self, bool dirty)`
*   `setExportMacro (self, QString exportMacro)`
*   `setFeatures (self, Feature f)`
*   `setFileName (self, QString fileName)`
*   `setGrid (self, QPoint grid)`
*   `setIncludeHints (self, QStringList includeHints)`
*   `setLayoutDefault (self, int margin, int spacing)`
*   `setLayoutFunction (self, QString margin, QString spacing)`
*   `setMainContainer (self, QWidget mainContainer)`
*   `setPixmapFunction (self, QString pixmapFunction)`
*   `unmanageWidget (self, QWidget widget)`

### Static Methods

*   `QDesignerFormWindowInterface findFormWindow (QWidget w)`
*   `QDesignerFormWindowInterface findFormWindow (QObject obj)`

### Qt Signals

*   `void aboutToUnmanageWidget (QWidget *)`
*   `void activated (QWidget *)`
*   `void changed ()`
*   `void featureChanged (QDesignerFormWindowInterface::Feature)`
*   `void fileNameChanged (const QString&)`
*   `void geometryChanged ()`
*   `void mainContainerChanged (QWidget *)`
*   `void objectRemoved (QObject *)`
*   `void resourceFilesChanged ()`
*   `void selectionChanged ()`
*   `void widgetManaged (QWidget *)`
*   `void widgetRemoved (QWidget *)`
*   `void widgetUnmanaged (QWidget *)`

* * *

## Detailed Description

该QDesignerFormWindowInterface类允许你查询和操作出现在Qt Designer中的工作空间形式的窗口。

QDesignerFormWindowInterface提供有关关联的表格的窗口信息，以及允许被改变其属性。该接口不打算直接实例化，而是提供访问_Qt Designer_受控制的电流形式的窗口_Qt Designer_的[form window manager](qdesignerformwindowmanagerinterface.html)。

如果你正在寻找含有特定插件的形式窗口中，您可以使用静态[QDesignerFormWindowInterface.findFormWindow](qdesignerformwindowinterface.html#findFormWindow)（ ）函数：

```
     QDesignerFormWindowInterface *formWindow;
     formWindow = QDesignerFormWindowInterface.findFormWindow(myWidget);

```

但除此之外，你可以通过访问任何当前窗体窗口_Qt Designer_的形成窗口管理器：使用[QDesignerFormEditorInterface.formWindowManager](qdesignerformeditorinterface.html#formWindowManager)（ ）函数来检索一个接口给经理。一旦你有了这个接口，您可以访问所有的_Qt Designer_通过目前的形式窗口[QDesignerFormWindowManagerInterface.formWindow](qdesignerformwindowmanagerinterface.html#formWindow)（）函数。例如：

```
     [QList](index.htm)<QDesignerFormWindowInterface *> forms;
     QDesignerFormWindowInterface *formWindow;

     [QDesignerFormWindowManagerInterface](qdesignerformwindowmanagerinterface.html) *manager = formEditor->formWindowManager();

     for (int i = 0; i < manager->formWindowCount(); i++) {
         formWindow = manager->formWindow(i);
         forms.append(formWindow);
     }

```

指针_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。当实现一个自定义的widget插件，你必须在子类[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)类，以你的插件暴露_Qt Designer_。

一旦你的窗体窗口，就可以查询其属性。例如，一个普通的自定义窗口小部件插件是由管理_Qt Designer_只有在其顶部的水平，即没有其子控件中可以调整大小_Qt Designer_的工作空间。但QDesignerFormWindowInterface为您提供的功能，使您能够控制是否一个小部件应由管理_Qt Designer_，还是不行：

```
         if (formWindow->isManaged(myWidget))
             formWindow->manageWidget(myWidget->childWidget);

```

关于窗口管理函数的完整列表是：[isManaged](qdesignerformwindowinterface.html#isManaged)（ ）[manageWidget](qdesignerformwindowinterface.html#manageWidget)（）和[unmanageWidget](qdesignerformwindowinterface.html#unmanageWidget)（ ） 。也有一些相关的信号：[widgetManaged](qdesignerformwindowinterface.html#widgetManaged)（ ）[widgetRemoved](qdesignerformwindowinterface.html#widgetRemoved)（ ）[aboutToUnmanageWidget](qdesignerformwindowinterface.html#aboutToUnmanageWidget)（）和[widgetUnmanaged](qdesignerformwindowinterface.html#widgetUnmanaged)（ ） 。

除了控制部件的管理，可以使用控制当前选择窗体窗口的[selectWidget](qdesignerformwindowinterface.html#selectWidget)（ ）[clearSelection](qdesignerformwindowinterface.html#clearSelection)（）和[emitSelectionChanged](qdesignerformwindowinterface.html#emitSelectionChanged)（）函数，并且[selectionChanged](qdesignerformwindowinterface.html#selectionChanged)（）信号。

您还可以使用检索有关的形式存储的信息[absoluteDir](qdesignerformwindowinterface.html#absoluteDir)（） ，其包括：使用文件[includeHints](qdesignerformwindowinterface.html#includeHints)使用（） ，其布局和像素映射功能[layoutDefault](qdesignerformwindowinterface.html#layoutDefault)（ ）[layoutFunction](qdesignerformwindowinterface.html#layoutFunction)（）和[pixmapFunction](qdesignerformwindowinterface.html#pixmapFunction)（ ） 。你可以找出是否该窗体窗口已被修改（但不保存）或不使用[isDirty](qdesignerformwindowinterface.html#isDirty)（）函数。你可以检索其[author](qdesignerformwindowinterface.html#author)（） ，其[contents](qdesignerformwindowinterface.html#contents)（） ，其[fileName](qdesignerformwindowinterface.html#fileName)（ ） ，相关[comment](qdesignerformwindowinterface.html#comment)（）和[exportMacro](qdesignerformwindowinterface.html#exportMacro)（） ，其[mainContainer](qdesignerformwindowinterface.html#mainContainer)（） ，其[features](qdesignerformwindowinterface.html#features)（） ，其[grid](qdesignerformwindowinterface.html#grid)（）和其[resourceFiles](qdesignerformwindowinterface.html#resourceFiles)（ ） 。

该接口提供了功能和插槽让您可以改变其中的大部分信息，以及。唯一的例外是存储窗体窗口的目录。最后，还有一个与修改上面和在一般形式的窗口输入的信息相关联的若干信号。

* * *

## Type Documentation

```
QDesignerFormWindowInterface.FeatureFlag
```

该枚举说明可用，并且可以通过表单窗口界面进行控制的功能。查询窗体窗口时确定它所支持的功能使用这些值：

| Constant | Value | Description |
| --- | --- | --- |
| `QDesignerFormWindowInterface.EditFeature` | `0x01` | 表单编辑 |
| `QDesignerFormWindowInterface.GridFeature` | `0x02` | 网格显示和编辑捕捉到电网设施 |
| `QDesignerFormWindowInterface.TabOrderFeature` | `0x04` | 标籤订单管理 |
| `QDesignerFormWindowInterface.DefaultFeature` | `EditFeature &#124; GridFeature` | 支持预设的功能（表单编辑和网格） |

特征类型是一个typedef为[QFlags](index.htm)\u003cFeatureFlag\u003e 。它存储FeatureFlag值的或组合。

**See also** [hasFeature](qdesignerformwindowinterface.html#hasFeature)（）和[features](qdesignerformwindowinterface.html#features)（ ） 。

* * *

## Method Documentation

```
QDesignerFormWindowInterface.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个表单窗口界面与给定_parent_和在指定的窗口_flags_。

```
QDir QDesignerFormWindowInterface.absoluteDir (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回包含表格窗口中显示的形式目录的绝对位置。

```
QDesignerFormWindowInterface.addResourceFile (self, QString path)
```

这种方法是抽象的，应在任何子类中重新实现。

添加的资源文件在给定_path_那些使用的形式。

](qdir.html)

[**See also**](qdir.html) [resourceFiles](qdesignerformwindowinterface.html#resourceFiles)（）和[resourceFilesChanged](qdesignerformwindowinterface.html#resourceFilesChanged)（ ） 。

```
QString QDesignerFormWindowInterface.author (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回当前正在显示的窗口窗体的作者或创作者的详细信息。

**See also** [setAuthor](qdesignerformwindowinterface.html#setAuthor)（ ） 。

```
QDesignerFormWindowInterface.clearSelection (self, bool update = True)
```

这种方法也是一个Qt槽与C + +的签名`void clearSelection(bool = 1)`。

这种方法是抽象的，应在任何子类中重新实现。

清除当前选择窗体窗口。如果_update_是真的，[emitSelectionChanged](qdesignerformwindowinterface.html#emitSelectionChanged)（ ）函数被调用时，发光[selectionChanged](qdesignerformwindowinterface.html#selectionChanged)（）信号。

**See also** [selectWidget](qdesignerformwindowinterface.html#selectWidget)（ ） 。

```
QString QDesignerFormWindowInterface.comment (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回有关当前正在显示的窗口形式的意见。

**See also** [setComment](qdesignerformwindowinterface.html#setComment)（ ） 。

```
QString QDesignerFormWindowInterface.contents (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回当前显示在窗口中的表单的内容细节。

**See also** [setContents](qdesignerformwindowinterface.html#setContents)（ ） 。

```
QDesignerFormEditorInterface QDesignerFormWindowInterface.core (self)
```

[](qdesignerformeditorinterface.html)

[返回一个指针_Qt Designer_目前的](qdesignerformeditorinterface.html)[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象。

```
QDesignerFormWindowCursorInterface QDesignerFormWindowInterface.cursor (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回表单使用窗口光标接口。

```
QDesignerFormWindowInterface.emitSelectionChanged (self)
```

这种方法是抽象的，应在任何子类中重新实现。

](qdesignerformwindowcursorinterface.html)

[放出](qdesignerformwindowcursorinterface.html)[selectionChanged](qdesignerformwindowinterface.html#selectionChanged)（）信号。

**See also** [selectWidget](qdesignerformwindowinterface.html#selectWidget)（）和[clearSelection](qdesignerformwindowinterface.html#clearSelection)（ ） 。

```
QString QDesignerFormWindowInterface.exportMacro (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回与当前显示在窗口中的表单相关联的出口宏。导出宏时使用的形式被编译创建一个widget插件。

**See also** [setExportMacro](qdesignerformwindowinterface.html#setExportMacro)（）和[Creating Custom Widgets for Qt Designer](index.htm)。

```
Feature QDesignerFormWindowInterface.features (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](index.htm)

[返回由与该接口相关联的窗体窗口提供的功能相结合。返回的值可以对被测试](index.htm)[Feature](qdesignerformwindowinterface.html#FeatureFlag-enum)枚举值，以确定哪些功能由窗支撑。

**See also** [setFeatures](qdesignerformwindowinterface.html#setFeatures)（）和[hasFeature](qdesignerformwindowinterface.html#hasFeature)（ ） 。

```
QString QDesignerFormWindowInterface.fileName (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回描述当前正在显示的形式的用户界面的文件的文件名。

**See also** [setFileName](qdesignerformwindowinterface.html#setFileName)（ ） 。

```
QDesignerFormWindowInterface QDesignerFormWindowInterface.findFormWindow (QWidget w)
```

[

返回窗体窗口界面对于给定的_widget_。

](qdesignerformwindowinterface.html)

```
QDesignerFormWindowInterface QDesignerFormWindowInterface.findFormWindow (QObject obj)
```

[

返回窗体窗口界面对于给定的_object_。

此功能被引入Qt的4.4 。

](qdesignerformwindowinterface.html)

```
QPoint QDesignerFormWindowInterface.grid (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回所使用的表格窗口中的网格间距。

](qpoint.html)

[**See also**](qpoint.html) [setGrid](qdesignerformwindowinterface.html#setGrid)（ ） 。

```
bool QDesignerFormWindowInterface.hasFeature (self, Feature f)
```

这种方法是抽象的，应在任何子类中重新实现。

如果表单窗口提供指定的，则返回True_feature_否则返回False 。

**See also** [features](qdesignerformwindowinterface.html#features)（ ） 。

```
QStringList QDesignerFormWindowInterface.includeHints (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回将被包含在窗体窗口的相关的UI文件的头文件的列表。

头文件可以是本地的，即相对于项目的目录，`"mywidget.h"`，或全球性的， Qt的或编译器的标准库的一部分，即：`&lt;QtGui/QWidget&gt;`。

**See also** [setIncludeHints](qdesignerformwindowinterface.html#setIncludeHints)（ ） 。

```
bool QDesignerFormWindowInterface.isDirty (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果表单窗口是“脏” （已修改但尚未保存），否则返回False 。

**See also** [setDirty](qdesignerformwindowinterface.html#setDirty)（ ） 。

```
bool QDesignerFormWindowInterface.isManaged (self, QWidget widget)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果指定的_widget_由窗体窗口管理，否则返回False 。

**See also** [manageWidget](qdesignerformwindowinterface.html#manageWidget)（ ） 。

```
(int margin, int spacing) QDesignerFormWindowInterface.layoutDefault (self)
```

这种方法是抽象的，应在任何子类中重新实现。

填写默认的边距和间距在窗体的默认布局_margin_和_spacing_指定的变量。

**See also** [setLayoutDefault](qdesignerformwindowinterface.html#setLayoutDefault)（ ） 。

```
(QString margin, QString spacing) QDesignerFormWindowInterface.layoutFunction (self)
```

这种方法是抽象的，应在任何子类中重新实现。

填补了目前的利润率和间距在窗体的布局_margin_和_spacing_指定的变量。

**See also** [setLayoutFunction](qdesignerformwindowinterface.html#setLayoutFunction)（ ） 。

```
QWidget QDesignerFormWindowInterface.mainContainer (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回主容器部件的窗体窗口。

](qwidget.html)

[**See also**](qwidget.html) [setMainContainer](qdesignerformwindowinterface.html#setMainContainer)（ ） 。

```
QDesignerFormWindowInterface.manageWidget (self, QWidget widget)
```

这种方法也是一个Qt槽与C + +的签名`void manageWidget(QWidget *)`。

这种方法是抽象的，应在任何子类中重新实现。

指示窗体窗口管理规定_widget_。

**See also** [isManaged](qdesignerformwindowinterface.html#isManaged)（ ）[unmanageWidget](qdesignerformwindowinterface.html#unmanageWidget)（）和[widgetManaged](qdesignerformwindowinterface.html#widgetManaged)（ ） 。

```
QString QDesignerFormWindowInterface.pixmapFunction (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回用于加载的像素映射到表单窗口中的函数的名称。

**See also** [setPixmapFunction](qdesignerformwindowinterface.html#setPixmapFunction)（ ） 。

```
QDesignerFormWindowInterface.removeResourceFile (self, QString path)
```

这种方法是抽象的，应在任何子类中重新实现。

删除该资源文件在指定的_path_从所采用的表格的列表。

**See also** [resourceFiles](qdesignerformwindowinterface.html#resourceFiles)（）和[resourceFilesChanged](qdesignerformwindowinterface.html#resourceFilesChanged)（ ） 。

```
QStringList QDesignerFormWindowInterface.resourceFiles (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的路径的列表的资源当前正在使用的窗口形式的文件。

**See also** [addResourceFile](qdesignerformwindowinterface.html#addResourceFile)（）和[removeResourceFile](qdesignerformwindowinterface.html#removeResourceFile)（ ） 。

```
QDesignerFormWindowInterface.selectWidget (self, QWidget widget, bool select = True)
```

这种方法也是一个Qt槽与C + +的签名`void selectWidget(QWidget *,bool = 1)`。

这种方法是抽象的，应在任何子类中重新实现。

If _select_诚然，在给定_widget_被选择，否则_widget_被取消。

**See also** [clearSelection](qdesignerformwindowinterface.html#clearSelection)（）和[selectionChanged](qdesignerformwindowinterface.html#selectionChanged)（ ） 。

```
QDesignerFormWindowInterface.setAuthor (self, QString author)
```

这种方法是抽象的，应在任何子类中重新实现。

设置的详细资料，作者或形式的创造者到_author_规定。

**See also** [author](qdesignerformwindowinterface.html#author)（ ） 。

```
QDesignerFormWindowInterface.setComment (self, QString comment)
```

这种方法是抽象的，应在任何子类中重新实现。

设置有关表单中的信息的_comment_规定。这些信息应该是关于形式的人类可读的注解。

**See also** [comment](qdesignerformwindowinterface.html#comment)（ ） 。

```
QDesignerFormWindowInterface.setContents (self, QIODevice dev)
```

这种方法是抽象的，应在任何子类中重新实现。

设置使用从给定获得的数据表单的内容_device_。

数据可以读出[QFile](qfile.html)对象或任何其它亚类[QIODevice](qiodevice.html)。

**See also** [contents](qdesignerformwindowinterface.html#contents)（ ） 。

```
QDesignerFormWindowInterface.setContents (self, QString contents)
```

这种方法也是一个Qt槽与C + +的签名`void setContents(const QString&)`。

这种方法是抽象的，应在任何子类中重新实现。

设置使用从指定的读取数据表单的内容_contents_字符串。

**See also** [contents](qdesignerformwindowinterface.html#contents)（ ） 。

```
QDesignerFormWindowInterface.setDirty (self, bool dirty)
```

这种方法也是一个Qt槽与C + +的签名`void setDirty(bool)`。

这种方法是抽象的，应在任何子类中重新实现。

If _dirty_为True，表单窗口被标记为脏，这意味着它被修改但未保存。如果_dirty_是假的，表单窗口被认为是未经修改的。

**See also** [isDirty](qdesignerformwindowinterface.html#isDirty)（ ） 。

```
QDesignerFormWindowInterface.setExportMacro (self, QString exportMacro)
```

这种方法是抽象的，应在任何子类中重新实现。

设置表单窗口的出口宏_exportMacro_。构建一个Widget插件形式的接口导出到其他组件时，出口的宏使用。

**See also** [exportMacro](qdesignerformwindowinterface.html#exportMacro)（ ） 。

```
QDesignerFormWindowInterface.setFeatures (self, Feature f)
```

这种方法也是一个Qt槽与C + +的签名`void setFeatures(QDesignerFormWindowInterface::Feature)`。

这种方法是抽象的，应在任何子类中重新实现。

启用指定_features_表单窗口。

**See also** [features](qdesignerformwindowinterface.html#features)（）和[featureChanged](qdesignerformwindowinterface.html#featureChanged)（ ） 。

```
QDesignerFormWindowInterface.setFileName (self, QString fileName)
```

这种方法也是一个Qt槽与C + +的签名`void setFileName(const QString&)`。

这种方法是抽象的，应在任何子类中重新实现。

设置窗体的文件名给定_fileName_。

**See also** [fileName](qdesignerformwindowinterface.html#fileName)（）和[fileNameChanged](qdesignerformwindowinterface.html#fileNameChanged)（ ） 。

```
QDesignerFormWindowInterface.setGrid (self, QPoint grid)
```

这种方法也是一个Qt槽与C + +的签名`void setGrid(const QPoint&)`。

这种方法是抽象的，应在任何子类中重新实现。

设置网格大小的表格窗口，由指定的点_grid_。在这个函数中，在坐标[QPoint](qpoint.html)用于指定在网格的矩形的尺寸。

**See also** [grid](qdesignerformwindowinterface.html#grid)（ ） 。

```
QDesignerFormWindowInterface.setIncludeHints (self, QStringList includeHints)
```

这种方法是抽象的，应在任何子类中重新实现。

设置将被包含在窗体窗口的相关的UI文件到指定的头文件_includeHints_。

头文件可以是本地的，即相对于项目的目录，`"mywidget.h"`，或全球性的， Qt的或编译器的标准库的一部分，即：`&lt;QtGui/QWidget&gt;`。

**See also** [includeHints](qdesignerformwindowinterface.html#includeHints)（ ） 。

```
QDesignerFormWindowInterface.setLayoutDefault (self, int margin, int spacing)
```

这种方法是抽象的，应在任何子类中重新实现。

设置默认_margin_和_spacing_表单的布局。

**See also** [layoutDefault](qdesignerformwindowinterface.html#layoutDefault)（ ） 。

```
QDesignerFormWindowInterface.setLayoutFunction (self, QString margin, QString spacing)
```

这种方法是抽象的，应在任何子类中重新实现。

设置_margin_和_spacing_表单的布局。

默认的布局属性会被相应的布局功能所取代时，`uic`生成代码的形式，即，如果指定的功能。这是有用的，当不同的环境需要不同的布局形式相同。

**See also** [layoutFunction](qdesignerformwindowinterface.html#layoutFunction)（ ） 。

```
QDesignerFormWindowInterface.setMainContainer (self, QWidget mainContainer)
```

这种方法是抽象的，应在任何子类中重新实现。

设置窗体上的主容器控件到指定的_mainContainer_。

**See also** [mainContainer](qdesignerformwindowinterface.html#mainContainer)（）和[mainContainerChanged](qdesignerformwindowinterface.html#mainContainerChanged)（ ） 。

```
QDesignerFormWindowInterface.setPixmapFunction (self, QString pixmapFunction)
```

这种方法是抽象的，应在任何子类中重新实现。

设置用于加载的像素映射到表单窗口给定的函数_pixmapFunction_。

**See also** [pixmapFunction](qdesignerformwindowinterface.html#pixmapFunction)（ ） 。

```
QDesignerFormWindowInterface.unmanageWidget (self, QWidget widget)
```

这种方法也是一个Qt槽与C + +的签名`void unmanageWidget(QWidget *)`。

这种方法是抽象的，应在任何子类中重新实现。

指示窗体窗口不是管理规定_widget_。

**See also** [aboutToUnmanageWidget](qdesignerformwindowinterface.html#aboutToUnmanageWidget)（）和[widgetUnmanaged](qdesignerformwindowinterface.html#widgetUnmanaged)（ ） 。

* * *

## Qt Signal Documentation

```
void aboutToUnmanageWidget (QWidget *)
```

这是该信号的默认超载。

这个信号被发射时窗体上的控件即将成为非讬管。当这个信号被发射时，指定_widget_还在管理，以及[widgetUnmanaged](qdesignerformwindowinterface.html#widgetUnmanaged)（ ）信号会随之而来，指示当它不再管理。

**See also** [unmanageWidget](qdesignerformwindowinterface.html#unmanageWidget)（）和[isManaged](qdesignerformwindowinterface.html#isManaged)（ ） 。

```
void activated (QWidget *)
```

这是该信号的默认超载。

这个信号被发射时小部件的形式激活。被激活的窗口小部件被指定_widget_。

```
void changed ()
```

这是该信号的默认超载。

这个信号被发射时的格式被改变。

```
void featureChanged (QDesignerFormWindowInterface::Feature)
```

这是该信号的默认超载。

这个信号被发射时的特征形式的变化。新的功能是通过指定_feature_。

**See also** [setFeatures](qdesignerformwindowinterface.html#setFeatures)（ ） 。

```
void fileNameChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射的形式变化时的文件名。新的文件名由指定_fileName_。

**See also** [setFileName](qdesignerformwindowinterface.html#setFileName)（ ） 。

```
void geometryChanged ()
```

这是该信号的默认超载。

这个信号被发射时窗体的几何变化。

```
void mainContainerChanged (QWidget *)
```

这是该信号的默认超载。

这个信号被发射时在主容器的变化。新的容器是由指定的_mainContainer_。

**See also** [setMainContainer](qdesignerformwindowinterface.html#setMainContainer)（ ） 。

```
void objectRemoved (QObject *)
```

这是该信号的默认超载。

这个信号被发射时的对象（如一个动作或一个[QButtonGroup](qbuttongroup.html)）被从模中取出。被删除的对象被指定_object_。

此功能被引入Qt的4.5 。

```
void resourceFilesChanged ()
```

这是该信号的默认超载。

每当使用的形式变化带来的资源文件列表这个信号被发射。

**See also** [resourceFiles](qdesignerformwindowinterface.html#resourceFiles)（ ） 。

```
void selectionChanged ()
```

这是该信号的默认超载。

这个信号被发射时的选择的形式的变化。

**See also** [selectWidget](qdesignerformwindowinterface.html#selectWidget)（）和[clearSelection](qdesignerformwindowinterface.html#clearSelection)（ ） 。

```
void widgetManaged (QWidget *)
```

这是该信号的默认超载。

这个信号被发射时窗体上的控件变为管理。新管理部件被指定_widget_。

**See also** [manageWidget](qdesignerformwindowinterface.html#manageWidget)（ ） 。

```
void widgetRemoved (QWidget *)
```

这是该信号的默认超载。

每当一个小部件是从窗体中删除这个信号被发射。被删除的小部件被指定_widget_。

```
void widgetUnmanaged (QWidget *)
```

这是该信号的默认超载。

每当窗体上的控件变为非讬管这个信号被发射。新发布的部件是由指定的_widget_。

**See also** [unmanageWidget](qdesignerformwindowinterface.html#unmanageWidget)（）和[aboutToUnmanageWidget](qdesignerformwindowinterface.html#aboutToUnmanageWidget)（ ） 。