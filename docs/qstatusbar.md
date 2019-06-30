# QStatusBar Class Reference

## [[QtGui](index.htm) module]

该QStatusBar类提供适合呈现状态信息的单槓。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `addPermanentWidget (self, QWidget widget, int stretch = 0)`
*   `addWidget (self, QWidget widget, int stretch = 0)`
*   `clearMessage (self)`
*   `QString currentMessage (self)`
*   `bool event (self, QEvent)`
*   `hideOrShow (self)`
*   `int insertPermanentWidget (self, int index, QWidget widget, int stretch = 0)`
*   `int insertWidget (self, int index, QWidget widget, int stretch = 0)`
*   `bool isSizeGripEnabled (self)`
*   `paintEvent (self, QPaintEvent)`
*   `reformat (self)`
*   `removeWidget (self, QWidget widget)`
*   `resizeEvent (self, QResizeEvent)`
*   `setSizeGripEnabled (self, bool)`
*   `showEvent (self, QShowEvent)`
*   `showMessage (self, QString message, int msecs = 0)`

### Qt Signals

*   `void messageChanged (const QString&)`

* * *

## Detailed Description

该QStatusBar类提供适合呈现状态信息的单槓。

每一个状态指示灯分为三类：

*   _Temporary_ - briefly occupies most of the status bar. Used to explain tool tip texts or menu entries, for example.
*   _Normal_ - occupies part of the status bar and may be hidden by temporary messages. Used to display the page and line number in a word processor, for example.
*   _Permanent_ - is never hidden. Used for important mode indications, for example, some applications put a Caps Lock indicator in the status bar.

QStatusBar可以显示所有三种类型的指标。

