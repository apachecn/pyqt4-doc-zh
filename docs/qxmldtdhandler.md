# QXmlDTDHandler Class Reference

## [[QtXml](index.htm) module]

该QXmlDTDHandler类提供了一个接口来报告XML数据的DTD内容。[More...](#details)

通过继承[QXmlDefaultHandler](qxmldefaulthandler.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlDTDHandler)`
*   `QString errorString (self)`
*   `bool notationDecl (self, QString name, QString publicId, QString systemId)`
*   `bool unparsedEntityDecl (self, QString name, QString publicId, QString systemId, QString notationName)`

* * *

## Detailed Description

该QXmlDTDHandler类提供了一个接口来报告XML数据的DTD内容。

如果应用程序需要大约符号和未解析实体的信息，它可以实现此接口，并与注册实例[QXmlReader.setDTDHandler](qxmlreader.html#setDTDHandler)（ ） 。

请注意，此界面包括只使用那些事件的DTD的XML建议要求处理器汇报，即符号和未解析的实体声明[notationDecl](qxmldtdhandler.html#notationDecl)（）和[unparsedEntityDecl](qxmldtdhandler.html#unparsedEntityDecl)（ ）分别。

* * *

## Method Documentation

```
QXmlDTDHandler.__init__ (self)
```

```
QXmlDTDHandler.__init__ (self, QXmlDTDHandler)
```

```
QString QXmlDTDHandler.errorString (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来得到一个错误字符串，如果任何的处理函数返回False 。

```
bool QXmlDTDHandler.notationDecl (self, QString name, QString publicId, QString systemId)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用该函数时，它已解析的符号声明。

这个论点_name_是符号名称，_publicId_是符号的公共标识符和_systemId_是符号的系统标识符。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmldtdhandler.html#errorString)（ ）来获得错误信息。

```
bool QXmlDTDHandler.unparsedEntityDecl (self, QString name, QString publicId, QString systemId, QString notationName)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用该函数时，它发现了一个未解析的实体声明。

这个论点_name_是未解析实体的名称，_publicId_是实体的公共标识符，_systemId_是实体的系统标识符和_notationName_是关联的符号的名称。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmldtdhandler.html#errorString)（ ）来获得错误信息。