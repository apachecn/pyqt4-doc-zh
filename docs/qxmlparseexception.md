# QXmlParseException Class Reference

## [[QtXml](index.htm) module]

该QXmlParseException类用于报告的错误[QXmlErrorHandler](qxmlerrorhandler.html)接口。[More...](#details)

### Methods

*   `__init__ (self, QString name = QString(), int column = -1, int line = -1, QString publicId = QString(), QString systemId = QString())`
*   `__init__ (self, QXmlParseException other)`
*   `int columnNumber (self)`
*   `int lineNumber (self)`
*   `QString message (self)`
*   `QString publicId (self)`
*   `QString systemId (self)`

* * *

## Detailed Description

该QXmlParseException类用于报告的错误[QXmlErrorHandler](qxmlerrorhandler.html)接口。

在XML子系统构建在检测到错误时，这个类的一个实例。你可以检索到错误的使用发生的地方[systemId](qxmlparseexception.html#systemId)（ ）[publicId](qxmlparseexception.html#publicId)（ ）[lineNumber](qxmlparseexception.html#lineNumber)（）和[columnNumber](qxmlparseexception.html#columnNumber)（） ，以及错误[message](qxmlparseexception.html#message)（ ） 。可能的错误消息：

*   "no error occurred"
*   "error triggered by consumer"
*   "unexpected end of file"
*   "more than one document type definition"
*   "error occurred while parsing element"
*   "tag mismatch"
*   "error occurred while parsing content"
*   "unexpected character"
*   "invalid name for processing instruction"
*   "version expected while reading the XML declaration"
*   "wrong value for standalone declaration"
*   "encoding declaration or standalone declaration expected while reading the XML declaration"
*   "standalone declaration expected while reading the XML declaration"
*   "error occurred while parsing document type definition"
*   "letter is expected"
*   "error occurred while parsing comment"
*   "error occurred while parsing reference"
*   "internal general entity reference not allowed in DTD"
*   "external parsed general entity reference not allowed in attribute value"
*   "external parsed general entity reference not allowed in DTD"
*   "unparsed entity reference n wrong context"
*   "recursive entities"
*   "error in the text declaration of an external entity"

需要注意的是，如果你想显示这些错误信息到您的应用程序的用户，他们将，除非他们明确地翻译英文显示。

* * *

## Method Documentation

```
QXmlParseException.__init__ (self, QString name = QString(), int column = -1, int line = -1, QString publicId = QString(), QString systemId = QString())
```

与错误字符串构造一个解析异常_name_列_c_和行_l_对于公共标识符_p_和系统标识符_s_。

```
QXmlParseException.__init__ (self, QXmlParseException other)
```

创建副本_other_。

```
int QXmlParseException.columnNumber (self)
```

返回发生错误的位置的列号。

```
int QXmlParseException.lineNumber (self)
```

返回发生错误的行号。

```
QString QXmlParseException.message (self)
```

返回该错误消息。

```
QString QXmlParseException.publicId (self)
```

返回发生错误的公共标识。

```
QString QXmlParseException.systemId (self)
```

返回发生错误的位置的系统标识符。