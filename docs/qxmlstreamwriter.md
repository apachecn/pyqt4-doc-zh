# QXmlStreamWriter Class Reference

## [[QtCore](index.htm) module]

该QXmlStreamWriter类提供了一个XML编写一个简单的流API 。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice device)`
*   `__init__ (self, QByteArray array)`
*   `__init__ (self, QString string)`
*   `bool autoFormatting (self)`
*   `int autoFormattingIndent (self)`
*   `QTextCodec codec (self)`
*   `QIODevice device (self)`
*   `bool hasError (self)`
*   `setAutoFormatting (self, bool)`
*   `setAutoFormattingIndent (self, int spaces)`
*   `setCodec (self, QTextCodec codec)`
*   `setCodec (self, str codecName)`
*   `setDevice (self, QIODevice device)`
*   `writeAttribute (self, QString qualifiedName, QString value)`
*   `writeAttribute (self, QString namespaceUri, QString name, QString value)`
*   `writeAttribute (self, QXmlStreamAttribute attribute)`
*   `writeAttributes (self, QXmlStreamAttributes attributes)`
*   `writeCDATA (self, QString text)`
*   `writeCharacters (self, QString text)`
*   `writeComment (self, QString text)`
*   `writeCurrentToken (self, QXmlStreamReader reader)`
*   `writeDefaultNamespace (self, QString namespaceUri)`
*   `writeDTD (self, QString dtd)`
*   `writeEmptyElement (self, QString qualifiedName)`
*   `writeEmptyElement (self, QString namespaceUri, QString name)`
*   `writeEndDocument (self)`
*   `writeEndElement (self)`
*   `writeEntityReference (self, QString name)`
*   `writeNamespace (self, QString namespaceUri, QString prefix = QString())`
*   `writeProcessingInstruction (self, QString target, QString data = QString())`
*   `writeStartDocument (self)`
*   `writeStartDocument (self, QString version)`
*   `writeStartDocument (self, QString version, bool standalone)`
*   `writeStartElement (self, QString qualifiedName)`
*   `writeStartElement (self, QString namespaceUri, QString name)`
*   `writeTextElement (self, QString qualifiedName, QString text)`
*   `writeTextElement (self, QString namespaceUri, QString name, QString text)`

* * *

## Detailed Description

该QXmlStreamWriter类提供了一个XML编写一个简单的流API 。

QXmlStreamWriter是对口[QXmlStreamReader](qxmlstreamreader.html)用于编写XML 。像它的相关的类，它运行在一个[QIODevice](qiodevice.html)与指定[setDevice](qxmlstreamwriter.html#setDevice)（ ） 。该API是​​简单而直接：为每个XML标记或你想要写的事件，笔者提供了一个专门的功能。

开始时你有一个文件[writeStartDocument](qxmlstreamwriter.html#writeStartDocument)（ ）和结束它[writeEndDocument](qxmlstreamwriter.html#writeEndDocument)（ ） 。这将隐式关闭所有剩馀的开放标籤。

元素标记开[writeStartElement](qxmlstreamwriter.html#writeStartElement)（ ），随后[writeAttribute](qxmlstreamwriter.html#writeAttribute)（）或[writeAttributes](qxmlstreamwriter.html#writeAttributes)（） ，元素的内容，然后[writeEndElement](qxmlstreamwriter.html#writeEndElement)（ ） 。较短的形式[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ）可以用来写空元素，其次是[writeAttributes](qxmlstreamwriter.html#writeAttributes)（ ） 。

元素含量由两种字符，实体引用或嵌套元素。这是用[writeCharacters](qxmlstreamwriter.html#writeCharacters)（ ） ，这也需要转义禁止所有字符和字符序列的照顾，[writeEntityReference](qxmlstreamwriter.html#writeEntityReference)（ ） ，或后续调用[writeStartElement](qxmlstreamwriter.html#writeStartElement)（ ） 。一种简便方法[writeTextElement](qxmlstreamwriter.html#writeTextElement)（ ）可用于编写仅仅包含文本终端元素。

下面简略的代码片段显示了基本使用的类来写格式化的XML缩进：

```
     QXmlStreamWriter stream(&output);
     stream.setAutoFormatting(true);
     stream.writeStartDocument();
     ...
     stream.writeStartElement("bookmark");
     stream.writeAttribute("href", "http://qt.nokia.com/");
     stream.writeTextElement("title", "Qt Home");
     stream.writeEndElement(); // bookmark
     ...
     stream.writeEndDocument();

