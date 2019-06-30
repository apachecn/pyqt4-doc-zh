# QTreeWidgetItem Class Reference

## [[QtGui](index.htm) module]

该QTreeWidgetItem类提供的项目与使用[QTreeWidget](qtreewidget.html)方便的类。[More...](#details)

### Types

*   `enum ChildIndicatorPolicy { ShowIndicator, DontShowIndicator, DontShowIndicatorWhenChildless }`
*   `enum ItemType { Type, UserType }`

### Methods

*   `__init__ (self, int type = QTreeWidgetItem.Type)`
*   `__init__ (self, QStringList strings, int type = QTreeWidgetItem.Type)`
*   `__init__ (self, QTreeWidget parent, int type = QTreeWidgetItem.Type)`
*   `__init__ (self, QTreeWidget parent, QStringList strings, int type = QTreeWidgetItem.Type)`
*   `__init__ (self, QTreeWidget parent, QTreeWidgetItem preceding, int type = QTreeWidgetItem.Type)`
*   `__init__ (self, QTreeWidgetItem parent, int type = QTreeWidgetItem.Type)`
*   `__init__ (self, QTreeWidgetItem parent, QStringList strings, int type = QTreeWidgetItem.Type)`
*   `__init__ (self, QTreeWidgetItem parent, QTreeWidgetItem preceding, int type = QTreeWidgetItem.Type)`
*   `__init__ (self, QTreeWidgetItem other)`
*   `addChild (self, QTreeWidgetItem child)`
*   `addChildren (self, list-of-QTreeWidgetItem children)`
*   `QBrush background (self, int column)`
*   `QColor backgroundColor (self, int column)`
*   `Qt.CheckState checkState (self, int column)`
*   `QTreeWidgetItem child (self, int index)`
*   `int childCount (self)`
*   `ChildIndicatorPolicy childIndicatorPolicy (self)`
*   `QTreeWidgetItem clone (self)`
*   `int columnCount (self)`
*   `QVariant data (self, int column, int role)`
*   `emitDataChanged (self)`
*   `Qt.ItemFlags flags (self)`
*   `QFont font (self, int column)`
*   `QBrush foreground (self, int column)`
*   `QIcon icon (self, int column)`
*   `int indexOfChild (self, QTreeWidgetItem achild)`
*   `insertChild (self, int index, QTreeWidgetItem child)`
*   `insertChildren (self, int index, list-of-QTreeWidgetItem children)`
*   `bool isDisabled (self)`
*   `bool isExpanded (self)`
*   `bool isFirstColumnSpanned (self)`
*   `bool isHidden (self)`
*   `bool isSelected (self)`
*   `QTreeWidgetItem parent (self)`
*   `read (self, QDataStream in)`
*   `removeChild (self, QTreeWidgetItem child)`
*   `setBackground (self, int column, QBrush brush)`
*   `setBackgroundColor (self, int column, QColor color)`
*   `setCheckState (self, int column, Qt.CheckState state)`
*   `setChildIndicatorPolicy (self, ChildIndicatorPolicy policy)`
*   `setData (self, int column, int role, QVariant value)`
*   `setDisabled (self, bool disabled)`
*   `setExpanded (self, bool aexpand)`
*   `setFirstColumnSpanned (self, bool aspan)`
*   `setFlags (self, Qt.ItemFlags aflags)`
*   `setFont (self, int column, QFont afont)`
*   `setForeground (self, int column, QBrush brush)`
*   `setHidden (self, bool ahide)`
*   `setIcon (self, int column, QIcon aicon)`
*   `setSelected (self, bool aselect)`
*   `setSizeHint (self, int column, QSize size)`
*   `setStatusTip (self, int column, QString astatusTip)`
*   `setText (self, int column, QString atext)`
*   `setTextAlignment (self, int column, int alignment)`
*   `setTextColor (self, int column, QColor color)`
*   `setToolTip (self, int column, QString atoolTip)`
*   `setWhatsThis (self, int column, QString awhatsThis)`
*   `QSize sizeHint (self, int column)`
*   `sortChildren (self, int column, Qt.SortOrder order)`
*   `QString statusTip (self, int column)`
*   `QTreeWidgetItem takeChild (self, int index)`
*   `list-of-QTreeWidgetItem takeChildren (self)`
*   `QString text (self, int column)`
*   `int textAlignment (self, int column)`
*   `QColor textColor (self, int column)`
*   `QString toolTip (self, int column)`
*   `QTreeWidget treeWidget (self)`
*   `int type (self)`
*   `QString whatsThis (self, int column)`
*   `write (self, QDataStream out)`

### Special Methods

*   `bool __ge__ (self, QTreeWidgetItem other)`
*   `bool __lt__ (self, QTreeWidgetItem other)`

* * *

## Detailed Description

该QTreeWidgetItem类提供的项目与使用[QTreeWidget](qtreewidget.html)方便的类。

树部件项目用于容纳的行信息树窗口小部件。行通常包含若干列的数据，每一个都可以包含一个文本标籤和一个图标。

该QTreeWidgetItem类是替换QListViewItem类的Qt 3一个方便的类。它提供了一种用于产品的使用[QTreeWidget](qtreewidget.html)类。

货品一般构造与父母，要么是一个[QTreeWidget](qtreewidget.html)（顶级项目）或QTreeWidgetItem （关于树的下级项目） 。例如，下面的代码构造一个顶级项目，代表了世界城市，并增加了对奥斯陆的一个子项一个条目：

```
     QTreeWidgetItem *cities = new QTreeWidgetItem(treeWidget);
     cities->setText(0, tr("Cities"));
     QTreeWidgetItem *osloItem = new QTreeWidgetItem(cities);
     osloItem->setText(0, tr("Oslo"));
     osloItem->setText(1, tr("Yes"));

```

项目可以在一个特定的顺序添加指定他们也跟着当他们建造的项目：

```
     QTreeWidgetItem *planets = new QTreeWidgetItem(treeWidget, cities);
     planets->setText(0, tr("Planets"));

```

在一个项目的每一列都可以有其自己的背景刷子设置与[setBackground](qtreewidgetitem.html#setBackground)（）函数。当前的背景刷可以找到[background](qtreewidgetitem.html#background)（ ） 。对每一列中的文本标籤可以与它自己的字体和刷子来呈现。这些都与指定[setFont](qtreewidgetitem.html#setFont)（）和[setForeground](qtreewidgetitem.html#setForeground)（）函数，并读取与[font](qtreewidgetitem.html#font)（）和[foreground](qtreewidgetitem.html#foreground)（ ） 。

顶级项目以及在该树的下级之间的主要区别在于，一个顶级项目没有[parent](qtreewidgetitem.html#parent)（ ） 。此信息可以用来告诉项目之间的差异，并且是要知道从树插入和取出物品时非常有用。一个项目的孩子们可以与被删除[takeChild](qtreewidgetitem.html#takeChild)（） ，并插入一个给定的索引中的儿童用的清单[insertChild](qtreewidgetitem.html#insertChild)（）函数。

默认情况下，项目的启用，可选择，可复，可一拖源和拖放操作。每个项目的标志可以通过调用改变[setFlags](qtreewidgetitem.html#setFlags)（ ）用适当的值（见[Qt.ItemFlags](qt.html#ItemFlag-enum)） 。辨认的项目可以选中和未选中的[setCheckState](qtreewidgetitem.html#setCheckState)（）函数。相应的[checkState](qtreewidgetitem.html#checkState)（ ）函数表示该项目目前是否已选中。

### Subclassing

当子类QTreeWidgetItem提供自定义项目，可以为他们定义新类型，使他们能够从标准的项目区别开来。该构造函数需要此功能的子类需要调用基类的构造函数有一个新的类型值等于或大于[UserType](qtreewidgetitem.html#ItemType-enum)。

* * *

## Type Documentation

```
QTreeWidgetItem.ChildIndicatorPolicy
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTreeWidgetItem.ShowIndicator` | `0` | 用于展开和折叠的控件将显示此项目，即使有没有孩子。 |
| `QTreeWidgetItem.DontShowIndicator` | `1` | 将永远不会被显示为展开和折叠的控制，即使有孩子。如果节点被强行打开，用户将无法展开或折叠的项目。 |
| `QTreeWidgetItem.DontShowIndicatorWhenChildless` | `2` | 用于展开和折叠的控件将显示，如果该项目包含了孩子。 |

这个枚举被引入或修改的Qt 4.3 。

```
QTreeWidgetItem.ItemType
```

这个枚举变量描述了用于描述树形控件项目的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QTreeWidgetItem.Type` | `0` | 默认类型为树部件项目。 |
| `QTreeWidgetItem.UserType` | `1000` | 对于自定义类型的最小值。以下用户等级和积分值被Qt保留。 |

您可以定义新的用户类型[QTreeWidgetItem](qtreewidgetitem.html)子类以确保自定义项目经过特殊处理，例如，当项目进行排序。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

* * *

## Method Documentation

```
QTreeWidgetItem.__init__ (self, int type = QTreeWidgetItem.Type)
```

构造一个指定的树部件项目_type_。该项目必须被插入到树部件。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

```
QTreeWidgetItem.__init__ (self, QStringList strings, int type = QTreeWidgetItem.Type)
```

构造一个指定的树部件项目_type_。该项目必须被插入到树部件。给定列表_strings_将被设置为项的文本项中的每一列。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

```
QTreeWidgetItem.__init__ (self, QTreeWidget parent, int type = QTreeWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个指定的树部件项目_type_和附加到它在给定的项目_parent_。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

```
QTreeWidgetItem.__init__ (self, QTreeWidget parent, QStringList strings, int type = QTreeWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个指定的树部件项目_type_和附加到它在给定的项目_parent_。给定列表_strings_将被设置为项的文本项中的每一列。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

```
QTreeWidgetItem.__init__ (self, QTreeWidget parent, QTreeWidgetItem preceding, int type = QTreeWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个指定的树部件项目_type_并将其插入到给定的_parent_后_preceding_项目。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

```
QTreeWidgetItem.__init__ (self, QTreeWidgetItem parent, int type = QTreeWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个树形控件项目，并将其附加到给定_parent_。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

```
QTreeWidgetItem.__init__ (self, QTreeWidgetItem parent, QStringList strings, int type = QTreeWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个树形控件项目，并将其附加到给定_parent_。给定列表_strings_将被设置为项的文本项中的每一列。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

```
QTreeWidgetItem.__init__ (self, QTreeWidgetItem parent, QTreeWidgetItem preceding, int type = QTreeWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个指定的树部件项目_type_该插入_parent_后_preceding_子项。

**See also** [type](qtreewidgetitem.html#type)（ ） 。

```
QTreeWidgetItem.__init__ (self, QTreeWidgetItem other)
```

构造的副本_other_。需要注意的是[type](qtreewidgetitem.html#type)（）和[treeWidget](qtreewidgetitem.html#treeWidget)（ ）不会被复制。

重新实现时，此功能非常有用[clone](qtreewidgetitem.html#clone)（ ） 。

这个函数是Qt 4.1中引入。

**See also** [data](qtreewidgetitem.html#data)（）和[flags](qtreewidgetitem.html#flags)（ ） 。

```
QTreeWidgetItem.addChild (self, QTreeWidgetItem child)
```

该_child_说法有它的所有权转移给Qt的。

追加_child_项子项列表。

**See also** [insertChild](qtreewidgetitem.html#insertChild)（）和[takeChild](qtreewidgetitem.html#takeChild)（ ） 。

```
QTreeWidgetItem.addChildren (self, list-of-QTreeWidgetItem children)
```

该_children_说法有它的所有权转移给Qt的。

附加的给定列表_children_到该项目。

这个函数是Qt 4.1中引入。

**See also** [insertChildren](qtreewidgetitem.html#insertChildren)（）和[takeChildren](qtreewidgetitem.html#takeChildren)（ ） 。

```
QBrush QTreeWidgetItem.background (self, int column)
```

[

返回用于呈现指定的背景刷_column_。

这个函数中引入了Qt 4.2中。

](qbrush.html)

[**See also**](qbrush.html) [setBackground](qtreewidgetitem.html#setBackground)（）和[foreground](qtreewidgetitem.html#foreground)（ ） 。

```
QColor QTreeWidgetItem.backgroundColor (self, int column)
```

[](qcolor.html)

```
Qt.CheckState QTreeWidgetItem.checkState (self, int column)
```

[

返回指定标籤的检查状态_column_。

](qt.html#CheckState-enum)

[**See also**](qt.html#CheckState-enum) [setCheckState](qtreewidgetitem.html#setCheckState)（）和[Qt.CheckState](qt.html#CheckState-enum)。

```
QTreeWidgetItem QTreeWidgetItem.child (self, int index)
```

[

返回在给定的项目_index_在该项目的孩子列表。

](qtreewidgetitem.html)

[**See also**](qtreewidgetitem.html) [parent](qtreewidgetitem.html#parent)（ ） 。

```
int QTreeWidgetItem.childCount (self)
```

返回子项的数量。

```
ChildIndicatorPolicy QTreeWidgetItem.childIndicatorPolicy (self)
```

[

返回该项指标的政策。这一政策决定时，树枝展开/折叠指示器。

](qtreewidgetitem.html#ChildIndicatorPolicy-enum)

[**See also**](qtreewidgetitem.html#ChildIndicatorPolicy-enum) [setChildIndicatorPolicy](qtreewidgetitem.html#setChildIndicatorPolicy)（ ） 。

```
QTreeWidgetItem QTreeWidgetItem.clone (self)
```

[

创建其子项的项目和深拷贝。

```
int QTreeWidgetItem.columnCount (self)
```

返回列中的项数。

```
QVariant QTreeWidgetItem.data (self, int column, int role)
```

返回该项目的价值_column_和_role_。

](qtreewidgetitem.html)

[**See also**](qtreewidgetitem.html) [setData](qtreewidgetitem.html#setData)（ ） 。

```
QTreeWidgetItem.emitDataChanged (self)
```

原因与此文件相关的模型发出[dataChanged](qabstractitemmodel.html#dataChanged)（）信号为这个项目。

你通常只需要调用这个函数，如果你有子类[QTreeWidgetItem](qtreewidgetitem.html)并重新实现[data](qtreewidgetitem.html#data)（ ）和/或[setData](qtreewidgetitem.html#setData)（ ） 。

此功能被引入Qt的4.5 。

**See also** [setData](qtreewidgetitem.html#setData)（ ） 。

```
Qt.ItemFlags QTreeWidgetItem.flags (self)
```

[

返回用于描述产品的标志。这些判断项目是否可以被检查，编辑和选择。

](index.htm)

[为标志的缺省值是](index.htm)[Qt.ItemIsSelectable](qt.html#ItemFlag-enum)|[Qt.ItemIsUserCheckable](qt.html#ItemFlag-enum)|[Qt.ItemIsEnabled](qt.html#ItemFlag-enum)|[Qt.ItemIsDragEnabled](qt.html#ItemFlag-enum)。如果该项目是与父构造，标志将除了含有[Qt.ItemIsDropEnabled](qt.html#ItemFlag-enum)。

**See also** [setFlags](qtreewidgetitem.html#setFlags)（ ） 。

```
QFont QTreeWidgetItem.font (self, int column)
```

[

返回用于呈现在指定的文本的字体_column_。

](qfont.html)

[**See also**](qfont.html) [setFont](qtreewidgetitem.html#setFont)（ ） 。

```
QBrush QTreeWidgetItem.foreground (self, int column)
```

[

返回指定的用于呈现的前景（例如，文本）的刷_column_。

这个函数中引入了Qt 4.2中。

](qbrush.html)

[**See also**](qbrush.html) [setForeground](qtreewidgetitem.html#setForeground)（）和[background](qtreewidgetitem.html#background)（ ） 。

```
QIcon QTreeWidgetItem.icon (self, int column)
```

[

返回显示在所指定的图标_column_。

](qicon.html)

[**See also**](qicon.html) [setIcon](qtreewidgetitem.html#setIcon)（）和[iconSize](qabstractitemview.html#iconSize-prop)。

```
int QTreeWidgetItem.indexOfChild (self, QTreeWidgetItem achild)
```

返回给定索引_child_在儿童的项目的列表。

```
QTreeWidgetItem.insertChild (self, int index, QTreeWidgetItem child)
```

该_child_说法有它的所有权转移给Qt的。

插入_child_在项目_index_在孩子的列表。

如果孩子已经插入别的地方它不会被再次插入。

```
QTreeWidgetItem.insertChildren (self, int index, list-of-QTreeWidgetItem children)
```

该_children_说法有它的所有权转移给Qt的。

插入的给定列表_children_入项目的儿童在列表_index_。

那些已经被插入其他地方的孩子不会被插入。

这个函数是Qt 4.1中引入。

```
bool QTreeWidgetItem.isDisabled (self)
```

返回True如果该项目被禁用，否则返回False 。

此功能被引入Qt的4.3 。

**See also** [setFlags](qtreewidgetitem.html#setFlags)（ ） 。

```
bool QTreeWidgetItem.isExpanded (self)
```

返回True ，如果该项目被扩展，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [setExpanded](qtreewidgetitem.html#setExpanded)（ ） 。

```
bool QTreeWidgetItem.isFirstColumnSpanned (self)
```

返回True如果该项目跨越行中的所有列，否则返回False 。

此功能被引入Qt的4.3 。

**See also** [setFirstColumnSpanned](qtreewidgetitem.html#setFirstColumnSpanned)（ ） 。

```
bool QTreeWidgetItem.isHidden (self)
```

返回True如果该项目被隐藏，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [setHidden](qtreewidgetitem.html#setHidden)（ ） 。

```
bool QTreeWidgetItem.isSelected (self)
```

返回True如果该项目被选中，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [setSelected](qtreewidgetitem.html#setSelected)（ ） 。

```
QTreeWidgetItem QTreeWidgetItem.parent (self)
```

[

返回该项目的父。

](qtreewidgetitem.html)

[**See also**](qtreewidgetitem.html) [child](qtreewidgetitem.html#child)（ ） 。

```
QTreeWidgetItem.read (self, QDataStream in)
```

从流中读取的项目_in_。这只能读取数据到一个单一的项目。

**See also** [write](qtreewidgetitem.html#write)（ ） 。

```
QTreeWidgetItem.removeChild (self, QTreeWidgetItem child)
```

该_child_争论

删除所指示的给定项目_child_。拆下的项目不会被删除。

```
QTreeWidgetItem.setBackground (self, int column, QBrush brush)
```

设置标籤的背景刷子在给定的_column_到指定的_brush_。

这个函数中引入了Qt 4.2中。

**See also** [background](qtreewidgetitem.html#background)（）和[setForeground](qtreewidgetitem.html#setForeground)（ ） 。

```
QTreeWidgetItem.setBackgroundColor (self, int column, QColor color)
```

```
QTreeWidgetItem.setCheckState (self, int column, Qt.CheckState state)
```

设置在给定的项目_column_检查状态是_state_。

**See also** [checkState](qtreewidgetitem.html#checkState)（ ） 。

```
QTreeWidgetItem.setChildIndicatorPolicy (self, ChildIndicatorPolicy policy)
```

设置项指标_policy_。这一政策决定时，树枝展开/折叠指示器。默认值是ShowForChildren 。

**See also** [childIndicatorPolicy](qtreewidgetitem.html#childIndicatorPolicy)（ ） 。

```
QTreeWidgetItem.setData (self, int column, int role, QVariant value)
```

设置项目的价值_column_和_role_为给定的_value_。

该_role_描述了通过指定数据的类型_value_，并且由所定义的[Qt.ItemDataRole](qt.html#ItemDataRole-enum)枚举。

**See also** [data](qtreewidgetitem.html#data)（ ） 。

```
QTreeWidgetItem.setDisabled (self, bool disabled)
```

禁用的项目，如果_disabled_为True，否则使该项目。

此功能被引入Qt的4.3 。

**See also** [isDisabled](qtreewidgetitem.html#isDisabled)（）和[setFlags](qtreewidgetitem.html#setFlags)（ ） 。

```
QTreeWidgetItem.setExpanded (self, bool aexpand)
```

扩展项目，如果_expand_为True，否则崩溃的项目。

**Warning:**该[QTreeWidgetItem](qtreewidgetitem.html)必须被添加到该[QTreeWidget](qtreewidget.html)之前调用这个函数。

这个函数中引入了Qt 4.2中。

**See also** [isExpanded](qtreewidgetitem.html#isExpanded)（ ） 。

```
QTreeWidgetItem.setFirstColumnSpanned (self, bool aspan)
```

设置首节以跨越所有列，如果_span_是真的，否则所有项目的部分都显示。

此功能被引入Qt的4.3 。

**See also** [isFirstColumnSpanned](qtreewidgetitem.html#isFirstColumnSpanned)（ ） 。

```
QTreeWidgetItem.setFlags (self, Qt.ItemFlags aflags)
```

设置标志的项，以给定的_flags_。这些决定了项目是否可以选择或修改。这通常被用于禁用的项目。

**See also** [flags](qtreewidgetitem.html#flags)（ ） 。

```
QTreeWidgetItem.setFont (self, int column, QFont afont)
```

设置用于在给定的显示文本的字体_column_为给定的_font_。

**See also** [font](qtreewidgetitem.html#font)（ ）[setText](qtreewidgetitem.html#setText)（）和[setForeground](qtreewidgetitem.html#setForeground)（ ） 。

```
QTreeWidgetItem.setForeground (self, int column, QBrush brush)
```

设置标籤的前景刷子在给定的_column_到指定的_brush_。

这个函数中引入了Qt 4.2中。

**See also** [foreground](qtreewidgetitem.html#foreground)（）和[setBackground](qtreewidgetitem.html#setBackground)（ ） 。

```
QTreeWidgetItem.setHidden (self, bool ahide)
```

隐藏的项目，如果_hide_为True，否则显示的项目。

这个函数中引入了Qt 4.2中。

**See also** [isHidden](qtreewidgetitem.html#isHidden)（ ） 。

```
QTreeWidgetItem.setIcon (self, int column, QIcon aicon)
```

设置要显示在给定的图标_column_至_icon_。

**See also** [icon](qtreewidgetitem.html#icon)（ ）[setText](qtreewidgetitem.html#setText)（）和[iconSize](qabstractitemview.html#iconSize-prop)。

```
QTreeWidgetItem.setSelected (self, bool aselect)
```

设置项的选择状态，以_select_。

这个函数中引入了Qt 4.2中。

**See also** [isSelected](qtreewidgetitem.html#isSelected)（ ） 。

```
QTreeWidgetItem.setSizeHint (self, int column, QSize size)
```

设置尺寸暗示的树项目在给定的_column_要_size_。如果没有大小的提示设置，基于项目数据的项目代表将计算尺寸暗示。

这个函数是Qt 4.1中引入。

**See also** [sizeHint](qtreewidgetitem.html#sizeHint)（ ） 。

```
QTreeWidgetItem.setStatusTip (self, int column, QString astatusTip)
```

设置状态提示为给定的_column_为给定的_statusTip_。[QTreeWidget](qtreewidget.html)鼠标跟踪需要启用此功能工作。

**See also** [statusTip](qtreewidgetitem.html#statusTip)（ ）[setToolTip](qtreewidgetitem.html#setToolTip)（）和[setWhatsThis](qtreewidgetitem.html#setWhatsThis)（ ） 。

```
QTreeWidgetItem.setText (self, int column, QString atext)
```

设置要显示在给定的文本_column_为给定的_text_。

**See also** [text](qtreewidgetitem.html#text)（ ）[setFont](qtreewidgetitem.html#setFont)（）和[setForeground](qtreewidgetitem.html#setForeground)（ ） 。

```
QTreeWidgetItem.setTextAlignment (self, int column, int alignment)
```

设置在给定的文本对齐方式为标籤_column_到_alignment_规定（见[Qt.AlignmentFlag](qt.html#AlignmentFlag-enum)） 。

**See also** [textAlignment](qtreewidgetitem.html#textAlignment)（ ） 。

```
QTreeWidgetItem.setTextColor (self, int column, QColor color)
```

```
QTreeWidgetItem.setToolTip (self, int column, QString atoolTip)
```

设置工具提示为给定的_column_至_toolTip_。

**See also** [toolTip](qtreewidgetitem.html#toolTip)（ ）[setStatusTip](qtreewidgetitem.html#setStatusTip)（）和[setWhatsThis](qtreewidgetitem.html#setWhatsThis)（ ） 。

```
QTreeWidgetItem.setWhatsThis (self, int column, QString awhatsThis)
```

设置“这是什么？ ”帮助对于给定的_column_至_whatsThis_。

**See also** [whatsThis](qtreewidgetitem.html#whatsThis)（ ）[setStatusTip](qtreewidgetitem.html#setStatusTip)（）和[setToolTip](qtreewidgetitem.html#setToolTip)（ ） 。

```
QSize QTreeWidgetItem.sizeHint (self, int column)
```

[](qsize.html)

[返回树项目的大小设置提示在给定的_column_（见](qsize.html)[QSize](qsize.html)） 。

这个函数是Qt 4.1中引入。

**See also** [setSizeHint](qtreewidgetitem.html#setSizeHint)（ ） 。

```
QTreeWidgetItem.sortChildren (self, int column, Qt.SortOrder order)
```

排序的项目的使用给定的孩子_order_通过在给定的值_column_。

**Note:**这个函数不执行任何操作，如果该项目不与相关的[QTreeWidget](qtreewidget.html)。

这个函数中引入了Qt 4.2中。

```
QString QTreeWidgetItem.statusTip (self, int column)
```

返回状态提示为给定的内容_column_。

**See also** [setStatusTip](qtreewidgetitem.html#setStatusTip)（ ） 。

```
QTreeWidgetItem QTreeWidgetItem.takeChild (self, int index)
```

[

该_QTreeWidgetItem_结果

在删除的项目_index_并返回它，否则返回0 。

```
list-of-QTreeWidgetItem QTreeWidgetItem.takeChildren (self)
```

该_list-of-QTreeWidgetItem_结果

消除儿童的列表，并返回它，否则返回空列表。

这个函数是Qt 4.1中引入。

```
QString QTreeWidgetItem.text (self, int column)
```

在指定返回文本_column_。

](qtreewidgetitem.html)

[**See also**](qtreewidgetitem.html) [setText](qtreewidgetitem.html#setText)（ ） 。

```
int QTreeWidgetItem.textAlignment (self, int column)
```

返回给定文本的对齐方式为标籤_column_（见[Qt.AlignmentFlag](qt.html#AlignmentFlag-enum)） 。

**See also** [setTextAlignment](qtreewidgetitem.html#setTextAlignment)（ ） 。

```
QColor QTreeWidgetItem.textColor (self, int column)
```

[

```
QString QTreeWidgetItem.toolTip (self, int column)
```

返回刀尖对于给定的_column_。

](qcolor.html)

[**See also**](qcolor.html) [setToolTip](qtreewidgetitem.html#setToolTip)（ ） 。

```
QTreeWidget QTreeWidgetItem.treeWidget (self)
```

[

返回树部件包含该项目。

```
int QTreeWidgetItem.type (self)
```

](qtreewidget.html)

[返回传递给类型](qtreewidget.html)[QTreeWidgetItem](qtreewidgetitem.html)构造函数。

```
QString QTreeWidgetItem.whatsThis (self, int column)
```

返回“这是什么？ ”有助于对给定的内容_column_。

**See also** [setWhatsThis](qtreewidgetitem.html#setWhatsThis)（ ） 。

```
QTreeWidgetItem.write (self, QDataStream out)
```

写入流的项目_out_。这只能从一个单一的项目写入数据。

**See also** [read](qtreewidgetitem.html#read)（ ） 。

```
bool QTreeWidgetItem.__ge__ (self, QTreeWidgetItem other)
```

```
bool QTreeWidgetItem.__lt__ (self, QTreeWidgetItem other)
```