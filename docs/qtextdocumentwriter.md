# QTextDocumentWriter Class Reference

## [[QtGui](index.htm) module]

该QTextDocumentWriter类提供与格式无关的接口，用于编写[QTextDocument](qtextdocument.html)对文件或其他装置。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice device, QByteArray format)`
*   `__init__ (self, QString fileName, QByteArray format = QByteArray())`
*   `QTextCodec codec (self)`
*   `QIODevice device (self)`
*   `QString fileName (self)`
*   `QByteArray format (self)`
*   `setCodec (self, QTextCodec codec)`
*   `setDevice (self, QIODevice device)`
*   `setFileName (self, QString fileName)`
*   `setFormat (self, QByteArray format)`
*   `bool write (self, QTextDocument document)`
*   `bool write (self, QTextDocumentFragment fragment)`

### Static Methods

*   `list-of-QByteArray supportedDocumentFormats ()`

* * *

## Detailed Description

该QTextDocumentWriter类提供与格式无关的接口，用于编写[QTextDocument](qtextdocument.html)对文件或其他装置。

写一个文件，构造一个QTextDocumentWriter对象可以是文件名或一个设备对象，并指定要写入的文件格式。你可以构造一个作家，并使用设定的格式[setFormat](qtextdocumentwriter.html#setFormat)（ ）以后。

Call [write](qtextdocumentwriter.html#write)（）写的文件到该设备。如果文档被成功写入，这个函数返回True。但是，如果写文件时发生错误，将返回False 。

Call [supportedDocumentFormats](qtextdocumentwriter.html#supportedDocumentFormats)（ ）对于格式QTextDocumentWriter可以写一个清单。

由于所支持的输出格式的能力有很大的不同，笔者简单地输出各种格式对象的适当子集。这通常包括格式化的文本和文档中包含的图像。

* * *

## Method Documentation

```
QTextDocumentWriter.__init__ (self)
```

构造一个空[QTextDocumentWriter](qtextdocumentwriter.html)对象。写作之前，你必须调用[setFormat](qtextdocumentwriter.html#setFormat)（ ）来设置文档的格式，然后[setDevice](qtextdocumentwriter.html#setDevice)（）或[setFileName](qtextdocumentwriter.html#setFileName)（ ） 。

```
QTextDocumentWriter.__init__ (self, QIODevice device, QByteArray format)
```

构造一个[QTextDocumentWriter](qtextdocumentwriter.html)对象写入给定的_device_在由指定的文档格式_format_。

```
QTextDocumentWriter.__init__ (self, QString fileName, QByteArray format = QByteArray())
```

构造一个[QTextDocumentWriter](qtextdocumentwriter.html)对象将写入一个文件名为_fileName_使用由指定的文件格式_format_。如果_format_不设置，[QTextDocumentWriter](qtextdocumentwriter.html)将检测到的文件格式通过检查的延伸_fileName_。

```
QTextCodec QTextDocumentWriter.codec (self)
```

[

返回当前分配给该作家的编解码器。

](qtextcodec.html)

[**See also**](qtextcodec.html) [setCodec](qtextdocumentwriter.html#setCodec)（ ） 。

```
QIODevice QTextDocumentWriter.device (self)
```

[

返回当前分配的设备，或者0，如果没有设备已经被分配。

](qiodevice.html)

[**See also**](qiodevice.html) [setDevice](qtextdocumentwriter.html#setDevice)（ ） 。

```
QString QTextDocumentWriter.fileName (self)
```

如果当前分配装置是[QFile](qfile.html)，或者如果[setFileName](qtextdocumentwriter.html#setFileName)（）被调用时，该函数返回到被写入到该文件的名称。在所有其他情况下，它返回一个空字符串。

**See also** [setFileName](qtextdocumentwriter.html#setFileName)（）和[setDevice](qtextdocumentwriter.html#setDevice)（ ） 。

```
QByteArray QTextDocumentWriter.format (self)
```

[

返回用于书写文档的格式。

](qbytearray.html)

[**See also**](qbytearray.html) [setFormat](qtextdocumentwriter.html#setFormat)（ ） 。

```
QTextDocumentWriter.setCodec (self, QTextCodec codec)
```

设置编解码器，该流_codec_。编解码器是用于编码被写入任何数据。默认情况下，[QTextDocumentWriter](qtextdocumentwriter.html)使用UTF-8 。

**See also** [codec](qtextdocumentwriter.html#codec)（ ） 。

```
QTextDocumentWriter.setDevice (self, QIODevice device)
```

集作家的设备到_device_规定。如果设备已经设置，老设备被移除，但在其他方面保持不变。

如果该设备尚未打开，[QTextDocumentWriter](qtextdocumentwriter.html)将尝试在打开设备[QIODevice.WriteOnly](qiodevice.html#OpenModeFlag-enum)模式通过调用open （ ） 。

**Note:**这不会对某些设备，如工作[QProcess](qprocess.html)，[QTcpSocket](qtcpsocket.html)和[QUdpSocket](qudpsocket.html)，其中该装置之前，需要一些配置可以被打开。

**See also** [device](qtextdocumentwriter.html#device)（）和[setFileName](qtextdocumentwriter.html#setFileName)（ ） 。

```
QTextDocumentWriter.setFileName (self, QString fileName)
```

设置文件的要写入的名称_fileName_。在内部，[QTextDocumentWriter](qtextdocumentwriter.html)将创建一个[QFile](qfile.html)并在打开它[QIODevice.WriteOnly](qiodevice.html#OpenModeFlag-enum)模式，并编写文档时使用这个文件。

**See also** [fileName](qtextdocumentwriter.html#fileName)（）和[setDevice](qtextdocumentwriter.html#setDevice)（ ） 。

```
QTextDocumentWriter.setFormat (self, QByteArray format)
```

设置用于写文件的格式_format_规定。_format_是不区分大小写的文本字符串。例如：

```
         [QTextDocumentWriter](qtextdocumentwriter.html) writer;
         writer.setFormat("odf"); // same as writer.setFormat("ODF");

```

您可以致电[supportedDocumentFormats](qtextdocumentwriter.html#supportedDocumentFormats)（ ）对于格式的完整列表[QTextDocumentWriter](qtextdocumentwriter.html)支持。

**See also** [format](qtextdocumentwriter.html#format)（ ） 。

```
list-of-QByteArray QTextDocumentWriter.supportedDocumentFormats ()
```

返回的文档格式所支持的列表[QTextDocumentWriter](qtextdocumentwriter.html)。

默认情况下， Qt可以编写以下格式：

| Format | Description |
| --- | --- |
| plaintext | Plain text |
| HTML | HyperText Markup Language |
| ODF | OpenDocument Format |

**See also** [setFormat](qtextdocumentwriter.html#setFormat)（ ） 。

```
bool QTextDocumentWriter.write (self, QTextDocument document)
```

将给定_document_到指定的装置或档案，并成功返回True ，否则返回False 。

```
bool QTextDocumentWriter.write (self, QTextDocumentFragment fragment)
```

通过写入指定的文件片段_fragment_到指定的装置或档案，并成功返回True ，否则返回False 。