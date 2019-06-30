# QDesignerPropertySheetExtension Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerPropertySheetExtension类允许你操作并显示在Qt设计器的属性编辑器窗口小部件的属性。[More...](#details)

通过继承[QPyDesignerPropertySheetExtension](qpydesignerpropertysheetextension.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDesignerPropertySheetExtension)`
*   `int count (self)`
*   `bool hasReset (self, int index)`
*   `int indexOf (self, QString name)`
*   `bool isAttribute (self, int index)`
*   `bool isChanged (self, int index)`
*   `bool isVisible (self, int index)`
*   `QVariant property (self, int index)`
*   `QString propertyGroup (self, int index)`
*   `QString propertyName (self, int index)`
*   `bool reset (self, int index)`
*   `setAttribute (self, int index, bool b)`
*   `setChanged (self, int index, bool changed)`
*   `setProperty (self, int index, QVariant value)`
*   `setPropertyGroup (self, int index, QString group)`
*   `setVisible (self, int index, bool b)`

### Special Methods

*   `__len__ (self)`

* * *

## Detailed Description

该QDesignerPropertySheetExtension类允许你操作并显示在Qt设计器的属性编辑器窗口小部件的属性。

QDesignerPropertySheetExtension规定，通常用于查询窗口小部件的属性，操纵性能“出现在属性编辑器的功能的集合。例如：

```
 QDesignerPropertySheetExtension *propertySheet  = 0;
 [QExtensionManager](qextensionmanager.html) manager = formEditor->extensionManager();

 propertySheet = qt_extension<QDesignerPropertySheetExtension*>(manager, widget);
 int index = propertySheet->indexOf(QLatin1String("margin"));

 propertySheet->setProperty(index, 10);
 propertySheet->setChanged(index, true);

 delete propertySheet;

```

请注意，如果您使用更改属性的值[QDesignerPropertySheetExtension.setProperty](qdesignerpropertysheetextension.html#setProperty)（ ）函数，撤消堆栈没有更新。为了确保一个属性的值可以使用撤消堆栈被还原，则必须使用[QDesignerFormWindowCursorInterface.setProperty](qdesignerformwindowcursorinterface.html#setProperty)（ ）函数，或者它的夥伴[setWidgetProperty()](qdesignerformwindowcursorinterface.html#setWidgetProperty)代替。

当实现一个自定义的widget插件，一个指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。

属性表，或任何其他分机，可以通过查询检索_Qt Designer_使用的扩展管理器[qt_extension](qextensionmanager.html#qt_extension)（）函数。当你要释放的扩展，你只需要删除的指针。

所有的部件都有一个默认的属性表的填充_Qt Designer_的属性编辑器的控件的属性（即与所定义的那些[Q_PROPERTY](qobject.html#Q_PROPERTY)（）宏） 。但QDesignerPropertySheetExtension还提供了用于创建自定义属性表扩展的接口。

**Warning:** _Qt Designer_使用QDesignerPropertySheetExtension养活它的属性编辑器。每当一个小部件中选择其工作区，_Qt Designer_将查询窗口小部件的属性表扩展。如果选定部件有一个实现属性表的扩展，这个扩展将复盖默认的属性表。

要创建一个属性表的扩展，你的扩展类必须继承自两个[QObject](qobject.html)和QDesignerPropertySheetExtension 。然后，因为我们正在实现一个接口，我们必须确保它是由已知的元对象系统中使用[Q_INTERFACES](qobject.html#Q_INTERFACES)（）宏：

```
 class MyPropertySheetExtension : public [QObject](qobject.html),
         public QDesignerPropertySheetExtension
 {
     Q_OBJECT
     Q_INTERFACES(QDesignerPropertySheetExtension)

 public:
     ...
 }

