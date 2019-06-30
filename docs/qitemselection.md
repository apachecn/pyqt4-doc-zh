# QItemSelection Class Reference

## [[QtGui](index.htm) module]

该QItemSelection类管理有关模型中的选定项目的信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QModelIndex topLeft, QModelIndex bottomRight)`
*   `__init__ (self, QItemSelection)`
*   `append (self, QItemSelectionRange range)`
*   `clear (self)`
*   `bool contains (self, QModelIndex index)`
*   `int count (self, QItemSelectionRange range)`
*   `int count (self)`
*   `QItemSelectionRange first (self)`
*   `list-of-QModelIndex indexes (self)`
*   `int indexOf (self, QItemSelectionRange value, int from = 0)`
*   `insert (self, int i, QItemSelectionRange range)`
*   `bool isEmpty (self)`
*   `QItemSelectionRange last (self)`
*   `int lastIndexOf (self, QItemSelectionRange value, int from = -1)`
*   `merge (self, QItemSelection other, QItemSelectionModel.SelectionFlags command)`
*   `move (self, int from, int to)`
*   `prepend (self, QItemSelectionRange range)`
*   `int removeAll (self, QItemSelectionRange range)`
*   `removeAt (self, int i)`
*   `replace (self, int i, QItemSelectionRange range)`
*   `select (self, QModelIndex topLeft, QModelIndex bottomRight)`
*   `swap (self, int i, int j)`
*   `QItemSelectionRange takeAt (self, int i)`
*   `QItemSelectionRange takeFirst (self)`
*   `QItemSelectionRange takeLast (self)`

### Static Methods

*   `split (QItemSelectionRange range, QItemSelectionRange other, QItemSelection result)`

### Special Methods

*   `int __contains__ (self, QModelIndex index)`
*   `__delitem__ (self, int i)`
*   `__delitem__ (self, slice slice)`
*   `bool __eq__ (self, QItemSelection other)`
*   `QItemSelectionRange __getitem__ (self, int i)`
*   `QItemSelection __getitem__ (self, slice slice)`
*   `QItemSelection __iadd__ (self, QItemSelection other)`
*   `QItemSelection __iadd__ (self, QItemSelectionRange value)`
*   `__len__ (self)`
*   `bool __ne__ (self, QItemSelection other)`
*   `__setitem__ (self, int i, QItemSelectionRange range)`
*   `__setitem__ (self, slice slice, QItemSelection list)`

* * *

## Detailed Description

该QItemSelection类管理有关模型中的选定项目的信息。

甲QItemSelection描述在已经由用户选择的模式中的项目。一个QItemSelection基本上是选择范围列表，请参阅[QItemSelectionRange](qitemselectionrange.html)。它提供了用于创建和操作选择，并从模型中选择一个范围内的项目。

该QItemSelection类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

项目选择可以构造并初始化为包含范围从现有的模型项目。下面的示例构造一个包含从给定的各类物品的选择`model`，开始在`topLeft`，和结束的`bottomRight`。

```
 QItemSelection *selection = new QItemSelection(topLeft, bottomRight);

```

一个空的项目选择可以构造，后来填充的要求。因此，如果模型要当我们构建了项目选择为不可用，我们可以重写上面的代码中的方法如下：

```
 QItemSelection *selection = new QItemSelection();
 ...
 selection->select(topLeft, bottomRight);

