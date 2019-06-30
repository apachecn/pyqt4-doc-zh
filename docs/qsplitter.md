# QSplitter Class Reference

## [[QtGui](index.htm) module]

该QSplitter类实现分离器部件。[More...](#details)

继承[QFrame](qframe.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, Qt.Orientation orientation, QWidget parent = None)`
*   `addWidget (self, QWidget widget)`
*   `changeEvent (self, QEvent)`
*   `childEvent (self, QChildEvent)`
*   `bool childrenCollapsible (self)`
*   `int closestLegalPosition (self, int, int)`
*   `int count (self)`
*   `QSplitterHandle createHandle (self)`
*   `bool event (self, QEvent)`
*   `(int, int) getRange (self, int index)`
*   `QSplitterHandle handle (self, int index)`
*   `int handleWidth (self)`
*   `int indexOf (self, QWidget w)`
*   `insertWidget (self, int index, QWidget widget)`
*   `bool isCollapsible (self, int index)`
*   `QSize minimumSizeHint (self)`
*   `moveSplitter (self, int pos, int index)`
*   `bool opaqueResize (self)`
*   `Qt.Orientation orientation (self)`
*   `refresh (self)`
*   `resizeEvent (self, QResizeEvent)`
*   `bool restoreState (self, QByteArray state)`
*   `QByteArray saveState (self)`
*   `setChildrenCollapsible (self, bool)`
*   `setCollapsible (self, int index, bool)`
*   `setHandleWidth (self, int)`
*   `setOpaqueResize (self, bool opaque = True)`
*   `setOrientation (self, Qt.Orientation)`
*   `setRubberBand (self, int position)`
*   `setSizes (self, list-of-int list)`
*   `setStretchFactor (self, int index, int stretch)`
*   `QSize sizeHint (self)`
*   `list-of-int sizes (self)`
*   `QWidget widget (self, int index)`

### Special Methods

*   `__len__ (self)`

### Qt Signals

*   `void splitterMoved (int,int)`

* * *

## Detailed Description

该QSplitter类实现分离器部件。

分离器可以让用户通过拖动孩子们之间的边界控制子控件的大小。任何数量的微件可以由单个分离器进行控制。典型的使用QSplitter的是创建了几个小部件，并使用它们添加[insertWidget](qsplitter.html#insertWidget)（）或[addWidget](qsplitter.html#addWidget)（ ） 。

下面的例子将显示一个[QListView](qlistview.html)，[QTreeView](qtreeview.html)和[QTextEdit](qtextedit.html)并排，有两个分配器手柄：

```
     QSplitter *splitter = new QSplitter(parent);
     [QListView](qlistview.html) *listview = new [QListView](qlistview.html);
     [QTreeView](qtreeview.html) *treeview = new [QTreeView](qtreeview.html);
     [QTextEdit](qtextedit.html) *textedit = new [QTextEdit](qtextedit.html);
     splitter->addWidget(listview);
     splitter->addWidget(treeview);
     splitter->addWidget(textedit);

```

如果一个部件已经是一个QSplitter内部时，[insertWidget](qsplitter.html#insertWidget)（）或[addWidget](qsplitter.html#addWidget)（ ）被调用时，它会移动到新的位置。这可以用于以后重新排列在分离器的部件。您可以使用[indexOf](qsplitter.html#indexOf)（ ）[widget](qsplitter.html#widget)（）和[count](qsplitter.html#count)（ ）进入到分离器内的部件。

默认QSplitter将其子水平（并排） ，你可以使用setOrientation （[Qt.Vertical](qt.html#Orientation-enum)）垂直放置其子出来。

默认情况下，所有的widget可以大或小如用户意愿之间的[minimumSizeHint](qsplitter.html#minimumSizeHint)（ ）（或[minimumSize](qwidget.html#minimumSize-prop)（））和[maximumSize](qwidget.html#maximumSize-prop)小部件（ ） 。

QSplitter默认情况下，动态调整​​其子。如果你宁愿QSplitter调整孩子只有在调整操作结束时，调用setOpaqueResize （假） 。

尺寸的小部件之间的初始分布是通过将初始大小与拉伸系数相乘确定。您也可以使用[setSizes](qsplitter.html#setSizes)（ ）来设置所有的部件的尺寸。该功能[sizes](qsplitter.html#sizes)（）返回由用户设置的大小。或者，您可以保存和恢复窗口小部件的大小从[QByteArray](qbytearray.html) using [saveState](qsplitter.html#saveState)（）和[restoreState](qsplitter.html#restoreState)（ ）分别。

当你[hide](qwidget.html#hide)（ ）一个子其空间将会是其他孩子分发。这将恢复当你[show](qwidget.html#show)（ ）一次。

* * *

## Method Documentation

```
QSplitter.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个水平拆分与_parent_传递给参数[QFrame](qframe.html)构造函数。

**See also** [setOrientation](qsplitter.html#orientation-prop)（ ） 。

```
QSplitter.__init__ (self, Qt.Orientation orientation, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个分离器具有给定_orientation_和_parent_。

**See also** [setOrientation](qsplitter.html#orientation-prop)（ ） 。

```
QSplitter.addWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

将给定_widget_所有其他项目后分流器的布局。

If _widget_已经在分离器，将被移动到新的位置。

**See also** [insertWidget](qsplitter.html#insertWidget)（ ）[widget](qsplitter.html#widget)（）和[indexOf](qsplitter.html#indexOf)（ ） 。

```
QSplitter.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QSplitter.childEvent (self, QChildEvent)
```

从重新实现[QObject.childEvent](qobject.html#childEvent)（ ） 。

告诉孩子小部件描述的分配器_c_已经被插入或移除。

这种方法也可以用来处理其中一个部件与所述分离器创建作为父母，但不与显式添加的情况[insertWidget](qsplitter.html#insertWidget)（）或[addWidget](qsplitter.html#addWidget)（ ） 。这是为了兼容而不是将小部件成新的代码分离器的推荐方式。请使用[insertWidget](qsplitter.html#insertWidget)（）或[addWidget](qsplitter.html#addWidget)（ ）在新代码。

**See also** [addWidget](qsplitter.html#addWidget)（）和[insertWidget](qsplitter.html#insertWidget)（ ） 。

```
bool QSplitter.childrenCollapsible (self)
```

```
int QSplitter.closestLegalPosition (self, int, int)
```

返回最接近的合法地位_pos_与索引窗口小部件的_index_。

对于从右到左的语言，如阿拉伯语和希伯来语，水平分割的布局是相反的。位置然后从部件的右边缘测量。

**See also** [getRange](qsplitter.html#getRange)（ ） 。

```
int QSplitter.count (self)
```

返回包含在该分离器的布局的部件的数量。

**See also** [widget](qsplitter.html#widget)（）和[handle](qsplitter.html#handle)（ ） 。

```
QSplitterHandle QSplitter.createHandle (self)
```

[

返回一个新的分流器句柄作为这个分配器的子部件。此功能可以在子类中重新实现来提供定制手柄的支持。

](qsplitterhandle.html)

[**See also**](qsplitterhandle.html) [handle](qsplitter.html#handle)（）和[indexOf](qsplitter.html#indexOf)（ ） 。

```
bool QSplitter.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
(int, int) QSplitter.getRange (self, int index)
```

返回索引分离器的有效范围_index_在*_min_和*_max_如果_min_和_max_不为0。

```
QSplitterHandle QSplitter.handle (self, int index)
```

[

在给定的返回句柄向左（或以上）在分离器的布局的项目_index_。索引为0的句柄总是隐藏。

对于从右到左的语言，如阿拉伯语和希伯来语，水平分割的布局是相反的。手柄将是小部件的权于_index_。

](qsplitterhandle.html)

[**See also**](qsplitterhandle.html) [count](qsplitter.html#count)（ ）[widget](qsplitter.html#widget)（ ）[indexOf](qsplitter.html#indexOf)（ ）[createHandle](qsplitter.html#createHandle)（）和[setHandleWidth](qsplitter.html#handleWidth-prop)（ ） 。

```
int QSplitter.handleWidth (self)
```

```
int QSplitter.indexOf (self, QWidget w)
```

返回索引中指定的分路器的布局_widget_。这也适用于手柄。

手柄的编号从0 。因为有子控件居然有手柄，但手柄位置0永远是隐藏的。

**See also** [count](qsplitter.html#count)（）和[widget](qsplitter.html#widget)（ ） 。

```
QSplitter.insertWidget (self, int index, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

插入_widget_在给定的规定在分线器的布局_index_。

If _widget_已经在分离器，将被移动到新的位置。

如果_index_是一个无效的索引，那么控件将被插入在最后。

**See also** [addWidget](qsplitter.html#addWidget)（ ）[indexOf](qsplitter.html#indexOf)（）和[widget](qsplitter.html#widget)（ ） 。

```
bool QSplitter.isCollapsible (self, int index)
```

返回True如果在部件_index_是可折叠的，否则返回False

```
QSize QSplitter.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QSplitter.moveSplitter (self, int pos, int index)
```

将分割器手柄的左边缘或上边缘处_index_尽可能靠近定位_pos_，它是从微件的左边缘或上边缘之间的距离。

对于从右到左的语言，如阿拉伯语和希伯来语，水平分割的布局是相反的。_pos_然后，从部件的右边缘之间的距离。

**See also** [splitterMoved](qsplitter.html#splitterMoved)（ ）[closestLegalPosition](qsplitter.html#closestLegalPosition)（）和[getRange](qsplitter.html#getRange)（ ） 。

```
bool QSplitter.opaqueResize (self)
```

```
Qt.Orientation QSplitter.orientation (self)
```

[

```
QSplitter.refresh (self)
```

更新分路器的状态。你不应该需要调用这个函数。

```
QSplitter.resizeEvent (self, QResizeEvent)
```

](qt.html#Orientation-enum)

[从重新实现](qt.html#Orientation-enum)[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
bool QSplitter.restoreState (self, QByteArray state)
```

恢复分路器的布局到_state_规定。返回True如果状态恢复，否则返回False 。

通常，这是配合使用[QSettings](qsettings.html)从过去的会话还原大小。下面是一个例子：

恢复分路器的状态：

```
     [QSettings](qsettings.html) settings;
     splitter->restoreState(settings.value("splitterSizes").toByteArray());

```

如果未能恢复分路器的布局可能会导致无效或外的最新数据所提供的字节数组中。

**See also** [saveState](qsplitter.html#saveState)（ ） 。

```
QByteArray QSplitter.saveState (self)
```

[

保存分路器的布局的状态。

](qbytearray.html)

[通常，这是配合使用](qbytearray.html)[QSettings](qsettings.html)要记住的大小为今后的会议。版本号码被存储作为数据的一部分。下面是一个例子：

```
     [QSettings](qsettings.html) settings;
     settings.setValue("splitterSizes", splitter->saveState());

```

**See also** [restoreState](qsplitter.html#restoreState)（ ） 。

```
QSplitter.setChildrenCollapsible (self, bool)
```

```
QSplitter.setCollapsible (self, int index, bool)
```

设置是否在子构件索引_index_是可折叠_collapse_。

默认情况下，孩子是可折叠的，这意味着用户可以调整下来，大小为0 ，即使他们有一个非零[minimumSize](qwidget.html#minimumSize-prop)（）或[minimumSizeHint](qsplitter.html#minimumSizeHint)（ ） 。这种行为可以基于每个插件基础由通过设置在调用此函数，或全球范围内为在分离器的所有部件被改变的[childrenCollapsible](qsplitter.html#childrenCollapsible-prop)属性。

**See also** [isCollapsible](qsplitter.html#isCollapsible)（）和[childrenCollapsible](qsplitter.html#childrenCollapsible-prop)。

```
QSplitter.setHandleWidth (self, int)
```

```
QSplitter.setOpaqueResize (self, bool opaque = True)
```

```
QSplitter.setOrientation (self, Qt.Orientation)
```

```
QSplitter.setRubberBand (self, int position)
```

显示一个橡皮筋的位置_pos_。如果_pos_为负时，该橡胶带被除去。

```
QSplitter.setSizes (self, list-of-int list)
```

设置子控件的尺寸大小，以在给定的值_list_。

如果分离器是水平的，该值设置每个插件的宽度以像素为单位，从左至右。如果分离器是垂直的，每个插件的高度被设置，从顶部到底部。

在多馀的值_list_将被忽略。如果_list_包含的值太少，结果是不确定的，但程序仍然会表现良好。

分配器部件的整体尺寸不会受到影响。相反，任何附加的/缺失的空间是按照体积的相对重量之间分配部件。

如果指定大小为0 ，该部件将是不可见的。是小部件的大小策略保存。即，值越小则相应小窗口的最小尺寸暗示将由暗示的值来代替。

**See also** [sizes](qsplitter.html#sizes)（ ） 。

```
QSplitter.setStretchFactor (self, int index, int stretch)
```

更新widget的大小政策在位置_index_以具有一个伸展因子_stretch_。

_stretch_是不实际的伸展系数;的有效伸长率是通过采取小窗口的初始大小，并将其与计算出的乘法_stretch_。

此功能提供了方便。它相当于

```
 [QWidget](qwidget.html) *widget = splitter->widget(index);
 [QSizePolicy](qsizepolicy.html) policy = widget->sizePolicy();
 policy.setHorizontalStretch(stretch);
 policy.setVerticalStretch(stretch);
 widget->setSizePolicy(policy);

```

**See also** [setSizes](qsplitter.html#setSizes)（）和[widget](qsplitter.html#widget)（ ） 。

```
QSize QSplitter.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
list-of-int QSplitter.sizes (self)
```

返回此分路器的所有部件的尺寸参数列表。

如果分离器的方向是水平的，该列表包含该部件的宽度以像素为单位，从左至右，如果方向是垂直的，该列表包含以像素为单位的窗口小部件的高度，从顶部到底部。

给出的值到另一个分路器的[setSizes](qsplitter.html#setSizes)（）函数，会产生具有相同的布局，这其中一个分离器。

需要注意的是看不见的小部件有大小为0 。

**See also** [setSizes](qsplitter.html#setSizes)（ ） 。

```
QWidget QSplitter.widget (self, int index)
```

[

返回该插件在给定的_index_在分离器的布局。

](qwidget.html)

[**See also**](qwidget.html) [count](qsplitter.html#count)（ ）[handle](qsplitter.html#handle)（ ）[indexOf](qsplitter.html#indexOf)（）和[insertWidget](qsplitter.html#insertWidget)（ ） 。

```
 QSplitter.__len__ (self)
```

* * *

## Qt Signal Documentation

```
void splitterMoved (int,int)
```

这是该信号的默认超载。

这个信号被发射时，分离器处理在一个特定的_index_已经被移动到位置_pos_。

对于从右到左的语言，如阿拉伯语和希伯来语，水平分割的布局是相反的。_pos_然后，从部件的右边缘之间的距离。

**See also** [moveSplitter](qsplitter.html#moveSplitter)（ ） 。