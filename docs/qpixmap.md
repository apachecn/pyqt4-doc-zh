# QPixmap Class Reference

## [[QtGui](index.htm) module]

本的QPixmap类是可用于作为涂料设备离屏图像表示。[More...](#details)

继承[QPaintDevice](qpaintdevice.html)。

通过继承[QBitmap](qbitmap.html)。

### Types

*   `enum ShareMode { ImplicitlyShared, ExplicitlyShared }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, int w, int h)`
*   `__init__ (self, QSize)`
*   `__init__ (self, QString fileName, str format = None, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `__init__ (self, list-of-str xpm)`
*   `__init__ (self, QPixmap)`
*   `__init__ (self, QVariant variant)`
*   `QPixmap alphaChannel (self)`
*   `int cacheKey (self)`
*   `bool convertFromImage (self, QImage img, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `QPixmap copy (self, QRect rect = QRect())`
*   `QPixmap copy (self, int ax, int ay, int awidth, int aheight)`
*   `QBitmap createHeuristicMask (self, bool clipTight = True)`
*   `QBitmap createMaskFromColor (self, QColor maskColor, Qt.MaskMode mode)`
*   `QBitmap createMaskFromColor (self, QColor maskColor)`
*   `int depth (self)`
*   `detach (self)`
*   `int devType (self)`
*   `fill (self, QColor color = Qt.white)`
*   `fill (self, QWidget widget, QPoint ofs)`
*   `fill (self, QWidget widget, int xofs, int yofs)`
*   `int handle (self)`
*   `bool hasAlpha (self)`
*   `bool hasAlphaChannel (self)`
*   `int height (self)`
*   `bool isNull (self)`
*   `bool isQBitmap (self)`
*   `bool load (self, QString fileName, str format = None, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `bool loadFromData (self, str buf, str format = None, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `bool loadFromData (self, QByteArray buf, str format = None, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `QBitmap mask (self)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric)`
*   `QPaintEngine paintEngine (self)`
*   `QRect rect (self)`
*   `bool save (self, QString fileName, str format = None, int quality = -1)`
*   `bool save (self, QIODevice device, str format = None, int quality = -1)`
*   `QPixmap scaled (self, int width, int height, Qt.AspectRatioMode aspectRatioMode = Qt.IgnoreAspectRatio, Qt.TransformationMode transformMode = Qt.FastTransformation)`
*   `QPixmap scaled (self, QSize size, Qt.AspectRatioMode aspectRatioMode = Qt.IgnoreAspectRatio, Qt.TransformationMode transformMode = Qt.FastTransformation)`
*   `QPixmap scaledToHeight (self, int height, Qt.TransformationMode mode = Qt.FastTransformation)`
*   `QPixmap scaledToWidth (self, int width, Qt.TransformationMode mode = Qt.FastTransformation)`
*   `QRegion exposed scroll (self, int dx, int dy, QRect rect)`
*   `QRegion exposed scroll (self, int dx, int dy, int x, int y, int width, int height)`
*   `int serialNumber (self)`
*   `setAlphaChannel (self, QPixmap)`
*   `setMask (self, QBitmap)`
*   `QSize size (self)`
*   `swap (self, QPixmap other)`
*   `QImage toImage (self)`
*   `QPixmap transformed (self, QMatrix matrix, Qt.TransformationMode mode = Qt.FastTransformation)`
*   `QPixmap transformed (self, QTransform transform, Qt.TransformationMode mode = Qt.FastTransformation)`
*   `int width (self)`
*   `QX11Info x11Info (self)`
*   `int x11PictureHandle (self)`

### Static Methods

*   `int defaultDepth ()`
*   `QPixmap fromImage (QImage image, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `QPixmap fromImageReader (QImageReader imageReader, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `QPixmap fromX11Pixmap (int pixmap, ShareMode mode = QPixmap.ImplicitlyShared)`
*   `QPixmap grabWidget (QWidget widget, QRect rect)`
*   `QPixmap grabWidget (QWidget widget, int x = 0, int y = 0, int width = -1, int height = -1)`
*   `QPixmap grabWindow (int window, int x = 0, int y = 0, int width = -1, int height = -1)`
*   `QMatrix trueMatrix (QMatrix m, int w, int h)`
*   `QTransform trueMatrix (QTransform m, int w, int h)`

* * *

## Detailed Description

本的QPixmap类是可用于作为涂料设备离屏图像表示。

Qt提供了四个类用于处理图像数据：[QImage](qimage.html)， QPixmap的，[QBitmap](qbitmap.html)和[QPicture](qpicture.html)。[QImage](qimage.html)被设计和优化用于I / O ，并直接像素访问和操作，而QPixmap的设计和用于在屏幕上显示的图像进行了优化。[QBitmap](qbitmap.html)只有一个继承自QPixmap ，确保深度为1一个方便的类。该[isQBitmap](qpixmap.html#isQBitmap)（如果一个物体的QPixmap是一个真正的位图）函数返回True，否则返回False 。最后，该[QPicture](qpicture.html)类是一个绘图设备，记录和重放[QPainter](qpainter.html)的命令。

使用A的QPixmap可以很容易地显示在屏幕上[QLabel](qlabel.html)或1[QAbstractButton](qabstractbutton.html)的亚类（如[QPushButton](qpushbutton.html)和[QToolButton](qtoolbutton.html)） 。[QLabel](qlabel.html)有一个像素映射属性，而[QAbstractButton](qabstractbutton.html)有一个icon属性。

除了普通的构造函数，一个的QPixmap可以使用静态的构造[grabWidget](qpixmap.html#grabWidget)（）和[grabWindow](qpixmap.html#grabWindow)（ ），它创建了一个的QPixmap和油漆给定的部件，或窗口，进入它的功能。

的QPixmap对象可以围绕通过值传递，因为的QPixmap类使用隐式数据共享。欲了解更多信息，请参阅[Implicit Data Sharing](index.htm#implicit-data-sharing)文档。 QPixmap的对象也可以流。

需要注意的是在一个像素图的像素数据是内部和由基本窗口系统进行管理。因为QPixmap的是[QPaintDevice](qpaintdevice.html)子类，[QPainter](qpainter.html)可用于直接绘制到像素图。像素只能通过被访问[QPainter](qpainter.html)功能或通过转换的QPixmap到[QImage](qimage.html)。然而，本[fill](qpixmap.html#fill)（）函数是用于初始化整个像素映像与一个给定的颜色。

有功能之间的转换[QImage](qimage.html)和QPixmap的。典型地，该[QImage](qimage.html)类是用来加载一个图像文件，可选操作的图像数据，前[QImage](qimage.html)对象被转换成的QPixmap在屏幕上显示出来。另外，如果没有操作是理想，图像文件可以直接加载到的QPixmap 。在Windows上， QPixmap的类还支持之间的转换`HBITMAP`和QPixmap的。在Symbian中， QPixmap的类还支持的CFbsBitmap和的QPixmap之间的转换。

的QPixmap提供了可以被用来获得各种关于像素映像信息的功能的集合。此外，有几个函数，它使像素映像的转换。

### Reading and Writing Image Files

的QPixmap提供了阅读一个图像文件几种方法：该文件可以构建的QPixmap对象时被加载，或者通过使用[load](qpixmap.html#load)（）或[loadFromData](qpixmap.html#loadFromData)（ ）函数以后。当加载一个图像，文件名可以指在磁盘上的实际文件或应用的嵌入式资源之一。看[The Qt Resource System](index.htm)概述有关如何嵌入在应用程序的可执行映像和其他资源文件的详细信息。

只需调用[save](qpixmap.html#save)（ ）函数保存的QPixmap对象。

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
| XBM | X11 Bitmap | Read/write |
| XPM | X11 Pixmap | Read/write |

### Pixmap Information

的QPixmap提供了可以被用来获得各种关于像素映像信息的功能的集合：

|  | Available Functions |
| --- | --- |
| Geometry | The [size](qpixmap.html#size)(), [width](qpixmap.html#width)() and [height](qpixmap.html#height)() functions provide information about the pixmap's size. The [rect](qpixmap.html#rect)() function returns the image's enclosing rectangle. |
| Alpha component | The [hasAlphaChannel](qpixmap.html#hasAlphaChannel)() returns true if the pixmap has a format that respects the alpha channel, otherwise returns false. The [hasAlpha](qpixmap.html#hasAlpha)(), [setMask](qpixmap.html#setMask)() and [mask](qpixmap.html#mask)() functions are legacy and should not be used. They are potentially very slow.该[createHeuristicMask](qpixmap.html#createHeuristicMask)（ ）函数创建并返回一个1 - BPP启发式面膜（即[QBitmap](qbitmap.html)）这个像素映射。它的工作原理是从一个角选择一种颜色，然后小打小闹该颜色的像素，开始在所有的边缘。该[createMaskFromColor](qpixmap.html#createMaskFromColor)（ ）函数创建并返回一个掩码（即一[QBitmap](qbitmap.html)），用于根据一个给定的彩色的像素图。 |
| Low-level information | The [depth](qpixmap.html#depth)() function returns the depth of the pixmap. The [defaultDepth](qpixmap.html#defaultDepth)() function returns the default depth, i.e. the depth used by the application on the given screen.该[cacheKey](qpixmap.html#cacheKey)（ ）函数返回一个数字，唯一标识的QPixmap对象的内容。该[x11Info](qpixmap.html#x11Info)（ ）函数返回使用到的像素图目前属于屏幕的X显示的配置信息。该[x11PictureHandle](qpixmap.html#x11PictureHandle)（ ）函数返回的像素图的XRender的支持X11的图片处理。需要注意的是后两个功能仅适用于X11 。 |

### Pixmap Conversion

一个QPixmap的对象可以被转换成一个[QImage](qimage.html)使用[toImage](qpixmap.html#toImage)（）函数。同样，一个[QImage](qimage.html)可以使用被转换成的QPixmap的[fromImage](qpixmap.html#fromImage)（ ） 。如果这是过于昂贵的操作，您可以使用[QBitmap.fromImage](qbitmap.html#fromImage)（ ）来代替。

此外，在Windows上， QPixmap的类支持的转换和从HBITMAP ：在[toWinHBITMAP](qpixmap.html#toWinHBITMAP)（）函数创建了一个HBITMAP相当于QPixmap的，根据给定的[HBitmapFormat](qpixmap.html#HBitmapFormat-enum)，并返回HBITMAP句柄。该[fromWinHBITMAP](qpixmap.html#fromWinHBITMAP)（ ）函数返回的QPixmap ，它等效于在给定的位图具有指定格式。该的QPixmap类还支持转换和从HICON ：在[toWinHICON](qpixmap.html#toWinHICON)（ ）函数创建一个HICON相当于的QPixmap ，并返回HICON句柄。该[fromWinHICON](qpixmap.html#fromWinHICON)（ ）函数返回的QPixmap ，等效于给定的图标。

另外，在Symbian中， QPixmap的类支持的转换和从CFbsBitmap的方法：在[toSymbianCFbsBitmap](qpixmap.html#toSymbianCFbsBitmap)（ ）函数创建的CFbsBitmap相当于QPixmap的，根据给定的模式并返回的CFbsBitmap对象。该[fromSymbianCFbsBitmap](qpixmap.html#fromSymbianCFbsBitmap)（ ）函数返回的QPixmap ，等效于给定的位图，给定模式。

### Pixmap Transformations

的QPixmap支持许多函数，用于创建一个新的像素图，它是原始的转换后的版本：

该[scaled](qpixmap.html#scaled)（ ）[scaledToWidth](qpixmap.html#scaledToWidth)（）和[scaledToHeight](qpixmap.html#scaledToHeight)（ ）函数返回的像素图的缩放复印，而[copy](qpixmap.html#copy)（ ）函数创建一个QPixmap的是原来的一个普通的副本。

该[transformed](qpixmap.html#transformed)（ ）函数返回的转化与给定的变换矩阵与变换模式的像素图的副本：在内部，该变换矩阵进行调整，以补偿不需要翻译，即[transformed](qpixmap.html#transformed)（ ）返回一个包含原始像素图的全部改造点的最小像素图。静[trueMatrix](qpixmap.html#trueMatrix)（ ）函数返回用于转化像素图的实际矩阵。

**Note:**当使用原生的X11图形系统，在像素映射变为无效时，[QApplication](qapplication.html)实例被销毁。

* * *

## Type Documentation

```
QPixmap.ShareMode
```

这个枚举类型定义了共享模式创建时可用一[QPixmap](qpixmap.html)从原始的X11像素图句柄的对象。

| Constant | Value | Description |
| --- | --- | --- |
| `QPixmap.ImplicitlyShared` | `0` | 此模式将导致[QPixmap](qpixmap.html)反对建立内部数据的副本，然后才修改，从而保持原有的X11的像素图完好无损。 |
| `QPixmap.ExplicitlyShared` | `1` | 在这种模式下，像素映像数据将_not_前它被修改，这实际上会改变原来的X11像素映像被复制。 |

**Warning:**这个枚举仅用于X11的特定功能;使用它是不可移植的。

这个枚举被引入或修改的Qt 4.5 。

**See also** [QPixmap.fromX11Pixmap](qpixmap.html#fromX11Pixmap)（ ） 。

* * *

## Method Documentation

```
QPixmap.__init__ (self)
```

构造一个空像素图。

**See also** [isNull](qpixmap.html#isNull)（ ） 。

```
QPixmap.__init__ (self, int w, int h)
```

```
QPixmap.__init__ (self, QSize)
```

构造一个像素图与给定_width_和_height_。如果任_width_ or _height_是零，空像素图的构造。

**Warning:**这将创建一个[QPixmap](qpixmap.html)与未初始化的数据。通话[fill](qpixmap.html#fill)（ ）与绘制到它之前，以填补一个合适的颜色的像素图[QPainter](qpainter.html)。

**See also** [isNull](qpixmap.html#isNull)（ ） 。

```
QPixmap.__init__ (self, QString fileName, str format = None, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

构造一个像素图从文件中给定的_fileName_。如果文件不存在或未知格式，像素图变成了空像素图。

装载程序将尝试使用指定的读取像素图_format_。如果_format_未指定（这是默认值） ，加载器探测文件的标题来猜测文件格式。

文件名可以是指在磁盘上的实际文件或应用的嵌入式资源之一。请参阅[Resource System](index.htm)概述有关如何嵌入在应用程序的可执行映像和其他资源文件的详细信息。

如果图像需要进行修改，以适应在较低分辨率的结果（例如，从32位转换为8位），使用_flags_来控制转换。

该_fileName_，_format_和_flags_参数上传递[load](qpixmap.html#load)（ ） 。这意味着，在数据_fileName_是不是编译成二进制文件。如果_fileName_包含相对路径（例如，文件名只）的相关文件，必须找到相对于运行时的工作目录。

**See also** [Reading and Writing Image Files](qpixmap.html#reading-and-writing-image-files)。

```
QPixmap.__init__ (self, list-of-str xpm)
```

构造一个像素图从给定的_xpm_数据，该数据必须是有效的XPM图像。

错误被忽略。

请注意，它可能通过使用一个不同寻常的声明挤压XPM变量一点点：

```
 static const char * const start_xpm[]={
     "16 15 8 1",
     "a c #cec6bd",
 ....

```

额外的`const`使得整个定义为只读，这会更有效（例如，当该代码在一个共享库）和ROMable当应用程序被存储在ROM中。

```
QPixmap.__init__ (self, QPixmap)
```

构造一个像素映射，它是给定的一个副本_pixmap_。

**See also** [copy](qpixmap.html#copy)（ ） 。

```
QPixmap.__init__ (self, QVariant variant)
```

```
QPixmap QPixmap.alphaChannel (self)
```

[

```
int QPixmap.cacheKey (self)
```

](qpixmap.html)

[返回一个数字，用于标识此](qpixmap.html)[QPixmap](qpixmap.html)。不同[QPixmap](qpixmap.html)对象只能有相同的高速缓存密钥，如果它们指的是相同的内容。

该cacheKey （ ）会改变，当像素映射被改变。

```
bool QPixmap.convertFromImage (self, QImage img, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

代替该像素的数据与给定_image_使用指定的_flags_来控制转换。该_flags_参数是的一个按位或[Qt.ImageConversionFlags](qt.html#ImageConversionFlag-enum)。路过0_flags_设置所有的默认选项。返回True如果结果是，这个像素映射不为null 。

注：此功能是在Qt的4.6和更早的版本的Qt 3支持的一部分。它已被晋升为官方的API状态4.7支持更新的pixmap的图像，而无需创建一个新的[QPixmap](qpixmap.html)如[fromImage](qpixmap.html#fromImage)（ ）会。

此功能被引入Qt的4.7 。

**See also** [fromImage](qpixmap.html#fromImage)（ ） 。

```
QPixmap QPixmap.copy (self, QRect rect = QRect())
```

[](qpixmap.html)

[返回像素图的子集是由给定的指定的一个深层副本_rectangle_。有关深副本的详细信息，请参阅](qpixmap.html)[Implicit Data Sharing](index.htm#implicit-data-sharing)文档。

如果给定的_rectangle_为空时，整个图像被复制。

**See also** [operator=](qpixmap.html#operator-eq)（ ）[QPixmap](qpixmap.html#QPixmap)（）和[Pixmap Transformations](qpixmap.html#pixmap-transformations)。

```
QPixmap QPixmap.copy (self, int ax, int ay, int awidth, int aheight)
```

[

这是一个重载函数。

](qpixmap.html)

[返回像素图的子集是由矩形指定一个深层副本](qpixmap.html)[QRect](qrect.html)（_x_，_y_，_width_，_height_） 。

```
QBitmap QPixmap.createHeuristicMask (self, bool clipTight = True)
```

[

创建并返回一个启发式的面具为这个像素映射。

该功能是通过从一个角中选择一种颜色，然后小打小闹该颜色的像素处开始，所有的边。如果_clipTight_为True（默认值）的面具只是大到足以复盖的像素，否则，面膜比数据像素。

面具可能不是完美的，但它应该是合理的，所以你可以做的事情，如下列：

](qbitmap.html)

```
 QPixmap myPixmap;
 myPixmap->setMask(myPixmap->createHeuristicMask());

```

此功能是缓慢的，因为它涉及到从一个转换到/[QImage](qimage.html)和非平凡计算。

**See also** [QImage.createHeuristicMask](qimage.html#createHeuristicMask)（）和[createMaskFromColor](qpixmap.html#createMaskFromColor)（ ） 。

```
QBitmap QPixmap.createMaskFromColor (self, QColor maskColor, Qt.MaskMode mode)
```

[](qbitmap.html)

[创建并返回的基础上，给出了这个像素映射口罩_maskColor_。如果_mode_ is](qbitmap.html) [Qt.MaskInColor](qt.html#MaskMode-enum)，匹配MaskColor的所有像素将是透明的。如果_mode_ is [Qt.MaskOutColor](qt.html#MaskMode-enum)，匹配MaskColor的所有像素是不透明的。

此功能是缓慢的，因为它涉及到从一个转换到/[QImage](qimage.html)。

**See also** [createHeuristicMask](qpixmap.html#createHeuristicMask)（）和[QImage.createMaskFromColor](qimage.html#createMaskFromColor)（ ） 。

```
QBitmap QPixmap.createMaskFromColor (self, QColor maskColor)
```

[

这是一个重载函数。

](qbitmap.html)

[创建并返回的基础上，给出了这个像素映射口罩_maskColor_。与调用createMaskFromColor （ MaskColor的，](qbitmap.html)[Qt.MaskInColor](qt.html#MaskMode-enum)）

**See also** [createHeuristicMask](qpixmap.html#createHeuristicMask)（）和[QImage.createMaskFromColor](qimage.html#createMaskFromColor)（ ） 。

```
int QPixmap.defaultDepth ()
```

返回应用程序所使用的默认的pixmap的深度。

在Windows和Mac ，默认的深度始终是32 。在X11和嵌入式，在屏幕的深度将通过这个函数返回。

**See also** [depth](qpixmap.html#depth)（ ）[QColormap.depth](index.htm#depth)（）和[Pixmap Information](qpixmap.html#pixmap-information)。

```
int QPixmap.depth (self)
```

返回像素图的深度。

像素图的深度也被称为每像素位数（ BPP ）或像素图的位面。空像素图具有深度为0 。

**See also** [defaultDepth](qpixmap.html#defaultDepth)（）和[Pixmap Information](qpixmap.html#pixmap-information)。

```
QPixmap.detach (self)
```

分离从共享像素映射数据的像素图。

一个像素图是由Qt的自动分离，每当其内容是即将改变。这是在几乎所有做[QPixmap](qpixmap.html)该修改像素图的成员函数（[fill](qpixmap.html#fill)（ ）[fromImage](qpixmap.html#fromImage)（ ）[load](qpixmap.html#load)（） ，等等） ，并且在[QPainter.begin](qpainter.html#begin)（ ）上的一个像素映射。

有两个例外，其中分离（ ）必须被显式调用，在调用时是[handle](qpixmap.html#handle)（）或[x11PictureHandle](qpixmap.html#x11PictureHandle)（ ）函数（仅适用于X11 ） 。否则，使用系统调用进行任何修改，将在共享的数据进行的。

该分离（ ）函数立即返回，如果有只是一个参考，或者如果像素映射还没有被初始化。

```
int QPixmap.devType (self)
```

```
QPixmap.fill (self, QColor color = Qt.white)
```

填充像素图与给定_color_。

这个函数的作用时，像素图被画上是不确定的。

**See also** [Pixmap Transformations](qpixmap.html#pixmap-transformations)。

```
QPixmap.fill (self, QWidget widget, QPoint ofs)
```

填充的像素图_widget_根据给定的偏移量的背景颜色或像素图。

该[QPoint](qpoint.html) _offset_定义窗口小部件的点坐标到像素图的左上角的像素将被映射到。这是唯一的显着如果插件有一个背景像素映像，否则该像素映像将被简单地填充有小窗口的背景色。

```
QPixmap.fill (self, QWidget widget, int xofs, int yofs)
```

这是一个重载函数。

填充的像素图_widget_的背景颜色或像素图。给定的点， （_x_，_y_） ，定义了一个在小部件偏移坐标到像素图的左上角的像素将被映射到。

```
QPixmap QPixmap.fromImage (QImage image, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

[](qpixmap.html)

[转换给定的_image_使用指定的一个像素图_flags_来控制转换。该_flags_参数是的一个按位或](qpixmap.html)[Qt.ImageConversionFlags](qt.html#ImageConversionFlag-enum)。路过0_flags_设置所有的默认选项。

在单色的情况下和8位的图像，该图像首先被转换为一个32位的像素图，然后填充在颜色表的颜色。如果这是过于昂贵的操作，您可以使用[QBitmap.fromImage](qbitmap.html#fromImage)（ ）来代替。

**See also** [fromImageReader](qpixmap.html#fromImageReader)（ ）[toImage](qpixmap.html#toImage)（）和[Pixmap Conversion](qpixmap.html#pixmap-conversion)。

```
QPixmap QPixmap.fromImageReader (QImageReader imageReader, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

[](qpixmap.html)

[创建](qpixmap.html)[QPixmap](qpixmap.html)从直接从读取的图像_imageReader_。该_flags_参数是的一个按位或[Qt.ImageConversionFlags](qt.html#ImageConversionFlag-enum)。路过0_flags_设置所有的默认选项。

在某些系统中，直接读取图像[QPixmap](qpixmap.html)可以使用较少的内存比读一本[QImage](qimage.html)将其转换为[QPixmap](qpixmap.html)。

**See also** [fromImage](qpixmap.html#fromImage)（ ）[toImage](qpixmap.html#toImage)（）和[Pixmap Conversion](qpixmap.html#pixmap-conversion)。

```
QPixmap QPixmap.fromX11Pixmap (int pixmap, ShareMode mode = QPixmap.ImplicitlyShared)
```

[](qpixmap.html)

[创建](qpixmap.html)[QPixmap](qpixmap.html)从原生X11的像素图手柄_pixmap_，使用_mode_为共享模式。默认共享模式[QPixmap.ImplicitlyShared](qpixmap.html#ShareMode-enum)，这意味着像素图的副本，如果有人试图通过如要修改它是由绘制到它。

[QPixmap](qpixmap.html)不_not_采取所有权_pixmap_处理，并必须由用户删除。

**Warning:**这个功能是X11特定;使用它是不可移植的。

此功能被引入Qt的4.5 。

**See also** [QPixmap.ShareMode](qpixmap.html#ShareMode-enum)。

```
QPixmap QPixmap.grabWidget (QWidget widget, QRect rect)
```

[

创建一个像素图和油漆给定的_widget_，受限于给定的_rectangle_在它。如果_widget_有任何孩子，那么他们也画在适当的位置。

如果没有指定矩形（默认值）将整个窗体是画。

](qpixmap.html)

[If _widget_为0 ，指定的矩形不重叠部件的矩形，或发生错误，该函数将返回一个null](qpixmap.html)[QPixmap](qpixmap.html)。如果矩形是给定的一个超集_widget_，外面的区域_widget_都复盖着widget的背景。

这个功能实际上是问_widget_油漆本身（及其子画画本身）通过调用的paintEvent （ ）与画家重定向打开。但[QPixmap](qpixmap.html)还提供了[grabWindow](qpixmap.html#grabWindow)（ ）函数，它是一个快一点通过抓取像素直接关闭屏幕。此外，如果有重叠的窗口，[grabWindow](qpixmap.html#grabWindow)（ ） ，不像grabWidget （ ） ，会看到他们。

**Warning:**不要从它抢一个widget[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。然而，它是安全的抢从另一小窗口的小部件[paintEvent()](qwidget.html#paintEvent)。

**See also** [grabWindow](qpixmap.html#grabWindow)（ ） 。

```
QPixmap QPixmap.grabWidget (QWidget widget, int x = 0, int y = 0, int width = -1, int height = -1)
```

[

这是一个重载函数。

](qpixmap.html)

[创建一个像素图和油漆给定的_widget_，受限于](qpixmap.html)[QRect](qrect.html)（_x_，_y_，_width_，_height_） ，在它。

**Warning:**不要从它抢一个widget[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。然而，它是安全的抢从另一小窗口的小部件[paintEvent()](qwidget.html#paintEvent)。

```
QPixmap QPixmap.grabWindow (int window, int x = 0, int y = 0, int width = -1, int height = -1)
```

[](qpixmap.html)

[创建并返回被抓住给定的内容构成的像素图_window_限制](qpixmap.html)[QRect](qrect.html)（_x_，_y_，_width_，_height_） 。

该参数（_x_，_y_）指定的窗口偏移，而（_width_，_height_）指定要复制的区域。如果_width_为负，则函数将一切交给窗口的右边框。如果_height_是否定的，则函数将一切向窗口的底部。

窗口系统标识符（`WId`）可使用检索到的[QWidget.winId](qwidget.html#winId)（）函数。使用一个窗口标识符，而不是一个的理由[QWidget](qwidget.html)，是使窗口不属于该应用程序的一部分，窗口系统框架，等等抓取。

该grabWindow （ ）函数抓取像素的屏幕，而不是从窗口，也就是说，如果有另一个窗口部分或完全超过你抢，你从上复窗口得到的像素，太一。将鼠标光标一般不抓住。

注意：在X11 ，如果给定的_window_不具有相同的深度为根窗口，另一个窗口部分或全部掩盖你抢一个，你会_not_从上复窗口得到的像素。在像素图的遮挡区域的内容将是不确定的和未初始化的。

在Windows Vista及以上的抓住一个分层的窗口，这是通过设置创建[Qt.WA_TranslucentBackground](qt.html#WidgetAttribute-enum)属性，将无法正常工作。而是抓住了桌面widget应该工作。

**Warning:**一般情况下，抓一个区域外屏幕是不是安全。这取决于底层的窗口系统。

**See also** [grabWidget](qpixmap.html#grabWidget)（）和[Screenshot Example](index.htm)。

```
int QPixmap.handle (self)
```

返回像素图的句柄，设备上下文。

需要注意的是，由于[QPixmap](qpixmap.html)利用[implicit data sharing](index.htm#implicit-data-sharing)时，[detach](qpixmap.html#detach)（）函数必须被调用明确，以确保只有_this_如果像素图的数据是共享的像素图的数据被修改。

**Warning:**这个功能是X11特定;使用它是不可移植的。

**Warning:**由于4.8 ，像素映射没有一个X11的手柄，除非与创造[fromX11Pixmap()](qpixmap.html#fromX11Pixmap)或者，如果本机图形系统明确激活。

**See also** [detach](qpixmap.html#detach)（）和[QApplication.setGraphicsSystem](qapplication.html#setGraphicsSystem)（ ） 。

```
bool QPixmap.hasAlpha (self)
```

返回True如果该像素图有一个alpha通道，_or_有一个面具，否则返回False 。

**See also** [hasAlphaChannel](qpixmap.html#hasAlphaChannel)（）和[mask](qpixmap.html#mask)（ ） 。

```
bool QPixmap.hasAlphaChannel (self)
```

返回True如果像素映射有一个尊重的alpha通道的格式，否则返回False 。

**See also** [hasAlpha](qpixmap.html#hasAlpha)（ ） 。

```
int QPixmap.height (self)
```

返回像素图的高度。

**See also** [size](qpixmap.html#size)（）和[Pixmap Information](qpixmap.html#pixmap-information)。

```
bool QPixmap.isNull (self)
```

返回True如果这是一个空像素图，否则返回False 。

空像素映射具有零宽度，高度为零，没有内容。你可以不画在一个空像素图。

```
bool QPixmap.isQBitmap (self)
```

返回True如果这是一个[QBitmap](qbitmap.html)否则返回False 。

```
bool QPixmap.load (self, QString fileName, str format = None, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

加载一个像素图从文件给定的_fileName_。返回True如果成功加载的像素图，否则返回False 。

装载程序将尝试使用指定的读取像素图_format_。如果_format_未指定（这是默认值） ，加载器探测文件的标题来猜测文件格式。

文件名可以是指在磁盘上的实际文件或应用的嵌入式资源之一。请参阅[Resource System](index.htm)概述如何嵌入到应用程序的可执行像素图等资源文件的详细信息。

如果需要修改，以适应在一个较低分辨率的结果（例如，从32位转换为8位）的数据，使用_flags_来控制转换。

需要注意的是QPixmaps会自动添加到[QPixmapCache](qpixmapcache.html)当从文件加载;使用的密钥是内部的，不能获得的。

**See also** [loadFromData](qpixmap.html#loadFromData)（）和[Reading and Writing Image Files](qpixmap.html#reading-and-writing-image-files)。

```
bool QPixmap.loadFromData (self, str buf, str format = None, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

加载从一个像素图_len_给定的二进制字节第一_data_。返回True如果加载成功的像素图，否则返回False 。

装载程序将尝试使用指定的读取像素图_format_。如果_format_未指定（这是默认值） ，加载器探测文件的标题来猜测文件格式。

如果需要修改，以适应在一个较低分辨率的结果（例如，从32位转换为8位）的数据，使用_flags_来控制转换。

**See also** [load](qpixmap.html#load)（）和[Reading and Writing Image Files](qpixmap.html#reading-and-writing-image-files)。

```
bool QPixmap.loadFromData (self, QByteArray buf, str format = None, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

```
QBitmap QPixmap.mask (self)
```

[

从像素图的Alpha通道中提取位图蒙版。

**Warning:**这是一个潜在的昂贵的操作。像素映像的掩码是从PixelData取出动态萃取。

](qbitmap.html)

[**See also**](qbitmap.html) [setMask](qpixmap.html#setMask)（）和[Pixmap Information](qpixmap.html#pixmap-information)。

```
int QPixmap.metric (self, QPaintDevice.PaintDeviceMetric)
```

```
QPaintEngine QPixmap.paintEngine (self)
```

[](qpaintengine.html)

```
QRect QPixmap.rect (self)
```

[

返回像素图的外接矩形。

](qrect.html)

[**See also**](qrect.html) [Pixmap Information](qpixmap.html#pixmap-information)。

```
bool QPixmap.save (self, QString fileName, str format = None, int quality = -1)
```

节省了像素映像的文件用给定的_fileName_使用指定的图像文件_format_和_quality_因素。成功返回True ，否则返回False 。

该_quality_因子必须在范围[ 0,100 ]或-1 。指定0以获得小的压缩文件， 100为大型未压缩的文件，和-1来使用默认设置。

If _format_是0 ，图像格式将被选自_fileName_的后缀。

**See also** [Reading and Writing Image Files](qpixmap.html#reading-and-writing-image-files)。

```
bool QPixmap.save (self, QIODevice device, str format = None, int quality = -1)
```

这是一个重载函数。

该函数将一个[QPixmap](qpixmap.html)为给定的_device_使用指定的图像文件_format_和_quality_因素。这可以用来，例如，直接保存一个像素映像成[QByteArray](qbytearray.html)：

```
         [QPixmap](qpixmap.html) pixmap;
         [QByteArray](qbytearray.html) bytes;
         [QBuffer](qbuffer.html) buffer(&bytes);
         buffer.open([QIODevice](qiodevice.html).WriteOnly);
         pixmap.save(&buffer, "PNG"); // writes pixmap into bytes in PNG format

```

```
QPixmap QPixmap.scaled (self, int width, int height, Qt.AspectRatioMode aspectRatioMode = Qt.IgnoreAspectRatio, Qt.TransformationMode transformMode = Qt.FastTransformation)
```

[

缩放像素映射到给定_size_使用由指定的高宽比和变换模式_aspectRatioMode_和_transformMode_。

![](../img/qimage-scaling.png)

](qpixmap.html)

[](qpixmap.html)
*   [If _aspectRatioMode_ is](qpixmap.html) [Qt.IgnoreAspectRatio](qt.html#AspectRatioMode-enum), the pixmap is scaled to _size_.
*   If _aspectRatioMode_ is [Qt.KeepAspectRatio](qt.html#AspectRatioMode-enum), the pixmap is scaled to a rectangle as large as possible inside _size_, preserving the aspect ratio.
*   If _aspectRatioMode_ is [Qt.KeepAspectRatioByExpanding](qt.html#AspectRatioMode-enum), the pixmap is scaled to a rectangle as small as possible outside _size_, preserving the aspect ratio.

如果给定的_size_是空的，这个函数返回一个空的像素图。

在某些情况下，它可以更有利绘制像素映射到带刻度设置，而不是缩放的像素图画家。这种情况下，当基于OpenGL或当快速缩放因子变化的画家为实例。

**See also** [isNull](qpixmap.html#isNull)（）和[Pixmap Transformations](qpixmap.html#pixmap-transformations)。

```
QPixmap QPixmap.scaled (self, QSize size, Qt.AspectRatioMode aspectRatioMode = Qt.IgnoreAspectRatio, Qt.TransformationMode transformMode = Qt.FastTransformation)
```

[

这是一个重载函数。

返回像素图的缩放，以矩形与给定的一个副本_width_和_height_根据给定的_aspectRatioMode_和_transformMode_。

如果任何一个_width_或_height_为零或负数，则该函数返回一个空的pixmap 。

](qpixmap.html)

```
QPixmap QPixmap.scaledToHeight (self, int height, Qt.TransformationMode mode = Qt.FastTransformation)
```

[

返回图像的缩放复印。返回的图像被缩放为给定的_height_使用指定的变换_mode_。是自动计算的像素映像的宽度，使像素图的纵横比被保存下来。

If _height_为0或负数，则返回一个空的像素图。

](qpixmap.html)

[**See also**](qpixmap.html) [isNull](qpixmap.html#isNull)（）和[Pixmap Transformations](qpixmap.html#pixmap-transformations)。

```
QPixmap QPixmap.scaledToWidth (self, int width, Qt.TransformationMode mode = Qt.FastTransformation)
```

[

返回图像的缩放复印。返回的图像被缩放为给定的_width_使用指定的变换_mode_。像素映像的高度是自动计算的，使得像素图的纵横比被保存下来。

If _width_为0或负数，则返回一个空的像素图。

](qpixmap.html)

[**See also**](qpixmap.html) [isNull](qpixmap.html#isNull)（）和[Pixmap Transformations](qpixmap.html#pixmap-transformations)。

```
QRegion exposed QPixmap.scroll (self, int dx, int dy, QRect rect)
```

[](qregion.html)

[这个方便的功能等同于调用QPixmap.scroll （_dx_，_dy_，](qregion.html)[QRect](qrect.html)（_x_，_y_，_width_，_height_） ，_exposed_） 。

此功能被引入Qt的4.6 。

**See also** [QWidget.scroll](qwidget.html#scroll)（）和[QGraphicsItem.scroll](qgraphicsitem.html#scroll)（ ） 。

```
QRegion exposed QPixmap.scroll (self, int dx, int dy, int x, int y, int width, int height)
```

[](qregion.html)

[滚动区_rect_这个像素映射的（_dx_，_dy_） 。暴露区域保持不变。您可以选择性地传递一个指针为空](qregion.html)[QRegion](qregion.html)得到，它是区域_exposed_通过滚动操作。

```
 [QPixmap](qpixmap.html) pixmap("background.png");
 [QRegion](qregion.html) exposed;
 pixmap.scroll(10, 10, pixmap.rect(), &exposed);

```

你不能滚动，而没有对像素映射活跃的画家。

此功能被引入Qt的4.6 。

**See also** [QWidget.scroll](qwidget.html#scroll)（）和[QGraphicsItem.scroll](qgraphicsitem.html#scroll)（ ） 。

```
int QPixmap.serialNumber (self)
```

```
QPixmap.setAlphaChannel (self, QPixmap)
```

```
QPixmap.setMask (self, QBitmap)
```

设置掩码位图。

此功能的合并_mask_与像素图的Alpha通道。 1在面具的像素值表示像素图的像素保持不变; 0值表示的像素是透明的。掩模必须具有相同的尺寸，因为这像素图。

设置一个空面具复位面具，留下前面透明像素的黑色。这个函数的作用时，像素图被画上是不确定的。

**Warning:**这是一个潜在的昂贵的操作。

**See also** [mask](qpixmap.html#mask)（ ）[Pixmap Transformations](qpixmap.html#pixmap-transformations)和[QBitmap](qbitmap.html)。

```
QSize QPixmap.size (self)
```

[

返回该像素映像的大小。

](qsize.html)

[**See also**](qsize.html) [width](qpixmap.html#width)（ ）[height](qpixmap.html#height)（）和[Pixmap Information](qpixmap.html#pixmap-information)。

```
QPixmap.swap (self, QPixmap other)
```

掉期的pixmap_other_与此像素图。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QImage QPixmap.toImage (self)
```

[](qimage.html)

[像素图转换为](qimage.html)[QImage](qimage.html)。返回如果转换失败，一个空的图像。

如果像素映射有1位深度，返回的图像也将是1位深。有更多的比特图像将在格式返回密切代表了底层系统。通常这将是[QImage.Format_ARGB32_Premultiplied](qimage.html#Format-enum)对于用alpha像素图和[QImage.Format_RGB32](qimage.html#Format-enum) or [QImage.Format_RGB16](qimage.html#Format-enum)为像素图没有Alpha 。

请注意，就目前而言，在单色图像alpha蒙板被忽略。

**See also** [fromImage](qpixmap.html#fromImage)（）和[Image Formats](qimage.html#image-formats)。

```
QPixmap QPixmap.transformed (self, QMatrix matrix, Qt.TransformationMode mode = Qt.FastTransformation)
```

[

返回被转换的像素图的使用给定的转型副本_transform_改造_mode_。原始像素图不改变。

](qpixmap.html)

[改造_transform_是内部调整，以补偿不需要翻译，即所产生的像素图是包含原始像素图的所有转换后的点的最小像素图。使用](qpixmap.html)[trueMatrix](qpixmap.html#trueMatrix)（ ）函数来检索用于转化像素图的实际矩阵。

此功能是缓慢的，因为它涉及到转型为[QImage](qimage.html)，非平凡的计算和转换回[QPixmap](qpixmap.html)。

**See also** [trueMatrix](qpixmap.html#trueMatrix)（）和[Pixmap Transformations](qpixmap.html#pixmap-transformations)。

```
QPixmap QPixmap.transformed (self, QTransform transform, Qt.TransformationMode mode = Qt.FastTransformation)
```

[

这是一个重载函数。

](qpixmap.html)

[此功能方便的加载_matrix_成](qpixmap.html)[QTransform](qtransform.html)并调用重载函数。

```
QMatrix QPixmap.trueMatrix (QMatrix m, int w, int h)
```

[

返回用于转化一个像素映像与给定的实际的矩阵_width_，_height_和_matrix_。

](qmatrix.html)

[当使用一个转换的像素图](qmatrix.html)[transformed](qpixmap.html#transformed)（）函数，该变换矩阵是在内部调整以补偿不需要的翻译，即[transformed](qpixmap.html#transformed)（ ）返回一个包含原始像素图的全部改造点的最小像素图。这个函数返回修改后的矩阵，正确映射点从原来的像素映射到新的像素图。

**See also** [transformed](qpixmap.html#transformed)（）和[Pixmap Transformations](qpixmap.html#pixmap-transformations)。

```
QTransform QPixmap.trueMatrix (QTransform m, int w, int h)
```

[

这是一个重载函数。

](qtransform.html)

[这种方便的功能加载矩阵_m_成](qtransform.html)[QTransform](qtransform.html)并调用与重载的函数[QTransform](qtransform.html)和宽度_w_和高度_h_。

```
int QPixmap.width (self)
```

返回像素图的宽度。

**See also** [size](qpixmap.html#size)（）和[Pixmap Information](qpixmap.html#pixmap-information)。

```
QX11Info QPixmap.x11Info (self)
```

[

**X11 only:**返回有关所使用到的像素图目前属于屏幕的X显示的配置信息。

**Warning:**此功能仅适用于X11 。

](qx11info.html)

[**See also**](qx11info.html) [Pixmap Information](qpixmap.html#pixmap-information)。

```
int QPixmap.x11PictureHandle (self)
```

**X11 only:**返回像素图的XRender的支持X11的图片处理。

这个函数将返回0，如果XRender的支持是不会被编译到Qt的，如果XRender的扩展不支持X11的显示器上，或者如果无法创建的句柄。这个函数的使用是不可移植的。

**Warning:**此功能仅适用于X11 。

**See also** [Pixmap Information](qpixmap.html#pixmap-information)。