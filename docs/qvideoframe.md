# QVideoFrame Class Reference

## [[QtMultimedia](index.htm) module]

该QVideoFrame类提供​​的视频数据的帧的表示。[More...](#details)

### Types

*   `enum FieldType { ProgressiveFrame, TopField, BottomField, InterlacedFrame }`
*   `enum PixelFormat { Format_Invalid, Format_ARGB32, Format_ARGB32_Premultiplied, Format_RGB32, ..., Format_User }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QAbstractVideoBuffer buffer, QSize size, PixelFormat format)`
*   `__init__ (self, int bytes, QSize size, int bytesPerLine, PixelFormat format)`
*   `__init__ (self, QImage image)`
*   `__init__ (self, QVideoFrame other)`
*   `sip.voidptr bits (self)`
*   `int bytesPerLine (self)`
*   `int endTime (self)`
*   `FieldType fieldType (self)`
*   `QVariant handle (self)`
*   `QAbstractVideoBuffer.HandleType handleType (self)`
*   `int height (self)`
*   `bool isMapped (self)`
*   `bool isReadable (self)`
*   `bool isValid (self)`
*   `bool isWritable (self)`
*   `bool map (self, QAbstractVideoBuffer.MapMode mode)`
*   `QAbstractVideoBuffer.MapMode mapMode (self)`
*   `int mappedBytes (self)`
*   `PixelFormat pixelFormat (self)`
*   `setEndTime (self, int time)`
*   `setFieldType (self, FieldType)`
*   `setStartTime (self, int time)`
*   `QSize size (self)`
*   `int startTime (self)`
*   `unmap (self)`
*   `int width (self)`

### Static Methods

*   `QImage.Format imageFormatFromPixelFormat (PixelFormat format)`
*   `PixelFormat pixelFormatFromImageFormat (QImage.Format format)`

* * *

## Detailed Description

该QVideoFrame类提供​​的视频数据的帧的表示。

一个QVideoFrame封装了一个视频帧，以及有关帧信息的数据。

一视频帧的内容可以通过使用被映射到存储器中的[map](qvideoframe.html#map)（）函数。而映射到的视频数据可以使用访问[bits](qvideoframe.html#bits)（）函数返回一个指向缓冲区的指针，它的总的大小是由给定的[mappedBytes](qvideoframe.html#mappedBytes)（）和每一行的大小由下式给出[bytesPerLine](qvideoframe.html#bytesPerLine)（ ） 。的返回值[handle](qvideoframe.html#handle)（）函数可用于使用内部缓冲器的本机API来访问帧数据。

在一个QVideoFrame视频数据被封装在一个[QAbstractVideoBuffer](qabstractvideobuffer.html)。一个QVideoFrame可以从任何缓冲类型的子类的构造[QAbstractVideoBuffer](qabstractvideobuffer.html)类。

**Note:**QVideoFrame是公开共享的，以视频帧所做的任何更改也将适用于任何副本。

* * *

## Type Documentation

```
QVideoFrame.FieldType
```

指定的隔行扫描视频帧所属的领域。

| Constant | Value | Description |
| --- | --- | --- |
| `QVideoFrame.ProgressiveFrame` | `0` | 该框架是没有交错。 |
| `QVideoFrame.TopField` | `1` | 该帧包含一个顶场。 |
| `QVideoFrame.BottomField` | `2` | 该帧包含一个底场。 |
| `QVideoFrame.InterlacedFrame` | `3` | 该帧包含一个合并的顶和底场。 |

```
QVideoFrame.PixelFormat
```

列举的视频数据类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QVideoFrame.Format_Invalid` | `0` | 该框架是无效的。 |
| `QVideoFrame.Format_ARGB32` | `1` | 该帧是使用32位ARGB格式（ 0xAARRGGBB ）存储。这等效于[QImage.Format_ARGB32](qimage.html#Format-enum)。 |
| `QVideoFrame.Format_ARGB32_Premultiplied` | `2` | 使用预乘32位ARGB格式（ 0xAARRGGBB ）存储帧。这等效于[QImage.Format_ARGB32_Premultiplied](qimage.html#Format-enum)。 |
| `QVideoFrame.Format_RGB32` | `3` | 使用32位RGB格式（ 0xffRRGGBB ）存储帧。这等效于[QImage.Format_RGB32](qimage.html#Format-enum) |
| `QVideoFrame.Format_RGB24` | `4` | 该框架是采用24位RGB格式（ 8-8-8 ）存储。这等效于[QImage.Format_RGB888](qimage.html#Format-enum) |
| `QVideoFrame.Format_RGB565` | `5` | 该帧是使用一个16位的RGB格式（ 5-6-5 ）存储。这等效于[QImage.Format_RGB16](qimage.html#Format-enum)。 |
| `QVideoFrame.Format_RGB555` | `6` | 该帧是使用一个16位的RGB格式（ 5-5-5 ）存储。这等效于[QImage.Format_RGB555](qimage.html#Format-enum)。 |
| `QVideoFrame.Format_ARGB8565_Premultiplied` | `7` | 该框架是用一个24位预乘的ARGB格式（ 8-6-6-5 ）存储。 |
| `QVideoFrame.Format_BGRA32` | `8` | 该帧是使用32位ARGB格式（ 0xBBGGRRAA ）存储。 |
| `QVideoFrame.Format_BGRA32_Premultiplied` | `9` | 该框架是使用预乘32位的BGRA格式存储。 |
| `QVideoFrame.Format_BGR32` | `10` | 该帧是使用一个32位的BGR格式（ 0xBBGGRRff ）存储。 |
| `QVideoFrame.Format_BGR24` | `11` | 该框架是使用24位BGR格式（ 0xBBGGRR ）存储。 |
| `QVideoFrame.Format_BGR565` | `12` | 该帧是使用一个16位的BGR格式（ 5-6-5 ）存储。 |
| `QVideoFrame.Format_BGR555` | `13` | 该帧是使用一个16位的BGR格式（ 5-5-5 ）存储。 |
| `QVideoFrame.Format_BGRA5658_Premultiplied` | `14` | 该框架是用一个24位预乘的BGRA格式（ 5-6-5-8 ）存储。 |
| `QVideoFrame.Format_AYUV444` | `15` | 该框架是使用填充32位AYUV格式（ 0xAAYYUUVV ）存储。 |
| `QVideoFrame.Format_AYUV444_Premultiplied` | `16` | 该框架是使用填充预乘32位AYUV格式（ 0xAAYYUUVV ）存储。 |
| `QVideoFrame.Format_YUV444` | `17` | 该框架是使用24 - bit包装YUV格式（ 8-8-8 ）存储。 |
| `QVideoFrame.Format_YUV420P` | `18` | 该帧是使用与U和V平面的8位每个组件的平面YUV格式的水平和垂直子采样，即， U和V平面的高度和宽度的一半， Y平面的存储。 |
| `QVideoFrame.Format_YV12` | `19` | 该帧被使用与所述V和U平面的8位每个组件的平面YVU格式水平和垂直子采样，即V和U平面的高度和宽度的一半， Y平面的存储。 |
| `QVideoFrame.Format_UYVY` | `20` | 该帧是使用与U和V平面的8位每个组件填充YUV格式的水平子采样（ UYVY ）存储的，也就是两个水平相邻的像素被作为一个32位的宏像素具有用于每个像素的Y值和存储普通U和V值。 |
| `QVideoFrame.Format_YUYV` | `21` | 该帧是使用与U和V平面的8位每个组件填充YUV格式的水平子采样（ YUYV ）存储的，也就是两个水平相邻的像素被作为一个32位的宏像素具有用于每个像素的Y值和存储普通U和V值。 |
| `QVideoFrame.Format_NV12` | `22` | 该帧被使用每组件半平面YUV格式的8位与后跟一个水平和垂直子采样，填充UV平面（UV）一个Y平面（Y）存储起来。 |
| `QVideoFrame.Format_NV21` | `23` | 该帧被使用每组件半平面YUV格式的8位与后跟一个水平和垂直子采样一Y平面（Y）存储，包装VU平面（ VU） 。 |
| `QVideoFrame.Format_IMC1` | `24` | 该帧是使用与U和V平面的8位每个组件的平面YUV格式的水平和垂直子采样存储。这是类似于Format_YUV420P类型，不同的是每U和V平面的线的字节被填充为同一跨距为Y平面。 |
| `QVideoFrame.Format_IMC2` | `25` | 该帧是使用与U和V平面的8位每个组件的平面YUV格式的水平和垂直子采样存储。这是类似于Format_YUV420P类型，不同的是U和V平面的线被交织，即U数据的每一行之后是一条线的V数据的创建相同的跨距为Y数据的一条线。 |
| `QVideoFrame.Format_IMC3` | `26` | 该帧被使用与所述V和U平面水平和垂直子采样的一个8位的每部分的平面YVU格式存储。这是类似于Format_YV12类型，不同之处在于每对V和U平面的线的字节被填充为相同的跨距为Y平面。 |
| `QVideoFrame.Format_IMC4` | `27` | 该帧被使用与所述V和U平面水平和垂直子采样的一个8位的每部分的平面YVU格式存储。这是类似于Format_YV12类型，除了V和U平面的线是交错的，即V数据的每一行之后是一条线的U数据创建相同的跨距为Y数据的一条线。 |
| `QVideoFrame.Format_Y8` | `28` | 该帧被使用8位灰度格式存储。 |
| `QVideoFrame.Format_Y16` | `29` | 该帧是使用一个16位线性灰度格式存储。小尾数。 |
| `QVideoFrame.Format_User` | `1000` | 用户定义的像素格式起始值。 |

* * *

## Method Documentation

```
QVideoFrame.__init__ (self)
```

构造一个空的视频帧。

```
QVideoFrame.__init__ (self, QAbstractVideoBuffer buffer, QSize size, PixelFormat format)
```

构造一个视频帧从一个_buffer_给定像素的_format_和_size_以像素为单位。

**Note:**这不会增加视频缓冲区的引用计数。

```
QVideoFrame.__init__ (self, int bytes, QSize size, int bytesPerLine, PixelFormat format)
```

构造的给定像素的视频帧_format_和_size_以像素为单位。

该_bytesPerLine_（步幅），以字节为单位的每个扫描线的长度，并_bytes_是一个字节必须被分配给该帧的总数。

```
QVideoFrame.__init__ (self, QImage image)
```

构造一个视频帧从_image_。

**Note:**这将构造一个无效的视频帧，如果没有帧类型等效于图像格式。

**See also** [pixelFormatFromImageFormat](qvideoframe.html#pixelFormatFromImageFormat)（ ） 。

```
QVideoFrame.__init__ (self, QVideoFrame other)
```

构造的副本_other_。

```
sip.voidptr QVideoFrame.bits (self)
```

返回一个指向帧数据缓冲区的开始。

而帧数据是这个值才有效[mapped](qvideoframe.html#map)。

**See also** [map](qvideoframe.html#map)（ ）[mappedBytes](qvideoframe.html#mappedBytes)（）和[bytesPerLine](qvideoframe.html#bytesPerLine)（ ） 。

```
int QVideoFrame.bytesPerLine (self)
```

返回的字节中的扫描线的数目。

**Note:**这是每个唯一的第一平面的线的字节数。随后飞机每行的字节数应计算为每帧类型。

而帧数据是这个值才有效[mapped](qvideoframe.html#map)。

**See also** [bits](qvideoframe.html#bits)（ ）[map](qvideoframe.html#map)（）和[mappedBytes](qvideoframe.html#mappedBytes)（ ） 。

```
int QVideoFrame.endTime (self)
```

返回演示文稿时，当一帧应该停止显示。

**See also** [setEndTime](qvideoframe.html#setEndTime)（ ） 。

```
FieldType QVideoFrame.fieldType (self)
```

[

返回一个隔行视频帧所属的领域。

如果视频不隔行扫描，这将返回WholeFrame 。

](qvideoframe.html#FieldType-enum)

[**See also**](qvideoframe.html#FieldType-enum) [setFieldType](qvideoframe.html#setFieldType)（ ） 。

```
QVariant QVideoFrame.handle (self)
```

返回一个特定类型的句柄，一个视频帧的缓冲区。

对于OpenGL纹理，这将是质感的ID 。

**See also** [QAbstractVideoBuffer.handle](qabstractvideobuffer.html#handle)（ ） 。

```
QAbstractVideoBuffer.HandleType QVideoFrame.handleType (self)
```

[

返回一个视频帧的句柄类型。

```
int QVideoFrame.height (self)
```

返回一个视频帧的高度。

](qabstractvideobuffer.html#HandleType-enum)

```
QImage.Format QVideoFrame.imageFormatFromPixelFormat (PixelFormat format)
```

[](qimage.html#Format-enum)

[返回一个图像格式等同于一个视频帧的像素_format_。如果没有相等的格式](qimage.html#Format-enum)[QImage.Format_Invalid](qimage.html#Format-enum)返回来代替。

```
bool QVideoFrame.isMapped (self)
```

如果一个视频帧的内容被当前映射到系统存储器标识。

这是一个方便的功能，它会检查[MapMode](qabstractvideobuffer.html#MapMode-enum)帧不等于[QAbstractVideoBuffer.NotMapped](qabstractvideobuffer.html#MapMode-enum)。

返回True如果视频帧的内容映射到系统内存，否则返回False 。

**See also** [mapMode](qvideoframe.html#mapMode)（）和[QAbstractVideoBuffer.MapMode](qabstractvideobuffer.html#MapMode-enum)。

```
bool QVideoFrame.isReadable (self)
```

如果确定一个视频帧的映射内容物从帧中读出时，它被映射。

这是一个方便的功能，如果它检查[MapMode](qabstractvideobuffer.html#MapMode-enum)包含[QAbstractVideoBuffer.WriteOnly](qabstractvideobuffer.html#MapMode-enum)标志。

返回True如果映射的内存中的内容是从视频帧读出，否则返回False 。

**See also** [mapMode](qvideoframe.html#mapMode)（）和[QAbstractVideoBuffer.MapMode](qabstractvideobuffer.html#MapMode-enum)。

```
bool QVideoFrame.isValid (self)
```

识别的视频帧是否是有效的。

无效帧都有一个与之关联的视频缓冲器。

返回True如果该帧是有效的，并且假，如果事实并非如此。

```
bool QVideoFrame.isWritable (self)
```

如果识别视频帧的映射内容时，帧映射将被保存。

这是一个方便的功能，如果它检查[MapMode](qabstractvideobuffer.html#MapMode-enum)包含[QAbstractVideoBuffer.WriteOnly](qabstractvideobuffer.html#MapMode-enum)标志。

返回True ，如果视频帧将被更新，否则取消映射时，假。

**Note:**改变被映射在只读模式中的帧的数据的结果是不确定的。根据不同的缓冲区实现的变更可能会持续存在，或者更糟改变一个共享缓冲区。

**See also** [mapMode](qvideoframe.html#mapMode)（）和[QAbstractVideoBuffer.MapMode](qabstractvideobuffer.html#MapMode-enum)。

```
bool QVideoFrame.map (self, QAbstractVideoBuffer.MapMode mode)
```

映射一个视频帧的内容到存储器中。

地图_mode_指示是否映射存储器中的内容应被读出和/或写入帧。如果映射模式包括[QAbstractVideoBuffer.ReadOnly](qabstractvideobuffer.html#MapMode-enum)标志映射的内存将被填充的视频帧的内容映射时。如果地图模式inclues的[QAbstractVideoBuffer.WriteOnly](qabstractvideobuffer.html#MapMode-enum)映射的内存的标志内容将被保存在帧映射时。

而映射的一个视频帧的内容可以直接通过由返回的指针来访问[bits](qvideoframe.html#bits)（）函数。

当访问数据不再需要，一定要调用[unmap](qvideoframe.html#unmap)（ ）函数释放映射内存。

返回True如果缓冲区被映射到内存中给定的_mode_否则为False。

**See also** [unmap](qvideoframe.html#unmap)（ ）[mapMode](qvideoframe.html#mapMode)（）和[bits](qvideoframe.html#bits)（ ） 。

```
QAbstractVideoBuffer.MapMode QVideoFrame.mapMode (self)
```

[

返回一个视频帧被映射到系统存储器英寸的模式

](qabstractvideobuffer.html#MapMode-enum)

[**See also**](qabstractvideobuffer.html#MapMode-enum) [map](qvideoframe.html#map)（）和[QAbstractVideoBuffer.MapMode](qabstractvideobuffer.html#MapMode-enum)。

```
int QVideoFrame.mappedBytes (self)
```

返回由对应的帧数据所佔用的字节数。

而帧数据是这个值才有效[mapped](qvideoframe.html#map)。

**See also** [map](qvideoframe.html#map)（ ） 。

```
PixelFormat QVideoFrame.pixelFormat (self)
```

[

返回一个视频帧的颜色格式。

](qvideoframe.html#PixelFormat-enum)

```
PixelFormat QVideoFrame.pixelFormatFromImageFormat (QImage.Format format)
```

[

返回一个视频像素格式相当于一个图像_format_。如果没有相等的格式QVideoFrame.InvalidType返回来代替。

```
QVideoFrame.setEndTime (self, int time)
```

设置演示文稿_time_当一个帧应停止显示。

](qvideoframe.html#PixelFormat-enum)

[**See also**](qvideoframe.html#PixelFormat-enum) [endTime](qvideoframe.html#endTime)（ ） 。

```
QVideoFrame.setFieldType (self, FieldType)
```

设置_field_隔行扫描视频帧属于。

**See also** [fieldType](qvideoframe.html#fieldType)（ ） 。

```
QVideoFrame.setStartTime (self, int time)
```

设置演示文稿_time_当帧的显示方式。

**See also** [startTime](qvideoframe.html#startTime)（ ） 。

```
QSize QVideoFrame.size (self)
```

[

返回一个视频帧的大小。

```
int QVideoFrame.startTime (self)
```

返回时，应显示的帧的显示时间。

](qsize.html)

[**See also**](qsize.html) [setStartTime](qvideoframe.html#setStartTime)（ ） 。

```
QVideoFrame.unmap (self)
```

发布映射的内存[map](qvideoframe.html#map)（）函数。

如果[MapMode](qabstractvideobuffer.html#MapMode-enum)包括[QAbstractVideoBuffer.WriteOnly](qabstractvideobuffer.html#MapMode-enum)标志，这将持续映射内存的当前内容到视频帧。

**See also** [map](qvideoframe.html#map)（ ） 。

```
int QVideoFrame.width (self)
```

返回一个视频帧的宽度。