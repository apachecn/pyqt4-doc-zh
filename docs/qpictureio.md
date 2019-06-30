# QPictureIO Class Reference

## [[QtGui](index.htm) module]

该QPictureIO类包含用于加载和保存图片的参数。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice ioDevice, str format)`
*   `__init__ (self, QString fileName, str format)`
*   `QString description (self)`
*   `QString fileName (self)`
*   `str format (self)`
*   `float gamma (self)`
*   `QIODevice ioDevice (self)`
*   `str parameters (self)`
*   `QPicture picture (self)`
*   `int quality (self)`
*   `bool read (self)`
*   `setDescription (self, QString)`
*   `setFileName (self, QString)`
*   `setFormat (self, str)`
*   `setGamma (self, float)`
*   `setIODevice (self, QIODevice)`
*   `setParameters (self, str)`
*   `setPicture (self, QPicture)`
*   `setQuality (self, int)`
*   `setStatus (self, int)`
*   `int status (self)`
*   `bool write (self)`

### Static Methods

*   `defineIOHandler (str format, str header, str flags, callable read_picture, callable write_picture)`
*   `list-of-QByteArray inputFormats ()`
*   `list-of-QByteArray outputFormats ()`
*   `QByteArray pictureFormat (QString fileName)`
*   `QByteArray pictureFormat (QIODevice)`

* * *

## Detailed Description

该QPictureIO类包含用于加载和保存图片的参数。

QPictureIO包含一个[QIODevice](qiodevice.html)对象是用于图像数据I / O。程序员可以在除了那些Qt提供了安装新的图片文件格式。

你通常不需要使用这个类;[QPicture.load](qpicture.html#load)（ ）[QPicture.save](qpicture.html#save)（ ） 。

* * *

## Method Documentation

```
QPictureIO.__init__ (self)
```

构造一个[QPictureIO](qpictureio.html)对象设置为零的所有参数。

```
QPictureIO.__init__ (self, QIODevice ioDevice, str format)
```

构造一个[QPictureIO](qpictureio.html)与I / O设备对象_ioDevice_和_format_标记。

```
QPictureIO.__init__ (self, QString fileName, str format)
```

构造一个[QPictureIO](qpictureio.html)用文件名对象_fileName_和_format_标记。

```
QPictureIO.defineIOHandler (str format, str header, str flags, callable read_picture, callable write_picture)
```

该_read_picture_参数也可能没有。

该_write_picture_参数也可能没有。

定义图片的I / O处理程序称为图片格式_format_，其使用中所定义的正则表达式被确认_header_，读取使用_readPicture_并采用书面_writePicture_。

_flags_是一个字符串的单字符标志这种格式。定义的唯一标志目前为T （大写） ，所以唯一的合法值_flags_是“T”和空字符串。 “T”型标志表示该图像文件是一个文本文件，和Qt应该把所有的换行符约定等同。 （ XPM文件和一些PPM文件是文本文件的例子。 ）

_format_用于选择处理程序写[QPicture](qpicture.html);_header_用于选择一个处理器来读取一个图像文件。

If _readPicture_是一个空指针，[QPictureIO](qpictureio.html)将无法读取图片中_format_。如果_writePicture_是一个空指针，[QPictureIO](qpictureio.html)将无法在写图片_format_。如果两者都为null，则[QPictureIO](qpictureio.html)对象是有效的，但没用。

例如：

```
 void readSVG([QPictureIO](qpictureio.html) *picture)
 {
     // read the picture using the picture->ioDevice()
 }

 void writeSVG([QPictureIO](qpictureio.html) *picture)
 {
     // write the picture using the picture->ioDevice()
 }

     // add the SVG picture handler
     // ...