```

QXmlStreamWriter采用前缀命名空间的照顾，你需要做的就是指定`namespaceUri`写元素或属性的时候。如果您必须符合一定的前缀，你可以强制笔者通过手动声明的命名空间使用它们[writeNamespace](qxmlstreamwriter.html#writeNamespace)（）或[writeDefaultNamespace](qxmlstreamwriter.html#writeDefaultNamespace)（ ） 。或者，您可以绕过流作家的命名空间支持，并使用该采取一个合格的名称，而不是重载方法。命名空间_http://www.w3.org/XML/1998/namespace_是隐式映射到前缀_xml_。

流作家可以通过添加换行符和缩进到元素之间的空白部分，使XML数据的可读性更强的人类和更容易使用的大部分源代码管理系统自动格式化生成的XML数据。该功能可以被打开以[autoFormatting](qxmlstreamwriter.html#autoFormatting-prop)物业和定制与[autoFormattingIndent](qxmlstreamwriter.html#autoFormattingIndent-prop)属性。

其它功能[writeCDATA](qxmlstreamwriter.html#writeCDATA)（ ）[writeComment](qxmlstreamwriter.html#writeComment)（ ）[writeProcessingInstruction](qxmlstreamwriter.html#writeProcessingInstruction)（）和[writeDTD](qxmlstreamwriter.html#writeDTD)（ ） 。 XML流的链接时支持[writeCurrentToken](qxmlstreamwriter.html#writeCurrentToken)（ ） 。

默认情况下， QXmlStreamWriter XML编码为UTF -8 。不同的编码可以通过强制执行[setCodec](qxmlstreamwriter.html#setCodec)（ ） 。

如果在写入到底层设备发生错误，[hasError](qxmlstreamwriter.html#hasError)（ ）开始返回真和随后的写入被忽略。

该[QXmlStream Bookmarks Example](index.htm)说明如何使用流作家写一个XML书籤文件（ XBEL ） ，是由以前在读[QXmlStreamReader](qxmlstreamreader.html)。

* * *

## Method Documentation

```
QXmlStreamWriter.__init__ (self)
```

构造一个流作家。

**See also** [setDevice](qxmlstreamwriter.html#setDevice)（ ） 。

```
QXmlStreamWriter.__init__ (self, QIODevice device)
```

构造一个流作家写入到_device_;

```
QXmlStreamWriter.__init__ (self, QByteArray array)
```

构造一个流作家写入到_array_。这是一样的创建XML编写器运行在一个[QBuffer](qbuffer.html)装置，该装置反过来作用于_array_。

```
QXmlStreamWriter.__init__ (self, QString string)
```

构造一个流作家写入到_string_。

```
bool QXmlStreamWriter.autoFormatting (self)
```

```
int QXmlStreamWriter.autoFormattingIndent (self)
```

```
QTextCodec QXmlStreamWriter.codec (self)
```

[

返回当前分配给流的编解码器。

](qtextcodec.html)

[**See also**](qtextcodec.html) [setCodec](qxmlstreamwriter.html#setCodec)（ ） 。

```
QIODevice QXmlStreamWriter.device (self)
```

[](qiodevice.html)

[返回与关联的当前设备](qiodevice.html)[QXmlStreamWriter](qxmlstreamwriter.html)，或者0，如果没有设备已经被分配。

**See also** [setDevice](qxmlstreamwriter.html#setDevice)（ ） 。

```
bool QXmlStreamWriter.hasError (self)
```

返回True如果流无法写入到基础设备，否则返回False 。

错误状态永远不会复位。发生写入错误发生后会被忽略，即使错误条件被清除。

此功能被引入Qt的4.8 。

```
QXmlStreamWriter.setAutoFormatting (self, bool)
```

```
QXmlStreamWriter.setAutoFormattingIndent (self, int spaces)
```

```
QXmlStreamWriter.setCodec (self, QTextCodec codec)
```

设置编解码器，该流_codec_。编解码器是用于编码被写入任何数据。默认情况下，[QXmlStreamWriter](qxmlstreamwriter.html)使用UTF-8 。

该编码信息存储在其中，当你调用将会写入初始XML标记[writeStartDocument](qxmlstreamwriter.html#writeStartDocument)（ ） 。在调用之前调用此函数[writeStartDocument](qxmlstreamwriter.html#writeStartDocument)（ ） 。

**See also** [codec](qxmlstreamwriter.html#codec)（ ） 。

```
QXmlStreamWriter.setCodec (self, str codecName)
```

设置编解码器，该数据流的[QTextCodec](qtextcodec.html)对于由指定的编码_codecName_。为共同的价值观`codecName`包括“ ISO 8859 ”，“ UTF-8” ，和“UTF- 16” 。如果编码不被识别，没有任何反应。

**See also** [QTextCodec.codecForName](qtextcodec.html#codecForName)（ ） 。

```
QXmlStreamWriter.setDevice (self, QIODevice device)
```

设置当前设备_device_。如果你想流写入到一个[QByteArray](qbytearray.html)，你可以创建一个[QBuffer](qbuffer.html)设备。

**See also** [device](qxmlstreamwriter.html#device)（ ） 。

```
QXmlStreamWriter.writeAttribute (self, QString qualifiedName, QString value)
```

写与属性_name_和_value_，前缀为指定_namespaceUri_。如果命名空间还没有被宣布的是，[QXmlStreamWriter](qxmlstreamwriter.html)将生成一个命名空间声明它。

此功能后，才可以称为[writeStartElement](qxmlstreamwriter.html#writeStartElement)（ ）任何内容被写入之前，或之后[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ） 。

```
QXmlStreamWriter.writeAttribute (self, QString namespaceUri, QString name, QString value)
```

这是一个重载函数。

写与属性_qualifiedName_和_value_。

此功能后，才可以称为[writeStartElement](qxmlstreamwriter.html#writeStartElement)（ ）任何内容被写入之前，或之后[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ） 。

```
QXmlStreamWriter.writeAttribute (self, QXmlStreamAttribute attribute)
```

这是一个重载函数。

写_attribute_。

此功能后，才可以称为[writeStartElement](qxmlstreamwriter.html#writeStartElement)（ ）任何内容被写入之前，或之后[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ） 。

```
QXmlStreamWriter.writeAttributes (self, QXmlStreamAttributes attributes)
```

写入属性向量_attributes_。如果在属性中引用的命名空间没有被宣布的是，[QXmlStreamWriter](qxmlstreamwriter.html)将生成一个命名空间声明它。

此功能后，才可以称为[writeStartElement](qxmlstreamwriter.html#writeStartElement)（ ）任何内容被写入之前，或之后[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ） 。

**See also** [writeAttribute](qxmlstreamwriter.html#writeAttribute)（）和[writeNamespace](qxmlstreamwriter.html#writeNamespace)（ ） 。

```
QXmlStreamWriter.writeCDATA (self, QString text)
```

Writes _text_作为CDATA节。如果_text_包含禁止字符序列“ ]]\u003e ” ，它被分成不同的CDATA节。

此功能主要存在的完整性。通常你应该不需要使用它，因为[writeCharacters](qxmlstreamwriter.html#writeCharacters)（ ）自动转义所有非内容的字符。

```
QXmlStreamWriter.writeCharacters (self, QString text)
```

Writes _text_。字符“ \u003c ” ， “＆ ”和“ ” “被转义为实体引用”\u003c“ ， ”＆ ，和“”“ 。为了避免禁止序列“ ]]\u003e ” ， “ \u003e ”也转义为“ \u003e ” 。

**See also** [writeEntityReference](qxmlstreamwriter.html#writeEntityReference)（ ） 。

```
QXmlStreamWriter.writeComment (self, QString text)
```

Writes _text_作为XML注释，其中_text_不得含有禁序列“ - ”或终结“ - ” 。在注释 - 请注意， XML不提供任何方式来逃避“ ” 。

```
QXmlStreamWriter.writeCurrentToken (self, QXmlStreamReader reader)
```

写入的当前状态_reader_。所有可能的有效状态的支持。

此功能的目的是为了支持XML数据的链接的处理。

**See also** [QXmlStreamReader.tokenType](qxmlstreamreader.html#tokenType)（ ） 。

```
QXmlStreamWriter.writeDefaultNamespace (self, QString namespaceUri)
```

写一个默认的命名空间声明_namespaceUri_。

If [writeStartElement](qxmlstreamwriter.html#writeStartElement)（）或[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ）被调用，该声明适用于当前元素，否则它适用于下一个子元素。

请注意，命名空间_http://www.w3.org/XML/1998/namespace_（绑定到_xmlns_）和_http://www.w3.org/2000/xmlns/_（绑定到_xml_）由定义不能被声明为默认值。

```
QXmlStreamWriter.writeDTD (self, QString dtd)
```

写一个DTD部分。该_dtd_表示从XML 1.0规范整个doctypedecl产品。

```
QXmlStreamWriter.writeEmptyElement (self, QString qualifiedName)
```

写一个空元素与_name_，前缀为指定_namespaceUri_。如果命名空间还没有被宣布，[QXmlStreamWriter](qxmlstreamwriter.html)将生成一个命名空间声明它。后续调用[writeAttribute](qxmlstreamwriter.html#writeAttribute)（ ）将属性添加到这个元素。

**See also** [writeNamespace](qxmlstreamwriter.html#writeNamespace)（ ） 。

```
QXmlStreamWriter.writeEmptyElement (self, QString namespaceUri, QString name)
```

这是一个重载函数。

写一个空元素与限定名_qualifiedName_。后续调用[writeAttribute](qxmlstreamwriter.html#writeAttribute)（ ）将属性添加到这个元素。

```
QXmlStreamWriter.writeEndDocument (self)
```

关闭所有剩馀的开放开始元素和写入一个换行符。

**See also** [writeStartDocument](qxmlstreamwriter.html#writeStartDocument)（ ） 。

```
QXmlStreamWriter.writeEndElement (self)
```

关闭以前开始元素。

**See also** [writeStartElement](qxmlstreamwriter.html#writeStartElement)（ ） 。

```
QXmlStreamWriter.writeEntityReference (self, QString name)
```

写实体引用_name_到流中，如“与_name_; “ 。

```
QXmlStreamWriter.writeNamespace (self, QString namespaceUri, QString prefix = QString())
```

写一个命名空间声明_namespaceUri_同_prefix_。如果_prefix_是空的，[QXmlStreamWriter](qxmlstreamwriter.html)指定由字母' N'后跟一个数字的唯一的前缀。

If [writeStartElement](qxmlstreamwriter.html#writeStartElement)（）或[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ）被调用，该声明适用于当前元素，否则它适用于下一个子元素。

注意，前缀_xml_是预定义的和保留的_http://www.w3.org/XML/1998/namespace_，这反过来又不能绑定到任何其他前缀。前缀_xmlns_和它的URI_http://www.w3.org/2000/xmlns/_用于命名空间机制本身，因此在声明中完全禁止的。

```
QXmlStreamWriter.writeProcessingInstruction (self, QString target, QString data = QString())
```

写一个XML处理指令_target_和_data_，其中_data_不得包含序列“ ？ \u003e ” 。

```
QXmlStreamWriter.writeStartDocument (self)
```

写入一个文件的开始与XML版本号_version_。

**See also** [writeEndDocument](qxmlstreamwriter.html#writeEndDocument)（ ） 。

```
QXmlStreamWriter.writeStartDocument (self, QString version)
```

写入一个文件的开始与XML版本号_version_和一个独立的属性_standalone_。

此功能被引入Qt的4.5 。

**See also** [writeEndDocument](qxmlstreamwriter.html#writeEndDocument)（ ） 。

```
QXmlStreamWriter.writeStartDocument (self, QString version, bool standalone)
```

这是一个重载函数。

写入一个文件开始的XML版本号“1.0” 。这也写入编码信息。

此功能被引入Qt的4.5 。

**See also** [writeEndDocument](qxmlstreamwriter.html#writeEndDocument)（）和[setCodec](qxmlstreamwriter.html#setCodec)（ ） 。

```
QXmlStreamWriter.writeStartElement (self, QString qualifiedName)
```

写一个开始元素与_name_，前缀为指定_namespaceUri_。如果命名空间还没有被宣布的是，[QXmlStreamWriter](qxmlstreamwriter.html)将生成一个命名空间声明它。后续调用[writeAttribute](qxmlstreamwriter.html#writeAttribute)（ ）将属性添加到这个元素。

**See also** [writeNamespace](qxmlstreamwriter.html#writeNamespace)（ ）[writeEndElement](qxmlstreamwriter.html#writeEndElement)（）和[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ） 。

```
QXmlStreamWriter.writeStartElement (self, QString namespaceUri, QString name)
```

这是一个重载函数。

写一个开始元素与_qualifiedName_。后续调用[writeAttribute](qxmlstreamwriter.html#writeAttribute)（ ）将属性添加到这个元素。

**See also** [writeEndElement](qxmlstreamwriter.html#writeEndElement)（）和[writeEmptyElement](qxmlstreamwriter.html#writeEmptyElement)（ ） 。

```
QXmlStreamWriter.writeTextElement (self, QString qualifiedName, QString text)
```

写入一个文本元素与_name_，前缀为指定_namespaceUri_和_text_。如果命名空间还没有被宣布，[QXmlStreamWriter](qxmlstreamwriter.html)将生成一个命名空间声明它。

这是一个方便的功能等同于：

```
         writeStartElement(namespaceUri, name);
         writeCharacters(text);
         writeEndElement();

```

```
QXmlStreamWriter.writeTextElement (self, QString namespaceUri, QString name, QString text)
```

这是一个重载函数。

写入一个文本元素与_qualifiedName_和_text_。

这是一个方便的功能等同于：

```
         writeStartElement(qualifiedName);
         writeCharacters(text);
         writeEndElement();

```