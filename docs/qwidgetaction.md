# QWidgetAction Class Reference

## [[QtGui](index.htm) module]

该QWidgetAction类扩展[QAction](qaction.html)通过插入自定义的控件到基础的行动的容器，如工具栏的接口。[More...](#details)

继承[QAction](qaction.html)。

### Methods

*   `__init__ (self, QObject parent)`
*   `list-of-QWidget createdWidgets (self)`
*   `QWidget createWidget (self, QWidget parent)`
*   `QWidget defaultWidget (self)`
*   `deleteWidget (self, QWidget widget)`
*   `bool event (self, QEvent)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `releaseWidget (self, QWidget widget)`
*   `QWidget requestWidget (self, QWidget parent)`
*   `setDefaultWidget (self, QWidget w)`

* * *

## Detailed Description

该QWidgetAction类扩展[QAction](qaction.html)通过插入自定义的控件到基础的行动的容器，如工具栏的接口。

大多数操作在一个应用程序中表示为在工具栏菜单或按钮的项目。但有时比较复杂的部件是必要的。例如，在一个文字处理软件的缩放操作可使用实现[QComboBox](qcombobox.html)在[QToolBar](qtoolbar.html)，呈现出各种不同的缩放级别。[QToolBar](qtoolbar.html)提供[QToolBar.insertWidget](qtoolbar.html#insertWidget)（）作为便利的功能，用于插入一个单一的部件。但是，如果你想实现在多个容器使用自定义的小部件进行可视化的操作，那么你必须继承QWidgetAction 。

如果一个QWidgetAction被添加到例如[QToolBar](qtoolbar.html)然后[QWidgetAction.createWidget](qwidgetaction.html#createWidget)（）被调用。该函数的重新实现应该创建一个新的自定义小部件指定的父。

如果动作是从一个容器控件，然后取出[QWidgetAction.deleteWidget](qwidgetaction.html#deleteWidget)（ ）被调用先前创建的自定义窗口小部件作为参数。默认实现隐藏窗口小部件并使用它删除[QObject.deleteLater](qobject.html#deleteLater)（ ） 。

如果你只有一个单一的自定义窗口小部件，那么你可以用它设置为默认的小工具[setDefaultWidget](qwidgetaction.html#setDefaultWidget)（ ） 。如果该操作被添加到该插件将被用于[QToolBar](qtoolbar.html)或者一般来支持QWidgetAction动作容器。如果只有一个默认插件一个QWidgetAction被添加到两个工具栏的同时则默认插件仅示出了在操作中加入第一工具条。 QWidgetAction接管了默认的窗口小部件的所有权。

请注意，它是由小部件通过重新实现鼠标事件处理程序，并调用激活动作，例如[QAction.trigger](qaction.html#trigger)（ ） 。

**Mac OS X**：如果您添加一个Widget在Mac OS X上的应用程序的菜单栏中的菜单，小工具将被添加，它会发挥作用，但有一些限制：

1.  小部件是从重设父离开[QMenu](qmenu.html)本机菜单视图。如果你表现出的菜单在其他地方（例如，作为一个弹出菜单） ，小部件不会在那里。
2.  widget的对焦/键盘操作是不可能的。
3.  由于苹果的设计，在部件上鼠标跟踪目前不起作用。
4.  连接[triggered](qaction.html#triggered)（）信号来打开一个模态对话框会导致在Mac OS X 10.4 （已知的bug被苹果公司承认）崩溃插槽，一个解决方法是使用一个QueuedConnection而不是DirectConnection 。

* * *

## Method Documentation

```
QWidgetAction.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个行动_parent_。

```
list-of-QWidget QWidgetAction.createdWidgets (self)
```

返回已使用该控件列表[createWidget](qwidgetaction.html#createWidget)（）和目前正在由小部件使用的行动已被添加到。

```
QWidget QWidgetAction.createWidget (self, QWidget parent)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

这个函数被调用时的动作被添加到支持自定义部件的容器控件。如果你不希望一个自定义窗口小部件被用作指定的操作的代表性_parent_窗口小部件然后0应该返回。

](qwidget.html)

[**See also**](qwidget.html) [deleteWidget](qwidgetaction.html#deleteWidget)（ ） 。

```
QWidget QWidgetAction.defaultWidget (self)
```

[

返回默认的小部件。

](qwidget.html)

[**See also**](qwidget.html) [setDefaultWidget](qwidgetaction.html#setDefaultWidget)（ ） 。

```
QWidgetAction.deleteWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

每当行动是从一个容器控件，使用一个自定义的显示操作删除这个函数被调用_widget_以前使用创建[createWidget](qwidgetaction.html#createWidget)（ ） 。默认实现隐藏_widget_并用准备好删除[QObject.deleteLater](qobject.html#deleteLater)（ ） 。

**See also** [createWidget](qwidgetaction.html#createWidget)（ ） 。

```
bool QWidgetAction.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QWidgetAction.eventFilter (self, QObject, QEvent)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
QWidgetAction.releaseWidget (self, QWidget widget)
```

该_widget_争论

指定发布_widget_。

支持行动容器部件调用此函数时，窗口小部件操作被删除。

**See also** [requestWidget](qwidgetaction.html#requestWidget)（ ）[deleteWidget](qwidgetaction.html#deleteWidget)（）和[defaultWidget](qwidgetaction.html#defaultWidget)（ ） 。

```
QWidget QWidgetAction.requestWidget (self, QWidget parent)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

返回表示动作的部件，用给定的_parent_。

支持行动集装箱部件可以调用这个函数来请求一个widget作为动作的视觉表现。

](qwidget.html)

[**See also**](qwidget.html) [releaseWidget](qwidgetaction.html#releaseWidget)（ ）[createWidget](qwidgetaction.html#createWidget)（）和[defaultWidget](qwidgetaction.html#defaultWidget)（ ） 。

```
QWidgetAction.setDefaultWidget (self, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

Sets _widget_是默认的小部件。所有权转移至[QWidgetAction](qwidgetaction.html)。除非[createWidget](qwidgetaction.html#createWidget)（ ）是由一个子类重新实现当一个容器控件通过请求将Widget返回一个新插件的默认控件是用来[requestWidget](qwidgetaction.html#requestWidget)（ ） 。

**See also** [defaultWidget](qwidgetaction.html#defaultWidget)（ ） 。