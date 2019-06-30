# QItemSelectionModel Class Reference

## [[QtGui](index.htm) module]

该QItemSelectionModel类跟踪视图的选定项目。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum SelectionFlag { NoUpdate, Clear, Select, Deselect, ..., ClearAndSelect }`
*   `class **[SelectionFlags](index.htm)**`

### Methods

*   `__init__ (self, QAbstractItemModel model)`
*   `__init__ (self, QAbstractItemModel model, QObject parent)`
*   `clear (self)`
*   `clearSelection (self)`
*   `bool columnIntersectsSelection (self, int column, QModelIndex parent)`
*   `QModelIndex currentIndex (self)`
*   `emitSelectionChanged (self, QItemSelection newSelection, QItemSelection oldSelection)`
*   `bool hasSelection (self)`
*   `bool isColumnSelected (self, int column, QModelIndex parent)`
*   `bool isRowSelected (self, int row, QModelIndex parent)`
*   `bool isSelected (self, QModelIndex index)`
*   `QAbstractItemModel model (self)`
*   `reset (self)`
*   `bool rowIntersectsSelection (self, int row, QModelIndex parent)`
*   `select (self, QModelIndex index, SelectionFlags command)`
*   `select (self, QItemSelection selection, SelectionFlags command)`
*   `list-of-QModelIndex selectedColumns (self, int row = 0)`
*   `list-of-QModelIndex selectedIndexes (self)`
*   `list-of-QModelIndex selectedRows (self, int column = 0)`
*   `QItemSelection selection (self)`
*   `setCurrentIndex (self, QModelIndex index, SelectionFlags command)`

### Qt Signals

*   `void currentChanged (const QModelIndex&,const QModelIndex&)`
*   `void currentColumnChanged (const QModelIndex&,const QModelIndex&)`
*   `void currentRowChanged (const QModelIndex&,const QModelIndex&)`
*   `void selectionChanged (const QItemSelection&,const QItemSelection&)`

* * *

## Detailed Description

该QItemSelectionModel类跟踪视图的选定项目。

一个QItemSelectionModel跟踪选定的项目在一个视图或多个视图到同一个模型。它也跟踪当前所选项目的视图中。

该QItemSelectionModel类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

所选择的项目，采用范围存储。每当你要修改的选定项目[select](qitemselectionmodel.html#select)（ ），并提供任一[QItemSelection](qitemselection.html)或[QModelIndex](qmodelindex.html)和[QItemSelectionModel.SelectionFlag](qitemselectionmodel.html#SelectionFlag-enum)。

该QItemSelectionModel需要一个两层的方法来选择管理，处理已提交双方选定的项目，并且是当前选择的一部分项目。在当前选择的项目是当前交互的选择（例如用橡皮筋选择或键盘移位的选择）的一部分。

要更新当前选定的项目，使用或按位[QItemSelectionModel.Current](qitemselectionmodel.html#SelectionFlag-enum)和任何其它的[SelectionFlags](qitemselectionmodel.html#SelectionFlag-enum)。如果省略了[QItemSelectionModel.Current](qitemselectionmodel.html#SelectionFlag-enum)命令，新的当前选择将被创建，并且前一个加入到整个选择。所有的功能在两个层次上作业，例如， selectedItems （ ）将从两个层返回的项目。

* * *

## Type Documentation

```
QItemSelectionModel.SelectionFlag
```

这个枚举变量描述的方式选择模型将被更新。

| Constant | Value | Description |
| --- | --- | --- |
| `QItemSelectionModel.NoUpdate` | `0x0000` | 没有选择将会作出修改。 |
| `QItemSelectionModel.Clear` | `0x0001` | 完整的选择将被清零。 |
| `QItemSelectionModel.Select` | `0x0002` | 所有指定的索引将被选中。 |
| `QItemSelectionModel.Deselect` | `0x0004` | 所有指定的索引将被取消。 |
| `QItemSelectionModel.Toggle` | `0x0008` | 所有指定的索引将被选择或取消选择取决于它们的当前状态。 |
| `QItemSelectionModel.Current` | `0x0010` | 当前的选择将被更新。 |
| `QItemSelectionModel.Rows` | `0x0020` | 所有索引将扩大到跨越行。 |
| `QItemSelectionModel.Columns` | `0x0040` | 所有索引将扩大到跨列。 |
| `QItemSelectionModel.SelectCurrent` | `Select &#124; Current` | 选择和电流的组合，提供了方便。 |
| `QItemSelectionModel.ToggleCurrent` | `Toggle &#124; Current` | 切换和电流的组合，提供了方便。 |
| `QItemSelectionModel.ClearAndSelect` | `Clear &#124; Select` | 清除和选择的组合，提供了方便。 |

