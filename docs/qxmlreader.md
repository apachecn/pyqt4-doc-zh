# QXmlReader Class Reference

## [[QtXml](index.htm) module]

该QXmlReader类提供对XML的读者（即解析器）的接口。[More...](#details)

通过继承[QXmlSimpleReader](qxmlsimplereader.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlReader)`
*   `QXmlContentHandler contentHandler (self)`
*   `QXmlDeclHandler declHandler (self)`
*   `QXmlDTDHandler DTDHandler (self)`
*   `QXmlEntityResolver entityResolver (self)`
*   `QXmlErrorHandler errorHandler (self)`
*   `(bool, bool ok) feature (self, QString name)`
*   `bool hasFeature (self, QString name)`
*   `bool hasProperty (self, QString name)`
*   `QXmlLexicalHandler lexicalHandler (self)`
*   `bool parse (self, QXmlInputSource input)`
*   `bool parse (self, QXmlInputSource input)`
*   `(sip.voidptr, bool ok) property (self, QString name)`
*   `setContentHandler (self, QXmlContentHandler handler)`
*   `setDeclHandler (self, QXmlDeclHandler handler)`
*   `setDTDHandler (self, QXmlDTDHandler handler)`
*   `setEntityResolver (self, QXmlEntityResolver handler)`
*   `setErrorHandler (self, QXmlErrorHandler handler)`
*   `setFeature (self, QString name, bool value)`
*   `setLexicalHandler (self, QXmlLexicalHandler handler)`
*   `setProperty (self, QString name, sip.voidptr value)`

* * *

## Detailed Description

该QXmlReader类提供对XML的读者（即解析器）的接口。

这个抽象类提供了所有Qt的XML读取器的接口。目前只有一个执行包括在Qt的XML模块的读取器的：[QXmlSimpleReader](qxmlsimplereader.html)。在未来的版本中可能会有更多的读者提供（例如验证解析器）不同的属性。

XML类的设计遵循[SAX2 Java interface](http://www.saxproject.org/)，与调整以适应Qt的命名约定的名称。这应该是很容易的人谁曾与SAX2合作，开始使用Qt的XML类。

所有读者使用类[QXmlInputSource](qxmlinputsource.html)读取输入文档。既然你是在XML文档中的特定内容通常兴趣，读者通过特别的处理类（报告内容[QXmlDTDHandler](qxmldtdhandler.html)，[QXmlDeclHandler](qxmldeclhandler.html)，[QXmlContentHandler](qxmlcontenthandler.html)，[QXmlEntityResolver](qxmlentityresolver.html)，[QXmlErrorHandler](qxmlerrorhandler.html)和[QXmlLexicalHandler](qxmllexicalhandler.html)），您必须继承，如果你要处理的内容。

由于处理程序类只描述接口，你必须实现所有的功能。我们所提供的[QXmlDefaultHandler](qxmldefaulthandler.html)类来简化这一过程：它实现了一个默认的行为（做什么）的所有功能，所以你可以继承它，只是实现您感兴趣的功能

功能和读取器的性能可与设置[setFeature](qxmlreader.html#setFeature)（）和[setProperty](qxmlreader.html#setProperty)（ ）分别。您可以设置读卡器使用自己的子类与[setEntityResolver](qxmlreader.html#setEntityResolver)（ ）[setDTDHandler](qxmlreader.html#setDTDHandler)（ ）[setContentHandler](qxmlreader.html#setContentHandler)（ ）[setErrorHandler](qxmlreader.html#setErrorHandler)（ ）[setLexicalHandler](qxmlreader.html#setLexicalHandler)（）和[setDeclHandler](qxmlreader.html#setDeclHandler)（ ） 。解析本身开始调用[parse](qxmlreader.html#parse)（ ） 。

* * *

## Method Documentation

```
QXmlReader.__init__ (self)
```

```
QXmlReader.__init__ (self, QXmlReader)
```

```
QXmlContentHandler QXmlReader.contentHandler (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回内容处理程序或0，如果没有被设置。

](qxmlcontenthandler.html)

[**See also**](qxmlcontenthandler.html) [setContentHandler](qxmlreader.html#setContentHandler)（ ） 。

```
QXmlDeclHandler QXmlReader.declHandler (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回声明的处理程序或0，如果没有被设置。

](qxmldeclhandler.html)

[**See also**](qxmldeclhandler.html) [setDeclHandler](qxmlreader.html#setDeclHandler)（ ） 。

```
QXmlDTDHandler QXmlReader.DTDHandler (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回DTD处理程序或0，如果没有被设置。

](qxmldtdhandler.html)

[**See also**](qxmldtdhandler.html) [setDTDHandler](qxmlreader.html#setDTDHandler)（ ） 。

```
QXmlEntityResolver QXmlReader.entityResolver (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回实体解析器或0，如果没有被设置。

](qxmlentityresolver.html)

[**See also**](qxmlentityresolver.html) [setEntityResolver](qxmlreader.html#setEntityResolver)（ ） 。

```
QXmlErrorHandler QXmlReader.errorHandler (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回的错误处理程序或0 ，如果没有被设置。

](qxmlerrorhandler.html)

[**See also**](qxmlerrorhandler.html) [setErrorHandler](qxmlreader.html#setErrorHandler)（ ） 。

```
(bool, bool ok) QXmlReader.feature (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

如果读者有所谓的功能_name_，则返回功能的值。如果不存在此类功能的返回值是不确定的。

If _ok_不为0时：`*`_ok_被设置为True，如果读者有所谓的功能_name_否则`*`_ok_设置为False 。

**See also** [setFeature](qxmlreader.html#setFeature)（）和[hasFeature](qxmlreader.html#hasFeature)（ ） 。

```
bool QXmlReader.hasFeature (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

Returns `true`如果读者有所谓的功能_name_否则返回False 。

**See also** [feature](qxmlreader.html#feature)（）和[setFeature](qxmlreader.html#setFeature)（ ） 。

```
bool QXmlReader.hasProperty (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

如果读者有属性，则返回True_name_否则返回False 。

**See also** [property](qxmlreader.html#property)（）和[setProperty](qxmlreader.html#setProperty)（ ） 。

```
QXmlLexicalHandler QXmlReader.lexicalHandler (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回词法处理程序或0，如果没有被设置。

](qxmllexicalhandler.html)

[**See also**](qxmllexicalhandler.html) [setLexicalHandler](qxmlreader.html#setLexicalHandler)（ ） 。

```
bool QXmlReader.parse (self, QXmlInputSource input)
```

这种方法是抽象的，应在任何子类中重新实现。

读取从XML文档_input_并解析它。返回True如果解析成功，否则返回False 。

```
bool QXmlReader.parse (self, QXmlInputSource input)
```

这种方法是抽象的，应在任何子类中重新实现。

```
(sip.voidptr, bool ok) QXmlReader.property (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

如果读者有物业_name_，这个函数返回的属性的值，否则返回值是不确定的。

If _ok_不为0 ：如果读者有_name_属性`*`_ok_设置为True ，否则`*`_ok_设置为False 。

**See also** [setProperty](qxmlreader.html#setProperty)（）和[hasProperty](qxmlreader.html#hasProperty)（ ） 。

```
QXmlReader.setContentHandler (self, QXmlContentHandler handler)
```

这种方法是抽象的，应在任何子类中重新实现。

设置内容处理器_handler_。

**See also** [contentHandler](qxmlreader.html#contentHandler)（ ） 。

```
QXmlReader.setDeclHandler (self, QXmlDeclHandler handler)
```

这种方法是抽象的，应在任何子类中重新实现。

设置申报处理程序_handler_。

**See also** [declHandler](qxmlreader.html#declHandler)（ ） 。

```
QXmlReader.setDTDHandler (self, QXmlDTDHandler handler)
```

这种方法是抽象的，应在任何子类中重新实现。

设置DTD处理程序_handler_。

**See also** [DTDHandler](qxmlreader.html#DTDHandler)（ ） 。

```
QXmlReader.setEntityResolver (self, QXmlEntityResolver handler)
```

这种方法是抽象的，应在任何子类中重新实现。

设置实体解析器_handler_。

**See also** [entityResolver](qxmlreader.html#entityResolver)（ ） 。

```
QXmlReader.setErrorHandler (self, QXmlErrorHandler handler)
```

这种方法是抽象的，应在任何子类中重新实现。

设置错误处理程序_handler_。清除错误处理程序，如果_handler_为0。

**See also** [errorHandler](qxmlreader.html#errorHandler)（ ） 。

```
QXmlReader.setFeature (self, QString name, bool value)
```

这种方法是抽象的，应在任何子类中重新实现。

设置所谓的功能_name_为给定的_value_。如果读者不具备该功能没有任何反应。

**See also** [feature](qxmlreader.html#feature)（）和[hasFeature](qxmlreader.html#hasFeature)（ ） 。

```
QXmlReader.setLexicalHandler (self, QXmlLexicalHandler handler)
```

这种方法是抽象的，应在任何子类中重新实现。

设置词法处理程序_handler_。

**See also** [lexicalHandler](qxmlreader.html#lexicalHandler)（ ） 。

```
QXmlReader.setProperty (self, QString name, sip.voidptr value)
```

这种方法是抽象的，应在任何子类中重新实现。

设置属性_name_至_value_。如果读者不具备的属性没有任何反应。

**See also** [property](qxmlreader.html#property)（）和[hasProperty](qxmlreader.html#hasProperty)（ ） 。