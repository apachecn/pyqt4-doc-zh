# QDesignerCustomWidgetInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerCustomWidgetInterface类使Qt Designer来访问和构建自定义部件。[More...](#details)

通过继承[QPyDesignerCustomWidgetPlugin](qpydesignercustomwidgetplugin.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDesignerCustomWidgetInterface)`
*   `QString codeTemplate (self)`
*   `QWidget createWidget (self, QWidget parent)`
*   `QString domXml (self)`
*   `QString group (self)`
*   `QIcon icon (self)`
*   `QString includeFile (self)`
*   `initialize (self, QDesignerFormEditorInterface core)`
*   `bool isContainer (self)`
*   `bool isInitialized (self)`
*   `QString name (self)`
*   `QString toolTip (self)`
*   `QString whatsThis (self)`

* * *

## Detailed Description

该QDesignerCustomWidgetInterface类使Qt Designer来访问和构建自定义部件。

QDesignerCustomWidgetInterface提供了自定义小部件的接口。这个类包含了一组必须被继承来返回小部件，比如它的类名和其头文件的名称基本信息的功能。其他功能必须实现在加载时初始化插件，构建自定义窗口小部件的实例_Qt Designer_来使用。

在实现自定义窗口小部件，您必须继承QDesignerCustomWidgetInterface到你的widget暴露在_Qt Designer_。例如，这是声明中使用的插件[Custom Widget Plugin example](index.htm)它使一个模拟时钟定制窗口小部件要使用的_Qt Designer_：

```
 class AnalogClockPlugin : public [QObject](qobject.html), public QDesignerCustomWidgetInterface
 {
     Q_OBJECT
     Q_INTERFACES(QDesignerCustomWidgetInterface)

 public:
     AnalogClockPlugin([QObject](qobject.html) *parent = 0);

     bool isContainer() const;
     bool isInitialized() const;
     [QIcon](qicon.html) icon() const;
     [QString](qstring.html) domXml() const;
     [QString](qstring.html) group() const;
     [QString](qstring.html) includeFile() const;
     [QString](qstring.html) name() const;
     [QString](qstring.html) toolTip() const;
     [QString](qstring.html) whatsThis() const;
     [QWidget](qwidget.html) *createWidget([QWidget](qwidget.html) *parent);
     void initialize([QDesignerFormEditorInterface](qdesignerformeditorinterface.html) *core);

 private:
     bool initialized;
 };

```

需要注意的是类定义的特定于这个特定的自定义插件的唯一部分是类名。此外，由于我们正在实施一个接口，我们必须确保它是由已知的元对象系统中使用[Q_INTERFACES](qobject.html#Q_INTERFACES)（）宏。这使_Qt Designer_使用[qobject_cast](qobject.html#qobject_cast)（ ）函数用什么来查询所支持的接口，但一[QObject](qobject.html)指针。

后_Qt Designer_加载一个自定义的widget插件，它会调用该接口的[initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数，使之能够成立，它可能需要的任何资源。这个函数被调用了[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)参数，它提供了插件与网关对所有的_Qt Designer_的API 。

_Qt Designer_通过调用插件的构建自定义窗口小部件的实例[createWidget](qdesignercustomwidgetinterface.html#createWidget)（）函数，用合适的亲代部件。插件必须构造并返回一个自定义窗口小部件的实例与指定的父控件。

在类的实现，你必须记住你的自定义的widget插件导出到_Qt Designer_使用[Q_EXPORT_PLUGIN2](index.htm#Q_EXPORT_PLUGIN2)（）宏。例如，如果一个所谓的库`libcustomwidgetplugin.so`（ Unix）或`libcustomwidget.dll`（在Windows上）中包含一个称为widget类`MyCustomWidget`，我们可以通过添加下面的行到包含插件实现文件导出：

```
 Q_EXPORT_PLUGIN2(customwidgetplugin, MyCustomWidget)

