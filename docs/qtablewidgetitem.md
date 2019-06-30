# QTableWidgetItem Class Reference

## [[QtGui](index.htm) module]

该QTableWidgetItem类提供的项目与使用[QTableWidget](qtablewidget.html)类。[More...](#details)

### Types

*   `enum ItemType { Type, UserType }`

### Methods

*   `__init__ (self, int type = QTableWidgetItem.Type)`
*   `__init__ (self, QString text, int type = QTableWidgetItem.Type)`
*   `__init__ (self, QIcon icon, QString text, int type = QTableWidgetItem.Type)`
*   `__init__ (self, QTableWidgetItem other)`
*   `QBrush background (self)`
*   `QColor backgroundColor (self)`
*   `Qt.CheckState checkState (self)`
*   `QTableWidgetItem clone (self)`
*   `int column (self)`
*   `QVariant data (self, int role)`
*   `Qt.ItemFlags flags (self)`
*   `QFont font (self)`
*   `QBrush foreground (self)`
*   `QIcon icon (self)`
*   `bool isSelected (self)`
*   `read (self, QDataStream in)`
*   `int row (self)`
*   `setBackground (self, QBrush brush)`
*   `setBackgroundColor (self, QColor color)`
*   `setCheckState (self, Qt.CheckState state)`
*   `setData (self, int role, QVariant value)`
*   `setFlags (self, Qt.ItemFlags aflags)`
*   `setFont (self, QFont afont)`
*   `setForeground (self, QBrush brush)`
*   `setIcon (self, QIcon aicon)`
*   `setSelected (self, bool aselect)`
*   `setSizeHint (self, QSize size)`
*   `setStatusTip (self, QString astatusTip)`
*   `setText (self, QString atext)`
*   `setTextAlignment (self, int alignment)`
*   `setTextColor (self, QColor color)`
*   `setToolTip (self, QString atoolTip)`
*   `setWhatsThis (self, QString awhatsThis)`
*   `QSize sizeHint (self)`
*   `QString statusTip (self)`
*   `QTableWidget tableWidget (self)`
*   `QString text (self)`
*   `int textAlignment (self)`
*   `QColor textColor (self)`
*   `QString toolTip (self)`
*   `int type (self)`
*   `QString whatsThis (self)`
*   `write (self, QDataStream out)`

### Special Methods

*   `bool __ge__ (self, QTableWidgetItem other)`
*   `bool __lt__ (self, QTableWidgetItem other)`

* * *

## Detailed Description

该QTableWidgetItem类提供的项目与使用[QTableWidget](qtablewidget.html)类。

表项是用来存放部分信息的表的小部件。项目通常包含文字，图标或复选框

该QTableWidgetItem类是取代了一个方便的类`QTableItem`类的Qt 3 。它提供了一种用于产品的使用[QTableWidget](qtablewidget.html)类。

顶级项目，没有父母，然后在由一对行和列数的指定位置插入的构造：

```
     QTableWidgetItem *newItem = new QTableWidgetItem(tr("%1").arg(
         pow(row, column+1)));
     tableWidget->setItem(row, column, newItem);

```

每个项目都可以有自己的背景刷子设置与[setBackground](qtablewidgetitem.html#setBackground)（）函数。当前的背景刷可以找到[background](qtablewidgetitem.html#background)（ ） 。每个项目的文本标籤可以有自己的字体和笔刷渲染。这些都与指定[setFont](qtablewidgetitem.html#setFont)（）和[setForeground](qtablewidgetitem.html#setForeground)（）函数，并读取与[font](qtablewidgetitem.html#font)（）和[foreground](qtablewidgetitem.html#foreground)（ ） 。

默认情况下，项目的启用，可编辑，可选择辨认的，可同时用作拖动的来源又是释放的操作和放置目标。每个项目的标志可以通过调用改变[setFlags](qtablewidgetitem.html#setFlags)（ ）用适当的值（见[Qt.ItemFlags](qt.html#ItemFlag-enum)） 。辨认的项目可以选中和未选中的[setCheckState](qtablewidgetitem.html#setCheckState)（）函数。相应的[checkState](qtablewidgetitem.html#checkState)（ ）函数表示该项目目前是否已选中。

### Subclassing

当子类化QTableWidgetItem提供自定义项目，可以为他们定义新类型，使他们能够从标准的项目区别开来。该构造函数需要此功能的子类需要调用基类的构造函数有一个新的类型值等于或大于[UserType](qtablewidgetitem.html#ItemType-enum)。

* * *

## Type Documentation

```
QTableWidgetItem.ItemType
```

这个枚举变量描述了用于描述表部件项目的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QTableWidgetItem.Type` | `0` | 默认类型为表部件项目。 |
| `QTableWidgetItem.UserType` | `1000` | 对于自定义类型的最小值。以下用户等级和积分值被Qt保留。 |

您可以定义新的用户类型[QTableWidgetItem](qtablewidgetitem.html)子类以确保自定义项目被特殊处理。

**See also** [type](qtablewidgetitem.html#type)（ ） 。

* * *

## Method Documentation

```
QTableWidgetItem.__init__ (self, int type = QTableWidgetItem.Type)
```

构造一个指定的表项_type_不属于任何表。

**See also** [type](qtablewidgetitem.html#type)（ ） 。

```
QTableWidgetItem.__init__ (self, QString text, int type = QTableWidgetItem.Type)
```

构造具有给定一个表项_text_。

**See also** [type](qtablewidgetitem.html#type)（ ） 。

```
QTableWidgetItem.__init__ (self, QIcon icon, QString text, int type = QTableWidgetItem.Type)
```

构造具有给定一个表项_icon_和_text_。

**See also** [type](qtablewidgetitem.html#type)（ ） 。

```
QTableWidgetItem.__init__ (self, QTableWidgetItem other)
```

构造的副本_other_。需要注意的是[type](qtablewidgetitem.html#type)（）和[tableWidget](qtablewidgetitem.html#tableWidget)（ ）不会被复制。

重新实现时，此功能非常有用[clone](qtablewidgetitem.html#clone)（ ） 。

这个函数是Qt 4.1中引入。

**See also** [data](qtablewidgetitem.html#data)（）和[flags](qtablewidgetitem.html#flags)（ ） 。

```
QBrush QTableWidgetItem.background (self)
```

[

返回用于呈现项的背景的画笔。

这个函数中引入了Qt 4.2中。

](qbrush.html)

[**See also**](qbrush.html) [setBackground](qtablewidgetitem.html#setBackground)（）和[foreground](qtablewidgetitem.html#foreground)（ ） 。

```
QColor QTableWidgetItem.backgroundColor (self)
```

[](qcolor.html)

```
Qt.CheckState QTableWidgetItem.checkState (self)
```

[

返回表项的选中状态。

](qt.html#CheckState-enum)

[**See also**](qt.html#CheckState-enum) [setCheckState](qtablewidgetitem.html#setCheckState)（）和[flags](qtablewidgetitem.html#flags)（ ） 。

```
QTableWidgetItem QTableWidgetItem.clone (self)
```

[

创建项目的副本。

```
int QTableWidgetItem.column (self)
```

返回表中的该项目的列。如果项目是不是在一个表中，该函数将返回-1 。

这个函数中引入了Qt 4.2中。

](qtablewidgetitem.html)

[**See also**](qtablewidgetitem.html) [row](qtablewidgetitem.html#row)（ ） 。

```
QVariant QTableWidgetItem.data (self, int role)
```

返回的项目的数据为给定的_role_。

**See also** [setData](qtablewidgetitem.html#setData)（ ） 。

```
Qt.ItemFlags QTableWidgetItem.flags (self)
```

[

返回用于描述产品的标志。这些判断项目是否可以被检查，编辑和选择。

](index.htm)

[**See also**](index.htm) [setFlags](qtablewidgetitem.html#setFlags)（ ） 。

```
QFont QTableWidgetItem.font (self)
```

[

返回用于呈现项的文本的字体。

](qfont.html)

[**See also**](qfont.html) [setFont](qtablewidgetitem.html#setFont)（ ） 。

```
QBrush QTableWidgetItem.foreground (self)
```

[

返回用于呈现项目的前景（如文字）的笔刷。

这个函数中引入了Qt 4.2中。

](qbrush.html)

[**See also**](qbrush.html) [setForeground](qtablewidgetitem.html#setForeground)（）和[background](qtablewidgetitem.html#background)（ ） 。

```
QIcon QTableWidgetItem.icon (self)
```

[

返回该项目的图标。

](qicon.html)

[**See also**](qicon.html) [setIcon](qtablewidgetitem.html#setIcon)（）和[iconSize](qabstractitemview.html#iconSize-prop)。

```
bool QTableWidgetItem.isSelected (self)
```

返回True如果该项目被选中，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [setSelected](qtablewidgetitem.html#setSelected)（ ） 。

```
QTableWidgetItem.read (self, QDataStream in)
```

从流中读取的项目_in_。

**See also** [write](qtablewidgetitem.html#write)（ ） 。

```
int QTableWidgetItem.row (self)
```

返回表中的项的行。如果项目是不是在一个表中，该函数将返回-1 。

这个函数中引入了Qt 4.2中。

**See also** [column](qtablewidgetitem.html#column)（ ） 。

```
QTableWidgetItem.setBackground (self, QBrush brush)
```

设置项的背景刷到指定的_brush_。

这个函数中引入了Qt 4.2中。

**See also** [background](qtablewidgetitem.html#background)（）和[setForeground](qtablewidgetitem.html#setForeground)（ ） 。

```
QTableWidgetItem.setBackgroundColor (self, QColor color)
```

```
QTableWidgetItem.setCheckState (self, Qt.CheckState state)
```

设置表项的检查状态是_state_。

**See also** [checkState](qtablewidgetitem.html#checkState)（ ） 。

```
QTableWidgetItem.setData (self, int role, QVariant value)
```

设置项的数据为给定的_role_到指定的_value_。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)和[data](qtablewidgetitem.html#data)（ ） 。

```
QTableWidgetItem.setFlags (self, Qt.ItemFlags aflags)
```

设置标志的项，以给定的_flags_。这些决定了项目是否可以选择或修改。

**See also** [flags](qtablewidgetitem.html#flags)（ ） 。

```
QTableWidgetItem.setFont (self, QFont afont)
```

设置用于显示项目的文字给定的字体_font_。

**See also** [font](qtablewidgetitem.html#font)（ ）[setText](qtablewidgetitem.html#setText)（）和[setForeground](qtablewidgetitem.html#setForeground)（ ） 。

```
QTableWidgetItem.setForeground (self, QBrush brush)
```

设置项的前景色刷到指定的_brush_。

这个函数中引入了Qt 4.2中。

**See also** [foreground](qtablewidgetitem.html#foreground)（）和[setBackground](qtablewidgetitem.html#setBackground)（ ） 。

```
QTableWidgetItem.setIcon (self, QIcon aicon)
```

设置项的图标_icon_规定。

**See also** [icon](qtablewidgetitem.html#icon)（ ）[setText](qtablewidgetitem.html#setText)（）和[iconSize](qabstractitemview.html#iconSize-prop)。

```
QTableWidgetItem.setSelected (self, bool aselect)
```

设置项的选择状态，以_select_。

这个函数中引入了Qt 4.2中。

**See also** [isSelected](qtablewidgetitem.html#isSelected)（ ） 。

```
QTableWidgetItem.setSizeHint (self, QSize size)
```

设置尺寸暗示的表项是_size_。如果没有大小的提示设置，基于项目数据的项目代表将计算尺寸暗示。

这个函数是Qt 4.1中引入。

**See also** [sizeHint](qtablewidgetitem.html#sizeHint)（ ） 。

```
QTableWidgetItem.setStatusTip (self, QString astatusTip)
```

设置状态提示为表项所指定的文本_statusTip_。[QTableWidget](qtablewidget.html)鼠标跟踪需要启用此功能工作。

**See also** [statusTip](qtablewidgetitem.html#statusTip)（ ）[setToolTip](qtablewidgetitem.html#setToolTip)（）和[setWhatsThis](qtablewidgetitem.html#setWhatsThis)（ ） 。

```
QTableWidgetItem.setText (self, QString atext)
```

设置项的文字到_text_规定。

**See also** [text](qtablewidgetitem.html#text)（ ）[setFont](qtablewidgetitem.html#setFont)（）和[setForeground](qtablewidgetitem.html#setForeground)（ ） 。

```
QTableWidgetItem.setTextAlignment (self, int alignment)
```

设置文本对齐方式为项目的文字到_alignment_规定。

**See also** [textAlignment](qtablewidgetitem.html#textAlignment)（）和[Qt.Alignment](qt.html#AlignmentFlag-enum)。

```
QTableWidgetItem.setTextColor (self, QColor color)
```

```
QTableWidgetItem.setToolTip (self, QString atoolTip)
```

设置项的提示通过指定的字符串_toolTip_。

**See also** [toolTip](qtablewidgetitem.html#toolTip)（ ）[setStatusTip](qtablewidgetitem.html#setStatusTip)（）和[setWhatsThis](qtablewidgetitem.html#setWhatsThis)（ ） 。

```
QTableWidgetItem.setWhatsThis (self, QString awhatsThis)
```

设置项的“这是什么？ ”有助于通过指定的字符串_whatsThis_。

**See also** [whatsThis](qtablewidgetitem.html#whatsThis)（ ）[setStatusTip](qtablewidgetitem.html#setStatusTip)（）和[setToolTip](qtablewidgetitem.html#setToolTip)（ ） 。

```
QSize QTableWidgetItem.sizeHint (self)
```

[

返回该表项的大小提示集。

这个函数是Qt 4.1中引入。

](qsize.html)

[**See also**](qsize.html) [setSizeHint](qtablewidgetitem.html#setSizeHint)（ ） 。

```
QString QTableWidgetItem.statusTip (self)
```

返回项目的状态提示。

**See also** [setStatusTip](qtablewidgetitem.html#setStatusTip)（ ） 。

```
QTableWidget QTableWidgetItem.tableWidget (self)
```

[

返回包含项目的表格部件。

```
QString QTableWidgetItem.text (self)
```

返回项的文本。

](qtablewidget.html)

[**See also**](qtablewidget.html) [setText](qtablewidgetitem.html#setText)（ ） 。

```
int QTableWidgetItem.textAlignment (self)
```

返回文本对齐方式项的文本。

**See also** [setTextAlignment](qtablewidgetitem.html#setTextAlignment)（）和[Qt.Alignment](qt.html#AlignmentFlag-enum)。

```
QColor QTableWidgetItem.textColor (self)
```

[

```
QString QTableWidgetItem.toolTip (self)
```

返回该项目的工具提示。

](qcolor.html)

[**See also**](qcolor.html) [setToolTip](qtablewidgetitem.html#setToolTip)（ ） 。

```
int QTableWidgetItem.type (self)
```

返回传递给类型[QTableWidgetItem](qtablewidgetitem.html)构造函数。

```
QString QTableWidgetItem.whatsThis (self)
```

返回该项目的“这是什么？ ”帮助。

**See also** [setWhatsThis](qtablewidgetitem.html#setWhatsThis)（ ） 。

```
QTableWidgetItem.write (self, QDataStream out)
```

写入流的项目_out_。

**See also** [read](qtablewidgetitem.html#read)（ ） 。

```
bool QTableWidgetItem.__ge__ (self, QTableWidgetItem other)
```

```
bool QTableWidgetItem.__lt__ (self, QTableWidgetItem other)
```