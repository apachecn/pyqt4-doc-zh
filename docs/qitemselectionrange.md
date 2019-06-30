# QItemSelectionRange Class Reference

## [[QtGui](index.htm) module]

该QItemSelectionRange类管理有关的一系列模型中的选定项目的信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QItemSelectionRange other)`
*   `__init__ (self, QModelIndex atopLeft, QModelIndex abottomRight)`
*   `__init__ (self, QModelIndex index)`
*   `int bottom (self)`
*   `QModelIndex bottomRight (self)`
*   `bool contains (self, QModelIndex index)`
*   `bool contains (self, int row, int column, QModelIndex parentIndex)`
*   `int height (self)`
*   `list-of-QModelIndex indexes (self)`
*   `QItemSelectionRange intersect (self, QItemSelectionRange other)`
*   `QItemSelectionRange intersected (self, QItemSelectionRange other)`
*   `bool intersects (self, QItemSelectionRange other)`
*   `bool isEmpty (self)`
*   `bool isValid (self)`
*   `int left (self)`
*   `QAbstractItemModel model (self)`
*   `QModelIndex parent (self)`
*   `int right (self)`
*   `int top (self)`
*   `QModelIndex topLeft (self)`
*   `int width (self)`

### Special Methods

*   `bool __eq__ (self, QItemSelectionRange other)`
*   `bool __ge__ (self, QItemSelectionRange other)`
*   `int __hash__ (self)`
*   `bool __lt__ (self, QItemSelectionRange other)`
*   `bool __ne__ (self, QItemSelectionRange other)`

* * *

## Detailed Description

该QItemSelectionRange类管理有关的一系列模型中的选定项目的信息。

一个QItemSelectionRange包含了一系列模型中选定项目的信息。件的范围是模型件的邻接阵列，延伸至包括多个相邻的行和列中具有共同的父项，这可以看作是细胞的表中的一个两维块。选择范围有[top](qitemselectionrange.html#top)（ ）[left](qitemselectionrange.html#left)（ ）一[bottom](qitemselectionrange.html#bottom)（ ）[right](qitemselectionrange.html#right)（）和一个[parent](qitemselectionrange.html#parent)（ ） 。

该QItemSelectionRange类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

包含在选择的范围中的模型项可使用所获得的[indexes](qitemselectionrange.html#indexes)（）函数。使用[QItemSelectionModel.selectedIndexes](qitemselectionmodel.html#selectedIndexes)（）来获取所有选定的项目的视图列表。

您可以决定是否给定的模型项目通过使用位于一个特定的范围内，[contains](qitemselectionrange.html#contains)（）函数。范围也可以使用重载运算符的平等和不平等相比，和[intersects](qitemselectionrange.html#intersects)（ ）函数允许您确定两个范围是否重叠。

* * *

## Method Documentation

```
QItemSelectionRange.__init__ (self)
```

构造一个空的选择范围。

```
QItemSelectionRange.__init__ (self, QItemSelectionRange other)
```

拷贝构造函数。构造一个新的选择范围与内容相同_other_范围内给出。

```
QItemSelectionRange.__init__ (self, QModelIndex atopLeft, QModelIndex abottomRight)
```

构造一个包含只能由指定的索引一个新的选择范围_topLeft_和索引_bottomRight_。

```
QItemSelectionRange.__init__ (self, QModelIndex index)
```

构造一个只包含由模型索引指定的模型项新的选择范围_index_。

```
int QItemSelectionRange.bottom (self)
```

返回对应于最下面选定行中的选择范围之列索引。

```
QModelIndex QItemSelectionRange.bottomRight (self)
```

[

返回指数位于的选择范围右下角的项目。

](qmodelindex.html)

[**See also**](qmodelindex.html) [bottom](qitemselectionrange.html#bottom)（ ）[right](qitemselectionrange.html#right)（）和[topLeft](qitemselectionrange.html#topLeft)（ ） 。

```
bool QItemSelectionRange.contains (self, QModelIndex index)
```

返回True如果指定的模型项目_index_位于所选项目的范围之内，否则返回False 。

```
bool QItemSelectionRange.contains (self, int row, int column, QModelIndex parentIndex)
```

这是一个重载函数。

如果指定的（模型项目，则返回True_row_，_column_）中，用_parentIndex_父项目位于所选项目的范围之内，否则返回False 。

```
int QItemSelectionRange.height (self)
```

返回值的选择范围中选择的行数。

```
list-of-QModelIndex QItemSelectionRange.indexes (self)
```

返回存储在选择模型索引项的列表。

```
QItemSelectionRange QItemSelectionRange.intersect (self, QItemSelectionRange other)
```

[](qitemselectionrange.html)

```
QItemSelectionRange QItemSelectionRange.intersected (self, QItemSelectionRange other)
```

[

返回一个包含仅被发现在选择范围的项目和一个新的选择范围_other_选择范围。

这个函数中引入了Qt 4.2中。

```
bool QItemSelectionRange.intersects (self, QItemSelectionRange other)
```

如果这个选择范围相交，则返回True （重叠含）_other_给定范围内，否则返回False 。

```
bool QItemSelectionRange.isEmpty (self)
```

如果选择范围不包含可选的项目，则返回True

此功能被引入Qt的4.7 。

```
bool QItemSelectionRange.isValid (self)
```

返回True如果选择范围是有效的，否则返回False 。

```
int QItemSelectionRange.left (self)
```

返回对应于选择范围最左边的选定列的列索引。

](qitemselectionrange.html)

```
QAbstractItemModel QItemSelectionRange.model (self)
```

[

返回在选择范围中的项目属于该模型。

](qabstractitemmodel.html)

```
QModelIndex QItemSelectionRange.parent (self)
```

[

返回在选择范围内的项目父模型项目索引。

```
int QItemSelectionRange.right (self)
```

返回对应于选择范围最右边的选定列的列索引。

```
int QItemSelectionRange.top (self)
```

返回对应于最上方的选定行中的选择范围之列索引。

](qmodelindex.html)

```
QModelIndex QItemSelectionRange.topLeft (self)
```

[

返回的索引位于选择范围的左上角的项目。

](qmodelindex.html)

[**See also**](qmodelindex.html) [top](qitemselectionrange.html#top)（ ）[left](qitemselectionrange.html#left)（）和[bottomRight](qitemselectionrange.html#bottomRight)（ ） 。

```
int QItemSelectionRange.width (self)
```

返回在选择范围内选择的列数。

```
bool QItemSelectionRange.__eq__ (self, QItemSelectionRange other)
```

```
bool QItemSelectionRange.__ge__ (self, QItemSelectionRange other)
```

```
int QItemSelectionRange.__hash__ (self)
```

```
bool QItemSelectionRange.__lt__ (self, QItemSelectionRange other)
```

```
bool QItemSelectionRange.__ne__ (self, QItemSelectionRange other)
```