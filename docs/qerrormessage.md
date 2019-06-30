# QErrorMessage Class Reference

## [[QtGui](index.htm) module]

该QErrorMessage类提供​​一个错误信息显示对话框。[More...](#details)

继承[QDialog](qdialog.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `changeEvent (self, QEvent e)`
*   `done (self, int)`
*   `showMessage (self, QString message)`
*   `showMessage (self, QString message, QString type)`

### Static Methods

*   `QErrorMessage qtHandler ()`

* * *

## Detailed Description

该QErrorMessage类提供​​一个错误信息显示对话框。

一个错误信息窗口小部件由一个文本标籤和一个复选框。该复选框允许用户控制是否相同的错误消息会在未来再次显示出来，通常显示文本“，再次显示此消息”翻译成当地合适的语言。

在生产应用中，类可以用来显示所述用户只需要看到一次的消息。使用QErrorMessage这样，你通常的方式创建对话框，并通过调用显示它的[showMessage](qerrormessage.html#showMessage)（）槽或连接信号给它。

静[qtHandler](qerrormessage.html#qtHandler)（ ）函数安装使用消息处理程序[qInstallMsgHandler](index.htm#qInstallMsgHandler)（ ）并创建一个QErrorMessage的显示器[qDebug](index.htm#qDebug)（ ）[qWarning](index.htm#qWarning)（）和[qFatal](index.htm#qFatal)（ ）消息。这是最有用的环境中没有控制台可以显示警告和错误消息。

在这两种情况下QErrorMessage将伫列中等待消息，并为了显示他们，只要用户已经接受以前的消息被显示的每个新的消息。一旦用户指定的消息不被再次显示它会自动跳过，并且对话框将显示在队列中的下一个相应的消息。

该[Standard Dialogs](index.htm)示例显示了如何使用QErrorMessage以及其他内置Qt对话框。

![](../img/qerrormessage.png)

* * *

## Method Documentation

```
QErrorMessage.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造并用给定的安装错误处理程序窗口_parent_。

```
QErrorMessage.changeEvent (self, QEvent e)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QErrorMessage.done (self, int)
```

从重新实现[QDialog.done](qdialog.html#done)（ ） 。

```
QErrorMessage QErrorMessage.qtHandler ()
```

[](qerrormessage.html)

[返回一个指针，指向一个](qerrormessage.html)[QErrorMessage](qerrormessage.html)对象，其输出的默认Qt的消息。该函数创建这样一个对象，如果没有一个已。

```
QErrorMessage.showMessage (self, QString message)
```

这种方法也是一个Qt槽与C + +的签名`void showMessage(const QString&)`。

显示给定的消息，_message_，并立即返回。如果用户请求的消息不被再次显示，该函数不起作用。

通常情况下，会立即显示该消息。然而，如果存在挂起的消息，它将被排队在后面显示。

```
QErrorMessage.showMessage (self, QString message, QString type)
```

这种方法也是一个Qt槽与C + +的签名`void showMessage(const QString&,const QString&)`。

这是一个重载函数。

显示给定的消息，_message_，并立即返回。如果用户已经请求类型的消息_type_，不被再次显示，该函数不起作用。

通常情况下，会立即显示该消息。然而，如果存在挂起的消息，它将被排队在后面显示。

此功能被引入Qt的4.5 。

**See also** [showMessage](qerrormessage.html#showMessage)（ ） 。