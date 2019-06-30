# QPicture Class Reference

## [[QtGui](index.htm) module]

该QPicture类是一个绘图设备，记录和重放[QPainter](qpainter.html)的命令。[More...](#details)

继承[QPaintDevice](qpaintdevice.html)。

### Methods

*   `__init__ (self, int formatVersion = -1)`
*   `__init__ (self, QPicture)`
*   `QRect boundingRect (self)`
*   `str data (self)`
*   `detach (self)`
*   `int devType (self)`
*   `bool isDetached (self)`
*   `bool isNull (self)`
*   `bool load (self, QIODevice dev, str format = None)`
*   `bool load (self, QString fileName, str format = None)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric m)`
*   `QPaintEngine paintEngine (self)`
*   `bool play (self, QPainter p)`
*   `bool save (self, QIODevice dev, str format = None)`
*   `bool save (self, QString fileName, str format = None)`
*   `setBoundingRect (self, QRect r)`
*   `setData (self, str data)`
*   `int size (self)`
*   `swap (self, QPicture other)`

### Static Methods

*   `QStringList inputFormatList ()`
*   `list-of-QByteArray inputFormats ()`
*   `QStringList outputFormatList ()`
*   `list-of-QByteArray outputFormats ()`
*   `str pictureFormat (QString fileName)`

* * *

## Detailed Description

该QPicture类是一个绘图设备，记录和重放[QPainter](qpainter.html)的命令。

的图片序列画家命令IO设备在一个平台无关的格式。它们有时被称为元文件。

Qt的图片用一个专有的二进制格式。不像本地图片（元文件）在许多窗口系统格式， Qt的图片有关于他们的内容没有限制。所有可以被画上一个小部件或像素（例如，字体，像素图，区域，变换图形等）也可以被存储在一个图像。

QPicture是与分辨率无关，即QPicture可以显示在不同的设备（例如SVG ， PDF，PS ，打印机和屏幕）寻找相同。这是，例如，需要所见即所得的打印预览。 QPicture运行在默认的系统DPI ，并缩放画家，以符合视视窗系统上的分辨率的差异。

如何进行拍摄的例子：

```
         QPicture picture;
         [QPainter](qpainter.html) painter;
         painter.begin(&picture);           // paint in picture
         painter.drawEllipse(10,20, 80,70); // draw an ellipse
         painter.end();                     // painting done
         picture.save("drawing.pic");       // save picture

```

需要注意的是画家的命令列表被重置在每次调用[QPainter.begin](qpainter.html#begin)（）函数。

如何重播图片的例子：

```
         QPicture picture;
         picture.load("drawing.pic");           // load picture
         [QPainter](qpainter.html) painter;
         painter.begin(&myImage);               // paint in myImage
         painter.drawPicture(0, 0, picture);    // draw the picture at (0,0)
         painter.end();                         // painting done

```

图片也可以使用拉伸[play](qpicture.html#play)（ ） 。关于一个图像的一些基本数据是可用的，例如，[size](qpicture.html#size)（ ）[isNull](qpicture.html#isNull)（）和[boundingRect](qpicture.html#boundingRect)（ ） 。

* * *

## Method Documentation

```
QPicture.__init__ (self, int formatVersion = -1)
```

构造一个空的图片。

该_formatVersion_参数可以被用于_create_一[QPicture](qpicture.html)可以由与Qt的早期版本编译的应用程序可以读取。

请注意，默认formatVersion是-1，表示当前版本，即Qt的4.0 7 formatVersion是一样的为默认值-1 formatVersion 。

是不是在Qt的4.0支持Qt的早期版本生成的读图时代。

```
QPicture.__init__ (self, QPicture)
```

构造的副本_pic_。

这个构造函数是快的感谢[implicit sharing](index.htm)。

```
QRect QPicture.boundingRect (self)
```

[

返回图片的边界矩形或无效矩形如果图片不包含任何数据。

](qrect.html)

[**See also**](qrect.html) [setBoundingRect](qpicture.html#setBoundingRect)（ ） 。

```
str QPicture.data (self)
```

返回一个指向图片数据。指针才有效，直到下一个非const函数被调用的这张图片。返回的指针为0，如果图像不包含任何数据。

**See also** [setData](qpicture.html#setData)（ ）[size](qpicture.html#size)（）和[isNull](qpicture.html#isNull)（ ） 。

```
QPicture.detach (self)
```

```
int QPicture.devType (self)
```

```
QStringList QPicture.inputFormatList ()
```

```
list-of-QByteArray QPicture.inputFormats ()
```

```
bool QPicture.isDetached (self)
```

```
bool QPicture.isNull (self)
```

返回True如果图像不包含任何数据，否则返回False 。

```
bool QPicture.load (self, QIODevice dev, str format = None)
```

加载一幅图片从指定的文件_fileName_如果成功返回True，否则返回False 。

请注意，这个_format_参数已被取代，不会有任何效果。

**See also** [save](qpicture.html#save)（ ） 。

```
bool QPicture.load (self, QString fileName, str format = None)
```

这是一个重载函数。

_dev_是该装置用于载入。

```
int QPicture.metric (self, QPaintDevice.PaintDeviceMetric m)
```

```
QStringList QPicture.outputFormatList ()
```

```
list-of-QByteArray QPicture.outputFormats ()
```

```
QPaintEngine QPicture.paintEngine (self)
```

[

```
str QPicture.pictureFormat (QString fileName)
```

```
bool QPicture.play (self, QPainter p)
```

重播的画面使用_painter_，并成功返回True ，否则返回False 。

](qpaintengine.html)

[这个函数完全一样](qpaintengine.html)[QPainter.drawPicture](qpainter.html#drawPicture)（ ）与（X，Y ）=（0 ，0）。

```
bool QPicture.save (self, QIODevice dev, str format = None)
```

保存图片到由指定的文件_fileName_如果成功返回True，否则返回False 。

请注意，这个_format_参数已被取代，不会有任何效果。

**See also** [load](qpicture.html#load)（ ） 。

```
bool QPicture.save (self, QString fileName, str format = None)
```

这是一个重载函数。

_dev_是设备用于储蓄。

```
QPicture.setBoundingRect (self, QRect r)
```

设置图片的边界矩形_r_。自动计算的值被复盖。

**See also** [boundingRect](qpicture.html#boundingRect)（ ） 。

```
QPicture.setData (self, str data)
```

直接将画面设置数据_data_和_size_。此功能将输入数据复制。

**See also** [data](qpicture.html#data)（）和[size](qpicture.html#size)（ ） 。

```
int QPicture.size (self)
```

返回的图片数据的大小。

**See also** [data](qpicture.html#data)（ ） 。

```
QPicture.swap (self, QPicture other)
```

掉期图片_other_与此图片。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。