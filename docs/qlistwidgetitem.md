# QListWidgetItem Class Reference

## [[QtGui](index.htm) module]

该QListWidgetItem类提供的项目与使用[QListWidget](qlistwidget.html)项目视图类。[More...](#details)

### Types

*   `enum ItemType { Type, UserType }`

### Methods

*   `__init__ (self, QListWidget parent = None, int type = QListWidgetItem.Type)`
*   `__init__ (self, QString text, QListWidget parent = None, int type = QListWidgetItem.Type)`
*   `__init__ (self, QIcon icon, QString text, QListWidget parent = None, int type = QListWidgetItem.Type)`
*   `__init__ (self, QListWidgetItem other)`
*   `QBrush background (self)`
*   `QColor backgroundColor (self)`
*   `Qt.CheckState checkState (self)`
*   `QListWidgetItem clone (self)`
*   `QVariant data (self, int role)`
*   `Qt.ItemFlags flags (self)`
*   `QFont font (self)`
*   `QBrush foreground (self)`
*   `QIcon icon (self)`
*   `bool isHidden (self)`
*   `bool isSelected (self)`
*   `QListWidget listWidget (self)`
*   `read (self, QDataStream in)`
*   `setBackground (self, QBrush brush)`
*   `setBackgroundColor (self, QColor color)`
*   `setCheckState (self, Qt.CheckState state)`
*   `setData (self, int role, QVariant value)`
*   `setFlags (self, Qt.ItemFlags aflags)`
*   `setFont (self, QFont afont)`
*   `setForeground (self, QBrush brush)`
*   `setHidden (self, bool ahide)`
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
*   `QString text (self)`
*   `int textAlignment (self)`
*   `QColor textColor (self)`
*   `QString toolTip (self)`
*   `int type (self)`
*   `QString whatsThis (self)`
*   `write (self, QDataStream out)`

### Special Methods

*   `bool __ge__ (self, QListWidgetItem other)`
*   `bool __lt__ (self, QListWidgetItem other)`

* * *

## Detailed Description

该QListWidgetItem类提供的项目与使用[QListWidget](qlistwidget.html)项目视图类。

一个QListWidgetItem代表一个单一的项目[QListWidget](qlistwidget.html)。每个项目可容纳几条信息，并会适当地显示出来。

项目视图便利类使用一个典型的项目为基础的界面，而不是一个纯粹的模型/视图的方法。对于一个更加灵活的列表视图控件，可以考虑使用[QListView](qlistview.html)类与标准模型。

列表项可以被自动插入到一个列表中，当它们被建造，通过指定列表控件：

```
     new QListWidgetItem(tr("Hazel"), listWidget);

```

或者，列表项，也可以没有父窗口部件创建的，并在以后使用插入到列表[QListWidget.insertItem](qlistwidget.html#insertItem)（ ） 。

列表项通常用于显示[text](qlistwidgetitem.html#text)（）和一个[icon](qlistwidgetitem.html#icon)（ ） 。这些设置与[setText](qlistwidgetitem.html#setText)（）和[setIcon](qlistwidgetitem.html#setIcon)（）函数。文本的外观可与定制[setFont](qlistwidgetitem.html#setFont)（ ）[setForeground](qlistwidgetitem.html#setForeground)（）和[setBackground](qlistwidgetitem.html#setBackground)（ ） 。在列表项的文本可使用对齐[setTextAlignment](qlistwidgetitem.html#setTextAlignment)（）函数。工具提示，状态提示和“这是什么？ ”说明可以被添加到列表中的内容[setToolTip](qlistwidgetitem.html#setToolTip)（ ）[setStatusTip](qlistwidgetitem.html#setStatusTip)（）和[setWhatsThis](qlistwidgetitem.html#setWhatsThis)（ ） 。

默认情况下，项目的启用，可选择，可复，可拖放操作的来源。

每个项目的标志可以通过调用改变[setFlags](qlistwidgetitem.html#setFlags)（ ）用适当的值（见[Qt.ItemFlags](qt.html#ItemFlag-enum)） 。辨认的项目可以被选中，未选中并与部分检查[setCheckState](qlistwidgetitem.html#setCheckState)（）函数。相应的[checkState](qlistwidgetitem.html#checkState)（ ）函数表示该项目的当前选中状态。

该[isHidden](qlistwidgetitem.html#isHidden)（）函数可以被用来确定该项目是否被隐藏。若要隐藏某个项目，用[setHidden](qlistwidgetitem.html#setHidden)（ ） 。

### Subclassing

当子类QListWidgetItem提供自定义项目，可以为他们使他们能够从标准的项目区分开来定义新的类型。对于需要此功能的子类，请确保调用基类的构造函数有一个新的类型值等于或大于[UserType](qlistwidgetitem.html#ItemType-enum)，内_your_构造函数。

* * *

## Type Documentation

```
QListWidgetItem.ItemType
```

该枚举描述了用于描述列表插件项的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QListWidgetItem.Type` | `0` | 默认类型为列表控件的项目。 |
| `QListWidgetItem.UserType` | `1000` | 对于自定义类型的最小值。以下用户等级和积分值被Qt保留。 |

您可以定义新的用户类型[QListWidgetItem](qlistwidgetitem.html)子类以确保自定义项目被特殊处理。

**See also** [type](qlistwidgetitem.html#type)（ ） 。

* * *

## Method Documentation

```
QListWidgetItem.__init__ (self, QListWidget parent = None, int type = QListWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造指定一个空的列表控件项_type_用给定的_parent_。如果_parent_没有被指定，该项目将需要被插入到一个列表部件与[QListWidget.insertItem](qlistwidget.html#insertItem)（ ） 。

这个构造函数插入项目到传递给构造函数的父模型。如果模型被排序，然后插入物的行为是不确定的，因为该模型将调用`'&lt;'`运营商的方法上，在这一点上，尚未建成的项目。为了避免不确定的行为，我们建议不要指定父和使用[QListWidget.insertItem](qlistwidget.html#insertItem)（ ）来代替。

**See also** [type](qlistwidgetitem.html#type)（ ） 。

```
QListWidgetItem.__init__ (self, QString text, QListWidget parent = None, int type = QListWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造指定一个空的列表控件项_type_用给定的_text_和_parent_。如果未指定父，则该项目将需要被插入到一个列表部件与[QListWidget.insertItem](qlistwidget.html#insertItem)（ ） 。

这个构造函数插入项目到传递给构造函数的父模型。如果模型被排序，然后插入物的行为是不确定的，因为该模型将调用`'&lt;'`运营商的方法上，在这一点上，尚未建成的项目。为了避免不确定的行为，我们建议不要指定父和使用[QListWidget.insertItem](qlistwidget.html#insertItem)（ ）来代替。

**See also** [type](qlistwidgetitem.html#type)（ ） 。

```
QListWidgetItem.__init__ (self, QIcon icon, QString text, QListWidget parent = None, int type = QListWidgetItem.Type)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造指定一个空的列表控件项_type_用给定的_icon_，_text_和_parent_。如果未指定父，则该项目将需要被插入到一个列表部件与[QListWidget.insertItem](qlistwidget.html#insertItem)（ ） 。

这个构造函数插入项目到传递给构造函数的父模型。如果模型被排序，然后插入物的行为是不确定的，因为该模型将调用`'&lt;'`运营商的方法上，在这一点上，尚未建成的项目。为了避免不确定的行为，我们建议不要指定父和使用[QListWidget.insertItem](qlistwidget.html#insertItem)（ ）来代替。

**See also** [type](qlistwidgetitem.html#type)（ ） 。

```
QListWidgetItem.__init__ (self, QListWidgetItem other)
```

构造的副本_other_。需要注意的是[type](qlistwidgetitem.html#type)（）和[listWidget](qlistwidgetitem.html#listWidget)（ ）不会被复制。

重新实现时，此功能非常有用[clone](qlistwidgetitem.html#clone)（ ） 。

这个函数是Qt 4.1中引入。

**See also** [data](qlistwidgetitem.html#data)（）和[flags](qlistwidgetitem.html#flags)（ ） 。

```
QBrush QListWidgetItem.background (self)
```

[

返回用于显示列表项的背景的画笔。

这个函数中引入了Qt 4.2中。

](qbrush.html)

[**See also**](qbrush.html) [setBackground](qlistwidgetitem.html#setBackground)（）和[foreground](qlistwidgetitem.html#foreground)（ ） 。

```
QColor QListWidgetItem.backgroundColor (self)
```

[](qcolor.html)

```
Qt.CheckState QListWidgetItem.checkState (self)
```

[](qt.html#CheckState-enum)

[返回列表项的选中状态（见](qt.html#CheckState-enum)[Qt.CheckState](qt.html#CheckState-enum)） 。

**See also** [setCheckState](qlistwidgetitem.html#setCheckState)（）和[flags](qlistwidgetitem.html#flags)（ ） 。

```
QListWidgetItem QListWidgetItem.clone (self)
```

[

创建该项目的精确副本。

```
QVariant QListWidgetItem.data (self, int role)
```

返回的项目的数据对于一个给定_role_。如果你需要额外的角色或某些角色的特殊行为重新实现这个函数。

](qlistwidgetitem.html)

[**See also**](qlistwidgetitem.html) [Qt.ItemDataRole](qt.html#ItemDataRole-enum)和[setData](qlistwidgetitem.html#setData)（ ） 。

```
Qt.ItemFlags QListWidgetItem.flags (self)
```

[](index.htm)

[返回该项目的标志为这个项目（见](index.htm)[Qt.ItemFlags](qt.html#ItemFlag-enum)） 。

**See also** [setFlags](qlistwidgetitem.html#setFlags)（ ） 。

```
QFont QListWidgetItem.font (self)
```

[

返回用于显示该列表项的文本的字体。

](qfont.html)

[**See also**](qfont.html) [setFont](qlistwidgetitem.html#setFont)（ ） 。

```
QBrush QListWidgetItem.foreground (self)
```

[

返回用于显示列表项的前景（如文字）的笔刷。

这个函数中引入了Qt 4.2中。

](qbrush.html)

[**See also**](qbrush.html) [setForeground](qlistwidgetitem.html#setForeground)（）和[background](qlistwidgetitem.html#background)（ ） 。

```
QIcon QListWidgetItem.icon (self)
```

[

返回列表项的图标。

](qicon.html)

[**See also**](qicon.html) [setIcon](qlistwidgetitem.html#setIcon)（）和[iconSize](qabstractitemview.html#iconSize-prop)。

```
bool QListWidgetItem.isHidden (self)
```

返回True如果该项目是隐藏，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [setHidden](qlistwidgetitem.html#setHidden)（ ） 。

```
bool QListWidgetItem.isSelected (self)
```

返回True如果该项目被选中，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [setSelected](qlistwidgetitem.html#setSelected)（ ） 。

```
QListWidget QListWidgetItem.listWidget (self)
```

[

返回包含项目的列表控件。

```
QListWidgetItem.read (self, QDataStream in)
```

从流中读取的项目_in_。

](qlistwidget.html)

[**See also**](qlistwidget.html) [write](qlistwidgetitem.html#write)（ ） 。

```
QListWidgetItem.setBackground (self, QBrush brush)
```

设置列表项的背景刷到给定_brush_。

这个函数中引入了Qt 4.2中。

**See also** [background](qlistwidgetitem.html#background)（）和[setForeground](qlistwidgetitem.html#setForeground)（ ） 。

```
QListWidgetItem.setBackgroundColor (self, QColor color)
```

```
QListWidgetItem.setCheckState (self, Qt.CheckState state)
```

设置列表项的复选状态_state_。

**See also** [checkState](qlistwidgetitem.html#checkState)（ ） 。

```
QListWidgetItem.setData (self, int role, QVariant value)
```

设置数据对于一个给定_role_为给定的_value_。如果你需要额外的角色或某些角色的特殊行为重新实现这个函数。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)和[data](qlistwidgetitem.html#data)（ ） 。

```
QListWidgetItem.setFlags (self, Qt.ItemFlags aflags)
```

设置项标志为列表项_flags_。

**See also** [flags](qlistwidgetitem.html#flags)（）和[Qt.ItemFlags](qt.html#ItemFlag-enum)。

```
QListWidgetItem.setFont (self, QFont afont)
```

画设定的项目给定的时使用的字体_font_。

**See also** [font](qlistwidgetitem.html#font)（ ） 。

```
QListWidgetItem.setForeground (self, QBrush brush)
```

设置列表项的前景画笔给定的_brush_。

这个函数中引入了Qt 4.2中。

**See also** [foreground](qlistwidgetitem.html#foreground)（）和[setBackground](qlistwidgetitem.html#setBackground)（ ） 。

```
QListWidgetItem.setHidden (self, bool ahide)
```

隐藏的项目，如果_hide_为True，否则显示的项目。

这个函数中引入了Qt 4.2中。

**See also** [isHidden](qlistwidgetitem.html#isHidden)（ ） 。

```
QListWidgetItem.setIcon (self, QIcon aicon)
```

设置为列表项的图标给定的_icon_。

**See also** [icon](qlistwidgetitem.html#icon)（ ）[text](qlistwidgetitem.html#text)（）和[iconSize](qabstractitemview.html#iconSize-prop)。

```
QListWidgetItem.setSelected (self, bool aselect)
```

设置项的选择状态，以_select_。

这个函数中引入了Qt 4.2中。

**See also** [isSelected](qlistwidgetitem.html#isSelected)（ ） 。

```
QListWidgetItem.setSizeHint (self, QSize size)
```

设置尺寸暗示的列表项是_size_。如果没有大小的提示设置，基于项目数据的项目代表将计算尺寸暗示。

这个函数是Qt 4.1中引入。

**See also** [sizeHint](qlistwidgetitem.html#sizeHint)（ ） 。

```
QListWidgetItem.setStatusTip (self, QString astatusTip)
```

设置状态提示为列表项由指定的文本_statusTip_。[QListWidget](qlistwidget.html)mouseTracking需要启用此功能工作。

**See also** [statusTip](qlistwidgetitem.html#statusTip)（ ）[setToolTip](qlistwidgetitem.html#setToolTip)（ ）[setWhatsThis](qlistwidgetitem.html#setWhatsThis)（）和[QWidget.setMouseTracking](qwidget.html#mouseTracking-prop)（ ） 。

```
QListWidgetItem.setText (self, QString atext)
```

设置文本列表控件项的给定_text_。

**See also** [text](qlistwidgetitem.html#text)（ ） 。

```
QListWidgetItem.setTextAlignment (self, int alignment)
```

设置列表项的文本对齐方式_alignment_。

**See also** [textAlignment](qlistwidgetitem.html#textAlignment)（）和[Qt.AlignmentFlag](qt.html#AlignmentFlag-enum)。

```
QListWidgetItem.setTextColor (self, QColor color)
```

```
QListWidgetItem.setToolTip (self, QString atoolTip)
```

设置工具提示的列表项由指定的文本_toolTip_。

**See also** [toolTip](qlistwidgetitem.html#toolTip)（ ）[setStatusTip](qlistwidgetitem.html#setStatusTip)（）和[setWhatsThis](qlistwidgetitem.html#setWhatsThis)（ ） 。

```
QListWidgetItem.setWhatsThis (self, QString awhatsThis)
```

设置“这是什么？ ”帮助列表项由指定的文本_whatsThis_。

**See also** [whatsThis](qlistwidgetitem.html#whatsThis)（ ）[setStatusTip](qlistwidgetitem.html#setStatusTip)（）和[setToolTip](qlistwidgetitem.html#setToolTip)（ ） 。

```
QSize QListWidgetItem.sizeHint (self)
```

[

返回列表项的大小提示集。

这个函数是Qt 4.1中引入。

](qsize.html)

[**See also**](qsize.html) [setSizeHint](qlistwidgetitem.html#setSizeHint)（ ） 。

```
QString QListWidgetItem.statusTip (self)
```

返回列表项的状态提示。

**See also** [setStatusTip](qlistwidgetitem.html#setStatusTip)（ ） 。

```
QString QListWidgetItem.text (self)
```

返回列表项的文本。

**See also** [setText](qlistwidgetitem.html#setText)（ ） 。

```
int QListWidgetItem.textAlignment (self)
```

返回文本对齐方式为列表项。

**See also** [setTextAlignment](qlistwidgetitem.html#setTextAlignment)（）和[Qt.AlignmentFlag](qt.html#AlignmentFlag-enum)。

```
QColor QListWidgetItem.textColor (self)
```

[

```
QString QListWidgetItem.toolTip (self)
```

返回列表项的工具提示。

](qcolor.html)

[**See also**](qcolor.html) [setToolTip](qlistwidgetitem.html#setToolTip)（ ）[statusTip](qlistwidgetitem.html#statusTip)（）和[whatsThis](qlistwidgetitem.html#whatsThis)（ ） 。

```
int QListWidgetItem.type (self)
```

返回传递给类型[QListWidgetItem](qlistwidgetitem.html)构造函数。

```
QString QListWidgetItem.whatsThis (self)
```

返回列表项的“这是什么？ ”帮助文本。

**See also** [setWhatsThis](qlistwidgetitem.html#setWhatsThis)（ ）[statusTip](qlistwidgetitem.html#statusTip)（）和[toolTip](qlistwidgetitem.html#toolTip)（ ） 。

```
QListWidgetItem.write (self, QDataStream out)
```

写入流的项目_out_。

**See also** [read](qlistwidgetitem.html#read)（ ） 。

```
bool QListWidgetItem.__ge__ (self, QListWidgetItem other)
```

```
bool QListWidgetItem.__lt__ (self, QListWidgetItem other)
```