```

这使_Qt Designer_使用[qobject_cast](qobject.html#qobject_cast)（）来查询只是用一个接口支持[QObject](qobject.html)指针。

In _Qt Designer_未创建的扩展，直到你需要它们。出于这个原因，实现属性表扩展时，您还必须创建一个[QExtensionFactory](qextensionfactory.html)，即一个类，它能够让你的扩展的一个实例，并使用它注册_Qt Designer_的[extension manager](qextensionmanager.html)。

当一个属性表扩展是必需的，_Qt Designer_的[extension manager](qextensionmanager.html)将通过其所有已注册的工厂运行要求[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）对每一直到第一个是能够创造一个属性表扩展选定控件，被找到。这家工厂将使这个扩展的实例。如果没有这样的工厂，可以发现，_Qt Designer_将使用默认的属性表。

有扩展的四个可用的类型_Qt Designer_：[QDesignerContainerExtension](qdesignercontainerextension.html)，[QDesignerMemberSheetExtension](qdesignermembersheetextension.html)， QDesignerPropertySheetExtension和[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)。 Qt设计器的行为是一样的具有多页的容器，一个成员表，属性表或任务菜单中的延期申请是否相关。

该[QExtensionFactory](qextensionfactory.html)类提供了一个标准的扩展工厂，并且也可以用作用于定义扩展工厂的接口。您可以创建一个新的[QExtensionFactory](qextensionfactory.html)并重新实现[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（）函数。例如：

```
 [QObject](qobject.html) *ANewExtensionFactory.createExtension([QObject](qobject.html) *object,
         const [QString](qstring.html) &iid, [QObject](qobject.html) *parent) const
 {
     if (iid != Q_TYPEID(QDesignerPropertySheetExtension))
         return 0;

     if (MyCustomWidget *widget = qobject_cast<MyCustomWidget*>
            (object))
         return new MyPropertySheetExtension(widget, parent);

     return 0;
 }

```

或者您可以使用现有的工厂，扩大[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）函数，使工厂能够创建一个属性表扩展延伸为好。例如：

```
 [QObject](qobject.html) *AGeneralExtensionFactory.createExtension([QObject](qobject.html) *object,
         const [QString](qstring.html) &iid, [QObject](qobject.html) *parent) const
 {
     MyCustomWidget *widget = qobject_cast<MyCustomWidget*>(object);

     if (widget && (iid == Q_TYPEID([QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)))) {
         return new MyTaskMenuExtension(widget, parent);

     } else if (widget && (iid == Q_TYPEID(QDesignerPropertySheetExtension))) {
         return new MyPropertySheetExtension(widget, parent);

     } else {
         return 0;
     }
 }

