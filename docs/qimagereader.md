# QImageReader Class Reference

## [[QtGui](index.htm) module]

该QImageReader类提供了从文件或其它设备读取图像的格式无关的接口。[More...](#details)

### Types

*   `enum ImageReaderError { UnknownError, FileNotFoundError, DeviceError, UnsupportedFormatError, InvalidDataError }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice device, QByteArray format = QByteArray())`
*   `__init__ (self, QString fileName, QByteArray format = QByteArray())`
*   `bool autoDetectImageFormat (self)`
*   `QColor backgroundColor (self)`
*   `bool canRead (self)`
*   `QRect clipRect (self)`
*   `int currentImageNumber (self)`
*   `QRect currentImageRect (self)`
*   `bool decideFormatFromContent (self)`
*   `QIODevice device (self)`
*   `ImageReaderError error (self)`
*   `QString errorString (self)`
*   `QString fileName (self)`
*   `QByteArray format (self)`
*   `int imageCount (self)`
*   `QImage.Format imageFormat (self)`
*   `bool jumpToImage (self, int imageNumber)`
*   `bool jumpToNextImage (self)`
*   `int loopCount (self)`
*   `int nextImageDelay (self)`
*   `int quality (self)`
*   `QImage read (self)`
*   `bool read (self, QImage image)`
*   `QRect scaledClipRect (self)`
*   `QSize scaledSize (self)`
*   `setAutoDetectImageFormat (self, bool enabled)`
*   `setBackgroundColor (self, QColor color)`
*   `setClipRect (self, QRect rect)`
*   `setDecideFormatFromContent (self, bool ignored)`
*   `setDevice (self, QIODevice device)`
*   `setFileName (self, QString fileName)`
*   `setFormat (self, QByteArray format)`
*   `setQuality (self, int quality)`
*   `setScaledClipRect (self, QRect rect)`
*   `setScaledSize (self, QSize size)`
*   `QSize size (self)`
*   `bool supportsAnimation (self)`
*   `bool supportsOption (self, QImageIOHandler.ImageOption option)`
*   `QString text (self, QString key)`
*   `QStringList textKeys (self)`

### Static Methods

*   `QByteArray imageFormat (QString fileName)`
*   `QByteArray imageFormat (QIODevice device)`
*   `list-of-QByteArray supportedImageFormats ()`

* * *

## Detailed Description

该QImageReader类提供了从文件或其它设备读取图像的格式无关的接口。

对图像进行读取的最常见的方式是通过[QImage](qimage.html)和[QPixmap](qpixmap.html)的构造函数，或致电[QImage.load](qimage.html#load)（）和[QPixmap.load](qpixmap.html#load)（ ） 。 QImageReader是一家专业类阅读图像时它给你更多的控制。例如，你可以通过调用读取图像到一个特定的大小[setScaledSize](qimagereader.html#setScaledSize)（ ） ，你可以选择一个剪辑矩形，有效地只加载部分的图像，通过调用[setClipRect](qimagereader.html#setClipRect)（ ） 。根据不同的图像格式的支持基础上的，这样可以节省内存，加快加载图像。

要读取的图像，你通过构建一个QImageReader对象开始。通过其中一个文件名或设备指针，图像格式QImageReader的构造函数。然后，您可以设置多个选项，如剪辑矩形（通过调用[setClipRect](qimagereader.html#setClipRect)（ ） ）和缩放大小（通过调用[setScaledSize](qimagereader.html#setScaledSize)（））。[canRead](qimagereader.html#canRead)（）返回的图像，如果QImageReader可以读取图像（即，被支持的图像格式和设备开放阅读） 。通话[read](qimagereader.html#read)（）来读取该图像。

如果在读取图像时出现任何错误，[read](qimagereader.html#read)（ ）将返回一个null[QImage](qimage.html)。然后，您可以调用[error](qimagereader.html#error)（）找到所发生的错误的类型，或者[errorString](qimagereader.html#errorString)（）来得到一个什么地方出了错人类可读的描述。

Call [supportedImageFormats](qimagereader.html#supportedImageFormats)（）用于该QImageReader可以阅读格式的列表。 QImageReader支持所有内置的图像格式，除了支持读取任何图像格式的插件。

QImageReader自动检测默认的图像格式，通过查看所提供（可选）格式字符串，文件名后缀，和数据流内容。您可以启用或禁用此功能，通过调用[setAutoDetectImageFormat](qimagereader.html#setAutoDetectImageFormat)（ ） 。

* * *

## Type Documentation

```
QImageReader.ImageReaderError
```

这个枚举变量描述了不同类型的错误与读取图像时可能发生的[QImageReader](qimagereader.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QImageReader.FileNotFoundError` | `1` | [QImageReader](qimagereader.html)被使用的文件名，而不是文件被发现使用该名称。这也可能发生，如果文件名不包含扩展名，不支持的Qt用正确的扩展名的文件。 |
| `QImageReader.DeviceError` | `2` | [QImageReader](qimagereader.html)读取图像时遇到设备错误。您可以谘询您的特定设备上出了什么问题的更多细节。 |
| `QImageReader.UnsupportedFormatError` | `3` | Qt不支持所请求的图像的格式。 |
| `QImageReader.InvalidDataError` | `4` | 图像数据是无效的，并[QImageReader](qimagereader.html)无法从中读取图像。如果图像文件被损坏可能发生。 |
| `QImageReader.UnknownError` | `0` | 发生未知错误。如果在调用后得到这个值[read](qimagereader.html#read)（ ） ，它是最有可能的一个错误引起的[QImageReader](qimagereader.html)。 |

* * *

## Method Documentation

```
QImageReader.__init__ (self)
```

构造一个空[QImageReader](qimagereader.html)对象。在阅读的图像，调用[setDevice](qimagereader.html#setDevice)（）或[setFileName](qimagereader.html#setFileName)（ ） 。

```
QImageReader.__init__ (self, QIODevice device, QByteArray format = QByteArray())
```

构造一个[QImageReader](qimagereader.html)与设备对象_device_和图像格式_format_。

```
QImageReader.__init__ (self, QString fileName, QByteArray format = QByteArray())
```

构造一个[QImageReader](qimagereader.html)用文件名对象_fileName_和图像格式_format_。

**See also** [setFileName](qimagereader.html#setFileName)（ ） 。

```
bool QImageReader.autoDetectImageFormat (self)
```

返回True如果图像格式自动检测是对这个形象的读者能，否则返回False 。默认情况下，自动检测被启用。

**See also** [setAutoDetectImageFormat](qimagereader.html#setAutoDetectImageFormat)（ ） 。

```
QColor QImageReader.backgroundColor (self)
```

[

返回的阅读一个图像时使用的背景颜色。如果图像格式不支持设置背景色无效的颜色恢复。

这个函数是Qt 4.1中引入。

](qcolor.html)

[**See also**](qcolor.html) [setBackgroundColor](qimagereader.html#setBackgroundColor)（）和[read](qimagereader.html#read)（ ） 。

```
bool QImageReader.canRead (self)
```

返回True如果图像可以读取的设备（例如，支持的图像格式，并且该设备似乎包含有效的数据），否则返回False 。

的CanRead （）是一个轻量级函数只能执行快速测试以查看该图像数据是有效的。[read](qimagereader.html#read)（ ）的CanRead后仍可能返回False （ ）返回True ，如果图像数据被破坏。

对于支持动画影像时，所有帧都被读取，的CanRead （ ）返回False 。

**See also** [read](qimagereader.html#read)（）和[supportedImageFormats](qimagereader.html#supportedImageFormats)（ ） 。

```
QRect QImageReader.clipRect (self)
```

[](qrect.html)

[返回图像的剪辑矩形（也被称为ROI ，或感兴趣区域） 。如果没有剪辑矩形已定，一个无效的](qrect.html)[QRect](qrect.html)返回。

**See also** [setClipRect](qimagereader.html#setClipRect)（ ） 。

```
int QImageReader.currentImageNumber (self)
```

对于支持动画图像格式，该函数返回当前帧的序列号。如果图像格式不支持动画，则返回0 。

该函数返回-1，如果发生了错误。

**See also** [supportsAnimation](qimagereader.html#supportsAnimation)（ ）[QImageIOHandler.currentImageNumber](qimageiohandler.html#currentImageNumber)（）和[canRead](qimagereader.html#canRead)（ ） 。

```
QRect QImageReader.currentImageRect (self)
```

[

对于支持动画图像格式，该函数返回的矩形为当前帧。否则，将返回一个空矩形。

](qrect.html)

[**See also**](qrect.html) [supportsAnimation](qimagereader.html#supportsAnimation)（）和[QImageIOHandler.currentImageRect](qimageiohandler.html#currentImageRect)（ ） 。

```
bool QImageReader.decideFormatFromContent (self)
```

返回的图像读取器是否应该决定哪些插件只使用基于数据流的内容，而不是文件扩展名。

**See also** [setDecideFormatFromContent](qimagereader.html#setDecideFormatFromContent)（ ） 。

```
QIODevice QImageReader.device (self)
```

[](qiodevice.html)

[返回当前分配给设备](qiodevice.html)[QImageReader](qimagereader.html)，或者0，如果没有设备已经被分配。

**See also** [setDevice](qimagereader.html#setDevice)（ ） 。

```
ImageReaderError QImageReader.error (self)
```

[

返回上次发生错误的类型。

](qimagereader.html#ImageReaderError-enum)

[**See also**](qimagereader.html#ImageReaderError-enum) [ImageReaderError](qimagereader.html#ImageReaderError-enum)和[errorString](qimagereader.html#errorString)（ ） 。

```
QString QImageReader.errorString (self)
```

返回上次发生错误的可读描述。

**See also** [error](qimagereader.html#error)（ ） 。

```
QString QImageReader.fileName (self)
```

如果当前分配装置是[QFile](qfile.html)，或者如果[setFileName](qimagereader.html#setFileName)（ ）被调用，此函数返回文件的名称[QImageReader](qimagereader.html)读取。否则（即，如果没有设备已被分配或设备不是[QFile](qfile.html)） ，空[QString](qstring.html)返回。

**See also** [setFileName](qimagereader.html#setFileName)（）和[setDevice](qimagereader.html#setDevice)（ ） 。

```
QByteArray QImageReader.format (self)
```

[](qbytearray.html)

[返回格式](qbytearray.html)[QImageReader](qimagereader.html)用来读取图像。

可以分配一个设备向读者以确定该设备的格式之后，调用此函数。例如：

```
 [QImageReader](qimagereader.html) reader("image.png");
 // reader.format() == "png"

```

如果读者不能从设备读取任何图像（例如，没有图像出现，或图像已经被读取） ，或者如果格式是不支持的，这个函数返回一个空QByteArray中（ ） 。

**See also** [setFormat](qimagereader.html#setFormat)（）和[supportedImageFormats](qimagereader.html#supportedImageFormats)（ ） 。

```
int QImageReader.imageCount (self)
```

对于支持动画图像格式，该函数返回的动画图像的总数。如果格式不支持动画，则返回0 。

该函数返回-1，如果发生了错误。

**See also** [supportsAnimation](qimagereader.html#supportsAnimation)（ ）[QImageIOHandler.imageCount](qimageiohandler.html#imageCount)（）和[canRead](qimagereader.html#canRead)（ ） 。

```
QByteArray QImageReader.imageFormat (QString fileName)
```

[](qbytearray.html)

[返回的图像的格式，而无需实际读出图像的内容。该格式描述的图像格式](qbytearray.html)[QImageReader.read](qimagereader.html#read)（ ）返回，而不是实际的图像的格式。

如果图像格式不支持此功能，这个函数返回一个无效的格式。

此功能被引入Qt的4.5 。

**See also** [QImageIOHandler.ImageOption](qimageiohandler.html#ImageOption-enum)，[QImageIOHandler.option](qimageiohandler.html#option)（）和[QImageIOHandler.supportsOption](qimageiohandler.html#supportsOption)（ ） 。

```
QByteArray QImageReader.imageFormat (QIODevice device)
```

[

如果支持的话，这个函数返回文件的图像格式_fileName_。否则，返回一个空字符串。

](qbytearray.html)

```
QImage.Format QImageReader.imageFormat (self)
```

[

如果支持，则该函数返回设备的图像格式_device_。否则，返回一个空字符串。

](qimage.html#Format-enum)

[**See also**](qimage.html#Format-enum) [QImageReader.autoDetectImageFormat](qimagereader.html#autoDetectImageFormat)（ ） 。

```
bool QImageReader.jumpToImage (self, int imageNumber)
```

对于支持动画图像格式，该函数将跳到其序列号是图像_imageNumber_，返回True，如果成功则返回False相应的图像不能被发现。

到下一次调用[read](qimagereader.html#read)（ ）将尝试读取这个形象。

**See also** [jumpToNextImage](qimagereader.html#jumpToNextImage)（）和[QImageIOHandler.jumpToImage](qimageiohandler.html#jumpToImage)（ ） 。

```
bool QImageReader.jumpToNextImage (self)
```

对于支持动画图像格式，该功能的步骤在当前图像，返回True，如果成功或假，如果有在动画没有下面的图像。

默认实现调用[read](qimagereader.html#read)（ ），则丢弃所得到的图像，但图像处理程序可能必须执行这一操作的更有效的方法。

**See also** [jumpToImage](qimagereader.html#jumpToImage)（）和[QImageIOHandler.jumpToNextImage](qimageiohandler.html#jumpToNextImage)（ ） 。

```
int QImageReader.loopCount (self)
```

对于支持动画图像格式，该函数返回的时候动画应该循环的次数。如果这个函数返回-1 ，它可以意味着动画应该永远循环下去，或者发生了错误。如果发生错误，则[canRead](qimagereader.html#canRead)（ ）将返回False 。

**See also** [supportsAnimation](qimagereader.html#supportsAnimation)（ ）[QImageIOHandler.loopCount](qimageiohandler.html#loopCount)（）和[canRead](qimagereader.html#canRead)（ ） 。

```
int QImageReader.nextImageDelay (self)
```

对于支持动画图像格式，该函数返回的毫秒数要等到显示在动画的下一帧。如果图像格式不支持动画，则返回0 。

该函数返回-1，如果发生了错误。

**See also** [supportsAnimation](qimagereader.html#supportsAnimation)（ ）[QImageIOHandler.nextImageDelay](qimageiohandler.html#nextImageDelay)（）和[canRead](qimagereader.html#canRead)（ ） 。

```
int QImageReader.quality (self)
```

返回的图像的质量级别。

这个函数中引入了Qt 4.2中。

**See also** [setQuality](qimagereader.html#setQuality)（ ） 。

```
QImage QImageReader.read (self)
```

[](qimage.html)

[读取从设备中的图像。成功时，所读取的图像传回，否则空](qimage.html)[QImage](qimage.html)返回。然后，您可以调用[error](qimagereader.html#error)（）找到所发生的错误的类型，或者[errorString](qimagereader.html#errorString)（ ）来获得错误的可读描述。

对于支持动画，调用读取的图像格式（ ）多次将返回下一帧。当所有的帧都被读取，一个空的图像将被退回。

**See also** [canRead](qimagereader.html#canRead)（ ）[supportedImageFormats](qimagereader.html#supportedImageFormats)（ ）[supportsAnimation](qimagereader.html#supportsAnimation)（）和[QMovie](qmovie.html)。

```
bool QImageReader.read (self, QImage image)
```

这是一个重载函数。

读取从设备中的图像进_image_，它必须指向一个[QImage](qimage.html)。成功时返回TRUE ，否则返回False 。

If _image_具有相同的格式和大小，因为这是将要读取的图像数据，此功能可能并不需要阅读之前，分配一个新的形象。正因为如此，它可以比其它快[read](qimagereader.html#read)（）重载，它总是构造一个新的形象;读取多个图像具有相同的格式和大小时尤其如此。

```
 [QImage](qimage.html) icon(64, 64, [QImage](qimage.html).Format_RGB32);
 [QImageReader](qimagereader.html) reader("icon_64x64.bmp");
 if (reader.read(&icon)) {
     // Display icon
 }

```

对于支持动画，调用图像格式[read](qimagereader.html#read)（ ）多次将返回下一帧。当所有的帧都被读取，一个空的图像将被退回。

**See also** [canRead](qimagereader.html#canRead)（ ）[supportedImageFormats](qimagereader.html#supportedImageFormats)（ ）[supportsAnimation](qimagereader.html#supportsAnimation)（）和[QMovie](qmovie.html)。

```
QRect QImageReader.scaledClipRect (self)
```

[

返回的图像的缩放的夹子正确。

](qrect.html)

[**See also**](qrect.html) [setScaledClipRect](qimagereader.html#setScaledClipRect)（ ） 。

```
QSize QImageReader.scaledSize (self)
```

[

返回的图像的缩放大小。

](qsize.html)

[**See also**](qsize.html) [setScaledSize](qimagereader.html#setScaledSize)（ ） 。

```
QImageReader.setAutoDetectImageFormat (self, bool enabled)
```

If _enabled_诚然，图像格式自动检测被启用，否则，它被禁用。默认情况下，自动检测被启用。

[QImageReader](qimagereader.html)使用广泛的方法来检测图像格式：首先，如果你传递一个文件名[QImageReader](qimagereader.html)，它会尝试检测文件的扩展名，如果给定的文件名不指向现有的文件，通过追加支持默认扩展到给定的文件名，一次一个。然后使用下面的方法来检测图像格式：

*   Image plugins are queried first, based on either the optional format string, or the file name suffix (if the source device is a file). No content detection is done at this stage. [QImageReader](qimagereader.html) will choose the first plugin that supports reading for this format.
*   If no plugin supports the image format, Qt's built-in handlers are checked based on either the optional format string, or the file name suffix.
*   If no capable plugins or built-in handlers are found, each plugin is tested by inspecting the content of the data stream.
*   If no plugins could detect the image format based on data contents, each built-in image handler is tested by inspecting the contents.
*   Finally, if all above approaches fail, [QImageReader](qimagereader.html) will report failure when trying to read the image.

通过禁用图像格式自动检测，[QImageReader](qimagereader.html)只有查询的基础上，格式字符串（例如，没有文件扩展名进行测试）的插件和内置的处理程序。

**See also** [autoDetectImageFormat](qimagereader.html#autoDetectImageFormat)（ ）[QImageIOHandler.canRead](qimageiohandler.html#canRead)（）和[QImageIOPlugin.capabilities](index.htm#capabilities)（ ） 。

```
QImageReader.setBackgroundColor (self, QColor color)
```

设置背景色为_color_。支持此操作的图像格式，预计到后台初始化_color_前阅读一个图像。

这个函数是Qt 4.1中引入。

**See also** [backgroundColor](qimagereader.html#backgroundColor)（）和[read](qimagereader.html#read)（ ） 。

```
QImageReader.setClipRect (self, QRect rect)
```

设定影像剪辑矩形（也称为投资回报率，或感兴趣区域） ，以_rect_。的坐标_rect_是相对于未转化的图像的大小，所返回的[size](qimagereader.html#size)（ ） 。

**See also** [clipRect](qimagereader.html#clipRect)（ ）[setScaledSize](qimagereader.html#setScaledSize)（）和[setScaledClipRect](qimagereader.html#setScaledClipRect)（ ） 。

```
QImageReader.setDecideFormatFromContent (self, bool ignored)
```

If _ignored_设置为True ，则图像阅读器将忽略指定的格式或文件扩展名，并决定哪些插件只是基于在数据流中的内容使用。

设置这个标志意味着所有图像插件被加载。每个插件将读取的图像数据的第一个字节，并决定是否插件兼容与否。

这也将禁用自动检测的图像格式。

**See also** [decideFormatFromContent](qimagereader.html#decideFormatFromContent)（ ） 。

```
QImageReader.setDevice (self, QIODevice device)
```

Sets [QImageReader](qimagereader.html)的设备_device_。如果设备已经被设置，旧设备是从除去[QImageReader](qimagereader.html)而在其他情况保持不变。

如果该设备尚未打开，[QImageReader](qimagereader.html)将尝试在打开设备[QIODevice.ReadOnly](qiodevice.html#OpenModeFlag-enum)模式通过调用open （ ） 。注意，这并不对某些设备，如工作[QProcess](qprocess.html)，[QTcpSocket](qtcpsocket.html)和[QUdpSocket](qudpsocket.html)，其中更多的逻辑需要打开设备。

**See also** [device](qimagereader.html#device)（）和[setFileName](qimagereader.html#setFileName)（ ） 。

```
QImageReader.setFileName (self, QString fileName)
```

设置的文件名[QImageReader](qimagereader.html)至_fileName_。在内部，[QImageReader](qimagereader.html)将创建一个[QFile](qfile.html)对象，并在打开它[QIODevice.ReadOnly](qiodevice.html#OpenModeFlag-enum)模式，阅读图像时使用这个。

If _fileName_不包括文件扩展名（例如， 。 PNG或。 BMP ） ，[QImageReader](qimagereader.html)将循环遍历所有支持的扩展，直到找到一个匹配的文件。

**See also** [fileName](qimagereader.html#fileName)（ ）[setDevice](qimagereader.html#setDevice)（）和[supportedImageFormats](qimagereader.html#supportedImageFormats)（ ） 。

```
QImageReader.setFormat (self, QByteArray format)
```

设置格式[QImageReader](qimagereader.html)将使用阅读图像时，以_format_。_format_是不区分大小写的文本字符串。例如：

```
 [QImageReader](qimagereader.html) reader;
 reader.setFormat("png"); // same as reader.setFormat("PNG");

```

您可以致电[supportedImageFormats](qimagereader.html#supportedImageFormats)（ ）对于格式的完整列表[QImageReader](qimagereader.html)支持。

**See also** [format](qimagereader.html#format)（ ） 。

```
QImageReader.setQuality (self, int quality)
```

这是一种图像格式的具体功能，用于设置图像的质量水平来_quality_。对于不支持设置质量的图像格式，该值将被忽略。

的取值范围_quality_取决于图像格式。例如， “JPEG”格式支持的质量范围从0（低品质，高压缩）到100 （高品质，低压缩率） 。

这个函数中引入了Qt 4.2中。

**See also** [quality](qimagereader.html#quality)（ ） 。

```
QImageReader.setScaledClipRect (self, QRect rect)
```

设置缩放剪辑矩形到_rect_。缩放剪辑矩形是剪辑矩形（也称为投资回报率，或感兴趣区域）所应用的图像已被缩放后。

**See also** [scaledClipRect](qimagereader.html#scaledClipRect)（）和[setScaledSize](qimagereader.html#setScaledSize)（ ） 。

```
QImageReader.setScaledSize (self, QSize size)
```

设置图像的缩放的大小来_size_。的缩放初始剪辑矩形后进行的，但经缩放的剪辑矩形应用之前。用于缩放的算法依赖于图像格式。默认情况下（即，如果图像格式不支持缩放）[QImageReader](qimagereader.html)将使用QImage.scale （ ）与Qt.SmoothScaling 。

**See also** [scaledSize](qimagereader.html#scaledSize)（ ）[setClipRect](qimagereader.html#setClipRect)（）和[setScaledClipRect](qimagereader.html#setScaledClipRect)（ ） 。

```
QSize QImageReader.size (self)
```

[

返回图像的大小，而无需实际读出图像的内容。

如果图像格式不支持此功能，这个函数返回一个无效的大小。 Qt的内置图像处理程序都支持此功能，但自定义图像格式的插件并不需要这么做。

](qsize.html)

[**See also**](qsize.html) [QImageIOHandler.ImageOption](qimageiohandler.html#ImageOption-enum)，[QImageIOHandler.option](qimageiohandler.html#option)（）和[QImageIOHandler.supportsOption](qimageiohandler.html#supportsOption)（ ） 。

```
list-of-QByteArray QImageReader.supportedImageFormats ()
```

传回的图像格式所支持的列表[QImageReader](qimagereader.html)。

默认情况下， Qt可以阅读以下格式：

| Format | Description |
| --- | --- |
| BMP | Windows Bitmap |
| GIF | Graphic Interchange Format (optional) |
| JPG | Joint Photographic Experts Group |
| JPEG | Joint Photographic Experts Group |
| MNG | Multiple-image Network Graphics |
| PNG | Portable Network Graphics |
| PBM | Portable Bitmap |
| PGM | Portable Graymap |
| PPM | Portable Pixmap |
| TIFF | Tagged Image File Format |
| XBM | X11 Bitmap |
| XPM | X11 Pixmap |
| SVG | Scalable Vector Graphics |
| TGA | Targa Image Format |

读取和写入SVG文件是通过Qt的支持[SVG Module](index.htm)。

TGA只支持扩展到读非RLE压缩文件。尤其调用 [capabilities](http://doc.qt.nokia.com/4.7-snapshot/qimageioplugin.html#capabilities)对于TGA插件只返回[QImageIOPlugin.CanRead](index.htm#Capability-enum)，不[QImageIOPlugin.CanWrite](index.htm#Capability-enum)。

要配置的Qt与支持GIF ，通过`-qt-gif`到`configure`脚本或检查在图形安装程序中的相应选项。

注意，这个[QApplication](qapplication.html)实例必须调用此函数之前创建。

**See also** [setFormat](qimagereader.html#setFormat)（ ）[QImageWriter.supportedImageFormats](qimagewriter.html#supportedImageFormats)（）和[QImageIOPlugin](index.htm)。

```
bool QImageReader.supportsAnimation (self)
```

返回True如果图像格式支持动画，否则返回False 。

这个函数是Qt 4.1中引入。

**See also** [QMovie.supportedFormats](qmovie.html#supportedFormats)().

```
bool QImageReader.supportsOption (self, QImageIOHandler.ImageOption option)
```

返回True如果读者支持_option_否则返回False 。

不同的图像格式支持不同的选项。调用此函数来判断某个选项是否支持当前格式。例如， PNG格式允许你嵌入文本到图像的元数据（见[text](qimagereader.html#text)（ ） ） ，和BMP格式允许您确定图像的大小，而无需加载整个图像到内存中（见[size](qimagereader.html#size)（））。

```
 [QImageReader](qimagereader.html) reader(":/image.png");
 if (reader.supportsOption([QImageIOHandler](qimageiohandler.html).Size))
     qDebug() << "Size:" << reader.size();

```

这个函数中引入了Qt 4.2中。

**See also** [QImageWriter.supportsOption](qimagewriter.html#supportsOption)（ ） 。

```
QString QImageReader.text (self, QString key)
```

返回与相关图像的文字_key_。

支持这个选项是通过实施[QImageIOHandler.Description](qimageiohandler.html#ImageOption-enum)。

这个函数是Qt 4.1中引入。

**See also** [textKeys](qimagereader.html#textKeys)（）和[QImageWriter.setText](qimagewriter.html#setText)（ ） 。

```
QStringList QImageReader.textKeys (self)
```

返回文本键这一形象。您可以使用这些按键与[text](qimagereader.html#text)（ ）列出图像文本的某些关键。

支持这个选项是通过实施[QImageIOHandler.Description](qimageiohandler.html#ImageOption-enum)。

这个函数是Qt 4.1中引入。

**See also** [text](qimagereader.html#text)（ ）[QImageWriter.setText](qimagewriter.html#setText)（）和[QImage.textKeys](qimage.html#textKeys)（ ） 。