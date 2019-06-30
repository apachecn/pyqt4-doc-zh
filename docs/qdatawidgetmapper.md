# QDataWidgetMapper Class Reference

## [[QtGui](index.htm) module]

该QDataWidgetMapper类提供了一个数据模型，以小部件的部分之间的映射。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum SubmitPolicy { AutoSubmit, ManualSubmit }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `addMapping (self, QWidget widget, int section)`
*   `addMapping (self, QWidget widget, int section, QByteArray propertyName)`
*   `clearMapping (self)`
*   `int currentIndex (self)`
*   `QAbstractItemDelegate itemDelegate (self)`
*   `QByteArray mappedPropertyName (self, QWidget widget)`
*   `int mappedSection (self, QWidget widget)`
*   `QWidget mappedWidgetAt (self, int section)`
*   `QAbstractItemModel model (self)`
*   `Qt.Orientation orientation (self)`
*   `removeMapping (self, QWidget widget)`
*   `revert (self)`
*   `QModelIndex rootIndex (self)`
*   `setCurrentIndex (self, int index)`
*   `setCurrentModelIndex (self, QModelIndex index)`
*   `setItemDelegate (self, QAbstractItemDelegate delegate)`
*   `setModel (self, QAbstractItemModel model)`
*   `setOrientation (self, Qt.Orientation aOrientation)`
*   `setRootIndex (self, QModelIndex index)`
*   `setSubmitPolicy (self, SubmitPolicy policy)`
*   `bool submit (self)`
*   `SubmitPolicy submitPolicy (self)`
*   `toFirst (self)`
*   `toLast (self)`
*   `toNext (self)`
*   `toPrevious (self)`

### Qt Signals

*   `void currentIndexChanged (int)`

* * *

## Detailed Description

该QDataWidgetMapper类提供了一个数据模型，以小部件的部分之间的映射。

QDataWidgetMapper可以使用它们映射到的项目模型部分来创建数据感知部件。 A节是模型中的列，如果方向是水平的（默认值） ，否则一排。

