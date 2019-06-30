# QImage Class Reference

## [[QtGui](index.htm) module]

QImage的类提供了与硬件无关的图像表示，它允许直接访问的像素数据，并可以作为一个绘图设备。[More...](#details)

继承[QPaintDevice](qpaintdevice.html)。

### Types

*   `enum Format { Format_Invalid, Format_Mono, Format_MonoLSB, Format_Indexed8, ..., Format_ARGB4444_Premultiplied }`
*   `enum InvertMode { InvertRgb, InvertRgba }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSize size, Format format)`
*   `__init__ (self, int width, int height, Format format)`
*   `__init__ (self, str data, int width, int height, Format format)`
*   `__init__ (self, sip.voidptr data, int width, int height, Format format)`
*   `__init__ (self, str data, int width, int height, int bytesPerLine, Format format)`
*   `__init__ (self, sip.voidptr data, int width, int height, int bytesPerLine, Format format)`
*   `__init__ (self, list-of-str xpm)`
*   `__init__ (self, QString fileName, str format = None)`
*   `__init__ (self, QImage)`
*   `__init__ (self, QVariant variant)`
*   `bool allGray (self)`
*   `QImage alphaChannel (self)`
*   `int bitPlaneCount (self)`
*   `sip.voidptr bits (self)`
*   `int byteCount (self)`
*   `int bytesPerLine (self)`
*   `int cacheKey (self)`
*   `int color (self, int i)`
*   `int colorCount (self)`
*   `list-of-int colorTable (self)`
*   `sip.voidptr constBits (self)`
*   `sip.voidptr constScanLine (self, int)`
*   `QImage convertToFormat (self, Format format, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `QImage convertToFormat (self, Format format, list-of-int colorTable, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `QImage copy (self, QRect rect = QRect())`
*   `QImage copy (self, int x, int y, int w, int h)`
*   `QImage createAlphaMask (self, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `QImage createHeuristicMask (self, bool clipTight = True)`
*   `QImage createMaskFromColor (self, int color, Qt.MaskMode mode = Qt.MaskInColor)`
*   `int depth (self)`
*   `detach (self)`
*   `int devType (self)`
*   `int dotsPerMeterX (self)`
*   `int dotsPerMeterY (self)`
*   `fill (self, Qt.GlobalColor color)`
*   `fill (self, QColor color)`
*   `fill (self, int pixel)`
*   `Format format (self)`
*   `bool hasAlphaChannel (self)`
*   `int height (self)`
*   `invertPixels (self, InvertMode mode = QImage.InvertRgb)`
*   `bool isDetached (self)`
*   `bool isGrayscale (self)`
*   `bool isNull (self)`
*   `bool load (self, QIODevice device, str format)`
*   `bool load (self, QString fileName, str format = None)`
*   `bool loadFromData (self, str data, str format = None)`
*   `bool loadFromData (self, QByteArray data, str format = None)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric metric)`
*   `QImage mirrored (self, bool horizontal = False, bool vertical = True)`
*   `int numBytes (self)`
*   `int numColors (self)`
*   `QPoint offset (self)`
*   `QPaintEngine paintEngine (self)`
*   `int pixel (self, QPoint pt)`
*   `int pixel (self, int x, int y)`
*   `int pixelIndex (self, QPoint pt)`
*   `int pixelIndex (self, int x, int y)`
*   `QRect rect (self)`
*   `QImage rgbSwapped (self)`
*   `bool save (self, QString fileName, str format = None, int quality = -1)`
*   `bool save (self, QIODevice device, str format = None, int quality = -1)`
*   `QImage scaled (self, int width, int height, Qt.AspectRatioMode aspectRatioMode = Qt.IgnoreAspectRatio, Qt.TransformationMode transformMode = Qt.FastTransformation)`
*   `QImage scaled (self, QSize size, Qt.AspectRatioMode aspectRatioMode = Qt.IgnoreAspectRatio, Qt.TransformationMode transformMode = Qt.FastTransformation)`
*   `QImage scaledToHeight (self, int height, Qt.TransformationMode mode = Qt.FastTransformation)`
*   `QImage scaledToWidth (self, int width, Qt.TransformationMode mode = Qt.FastTransformation)`
*   `sip.voidptr scanLine (self, int)`
*   `int serialNumber (self)`
*   `setAlphaChannel (self, QImage alphaChannel)`
*   `setColor (self, int i, int c)`
*   `setColorCount (self, int)`
*   `setColorTable (self, list-of-int colors)`
*   `setDotsPerMeterX (self, int)`
*   `setDotsPerMeterY (self, int)`
*   `setNumColors (self, int)`
*   `setOffset (self, QPoint)`
*   `setPixel (self, QPoint pt, int index_or_rgb)`
*   `setPixel (self, int x, int y, int index_or_rgb)`
*   `setText (self, QString key, QString value)`
*   `QSize size (self)`
*   `swap (self, QImage other)`
*   `QString text (self, QString key = QString())`
*   `QStringList textKeys (self)`
*   `QImage transformed (self, QMatrix matrix, Qt.TransformationMode mode = Qt.FastTransformation)`
*   `QImage transformed (self, QTransform matrix, Qt.TransformationMode mode = Qt.FastTransformation)`
*   `bool valid (self, QPoint pt)`
*   `bool valid (self, int x, int y)`
*   `int width (self)`

### Static Methods

*   `QImage fromData (str data, str format = None)`
*   `QImage fromData (QByteArray data, str format = None)`
*   `QMatrix trueMatrix (QMatrix, int w, int h)`
*   `QTransform trueMatrix (QTransform, int w, int h)`

### Special Methods

*   `bool __eq__ (self, QImage)`
*   `bool __ne__ (self, QImage)`

* * *

## Detailed Description

QImage的类提供了与硬件无关的图像表示，它允许直接访问的像素数据，并可以作为一个绘图设备。

Qt提供了四个类用于处理图像数据： QImage的，[QPixmap](qpixmap.html)，[QBitmap](qbitmap.html)和[QPicture](qpicture.html)。 QImage的设计和优化的I / O和直接像素访问和操作，而[QPixmap](qpixmap.html)设计并显示在屏幕上的图像进行了优化。[QBitmap](qbitmap.html)只有继承一个方便的类[QPixmap](qpixmap.html)，确保深度为1 。最后，该[QPicture](qpicture.html)类是一个绘图设备，记录和重放[QPainter](qpainter.html)的命令。

因为QImage的是[QPaintDevice](qpaintdevice.html)子类，[QPainter](qpainter.html)可用于直接绘制到图像。当使用[QPainter](qpainter.html)在QImage的，这幅画可以在另一个线程来执行比目前的GUI线程。

该QImage的类支持由所描述的几种图像格式[Format](qimage.html#Format-enum)枚举。这些措施包括单色， 8位， 32位和alpha混合图像这是适用于所有版本的Qt 4.x中的

QImage的规定的，可以被用来获得各种有关图像信息的功能的集合。也有几个功能，使图像的变换。

因为QImage的类使用QImage的对象可以被传来传去传值[implicit data sharing](index.htm#implicit-data-sharing)。 QImage的对象也可以流并进行比较。

**Note:**如果你想加载QImage的对象在静态编译的Qt ，指的是[Plugin HowTo](index.htm#static-plugins)。

**Warning:**画上的QImage与格式[QImage.Format_Indexed8](qimage.html#Format-enum)不被支持。

### Reading and Writing Image Files

提供QImage的加载图像文件的几种方法：该文件可以构造QImage的对象时被加载，或使用[load](qimage.html#load)（）或[loadFromData](qimage.html#loadFromData)（ ）函数以后。 QImage的还提供了静态[fromData](qimage.html#fromData)（）函数，从给定的数据构造一个QImage的。当加载一个图像，文件名可以指在磁盘上的实际文件或应用的嵌入式资源之一。看[The Qt Resource System](index.htm)概述有关如何嵌入在应用程序的可执行映像和其他资源文件的详细信息。

只需调用[save](qimage.html#save)（ ）函数来保存QImage的对象。

都可以通过支持的文件格式的完整列表[QImageReader.supportedImageFormats](qimagereader.html#supportedImageFormats)（）和[QImageWriter.supportedImageFormats](qimagewriter.html#supportedImageFormats)（）函数。新的文件格式可以添加插件。默认情况下， Qt支持以下格式：

| Format | Description | Qt's support |
| --- | --- | --- |
| BMP | Windows Bitmap | Read/write |
| GIF | Graphic Interchange Format (optional) | Read |
| JPG | Joint Photographic Experts Group | Read/write |
| JPEG | Joint Photographic Experts Group | Read/write |
| PNG | Portable Network Graphics | Read/write |
| PBM | Portable Bitmap | Read |
| PGM | Portable Graymap | Read |
| PPM | Portable Pixmap | Read/write |
| TIFF | Tagged Image File Format | Read/write |
| XBM | X11 Bitmap | Read/write |
| XPM | X11 Pixmap | Read/write |

### Image Information

QImage的规定的，可以被用来获得各种有关图像信息的功能的集合：

|  | Available Functions |
| --- | --- |
| Geometry | The [size](qimage.html#size)(), [width](qimage.html#width)(), [height](qimage.html#height)(), [dotsPerMeterX](qimage.html#dotsPerMeterX)(), and [dotsPerMeterY](qimage.html#dotsPerMeterY)() functions provide information about the image size and aspect ratio.该[rect](qimage.html#rect)（ ）函数返回图像的外接矩形。该[valid](qimage.html#valid)（ ）函数告诉如果给定的对坐标是该矩形内。该[offset](qimage.html#offset)（）函数返回由该图像的目的是当使用位于相对于其他图像，这些图像也可以被操纵，以此作为偏移的像素的数量的[setOffset](qimage.html#setOffset)（）函数。 |
| Colors | The color of a pixel can be retrieved by passing its coordinates to the [pixel](qimage.html#pixel)() function. The [pixel](qimage.html#pixel)() function returns the color as a [QRgb](qcolor.html#QRgb-typedef) value indepedent of the image's format.在单色的情况下和8位的图像，该[colorCount](qimage.html#colorCount)（）和[colorTable](qimage.html#colorTable)（）函数提供了有关用于存储图像数据的颜色成分的信息：该[colorTable](qimage.html#colorTable)（ ）函数返回图像的整个颜色表。为了得到一个单一的项目，请使用[pixelIndex](qimage.html#pixelIndex)（ ）函数来检索一个给定的对坐标的像素索引，然后使用[color](qimage.html#color)（ ）函数来检索的颜色。请注意，如果您手动创建一个8位图像，你必须设置在图像上有效的颜色表也是如此。该[hasAlphaChannel](qimage.html#hasAlphaChannel)（ ）函数告诉如果图像的格式，尊重alpha通道，还是不行。该[allGray](qimage.html#allGray)（）和[isGrayscale](qimage.html#isGrayscale)（ ）函数告诉了图像的颜色是否是灰色的形形色色。另见[Pixel Manipulation](#pixel-manipulation)和[Image Transformations](#image-transformations)部分。 |
| Text | The [text](qimage.html#text)() function returns the image text associated with the given text key. An image's text keys can be retrieved using the [textKeys](qimage.html#textKeys)() function. Use the [setText](qimage.html#setText)() function to alter an image's text. |
| Low-level information | The [depth](qimage.html#depth)() function returns the depth of the image. The supported depths are 1 (monochrome), 8, 16, 24 and 32 bits. The [bitPlaneCount](qimage.html#bitPlaneCount)() function tells how many of those bits that are used. For more information see the [Image Formats](#image-formats) section.该[format](qimage.html#format)（ ）[bytesPerLine](qimage.html#bytesPerLine)（）和[byteCount](qimage.html#byteCount)（）函数提供关于存储的图像中的数据的低级别信息。该[cacheKey](qimage.html#cacheKey)（ ）函数返回一个数字，它唯一标识此QImage的对象的内容。 |

### Pixel Manipulation

用于处理图像的像素的功能取决于图像格式。其原因是单色和8位图像是基于索引的，并使用一个颜色查找表，而32位图像存储ARGB值直接。有关图像格式的详细信息，请参阅[Image Formats](#image-formats)一节。

万一一个32位的图像，本[setPixel](qimage.html#setPixel)（）函数可以被用来改变该像素的颜色在指定的ARGB四联的给定坐标的任何其他颜色。为了让合适的[QRgb](qcolor.html#QRgb-typedef)值，使用[qRgb](index.htm#qRgb)（ ） （添加一个默认的alpha分量给定的RGB值，即创建一个不透明的颜色）或[qRgba](index.htm#qRgba)（）函数。例如：

| 32-bit |
| --- |
| ![](../img/qimage-32bit_scaled.png) | 

```
 QImage image(3, 3, QImage.Format_RGB32);
 [QRgb](qcolor.html#QRgb-typedef) value;

 value = qRgb(189, 149, 39); // 0xffbd9527
 image.setPixel(1, 1, value);

 value = qRgb(122, 163, 39); // 0xff7aa327
 image.setPixel(0, 1, value);
 image.setPixel(1, 0, value);

 value = qRgb(237, 187, 51); // 0xffedba31
 image.setPixel(2, 1, value);

```

 |

在壳体的8位和monchrome图像中，像素值是只从图像的颜色表的索引。所以，[setPixel](qimage.html#setPixel)（）函数仅可用于改变像素的颜色在给定的坐标以一个预定义的色彩从该图像的颜色表，即它只能改变像素的索引值。要更改或添加颜色到图像的颜色表，使用[setColor](qimage.html#setColor)（）函数。

在颜色表中的条目是一个ARGB四胞胎编码为[QRgb](qcolor.html#QRgb-typedef)值。使用[qRgb](index.htm#qRgb)（）和[qRgba](index.htm#qRgba)（ ）函数来作出适当的[QRgb](qcolor.html#QRgb-typedef)值与使用[setColor](qimage.html#setColor)（）函数。例如：

| 8-bit |
| --- |
| ![](../img/qimage-8bit_scaled.png) | 

```
 QImage image(3, 3, QImage.Format_Indexed8);
 [QRgb](qcolor.html#QRgb-typedef) value;

 value = qRgb(122, 163, 39); // 0xff7aa327
 image.setColor(0, value);

 value = qRgb(237, 187, 51); // 0xffedba31
 image.setColor(1, value);

 value = qRgb(189, 149, 39); // 0xffbd9527
 image.setColor(2, value);

 image.setPixel(0, 1, 0);
 image.setPixel(1, 0, 0);
 image.setPixel(1, 1, 2);
 image.setPixel(2, 1, 1);

```

 |

QImage的还提供了[scanLine](qimage.html#scanLine)（ ）函数返回一个指向像素数据在给定索引扫描线，以及[bits](qimage.html#bits)（ ）函数返回一个指向第一个像素的数据（这相当于`scanLine(0)`） 。

### Image Formats

存储在一个QImage的每个像素由一个整数表示。视格式的整数的大小而有所不同。 QImage的支持由所描述的几种图像格式[Format](qimage.html#Format-enum)枚举。

单色图像使用的是1位索引到颜色表最多两种颜色存储。有两种不同类型的黑白图像：大端（高位在前）和little endian（低位在前）位顺序。

8位的图像是使用8位的索引到一个颜色表中存储的，即它们具有每像素一个字节。该颜色表是一个[QVector](index.htm)\u003c[QRgb](qcolor.html#QRgb-typedef)\u003e和[QRgb](qcolor.html#QRgb-typedef)的typedef相当于包含的格式0xAARRGGBB一个ARGB四胞胎一个unsigned int 。

32位图像没有颜色表，而是每个像素包含一个[QRgb](qcolor.html#QRgb-typedef)值。有三种不同类型的32位图像分别存储的RGB （即0xffRRGGBB ） ， ARGB和预乘的ARGB值。在预乘格式的红色，绿色和蓝色通道是由alpha分量除以255乘以。

的图像的格式可以用要检索的[format](qimage.html#format)（）函数。使用[convertToFormat](qimage.html#convertToFormat)（）函数将图像转换成另一种格式。该[allGray](qimage.html#allGray)（）和[isGrayscale](qimage.html#isGrayscale)（）函数判断是否彩色图像可以安全地被转换为灰度图像。

### Image Transformations

QImage的支持许多函数，用于创建一个新的图像，它是原始的转换后的版本：该[createAlphaMask](qimage.html#createAlphaMask)（ ）函数建立和从这个图片的alpha缓冲区返回一个1 - BPP掩码和[createHeuristicMask](qimage.html#createHeuristicMask)（ ）函数创建并返回一个1 - BPP启发式掩码这一形象。后者的功能是通过从一个角中选择一种颜色，然后小打小闹该颜色的起始像素的所有边。

该[mirrored](qimage.html#mirrored)（）函数返回的图像的反射镜在所需方向上的[scaled](qimage.html#scaled)（）返回的图像缩放到所要求的措施，一个矩形的副本，并且该[rgbSwapped](qimage.html#rgbSwapped)（ ）函数构造一个BGR图像从RGB图像。

该[scaledToWidth](qimage.html#scaledToWidth)（）和[scaledToHeight](qimage.html#scaledToHeight)（ ）函数返回图像的缩放复印。

该[transformed](qimage.html#transformed)（ ）函数返回的转化与给定的变换矩阵与变换模式的图像的副本：在内部，该变换矩阵进行调整，以补偿不需要翻译，即[transformed](qimage.html#transformed)（ ）返回一个包含原始图像的所有变换的点的最小图像。静[trueMatrix](qimage.html#trueMatrix)（）函数返回用于变换图像的实际矩阵。

也有用于改变就地图像的属性功能：

| Function | Description |
| --- | --- |
| [setDotsPerMeterX](qimage.html#setDotsPerMeterX)() | Defines the aspect ratio by setting the number of pixels that fit horizontally in a physical meter. |
| [setDotsPerMeterY](qimage.html#setDotsPerMeterY)() | Defines the aspect ratio by setting the number of pixels that fit vertically in a physical meter. |
| [fill](qimage.html#fill)() | Fills the entire image with the given pixel value. |
| [invertPixels](qimage.html#invertPixels)() | Inverts all pixel values in the image using the given [InvertMode](qimage.html#InvertMode-enum) value. |
| [setColorTable](qimage.html#setColorTable)() | Sets the color table used to translate color indexes. Only monochrome and 8-bit formats. |
| [setColorCount](qimage.html#setColorCount)() | Resizes the color table. Only monochrome and 8-bit formats. |

### Legal Information

对于平滑缩放，[transformed](qimage.html#transformed)（ ）函数使用的代码基础上由Daniel M. Duley平滑缩放算法。

版权所有（C ） 2004，2005丹尼尔米Duley

再分配和在源代码和二进制形式的使用，无论修改与否，都允许下列条件：

1 。源代码的再分发必须保留上述版权声明，此条件列表和以下免责声明。 2 。以二进制形式再分发必须复制上述版权声明，此条件列表和文档和/或随分发提供的其他材料中的下列免责声明。

本软件是由作者``原样''任何明示或暗示的担保，包括但不限于适销性和适用性的暗示担保适用于某一特定用途的保证。在任何情况下，作者均不对任何直接的，间接的，附带的，特殊的，惩罚性的或后果性的损害（包括但不限于购买替代商品或服务，使用损失，数据丢失或利润损失或业务中断）而引起的任何责任理论，无论是在合同，严格赔偿责任或民事侵权行为（包括疏忽或其它）以任何方式产生出这种软件的使用，即使已被告知发生此类损害的可能性。

* * *

## Type Documentation

```
QImage.Format
```

下面的图像格式，可在Qt的。值大于QImage.Format_RGB16分别加入Qt的4.4 。请参阅下表后的注意事项。

| Constant | Value | Description |
| --- | --- | --- |
| `QImage.Format_Invalid` | `0` | 该图像是无效的。 |
| `QImage.Format_Mono` | `1` | 该图像是使用每像素1位的存储。字节首先挤满了最显着的位（MSB ） 。 |
| `QImage.Format_MonoLSB` | `2` | 该图像是使用每像素1位的存储。字节首先挤满了少显着位（LSB ） 。 |
| `QImage.Format_Indexed8` | `3` | 该图像是用8位的索引为一个颜色表存储。 |
| `QImage.Format_RGB32` | `4` | 该图像是使用一个32位的RGB格式（ 0xffRRGGBB ）存储。 |
| `QImage.Format_ARGB32` | `5` | 该图像是使用一个32位ARGB格式（ 0xAARRGGBB ）存储。 |
| `QImage.Format_ARGB32_Premultiplied` | `6` | 该图像是使用预乘32位ARGB格式（ 0xAARRGGBB ）存储，即红色，绿色和蓝色通道是由alpha分量除以255乘以。 （如果RR，GG或BB有更高的价值比alpha通道，结果是不确定的。 ）某些操作（如使用alpha混合图像组合物）使用速度更快左乘ARGB32比普通ARGB32 。 |
| `QImage.Format_RGB16` | `7` | 该图像是使用一个16位的RGB格式（ 5-6-5 ）存储。 |
| `QImage.Format_ARGB8565_Premultiplied` | `8` | 该图像是使用预乘24位ARGB格式（ 8-5-6-5 ）存储。 |
| `QImage.Format_RGB666` | `9` | 该图像是用一个24位的RGB格式（ 6-6-6 ）存储。未使用的最显着的位始终为零。 |
| `QImage.Format_ARGB6666_Premultiplied` | `10` | 该图像是使用预乘24位ARGB格式（ 6-6-6-6 ）存储。 |
| `QImage.Format_RGB555` | `11` | 该图像是使用一个16位的RGB格式（ 5-5-5 ）存储。未使用的最显着位始终为零。 |
| `QImage.Format_ARGB8555_Premultiplied` | `12` | 该图像是使用预乘24位ARGB格式（ 8-5-5-5 ）存储。 |
| `QImage.Format_RGB888` | `13` | 该图像是用一个24位的RGB格式（ 8-8-8 ）存储。 |
| `QImage.Format_RGB444` | `14` | 该图像是使用一个16位的RGB格式（ 4-4-4 ）存储。未使用的位始终为零。 |
| `QImage.Format_ARGB4444_Premultiplied` | `15` | 该图像是使用预乘16位ARGB格式（ 4-4-4-4 ）存储。 |

**Note:**拉丝成[QImage](qimage.html)与QImage.Format_Indexed8不支持。

**Note:**不要渲染成ARGB32使用的图像[QPainter](qpainter.html)。使用QImage.Format_ARGB32_Premultiplied是显着更快。

**See also** [format](qimage.html#format)（）和[convertToFormat](qimage.html#convertToFormat)（ ） 。

```
QImage.InvertMode
```

该枚举类型用于描述如何像素值应在倒[invertPixels](qimage.html#invertPixels)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QImage.InvertRgb` | `0` | 仅反转的RGB值，并保留alpha通道不变。 |
| `QImage.InvertRgba` | `1` | 反转所有通道，包括Alpha通道。 |

**See also** [invertPixels](qimage.html#invertPixels)（ ） 。

* * *

## Method Documentation

```
QImage.__init__ (self)
```

构造一个空图像。

**See also** [isNull](qimage.html#isNull)（ ） 。

```
QImage.__init__ (self, QSize size, Format format)
```

构造一个图像与给定的_size_和_format_。

A [null](qimage.html#isNull)如果内存无法分配图像返回。

**Warning:**这将创建一个[QImage](qimage.html)与未初始化的数据。通话[fill](qimage.html#fill)（ ）与绘制到它之前，以填补一个合适的像素值的图像[QPainter](qpainter.html)。

```
QImage.__init__ (self, int width, int height, Format format)
```

构造一个图像与给定的_width_，_height_和_format_。

A [null](qimage.html#isNull)如果内存无法分配图像将被退回。

**Warning:**这将创建一个[QImage](qimage.html)与未初始化的数据。通话[fill](qimage.html#fill)（ ）与绘制到它之前，以填补一个合适的像素值的图像[QPainter](qpainter.html)。

```
QImage.__init__ (self, str data, int width, int height, Format format)
```

构造一个图像与给定的_width_，_height_和_format_，使用现有的内存缓冲区，_data_。该_width_和_height_必须以像素为单位来指定，_data_必须是32位对齐的，并且在图像数据的每一个的扫描线也必须是32位对齐的。

该缓冲区必须保持有效的整个的生命[QImage](qimage.html)。图像不会删除缓冲区破坏。

If _format_是一种索引颜色格式，图像颜色表开始是空的，必须充分扩展了[setColorCount](qimage.html#setColorCount)（）或[setColorTable](qimage.html#setColorTable)（）的图像被使用之前。

```
QImage.__init__ (self, sip.voidptr data, int width, int height, Format format)
```

构造一个图像与给定的_width_，_height_和_format_中，使用现有的只读存储器缓冲器，_data_。该_width_和_height_必须以像素为单位来指定，_data_必须是32位对齐的，并且在图像数据的每一个的扫描线也必须是32位对齐的。

该缓冲区必须保持有效的整个的生命[QImage](qimage.html)而那些没有被修改或以其他方式脱离了原来的缓冲区中的所有副本。图像不会删除缓冲区破坏。

If _format_是一种索引颜色格式，图像颜色表开始是空的，必须充分扩展了[setColorCount](qimage.html#setColorCount)（）或[setColorTable](qimage.html#setColorTable)（）的图像被使用之前。

不同于类似[QImage](qimage.html)构造函数接受一个非const数据缓冲区，该版本将永远不会改变缓冲区的内容。例如，调用[QImage.bits](qimage.html#bits)（ ）将返回图像的深层副本，而不是缓冲区传递给构造函数。这使得构建的效率[QImage](qimage.html)从原始数据，而不对原始数据被改变的可能性。

```
QImage.__init__ (self, str data, int width, int height, int bytesPerLine, Format format)
```

构造一个图像与给定的_width_，_height_和_format_，使用现有的内存缓冲区，_data_。该_width_和_height_必须以像素为单位来指定。_bytesPerLine_指定每行（步幅）的字节数。

该缓冲区必须保持有效的整个的生命[QImage](qimage.html)。图像不会删除缓冲区破坏。

If _format_是一种索引颜色格式，图像颜色表开始是空的，必须充分扩展了[setColorCount](qimage.html#setColorCount)（）或[setColorTable](qimage.html#setColorTable)（）的图像被使用之前。

```
QImage.__init__ (self, sip.voidptr data, int width, int height, int bytesPerLine, Format format)
```

构造一个图像与给定的_width_，_height_和_format_，使用现有的内存缓冲区，_data_。该_width_和_height_必须以像素为单位来指定。_bytesPerLine_指定每行（步幅）的字节数。

该缓冲区必须保持有效的整个的生命[QImage](qimage.html)。图像不会删除缓冲区破坏。

If _format_是一种索引颜色格式，图像颜色表开始是空的，必须充分扩展了[setColorCount](qimage.html#setColorCount)（）或[setColorTable](qimage.html#setColorTable)（）的图像被使用之前。

不同于类似[QImage](qimage.html)构造函数接受一个非const数据缓冲区，该版本将永远不会改变缓冲区的内容。例如，调用[QImage.bits](qimage.html#bits)（ ）将返回图像的深层副本，而不是缓冲区传递给构造函数。这使得构建的效率[QImage](qimage.html)从原始数据，而不对原始数据被改变的可能性。

```
QImage.__init__ (self, list-of-str xpm)
```

构造一个图像从给定的_xpm_图像。

确保图像是一个有效的XPM图像。错误被忽略。

请注意，它可能通过使用一个不同寻常的声明挤压XPM变量一点点：

```
 static const char * const start_xpm[] = {
     "16 15 8 1",
     "a c #cec6bd",
 ....

```

额外的`const`使得整个定义为只读，这会更有效（例如，当代码是在一个共享库），并能够存储在ROM中的应用程序。

```
QImage.__init__ (self, QString fileName, str format = None)
```

构造一个图像，并尝试从该文件与给定的加载图像_fileName_。

加载器会尝试使用指定的读取图像_format_。如果_format_未指定（这是默认值） ，加载器探测文件的标题来猜测文件格式。

如果图像的装载失败，这个对象是一个空的图像。

文件名可以是指在磁盘上的实际文件或应用的嵌入式资源之一。请参阅[Resource System](index.htm)概述有关如何嵌入在应用程序的可执行映像和其他资源文件的详细信息。

**See also** [isNull](qimage.html#isNull)（）和[Reading and Writing Image Files](qimage.html#reading-and-writing-image-files)。

```
QImage.__init__ (self, QImage)
```

构造一个图像，并尝试从该文件与给定的加载图像_fileName_。

加载器会尝试使用指定的读取图像_format_。如果_format_未指定（这是默认值） ，加载器探测文件的标题来猜测文件格式。

如果图像的装载失败，这个对象是一个空的图像。

文件名可以是指在磁盘上的实际文件或应用的嵌入式资源之一。请参阅[Resource System](index.htm)概述有关如何嵌入在应用程序的可执行映像和其他资源文件的详细信息。

您可以通过定义禁用此构造函数`QT_NO_CAST_FROM_ASCII`当您编译您的应用程序。这可能是有用的，例如，如果你想确保所有用户可见的字符串经过[QObject.tr](qobject.html#tr)（ ） 。

**See also** [QString.fromAscii](qstring.html#fromAscii)（ ）[isNull](qimage.html#isNull)（）和[Reading and Writing Image Files](qimage.html#reading-and-writing-image-files)。

```
QImage.__init__ (self, QVariant variant)
```

构造给定的浅表副本_image_。

如需浅副本的详细信息，请参阅[Implicit Data Sharing](index.htm#implicit-data-sharing)文档。

**See also** [copy](qimage.html#copy)（ ） 。

```
bool QImage.allGray (self)
```

返回True如果图像中所有的颜色都是灰色的（也就是他们的红色，绿色和蓝色成分相同）的阴影，否则为False 。

注意，这个函数是没有颜色表的图像缓慢。

**See also** [isGrayscale](qimage.html#isGrayscale)（ ） 。

```
QImage QImage.alphaChannel (self)
```

[

```
int QImage.bitPlaneCount (self)
```

返回的图像中的位平面的数目。

位平面的数目为颜色和透明度信息对每个像素的比特数。这是从深度（即小于）时，图像格式包含未用的比特不同。

此功能被引入Qt的4.7 。

](qimage.html)

[**See also**](qimage.html) [depth](qimage.html#depth)（ ）[format](qimage.html#format)（）和[Image Formats](qimage.html#image-formats)。

```
sip.voidptr QImage.bits (self)
```

将指针返回到所述第一像素数据。这相当于扫描线（0）。

需要注意的是[QImage](qimage.html) uses [implicit data sharing](index.htm#implicit-data-sharing)。这个函数执行的共享像素数据的深层副本，从而确保这[QImage](qimage.html)可使用现行的返回值是唯一一个。

**See also** [scanLine](qimage.html#scanLine)（ ）[byteCount](qimage.html#byteCount)（）和[constBits](qimage.html#constBits)（ ） 。

```
int QImage.byteCount (self)
```

返回由图像数据所佔用的字节数。

此功能被引入Qt的4.6 。

**See also** [bytesPerLine](qimage.html#bytesPerLine)（ ）[bits](qimage.html#bits)（）和[Image Information](qimage.html#image-information)。

```
int QImage.bytesPerLine (self)
```

返回每幅图像扫描线的字节数。

这等效于[byteCount](qimage.html#byteCount)（）/[height](qimage.html#height)（ ） 。

**See also** [scanLine](qimage.html#scanLine)（ ） 。

```
int QImage.cacheKey (self)
```

返回一个数字，用于标识此内容[QImage](qimage.html)对象。不同[QImage](qimage.html)对象只能具有相同的密钥，如果它们指的是相同的内容。

该键将改变当图像被改变。

```
int QImage.color (self, int i)
```

在索引返回的颜色的颜色表_i_。第一种颜色的索引为0 。

图像中的颜色表中的颜色指定为ARGB四胞胎（[QRgb](qcolor.html#QRgb-typedef)） 。使用[qAlpha](index.htm#qAlpha)（ ）[qRed](index.htm#qRed)（ ）[qGreen](index.htm#qGreen)（）和[qBlue](index.htm#qBlue)（ ）函数来获取颜色值的组件。

**See also** [setColor](qimage.html#setColor)（ ）[pixelIndex](qimage.html#pixelIndex)（）和[Pixel Manipulation](qimage.html#pixel-manipulation)。

```
int QImage.colorCount (self)
```

返回颜色表的图像的大小。

请注意， colorCount （ ）返回0表示32位色的图像，因为这些图像不使用颜色表，而是编码的像素值作为ARGB四胞胎。

此功能被引入Qt的4.6 。

**See also** [setColorCount](qimage.html#setColorCount)（）和[Image Information](qimage.html#image-information)。

```
list-of-int QImage.colorTable (self)
```

返回包含在图像的颜色表中的颜色列表，或者一个空列表，如果图像没有颜色表

**See also** [setColorTable](qimage.html#setColorTable)（ ）[colorCount](qimage.html#colorCount)（）和[color](qimage.html#color)（ ） 。

```
sip.voidptr QImage.constBits (self)
```

将指针返回到所述第一像素数据。

需要注意的是[QImage](qimage.html) uses [implicit data sharing](index.htm#implicit-data-sharing)，但这个函数_not_执行共享像素数据的深层副本，因为返回的数据是常量。

此功能被引入Qt的4.7 。

**See also** [bits](qimage.html#bits)（）和[constScanLine](qimage.html#constScanLine)（ ） 。

```
sip.voidptr QImage.constScanLine (self, int)
```

返回一个指针，指向像素数据与索引扫描线_i_。第一个扫描行的索引为0 。

该扫描线数据是对齐的32位边界。

需要注意的是[QImage](qimage.html) uses [implicit data sharing](index.htm#implicit-data-sharing)，但这个函数_not_执行共享像素数据的深层副本，因为返回的数据是常量。

此功能被引入Qt的4.7 。

**See also** [scanLine](qimage.html#scanLine)（）和[constBits](qimage.html#constBits)（ ） 。

```
QImage QImage.convertToFormat (self, Format format, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

[

返回图像的一个副本在给定的_format_。

指定的图像转换_flags_控制如何在转换过程中的图像数据被处理。

](qimage.html)

[**See also**](qimage.html) [Image Format](qimage.html#image-formats)。

```
QImage QImage.convertToFormat (self, Format format, list-of-int colorTable, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

[

这是一个重载函数。

返回的图像的副本转换为给定_format_使用指定的_colorTable_。

从32位到8位索引转换是一个缓慢的操作，将使用一个简单的最接近的颜色的方法，无抖动。

](qimage.html)

```
QImage QImage.copy (self, QRect rect = QRect())
```

[

返回图像的子区域作为一个新的形象。

返回的图像从位置复制（_rectangle_， X（ ） ，_rectangle_， Y（ ） ）在这个形象，并总是具有给定的尺寸_rectangle_。

](qimage.html)

[在此以外的图像区域，像素被设置为0。对于32位RGB图像，这意味着黑，为32位ARGB图像，这意味着透明的黑色;为8位图像，这意味着索引为0的颜色表，可以是任何颜色， 1位图像中，这意味着](qimage.html)[Qt.color0](qt.html#GlobalColor-enum)。

如果给定的_rectangle_是一个空矩形整个图像被复制。

**See also** [QImage](qimage.html#QImage)（ ） 。

```
QImage QImage.copy (self, int x, int y, int w, int h)
```

[](qimage.html)

```
QImage QImage.createAlphaMask (self, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

[](qimage.html)

[构建并从该图像的alpha缓冲区返回1 BPP掩码。返回一个空图像，如果图像的格式是](qimage.html)[QImage.Format_RGB32](qimage.html#Format-enum)。

该_flags_参数是的一个按位或[Qt.ImageConversionFlags](qt.html#ImageConversionFlag-enum)和控制转换过程。路过0标志设置所有默认选项。

返回的图像有小端位顺序（即图像的格式是[QImage.Format_MonoLSB](qimage.html#Format-enum)） ，你可以转换为大端（[QImage.Format_Mono](qimage.html#Format-enum)）使用[convertToFormat](qimage.html#convertToFormat)（）函数。

**See also** [createHeuristicMask](qimage.html#createHeuristicMask)（）和[Image Transformations](qimage.html#image-transformations)。

```
QImage QImage.createHeuristicMask (self, bool clipTight = True)
```

[

创建并返回一个1 - BPP启发式掩码这一形象。

该功能的工作原理是从一个角选择一种颜色，然后小打小闹的颜色开始的像素，所有的边缘。四角投票的颜色是被屏蔽了。的情况下的拉伸（这通常意味着这个函数是不适用的图像） ，其结果是任意的。

](qimage.html)

[返回的图像有小端位顺序（即图像的格式是](qimage.html)[QImage.Format_MonoLSB](qimage.html#Format-enum)） ，你可以转换为大端（[QImage.Format_Mono](qimage.html#Format-enum)）使用[convertToFormat](qimage.html#convertToFormat)（）函数。

If _clipTight_为True（默认值）的面具只是大到足以复盖的像素，否则，面膜比数据像素。

注意，这个函数会忽略的alpha缓冲区。

**See also** [createAlphaMask](qimage.html#createAlphaMask)（）和[Image Transformations](qimage.html#image-transformations)。

```
QImage QImage.createMaskFromColor (self, int color, Qt.MaskMode mode = Qt.MaskInColor)
```

[

创建并返回的基础上，给出了这一形象口罩_color_值。如果_mode_是MaskInColor （默认值） ，所有像素匹配_color_将不透明像素的掩模。如果_mode_是MaskOutColor ，匹配给定颜色的所有像素将是透明的。

](qimage.html)

[**See also**](qimage.html) [createAlphaMask](qimage.html#createAlphaMask)（）和[createHeuristicMask](qimage.html#createHeuristicMask)（ ） 。

```
int QImage.depth (self)
```

返回图像的深度。

图像深度是用来存储一个像素的比特数，也称为每像素（bpp ）位。

支持的深度是1 ， 8 ， 16 ， 24和32 。

**See also** [bitPlaneCount](qimage.html#bitPlaneCount)（ ）[convertToFormat](qimage.html#convertToFormat)（ ）[Image Formats](qimage.html#image-formats)和[Image Information](qimage.html#image-information)。

```
QImage.detach (self)
```

```
int QImage.devType (self)
```

```
int QImage.dotsPerMeterX (self)
```

返回适合水平地在一个物理米的像素的数目。再加上[dotsPerMeterY](qimage.html#dotsPerMeterY)（），这个数定义期望的规模和图像的纵横比。

**See also** [setDotsPerMeterX](qimage.html#setDotsPerMeterX)（）和[Image Information](qimage.html#image-information)。

```
int QImage.dotsPerMeterY (self)
```

返回适合垂直于一个物理米的像素的数目。再加上[dotsPerMeterX](qimage.html#dotsPerMeterX)（），这个数定义期望的规模和图像的纵横比。

**See also** [setDotsPerMeterY](qimage.html#setDotsPerMeterY)（）和[Image Information](qimage.html#image-information)。

```
QImage.fill (self, Qt.GlobalColor color)
```

填充整个图像具有给定_pixelValue_。

如果这个图像的深度为1，只有最低位被使用。如果你说填（ 0 ） ，填充（ 2 ）等，图像充满了0。如果你说的填写（ 1 ） ，填充（ 3 ）等，图像充满了1秒。如果深度是8 ，最低的8位被使用，如果深度为16的最低16比特的使用。

注意：[QImage.pixel](qimage.html#pixel)（ ）返回像素的颜色，而在给定坐标[QColor.pixel](index.htm#pixel)（ ）返回底层窗口系统（本质上是一个索引值）的像素值，因此通常你会希望使用[QImage.pixel](qimage.html#pixel)（）使用从现有的图像的颜色或[QColor.rgb](qcolor.html#rgb)（）使用特定的颜色。

**See also** [depth](qimage.html#depth)（）和[Image Transformations](qimage.html#image-transformations)。

```
QImage.fill (self, QColor color)
```

这是一个重载函数。

填充图像与给定的_color_，描述为一个标准的全球色彩。

此功能被引入Qt的4.8 。

```
QImage.fill (self, int pixel)
```

这是一个重载函数。

填充整个图像具有给定_color_。

如果图像的深度为1 ，则图像将充满1如果_color_等于[Qt.color1](qt.html#GlobalColor-enum)它否则将被填0。

如果图像的深度是8 ，该图像将被填充的索引对应的_color_在颜色表中如果存在的话，它会以其他方式填0。

此功能被引入Qt的4.8 。

```
Format QImage.format (self)
```

[

返回的图像的格式。

](qimage.html#Format-enum)

[**See also**](qimage.html#Format-enum) [Image Formats](qimage.html#image-formats)。

```
QImage QImage.fromData (str data, str format = None)
```

[](qimage.html)

[构造一个](qimage.html)[QImage](qimage.html)从第一_size_给定的二进制字节_data_。加载器会尝试使用指定的读取图像_format_。如果_format_未指定（这是默认值） ，加载器探测文件的标题来猜测文件格式。二进制_data_。装载机尝试读取图像，或者使用可选的图像_format_指定或通过确定从数据的图像格式。

If _format_未指定（这是默认值） ，加载器探针头的文件，以确定该文件的格式。如果_format_被指定，它必须是通过返回的值之一[QImageReader.supportedImageFormats](qimagereader.html#supportedImageFormats)（ ） 。

如果图像的装载失败，返回的图像将是一个空的图像。

**See also** [load](qimage.html#load)（ ）[save](qimage.html#save)（）和[Reading and Writing Image Files](qimage.html#reading-and-writing-image-files)。

```
QImage QImage.fromData (QByteArray data, str format = None)
```

[

这是一个重载函数。

](qimage.html)

[加载一个图像从给定的](qimage.html)[QByteArray](qbytearray.html) _data_。

```
bool QImage.hasAlphaChannel (self)
```

返回True如果图像有一个尊重的alpha通道的格式，否则返回False 。

**See also** [Image Information](qimage.html#image-information)。

```
int QImage.height (self)
```

返回图像的高度。

**See also** [Image Information](qimage.html#image-information)。

```
QImage.invertPixels (self, InvertMode mode = QImage.InvertRgb)
```

反转图像中的所有像素值。

给定的倒置_mode_只有一个意义时，图像的深度为32。默认_mode_ is [InvertRgb](qimage.html#InvertMode-enum)，这让alpha通道不变。如果_mode_ is [InvertRgba](qimage.html#InvertMode-enum)中，α位也反转。

反相一个8位图像是指采用显色指数，以取代所有像素_i_使用显色指数255减去像素_i_。同样是一个1位的图像的情况。注意，颜色表是_not_改变。

**See also** [Image Transformations](qimage.html#image-transformations)。

```
bool QImage.isDetached (self)
```

```
bool QImage.isGrayscale (self)
```

对于32位图像，这个功能相当于[allGray](qimage.html#allGray)（ ） 。

对于8位色的图像，这个功能如果颜色（ i）为返回True[QRgb](qcolor.html#QRgb-typedef)（ I， I，I ）的颜色表的所有索引，否则返回False 。

**See also** [allGray](qimage.html#allGray)（）和[Image Formats](qimage.html#image-formats)。

```
bool QImage.isNull (self)
```

返回True ，如果它是一个空图像，否则返回False 。

一个空的图像具有设置为零的所有参数，没有分配的数据。

```
bool QImage.load (self, QIODevice device, str format)
```

加载一个图像从文件中给定的_fileName_。返回True如果成功加载图像，否则返回False 。

加载器会尝试使用指定的读取图像_format_，例如， PNG或JPG格式。如果_format_未指定（这是默认值） ，加载器探测文件的标题来猜测文件格式。

文件名可以是指在磁盘上的实际文件或应用的嵌入式资源之一。请参阅[Resource System](index.htm)概述有关如何嵌入在应用程序的可执行映像和其他资源文件的详细信息。

**See also** [Reading and Writing Image Files](qimage.html#reading-and-writing-image-files)。

```
bool QImage.load (self, QString fileName, str format = None)
```

这是一个重载函数。

该函数读取[QImage](qimage.html)从给定的_device_。这可以，例如，可以用来直接将图像加载到一个[QByteArray](qbytearray.html)。

```
bool QImage.loadFromData (self, str data, str format = None)
```

加载一个图像从第一_len_给定的二进制字节_data_。返回True如果成功加载图像，否则返回False 。

加载器会尝试使用指定的读取图像_format_，例如， PNG或JPG格式。如果_format_未指定（这是默认值） ，加载器探测文件的标题来猜测文件格式。

**See also** [Reading and Writing Image Files](qimage.html#reading-and-writing-image-files)。

```
bool QImage.loadFromData (self, QByteArray data, str format = None)
```

这是一个重载函数。

加载一个图像从给定的[QByteArray](qbytearray.html) _data_。

```
int QImage.metric (self, QPaintDevice.PaintDeviceMetric metric)
```

```
QImage QImage.mirrored (self, bool horizontal = False, bool vertical = True)
```

[

返回图像的镜像，镜像中的水平和/或垂直方向取决于是否_horizontal_和_vertical_被设置为True或False 。

请注意，原始图像没有改变。

](qimage.html)

[**See also**](qimage.html) [Image Transformations](qimage.html#image-transformations)。

```
int QImage.numBytes (self)
```

```
int QImage.numColors (self)
```

```
QPoint QImage.offset (self)
```

[

返回由该图像的目的是当定位相对于其它图像由被抵消的像素的数目。

](qpoint.html)

[**See also**](qpoint.html) [setOffset](qimage.html#setOffset)() and [Image Information](qimage.html#image-information).

```
QPaintEngine QImage.paintEngine (self)
```

[

```
int QImage.pixel (self, QPoint pt)
```

返回该像素的颜色在给定的_position_。

如果_position_是无效的，结果是不确定的。

**Warning:**此功能是昂贵的用于大规模的像素操作时。

](qpaintengine.html)

[**See also**](qpaintengine.html) [setPixel](qimage.html#setPixel)（ ）[valid](qimage.html#valid)（）和[Pixel Manipulation](qimage.html#pixel-manipulation)。

```
int QImage.pixel (self, int x, int y)
```

这是一个重载函数。

返回该像素的颜色坐标（_x_，_y_） 。

```
int QImage.pixelIndex (self, QPoint pt)
```

返回的像素指数在给定的_position_。

If _position_是无效的，或者如果图像是不是一个调色板图像（[depth](qimage.html#depth)（ ） \u003e 8 ） ，结果是不确定的。

**See also** [valid](qimage.html#valid)（ ）[depth](qimage.html#depth)（）和[Pixel Manipulation](qimage.html#pixel-manipulation)。

```
int QImage.pixelIndex (self, int x, int y)
```

这是一个重载函数。

返回像素的索引（_x_，_y_） 。

```
QRect QImage.rect (self)
```

[](qrect.html)

[返回的包围矩形（ 0，0，](qrect.html)[width](qimage.html#width)（ ）[height](qimage.html#height)的图像（））。

**See also** [Image Information](qimage.html#image-information)。

```
QImage QImage.rgbSwapped (self)
```

[](qimage.html)

[返回](qimage.html)[QImage](qimage.html)在其中的所有像素的红色和蓝色分量的值被交换，有效地转换为RGB图像到一个BGR图像。

原[QImage](qimage.html)不改变。

**See also** [Image Transformations](qimage.html#image-transformations)。

```
bool QImage.save (self, QString fileName, str format = None, int quality = -1)
```

的图像保存到文件中与给定的_fileName_，使用给定的图像文件_format_和_quality_因素。如果_format_为0时，[QImage](qimage.html)将尝试通过观察来猜测格式_fileName_的后缀。

该_quality_因子必须介于0到100或-1 。指定0以获得小的压缩文件， 100为大型无压缩文件，并-1（默认值）来使用默认设置。

返回True如果图像保存成功，否则返回False 。

**See also** [Reading and Writing Image Files](qimage.html#reading-and-writing-image-files)。

```
bool QImage.save (self, QIODevice device, str format = None, int quality = -1)
```

这是一个重载函数。

该函数将一个[QImage](qimage.html)为给定的_device_。

这可以，例如，可以用于图像直接保存成[QByteArray](qbytearray.html)：

```
         [QImage](qimage.html) image;
         [QByteArray](qbytearray.html) ba;
         [QBuffer](qbuffer.html) buffer(&ba);
         buffer.open([QIODevice](qiodevice.html).WriteOnly);
         image.save(&buffer, "PNG"); // writes image into ba in PNG format

```

```
QImage QImage.scaled (self, int width, int height, Qt.AspectRatioMode aspectRatioMode = Qt.IgnoreAspectRatio, Qt.TransformationMode transformMode = Qt.FastTransformation)
```

[

返回图像的缩放副本由给定定义的矩形_size_根据给定的_aspectRatioMode_和_transformMode_。

![](../img/qimage-scaling.png)

](qimage.html)

[](qimage.html)
*   [If _aspectRatioMode_ is](qimage.html) [Qt.IgnoreAspectRatio](qt.html#AspectRatioMode-enum), the image is scaled to _size_.
*   If _aspectRatioMode_ is [Qt.KeepAspectRatio](qt.html#AspectRatioMode-enum), the image is scaled to a rectangle as large as possible inside _size_, preserving the aspect ratio.
*   If _aspectRatioMode_ is [Qt.KeepAspectRatioByExpanding](qt.html#AspectRatioMode-enum), the image is scaled to a rectangle as small as possible outside _size_, preserving the aspect ratio.

如果给定的_size_是空的，这个函数返回一个空的图像。

**See also** [isNull](qimage.html#isNull)（）和[Image Transformations](qimage.html#image-transformations)。

```
QImage QImage.scaled (self, QSize size, Qt.AspectRatioMode aspectRatioMode = Qt.IgnoreAspectRatio, Qt.TransformationMode transformMode = Qt.FastTransformation)
```

[

这是一个重载函数。

返回图像的缩放，以一个矩形与给定的副本_width_和_height_根据给定的_aspectRatioMode_和_transformMode_。

如果任何一个_width_或_height_为零或负数，则该函数返回一个空的图像。

](qimage.html)

```
QImage QImage.scaledToHeight (self, int height, Qt.TransformationMode mode = Qt.FastTransformation)
```

[

返回图像的缩放复印。返回的图像被缩放为给定的_height_使用指定的变换_mode_。

这个函数自动计算的图像的宽度，以使图像的比率被保持。

如果给定的_height_为0或负数，则返回一个空的图像。

](qimage.html)

[**See also**](qimage.html) [Image Transformations](qimage.html#image-transformations)。

```
QImage QImage.scaledToWidth (self, int width, Qt.TransformationMode mode = Qt.FastTransformation)
```

[

返回图像的缩放复印。返回的图像被缩放为给定的_width_使用指定的变换_mode_。

这个函数自动计算图像的高度，使得其高宽比被保存下来。

如果给定的_width_为0或负数，则返回一个空的图像。

](qimage.html)

[**See also**](qimage.html) [Image Transformations](qimage.html#image-transformations)。

```
sip.voidptr QImage.scanLine (self, int)
```

返回一个指针，指向像素数据与索引扫描线_i_。第一个扫描行的索引为0 。

该扫描线数据是对齐的32位边界。

**Warning:**如果您正在访问32位色的图像数据，转换返回的指针`QRgb*`（[QRgb](qcolor.html#QRgb-typedef)有一个32位的大小） ，并用它来读取/写入的像素值。你不能使用`uchar*`直接指针，因为像素格式依赖于底层平台上的字节顺序。使用[qRed](index.htm#qRed)（ ）[qGreen](index.htm#qGreen)（ ）[qBlue](index.htm#qBlue)（）和[qAlpha](index.htm#qAlpha)（）来访问的像素。

**See also** [bytesPerLine](qimage.html#bytesPerLine)（ ）[bits](qimage.html#bits)（ ）[Pixel Manipulation](qimage.html#pixel-manipulation)和[constScanLine](qimage.html#constScanLine)（ ） 。

```
int QImage.serialNumber (self)
```

```
QImage.setAlphaChannel (self, QImage alphaChannel)
```

```
QImage.setColor (self, int i, int c)
```

设置颜色在给定的_index_在颜色表中，给定到_colorValue_。颜色值是一个ARGB四胞胎。

If _index_在颜色表的当前大小之外，它与扩展[setColorCount](qimage.html#setColorCount)（ ） 。

**See also** [color](qimage.html#color)（ ）[colorCount](qimage.html#colorCount)（ ）[setColorTable](qimage.html#setColorTable)（）和[Pixel Manipulation](qimage.html#pixel-manipulation)。

```
QImage.setColorCount (self, int)
```

调整大小，颜色表包含_colorCount_条目。

如果颜色表被扩展时，这些额外的颜色将被设置为透明的（即qRgba （0，0 ，0，0 ））。

当图像被使用时，颜色表必须足够大，以对所有存在于图像中的像素/索引值的条目，否则结果是不确定的。

此功能被引入Qt的4.6 。

**See also** [colorCount](qimage.html#colorCount)（ ）[colorTable](qimage.html#colorTable)（ ）[setColor](qimage.html#setColor)（）和[Image Transformations](qimage.html#image-transformations)。

```
QImage.setColorTable (self, list-of-int colors)
```

设置用来翻译的颜色索引颜色表[QRgb](qcolor.html#QRgb-typedef)值，与指定_colors_。

当图像被使用时，颜色表必须足够大，以对所有存在于图像中的像素/索引值的条目，否则结果是不确定的。

**See also** [colorTable](qimage.html#colorTable)（ ）[setColor](qimage.html#setColor)（）和[Image Transformations](qimage.html#image-transformations)。

```
QImage.setDotsPerMeterX (self, int)
```

设置适合于水平方向的物理米的像素的数目，以_x_。

再加上[dotsPerMeterY](qimage.html#dotsPerMeterY)（），这个数定义期望的规模和图像的纵横比，并确定比例在其中[QPainter](qpainter.html)将在图像上绘制图形。它不改变时，它是在其他绘图设备上呈现的图像的比例或纵横比。

**See also** [dotsPerMeterX](qimage.html#dotsPerMeterX)（）和[Image Information](qimage.html#image-information)。

```
QImage.setDotsPerMeterY (self, int)
```

设置适合垂直于一个物理米的像素的数目，以_y_。

再加上[dotsPerMeterX](qimage.html#dotsPerMeterX)（），这个数定义期望的规模和图像的纵横比，并确定比例在其中[QPainter](qpainter.html)将在图像上绘制图形。它不改变时，它是在其他绘图设备上呈现的图像的比例或纵横比。

**See also** [dotsPerMeterY](qimage.html#dotsPerMeterY)（）和[Image Information](qimage.html#image-information)。

```
QImage.setNumColors (self, int)
```

```
QImage.setOffset (self, QPoint)
```

设置由所述图像的目的是当定位相对于其他图像，以此作为偏移量的像素数_offset_。

**See also** [offset](qimage.html#offset)（）和[Image Information](qimage.html#image-information)。

```
QImage.setPixel (self, QPoint pt, int index_or_rgb)
```

设置在像素索引或颜色在给定的_position_至_index_or_rgb_。

如果图像的格式可以是单色或8位，在给定_index_or_rgb_值必须是一个索引图像的颜色表，否则该参数必须是一个[QRgb](qcolor.html#QRgb-typedef)值。

If _position_不是一个有效的坐标对图像中，或者如果_index_or_rgb_\u003e =[colorCount](qimage.html#colorCount)（ ）在单色和8位图像的情况下，结果是不确定的。

**Warning:**这个功能是昂贵的，由于内部的呼叫`detach()`函数调用中，如果性能是一个问题，我们建议使用[scanLine()](qimage.html#scanLine)以直接访问的像素数据。

**See also** [pixel](qimage.html#pixel)（）和[Pixel Manipulation](qimage.html#pixel-manipulation)。

```
QImage.setPixel (self, int x, int y, int index_or_rgb)
```

这是一个重载函数。

设定像素索引或颜色的（_x_，_y_）至_index_or_rgb_。

```
QImage.setText (self, QString key, QString value)
```

设置图像的文字给定的_text_并将它与给定的关联_key_。

如果你只是想存储一个单一的文本块（即“注释”或只是一个描述） ，你可以传递一个空键，或使用如“描述”一个通用密钥。

图像的文字嵌入到图像数据，当你调用[save](qimage.html#save)（）或[QImageWriter.write](qimagewriter.html#write)（ ） 。

不是所有的图像格式支持嵌入式文本。你可以发现，如果一个特定的图像格式，或通过使用支持嵌入文本[QImageWriter.supportsOption](qimagewriter.html#supportsOption)（ ） 。我们举一个例子：

```
         [QImageWriter](qimagewriter.html) writer;
         writer.setFormat("png");
         if (writer.supportsOption([QImageIOHandler](qimageiohandler.html).Description))
             qDebug() << "Png supports embedded text";

```

您可以使用[QImageWriter.supportedImageFormats](qimagewriter.html#supportedImageFormats)（）来找出哪些图像格式提供给您。

**See also** [text](qimage.html#text)（）和[textKeys](qimage.html#textKeys)（ ） 。

```
QSize QImage.size (self)
```

[](qsize.html)

[返回的图像的尺寸，即其](qsize.html)[width](qimage.html#width)（）和[height](qimage.html#height)（ ） 。

**See also** [Image Information](qimage.html#image-information)。

```
QImage.swap (self, QImage other)
```

掉期图像_other_与此图像。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QString QImage.text (self, QString key = QString())
```

返回与给定关联的图像文本_key_。如果指定的_key_是一个空字符串，则返回整个图像的文字，每个按键文对用换行分隔。

**See also** [setText](qimage.html#setText)（）和[textKeys](qimage.html#textKeys)（ ） 。

```
QStringList QImage.textKeys (self)
```

返回文本键这一形象。

您可以使用这些按键与[text](qimage.html#text)（ ）列出图像文本的某些关键。

**See also** [text](qimage.html#text)（ ） 。

```
QImage QImage.transformed (self, QMatrix matrix, Qt.TransformationMode mode = Qt.FastTransformation)
```

[

传回的图像，是利用给定的变换转化副本_matrix_改造_mode_。

](qimage.html)

[改造_matrix_在内部进行调整，以补偿不希望的翻译，即所产生的图像是包含原始图像的所有变换的点的最小图像。使用](qimage.html)[trueMatrix](qimage.html#trueMatrix)（）函数来检索用于转化的图像的实际的矩阵。

**See also** [trueMatrix](qimage.html#trueMatrix)（）和[Image Transformations](qimage.html#image-transformations)。

```
QImage QImage.transformed (self, QTransform matrix, Qt.TransformationMode mode = Qt.FastTransformation)
```

[

传回的图像，是利用给定的变换转化副本_matrix_改造_mode_。

](qimage.html)

[改造_matrix_在内部进行调整，以补偿不希望的翻译，即所产生的图像是包含原始图像的所有变换的点的最小图像。使用](qimage.html)[trueMatrix](qimage.html#trueMatrix)（）函数来检索用于转化的图像的实际的矩阵。

不像其他的过载时，此功能可用于对图像进行透视变换。

**See also** [trueMatrix](qimage.html#trueMatrix)（）和[Image Transformations](qimage.html#image-transformations)。

```
QMatrix QImage.trueMatrix (QMatrix, int w, int h)
```

[

返回用于转化的图像与给定的实际的矩阵_width_，_height_和_matrix_。

](qmatrix.html)

[当使用变换的图像的](qmatrix.html)[transformed](qimage.html#transformed)（）函数，该变换矩阵是在内部调整以补偿不需要的翻译，即[transformed](qimage.html#transformed)（ ）返回一个包含原始图像的所有变换的点的最小图像。这个函数返回修改后的矩阵，正确映射点从原始图像到新的形象。

**See also** [transformed](qimage.html#transformed)（）和[Image Transformations](qimage.html#image-transformations)。

```
QTransform QImage.trueMatrix (QTransform, int w, int h)
```

[

返回用于转化的图像与给定的实际的矩阵_width_，_height_和_matrix_。

](qtransform.html)

[当使用变换的图像的](qtransform.html)[transformed](qimage.html#transformed)（）函数，该变换矩阵是在内部调整以补偿不需要的翻译，即[transformed](qimage.html#transformed)（ ）返回一个包含原始图像的所有变换的点的最小图像。这个函数返回修改后的矩阵，正确映射点从原始图像到新的形象。

不像其他的过载，此功能创建可用于上的图像进行透视变换变换矩阵。

**See also** [transformed](qimage.html#transformed)（）和[Image Transformations](qimage.html#image-transformations)。

```
bool QImage.valid (self, QPoint pt)
```

返回True如果_pos_是一种有效的坐标在图像内对;否则返回False。

**See also** [rect](qimage.html#rect)（）和[QRect.contains](qrect.html#contains)（ ） 。

```
bool QImage.valid (self, int x, int y)
```

这是一个重载函数。

返回True如果[QPoint](qpoint.html)（_x_，_y_）是一个有效的坐标在图像内对;否则返回False。

```
int QImage.width (self)
```

返回图像的宽度。

**See also** [Image Information](qimage.html#image-information)。

```
bool QImage.__eq__ (self, QImage)
```

```
bool QImage.__ne__ (self, QImage)
```