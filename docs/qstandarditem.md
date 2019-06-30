# QStandardItem Class Reference

## [[QtGui](index.htm) module]

该QStandardItem类提供的项目与使用[QStandardItemModel](qstandarditemmodel.html)类。[More...](#details)

### Types

*   `enum ItemType { Type, UserType }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString text)`
*   `__init__ (self, QIcon icon, QString text)`
*   `__init__ (self, int rows, int columns = 1)`
*   `__init__ (self, QStandardItem other)`
*   `QString accessibleDescription (self)`
*   `QString accessibleText (self)`
*   `appendColumn (self, list-of-QStandardItem aitems)`
*   `appendRow (self, list-of-QStandardItem aitems)`
*   `appendRow (self, QStandardItem aitem)`
*   `appendRows (self, list-of-QStandardItem aitems)`
*   `QBrush background (self)`
*   `Qt.CheckState checkState (self)`
*   `QStandardItem child (self, int row, int column = 0)`
*   `QStandardItem clone (self)`
*   `int column (self)`
*   `int columnCount (self)`
*   `QVariant data (self, int role = Qt.UserRole+1)`
*   `emitDataChanged (self)`
*   `Qt.ItemFlags flags (self)`
*   `QFont font (self)`
*   `QBrush foreground (self)`
*   `bool hasChildren (self)`
*   `QIcon icon (self)`
*   `QModelIndex index (self)`
*   `insertColumn (self, int column, list-of-QStandardItem items)`
*   `insertColumns (self, int column, int count)`
*   `insertRow (self, int row, list-of-QStandardItem items)`
*   `insertRow (self, int arow, QStandardItem aitem)`
*   `insertRows (self, int row, int count)`
*   `insertRows (self, int row, list-of-QStandardItem items)`
*   `bool isCheckable (self)`
*   `bool isDragEnabled (self)`
*   `bool isDropEnabled (self)`
*   `bool isEditable (self)`
*   `bool isEnabled (self)`
*   `bool isSelectable (self)`
*   `bool isTristate (self)`
*   `QStandardItemModel model (self)`
*   `QStandardItem parent (self)`
*   `read (self, QDataStream in)`
*   `removeColumn (self, int column)`
*   `removeColumns (self, int column, int count)`
*   `removeRow (self, int row)`
*   `removeRows (self, int row, int count)`
*   `int row (self)`
*   `int rowCount (self)`
*   `setAccessibleDescription (self, QString aaccessibleDescription)`
*   `setAccessibleText (self, QString aaccessibleText)`
*   `setBackground (self, QBrush abrush)`
*   `setCheckable (self, bool checkable)`
*   `setCheckState (self, Qt.CheckState acheckState)`
*   `setChild (self, int row, int column, QStandardItem item)`
*   `setChild (self, int arow, QStandardItem aitem)`
*   `setColumnCount (self, int columns)`
*   `setData (self, QVariant value, int role = Qt.UserRole+1)`
*   `setDragEnabled (self, bool dragEnabled)`
*   `setDropEnabled (self, bool dropEnabled)`
*   `setEditable (self, bool editable)`
*   `setEnabled (self, bool enabled)`
*   `setFlags (self, Qt.ItemFlags flags)`
*   `setFont (self, QFont afont)`
*   `setForeground (self, QBrush abrush)`
*   `setIcon (self, QIcon aicon)`
*   `setRowCount (self, int rows)`
*   `setSelectable (self, bool selectable)`
*   `setSizeHint (self, QSize asizeHint)`
*   `setStatusTip (self, QString astatusTip)`
*   `setText (self, QString atext)`
*   `setTextAlignment (self, Qt.Alignment atextAlignment)`
*   `setToolTip (self, QString atoolTip)`
*   `setTristate (self, bool tristate)`
*   `setWhatsThis (self, QString awhatsThis)`
*   `QSize sizeHint (self)`
*   `sortChildren (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `QString statusTip (self)`
*   `QStandardItem takeChild (self, int row, int column = 0)`
*   `list-of-QStandardItem takeColumn (self, int column)`
*   `list-of-QStandardItem takeRow (self, int row)`
*   `QString text (self)`
*   `Qt.Alignment textAlignment (self)`
*   `QString toolTip (self)`
*   `int type (self)`
*   `QString whatsThis (self)`
*   `write (self, QDataStream out)`

### Special Methods

*   `bool __ge__ (self, QStandardItem other)`
*   `bool __lt__ (self, QStandardItem other)`

* * *

## Detailed Description

该QStandardItem类提供的项目与使用[QStandardItemModel](qstandarditemmodel.html)类。

项目通常包含文字，图标或复选框。

每个项目都可以有自己的背景刷子设置与[setBackground](qstandarditem.html#setBackground)（）函数。当前的背景刷可以找到[background](qstandarditem.html#background)（ ） 。每个项目的文本标籤可以有自己的字体和笔刷渲染。这些都与指定[setFont](qstandarditem.html#setFont)（）和[setForeground](qstandarditem.html#setForeground)（）函数，并读取与[font](qstandarditem.html#font)（）和[foreground](qstandarditem.html#foreground)（ ） 。

默认情况下，项目的启用，可编辑，可选择辨认的，可同时用作拖动的来源又是释放的操作和放置目标。每个项目的标志可以通过调用改变[setFlags](qstandarditem.html#setFlags)（ ） 。辨认的项目可以选中和未选中的[setCheckState](qstandarditem.html#setCheckState)（）函数。相应的[checkState](qstandarditem.html#checkState)（ ）函数表示该项目目前是否已选中。

你可以通过调用一个项目存储应用程序特定的数据[setData](qstandarditem.html#setData)（ ） 。

每个项目可以有一个二维子项表。这使得它可以构建项目的层次结构。典型的分层结构是树，在这种情况下，子表是一个表，用一个柱（列表）。

子表的尺寸可以与设置[setRowCount](qstandarditem.html#setRowCount)（）和[setColumnCount](qstandarditem.html#setColumnCount)（ ） 。物品可以放置在子表[setChild](qstandarditem.html#setChild)（ ） 。获取一个指针，指向一个子项与[child](qstandarditem.html#child)（ ） 。儿童的新的行和列，也可以插入[insertRow](qstandarditem.html#insertRow)（）和[insertColumn](qstandarditem.html#insertColumn)（），或者追加[appendRow](qstandarditem.html#appendRow)（）和[appendColumn](qstandarditem.html#appendColumn)（ ） 。当使用append和插入函数，子表的尺寸根据需要将增长。

儿童的现有行可以被删除[removeRow](qstandarditem.html#removeRow)（）或[takeRow](qstandarditem.html#takeRow)（）;相应地，一列可以具有去除[removeColumn](qstandarditem.html#removeColumn)（）或[takeColumn](qstandarditem.html#takeColumn)（ ） 。

一个项目的孩子可以通过调用进行排序[sortChildren](qstandarditem.html#sortChildren)（ ） 。

### Subclassing

当子类QStandardItem提供自定义项目，可以为他们定义新类型，使他们能够从基类区别开来。该[type](qstandarditem.html#type)（）函数应该被重新实现返回一个新的类型的值等于或大于[UserType](qstandarditem.html#ItemType-enum)。

重新实现[data](qstandarditem.html#data)（）和[setData](qstandarditem.html#setData)（ ）如果要执行数据查询的自定义处理和/或控制项的数据是如何表示的。

重新实现[clone](qstandarditem.html#clone)（ ）如果你想[QStandardItemModel](qstandarditemmodel.html)要能够根据需要创建自定义项目类的实例（见[QStandardItemModel.setItemPrototype](qstandarditemmodel.html#setItemPrototype)（））。

重新实现[read](qstandarditem.html#read)（）和[write](qstandarditem.html#write)（ ）如果你想控制项目如何代表他们的序列化形式。

重新实现[operator&lt;](qstandarditem.html#operator-lt)（ ）如果你想控制项目比较的语义。[operator&lt;](qstandarditem.html#operator-lt)（ ）确定排序顺序与排序项目时，[sortChildren](qstandarditem.html#sortChildren)（）或与[QStandardItemModel.sort](qstandarditemmodel.html#sort)（ ） 。

* * *

## Type Documentation

```
QStandardItem.ItemType
```

这个枚举变量描述了用于描述标准的项目的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QStandardItem.Type` | `0` | 默认类型为标准的项目。 |
| `QStandardItem.UserType` | `1000` | 对于自定义类型的最小值。以下用户等级和积分值被Qt保留。 |

您可以定义新的用户类型[QStandardItem](qstandarditem.html)子类以确保自定义项目经过特殊处理，例如，当项目进行排序。

**See also** [type](qstandarditem.html#type)（ ） 。

* * *

## Method Documentation

```
QStandardItem.__init__ (self)
```

构造一个项目。

```
QStandardItem.__init__ (self, QString text)
```

构造具有给定的项目_text_。

```
QStandardItem.__init__ (self, QIcon icon, QString text)
```

构造具有给定的项目_icon_和_text_。

```
QStandardItem.__init__ (self, int rows, int columns = 1)
```

构造与项目_rows_行和_columns_子项的列。

```
QStandardItem.__init__ (self, QStandardItem other)
```

构造的副本_other_。需要注意的是[model](qstandarditem.html#model)（ ）不会被复制。

重新实现时，此功能非常有用[clone](qstandarditem.html#clone)（ ） 。

```
QString QStandardItem.accessibleDescription (self)
```

返回该项目的可访问的描述。

可访问的说明是使用辅助技术（即谁不能用互动的传统方式用户） 。

**See also** [setAccessibleDescription](qstandarditem.html#setAccessibleDescription)（）和[accessibleText](qstandarditem.html#accessibleText)（ ） 。

```
QString QStandardItem.accessibleText (self)
```

返回该项目的访问的文本。

在访问的文本所使用的辅助技术（即谁不能使用交互的常规手段的用户） 。

**See also** [setAccessibleText](qstandarditem.html#setAccessibleText)（）和[accessibleDescription](qstandarditem.html#accessibleDescription)（ ） 。

```
QStandardItem.appendColumn (self, list-of-QStandardItem aitems)
```

该_aitems_说法有它的所有权转移给Qt的。

含追加一列_items_。如果有必要，该行数将增加至大小_items_。

**See also** [insertColumn](qstandarditem.html#insertColumn)（ ） 。

```
QStandardItem.appendRow (self, list-of-QStandardItem aitems)
```

该_aitems_说法有它的所有权转移给Qt的。

含追加的行_items_。如果需要的话，列计数值增加到的大小_items_。

**See also** [insertRow](qstandarditem.html#insertRow)（ ） 。

```
QStandardItem.appendRow (self, QStandardItem aitem)
```

该_aitem_说法有它的所有权转移给Qt的。

这是一个重载函数。

含追加的行_item_。

当建立一个列表，或者只有一列树，该功能提供了一种方便的方式来追加新的单一项目。

```
QStandardItem.appendRows (self, list-of-QStandardItem aitems)
```

该_aitems_说法有它的所有权转移给Qt的。

含追加行_items_。列计数不会改变。

**See also** [insertRow](qstandarditem.html#insertRow)（ ） 。

```
QBrush QStandardItem.background (self)
```

[

返回用于呈现项的背景的画笔。

](qbrush.html)

[**See also**](qbrush.html) [foreground](qstandarditem.html#foreground)（）和[setBackground](qstandarditem.html#setBackground)（ ） 。

```
Qt.CheckState QStandardItem.checkState (self)
```

[

返回项目的选中状态。

](qt.html#CheckState-enum)

[**See also**](qt.html#CheckState-enum) [setCheckState](qstandarditem.html#setCheckState)（）和[isCheckable](qstandarditem.html#isCheckable)（ ） 。

```
QStandardItem QStandardItem.child (self, int row, int column = 0)
```

[

返回位于（子项_row_，_column_）如果已设置，否则返回0 。

](qstandarditem.html)

[**See also**](qstandarditem.html) [setChild](qstandarditem.html#setChild)（ ）[takeChild](qstandarditem.html#takeChild)（）和[parent](qstandarditem.html#parent)（ ） 。

```
QStandardItem QStandardItem.clone (self)
```

[

返回此文件的副本。该项目的孩子不会被复制。

](qstandarditem.html)

[当子类](qstandarditem.html)[QStandardItem](qstandarditem.html)，你可以重新实现此功能提供[QStandardItemModel](qstandarditemmodel.html)用它可以用来创建随需应变的新项目工厂。

**See also** [QStandardItemModel.setItemPrototype](qstandarditemmodel.html#setItemPrototype)（）和[operator=](qstandarditem.html#operator-eq)（ ） 。

```
int QStandardItem.column (self)
```

返回列该项目位于其父的子表，或-1，如果该项目没有父。

**See also** [row](qstandarditem.html#row)（）和[parent](qstandarditem.html#parent)（ ） 。

```
int QStandardItem.columnCount (self)
```

返回子项列，该项目具有数量。

**See also** [setColumnCount](qstandarditem.html#setColumnCount)（）和[rowCount](qstandarditem.html#rowCount)（ ） 。

```
QVariant QStandardItem.data (self, int role = Qt.UserRole+1)
```

返回的项目的数据为给定的_role_，或无效[QVariant](qvariant.html)如果不存在数据的作用。

**Note:**默认实现对待[Qt.EditRole](qt.html#ItemDataRole-enum)和[Qt.DisplayRole](qt.html#ItemDataRole-enum)为是指相同的数据。

**See also** [setData](qstandarditem.html#setData)（ ） 。

```
QStandardItem.emitDataChanged (self)
```

原因与此文件相关的模型发出[dataChanged](qabstractitemmodel.html#dataChanged)（）信号为这个项目。

你通常只需要调用这个函数，如果你有子类[QStandardItem](qstandarditem.html)并重新实现[data](qstandarditem.html#data)（ ）和/或[setData](qstandarditem.html#setData)（ ） 。

此功能被引入Qt的4.4 。

**See also** [setData](qstandarditem.html#setData)（ ） 。

```
Qt.ItemFlags QStandardItem.flags (self)
```

[

返回项标志的项目。

项目标志确定用户如何能够与项目交互。

默认情况下，项目的启用，可编辑，可选择辨认的，可同时用作拖动的来源又是释放的操作和放置目标。

](index.htm)

[**See also**](index.htm) [setFlags](qstandarditem.html#setFlags)（ ） 。

```
QFont QStandardItem.font (self)
```

[

返回用于呈现项的文本的字体。

](qfont.html)

[**See also**](qfont.html) [setFont](qstandarditem.html#setFont)（ ） 。

```
QBrush QStandardItem.foreground (self)
```

[

返回用于呈现项目的前景（如文字）的笔刷。

](qbrush.html)

[**See also**](qbrush.html) [setForeground](qstandarditem.html#setForeground)（）和[background](qstandarditem.html#background)（ ） 。

```
bool QStandardItem.hasChildren (self)
```

返回True如果资料有任何子女;否则返回False。

**See also** [rowCount](qstandarditem.html#rowCount)（ ）[columnCount](qstandarditem.html#columnCount)（）和[child](qstandarditem.html#child)（ ） 。

```
QIcon QStandardItem.icon (self)
```

[

返回该项目的图标。

](qicon.html)

[**See also**](qicon.html) [setIcon](qstandarditem.html#setIcon)（）和[iconSize](qabstractitemview.html#iconSize-prop)。

```
QModelIndex QStandardItem.index (self)
```

[](qmodelindex.html)

[返回](qmodelindex.html)[QModelIndex](qmodelindex.html)与此文件相关。

当你需要调用一个功能项[QModelIndex](qmodelindex.html)的API （例如[QAbstractItemView](qabstractitemview.html)） ，你可以调用这个函数来获得与该项目的位置在模型中的索引。

如果该项目没有与模型，无效的关联[QModelIndex](qmodelindex.html)返回。

**See also** [model](qstandarditem.html#model)（）和[QStandardItemModel.itemFromIndex](qstandarditemmodel.html#itemFromIndex)（ ） 。

```
QStandardItem.insertColumn (self, int column, list-of-QStandardItem items)
```

该_items_说法有它的所有权转移给Qt的。

在插入一列_column_ containing _items_。如果有必要，该行数将增加至大小_items_。

**See also** [insertColumns](qstandarditem.html#insertColumns)（）和[insertRow](qstandarditem.html#insertRow)（ ） 。

```
QStandardItem.insertColumns (self, int column, int count)
```

Inserts _count_在柱子项的列_column_。

**See also** [insertColumn](qstandarditem.html#insertColumn)（）和[insertRows](qstandarditem.html#insertRows)（ ） 。

```
QStandardItem.insertRow (self, int row, list-of-QStandardItem items)
```

该_items_说法有它的所有权转移给Qt的。

插入一个一行_row_ containing _items_。如果需要的话，列计数值增加到的大小_items_。

**See also** [insertRows](qstandarditem.html#insertRows)（）和[insertColumn](qstandarditem.html#insertColumn)（ ） 。

```
QStandardItem.insertRow (self, int arow, QStandardItem aitem)
```

该_aitem_说法有它的所有权转移给Qt的。

这是一个重载函数。

插入一个一行_row_ containing _item_。

当建立一个列表，或者只有一列树，该功能提供了一种方便的方式来插入一个新的项目。

```
QStandardItem.insertRows (self, int row, int count)
```

Inserts _items_在_row_。列计数不会改变。

**See also** [insertRow](qstandarditem.html#insertRow)（）和[insertColumn](qstandarditem.html#insertColumn)（ ） 。

```
QStandardItem.insertRows (self, int row, list-of-QStandardItem items)
```

该_items_说法有它的所有权转移给Qt的。

Inserts _count_在一行行的子项_row_。

**See also** [insertRow](qstandarditem.html#insertRow)（）和[insertColumns](qstandarditem.html#insertColumns)（ ） 。

```
bool QStandardItem.isCheckable (self)
```

返回该项目是否是用户可选中。

默认值是False 。

**See also** [setCheckable](qstandarditem.html#setCheckable)（ ）[checkState](qstandarditem.html#checkState)（）和[isTristate](qstandarditem.html#isTristate)（ ） 。

```
bool QStandardItem.isDragEnabled (self)
```

返回该项目是否启用拖动。一个项目，是拖拉启用可以由用户进行拖动。

默认值是True 。

请注意，项目必须拖着在视图中启用拖放到工作;看[QAbstractItemView.dragEnabled](qabstractitemview.html#dragEnabled-prop)。

**See also** [setDragEnabled](qstandarditem.html#setDragEnabled)（ ）[isDropEnabled](qstandarditem.html#isDropEnabled)（）和[flags](qstandarditem.html#flags)（ ） 。

```
bool QStandardItem.isDropEnabled (self)
```

返回该项目是否下降启用。当一个项目是下拉使能时，它可以作为一个放置目标。

默认值是True 。

**See also** [setDropEnabled](qstandarditem.html#setDropEnabled)（ ）[isDragEnabled](qstandarditem.html#isDragEnabled)（）和[flags](qstandarditem.html#flags)（ ） 。

```
bool QStandardItem.isEditable (self)
```

返回是否该项目可以由用户进行编辑。

当一个项目是可编辑的（并启用） ，用户可以通过调用视图的编辑触发器中的一个编辑的项目;见[QAbstractItemView.editTriggers](qabstractitemview.html#editTriggers-prop)。

默认值是True 。

**See also** [setEditable](qstandarditem.html#setEditable)（）和[flags](qstandarditem.html#flags)（ ） 。

```
bool QStandardItem.isEnabled (self)
```

返回该项是否已启用。

当一个项目被启用，用户可以与它进行交互。可能的类型的交互是由其它产品的标志，如指定[isEditable](qstandarditem.html#isEditable)（）和[isSelectable](qstandarditem.html#isSelectable)（ ） 。

默认值是True 。

**See also** [setEnabled](qstandarditem.html#setEnabled)（）和[flags](qstandarditem.html#flags)（ ） 。

```
bool QStandardItem.isSelectable (self)
```

返回该产品是否是由用户选择的。

默认值是True 。

**See also** [setSelectable](qstandarditem.html#setSelectable)（）和[flags](qstandarditem.html#flags)（ ） 。

```
bool QStandardItem.isTristate (self)
```

该项目的回报是否是三态的，也就是说，如果它是可复用三个分开的状态。

默认值是False 。

**See also** [setTristate](qstandarditem.html#setTristate)（ ）[isCheckable](qstandarditem.html#isCheckable)（）和[checkState](qstandarditem.html#checkState)（ ） 。

```
QStandardItemModel QStandardItem.model (self)
```

[](qstandarditemmodel.html)

[返回](qstandarditemmodel.html)[QStandardItemModel](qstandarditemmodel.html)此项目属于。

如果该项目不属于模型的另一个项目的一个孩子，这个函数返回0 。

**See also** [index](qstandarditem.html#index)（ ） 。

```
QStandardItem QStandardItem.parent (self)
```

[

返回该项目的父项目，或者0，如果该项目没有父。

](qstandarditem.html)

[**See also**](qstandarditem.html) [child](qstandarditem.html#child)（ ） 。

```
QStandardItem.read (self, QDataStream in)
```

从流中读取的项目_in_。唯一的项的数据和标志读，而不是子项。

**See also** [write](qstandarditem.html#write)（ ） 。

```
QStandardItem.removeColumn (self, int column)
```

删除给定的_column_。这是该列中的项被删除。

**See also** [takeColumn](qstandarditem.html#takeColumn)（ ）[removeColumns](qstandarditem.html#removeColumns)（）和[removeRow](qstandarditem.html#removeRow)（ ） 。

```
QStandardItem.removeColumns (self, int column, int count)
```

移除_count_在列的列_column_。这是这些列中的项将被删除。

**See also** [removeColumn](qstandarditem.html#removeColumn)（）和[removeRows](qstandarditem.html#removeRows)（ ） 。

```
QStandardItem.removeRow (self, int row)
```

删除给定的_row_。这是该行中的项目被删除。

**See also** [takeRow](qstandarditem.html#takeRow)（ ）[removeRows](qstandarditem.html#removeRows)（）和[removeColumn](qstandarditem.html#removeColumn)（ ） 。

```
QStandardItem.removeRows (self, int row, int count)
```

移除_count_在一行行_row_。这是在这些行中的项目都将被删除。

**See also** [removeRow](qstandarditem.html#removeRow)（）和[removeColumn](qstandarditem.html#removeColumn)（ ） 。

```
int QStandardItem.row (self)
```

返回该行所在的项目位于其父的子表，或-1，如果该项目没有父。

**See also** [column](qstandarditem.html#column)（）和[parent](qstandarditem.html#parent)（ ） 。

```
int QStandardItem.rowCount (self)
```

返回该项目具有子项的行数。

**See also** [setRowCount](qstandarditem.html#setRowCount)（）和[columnCount](qstandarditem.html#columnCount)（ ） 。

```
QStandardItem.setAccessibleDescription (self, QString aaccessibleDescription)
```

设置项目的访问描述为字符串由指定的_accessibleDescription_。

可访问的说明是使用辅助技术（即谁不能用互动的传统方式用户） 。

**See also** [accessibleDescription](qstandarditem.html#accessibleDescription)（）和[setAccessibleText](qstandarditem.html#setAccessibleText)（ ） 。

```
QStandardItem.setAccessibleText (self, QString aaccessibleText)
```

设置项目的访问的文本由指定的字符串_accessibleText_。

在访问的文本所使用的辅助技术（即谁不能使用交互的常规手段的用户） 。

**See also** [accessibleText](qstandarditem.html#accessibleText)（）和[setAccessibleDescription](qstandarditem.html#setAccessibleDescription)（ ） 。

```
QStandardItem.setBackground (self, QBrush abrush)
```

设置项的背景刷到指定的_brush_。

**See also** [background](qstandarditem.html#background)（）和[setForeground](qstandarditem.html#setForeground)（ ） 。

```
QStandardItem.setCheckable (self, bool checkable)
```

设置项是否是用户可选中。如果_checkable_诚然，该项目可以由用户进行检查，否则用户无法检查的项目。

该项目委讬将呈现辨认的项目与项目旁边的文本的复选框。

**See also** [isCheckable](qstandarditem.html#isCheckable)（ ）[setCheckState](qstandarditem.html#setCheckState)（）和[setTristate](qstandarditem.html#setTristate)（ ） 。

```
QStandardItem.setCheckState (self, Qt.CheckState acheckState)
```

设置为项目的选中状态_state_。

**See also** [checkState](qstandarditem.html#checkState)（）和[setCheckable](qstandarditem.html#setCheckable)（ ） 。

```
QStandardItem.setChild (self, int row, int column, QStandardItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置在子项（_row_，_column_）至_item_。此产品（父项）需要的所有权_item_。如果必要，行数和列数都增加，以适应产品。

**See also** [child](qstandarditem.html#child)（ ） 。

```
QStandardItem.setChild (self, int arow, QStandardItem aitem)
```

该_aitem_说法有它的所有权转移给Qt的。

这是一个重载函数。

设定孩子_row_至_item_。

```
QStandardItem.setColumnCount (self, int columns)
```

设置子项的列数_columns_。如果它小于[columnCount](qstandarditem.html#columnCount)（） ，在不需要的列中的数据将被丢弃。

**See also** [columnCount](qstandarditem.html#columnCount)（）和[setRowCount](qstandarditem.html#setRowCount)（ ） 。

```
QStandardItem.setData (self, QVariant value, int role = Qt.UserRole+1)
```

设置项的数据为给定的_role_到指定的_value_。

如果子类[QStandardItem](qstandarditem.html)并且重新实现这个功能，你重新实现应该调用[emitDataChanged](qstandarditem.html#emitDataChanged)（ ）如果你不使用setData调用的基实现（ ） 。这将确保如使用模型视图通知的变化。

**Note:**默认实现对待[Qt.EditRole](qt.html#ItemDataRole-enum)和[Qt.DisplayRole](qt.html#ItemDataRole-enum)为是指相同的数据。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)，[data](qstandarditem.html#data)（）和[setFlags](qstandarditem.html#setFlags)（ ） 。

```
QStandardItem.setDragEnabled (self, bool dragEnabled)
```

设置项是否启用拖动。如果_dragEnabled_诚然，该项目可以由用户拖动，否则，用户无法拖曳项目。

请注意，您还需要确保该项目拖动在视图中启用;见[QAbstractItemView.dragEnabled](qabstractitemview.html#dragEnabled-prop)。

**See also** [isDragEnabled](qstandarditem.html#isDragEnabled)（ ）[setDropEnabled](qstandarditem.html#setDropEnabled)（）和[setFlags](qstandarditem.html#setFlags)（ ） 。

```
QStandardItem.setDropEnabled (self, bool dropEnabled)
```

设置项是否下降启用。如果_dropEnabled_诚然，该项目可作为放置目标，否则不能。

请注意，您还需要确保滴在视图中启用;见[QWidget.acceptDrops](qwidget.html#acceptDrops-prop)（）; ，且该模型支持所需的放置动作;见[QAbstractItemModel.supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ） 。

**See also** [isDropEnabled](qstandarditem.html#isDropEnabled)（ ）[setDragEnabled](qstandarditem.html#setDragEnabled)（）和[setFlags](qstandarditem.html#setFlags)（ ） 。

```
QStandardItem.setEditable (self, bool editable)
```

设置项是否可以编辑。如果_editable_诚然，该项目可以由用户进行编辑，否则用户无法编辑的项目。

如何通过视图的编辑触发器来确定用户可以编辑视图中的项目;见[QAbstractItemView.editTriggers](qabstractitemview.html#editTriggers-prop)。

**See also** [isEditable](qstandarditem.html#isEditable)（）和[setFlags](qstandarditem.html#setFlags)（ ） 。

```
QStandardItem.setEnabled (self, bool enabled)
```

设置该项是否已启用。如果_enabled_为真，则该项目被使能，这意味着用户可以与产品进行交互;若_enabled_为假，则用户不能与项目交互。

此标志优先于其他项目的标志;如如果项目没有被启用，它不能由用户选择的，即使[Qt.ItemIsSelectable](qt.html#ItemFlag-enum)标志已设置。

**See also** [isEnabled](qstandarditem.html#isEnabled)（ ）[Qt.ItemIsEnabled](qt.html#ItemFlag-enum)和[setFlags](qstandarditem.html#setFlags)（ ） 。

```
QStandardItem.setFlags (self, Qt.ItemFlags flags)
```

设置项标志的项目_flags_。

项目标志确定用户如何能够与项目交互。这通常被用于禁用的项目。

**See also** [flags](qstandarditem.html#flags)（）和[setData](qstandarditem.html#setData)（ ） 。

```
QStandardItem.setFont (self, QFont afont)
```

设置用于显示项目的文字给定的字体_font_。

**See also** [font](qstandarditem.html#font)（ ）[setText](qstandarditem.html#setText)（）和[setForeground](qstandarditem.html#setForeground)（ ） 。

```
QStandardItem.setForeground (self, QBrush abrush)
```

设置用于显示项目的前景（如文本）给定的画笔_brush_。

**See also** [foreground](qstandarditem.html#foreground)（ ）[setBackground](qstandarditem.html#setBackground)（）和[setFont](qstandarditem.html#setFont)（ ） 。

```
QStandardItem.setIcon (self, QIcon aicon)
```

设置项的图标_icon_规定。

**See also** [icon](qstandarditem.html#icon)（ ） 。

```
QStandardItem.setRowCount (self, int rows)
```

设置的子项目行数_rows_。如果它小于[rowCount](qstandarditem.html#rowCount)（） ，在不需要的行中的数据将被丢弃。

**See also** [rowCount](qstandarditem.html#rowCount)（）和[setColumnCount](qstandarditem.html#setColumnCount)（ ） 。

```
QStandardItem.setSelectable (self, bool selectable)
```

设置项是否可选。如果_selectable_诚然，该项目可以由用户来选择，否则，用户无法选择该项目。

您可以通过操纵自己的视图属性控制选择行为和模式，见[QAbstractItemView.selectionMode](qabstractitemview.html#selectionMode-prop)和[QAbstractItemView.selectionBehavior](qabstractitemview.html#selectionBehavior-prop)。

**See also** [isSelectable](qstandarditem.html#isSelectable)（）和[setFlags](qstandarditem.html#setFlags)（ ） 。

```
QStandardItem.setSizeHint (self, QSize asizeHint)
```

设置尺寸暗示该项目是_size_。如果没有大小的提示设置，基于项目数据的项目代表将计算尺寸暗示。

**See also** [sizeHint](qstandarditem.html#sizeHint)（ ） 。

```
QStandardItem.setStatusTip (self, QString astatusTip)
```

设置项目的状态提示由指定的字符串_statusTip_。

**See also** [statusTip](qstandarditem.html#statusTip)（ ）[setToolTip](qstandarditem.html#setToolTip)（）和[setWhatsThis](qstandarditem.html#setWhatsThis)（ ） 。

```
QStandardItem.setText (self, QString atext)
```

设置项的文字到_text_规定。

**See also** [text](qstandarditem.html#text)（ ）[setFont](qstandarditem.html#setFont)（）和[setForeground](qstandarditem.html#setForeground)（ ） 。

```
QStandardItem.setTextAlignment (self, Qt.Alignment atextAlignment)
```

设置文本对齐方式为项目的文字到_alignment_规定。

**See also** [textAlignment](qstandarditem.html#textAlignment)（ ） 。

```
QStandardItem.setToolTip (self, QString atoolTip)
```

设置项的提示通过指定的字符串_toolTip_。

**See also** [toolTip](qstandarditem.html#toolTip)（ ）[setStatusTip](qstandarditem.html#setStatusTip)（）和[setWhatsThis](qstandarditem.html#setWhatsThis)（ ） 。

```
QStandardItem.setTristate (self, bool tristate)
```

设置项是否为三态。如果_tristate_诚然，该项目是可复用三个独立的状态，否则，该项目是可复用两种状态。 （请注意，这也要求产品可复见[isCheckable](qstandarditem.html#isCheckable)（ ） 。 ）

**See also** [isTristate](qstandarditem.html#isTristate)（ ）[setCheckable](qstandarditem.html#setCheckable)（）和[setCheckState](qstandarditem.html#setCheckState)（ ） 。

```
QStandardItem.setWhatsThis (self, QString awhatsThis)
```

设置项的“这是什么？ ”有助于通过指定的字符串_whatsThis_。

**See also** [whatsThis](qstandarditem.html#whatsThis)（ ）[setStatusTip](qstandarditem.html#setStatusTip)（）和[setToolTip](qstandarditem.html#setToolTip)（ ） 。

```
QSize QStandardItem.sizeHint (self)
```

[](qsize.html)

[返回该项目的尺寸暗示组，或无效](qsize.html)[QSize](qsize.html)如果没有尺寸暗示已定。

如果没有大小提示已设置的基础上，项目数据的项目代表将计算尺寸暗示。

**See also** [setSizeHint](qstandarditem.html#setSizeHint)（ ） 。

```
QStandardItem.sortChildren (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

排序的项目的使用给定的孩子_order_通过在给定的值_column_。

**Note:**这个函数是递归的，因此它排序的项目，其孙子女，等孩子们

**See also** [operator&lt;](qstandarditem.html#operator-lt)（ ） 。

```
QString QStandardItem.statusTip (self)
```

返回项目的状态提示。

**See also** [setStatusTip](qstandarditem.html#setStatusTip)（ ）[toolTip](qstandarditem.html#toolTip)（）和[whatsThis](qstandarditem.html#whatsThis)（ ） 。

```
QStandardItem QStandardItem.takeChild (self, int row, int column = 0)
```

[

The _QStandardItem_ result

删除的子项（_row_，_column_）而不删除它，并返回一个指向的项目。如果没有孩子在给定的位置，那么这个函数返回0 。

](qstandarditem.html)

[注意，这个函数，不象](qstandarditem.html)[takeRow](qstandarditem.html#takeRow)（）和[takeColumn](qstandarditem.html#takeColumn)（ ） ，不影响子表的尺寸。

**See also** [child](qstandarditem.html#child)（ ）[takeRow](qstandarditem.html#takeRow)（）和[takeColumn](qstandarditem.html#takeColumn)（ ） 。

```
list-of-QStandardItem QStandardItem.takeColumn (self, int column)
```

该_list-of-QStandardItem_结果

移除_column_不删除的列项，并返回指针列表的删除的项。在尚未设定的列项，列表中的相应指针将是0 。

**See also** [removeColumn](qstandarditem.html#removeColumn)（ ）[insertColumn](qstandarditem.html#insertColumn)（）和[takeRow](qstandarditem.html#takeRow)（ ） 。

```
list-of-QStandardItem QStandardItem.takeRow (self, int row)
```

该_list-of-QStandardItem_结果

移除_row_不删除的行项目，并返回指针列表的删除的项目。对于没有被设置的行中的项目，列表中的相应指针将是0 。

**See also** [removeRow](qstandarditem.html#removeRow)（ ）[insertRow](qstandarditem.html#insertRow)（）和[takeColumn](qstandarditem.html#takeColumn)（ ） 。

```
QString QStandardItem.text (self)
```

返回项的文本。这是这是呈现给用户在视图中的文本。

**See also** [setText](qstandarditem.html#setText)（ ） 。

```
Qt.Alignment QStandardItem.textAlignment (self)
```

[

返回文本对齐方式项的文本。

](index.htm)

[**See also**](index.htm) [setTextAlignment](qstandarditem.html#setTextAlignment)（ ） 。

```
QString QStandardItem.toolTip (self)
```

返回该项目的工具提示。

**See also** [setToolTip](qstandarditem.html#setToolTip)（ ）[statusTip](qstandarditem.html#statusTip)（）和[whatsThis](qstandarditem.html#whatsThis)（ ） 。

```
int QStandardItem.type (self)
```

返回此项目的类型。该类型用于从基类区分自定义项目。当子类[QStandardItem](qstandarditem.html)，你应该重新实现这个函数，并返回一个新的值大于或等于[UserType](qstandarditem.html#ItemType-enum)。

**See also** [QStandardItem.Type](qstandarditem.html#ItemType-enum)。

```
QString QStandardItem.whatsThis (self)
```

返回该项目的“这是什么？ ”帮助。

**See also** [setWhatsThis](qstandarditem.html#setWhatsThis)（ ）[toolTip](qstandarditem.html#toolTip)（）和[statusTip](qstandarditem.html#statusTip)（ ） 。

```
QStandardItem.write (self, QDataStream out)
```

写入流的项目_out_。该项目的唯一的数据和标志都写，不是孩子的项目。

**See also** [read](qstandarditem.html#read)（ ） 。

```
bool QStandardItem.__ge__ (self, QStandardItem other)
```

```
bool QStandardItem.__lt__ (self, QStandardItem other)
```