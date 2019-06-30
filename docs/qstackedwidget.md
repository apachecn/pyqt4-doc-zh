# QStackedWidget Class Reference

## [[QtGui](index.htm) module]

该QStackedWidget类提供了一个堆叠部件，其中只有一个小部件是可见的时间的。[More...](#details)

继承[QFrame](qframe.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `int addWidget (self, QWidget w)`
*   `int count (self)`
*   `int currentIndex (self)`
*   `QWidget currentWidget (self)`
*   `bool event (self, QEvent e)`
*   `int indexOf (self, QWidget)`
*   `int insertWidget (self, int index, QWidget w)`
*   `removeWidget (self, QWidget w)`
*   `setCurrentIndex (self, int index)`
*   `setCurrentWidget (self, QWidget w)`
*   `QWidget widget (self, int)`

### Special Methods

*   `__len__ (self)`

### Qt Signals

*   `void currentChanged (int)`
*   `void widgetRemoved (int)`

* * *

## Detailed Description

该QStackedWidget类提供了一个堆叠部件，其中只有一个小部件是可见的时间的。

QStackedWidget可以用来创建类似于通过提供一个用户接口[QTabWidget](qtabwidget.html)。它是建立在顶部的便利布局小部件[QStackedLayout](qstackedlayout.html)类。

喜欢[QStackedLayout](qstackedlayout.html)， QStackedWidget可以构造并填充了一系列子控件（ “页” ）中：

```
     [QWidget](qwidget.html) *firstPageWidget = new [QWidget](qwidget.html);
     [QWidget](qwidget.html) *secondPageWidget = new [QWidget](qwidget.html);
     [QWidget](qwidget.html) *thirdPageWidget = new [QWidget](qwidget.html);

     QStackedWidget *stackedWidget = new QStackedWidget;
     stackedWidget->addWidget(firstPageWidget);
     stackedWidget->addWidget(secondPageWidget);
     stackedWidget->addWidget(thirdPageWidget);

     [QVBoxLayout](qvboxlayout.html) *layout = new [QVBoxLayout](qvboxlayout.html);
     layout->addWidget(stackedWidget);
     setLayout(layout);

```

QStackedWidget没有提供内在的手段来切换页面的用户。这通常是通过做[QComboBox](qcombobox.html)或[QListWidget](qlistwidget.html)用于存储QStackedWidget的页面的标题。例如：

```
     [QComboBox](qcombobox.html) *pageComboBox = new [QComboBox](qcombobox.html);
     pageComboBox->addItem(tr("Page 1"));
     pageComboBox->addItem(tr("Page 2"));
     pageComboBox->addItem(tr("Page 3"));
     connect(pageComboBox, SIGNAL(activated(int)),
             stackedWidget, SLOT(setCurrentIndex(int)));

```

当填充堆叠部件，该部件被添加到内部列表。该[indexOf](qstackedwidget.html#indexOf)（ ）函数返回在该列表中一个部件的指标。窗口小部件可以被使用添加到该列表的末尾的[addWidget](qstackedwidget.html#addWidget)（ ）函数，或者使用插入一个给定索引处的[insertWidget](qstackedwidget.html#insertWidget)（）函数。该[removeWidget](qstackedwidget.html#removeWidget)（ ）函数会移除堆叠部件一个部件。包含在堆叠部件的部件的数量，可使用所获得的[count](qstackedwidget.html#count-prop)（）函数。

该[widget](qstackedwidget.html#widget)（ ）函数返回的部件在给定的索引位置。这显示在屏幕上的小部件的指数由下式给出[currentIndex](qstackedwidget.html#currentIndex-prop)（） ，并且可以使用被改变[setCurrentIndex](qstackedwidget.html#currentIndex-prop)（ ） 。以类似的方式，将当前显示的窗口小部件可以使用被检索的[currentWidget](qstackedwidget.html#currentWidget)（）函数，并使用改变了[setCurrentWidget](qstackedwidget.html#setCurrentWidget)（）函数。

每当当前部件的叠层部件的改变或一个部件被从堆叠的部件移除时，[currentChanged](qstackedwidget.html#currentChanged)（）和[widgetRemoved](qstackedwidget.html#widgetRemoved)（）信号被分别发射。

* * *

## Method Documentation

```
QStackedWidget.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QStackedWidget](qstackedwidget.html)用给定的_parent_。

**See also** [addWidget](qstackedwidget.html#addWidget)（）和[insertWidget](qstackedwidget.html#insertWidget)（ ） 。

```
int QStackedWidget.addWidget (self, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

添加给定的_widget_到[QStackedWidget](qstackedwidget.html)并返回索引位置。所有权_widget_到传递[QStackedWidget](qstackedwidget.html)。

如果[QStackedWidget](qstackedwidget.html)为空，此函数被调用之前，_widget_成为当前窗口小部件。

**See also** [insertWidget](qstackedwidget.html#insertWidget)（ ）[removeWidget](qstackedwidget.html#removeWidget)（）和[setCurrentWidget](qstackedwidget.html#setCurrentWidget)（ ） 。

```
int QStackedWidget.count (self)
```

```
int QStackedWidget.currentIndex (self)
```

```
QWidget QStackedWidget.currentWidget (self)
```

[

返回当前窗口小部件，或者0 ，如果没有子控件。

](qwidget.html)

[**See also**](qwidget.html) [currentIndex](qstackedwidget.html#currentIndex-prop)（）和[setCurrentWidget](qstackedwidget.html#setCurrentWidget)（ ） 。

```
bool QStackedWidget.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QStackedWidget.indexOf (self, QWidget)
```

返回给定索引_widget_，或-1，如果给定的_widget_不是的孩子[QStackedWidget](qstackedwidget.html)。

**See also** [currentIndex](qstackedwidget.html#currentIndex-prop)（）和[widget](qstackedwidget.html#widget)（ ） 。

```
int QStackedWidget.insertWidget (self, int index, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

插入给定_widget_在给定的_index_在[QStackedWidget](qstackedwidget.html)。所有权_widget_到传递[QStackedWidget](qstackedwidget.html)。如果_index_超出范围时，_widget_追加（在这种情况下，它是实际的指数_widget_即返回） 。

如果[QStackedWidget](qstackedwidget.html)为空，此函数被调用之前，给定的_widget_成为当前窗口小部件。

插入一个新的widget指数小于或等于当前的索引处将增加当前索引，但保持当前的窗口小部件。

**See also** [addWidget](qstackedwidget.html#addWidget)（ ）[removeWidget](qstackedwidget.html#removeWidget)（）和[setCurrentWidget](qstackedwidget.html#setCurrentWidget)（ ） 。

```
QStackedWidget.removeWidget (self, QWidget w)
```

移除_widget_从[QStackedWidget](qstackedwidget.html)。即，_widget_ is _not_删除，但简单地从层叠布局除去，导致它被隐藏。

**Note:**所有权_widget_恢复到应用程序。

**See also** [addWidget](qstackedwidget.html#addWidget)（ ）[insertWidget](qstackedwidget.html#insertWidget)（）和[currentWidget](qstackedwidget.html#currentWidget)（ ） 。

```
QStackedWidget.setCurrentIndex (self, int index)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentIndex(int)`。

```
QStackedWidget.setCurrentWidget (self, QWidget w)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentWidget(QWidget *)`。

设置当前窗口小部件被指定_widget_。新的当前窗口小部件必须已经包含在这个堆叠部件。

**See also** [currentWidget](qstackedwidget.html#currentWidget)（）和[setCurrentIndex](qstackedwidget.html#currentIndex-prop)（ ） 。

```
QWidget QStackedWidget.widget (self, int)
```

[

返回该插件在给定的_index_或0，如果不存在这样的窗口小部件。

](qwidget.html)

[**See also**](qwidget.html) [currentWidget](qstackedwidget.html#currentWidget)（）和[indexOf](qstackedwidget.html#indexOf)（ ） 。

```
 QStackedWidget.__len__ (self)
```

* * *

## Qt Signal Documentation

```
void currentChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的电流小窗口改变。

该参数保存_index_新的当前窗口小部件，或者为-1 ，如果没有一个新的（例如，如果没有部件在[QStackedWidget](qstackedwidget.html)） 。

**See also** [currentWidget](qstackedwidget.html#currentWidget)（）和[setCurrentWidget](qstackedwidget.html#setCurrentWidget)（ ） 。

```
void widgetRemoved (int)
```

这是该信号的默认超载。

每当一个部件被去除这个信号被发射。 widget的_index_作为参数传递。

**See also** [removeWidget](qstackedwidget.html#removeWidget)（ ） 。