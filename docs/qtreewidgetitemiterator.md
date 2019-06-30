# QTreeWidgetItemIterator Class Reference

## [[QtGui](index.htm) module]

该QTreeWidgetItemIterator类提供了一种方法来遍历一个项目[QTreeWidget](qtreewidget.html)实例。[More...](#details)

### Types

*   `enum IteratorFlag { All, Hidden, NotHidden, Selected, ..., UserFlag }`
*   `class **[IteratorFlags](index.htm)**`

### Methods

*   `__init__ (self, QTreeWidgetItemIterator it)`
*   `__init__ (self, QTreeWidget widget, IteratorFlags flags = QTreeWidgetItemIterator.All)`
*   `__init__ (self, QTreeWidgetItem item, IteratorFlags flags = QTreeWidgetItemIterator.All)`
*   `QTreeWidgetItem value (self)`

### Special Methods

*   `QTreeWidgetItemIterator __iadd__ (self, int n)`
*   `QTreeWidgetItemIterator __isub__ (self, int n)`

* * *

## Detailed Description

该QTreeWidgetItemIterator类提供了一种方法来遍历一个项目[QTreeWidget](qtreewidget.html)实例。

迭代器都将走在一个前序遍历顺序选择项目，从而访问父节点_before_它继续到子节点。

例如，下面的代码示例每个项目在树上，检查中对用户指定的搜索字符串的第一个列中的文本：

```
     QTreeWidgetItemIterator it(treeWidget);
     while (*it) {
         if ((*it)->text(0) == itemText)
             (*it)->setSelected(true);
         ++it;
     }

```

另外，也可以通过将某些过滤掉某些类型的节点的[flags](qtreewidgetitemiterator.html#IteratorFlag-enum)到QTreeWidgetItemIterator的构造函数。

* * *

## Type Documentation

```
QTreeWidgetItemIterator.IteratorFlag
```

这些标志可以被传递给一个[QTreeWidgetItemIterator](qtreewidgetitemiterator.html)构造函数（或 - 编在一起，如果超过一个时） ，从而使迭代器将只遍历匹配给定的标志，物品。

| Constant | Value |
| --- | --- |
| `QTreeWidgetItemIterator.All` | `0x00000000` |
| `QTreeWidgetItemIterator.Hidden` | `0x00000001` |
| `QTreeWidgetItemIterator.NotHidden` | `0x00000002` |
| `QTreeWidgetItemIterator.Selected` | `0x00000004` |
| `QTreeWidgetItemIterator.Unselected` | `0x00000008` |
| `QTreeWidgetItemIterator.Selectable` | `0x00000010` |
| `QTreeWidgetItemIterator.NotSelectable` | `0x00000020` |
| `QTreeWidgetItemIterator.DragEnabled` | `0x00000040` |
| `QTreeWidgetItemIterator.DragDisabled` | `0x00000080` |
| `QTreeWidgetItemIterator.DropEnabled` | `0x00000100` |
| `QTreeWidgetItemIterator.DropDisabled` | `0x00000200` |
| `QTreeWidgetItemIterator.HasChildren` | `0x00000400` |
| `QTreeWidgetItemIterator.NoChildren` | `0x00000800` |
| `QTreeWidgetItemIterator.Checked` | `0x00001000` |
| `QTreeWidgetItemIterator.NotChecked` | `0x00002000` |
| `QTreeWidgetItemIterator.Enabled` | `0x00004000` |
| `QTreeWidgetItemIterator.Disabled` | `0x00008000` |
| `QTreeWidgetItemIterator.Editable` | `0x00010000` |
| `QTreeWidgetItemIterator.NotEditable` | `0x00020000` |
| `QTreeWidgetItemIterator.UserFlag` | `0x01000000` |

该IteratorFlags类型是一个typedef为[QFlags](index.htm)\u003cIteratorFlag\u003e 。它存储IteratorFlag值的或组合。

* * *

## Method Documentation

```
QTreeWidgetItemIterator.__init__ (self, QTreeWidgetItemIterator it)
```

构造一个迭代器相同[QTreeWidget](qtreewidget.html)如_it_。当前迭代项设置为点上的当前项目_it_。

```
QTreeWidgetItemIterator.__init__ (self, QTreeWidget widget, IteratorFlags flags = QTreeWidgetItemIterator.All)
```

构造一个迭代器对给定的_widget_使用指定的_flags_以确定哪些迭代过程中发现的项目。迭代器被设置为指向包含在插件的第一个顶级项目，或下一个匹配的项目，如果在最上层的项目不匹配的标志。

**See also** [QTreeWidgetItemIterator.IteratorFlag](qtreewidgetitemiterator.html#IteratorFlag-enum)。

```
QTreeWidgetItemIterator.__init__ (self, QTreeWidgetItem item, IteratorFlags flags = QTreeWidgetItemIterator.All)
```

构造一个迭代器对给定的_item_使用指定的_flags_以确定哪些迭代过程中发现的项目。迭代器被设置为指向_item_，或下一个匹配的项目，如果_item_不匹配的标志。

**See also** [QTreeWidgetItemIterator.IteratorFlag](qtreewidgetitemiterator.html#IteratorFlag-enum)。

```
QTreeWidgetItem QTreeWidgetItemIterator.value (self)
```

[](qtreewidgetitem.html)

```
QTreeWidgetItemIterator QTreeWidgetItemIterator.__iadd__ (self, int n)
```

[](qtreewidgetitemiterator.html)

```
QTreeWidgetItemIterator QTreeWidgetItemIterator.__isub__ (self, int n)
```

[](qtreewidgetitemiterator.html)