每当当前指数的变化，每个插件是通过在它的映射被做了指定的属性从模型数据更新。如果用户编辑窗口小部件的内容，使用相同的属性被读取和写回模型的变更。默认情况下，每个插件的[user property](qobject.html#Q_PROPERTY)用于传输的模型和部件之间的数据。由于Qt的4.3 ，额外的[addMapping](qdatawidgetmapper.html#addMapping)（ ）函数使一个名为属性，而不是默认的用户属性来使用。

它可以设定的项目委讬，支持自定义窗口小部件。默认情况下，[QItemDelegate](qitemdelegate.html)用于同步模式与窗口小部件。

让我们假设我们有一个名为项目模型`model`其内容如下：

| 1 | Qt Norway | Oslo |
| 2 | Qt Australia | Brisbane |
| 3 | Qt USA | Palo Alto |
| 4 | Qt China | Beijing |
| 5 | Qt Germany | Berlin |

下面的代码将模型中的列映射到部件称为`mySpinBox`，`myLineEdit`和`myCountryChooser`：

```
 QDataWidgetMapper *mapper = new QDataWidgetMapper;
 mapper->setModel(model);
 mapper->addMapping(mySpinBox, 0);
 mapper->addMapping(myLineEdit, 1);
 mapper->addMapping(myCountryChooser, 2);
 mapper->toFirst();

```

在调用后，[toFirst](qdatawidgetmapper.html#toFirst)（ ）`mySpinBox`显示值`1`，`myLineEdit`显示器`Qt Norway`和`myCountryChooser`显示器`Oslo`。导航功能[toFirst](qdatawidgetmapper.html#toFirst)（ ）[toNext](qdatawidgetmapper.html#toNext)（ ）[toPrevious](qdatawidgetmapper.html#toPrevious)（ ）[toLast](qdatawidgetmapper.html#toLast)（）和[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（）可以被用于导航模型中，并与从模型内容更新部件。

该[setRootIndex](qdatawidgetmapper.html#setRootIndex)（ ）函数实现了特定的项目中被指定为根指数的模型 - 这资料的孩子会被映射到用户界面相关的部件。

QDataWidgetMapper支持两种提交的政策，`AutoSubmit`和`ManualSubmit`。`AutoSubmit`将尽快更新模型作为当前控件失去焦点，`ManualSubmit`不会更新模型，除非[submit](qdatawidgetmapper.html#submit)（）被调用。`ManualSubmit`显示一个对话框，允许用户取消所有修改的时候非常有用。此外，该显示模型的其他视图将不会更新，直到用户完成所有的修改和提交。

需要注意的是QDataWidgetMapper跟踪外部修改。如果模型的内容​​的应用程序的另一个模块被更新时，窗口小部件被更新。

* * *

## Type Documentation

```
QDataWidgetMapper.SubmitPolicy
```

这个枚举变量描述了可能的提交政策[QDataWidgetMapper](qdatawidgetmapper.html)支持。

| Constant | Value | Description |
| --- | --- | --- |
| `QDataWidgetMapper.AutoSubmit` | `0` | 每当一个widget失去焦点时，控件的当前值设置为项目的模型。 |
| `QDataWidgetMapper.ManualSubmit` | `1` | 该模型不更新，直到[submit](qdatawidgetmapper.html#submit)（）被调用。 |

* * *

## Method Documentation

```
QDataWidgetMapper.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QDataWidgetMapper](qdatawidgetmapper.html)与父对象_parent_。默认情况下，方向是水平的，而提交政策`AutoSubmit`。

**See also** [setOrientation](qdatawidgetmapper.html#orientation-prop)（）和[setSubmitPolicy](qdatawidgetmapper.html#submitPolicy-prop)（ ） 。

```
QDataWidgetMapper.addMapping (self, QWidget widget, int section)
```

增加了之间的映射_widget_和_section_从模型。该_section_在模型中的列，如果方向是水平的（缺省设置） ，否则一排。

在下面的例子中，我们假设一个模型`myModel`有两列：第一包含的人在一组的名称，第二列包含他们的年龄。第一列被映射到[QLineEdit](qlineedit.html) `nameLineEdit`以及第二映射到[QSpinBox](qspinbox.html) `ageSpinBox`：

```
 [QDataWidgetMapper](qdatawidgetmapper.html) *mapper = new [QDataWidgetMapper](qdatawidgetmapper.html)();
 mapper->setModel(myModel);
 mapper->addMapping(nameLineEdit, 0);
 mapper->addMapping(ageSpinBox, 1);

```

**Notes:**

*   If the _widget_ is already mapped to a section, the old mapping will be replaced by the new one.
*   Only one-to-one mappings between sections and widgets are allowed. It is not possible to map a single section to multiple widgets, or to map a single widget to multiple sections.

**See also** [removeMapping](qdatawidgetmapper.html#removeMapping)（ ）[mappedSection](qdatawidgetmapper.html#mappedSection)（）和[clearMapping](qdatawidgetmapper.html#clearMapping)（ ） 。

```
QDataWidgetMapper.addMapping (self, QWidget widget, int section, QByteArray propertyName)
```

本质上是相同[addMapping](qdatawidgetmapper.html#addMapping)（ ） ，但增加了指定的属性来指定使用的可能性_propertyName_。

此功能被引入Qt的4.3 。

**See also** [addMapping](qdatawidgetmapper.html#addMapping)（ ） 。

```
QDataWidgetMapper.clearMapping (self)
```

清除所有映射。

**See also** [addMapping](qdatawidgetmapper.html#addMapping)（）和[removeMapping](qdatawidgetmapper.html#removeMapping)（ ） 。

```
int QDataWidgetMapper.currentIndex (self)
```

```
QAbstractItemDelegate QDataWidgetMapper.itemDelegate (self)
```

[

返回当前项目委讬。

](qabstractitemdelegate.html)

[**See also**](qabstractitemdelegate.html) [setItemDelegate](qdatawidgetmapper.html#setItemDelegate)（ ） 。

```
QByteArray QDataWidgetMapper.mappedPropertyName (self, QWidget widget)
```

[

返回被映射的数据时使用的属性的名称，以给定的_widget_。

此功能被引入Qt的4.3 。

](qbytearray.html)

[**See also**](qbytearray.html) [mappedSection](qdatawidgetmapper.html#mappedSection)（ ）[addMapping](qdatawidgetmapper.html#addMapping)（）和[removeMapping](qdatawidgetmapper.html#removeMapping)（ ） 。

```
int QDataWidgetMapper.mappedSection (self, QWidget widget)
```

返回节_widget_被映射到或-1，如果小部件不被映射。

**See also** [addMapping](qdatawidgetmapper.html#addMapping)（）和[removeMapping](qdatawidgetmapper.html#removeMapping)（ ） 。

```
QWidget QDataWidgetMapper.mappedWidgetAt (self, int section)
```

[

返回映射在小部件_section_，或者0 ，如果没有部件被映射在该节。

](qwidget.html)

[**See also**](qwidget.html) [addMapping](qdatawidgetmapper.html#addMapping)（）和[removeMapping](qdatawidgetmapper.html#removeMapping)（ ） 。

```
QAbstractItemModel QDataWidgetMapper.model (self)
```

[

返回当前的模式。

](qabstractitemmodel.html)

[**See also**](qabstractitemmodel.html) [setModel](qdatawidgetmapper.html#setModel)（ ） 。

```
Qt.Orientation QDataWidgetMapper.orientation (self)
```

[

```
QDataWidgetMapper.removeMapping (self, QWidget widget)
```

删除映射为给定的_widget_。

](qt.html#Orientation-enum)

[**See also**](qt.html#Orientation-enum) [addMapping](qdatawidgetmapper.html#addMapping)（）和[clearMapping](qdatawidgetmapper.html#clearMapping)（ ） 。

```
QDataWidgetMapper.revert (self)
```

这种方法也是一个Qt槽与C + +的签名`void revert()`。

重新填充所有部件与模型的当前数据。所有未提交的更改将会丢失。

**See also** [submit](qdatawidgetmapper.html#submit)（）和[setSubmitPolicy](qdatawidgetmapper.html#submitPolicy-prop)（ ） 。

```
QModelIndex QDataWidgetMapper.rootIndex (self)
```

[

返回当前根索引。

](qmodelindex.html)

[**See also**](qmodelindex.html) [setRootIndex](qdatawidgetmapper.html#setRootIndex)（ ） 。

```
QDataWidgetMapper.setCurrentIndex (self, int index)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentIndex(int)`。

```
QDataWidgetMapper.setCurrentModelIndex (self, QModelIndex index)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentModelIndex(const QModelIndex&)`。

设置当前索引的行_index_如果方向是水平的（默认值） ，否则到的列_index_。

电话[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（内部） 。这便利槽可连接到所述信号[currentRowChanged()](qitemselectionmodel.html#currentRowChanged) or [currentColumnChanged()](qitemselectionmodel.html#currentColumnChanged)另一种观点认为年代[selection model](qitemselectionmodel.html)。

下面的例子演示了如何更新所有的widget与新数据时的选择[QTableView](qtableview.html) named `myTableView`变化：

```
 [QDataWidgetMapper](qdatawidgetmapper.html) *mapper = new [QDataWidgetMapper](qdatawidgetmapper.html)();
 connect(myTableView->selectionModel(), SIGNAL(currentRowChanged([QModelIndex](qmodelindex.html),[QModelIndex](qmodelindex.html))),
         mapper, SLOT(setCurrentModelIndex([QModelIndex](qmodelindex.html))));

```

**See also** [currentIndex](qdatawidgetmapper.html#currentIndex-prop)（ ） 。

```
QDataWidgetMapper.setItemDelegate (self, QAbstractItemDelegate delegate)
```

设置项委讬_delegate_。该委讬将用于从模型数据写入到窗口小部件，并从部件的模型，用[QAbstractItemDelegate.setEditorData](qabstractitemdelegate.html#setEditorData)（）和[QAbstractItemDelegate.setModelData](qabstractitemdelegate.html#setModelData)（ ） 。

该代表还决定何时应用数据以及何时改变编辑器，使用[QAbstractItemDelegate.commitData](qabstractitemdelegate.html#commitData)（）和[QAbstractItemDelegate.closeEditor](qabstractitemdelegate.html#closeEditor)（ ） 。

**Warning:**你不应该共享控件映射程序或视图之间的委讬的同一实例。否则会导致不正确或不直观的编辑行为，因为在一个给定的委讬每个视图可能会收到[closeEditor()](qabstractitemdelegate.html#closeEditor)信号，并试图访问，修改或关闭一个已经被关闭的编辑器。

**See also** [itemDelegate](qdatawidgetmapper.html#itemDelegate)（ ） 。

```
QDataWidgetMapper.setModel (self, QAbstractItemModel model)
```

目前的模式设置为_model_。如果设置了另一种模式，所有映射到旧的模式被清除。

**See also** [model](qdatawidgetmapper.html#model)（ ） 。

```
QDataWidgetMapper.setOrientation (self, Qt.Orientation aOrientation)
```

```
QDataWidgetMapper.setRootIndex (self, QModelIndex index)
```

根项目设置为_index_。这可以被用来显示一个树的分支。传递一个无效的模型索引来显示最上面的分支。

**See also** [rootIndex](qdatawidgetmapper.html#rootIndex)（ ） 。

```
QDataWidgetMapper.setSubmitPolicy (self, SubmitPolicy policy)
```

```
bool QDataWidgetMapper.submit (self)
```

这种方法也是一个Qt槽与C + +的签名`bool submit()`。

从提交的映射部件的所有更改到模型中。

对于每一个映射部，该项目委讬从窗口小部件读取的当前值，并将其设置在模型中。最后，该模型是[submit()](qabstractitemmodel.html#submit)方法被调用。

如果所有的值被提交，否则为False ，则返回True 。

注意：对于数据库模型，[QSqlQueryModel.lastError](qsqlquerymodel.html#lastError)（ ）可以用来获取最后一个错误。

**See also** [revert](qdatawidgetmapper.html#revert)（）和[setSubmitPolicy](qdatawidgetmapper.html#submitPolicy-prop)（ ） 。

```
SubmitPolicy QDataWidgetMapper.submitPolicy (self)
```

[

```
QDataWidgetMapper.toFirst (self)
```

这种方法也是一个Qt槽与C + +的签名`void toFirst()`。

填充部件与从模型中的第一行的数据，如果方向是水平的（缺省设置） ，否则从第一列中的数据。

这等同于调用`setCurrentIndex(0)`。

](qdatawidgetmapper.html#SubmitPolicy-enum)

[**See also**](qdatawidgetmapper.html#SubmitPolicy-enum) [toLast](qdatawidgetmapper.html#toLast)（）和[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（ ） 。

```
QDataWidgetMapper.toLast (self)
```

这种方法也是一个Qt槽与C + +的签名`void toLast()`。

填充部件与模型的最后一行数据，如果方向是水平的（默认值） ，否则从最后一列的数据。

电话[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（内部） 。

**See also** [toFirst](qdatawidgetmapper.html#toFirst)（）和[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（ ） 。

```
QDataWidgetMapper.toNext (self)
```

这种方法也是一个Qt槽与C + +的签名`void toNext()`。

填充部件与模型的下一行数据，如果方向是水平的（默认值） ，否则与下一列的数据。

电话[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（内部） 。什么都不做，如果有在模型中没有下一行。

**See also** [toPrevious](qdatawidgetmapper.html#toPrevious)（）和[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（ ） 。

```
QDataWidgetMapper.toPrevious (self)
```

这种方法也是一个Qt槽与C + +的签名`void toPrevious()`。

填充部件与模型的上一行数据，如果方向是水平的（默认值） ，否则由前一列的数据。

电话[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（内部） 。什么都不做，如果有在模型中没有前一行。

**See also** [toNext](qdatawidgetmapper.html#toNext)（）和[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（ ） 。

* * *

## Qt Signal Documentation

```
void currentIndexChanged (int)
```

这是该信号的默认超载。

这个信号被发射后，目前指数已经改变，所有的部件都填充了新的数据。_index_为新的当前索引。

**See also** [currentIndex](qdatawidgetmapper.html#currentIndex-prop)（）和[setCurrentIndex](qdatawidgetmapper.html#currentIndex-prop)（ ） 。