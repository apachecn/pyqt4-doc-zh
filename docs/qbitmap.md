# QBitmap Class Reference

## [[QtGui](index.htm) module]

该QBitmap类提供单色（ 1位深度）的像素图。[More...](#details)

继承[QPixmap](qpixmap.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPixmap)`
*   `__init__ (self, int w, int h)`
*   `__init__ (self, QSize)`
*   `__init__ (self, QString fileName, str format = None)`
*   `__init__ (self, QVariant variant)`
*   `__init__ (self, QBitmap)`
*   `clear (self)`
*   `swap (self, QBitmap other)`
*   `QBitmap transformed (self, QMatrix)`
*   `QBitmap transformed (self, QTransform matrix)`

### Static Methods

*   `QBitmap fromData (QSize size, str bits, QImage.Format format = QImage.Format_MonoLSB)`
*   `QBitmap fromImage (QImage image, Qt.ImageConversionFlags flags = Qt.AutoColor)`

* * *

## Detailed Description

该QBitmap类提供单色（ 1位深度）的像素图。

该QBitmap类是单色主要用于创建自定义屏幕外漆设备[QCursor](qcursor.html)和[QBrush](qbrush.html)对象，构建[QRegion](qregion.html)对象，并设置口罩像素图和部件。

QBitmap是[QPixmap](qpixmap.html)子类确保一个深度为1 ，除了它具有为0的深度空对象。如果用深度大于1的像素图被分配给一个位图，该位图将被自动抖动。

使用[QColor](qcolor.html)对象[Qt.color0](qt.html#GlobalColor-enum)和[Qt.color1](qt.html#GlobalColor-enum)在QBitmap对象（或绘图时[QPixmap](qpixmap.html)随着深度的1反对） 。

与绘画[Qt.color0](qt.html#GlobalColor-enum)设置位图位为0，并用绘画[Qt.color1](qt.html#GlobalColor-enum)设置位为1位。为位图， 0位表示背景（或透明的像素）和1 - 位指示前景（或不透明像素）。使用[clear](qbitmap.html#clear)（ ）函数来设置所有位[Qt.color0](qt.html#GlobalColor-enum)。注意，使用[Qt.black](qt.html#GlobalColor-enum)和[Qt.white](qt.html#GlobalColor-enum)颜色没有任何意义，因为[QColor.pixel](index.htm#pixel)（ ）值不一定是0和黑1白。

该QBitmap类提供[transformed](qbitmap.html#transformed)（ ）函数返回的位图的转化副本;使用[QTransform](qtransform.html)参数平移，缩放，剪切，旋转位图。此外， QBitmap提供静态[fromData](qbitmap.html#fromData)（ ）函数，它返回从给定的构造位图`uchar`数据，并且将静态[fromImage](qbitmap.html#fromImage)（ ）函数返回的转换副本[QImage](qimage.html)对象。

就像[QPixmap](qpixmap.html)类， QBitmap通过使用隐式数据共享进行了优化。欲了解更多信息，请参阅[Implicit Data Sharing](index.htm#implicit-data-sharing)文档。

* * *

## Method Documentation

```
QBitmap.__init__ (self)
```

构造一个空的位图。

**See also** [QPixmap.isNull](qpixmap.html#isNull)（ ） 。

```
QBitmap.__init__ (self, QPixmap)
```

构造一个位图，它是给定的一个副本_pixmap_。

如果该像素图的深度大于1时，所得到的位图将被自动抖动。

**See also** [QPixmap.depth](qpixmap.html#depth)（ ）[fromImage](qbitmap.html#fromImage)（）和[fromData](qbitmap.html#fromData)（ ） 。

```
QBitmap.__init__ (self, int w, int h)
```

构造一个位图与给定_width_和_height_。像素内是未初始化的。

**See also** [clear](qbitmap.html#clear)（ ） 。

```
QBitmap.__init__ (self, QSize)
```

构造一个位图与给定_size_。位图中的像素被初始化。

**See also** [clear](qbitmap.html#clear)（ ） 。

```
QBitmap.__init__ (self, QString fileName, str format = None)
```

构造一个位图从给定的指定的文件_fileName_。如果文件不存在，或者有未知格式，位图变成一个空的位图。

该_fileName_和_format_参数上传递[QPixmap.load](qpixmap.html#load)（）函数。如果文件格式使用每像素1位以上，由此产生的位图将被自动抖动。

**See also** [QPixmap.isNull](qpixmap.html#isNull)（）和[QImageReader.imageFormat](qimagereader.html#imageFormat)（ ） 。

```
QBitmap.__init__ (self, QVariant variant)
```

```
QBitmap.__init__ (self, QBitmap)
```

```
QBitmap.clear (self)
```

清除该位图，它的所有位设置为[Qt.color0](qt.html#GlobalColor-enum)。

```
QBitmap QBitmap.fromData (QSize size, str bits, QImage.Format format = QImage.Format_MonoLSB)
```

[

构造一个位图与给定_size_，并且将内容发送到_bits_提供。

](qbitmap.html)

[位图数据必须字节对齐的，由指定的位顺序提供_monoFormat_。单格式必须是](qbitmap.html)[QImage.Format_Mono](qimage.html#Format-enum) or [QImage.Format_MonoLSB](qimage.html#Format-enum)。使用[QImage.Format_Mono](qimage.html#Format-enum)指定的XBM格式的数据。

**See also** [fromImage](qbitmap.html#fromImage)（ ） 。

```
QBitmap QBitmap.fromImage (QImage image, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

[

返回给定的一个副本_image_使用指定的图像变换转换为位图_flags_。

](qbitmap.html)

[**See also**](qbitmap.html) [fromData](qbitmap.html#fromData)（ ） 。

```
QBitmap.swap (self, QBitmap other)
```

掉期的位图_other_与此位图。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QBitmap QBitmap.transformed (self, QMatrix)
```

[

根据给定返回此位图的副本，转化_matrix_。

](qbitmap.html)

[**See also**](qbitmap.html) [QPixmap.transformed](qpixmap.html#transformed)（ ） 。

```
QBitmap QBitmap.transformed (self, QTransform matrix)
```

[](qbitmap.html)