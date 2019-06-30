# QXmlDeclHandler Class Reference

## [[QtXml](index.htm) module]

该QXmlDeclHandler类提供了一个接口来报告XML数据的声明内容。[More...](#details)

通过继承[QXmlDefaultHandler](qxmldefaulthandler.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlDeclHandler)`
*   `bool attributeDecl (self, QString eName, QString aName, QString type, QString valueDefault, QString value)`
*   `QString errorString (self)`
*   `bool externalEntityDecl (self, QString name, QString publicId, QString systemId)`
*   `bool internalEntityDecl (self, QString name, QString value)`

* * *

## Detailed Description

该QXmlDeclHandler类提供了一个接口来报告XML数据的声明内容。

您可以设置申报处理程序[QXmlReader.setDeclHandler](qxmlreader.html#setDeclHandler)（ ） 。

该接口是基于SAX2扩展DeclHandler 。

该接口提供[attributeDecl](qxmldeclhandler.html#attributeDecl)（ ）[internalEntityDecl](qxmldeclhandler.html#internalEntityDecl)（）和[externalEntityDecl](qxmldeclhandler.html#externalEntityDecl)（）函数。

* * *

## Method Documentation

```
QXmlDeclHandler.__init__ (self)
```

```
QXmlDeclHandler.__init__ (self, QXmlDeclHandler)
```

```
bool QXmlDeclHandler.attributeDecl (self, QString eName, QString aName, QString type, QString valueDefault, QString value)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告属性类型声明。只有有效的（第一个）声明一个属性的报导。

读者通过在相关元素的名称_eName_并在该属性的名称_aName_。它通过它表示该属性类型的字符串_type_并表示在该属性的默认字符串_valueDefault_。这个字符串是“ ＃IMPLIED ”之一，“ ＃REQUIRED ” ， “ ＃ FIXED”或空字符串（如果没有其他的应用） 。读者通过在该属性的默认值_value_。如果XML文件中没有指定默认值，_value_是一个空字符串。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmldeclhandler.html#errorString)（ ）来获得错误信息。

```
QString QXmlDeclHandler.errorString (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来得到一个错误字符串，如果任何的处理函数返回False 。

```
bool QXmlDeclHandler.externalEntityDecl (self, QString name, QString publicId, QString systemId)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告解析外部实体声明。只有有效的（第一个）声明为每个实体的报导。

读者通过在实体的名称_name_在公共标识符_publicId_和在系统中的标识符_systemId_。如果没有指定公共标识符，它传递一个空字符串_publicId_。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmldeclhandler.html#errorString)（ ）来获得错误信息。

```
bool QXmlDeclHandler.internalEntityDecl (self, QString name, QString value)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告内部实体声明。只有有效的（第一个）的声明报导。

读者通过在实体的名称_name_而在实体的值_value_。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmldeclhandler.html#errorString)（ ）来获得错误信息。