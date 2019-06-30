# QImageWriter Class Reference

## [[QtGui](index.htm) module]

该QImageWriter类提供用于编写图像文件或其它设备的格式无关的接口。[More...](#details)

### Types

*   `enum ImageWriterError { UnknownError, DeviceError, UnsupportedFormatError }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice device, QByteArray format)`
*   `__init__ (self, QString fileName, QByteArray format = QByteArray())`
*   `bool canWrite (self)`
*   `int compression (self)`
*   `QString description (self)`
*   `QIODevice device (self)`
*   `ImageWriterError error (self)`
*   `QString errorString (self)`
*   `QString fileName (self)`
*   `QByteArray format (self)`
*   `float gamma (self)`
*   `int quality (self)`
*   `setCompression (self, int compression)`
*   `setDescription (self, QString description)`
*   `setDevice (self, QIODevice device)`
*   `setFileName (self, QString fileName)`
*   `setFormat (self, QByteArray format)`
*   `setGamma (self, float gamma)`
*   `setQuality (self, int quality)`
*   `setText (self, QString key, QString text)`
*   `bool supportsOption (self, QImageIOHandler.ImageOption option)`
*   `bool write (self, QImage image)`

### Static Methods

*   `list-of-QByteArray supportedImageFormats ()`

* * *

## Detailed Description

该QImageWriter类提供用于编写图像文件或其它设备的格式无关的接口。

QImageWriter支持设置格式特定的选项，如Gamma值，压缩水平和质量，在存储图像前。如果你不需要这样的选项，您可以使用[QImage.save](qimage.html#save)（）或[QPixmap.save](qpixmap.html#save)（ ）来代替。

要存储的图像，你通过构建一个QImageWriter对象开始。通过其中一个文件名或设备指针，图像格式QImageWriter的构造函数。然后，您可以设置多个选项，如伽玛值（通过调用[setGamma](qimagewriter.html#setGamma)（ ） ）和质量（通过调用[setQuality](qimagewriter.html#setQuality)（））。[canWrite](qimagewriter.html#canWrite)（ ）返回True ，如果QImageWriter可写的图像（即图像格式的支持和设备是开放的写作） 。通话[write](qimagewriter.html#write)（ ）将图像写入到设备。

如果写入图像时出现任何错误，[write](qimagewriter.html#write)（ ）将返回False 。然后，您可以调用[error](qimagewriter.html#error)（）找到所发生的错误的类型，或者[errorString](qimagewriter.html#errorString)（）来得到一个什么地方出了错人类可读的描述。

Call [supportedImageFormats](qimagewriter.html#supportedImageFormats)（ ）对于格式QImageWriter可以写一个清单。 QImageWriter支持所有内置的图像格式，除了支持写入任何图像格式的插件。

* * *

## Type Documentation

```
QImageWriter.ImageWriterError
```

这个枚举变量描述了编写图像时可能发生的错误[QImageWriter](qimagewriter.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QImageWriter.DeviceError` | `1` | [QImageWriter](qimagewriter.html)写入图像数据时遇到的一个装置的错误。请谘询您的设备上出了什么问题的更多细节。 |
| `QImageWriter.UnsupportedFormatError` | `2` | Qt不支持所请求的图像的格式。 |
| `QImageWriter.UnknownError` | `0` | 发生未知错误。如果在调用后得到这个值[write](qimagewriter.html#write)（ ） ，它是最有可能的一个错误引起的[QImageWriter](qimagewriter.html)。 |

* * *

## Method Documentation

```
QImageWriter.__init__ (self)
```

构造一个空[QImageWriter](qimagewriter.html)对象。写作之前，你必须调用[setFormat](qimagewriter.html#setFormat)（）来设置图像格式，然后[setDevice](qimagewriter.html#setDevice)（）或[setFileName](qimagewriter.html#setFileName)（ ） 。

```
QImageWriter.__init__ (self, QIODevice device, QByteArray format)
```

构造一个[QImageWriter](qimagewriter.html)使用该设备对象_device_和图像格式_format_。

```
QImageWriter.__init__ (self, QString fileName, QByteArray format = QByteArray())
```

构造一个[QImageWriter](qimagewriter.html)这将写入一个文件名为对象_fileName_使用的图像格式_format_。如果_format_不设置，[QImageWriter](qimagewriter.html)将检测到的图像格式通过检查的延伸_fileName_。

```
bool QImageWriter.canWrite (self)
```

返回True如果[QImageWriter](qimagewriter.html)可以写的图像，也就是说，图像格式的支持以及分配的装置打开阅读。

**See also** [write](qimagewriter.html#write)（ ）[setDevice](qimagewriter.html#setDevice)（）和[setFormat](qimagewriter.html#setFormat)（ ） 。

```
int QImageWriter.compression (self)
```

返回图像的压缩。

**See also** [setCompression](qimagewriter.html#setCompression)（ ） 。

```
QString QImageWriter.description (self)
```

```
QIODevice QImageWriter.device (self)
```

[](qiodevice.html)

[返回当前分配给设备](qiodevice.html)[QImageWriter](qimagewriter.html)，或者0，如果没有设备已经被分配。

**See also** [setDevice](qimagewriter.html#setDevice)（ ） 。

```
ImageWriterError QImageWriter.error (self)
```

[

返回上次发生错误的类型。

](qimagewriter.html#ImageWriterError-enum)

[**See also**](qimagewriter.html#ImageWriterError-enum) [ImageWriterError](qimagewriter.html#ImageWriterError-enum)和[errorString](qimagewriter.html#errorString)（ ） 。

```
QString QImageWriter.errorString (self)
```

返回上次发生错误的可读描述。

**See also** [error](qimagewriter.html#error)（ ） 。

```
QString QImageWriter.fileName (self)
```

如果当前分配装置是[QFile](qfile.html)，或者如果[setFileName](qimagewriter.html#setFileName)（ ）被调用，此函数返回文件的名称[QImageWriter](qimagewriter.html)写入。否则（即，如果没有设备已被分配或设备不是[QFile](qfile.html)） ，空[QString](qstring.html)返回。

**See also** [setFileName](qimagewriter.html#setFileName)（）和[setDevice](qimagewriter.html#setDevice)（ ） 。

```
QByteArray QImageWriter.format (self)
```

[](qbytearray.html)

[返回格式](qbytearray.html)[QImageWriter](qimagewriter.html)用来书写的图像。

**See also** [setFormat](qimagewriter.html#setFormat)（ ） 。

```
float QImageWriter.gamma (self)
```

返回图像的灰度级。

**See also** [setGamma](qimagewriter.html#setGamma)（ ） 。

```
int QImageWriter.quality (self)
```

返回的图像的质量级别。

**See also** [setQuality](qimagewriter.html#setQuality)（ ） 。

```
QImageWriter.setCompression (self, int compression)
```

这是设置一个图像的压缩图像格式的具体功能。对于不支持设置压缩图像格式，该值将被忽略。

的取值范围_compression_取决于图像格式。例如， “ TIFF ”格式支持两个值， 0 （不压缩）和1（ LZW压缩） 。

**See also** [compression](qimagewriter.html#compression)（ ） 。

```
QImageWriter.setDescription (self, QString description)
```

```
QImageWriter.setDevice (self, QIODevice device)
```

Sets [QImageWriter](qimagewriter.html)的设备_device_。如果设备已经被设置，旧设备是从除去[QImageWriter](qimagewriter.html)而在其他情况保持不变。

如果该设备尚未打开，[QImageWriter](qimagewriter.html)将尝试在打开设备[QIODevice.WriteOnly](qiodevice.html#OpenModeFlag-enum)模式通过调用open （ ） 。注意，这并不对某些设备，如工作[QProcess](qprocess.html)，[QTcpSocket](qtcpsocket.html)和[QUdpSocket](qudpsocket.html)，其中更多的逻辑需要打开设备。

**See also** [device](qimagewriter.html#device)（）和[setFileName](qimagewriter.html#setFileName)（ ） 。

```
QImageWriter.setFileName (self, QString fileName)
```

设置的文件名[QImageWriter](qimagewriter.html)至_fileName_。在内部，[QImageWriter](qimagewriter.html)将创建一个[QFile](qfile.html)并在打开它[QIODevice.WriteOnly](qiodevice.html#OpenModeFlag-enum)模式，并写入图像时使用这个文件。

**See also** [fileName](qimagewriter.html#fileName)（）和[setDevice](qimagewriter.html#setDevice)（ ） 。

```
QImageWriter.setFormat (self, QByteArray format)
```

设置格式[QImageWriter](qimagewriter.html)写图像时，要会用_format_。_format_是不区分大小写的文本字符串。例如：

```
 [QImageWriter](qimagewriter.html) writer;
 writer.setFormat("png"); // same as writer.setFormat("PNG");

```

您可以致电[supportedImageFormats](qimagewriter.html#supportedImageFormats)（ ）对于格式的完整列表[QImageWriter](qimagewriter.html)支持。

**See also** [format](qimagewriter.html#format)（ ） 。

```
QImageWriter.setGamma (self, float gamma)
```

这是一种图像格式的具体功能，用于设置图像的伽马电平到_gamma_。对于不支持设置的Gamma值的图像格式，该值将被忽略。

的取值范围_gamma_取决于图像格式。例如， “ PNG ”格式支持一个伽玛范围从0.0到1.0。

**See also** [gamma](qimagewriter.html#gamma)（）和[quality](qimagewriter.html#quality)（ ） 。

```
QImageWriter.setQuality (self, int quality)
```

这是一种图像格式的具体功能，用于设置图像的质量水平来_quality_。对于不支持设置质量的图像格式，该值将被忽略。

的取值范围_quality_取决于图像格式。例如， “JPEG”格式支持的质量范围从0（低品质，高压缩）到100 （高品质，低压缩率） 。

**See also** [quality](qimagewriter.html#quality)（ ） 。

```
QImageWriter.setText (self, QString key, QString text)
```

设置与该键关联图像的文字_key_至_text_。这是用于存储版权信息或图像等信息是有用的。例如：

```
 [QImage](qimage.html) image("some/image.jpeg");
 [QImageWriter](qimagewriter.html) writer("../img/outimage.png", "png");
 writer.setText("Author", "John Smith");
 writer.write(image);

```

如果你想存储数据的一个单一的块（例如，注释） ，你可以传递一个空键，或使用如“描述”一个通用密钥。

键和文本将被嵌入到图像数据后调用[write](qimagewriter.html#write)（ ） 。

支持这个选项是通过实施[QImageIOHandler.Description](qimageiohandler.html#ImageOption-enum)。

这个函数是Qt 4.1中引入。

**See also** [QImage.setText](qimage.html#setText)（）和[QImageReader.text](qimagereader.html#text)（ ） 。

```
list-of-QByteArray QImageWriter.supportedImageFormats ()
```

传回的图像格式所支持的列表[QImageWriter](qimagewriter.html)。

默认情况下， Qt可以编写以下格式：

| Format | Description |
| --- | --- |
| BMP | Windows Bitmap |
| JPG | Joint Photographic Experts Group |
| JPEG | Joint Photographic Experts Group |
| PNG | Portable Network Graphics |
| PPM | Portable Pixmap |
| TIFF | Tagged Image File Format |
| XBM | X11 Bitmap |
| XPM | X11 Pixmap |

读取和写入SVG文件是通过Qt的支持[SVG Module](index.htm)。

注意，这个[QApplication](qapplication.html)实例必须调用此函数之前创建。

**See also** [setFormat](qimagewriter.html#setFormat)（ ）[QImageReader.supportedImageFormats](qimagereader.html#supportedImageFormats)（）和[QImageIOPlugin](index.htm)。

```
bool QImageWriter.supportsOption (self, QImageIOHandler.ImageOption option)
```

返回True如果writer支持_option_否则返回False 。

不同的图像格式支持不同的选项。调用此函数来判断某个选项是否支持当前格式。例如， PNG格式允许你嵌入文本到图像的元数据（见正文（ ） ） 。

```
 [QImageWriter](qimagewriter.html) writer(fileName);
 if (writer.supportsOption([QImageIOHandler](qimageiohandler.html).Description))
     writer.setText("Author", "John Smith");

```

之后笔者已经与格式相关的选项可以进行测试。

这个函数中引入了Qt 4.2中。

**See also** [QImageReader.supportsOption](qimagereader.html#supportsOption)（）和[setFormat](qimagewriter.html#setFormat)（ ） 。

```
bool QImageWriter.write (self, QImage image)
```

写入图像_image_到指定的设备或文件名。成功时返回TRUE ，否则返回False 。如果操作失败，您可以拨打[error](qimagewriter.html#error)（）找到所发生的错误的类型，或者[errorString](qimagewriter.html#errorString)（ ）来获得错误的可读描述。

**See also** [canWrite](qimagewriter.html#canWrite)（ ）[error](qimagewriter.html#error)（）和[errorString](qimagewriter.html#errorString)（ ） 。