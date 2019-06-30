# QItemEditorFactory Class Reference

## [[QtGui](index.htm) module]

该QItemEditorFactory类提供的小部件，用于编辑项目的数据在视图和代表。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QItemEditorFactory)`
*   `QWidget createEditor (self, Type type, QWidget parent)`
*   `registerEditor (self, Type type, QItemEditorCreatorBase creator)`
*   `QByteArray valuePropertyName (self, Type type)`

### Static Methods

*   `QItemEditorFactory defaultFactory ()`
*   `setDefaultFactory (QItemEditorFactory factory)`

* * *

## Detailed Description

该QItemEditorFactory类提供的小部件，用于编辑项目的数据在视图和代表。

当编辑在项目视图数据，编辑由委讬创建并显示。[QItemDelegate](qitemdelegate.html)，这是在默认情况下安装在Qt的项目视图的委讬，采用的是QItemEditorFactory创建编辑它。由QItemEditorFactory提供一个默认的唯一实例被所有项目的代表。如果你设置新的默认出厂带[setDefaultFactory](qitemeditorfactory.html#setDefaultFactory)（ ） ，该新工厂将用于现有的和新的代表。

一个工厂保持集合[QItemEditorCreatorBase](qitemeditorcreatorbase.html)情况下，这是产生编辑一个特定的专门的编辑器[QVariant](qvariant.html)数据类型（所有Qt的模型将其数据存储在[QVariant](qvariant.html)S） 。

### Standard Editing Widgets

标准厂房的实施提供了编辑器，适用于各种数据类型。这些被创建时的委讬需要提供的编辑器由模型提供的数据。下表显示的类型和所提供的标准编辑器之间的关系。

| Type | Editor Widget |
| --- | --- |
| bool | [QComboBox](qcombobox.html) |
| double | [QDoubleSpinBox](qdoublespinbox.html) |
| int | [QSpinBox](qspinbox.html) |
| unsigned int |
| [QDate](qdate.html) | [QDateEdit](qdateedit.html) |
| [QDateTime](qdatetime.html) | [QDateTimeEdit](qdatetimeedit.html) |
| [QPixmap](qpixmap.html) | [QLabel](qlabel.html) |
| [QString](qstring.html) | [QLineEdit](qlineedit.html) |
| [QTime](qtime.html) | [QTimeEdit](qtimeedit.html) |

其他编辑器可以与注册[registerEditor](qitemeditorfactory.html#registerEditor)（）函数。

* * *

## Method Documentation

```
QItemEditorFactory.__init__ (self)
```

构造一个新的项目编辑器的工厂。

```
QItemEditorFactory.__init__ (self, QItemEditorFactory)
```

```
QWidget QItemEditorFactory.createEditor (self, Type type, QWidget parent)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qwidget.html)

[创建一个编辑器部件与给定_parent_为指定的_type_的数据，并返回它作为一个的](qwidget.html)[QWidget](qwidget.html)。

**See also** [registerEditor](qitemeditorfactory.html#registerEditor)（ ） 。

```
QItemEditorFactory QItemEditorFactory.defaultFactory ()
```

[

返回默认项目编辑器的工厂。

](qitemeditorfactory.html)

[**See also**](qitemeditorfactory.html) [setDefaultFactory](qitemeditorfactory.html#setDefaultFactory)（ ） 。

```
QItemEditorFactory.registerEditor (self, Type type, QItemEditorCreatorBase creator)
```

该_creator_说法有它的所有权转移给Qt的。

通过注册一个指定的项目编辑器创造者_creator_对于给定的_type_数据。

**Note:**本厂承接的项目编辑器创建者的所有权，并会破坏它，如果相同类型的新创造者以后注册。

**See also** [createEditor](qitemeditorfactory.html#createEditor)（ ） 。

```
QItemEditorFactory.setDefaultFactory (QItemEditorFactory factory)
```

该_factory_说法有它的所有权转移给Qt的。

设置默认项目编辑器厂家给定的_factory_。新的和现有的代表将使用新的工厂。

**See also** [defaultFactory](qitemeditorfactory.html#defaultFactory)（ ） 。

```
QByteArray QItemEditorFactory.valuePropertyName (self, Type type)
```

[

返回用于访问数据为给定的属性名_type_数据。

](qbytearray.html)