通常情况下，状态栏功能的请求时就某[QMainWindow](qmainwindow.html)对象。[QMainWindow](qmainwindow.html)提供了一个主应用程序窗口，带有菜单栏，工具栏，停靠小部件_and_围绕一个大型的中央部件的状态栏。状态栏可使用的检索[QMainWindow.statusBar](qmainwindow.html#statusBar)（）函数，并使用替代的[QMainWindow.setStatusBar](qmainwindow.html#setStatusBar)（）函数。

使用[showMessage](qstatusbar.html#showMessage)（）槽，以显示_temporary_消息：

```
 void MainWindow.createStatusBar()
 {
     statusBar()->showMessage(tr("Ready"));
 }

```

要删除一个临时消息，使用[clearMessage](qstatusbar.html#clearMessage)（）槽，或调用时，设置一个时间限制[showMessage](qstatusbar.html#showMessage)（ ） 。例如：

```
 void MainWindow.print()
 {
 #ifndef QT_NO_PRINTDIALOG
     [QTextDocument](qtextdocument.html) *document = textEdit->document();
     [QPrinter](qprinter.html) printer;

     [QPrintDialog](qprintdialog.html) *dlg = new [QPrintDialog](qprintdialog.html)(&printer, this);
     if (dlg->exec() != [QDialog](qdialog.html).Accepted)
         return;

     document->print(&printer);

     statusBar()->showMessage(tr("Ready"), 2000);
 #endif
 }

```

使用[currentMessage](qstatusbar.html#currentMessage)（ ）函数来检索当前显示的临时消息。该QStatusBar类还提供了[messageChanged](qstatusbar.html#messageChanged)（ ）这是发射时的临时状态信息变化的信号。

_Normal_和_Permanent_消息显示通过创建一个小部件（[QLabel](qlabel.html)，[QProgressBar](qprogressbar.html)甚至[QToolButton](qtoolbutton.html)） ，然后用其添加到状态栏[addWidget](qstatusbar.html#addWidget)（）或[addPermanentWidget](qstatusbar.html#addPermanentWidget)（）函数。使用[removeWidget](qstatusbar.html#removeWidget)（ ）函数从状态栏中删除此类消息。

```
 statusBar()->addWidget(new MyReadWriteIndication);

```

默认情况下QStatusBar提供[QSizeGrip](qsizegrip.html)在右下角。您可以使用禁用的[setSizeGripEnabled](qstatusbar.html#sizeGripEnabled-prop)（）函数。使用[isSizeGripEnabled](qstatusbar.html#sizeGripEnabled-prop)（ ）函数来确定大小手柄的当前状态。

![A status bar shown in the Plastique widget style](../img/plastique-statusbar.png)

* * *

## Method Documentation

```
QStatusBar.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个状态栏有一个大小的抓地力和给定_parent_。

**See also** [setSizeGripEnabled](qstatusbar.html#sizeGripEnabled-prop)（ ） 。

```
QStatusBar.addPermanentWidget (self, QWidget widget, int stretch = 0)
```

该_widget_说法有它的所有权转移给Qt的。

将给定_widget_永久这个状态栏，重定父级的小工具，如果它已经不这样子[QStatusBar](qstatusbar.html)对象。该_stretch_参数被用来计算一个合适的尺寸对于给定的_widget_作为状态栏的增长和收缩。默认拉伸系数为0，即给插件最小的空间。

永久意味着该插件可能无法被临时消息遮蔽。它位于状态栏的最右边。

**See also** [insertPermanentWidget](qstatusbar.html#insertPermanentWidget)（ ）[removeWidget](qstatusbar.html#removeWidget)（）和[addWidget](qstatusbar.html#addWidget)（ ） 。

```
QStatusBar.addWidget (self, QWidget widget, int stretch = 0)
```

该_widget_说法有它的所有权转移给Qt的。

将给定_widget_这个状态栏，重定父级的小工具，如果它已经不这样子[QStatusBar](qstatusbar.html)对象。该_stretch_参数被用来计算一个合适的尺寸对于给定的_widget_作为状态栏的增长和收缩。默认拉伸系数为0，即给插件最小的空间。

窗口小部件是位于最左侧的第一个永久部件（见[addPermanentWidget](qstatusbar.html#addPermanentWidget)（）） ，并且可以通过临时的消息遮蔽。

**See also** [insertWidget](qstatusbar.html#insertWidget)（ ）[removeWidget](qstatusbar.html#removeWidget)（）和[addPermanentWidget](qstatusbar.html#addPermanentWidget)（ ） 。

```
QStatusBar.clearMessage (self)
```

这种方法也是一个Qt槽与C + +的签名`void clearMessage()`。

删除正在显示的任何临时消息。

**See also** [currentMessage](qstatusbar.html#currentMessage)（ ）[showMessage](qstatusbar.html#showMessage)（）和[removeWidget](qstatusbar.html#removeWidget)（ ） 。

```
QString QStatusBar.currentMessage (self)
```

如果没有这样的消息返回当前显示的临时消息，或空字符串。

**See also** [showMessage](qstatusbar.html#showMessage)（ ） 。

```
bool QStatusBar.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QStatusBar.hideOrShow (self)
```

确保正确的窗口小部件是可见的。

所使用的[showMessage](qstatusbar.html#showMessage)（）和[clearMessage](qstatusbar.html#clearMessage)（）函数。

```
int QStatusBar.insertPermanentWidget (self, int index, QWidget widget, int stretch = 0)
```

该_widget_说法有它的所有权转移给Qt的。

插入给定_widget_在给定的_index_永久这个状态栏，重定父级的小工具，如果它已经不这样子[QStatusBar](qstatusbar.html)对象。如果_index_超出范围，小部件被追加（在这种情况下它是返回的widget的实际索引） 。

该_stretch_参数被用来计算一个合适的尺寸对于给定的_widget_作为状态栏的增长和收缩。默认拉伸系数为0，即给插件最小的空间。

永久意味着该插件可能无法被临时消息遮蔽。它位于状态栏的最右边。

这个函数中引入了Qt 4.2中。

**See also** [addPermanentWidget](qstatusbar.html#addPermanentWidget)（ ）[removeWidget](qstatusbar.html#removeWidget)（）和[addWidget](qstatusbar.html#addWidget)（ ） 。

```
int QStatusBar.insertWidget (self, int index, QWidget widget, int stretch = 0)
```

该_widget_说法有它的所有权转移给Qt的。

插入给定_widget_在给定的_index_这个状态栏，重定父级的小工具，如果它已经不这样子[QStatusBar](qstatusbar.html)对象。如果_index_超出范围，小部件被追加（在这种情况下它是返回的widget的实际索引） 。

该_stretch_参数被用来计算一个合适的尺寸对于给定的_widget_作为状态栏的增长和收缩。默认拉伸系数为0，即给插件最小的空间。

窗口小部件是位于最左侧的第一个永久部件（见[addPermanentWidget](qstatusbar.html#addPermanentWidget)（）） ，并且可以通过临时的消息遮蔽。

这个函数中引入了Qt 4.2中。

**See also** [addWidget](qstatusbar.html#addWidget)（ ）[removeWidget](qstatusbar.html#removeWidget)（）和[addPermanentWidget](qstatusbar.html#addPermanentWidget)（ ） 。

```
bool QStatusBar.isSizeGripEnabled (self)
```

```
QStatusBar.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

示出了临时消息，如果合适，响应于所述涂料_event_。

```
QStatusBar.reformat (self)
```

改变状态栏的外观佔项目变更。

特殊的子类可能需要该功能，但几何管理通常会采取任何必要重排的照顾。

```
QStatusBar.removeWidget (self, QWidget widget)
```

删除指定的_widget_从状态栏。

**Note:**此功能不会删除该组件，但是_hides_它。再次添加窗口小部件，你必须调用两个[addWidget](qstatusbar.html#addWidget)（）和[show](qwidget.html#show)（）函数。

**See also** [addWidget](qstatusbar.html#addWidget)（ ）[addPermanentWidget](qstatusbar.html#addPermanentWidget)（）和[clearMessage](qstatusbar.html#clearMessage)（ ） 。

```
QStatusBar.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QStatusBar.setSizeGripEnabled (self, bool)
```

```
QStatusBar.showEvent (self, QShowEvent)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QStatusBar.showMessage (self, QString message, int msecs = 0)
```

这种方法也是一个Qt槽与C + +的签名`void showMessage(const QString&,int = 0)`。

隐藏在正常状态指示，并显示给定的_message_为毫秒（指定数目_timeout_） 。如果_timeout_为0 （默认），_message_保持显示，直到[clearMessage](qstatusbar.html#clearMessage)（ ）槽被调用，或者直到showMessage （）槽被再次调用来更改消息。

需要注意的是showMessage （ ）被调用，以显示工具提示文本的临时解释，所以传递_timeout_0不足以显示[permanent message](qstatusbar.html#permanent-message)。

**See also** [messageChanged](qstatusbar.html#messageChanged)（ ）[currentMessage](qstatusbar.html#currentMessage)（）和[clearMessage](qstatusbar.html#clearMessage)（ ） 。

* * *

## Qt Signal Documentation

```
void messageChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的临时状态信息变化。新的临时消息传递的_message_参数是一个空字符串时，该消息已被删除。

**See also** [showMessage](qstatusbar.html#showMessage)（）和[clearMessage](qstatusbar.html#clearMessage)（ ） 。