```

对于使用扩展类的完整示例，请参见[Task Menu Extension example](index.htm)。该示例显示了如何创建一个自定义的widget插件Qt Designer中，以及如何使用[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)类的自定义项添加到_Qt Designer_的任务菜单。

* * *

## Method Documentation

```
QDesignerPropertySheetExtension.__init__ (self)
```

```
QDesignerPropertySheetExtension.__init__ (self, QDesignerPropertySheetExtension)
```

```
int QDesignerPropertySheetExtension.count (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的属性所选部件的数量。

```
bool QDesignerPropertySheetExtension.hasReset (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果给定的酒店在_index_有一个复位按钮_Qt Designer_的属性编辑器，否则为False 。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（）和[reset](qdesignerpropertysheetextension.html#reset)（ ） 。

```
int QDesignerPropertySheetExtension.indexOf (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

返回索引对于给定的属性_name_。

**See also** [propertyName](qdesignerpropertysheetextension.html#propertyName)（ ） 。

```
bool QDesignerPropertySheetExtension.isAttribute (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果给定的酒店在_index_是一个属性，这将是_excluded_从UI文件，否则为False。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（）和[setAttribute](qdesignerpropertysheetextension.html#setAttribute)（ ） 。

```
bool QDesignerPropertySheetExtension.isChanged (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果给定的属性的值_index_不同于属性的默认值，否则返回False 。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（ ）[setChanged](qdesignerpropertysheetextension.html#setChanged)（）和[reset](qdesignerpropertysheetextension.html#reset)（ ） 。

```
bool QDesignerPropertySheetExtension.isVisible (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果给定的酒店在_index_在可见_Qt Designer_的属性编辑器，否则为False 。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（）和[setVisible](qdesignerpropertysheetextension.html#setVisible)（ ） 。

```
QVariant QDesignerPropertySheetExtension.property (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

在给定的返回属性的值_index_。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（ ）[setProperty](qdesignerpropertysheetextension.html#setProperty)（）和[propertyGroup](qdesignerpropertysheetextension.html#propertyGroup)（ ） 。

```
QString QDesignerPropertySheetExtension.propertyGroup (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

在给定的返回属性组属性_index_。

_Qt Designer_的属性编辑器支持属性组，相关性，即部分。一个属性可以使用上与一组[setPropertyGroup](qdesignerpropertysheetextension.html#setPropertyGroup)（）函数。任何属性的默认组是定义它的类的名称。例如，本[QObject.objectName](qobject.html#objectName-prop)物业内出现的[QObject](qobject.html)属性组。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（）和[setPropertyGroup](qdesignerpropertysheetextension.html#setPropertyGroup)（ ） 。

```
QString QDesignerPropertySheetExtension.propertyName (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回属性的名称在给定的_index_。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（ ） 。

```
bool QDesignerPropertySheetExtension.reset (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

复位在给定的属性的值_index_，为默认值。返回True如果默认值可以发现，否则为False 。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（ ）[hasReset](qdesignerpropertysheetextension.html#hasReset)（）和[isChanged](qdesignerpropertysheetextension.html#isChanged)（ ） 。

```
QDesignerPropertySheetExtension.setAttribute (self, int index, bool b)
```

这种方法是抽象的，应在任何子类中重新实现。

If _attribute_诚然，该物业在给定的_index_由这将是一个属性_excluded_从UI文件，否则将被纳入。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（）和[isAttribute](qdesignerpropertysheetextension.html#isAttribute)（ ） 。

```
QDesignerPropertySheetExtension.setChanged (self, int index, bool changed)
```

这种方法是抽象的，应在任何子类中重新实现。

设置该属性是否在给定的_index_从它的默认值，或没有，根据不同的_changed_参数。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（）和[isChanged](qdesignerpropertysheetextension.html#isChanged)（ ） 。

```
QDesignerPropertySheetExtension.setProperty (self, int index, QVariant value)
```

这种方法是抽象的，应在任何子类中重新实现。

设置_value_酒店在给定的_index_。

**Warning:**如果更改使用此功能的属性的值，撤消堆栈没有更新。为了确保一个属性的值可以使用撤消堆栈被还原，则必须使用[QDesignerFormWindowCursorInterface.setProperty](qdesignerformwindowcursorinterface.html#setProperty)（ ）函数，或者它的夥伴[setWidgetProperty()](qdesignerformwindowcursorinterface.html#setWidgetProperty)代替。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（ ）[property](qdesignerpropertysheetextension.html#property)（）和[propertyGroup](qdesignerpropertysheetextension.html#propertyGroup)（ ） 。

```
QDesignerPropertySheetExtension.setPropertyGroup (self, int index, QString group)
```

这种方法是抽象的，应在任何子类中重新实现。

设置属性组的属性在给定_index_至_group_。

有关物业为一组使得在属性编辑器该组的部分中也出现。默认属性组中的任何财产是定义它的类的名称。例如，本[QObject.objectName](qobject.html#objectName-prop)物业内出现的[QObject](qobject.html)属性组。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（ ）[property](qdesignerpropertysheetextension.html#property)（）和[propertyGroup](qdesignerpropertysheetextension.html#propertyGroup)（ ） 。

```
QDesignerPropertySheetExtension.setVisible (self, int index, bool b)
```

这种方法是抽象的，应在任何子类中重新实现。

If _visible_诚然，该物业在给定的_index_在可见_Qt Designer_的属性编辑器，否则该属性是隐藏的。

**See also** [indexOf](qdesignerpropertysheetextension.html#indexOf)（）和[isVisible](qdesignerpropertysheetextension.html#isVisible)（ ） 。

```
 QDesignerPropertySheetExtension.__len__ (self)
```