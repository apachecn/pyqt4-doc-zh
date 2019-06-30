# QAbstractMessageHandler Class Reference

## [[QtXmlPatterns](index.htm) module]

该QAbstractMessageHandler类提供用于处理消息的回调接口。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `handleMessage (self, QtMsgType type, QString description, QUrl identifier, QSourceLocation sourceLocation)`
*   `message (self, QtMsgType type, QString description, QUrl identifier = QUrl(), QSourceLocation sourceLocation = QSourceLocation())`

* * *

## Detailed Description

该QAbstractMessageHandler类提供用于处理消息的回调接口。

QAbstractMessageHandler是提供用于处理消息的回调接口的抽象基类。例如，类[QXmlQuery](qxmlquery.html)分析和运行的[XQuery](index.htm)。当它检测到一个编译或运行时错误，它会生成一个相应的错误信息，而不是输出消息本身，它传递的消息到[message](qabstractmessagehandler.html#message)（ ）函数将其QAbstractMessageHandler的。看[QXmlQuery.setMessageHandler](qxmlquery.html#setMessageHandler)（ ） 。

你通过继承QAbstractMessageHandler和实施创建消息处理程序[handleMessage](qabstractmessagehandler.html#handleMessage)（ ） 。然后，将指针传递给你的子类的实例必须生成消息的任何类。该消息通过发送到消息处理程序[message](qabstractmessagehandler.html#message)（ ）函数，该函数将它们转发给你的handleMessge （ ） 。其效果是序列化的所有消息的处理，这意味着你的QAbstractMessageHandler子类是线程安全的。

QAbstractMessageHandler的单个实例可以被调用来处理来自多个来源的消息。因此，消息的内容，它是_description_传递给参数[message](qabstractmessagehandler.html#message)（）和[handleMessage](qabstractmessagehandler.html#handleMessage)（ ） ，必须解释在光需要发送消息的上下文。这种情况下被指定的_identifier_和_sourceLocation_参数[message](qabstractmessagehandler.html#message)（ ）[handleMessage](qabstractmessagehandler.html#handleMessage)（ ） 。

* * *

## Method Documentation

```
QAbstractMessageHandler.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QAbstractMessageHandler](qabstractmessagehandler.html)。该_parent_被传递到[QObject](qobject.html)基类的构造函数。

```
QAbstractMessageHandler.handleMessage (self, QtMsgType type, QString description, QUrl identifier, QSourceLocation sourceLocation)
```

这种方法是抽象的，应在任何子类中重新实现。

这个功能必须由子类来实现。[message](qabstractmessagehandler.html#message)（ ）会调用这个函数，传入的参数，_type_，_description_，_identifier_和_sourceLocation_未修改。

```
QAbstractMessageHandler.message (self, QtMsgType type, QString description, QUrl identifier = QUrl(), QSourceLocation sourceLocation = QSourceLocation())
```

将消息发送到这个消息处理程序。_type_正在发送消息的种类。_description_是消息的内容。该_identifier_是标识的消息，是关键解释其他参数的URI 。

通常情况下，这个类是用于报告错误，是这样[QXmlQuery](qxmlquery.html)，它采用了[QAbstractMessageHandler](qabstractmessagehandler.html)报告编译和运行时[XQuery](index.htm)错误。因此，使用一个[QUrl](qurl.html)作为消息_identifier_IS的灵感来自于的解释[error handling in the XQuery language](http://www.w3.org/TR/xquery/#errors)。因为_identifier_是由一个命名空间URI和本地部分，标识符具有相同本地部分是唯一的。来电者是负责确保_identifier_是一个有效的[QUrl](qurl.html)或默认构造[QUrl](qurl.html)。

_sourceLocation_在一个资源（即，文件或文件）中检测是否需要报告一个消息，其中，识别一个位置。

这个函数直接调用[handleMessage](qabstractmessagehandler.html#handleMessage)（ ） ，传递其所有参数不变。

**See also** [http://www.w3.org/TR/xquery/#errors](http://www.w3.org/TR/xquery/#errors)。