# QXmlLocator Class Reference

## [[QtXml](index.htm) module]

该QXmlLocator类提供的XML处理类约在一个文件中解析位置信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlLocator)`
*   `int columnNumber (self)`
*   `int lineNumber (self)`

* * *

## Detailed Description

该QXmlLocator类提供的XML处理类约在一个文件中解析位置信息。

读者报告一个QXmlLocator的内容处理程序才开始解析文档。这是与完成[QXmlContentHandler.setDocumentLocator](qxmlcontenthandler.html#setDocumentLocator)（）函数。处理程序类现在可以使用这个定位器来获取位置（[lineNumber](qxmllocator.html#lineNumber)（）和[columnNumber](qxmllocator.html#columnNumber)（ ） ） ，读者已经达到了。

* * *

## Method Documentation

```
QXmlLocator.__init__ (self)
```

构造函数。

```
QXmlLocator.__init__ (self, QXmlLocator)
```

```
int QXmlLocator.columnNumber (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的列号（从1开始）或-1，如果没有可用的列数。

```
int QXmlLocator.lineNumber (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的行数（从1开始）或-1，如果没有可用的行号。