该SelectionFlags类型是一个typedef为[QFlags](index.htm)\u003cSelectionFlag\u003e 。它存储SelectionFlag值的或组合。

* * *

## Method Documentation

```
QItemSelectionModel.__init__ (self, QAbstractItemModel model)
```

构造一个运行在指定项目的选择模型_model_。

```
QItemSelectionModel.__init__ (self, QAbstractItemModel model, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个运行在指定项目的选择模型_model_同_parent_。

```
QItemSelectionModel.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

清除选择模型。发射[selectionChanged](qitemselectionmodel.html#selectionChanged)（）和[currentChanged](qitemselectionmodel.html#currentChanged)（ ） 。

```
QItemSelectionModel.clearSelection (self)
```

这种方法也是一个Qt槽与C + +的签名`void clearSelection()`。

清除选择中的选择模型。发射[selectionChanged](qitemselectionmodel.html#selectionChanged)（ ） 。

这个函数中引入了Qt 4.2中。

```
bool QItemSelectionModel.columnIntersectsSelection (self, int column, QModelIndex parent)
```

如果在所选择的任何项目，则返回True_column_用给定的_parent_。

```
QModelIndex QItemSelectionModel.currentIndex (self)
```

[

返回模型项指数目前的项目，或无效的索引，如果没有当前项目。

](qmodelindex.html)

[**See also**](qmodelindex.html) [setCurrentIndex](qitemselectionmodel.html#setCurrentIndex)（ ） 。

```
QItemSelectionModel.emitSelectionChanged (self, QItemSelection newSelection, QItemSelection oldSelection)
```

比较了两种选择_newSelection_和_oldSelection_并发出[selectionChanged](qitemselectionmodel.html#selectionChanged)（ ）与取消和选定的项目。

```
bool QItemSelectionModel.hasSelection (self)
```

返回True如果选择模型中包含的任何选择的范围，否则返回False 。

这个函数中引入了Qt 4.2中。

```
bool QItemSelectionModel.isColumnSelected (self, int column, QModelIndex parent)
```

如果所有项目中被选中，则返回True_column_用给定的_parent_。

注意，这个函数通常比调用更快[isSelected](qitemselectionmodel.html#isSelected)（）在同一列中，并且所有的项目不可选择的数据项都被忽略。

```
bool QItemSelectionModel.isRowSelected (self, int row, QModelIndex parent)
```

如果所有项目中被选中，则返回True_row_用给定的_parent_。

注意，这个函数通常比调用更快[isSelected](qitemselectionmodel.html#isSelected)（）在同一行和所有项目不可选择的数据项都被忽略。

```
bool QItemSelectionModel.isSelected (self, QModelIndex index)
```

返回True如果给定的模型项目_index_被选中。

```
QAbstractItemModel QItemSelectionModel.model (self)
```

[

返回由选择模型上操作的项目模型。

```
QItemSelectionModel.reset (self)
```

这种方法也是一个Qt槽与C + +的签名`void reset()`。

清除选择模型。不发射任何信号。

```
bool QItemSelectionModel.rowIntersectsSelection (self, int row, QModelIndex parent)
```

如果在所选择的任何项目，则返回True_row_用给定的_parent_。

```
QItemSelectionModel.select (self, QModelIndex index, SelectionFlags command)
```

这种方法也是一个Qt槽与C + +的签名`void select(const QModelIndex&,QItemSelectionModel::SelectionFlags)`。

](qabstractitemmodel.html)

[选择模型项目_index_使用指定的_command_，并发射](qabstractitemmodel.html)[selectionChanged](qitemselectionmodel.html#selectionChanged)（ ） 。

**See also** [QItemSelectionModel.SelectionFlags](qitemselectionmodel.html#SelectionFlag-enum)。

```
QItemSelectionModel.select (self, QItemSelection selection, SelectionFlags command)
```

这种方法也是一个Qt槽与C + +的签名`void select(const QItemSelection&,QItemSelectionModel::SelectionFlags)`。

选择项目_selection_使用指定的_command_，并发射[selectionChanged](qitemselectionmodel.html#selectionChanged)（ ） 。

**See also** [QItemSelectionModel.SelectionFlag](qitemselectionmodel.html#SelectionFlag-enum)。

```
list-of-QModelIndex QItemSelectionModel.selectedColumns (self, int row = 0)
```

返回该索引中的给定_row_对其中所有行被选中的列。

这个函数中引入了Qt 4.2中。

**See also** [selectedIndexes](qitemselectionmodel.html#selectedIndexes)（）和[selectedRows](qitemselectionmodel.html#selectedRows)（ ） 。

```
list-of-QModelIndex QItemSelectionModel.selectedIndexes (self)
```

返回所有选定的模型项目索引的列表。该列表包含没有重复，并没有排序。

```
list-of-QModelIndex QItemSelectionModel.selectedRows (self, int column = 0)
```

返回该索引中的给定_column_对所有列被选中的行。

这个函数中引入了Qt 4.2中。

**See also** [selectedIndexes](qitemselectionmodel.html#selectedIndexes)（）和[selectedColumns](qitemselectionmodel.html#selectedColumns)（ ） 。

```
QItemSelection QItemSelectionModel.selection (self)
```

[

返回存储在选择模型的选择范围。

```
QItemSelectionModel.setCurrentIndex (self, QModelIndex index, SelectionFlags command)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentIndex(const QModelIndex&,QItemSelectionModel::SelectionFlags)`。

](qitemselection.html)

[设定模型项目_index_为当前项目，并发射](qitemselection.html)[currentChanged](qitemselectionmodel.html#currentChanged)（ ） 。目前项目用于键盘导航和焦点指示，它是独立于任何选定的项目，虽然选择的项目也可以是当前项目。

根据指定的_command_时，_index_也可以成为当前选择的一部分。

**See also** [currentIndex](qitemselectionmodel.html#currentIndex)（）和[select](qitemselectionmodel.html#select)（ ） 。

* * *

## Qt Signal Documentation

```
void currentChanged (const QModelIndex&,const QModelIndex&)
```

这是该信号的默认超载。

这个信号被发射时的当前项的变化。该_previous_模型项目指标被替换_current_指标作为选择的当前项。

请注意，当产品模型被重新设定此信号将不被发射。

**See also** [currentIndex](qitemselectionmodel.html#currentIndex)（ ）[setCurrentIndex](qitemselectionmodel.html#setCurrentIndex)（）和[selectionChanged](qitemselectionmodel.html#selectionChanged)（ ） 。

```
void currentColumnChanged (const QModelIndex&,const QModelIndex&)
```

这是该信号的默认超载。

这个信号被发射，如果_current_项目的变化和它的列是不同的列_previous_目前的项目。

请注意，当产品模型被重新设定此信号将不被发射。

**See also** [currentChanged](qitemselectionmodel.html#currentChanged)（ ）[currentRowChanged](qitemselectionmodel.html#currentRowChanged)（ ）[currentIndex](qitemselectionmodel.html#currentIndex)（）和[setCurrentIndex](qitemselectionmodel.html#setCurrentIndex)（ ） 。

```
void currentRowChanged (const QModelIndex&,const QModelIndex&)
```

这是该信号的默认超载。

这个信号被发射，如果_current_项目的变化和它的行是不同的行_previous_目前的项目。

请注意，当产品模型被重新设定此信号将不被发射。

**See also** [currentChanged](qitemselectionmodel.html#currentChanged)（ ）[currentColumnChanged](qitemselectionmodel.html#currentColumnChanged)（ ）[currentIndex](qitemselectionmodel.html#currentIndex)（）和[setCurrentIndex](qitemselectionmodel.html#setCurrentIndex)（ ） 。

```
void selectionChanged (const QItemSelection&,const QItemSelection&)
```

这是该信号的默认超载。

这个信号被发射时的选择改变。在选择的变化被表示为一个项目的选择_deselected_项目和项目的选择_selected_项目。

请注意，目前指数从选择独立的变化。还要注意的是，当该项目模型复位这个信号将不发射。

**See also** [select](qitemselectionmodel.html#select)（）和[currentChanged](qitemselectionmodel.html#currentChanged)（ ） 。