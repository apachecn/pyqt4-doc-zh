# QTableWidgetSelectionRange Class Reference

## [[QtGui](index.htm) module]

该QTableWidgetSelectionRange类提供了一种与选择的模型，而无需使用模型索引和选择模型进行交互。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, int top, int left, int bottom, int right)`
*   `__init__ (self, QTableWidgetSelectionRange other)`
*   `int bottomRow (self)`
*   `int columnCount (self)`
*   `int leftColumn (self)`
*   `int rightColumn (self)`
*   `int rowCount (self)`
*   `int topRow (self)`

* * *

## Detailed Description

该QTableWidgetSelectionRange类提供了一种与选择的模型，而无需使用模型索引和选择模型进行交互。

该QTableWidgetSelectionRange类存储左上角和表中的右下方的行数和选择范围的列。在表中的选项可以由几个选择范围。

**Note:**如果选择范围内的项目被标记为不可选，例如，`itemFlags() & Qt.ItemIsSelectable == 0`那么就不会出现在选择范围内。

* * *

## Method Documentation

```
QTableWidgetSelectionRange.__init__ (self)
```

构造一个表的选择范围，即其范围[rowCount](qtablewidgetselectionrange.html#rowCount)（）和[columnCount](qtablewidgetselectionrange.html#columnCount)（）均为0。

```
QTableWidgetSelectionRange.__init__ (self, int top, int left, int bottom, int right)
```

构建表选择范围从给定的_top_，_left_，_bottom_和_right_表的行和列。

**See also** [topRow](qtablewidgetselectionrange.html#topRow)（ ）[leftColumn](qtablewidgetselectionrange.html#leftColumn)（ ）[bottomRow](qtablewidgetselectionrange.html#bottomRow)（）和[rightColumn](qtablewidgetselectionrange.html#rightColumn)（ ） 。

```
QTableWidgetSelectionRange.__init__ (self, QTableWidgetSelectionRange other)
```

通过复制特定构造一个表中选择范围_other_表的选择范围。

```
int QTableWidgetSelectionRange.bottomRow (self)
```

返回范围的最下面一行。

**See also** [topRow](qtablewidgetselectionrange.html#topRow)（ ）[rightColumn](qtablewidgetselectionrange.html#rightColumn)（）和[rowCount](qtablewidgetselectionrange.html#rowCount)（ ） 。

```
int QTableWidgetSelectionRange.columnCount (self)
```

返回的列的范围内的数目。

这等效于[rightColumn](qtablewidgetselectionrange.html#rightColumn)（） - [leftColumn](qtablewidgetselectionrange.html#leftColumn)（）+ 1 。

这个函数是Qt 4.1中引入。

**See also** [rowCount](qtablewidgetselectionrange.html#rowCount)（ ）[leftColumn](qtablewidgetselectionrange.html#leftColumn)（）和[rightColumn](qtablewidgetselectionrange.html#rightColumn)（ ） 。

```
int QTableWidgetSelectionRange.leftColumn (self)
```

返回范围的左栏。

**See also** [rightColumn](qtablewidgetselectionrange.html#rightColumn)（ ）[topRow](qtablewidgetselectionrange.html#topRow)（）和[columnCount](qtablewidgetselectionrange.html#columnCount)（ ） 。

```
int QTableWidgetSelectionRange.rightColumn (self)
```

返回该范围的右列。

**See also** [leftColumn](qtablewidgetselectionrange.html#leftColumn)（ ）[bottomRow](qtablewidgetselectionrange.html#bottomRow)（）和[columnCount](qtablewidgetselectionrange.html#columnCount)（ ） 。

```
int QTableWidgetSelectionRange.rowCount (self)
```

返回行范围内的号码。

这等效于[bottomRow](qtablewidgetselectionrange.html#bottomRow)（） - [topRow](qtablewidgetselectionrange.html#topRow)（）+ 1 。

这个函数是Qt 4.1中引入。

**See also** [columnCount](qtablewidgetselectionrange.html#columnCount)（ ）[topRow](qtablewidgetselectionrange.html#topRow)（）和[bottomRow](qtablewidgetselectionrange.html#bottomRow)（ ） 。

```
int QTableWidgetSelectionRange.topRow (self)
```

返回范围的顶行。

**See also** [bottomRow](qtablewidgetselectionrange.html#bottomRow)（ ）[leftColumn](qtablewidgetselectionrange.html#leftColumn)（）和[rowCount](qtablewidgetselectionrange.html#rowCount)（ ） 。