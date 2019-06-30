# QStackedLayout Class Reference

## [[QtGui](index.htm) module]

该QStackedLayout类提供了一个堆叠部件，其中只有一个小部件是可见的时间的。[More...](#details)

继承[QLayout](qlayout.html)。

### Types

*   `enum StackingMode { StackOne, StackAll }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QWidget parent)`
*   `__init__ (self, QLayout parentLayout)`
*   `addItem (self, QLayoutItem item)`
*   `int addWidget (self, QWidget w)`
*   `int count (self)`
*   `int currentIndex (self)`
*   `QWidget currentWidget (self)`
*   `int insertWidget (self, int index, QWidget w)`
*   `QLayoutItem itemAt (self, int)`
*   `QSize minimumSize (self)`
*   `setCurrentIndex (self, int index)`
*   `setCurrentWidget (self, QWidget w)`
*   `setGeometry (self, QRect rect)`
*   `setStackingMode (self, StackingMode stackingMode)`
*   `QSize sizeHint (self)`
*   `StackingMode stackingMode (self)`
*   `QLayoutItem takeAt (self, int)`
*   `QWidget widget (self, int)`
*   `QWidget widget (self)`

### Qt Signals

*   `void currentChanged (int)`
*   `void widgetRemoved (int)`

* * *

## Detailed Description

该QStackedLayout类提供了一个堆叠部件，其中只有一个小部件是可见的时间的。

QStackedLayout可以用来创建类似于通过提供一个用户接口[QTabWidget](qtabwidget.html)。还有一个方便[QStackedWidget](qstackedwidget.html)类建立在QStackedLayout之上。

一个QStackedLayout可以填入一些子控件（ “页” ）的。例如：

```
     [QWidget](qwidget.html) *firstPageWidget = new [QWidget](qwidget.html);
     [QWidget](qwidget.html) *secondPageWidget = new [QWidget](qwidget.html);
     [QWidget](qwidget.html) *thirdPageWidget = new [QWidget](qwidget.html);

     QStackedLayout *stackedLayout = new QStackedLayout;
     stackedLayout->addWidget(firstPageWidget);
     stackedLayout->addWidget(secondPageWidget);
     stackedLayout->addWidget(thirdPageWidget);

     [QVBoxLayout](qvboxlayout.html) *mainLayout = new [QVBoxLayout](qvboxlayout.html);
     mainLayout->addLayout(stackedLayout);
     setLayout(mainLayout);

```

QStackedLayout没有提供内在的手段来切换页面的用户。这通常是通过做[QComboBox](qcombobox.html)或[QListWidget](qlistwidget.html)用于存储QStackedLayout的页面的标题。例如：

```
     [QComboBox](qcombobox.html) *pageComboBox = new [QComboBox](qcombobox.html);
     pageComboBox->addItem(tr("Page 1"));
     pageComboBox->addItem(tr("Page 2"));
     pageComboBox->addItem(tr("Page 3"));
     connect(pageComboBox, SIGNAL(activated(int)),
             stackedLayout, SLOT(setCurrentIndex(int)));

```

当填充布局，窗口小部件添加到内部列表。该[indexOf](qlayout.html#indexOf)（ ）函数返回在该列表中一个部件的指标。窗口小部件可以被使用添加到该列表的末尾的[addWidget](qstackedlayout.html#addWidget)（ ）函数，或者使用插入一个给定索引处的[insertWidget](qstackedlayout.html#insertWidget)（）函数。该[removeWidget](qlayout.html#removeWidget)（ ）函数移除插件的给定索引从布局的。包含在布局窗口小部件的数量，可使用所获得的[count](qstackedlayout.html#count-prop)（）函数。

该[widget](qstackedlayout.html#widget)（ ）函数返回的部件在给定的索引位置。这显示在屏幕上的小部件的指数由下式给出[currentIndex](qstackedlayout.html#currentIndex-prop)（） ，并且可以使用被改变[setCurrentIndex](qstackedlayout.html#currentIndex-prop)（ ） 。以类似的方式，将当前显示的窗口小部件可以使用被检索的[currentWidget](qstackedlayout.html#currentWidget)（）函数，并使用改变了[setCurrentWidget](qstackedlayout.html#setCurrentWidget)（）函数。

每当当前部件的布局的变化或窗口小部件是从布局中删除，则[currentChanged](qstackedlayout.html#currentChanged)（）和[widgetRemoved](qstackedlayout.html#widgetRemoved)（）信号被分别发射。

* * *

## Type Documentation

```
QStackedLayout.StackingMode
```

这个枚举变量指定的布局如何处理其对自己的知名度子部件。

| Constant | Value | Description |
| --- | --- | --- |
| `QStackedLayout.StackOne` | `0` | 只在当前窗口小部件是可见的。这是默认的。 |
| `QStackedLayout.StackAll` | `1` | 所有部件都是可见的。当前插件仅仅提高。 |

这个枚举被引入或修改的Qt 4.4 。

* * *

## Method Documentation

```
QStackedLayout.__init__ (self)
```

构造一个[QStackedLayout](qstackedlayout.html)没有父。

This [QStackedLayout](qstackedlayout.html)必须安装在稍后一个部件才能生效。

**See also** [addWidget](qstackedlayout.html#addWidget)（）和[insertWidget](qstackedlayout.html#insertWidget)（ ） 。

```
QStackedLayout.__init__ (self, QWidget parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QStackedLayout](qstackedlayout.html)用给定的_parent_。

这种布局将在自行安装_parent_小工具和管理其子的几何形状。

```
QStackedLayout.__init__ (self, QLayout parentLayout)
```

该_parentLayout_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QStackedLayout](qstackedlayout.html)并将其插入到给定的_parentLayout_。

```
QStackedLayout.addItem (self, QLayoutItem item)
```

该_item_说法有它的所有权转移给Qt的。

从重新实现[QLayout.addItem](qlayout.html#addItem)（ ） 。

```
int QStackedLayout.addWidget (self, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

将给定_widget_这一布局的结尾，并返回的索引位置_widget_。

如果[QStackedLayout](qstackedlayout.html)为空，此函数被调用之前，给定的_widget_成为当前窗口小部件。

**See also** [insertWidget](qstackedlayout.html#insertWidget)（ ）[removeWidget](qlayout.html#removeWidget)（）和[setCurrentWidget](qstackedlayout.html#setCurrentWidget)（ ） 。

```
int QStackedLayout.count (self)
```

```
int QStackedLayout.currentIndex (self)
```

```
QWidget QStackedLayout.currentWidget (self)
```

[

返回当前窗口小部件，或者0 ，如果有这个布局没有任何部件。

](qwidget.html)

[**See also**](qwidget.html) [currentIndex](qstackedlayout.html#currentIndex-prop)（）和[setCurrentWidget](qstackedlayout.html#setCurrentWidget)（ ） 。

```
int QStackedLayout.insertWidget (self, int index, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

插入给定_widget_在给定的_index_在这[QStackedLayout](qstackedlayout.html)。如果_index_超出范围，小部件被追加（在这种情况下，它是实际的指数_widget_即返回） 。

如果[QStackedLayout](qstackedlayout.html)为空，此函数被调用之前，给定的_widget_成为当前窗口小部件。

插入一个新的widget指数小于或等于当前的索引处将增加当前索引，但保持当前的窗口小部件。

**See also** [addWidget](qstackedlayout.html#addWidget)（ ）[removeWidget](qlayout.html#removeWidget)（）和[setCurrentWidget](qstackedlayout.html#setCurrentWidget)（ ） 。

```
QLayoutItem QStackedLayout.itemAt (self, int)
```

[](qlayoutitem.html)

[从重新实现](qlayoutitem.html)[QLayout.itemAt](qlayout.html#itemAt)（ ） 。

```
QSize QStackedLayout.minimumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.minimumSize](qlayoutitem.html#minimumSize)（ ） 。

```
QStackedLayout.setCurrentIndex (self, int index)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentIndex(int)`。

```
QStackedLayout.setCurrentWidget (self, QWidget w)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentWidget(QWidget *)`。

设置当前窗口小部件被指定_widget_。新的当前窗口小部件必须已经包含在这个堆叠布局。

**See also** [setCurrentIndex](qstackedlayout.html#currentIndex-prop)（）和[currentWidget](qstackedlayout.html#currentWidget)（ ） 。

```
QStackedLayout.setGeometry (self, QRect rect)
```

从重新实现[QLayoutItem.setGeometry](qlayoutitem.html#setGeometry)（ ） 。

```
QStackedLayout.setStackingMode (self, StackingMode stackingMode)
```

```
QSize QStackedLayout.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.sizeHint](qlayoutitem.html#sizeHint)（ ） 。

```
StackingMode QStackedLayout.stackingMode (self)
```

[](qstackedlayout.html#StackingMode-enum)

```
QLayoutItem QStackedLayout.takeAt (self, int)
```

[

该_QLayoutItem_结果

](qlayoutitem.html)

[从重新实现](qlayoutitem.html)[QLayout.takeAt](qlayout.html#takeAt)（ ） 。

```
QWidget QStackedLayout.widget (self, int)
```

[

返回该插件在给定的_index_或0 ，如果没有插件在给定的位置上。

](qwidget.html)

[**See also**](qwidget.html) [currentWidget](qstackedlayout.html#currentWidget)（）和[indexOf](qlayout.html#indexOf)（ ） 。

```
QWidget QStackedLayout.widget (self)
```

[

* * *

## Qt Signal Documentation

```
void currentChanged (int)
```

这是该信号的默认超载。

](qwidget.html)

[这个信号被发射时的电流小部件在布局中的变化。该_index_指定新的当前部件的索引，或者-1，如果没有一个新的（例如，如果没有部件在](qwidget.html)[QStackedLayout](qstackedlayout.html)）

**See also** [currentWidget](qstackedlayout.html#currentWidget)（）和[setCurrentWidget](qstackedlayout.html#setCurrentWidget)（ ） 。

```
void widgetRemoved (int)
```

这是该信号的默认超载。

每当一个部件被从布局中删除这个信号被发射。 widget的_index_作为参数传递。

**See also** [removeWidget](qlayout.html#removeWidget)（ ） 。