```

这个宏可以确保_Qt Designer_可以访问和构建自定义部件。如果没有这个宏，是没有办法的_Qt Designer_使用它。

当实现一个自定义的widget插件，你把它做成一个单独的库。如果你想包括几个自定义的widget插件在同一个库中，你必须在另外的子类[QDesignerCustomWidgetCollectionInterface](qdesignercustomwidgetcollectioninterface.html)。

**Warning:**如果您的自定义窗口小部件插件包含[QVariant](qvariant.html)性能，要知道，只有以下[types](qvariant.html#Type-enum)支持：

*   [QVariant.ByteArray](qvariant.html#Type-enum)
*   [QVariant.Bool](qvariant.html#Type-enum)
*   [QVariant.Color](qvariant.html#Type-enum)
*   [QVariant.Cursor](qvariant.html#Type-enum)
*   [QVariant.Date](qvariant.html#Type-enum)
*   [QVariant.DateTime](qvariant.html#Type-enum)
*   [QVariant.Double](qvariant.html#Type-enum)
*   [QVariant.Int](qvariant.html#Type-enum)
*   [QVariant.Point](qvariant.html#Type-enum)
*   [QVariant.Rect](qvariant.html#Type-enum)
*   [QVariant.Size](qvariant.html#Type-enum)
*   [QVariant.SizePolicy](qvariant.html#Type-enum)
*   [QVariant.String](qvariant.html#Type-enum)
*   [QVariant.Time](qvariant.html#Type-enum)
*   [QVariant.UInt](qvariant.html#Type-enum)

对于使用QDesignerCustomWidgetInterface类的完整示例，请参见[Custom Widget Example](index.htm)。该示例显示了如何创建一个自定义的widget插件_Qt Designer_。

* * *

## Method Documentation

```
QDesignerCustomWidgetInterface.__init__ (self)
```

```
QDesignerCustomWidgetInterface.__init__ (self, QDesignerCustomWidgetInterface)
```

```
QString QDesignerCustomWidgetInterface.codeTemplate (self)
```

此功能保留供将来使用_Qt Designer_。

```
QWidget QDesignerCustomWidgetInterface.createWidget (self, QWidget parent)
```

[

这种方法是抽象的，应在任何子类中重新实现。

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

返回自定义窗口小部件的一个新实例，用给定的_parent_。

```
QString QDesignerCustomWidgetInterface.domXml (self)
```

返回用于描述自定义窗口小部件的属性到XML_Qt Designer_。

```
QString QDesignerCustomWidgetInterface.group (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回到自定义窗口小部件所属的组的名称。

](qwidget.html)

```
QIcon QDesignerCustomWidgetInterface.icon (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回用于表示在自定义插件的图标_Qt Designer_的小工具盒。

```
QString QDesignerCustomWidgetInterface.includeFile (self)
```

这种方法是抽象的，应在任何子类中重新实现。

](qicon.html)

[返回的路径，包含文件](qicon.html)[uic](index.htm#uic)创建自定义窗口小部件代码时使用。

```
QDesignerCustomWidgetInterface.initialize (self, QDesignerFormEditorInterface core)
```

初始化部件具有指定用途_formEditor_接口。

**See also** [isInitialized](qdesignercustomwidgetinterface.html#isInitialized)（ ） 。

```
bool QDesignerCustomWidgetInterface.isContainer (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果自定义部件的目的是作为一个容器，否则返回False 。

大多数自定义窗体并不用来装其他部件，所以这个功能的实现将返回False ，但自定义容器将返回True ，以确保他们正确的行为_Qt Designer_。

```
bool QDesignerCustomWidgetInterface.isInitialized (self)
```

返回True如果控件已被初始化，否则返回False 。

**See also** [initialize](qdesignercustomwidgetinterface.html#initialize)（ ） 。

```
QString QDesignerCustomWidgetInterface.name (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回由该接口提供的自定义窗口小部件的类名。

返回的名称_must_是相同的用于自定义插件的类名。

```
QString QDesignerCustomWidgetInterface.toolTip (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回可使用的窗口小部件的简短说明_Qt Designer_在工具提示。

```
QString QDesignerCustomWidgetInterface.whatsThis (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回可使用的窗口小部件的描述_Qt Designer_在“这是什么？ ”帮助小部件。