# QCommandLinkButton Class Reference

## [[QtGui](index.htm) module]

该QCommandLinkButton小工具提供了Vista的风格命令链接按钮。[More...](#details)

继承[QPushButton](qpushbutton.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QString text, QWidget parent = None)`
*   `__init__ (self, QString text, QString description, QWidget parent = None)`
*   `QString description (self)`
*   `bool event (self, QEvent e)`
*   `int heightForWidth (self, int)`
*   `QSize minimumSizeHint (self)`
*   `paintEvent (self, QPaintEvent)`
*   `setDescription (self, QString description)`
*   `QSize sizeHint (self)`

* * *

## Detailed Description

该QCommandLinkButton小工具提供了Vista的风格命令链接按钮。

命令链接是由Windows Vista中引入了一个新的控制。它的用途是类似于一个单选按钮的，因为它是用于一组相互排斥的选项之间进行选择的。命令链接按钮不应该使用本身，而是作为一种替代的向导和对话框单选按钮，使按下“下一步”按钮多馀的。外观通常类似于一个扁平按钮的，但是它允许在除了正常的按钮上的文字的描述性文本。默认情况下，它也将携带一个箭头图标，表明按下控制将打开另一个窗口或页面。

* * *

## Method Documentation

```
QCommandLinkButton.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造不带文本和命令链接_parent_。

```
QCommandLinkButton.__init__ (self, QString text, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造与父命令链接_parent_和文本_text_。

```
QCommandLinkButton.__init__ (self, QString text, QString description, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个命令链接_text_，一_description_和_parent_。

```
QString QCommandLinkButton.description (self)
```

```
bool QCommandLinkButton.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QCommandLinkButton.heightForWidth (self, int)
```

从重新实现[QWidget.heightForWidth](qwidget.html#heightForWidth)（ ） 。

```
QSize QCommandLinkButton.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QCommandLinkButton.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QCommandLinkButton.setDescription (self, QString description)
```

```
QSize QCommandLinkButton.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。