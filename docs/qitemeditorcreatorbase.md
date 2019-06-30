# QItemEditorCreatorBase Class Reference

## [[QtGui](index.htm) module]

该QItemEditorCreatorBase类提供​​了必须实施新的项目编辑器创造者时被继承的抽象基类。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QItemEditorCreatorBase)`
*   `QWidget createWidget (self, QWidget parent)`
*   `QByteArray valuePropertyName (self)`

* * *

## Detailed Description

该QItemEditorCreatorBase类提供​​了必须实施新的项目编辑器创造者时被继承的抽象基类。

QItemEditorCreatorBase对象是专门的窗口小部件的工厂提供的编辑器部件为一个特定的[QVariant](qvariant.html)数据类型。它们被用来通过[QItemEditorFactory](qitemeditorfactory.html)创建编辑器[QItemDelegate](qitemdelegate.html)秒。造物主基地必须与注册[QItemEditorFactory.registerEditor](qitemeditorfactory.html#registerEditor)（ ） 。

编辑应为它编辑的数据提供了一个用户属性。然后QItemDelagates可以使用Qt的访问属性[meta-object system](index.htm#meta-object-system)设置和检索的编辑数据。一个属性被设置为与用户关键字的用户属性：

```
 Q_PROPERTY([QColor](qcolor.html) color READ color WRITE setColor USER true)

```

如果编辑器不提供用户属性，它必须从返回的属性的名称[valuePropertyName](qitemeditorcreatorbase.html#valuePropertyName)（）;代表将使用此名称来访问属性。如果用户属性存在，项目代表将不会调用[valuePropertyName](qitemeditorcreatorbase.html#valuePropertyName)（ ） 。

[QStandardItemEditorCreator](index.htm)是可以用于注册的小部件，而不需要子类QItemEditorCreatorBase方便的模板类。

* * *

## Method Documentation

```
QItemEditorCreatorBase.__init__ (self)
```

```
QItemEditorCreatorBase.__init__ (self, QItemEditorCreatorBase)
```

```
QWidget QItemEditorCreatorBase.createWidget (self, QWidget parent)
```

[

这种方法是抽象的，应在任何子类中重新实现。

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

返回一个编辑器部件与给定_parent_。

当实现这个类的子类此功能，您必须构造并返回新的编辑器部件使用指定的父控件。

](qwidget.html)

```
QByteArray QItemEditorCreatorBase.valuePropertyName (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回用于获取和创建者的编辑器窗口小部件设置值的属性的名称。

](qbytearray.html)

[当实现在子类中此功能，您必须确保在这个函数中指定的编辑器部件的属性可以接受的创造者注册的类型。例如，制作者它构造](qbytearray.html)[QCheckBox](qcheckbox.html)小工具来编辑布尔值将返回[checkable](qabstractbutton.html#checkable-prop)从这个函数的属性名称，并且必须在项目编辑器工厂登记[QVariant.Bool](qvariant.html#Type-enum)类型。

注：由于Qt 4.2中的项目代表查询小工具的用户属性，只有调用这个函数，如果部件没有用户属性。您可以通过重新实现复盖此行为[QAbstractItemDelegate.setModelData](qabstractitemdelegate.html#setModelData)（）和[QAbstractItemDelegate.setEditorData](qabstractitemdelegate.html#setEditorData)（ ） 。

**See also** [QMetaObject.userProperty](qmetaobject.html#userProperty)（）和[QItemEditorFactory.registerEditor](qitemeditorfactory.html#registerEditor)（ ） 。