```

QItemSelection节省内存，并避免不必要的工作，通过与选择范围工作，而不是记录的模型项目的索引为每个项目中选择。一般来说，这个类的实例将包含非重叠选择范围的列表。

使用[merge](qitemselection.html#merge)（ ）合并一个项目的选择到另一个未做重叠的范围。使用[split](qitemselection.html#split)（ ）的基础上另外一个选择范围分割一个选择范围为更小的范围。

* * *

## Method Documentation

```
QItemSelection.__init__ (self)
```

构造一个空的选择。

```
QItemSelection.__init__ (self, QModelIndex topLeft, QModelIndex bottomRight)
```

构造一个项目选择，从左上角模型项目延伸，由指定的_topLeft_指数，在右下角项目，由指定的_bottomRight_。

```
QItemSelection.__init__ (self, QItemSelection)
```

```
QItemSelection.append (self, QItemSelectionRange range)
```

```
QItemSelection.clear (self)
```

```
bool QItemSelection.contains (self, QModelIndex index)
```

如果选择包含给定的，则返回True_index_否则返回False 。

```
int QItemSelection.count (self, QItemSelectionRange range)
```

```
int QItemSelection.count (self)
```

```
QItemSelectionRange QItemSelection.first (self)
```

[

```
list-of-QModelIndex QItemSelection.indexes (self)
```

返回对应于所选择的项的模型索引的列表。

```
int QItemSelection.indexOf (self, QItemSelectionRange value, int from = 0)
```

```
QItemSelection.insert (self, int i, QItemSelectionRange range)
```

```
bool QItemSelection.isEmpty (self)
```

](qitemselectionrange.html)

```
QItemSelectionRange QItemSelection.last (self)
```

[

```
int QItemSelection.lastIndexOf (self, QItemSelectionRange value, int from = -1)
```

```
QItemSelection.merge (self, QItemSelection other, QItemSelectionModel.SelectionFlags command)
```

](qitemselectionrange.html)

[合并的_other_选择与此](qitemselectionrange.html)[QItemSelection](qitemselection.html)使用_command_给出。这种方法保证了没有范围是重叠的。

请注意，只有[QItemSelectionModel.Select](qitemselectionmodel.html#SelectionFlag-enum)，[QItemSelectionModel.Deselect](qitemselectionmodel.html#SelectionFlag-enum)和[QItemSelectionModel.Toggle](qitemselectionmodel.html#SelectionFlag-enum)被支持。

**See also** [split](qitemselection.html#split)（ ） 。

```
QItemSelection.move (self, int from, int to)
```

```
QItemSelection.prepend (self, QItemSelectionRange range)
```

```
int QItemSelection.removeAll (self, QItemSelectionRange range)
```

```
QItemSelection.removeAt (self, int i)
```

```
QItemSelection.replace (self, int i, QItemSelectionRange range)
```

```
QItemSelection.select (self, QModelIndex topLeft, QModelIndex bottomRight)
```

添加该范围中的项目，从左上角的模型项上延伸，由指定的_topLeft_指数，在右下角项目，由指定的_bottomRight_到列表中。

**Note:** _topLeft_和_bottomRight_必须具有相同的父代。

```
QItemSelection.split (QItemSelectionRange range, QItemSelectionRange other, QItemSelection result)
```

拆分选择_range_使用选择_other_范围。在删除所有项目_other_从_range_并将该结果_result_。这可以用的语义进行比较_subtract_的一组操作。

**See also** [merge](qitemselection.html#merge)（ ） 。

```
QItemSelection.swap (self, int i, int j)
```

```
QItemSelectionRange QItemSelection.takeAt (self, int i)
```

[](qitemselectionrange.html)

```
QItemSelectionRange QItemSelection.takeFirst (self)
```

[](qitemselectionrange.html)

```
QItemSelectionRange QItemSelection.takeLast (self)
```

[

```
int QItemSelection.__contains__ (self, QModelIndex index)
```

```
QItemSelection.__delitem__ (self, int i)
```

```
QItemSelection.__delitem__ (self, slice slice)
```

```
bool QItemSelection.__eq__ (self, QItemSelection other)
```

](qitemselectionrange.html)

```
QItemSelectionRange QItemSelection.__getitem__ (self, int i)
```

[](qitemselectionrange.html)

```
QItemSelection QItemSelection.__getitem__ (self, slice slice)
```

[](qitemselection.html)

```
QItemSelection QItemSelection.__iadd__ (self, QItemSelection other)
```

[](qitemselection.html)

```
QItemSelection QItemSelection.__iadd__ (self, QItemSelectionRange value)
```

[

```
 QItemSelection.__len__ (self)
```

```
bool QItemSelection.__ne__ (self, QItemSelection other)
```

```
QItemSelection.__setitem__ (self, int i, QItemSelectionRange range)
```

```
QItemSelection.__setitem__ (self, slice slice, QItemSelection list)
```

](qitemselection.html)