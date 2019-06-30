# QXmlErrorHandler Class Reference

## [[QtXml](index.htm) module]

该QXmlErrorHandler类提供了一个接口来报告在XML中的数据错误。[More...](#details)

通过继承[QXmlDefaultHandler](qxmldefaulthandler.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlErrorHandler)`
*   `bool error (self, QXmlParseException exception)`
*   `QString errorString (self)`
*   `bool fatalError (self, QXmlParseException exception)`
*   `bool warning (self, QXmlParseException exception)`

* * *

## Detailed Description

该QXmlErrorHandler类提供了一个接口来报告在XML中的数据错误。

如果你希望你的应用程序错误报告给用户或执行自定义的错误处理，你应该继承这个类。

您可以设置错误处理程序[QXmlReader.setErrorHandler](qxmlreader.html#setErrorHandler)（ ） 。

错误可以使用报告[warning](qxmlerrorhandler.html#warning)（ ）[error](qxmlerrorhandler.html#error)（）和[fatalError](qxmlerrorhandler.html#fatalError)（ ） ，与错误的文字被报导与[errorString](qxmlerrorhandler.html#errorString)（ ） 。

* * *

## Method Documentation

```
QXmlErrorHandler.__init__ (self)
```

```
QXmlErrorHandler.__init__ (self, QXmlErrorHandler)
```

```
bool QXmlErrorHandler.error (self, QXmlParseException exception)
```

这种方法是抽象的，应在任何子类中重新实现。

读者可能使用此功能来报告一个可恢复的错误。可恢复的错误对应于“错误”的XML 1.0规范的第1.2节的definiton 。错误的详细信息存储在_exception_。

读者必须继续调用此函数后提供正常的解析事件。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlerrorhandler.html#errorString)（ ）来获得错误信息。

```
QString QXmlErrorHandler.errorString (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来得到一个错误字符串，如果任何的处理函数返回False 。

```
bool QXmlErrorHandler.fatalError (self, QXmlParseException exception)
```

这种方法是抽象的，应在任何子类中重新实现。

一位读者必须使用此功能来报告一个不可恢复的错误。错误的详细信息存储在_exception_。

如果这个函数返回True，读者可能会试图去解析和报告进一步的错误，但没有正规的解析事件的报告。

```
bool QXmlErrorHandler.warning (self, QXmlParseException exception)
```

这种方法是抽象的，应在任何子类中重新实现。

读者可以使用此功能来报告一个警告。警告是由XML 1.0规范定义不属于错误或致命错误条件。该警告的详细信息存储在_exception_。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlerrorhandler.html#errorString)（ ）来获得错误信息。