```

正则表达式测试前，在文件头全部为0字节转换为1个字节。这样做是因为当Qt的是基于ASCII的，[QRegExp](qregexp.html)无法处理的字符串0字节。

正则表达式只适用于前14个字节的文件。

（请注意，如果一个handlerIO支持写入的格式，另外支持读取它， Qt支持读取和写入。如果两个处理器都支持相同的操作， Qt的选择一个武断。 ）

```
QString QPictureIO.description (self)
```

返回图片描述字符串。

**See also** [setDescription](qpictureio.html#setDescription)（ ） 。

```
QString QPictureIO.fileName (self)
```

返回当前设置的文件名。

**See also** [setFileName](qpictureio.html#setFileName)（ ） 。

```
str QPictureIO.format (self)
```

返回图片格式的字符串或0 ，如果没有格式已显式设置。

**See also** [setFormat](qpictureio.html#setFormat)（ ） 。

```
float QPictureIO.gamma (self)
```

返回在其照片将被视为伽玛值。

**See also** [setGamma](qpictureio.html#setGamma)（ ） 。

```
list-of-QByteArray QPictureIO.inputFormats ()
```

返回所支持的图像输入格式图片排序列表。

```
QIODevice QPictureIO.ioDevice (self)
```

[

返回当前设置的IO设备。

](qiodevice.html)

[**See also**](qiodevice.html) [setIODevice](qpictureio.html#setIODevice)（ ） 。

```
list-of-QByteArray QPictureIO.outputFormats ()
```

返回所支持的图像输出图像格式排序列表。

```
str QPictureIO.parameters (self)
```

返回图片的参数字符串。

**See also** [setParameters](qpictureio.html#setParameters)（ ） 。

```
QPicture QPictureIO.picture (self)
```

[

返回当前设置的图片。

](qpicture.html)

[**See also**](qpicture.html) [setPicture](qpictureio.html#setPicture)（ ） 。

```
QByteArray QPictureIO.pictureFormat (QString fileName)
```

[

返回一个字符串，该字符串指定的文件的图片格式_fileName_，或null，如果文件不能被读取或者格式无法识别。

](qbytearray.html)

```
QByteArray QPictureIO.pictureFormat (QIODevice)
```

[

这是一个重载函数。

返回一个字符串，它指定从IO设备读取图片的图片格式_d_，或者0，如果设备无法读取或者格式无法识别。

确保_d_是在设备（例如，在文件的开头）的位置上。

](qbytearray.html)

[**See also**](qbytearray.html) [QIODevice.at](index.htm#at)（ ） 。

```
int QPictureIO.quality (self)
```

返回写入的图像的质量，相关的压缩比。

**See also** [setQuality](qpictureio.html#setQuality)（）和[QPicture.save](qpicture.html#save)（ ） 。

```
bool QPictureIO.read (self)
```

读取图片到内存中，并返回True，如果图片是成功读取，否则返回False 。

在阅读的图片，你必须设置一个IO设备或文件名。如果两个IO设备和一个文件名被设置， IO装置将被使用。

设置图像文件的格式字符串是可选的。

请注意，这个函数_not_设置[format](qpictureio.html#format)用于读取图像。如果您需要这些信息，使用[pictureFormat](qpictureio.html#pictureFormat)（ ）静态函数。

例如：

```
         [QPictureIO](qpictureio.html) iio;
         [QPixmap](qpixmap.html)  pixmap;
         iio.setFileName("vegeburger.pic");
         if (iio.read()) {        // OK
             [QPicture](qpicture.html) picture = iio.picture();
             [QPainter](qpainter.html) painter(&pixmap);
             painter.drawPicture(0, 0, picture);
         }

