# QXmlEntityResolver Class Reference

## [[QtXml](index.htm) module]

该QXmlEntityResolver类提供解决包含在XML数据的外部实体的接口。[More...](#details)

通过继承[QXmlDefaultHandler](qxmldefaulthandler.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlEntityResolver)`
*   `QString errorString (self)`
*   `(bool, QXmlInputSource ret) resolveEntity (self, QString publicId, QString systemId)`

* * *

## Detailed Description

该QXmlEntityResolver类提供解决包含在XML数据的外部实体的接口。

如果一个应用程序需要实现自定义处理外部实体，它必须实现这个接口，即[resolveEntity](qxmlentityresolver.html#resolveEntity)（ ） ，并用它注册[QXmlReader.setEntityResolver](qxmlreader.html#setEntityResolver)（ ） 。

* * *

## Method Documentation

```
QXmlEntityResolver.__init__ (self)
```

```
QXmlEntityResolver.__init__ (self, QXmlEntityResolver)
```

```
QString QXmlEntityResolver.errorString (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来得到一个错误字符串，如果任何的处理函数返回False 。

```
(bool, QXmlInputSource ret) QXmlEntityResolver.resolveEntity (self, QString publicId, QString systemId)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数之前，它打开任何外部实体，除了顶级文档实体。该应用程序可能会要求读者解决实体本身（_ret_是0） ，或使用完全不同的输入源（_ret_指向输入源） 。

读者会删除输入源_ret_当它不再需要它，所以你应该为它分配在堆上用`new`。

这个论点_publicId_是外部实体的公共标识符，_systemId_为外部实体的系统标识符和_ret_是这个函数的返回值。如果_ret_为0时，读者应该解决实体本身，如果是非零它必须指向该阅读器使用，而不是一个输入源。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlentityresolver.html#errorString)（ ）来获得错误信息。