# QDesignerPropertyEditorInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerPropertyEditorInterface类允许你查询和操作的Qt设计器的属性编辑器的当前状态。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent, Qt.WindowFlags flags = 0)`
*   `QDesignerFormEditorInterface core (self)`
*   `QString currentPropertyName (self)`
*   `bool isReadOnly (self)`
*   `QObject object (self)`
*   `setObject (self, QObject object)`
*   `setPropertyValue (self, QString name, QVariant value, bool changed = True)`
*   `setReadOnly (self, bool readOnly)`

### Qt Signals

*   `void propertyChanged (const QString&,const QVariant&)`

* * *

## Detailed Description

该QDesignerPropertyEditorInterface类允许你查询和操作的Qt设计器的属性编辑器的当前状态。

QDesignerPropertyEditorInterface包含了通常用于查询的属性编辑器，其当前状态的功能，和几个插槽集合操纵它的状态。该接口还提供了一个信号，[propertyChanged](qdesignerpropertyeditorinterface.html#propertyChanged)（ ） ，这是发射时在属性编辑器中的属性更改。该信号的参数是已更改的属性及其新值。

例如，实现一个自定义的widget插件时，你可以将信号连接到一个自定义的槽：

```
         QDesignerPropertyEditorInterface *propertyEditor = 0;
         propertyEditor = formEditor->propertyEditor();

         connect(propertyEditor, SIGNAL(propertyChanged([QString](qstring.html), [QVariant](qvariant.html))),
                 this, SLOT(checkProperty([QString](qstring.html), [QVariant](qvariant.html))));

```

此外，定制的插槽可以检查新值，我们希望在一个指定的属性，属于特定窗口小部件，改变的范围之内：

```
         void checkProperty([QString](qstring.html) property, [QVariant](qvariant.html) value) {
             QDesignerPropertyEditorInterface *propertyEditor = 0;
             propertyEditor = formEditor->propertyEditor();

             [QObject](qobject.html) *object = propertyeditor->object();
             MyCustomWidget *widget = qobject_cast<MyCustomWidget>(object);

             if (widget && property == aProperty && value != expectedValue)
                 {...}
         }

```

该QDesignerPropertyEditorInterface类不适合直接实例化。你可以检索界面_Qt Designer_使用的属性编辑器[QDesignerFormEditorInterface.propertyEditor](qdesignerformeditorinterface.html#propertyEditor)（）函数。一个指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。当实现一个自定义的widget插件，你必须在子类[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)暴露你的插件_Qt Designer_。

访问属性编辑器的功能是[core](qdesignerpropertyeditorinterface.html#core)（ ）函数，你可以使用它来检索一个接口，表单编辑器中，[currentPropertyName](qdesignerpropertyeditorinterface.html#currentPropertyName)（ ）函数，返回的属性编辑器中当前所选属性的名称时，[object](qdesignerpropertyeditorinterface.html#object)（ ）函数，返回当前选定的对象_Qt Designer_的工作空间，以及[isReadOnly](qdesignerpropertyeditorinterface.html#isReadOnly)（ ）函数，如果属性编辑器是写proteced返回True （否则返回False ） 。

操纵属性编辑器的状态的槽的[setObject](qdesignerpropertyeditorinterface.html#setObject)（）槽，你可以用它来改变当前选定的对象_Qt Designer_的工作区时，[setPropertyValue](qdesignerpropertyeditorinterface.html#setPropertyValue)（）槽，改变一个给定属性的值和[setReadOnly](qdesignerpropertyeditorinterface.html#setReadOnly)（）槽控制的属性编辑器的写保护。

* * *

## Method Documentation

```
QDesignerPropertyEditorInterface.__init__ (self, QWidget parent, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个属性编辑器界面与给定_parent_和在指定的窗口_flags_。

```
QDesignerFormEditorInterface QDesignerPropertyEditorInterface.core (self)
```

[](qdesignerformeditorinterface.html)

[返回一个指针_Qt Designer_目前的](qdesignerformeditorinterface.html)[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象。

```
QString QDesignerPropertyEditorInterface.currentPropertyName (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回在属性编辑器中当前所选属性的名称。

**See also** [setPropertyValue](qdesignerpropertyeditorinterface.html#setPropertyValue)（ ） 。

```
bool QDesignerPropertyEditorInterface.isReadOnly (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True，如果属性编辑器处于写保护状态，否则为False 。

**See also** [setReadOnly](qdesignerpropertyeditorinterface.html#setReadOnly)（ ） 。

```
QObject QDesignerPropertyEditorInterface.object (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回当前选定的对象_Qt Designer_的工作空间。

](qobject.html)

[**See also**](qobject.html) [setObject](qdesignerpropertyeditorinterface.html#setObject)（ ） 。

```
QDesignerPropertyEditorInterface.setObject (self, QObject object)
```

这种方法也是一个Qt槽与C + +的签名`void setObject(QObject *)`。

这种方法是抽象的，应在任何子类中重新实现。

在更改当前选定的对象_Qt Designer_的工作空间，以_object_。

**See also** [object](qdesignerpropertyeditorinterface.html#object)（ ） 。

```
QDesignerPropertyEditorInterface.setPropertyValue (self, QString name, QVariant value, bool changed = True)
```

这种方法也是一个Qt槽与C + +的签名`void setPropertyValue(const QString&,const QVariant&,bool = 1)`。

这种方法是抽象的，应在任何子类中重新实现。

通过设置指定的属性值_name_至_value_。

此外，该属性标记为_changed_在属性编辑器，即它的值从默认值不同。

**See also** [currentPropertyName](qdesignerpropertyeditorinterface.html#currentPropertyName)（）和[propertyChanged](qdesignerpropertyeditorinterface.html#propertyChanged)（ ） 。

```
QDesignerPropertyEditorInterface.setReadOnly (self, bool readOnly)
```

这种方法也是一个Qt槽与C + +的签名`void setReadOnly(bool)`。

这种方法是抽象的，应在任何子类中重新实现。

If _readOnly_为True，则属性编辑器是由写保护，否则写保护被删除。

**See also** [isReadOnly](qdesignerpropertyeditorinterface.html#isReadOnly)（ ） 。

* * *

## Qt Signal Documentation

```
void propertyChanged (const QString&,const QVariant&)
```

这是该信号的默认超载。

这个信号被发射时在属性编辑器中的属性更改。这改变了其新的价值的财产被指定_name_和_value_分别。

**See also** [setPropertyValue](qdesignerpropertyeditorinterface.html#setPropertyValue)（ ） 。