# QToolBox Class Reference

## [[QtGui](index.htm) module]

该QToolBox类提供了选项卡式窗口小部件项目的列。[More...](#details)

继承[QFrame](qframe.html)。

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `int addItem (self, QWidget item, QString text)`
*   `int addItem (self, QWidget item, QIcon iconSet, QString text)`
*   `changeEvent (self, QEvent)`
*   `int count (self)`
*   `int currentIndex (self)`
*   `QWidget currentWidget (self)`
*   `bool event (self, QEvent e)`
*   `int indexOf (self, QWidget widget)`
*   `int insertItem (self, int index, QWidget item, QString text)`
*   `int insertItem (self, int index, QWidget widget, QIcon icon, QString text)`
*   `bool isItemEnabled (self, int index)`
*   `QIcon itemIcon (self, int index)`
*   `itemInserted (self, int index)`
*   `itemRemoved (self, int index)`
*   `QString itemText (self, int index)`
*   `QString itemToolTip (self, int index)`
*   `removeItem (self, int index)`
*   `setCurrentIndex (self, int index)`
*   `setCurrentWidget (self, QWidget widget)`
*   `setItemEnabled (self, int index, bool enabled)`
*   `setItemIcon (self, int index, QIcon icon)`
*   `setItemText (self, int index, QString text)`
*   `setItemToolTip (self, int index, QString toolTip)`
*   `showEvent (self, QShowEvent e)`
*   `QWidget widget (self, int index)`

### Special Methods

*   `__len__ (self)`

### Qt Signals

*   `void currentChanged (int)`

* * *

## Detailed Description

该QToolBox类提供了选项卡式窗口小部件项目的列。

工具箱是显示卡另一个上方的一列，与当前选项卡下面显示当前项目的Widget。每个标籤具有标籤的列中的索引位置。一个标籤的项目是[QWidget](qwidget.html)。

每个项目都有一个[itemText](qtoolbox.html#itemText)（） ，可选[itemIcon](qtoolbox.html#itemIcon)（） ，可选[itemToolTip](qtoolbox.html#itemToolTip)（） ，和一个[widget](qtoolbox.html#widget)（ ） 。该项目的属性可以与被改变[setItemText](qtoolbox.html#setItemText)（ ）[setItemIcon](qtoolbox.html#setItemIcon)（）和[setItemToolTip](qtoolbox.html#setItemToolTip)（ ） 。每个项目可以启用或禁用单独[setItemEnabled](qtoolbox.html#setItemEnabled)（ ） 。

项目，采用加[addItem](qtoolbox.html#addItem)（），或者使用插入在特定位置[insertItem](qtoolbox.html#insertItem)（ ） 。的总项数由下式给出[count](qtoolbox.html#count-prop)（ ） 。项目可以用delete删除，或从工具箱中删除[removeItem](qtoolbox.html#removeItem)（ ） 。结合[removeItem](qtoolbox.html#removeItem)（）和[insertItem](qtoolbox.html#insertItem)（）允许您将项目移到不同的位置。

目前项目widget的指数是由返回[currentIndex](qtoolbox.html#currentIndex-prop)（ ），并设置用[setCurrentIndex](qtoolbox.html#currentIndex-prop)（ ） 。特定项目的索引可以使用被发现[indexOf](qtoolbox.html#indexOf)（ ） ，和一个给定的索引处的项目被退回[item](index.htm#item)（ ） 。

该[currentChanged](qtoolbox.html#currentChanged)在当前项目改变（ ）信号被发射。

* * *

## Method Documentation

```
QToolBox.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的工具箱给定的_parent_和标志，_f_。

```
int QToolBox.addItem (self, QWidget item, QString text)
```

该_item_说法有它的所有权转移给Qt的。

添加_widget_在在工具箱的底部有一个新的选项卡。新标籤的文本设置为_text_和_iconSet_被显示到的左_text_。返回新的选项卡的索引。

```
int QToolBox.addItem (self, QWidget item, QIcon iconSet, QString text)
```

该_item_说法有它的所有权转移给Qt的。

这是一个重载函数。

添加小工具_w_在在工具箱的底部有一个新的选项卡。新标籤的文本设置为_text_。返回新的选项卡的索引。

```
QToolBox.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
int QToolBox.count (self)
```

```
int QToolBox.currentIndex (self)
```

```
QWidget QToolBox.currentWidget (self)
```

[

返回一个指针，当前窗口小部件，或者0，如果不存在这样的资料。

](qwidget.html)

[**See also**](qwidget.html) [currentIndex](qtoolbox.html#currentIndex-prop)（）和[setCurrentWidget](qtoolbox.html#setCurrentWidget)（ ） 。

```
bool QToolBox.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QToolBox.indexOf (self, QWidget widget)
```

返回的索引_widget_，或-1，如果该项目不存在。

```
int QToolBox.insertItem (self, int index, QWidget item, QString text)
```

该_item_说法有它的所有权转移给Qt的。

插入_widget_在位置_index_，或在工具箱的底部，如果_index_超出范围。新项目的文本设置为_text_和_icon_被显示到的左_text_。返回新项目的索引。

```
int QToolBox.insertItem (self, int index, QWidget widget, QIcon icon, QString text)
```

该_widget_说法有它的所有权转移给Qt的。

这是一个重载函数。

插入_widget_在位置_index_，或在工具箱的底部，如果_index_超出范围。新项目的文本设置为_text_。返回新项目的索引。

```
bool QToolBox.isItemEnabled (self, int index)
```

返回True如果在位置的项目_index_被启用，否则返回False 。

```
QIcon QToolBox.itemIcon (self, int index)
```

[

返回该项目的位置的图标_index_如果，或者一个空图标_index_超出范围。

](qicon.html)

[**See also**](qicon.html) [setItemIcon](qtoolbox.html#setItemIcon)（ ） 。

```
QToolBox.itemInserted (self, int index)
```

后一个新的项目加入或位置插入这个虚拟处理器被调用_index_。

**See also** [itemRemoved](qtoolbox.html#itemRemoved)（ ） 。

```
QToolBox.itemRemoved (self, int index)
```

一个项目从位置移除后，此虚拟处理器被调用_index_。

**See also** [itemInserted](qtoolbox.html#itemInserted)（ ） 。

```
QString QToolBox.itemText (self, int index)
```

在位置返回项的文本_index_如果，或者一个空字符串_index_超出范围。

**See also** [setItemText](qtoolbox.html#setItemText)（ ） 。

```
QString QToolBox.itemToolTip (self, int index)
```

返回该项目的工具提示的位置_index_如果，或者一个空字符串_index_超出范围。

**See also** [setItemToolTip](qtoolbox.html#setItemToolTip)（ ） 。

```
QToolBox.removeItem (self, int index)
```

删除位置的项目_index_从工具箱中。注意，该部件是_not_删除。

```
QToolBox.setCurrentIndex (self, int index)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentIndex(int)`。

```
QToolBox.setCurrentWidget (self, QWidget widget)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentWidget(QWidget *)`。

品牌_widget_当前的窗口小部件。该_widget_必须在此工具框中的项目。

**See also** [addItem](qtoolbox.html#addItem)（ ）[setCurrentIndex](qtoolbox.html#currentIndex-prop)（）和[currentWidget](qtoolbox.html#currentWidget)（ ） 。

```
QToolBox.setItemEnabled (self, int index, bool enabled)
```

If _enabled_为真，则在位置的项目_index_被启用，否则在位置的项目_index_被禁用。

**See also** [isItemEnabled](qtoolbox.html#isItemEnabled)（ ） 。

```
QToolBox.setItemIcon (self, int index, QIcon icon)
```

设置项的位置的图标_index_至_icon_。

**See also** [itemIcon](qtoolbox.html#itemIcon)（ ） 。

```
QToolBox.setItemText (self, int index, QString text)
```

设置项处位置的文本_index_至_text_。

如果提供的文字包含符号字符（ '＆' ） ，助记符会自动为它创建。后面的“＆”将被用来作为快捷键的字符。任何先前的记忆将被复盖，或者如果没有助记符由文本定义清除。请参阅[QShortcut](qshortcut.html#mnemonic)有关详细信息的文档（显示的实际符号，使用“\u0026\u0026” ） 。

**See also** [itemText](qtoolbox.html#itemText)（ ） 。

```
QToolBox.setItemToolTip (self, int index, QString toolTip)
```

设置项的位置的工具提示_index_至_toolTip_。

**See also** [itemToolTip](qtoolbox.html#itemToolTip)（ ） 。

```
QToolBox.showEvent (self, QShowEvent e)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QWidget QToolBox.widget (self, int index)
```

[

返回小部件位置_index_或0，如果不存在这样的资料。

```
 QToolBox.__len__ (self)
```

* * *

## Qt Signal Documentation

```
void currentChanged (int)
```

这是该信号的默认超载。

在当前项目改变这个信号被发射。新的当前项目的索引是通过在_index_，或-1，如果没有当前项目。

](qwidget.html)