```

**See also** [setIODevice](qpictureio.html#setIODevice)（ ）[setFileName](qpictureio.html#setFileName)（ ）[setFormat](qpictureio.html#setFormat)（ ）[write](qpictureio.html#write)（）和[QPixmap.load](qpixmap.html#load)（ ） 。

```
QPictureIO.setDescription (self, QString)
```

将画面设置描述字符串为支持图片说明，以图片处理程序_description_。

目前， Qt所支持无图像格式使用的描述字符串。

**See also** [description](qpictureio.html#description)（ ） 。

```
QPictureIO.setFileName (self, QString)
```

设置读取或写入一个图片文件的名称从到_fileName_。

**See also** [fileName](qpictureio.html#fileName)（）和[setIODevice](qpictureio.html#setIODevice)（ ） 。

```
QPictureIO.setFormat (self, str)
```

设置图片格式_format_对图像进行读取或写入。

有必要写入一个画面之前指定格式，但它不是必需的阅读一个图像之前指定的格式。

如果没有指定格式已定， Qt的猜测图片的格式读取它。如果格式被设置，如果它有格式的图片才会被读取。

**See also** [read](qpictureio.html#read)（ ）[write](qpictureio.html#write)（）和[format](qpictureio.html#format)（ ） 。

```
QPictureIO.setGamma (self, float)
```

设置在该画面将被视为对伽玛值_gamma_。如果图像格式存储的伽马值的量，图像拟被使用，那么该设置将被用于修改图像。设置为0.0将禁用gamma校正（即文件中的任何规范将被忽略） 。

默认值是0.0 。

**See also** [gamma](qpictureio.html#gamma)（ ） 。

```
QPictureIO.setIODevice (self, QIODevice)
```

设置IO设备用于读取或写入的图像。

设置IO设备使照片可读取/写入任何面向块[QIODevice](qiodevice.html)。

If _ioDevice_不为空，这个IO设备将复盖文件名设置。

**See also** [setFileName](qpictureio.html#setFileName)（ ） 。

```
QPictureIO.setParameters (self, str)
```

图片的参数字符串设置为_parameters_。这对于那些需要特殊参数图片处理程序。

虽然Qt所支持当前图片格式忽略的参数字符串，它可能会在未来的扩展或贡献（例如， JPEG）使用。

**See also** [parameters](qpictureio.html#parameters)（ ） 。

```
QPictureIO.setPicture (self, QPicture)
```

将画面设置为_picture_。

**See also** [picture](qpictureio.html#picture)（ ） 。

```
QPictureIO.setQuality (self, int)
```

设置写入的图像的质量_q_，相关的压缩比。

_q_必须在范围-1 .. 100 。指定0以获得小的压缩文件， 100为大型未压缩的文件。 （-1表示默认的压缩。 ）

**See also** [quality](qpictureio.html#quality)（）和[QPicture.save](qpicture.html#save)（ ） 。

```
QPictureIO.setStatus (self, int)
```

将画面设置的IO状态_status_。一个非零值表示错误，而0表示IO操作是成功的。

**See also** [status](qpictureio.html#status)（ ） 。

```
int QPictureIO.status (self)
```

返回图片的IO状态。一个非零值表示错误，而0表示IO操作是成功的。

**See also** [setStatus](qpictureio.html#setStatus)（ ） 。

```
bool QPictureIO.write (self)
```

写一个图片IO设备并返回True如果图片被成功写入，否则返回False 。

之前写一个图片，你必须设置一个IO设备或文件名。如果两个IO设备和一个文件名被设置， IO装置将被使用。

图片将使用指定的图片格式写入。

例如：

```
         [QPictureIO](qpictureio.html) iio;
         [QPicture](qpicture.html)   picture;
         [QPainter](qpainter.html) painter(&picture);
         painter.drawPixmap(0, 0, pixmap);
         iio.setPicture(picture);
         iio.setFileName("vegeburger.pic");
         iio.setFormat("PIC");
         if (iio.write())
             return true; // returned true if written successfully

```

**See also** [setIODevice](qpictureio.html#setIODevice)（ ）[setFileName](qpictureio.html#setFileName)（ ）[setFormat](qpictureio.html#setFormat)（ ）[read](qpictureio.html#read)（）和[QPixmap.save](qpixmap.html#save)（ ） 。