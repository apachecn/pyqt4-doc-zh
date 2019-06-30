# QImageIOHandler Class Reference

## [[QtGui](index.htm) module]

该QImageIOHandler类定义Qt中的所有图像格式的图像常见的I / O接口。[More...](#details)

### Types

*   `enum ImageOption { Size, ClipRect, Description, ScaledClipRect, ..., BackgroundColor }`

### Methods

*   `__init__ (self)`
*   `bool canRead (self)`
*   `int currentImageNumber (self)`
*   `QRect currentImageRect (self)`
*   `QIODevice device (self)`
*   `QByteArray format (self)`
*   `int imageCount (self)`
*   `bool jumpToImage (self, int imageNumber)`
*   `bool jumpToNextImage (self)`
*   `int loopCount (self)`
*   `QByteArray name (self)`
*   `int nextImageDelay (self)`
*   `QVariant option (self, ImageOption option)`
*   `bool read (self, QImage image)`
*   `setDevice (self, QIODevice device)`
*   `setFormat (self, QByteArray format)`
*   `setOption (self, ImageOption option, QVariant value)`
*   `bool supportsOption (self, ImageOption option)`
*   `bool write (self, QImage image)`

* * *

## Detailed Description

该QImageIOHandler类定义Qt中的所有图像格式的图像常见的I / O接口。

Qt使用QImageIOHandler通过读取和写入图像[QImageReader](qimagereader.html)和[QImageWriter](qimagewriter.html)。您也可以从这个类派生使用Qt的插件机制来编写自己的图像格式处理程序。

Call [setDevice](qimageiohandler.html#setDevice)（ ）到设备分配给处理程序，[setFormat](qimageiohandler.html#setFormat)（ ）的形式分配给它。一QImageIOHandler可以支持一个以上的图像格式。[canRead](qimageiohandler.html#canRead)（）返回True，如果一个图像可以从设备读取，并[read](qimageiohandler.html#read)（）和[write](qimageiohandler.html#write)（ ）返回True，如果读取或写入图像已成功完成。

QImageIOHandler也有动画格式的支持，通过功能[loopCount](qimageiohandler.html#loopCount)（ ）[imageCount](qimageiohandler.html#imageCount)（ ）[nextImageDelay](qimageiohandler.html#nextImageDelay)（）和[currentImageNumber](qimageiohandler.html#currentImageNumber)（ ） 。

为了确定哪些选项的图像处理程序支持， Qt会调用[supportsOption](qimageiohandler.html#supportsOption)（）和[setOption](qimageiohandler.html#setOption)（ ） 。请务必重新实现这些功能，如果你能提供任何在该选项的支持[ImageOption](qimageiohandler.html#ImageOption-enum)枚举。

写你自己的图像处理程序，您必须至少重新实现[canRead](qimageiohandler.html#canRead)（）和[read](qimageiohandler.html#read)（ ） 。然后创建一个[QImageIOPlugin](index.htm)它可以创建的处理程序。最后，安装插件，[QImageReader](qimagereader.html)和[QImageWriter](qimagewriter.html)将自动加载该插件，并开始使用它。

* * *

## Type Documentation

```
QImageIOHandler.ImageOption
```

这个枚举变量描述了所支持的不同选择[QImageIOHandler](qimageiohandler.html)。有些选项是用来查询的图像的性质，有些则是用来切换中的图像应该写入的方式。

| Constant | Value | Description |
| --- | --- | --- |
| `QImageIOHandler.Size` | `0` | 图像的原始尺寸。支持此选项的处理程序，预计从图像元数据读取的图像的大小，并从返回此尺寸[option](qimageiohandler.html#option)（ ），为[QSize](qsize.html)。 |
| `QImageIOHandler.ClipRect` | `1` | 剪辑矩形，或ROI （感兴趣区域） 。支持此选项的处理程序，预计只能读取提供[QRect](qrect.html)从原始图像区域[read](qimageiohandler.html#read)（ ） ，任何其他应用转换之前。 |
| `QImageIOHandler.ScaledSize` | `4` | 图像的缩放大小。支持此选项的处理程序，预计将图像缩放到所提供的尺寸（[QSize](qsize.html)） ，应用任何剪辑矩形变换（ ClipRect ）之后。如果处理程序不支持此选项，[QImageReader](qimagereader.html)将执行缩放图像已被读取。 |
| `QImageIOHandler.ScaledClipRect` | `3` | 缩放剪辑矩形的图像（或ROI ，感兴趣区域） 。支持此选项的处理程序，预计申请所提供的剪辑矩形（一[QRect](qrect.html)） ，应用任何缩放（ ScaleSize ）或定期修剪（ ClipRect ）之后。如果处理程序不支持此选项，[QImageReader](qimagereader.html)将应用缩放剪辑矩形图像已被读取。 |
| `QImageIOHandler.Description` | `2` | 形象的描述。一些图像格式，如GIF和PNG ，可以使文字或意见嵌入到图像数据（例如，用于存储版权信息） 。这是常见的文本存储在键 - 值对的，但一些格式存储所有的文字在一个连续的块。[QImageIOHandler](qimageiohandler.html)返回文本为一体[QString](qstring.html)，其中键和值由分隔'：'和键 - 值对是由两个换行符（ \ n \ n已）分隔。例如， “标题：日落\ N \ nAuthor ：吉姆·史密斯\ nSarah琼斯\ n \ n已” 。存储文本在一个单一的块格式可以使用“描述”为重点。 |
| `QImageIOHandler.CompressionRatio` | `5` | 的图像数据的压缩比。支持此选项的处理程序，预计在写入时设置取决于此选项的值它的压缩率（ int类型） 。 |
| `QImageIOHandler.Gamma` | `6` | 图像的灰度级。支持此选项的处理程序，预计在写入时设置取决于此选项的值图像Gamma值（浮点数） 。 |
| `QImageIOHandler.Quality` | `7` | 的图像的质量级别。支持此选项的处理程序，预计写入时设置图像质量水平取决于该选项的值（一个int ） 。 |
| `QImageIOHandler.Name` | `8` | 该图像的名称。支持此选项的处理程序，预计从图像元数据读取的名称，并返回此作为[QString](qstring.html)或写入预期要存储在图像的元数据的名称的图像时。 |
| `QImageIOHandler.SubType` | `9` | 图像的子类型。支持此选项的处理程序可以使用子类型值，以帮助阅读和写作的图像时。例如， PPM处理程序可以具有“ PPM ”或“ ppmraw ”的子类型的值。 |
| `QImageIOHandler.IncrementalReading` | `10` | 支持此选项的处理程序，预计读取图像中的几次传球，就好像它是一个动画。[QImageReader](qimagereader.html)将把图像作为动画。 |
| `QImageIOHandler.Endianness` | `11` | 图像的字节序。某些图像格式可以存储为大尾端或LittleEndian 。支持字节序的处理程序使用此选项的值，以确定如何在图像的存储位置。 |
| `QImageIOHandler.Animation` | `12` | 支持动画返回True此值图像格式[supportsOption](qimageiohandler.html#supportsOption)（ ），否则，则返回False。 |
| `QImageIOHandler.BackgroundColor` | `13` | 某些图像格式允许指定背景颜色。支持BACKGROUNDCOLOR处理程序初始化背景色为这个选项（一[QColor](qcolor.html)）读取图像时。 |
| `QImageIOHandler.ImageFormat` | `14` | 由处理图像的数据格式返回。这可以是任意的中列出的格式[QImage.Format](qimage.html#Format-enum)。 |

* * *

## Method Documentation

```
QImageIOHandler.__init__ (self)
```

构造一个[QImageIOHandler](qimageiohandler.html)对象。

```
bool QImageIOHandler.canRead (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果图像可以从设备读取（即图像格式的支持，该设备可以读取和初始头信息表明，图像可以被读取），否则返回False 。

当重新实现的CanRead （ ） ，请确保I / O设备（[device](qimageiohandler.html#device)（））被留在其原来的状态（例如，通过使用PEEK（ ），而不是[read](qimageiohandler.html#read)（））。

**See also** [read](qimageiohandler.html#read)（）和[QIODevice.peek](qiodevice.html#peek)（ ） 。

```
int QImageIOHandler.currentImageNumber (self)
```

对于支持动画图像格式，该函数返回当前图像的动画序列号。如果这个函数被调用任何图像之前[read](qimageiohandler.html#read)（ ） ，则返回-1。序列中的第一图像的数目是0。

如果图像格式不支持动画，则返回0 。

**See also** [read](qimageiohandler.html#read)（ ） 。

```
QRect QImageIOHandler.currentImageRect (self)
```

[

返回当前图像的正确。如果没有RECT定义为图像，以及空查阅QRect （ ）返回。

这个功能对于动画，其中帧的唯一部件可以在同一时间进行更新是有用的。

](qrect.html)

```
QIODevice QImageIOHandler.device (self)
```

[](qiodevice.html)

[返回当前分配给该设备](qiodevice.html)[QImageIOHandler](qimageiohandler.html)。如果没有设备已经被分配，则返回0 。

**See also** [setDevice](qimageiohandler.html#setDevice)（ ） 。

```
QByteArray QImageIOHandler.format (self)
```

[](qbytearray.html)

[返回当前分配到的格式](qbytearray.html)[QImageIOHandler](qimageiohandler.html)。如果没有指定格式已被分配，则返回一个空字符串。

**See also** [setFormat](qimageiohandler.html#setFormat)（ ） 。

```
int QImageIOHandler.imageCount (self)
```

对于支持动画图像格式，该函数返回的动画图像的数量。如果图像格式不支持动画，或者如果它是无法确定的图像的数量，则返回0 。

默认实现返回1 ，如果[canRead](qimageiohandler.html#canRead)（ ）返回True，否则返回0。

```
bool QImageIOHandler.jumpToImage (self, int imageNumber)
```

对于支持动画图像格式，该函数跳转到的序列号是图像_imageNumber_。到下一次调用[read](qimageiohandler.html#read)（ ）将尝试读取这个形象。

默认实现不执行任何操作，并返回False 。

```
bool QImageIOHandler.jumpToNextImage (self)
```

对于支持动画图像格式，该功能跳转到下一个图像。

默认实现不执行任何操作，并返回False 。

```
int QImageIOHandler.loopCount (self)
```

对于支持动画图像格式，该函数返回的时候动画应该循环的次数。如果图像格式不支持动画，则返回0 。

```
QByteArray QImageIOHandler.name (self)
```

[

```
int QImageIOHandler.nextImageDelay (self)
```

对于支持动画图像格式，该函数返回的毫秒数要等到读取下一个图像。如果图像格式不支持动画，则返回0 。

```
QVariant QImageIOHandler.option (self, ImageOption option)
```

](qbytearray.html)

[返回指定的值_option_作为](qbytearray.html)[QVariant](qvariant.html)。值的类型取决于选项。例如，选项（尺寸）返回一个[QSize](qsize.html)变体。

**See also** [setOption](qimageiohandler.html#setOption)（）和[supportsOption](qimageiohandler.html#supportsOption)（ ） 。

```
bool QImageIOHandler.read (self, QImage image)
```

这种方法是抽象的，应在任何子类中重新实现。

从设备中读取的图像，并将其存储在_image_。返回True如果图像被成功读取，否则返回False 。

对于支持增量加载的图像格式，并为动画格式，图像处理程序可以假设_image_指向前一帧。

**See also** [canRead](qimageiohandler.html#canRead)（ ） 。

```
QImageIOHandler.setDevice (self, QIODevice device)
```

设置的设备[QImageIOHandler](qimageiohandler.html)至_device_。读取和写入图像时的图像处理程序将使用该设备。

该设备只能设置一次，并调用之前必须设置[canRead](qimageiohandler.html#canRead)（ ）[read](qimageiohandler.html#read)（ ）[write](qimageiohandler.html#write)（ ）等，如果你需要读取多个文件，建立相应的多个实例[QImageIOHandler](qimageiohandler.html)子类。

**See also** [device](qimageiohandler.html#device)（ ） 。

```
QImageIOHandler.setFormat (self, QByteArray format)
```

设置的格式[QImageIOHandler](qimageiohandler.html)至_format_。该格式是支持多种格式的图像处理程序非常有用。

**See also** [format](qimageiohandler.html#format)（ ） 。

```
QImageIOHandler.setOption (self, ImageOption option, QVariant value)
```

设置选项_option_与该值_value_。

**See also** [option](qimageiohandler.html#option)（）和[ImageOption](qimageiohandler.html#ImageOption-enum)。

```
bool QImageIOHandler.supportsOption (self, ImageOption option)
```

返回True如果[QImageIOHandler](qimageiohandler.html)支持选项_option_否则返回False 。例如，如果[QImageIOHandler](qimageiohandler.html)支持[Size](qimageiohandler.html#ImageOption-enum)选项， supportsOption （尺寸）必须返回True 。

**See also** [setOption](qimageiohandler.html#setOption)（）和[option](qimageiohandler.html#option)（ ） 。

```
bool QImageIOHandler.write (self, QImage image)
```

写入图像_image_到所分配的设备。成功时返回TRUE ，否则返回False 。

默认实现不执行任何操作，并简单地返回False 。