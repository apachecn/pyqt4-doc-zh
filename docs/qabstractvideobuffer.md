# QAbstractVideoBuffer Class Reference

## [[QtMultimedia](index.htm) module]

该QAbstractVideoBuffer类是视频数据的抽象。[More...](#details)

### Types

*   `enum HandleType { NoHandle, GLTextureHandle, XvShmImageHandle, CoreImageHandle, QPixmapHandle, UserHandle }`
*   `enum MapMode { NotMapped, ReadOnly, WriteOnly, ReadWrite }`

### Methods

*   `__init__ (self, HandleType type)`
*   `QVariant handle (self)`
*   `HandleType handleType (self)`
*   `(sip.voidptr, int numBytes, int bytesPerLine) map (self, MapMode mode)`
*   `MapMode mapMode (self)`
*   `unmap (self)`

* * *

## Detailed Description

该QAbstractVideoBuffer类是视频数据的抽象。

该[QVideoFrame](qvideoframe.html)类利用一个QAbstractVideoBuffer的内部参考视频数据的缓冲区。创建QAbstractVideoBuffer的子类可以让你从预分配或静态缓冲构造的视频帧。

一个缓冲区的内容可以通过使用缓冲映射到存储器进行访问的[map](qabstractvideobuffer.html#map)（）函数返回一个指针，指向包含在视频缓冲器中的内容的记忆。通过返回的内存[map](qabstractvideobuffer.html#map)（ ）被释放通过调用[unmap](qabstractvideobuffer.html#unmap)（）函数。

该[handle](qabstractvideobuffer.html#handle)的缓冲液（）也可以被用来操纵它的使用类型特定的API含量。的缓冲器的句柄类型是由给定的[handleType](qabstractvideobuffer.html#handleType)（）函数。

* * *

## Type Documentation

```
QAbstractVideoBuffer.HandleType
```

确定了视频缓冲器处理的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractVideoBuffer.NoHandle` | `0` | 该缓冲液具有无手柄，它的数据只能通过映射缓冲存取。 |
| `QAbstractVideoBuffer.GLTextureHandle` | `1` | 缓冲区的句柄是一个OpenGL纹理的ID 。 |
| `QAbstractVideoBuffer.XvShmImageHandle` | `2` | 手柄中包含指向共享内存的XVideo形象。 |
| `QAbstractVideoBuffer.CoreImageHandle` | `3` | 手柄包含指针到Mac OS X CIImage 。 |
| `QAbstractVideoBuffer.QPixmapHandle` | `4` | 缓冲区的把手是[QPixmap](qpixmap.html)。 |
| `QAbstractVideoBuffer.UserHandle` | `1000` | 用户定义句柄类型起始值。 |

**See also** [handleType](qabstractvideobuffer.html#handleType)（ ） 。

```
QAbstractVideoBuffer.MapMode
```

列举了视频缓冲器的数据是如何映射到内存。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractVideoBuffer.NotMapped` | `0x00` | 视频缓冲区没有映射到内存。 |
| `QAbstractVideoBuffer.ReadOnly` | `0x01` | 映射的内存中填充了从视频缓冲区中的数据映射时，但映射的内存的内容可能会被丢弃时映射。 |
| `QAbstractVideoBuffer.WriteOnly` | `0x02` | 所映射的存储器是未初始化的映射时，内容将被用于映射时填充视频缓冲器。 |
| `QAbstractVideoBuffer.ReadWrite` | `ReadOnly &#124; WriteOnly` | 所映射的存储器中填充了从视频缓冲器中的数据，和视频缓冲器被重新填充与映射的存储器的内容。 |

**See also** [mapMode](qabstractvideobuffer.html#mapMode)（）和[map](qabstractvideobuffer.html#map)（ ） 。

* * *

## Method Documentation

```
QAbstractVideoBuffer.__init__ (self, HandleType type)
```

构造给定一个抽象的视频缓冲器_type_。

```
QVariant QAbstractVideoBuffer.handle (self)
```

返回一个类型的具体处理到数据缓冲区。

手柄的类型由下式给出[handleType](qabstractvideobuffer.html#handleType)（）函数。

**See also** [handleType](qabstractvideobuffer.html#handleType)（ ） 。

```
HandleType QAbstractVideoBuffer.handleType (self)
```

[

传回的视频缓冲区的句柄类型。

](qabstractvideobuffer.html#HandleType-enum)

[**See also**](qabstractvideobuffer.html#HandleType-enum) [handle](qabstractvideobuffer.html#handle)（ ） 。

```
(sip.voidptr, int numBytes, int bytesPerLine) QAbstractVideoBuffer.map (self, MapMode mode)
```

这种方法是抽象的，应在任何子类中重新实现。

映射一个视频缓冲器的内容传送到存储器中。

地图_mode_指示是否映射存储器中的内容应被读出和/或写入到缓冲区。如果映射模式包括[QAbstractVideoBuffer.ReadOnly](qabstractvideobuffer.html#MapMode-enum)标志映射的内存将被填入视频缓冲区的内容映射时。如果映射模式包括[QAbstractVideoBuffer.WriteOnly](qabstractvideobuffer.html#MapMode-enum)映射的内存的标志内容将被保存在缓冲区中，当未映射。

当访问数据不再需要，一定要调用[unmap](qabstractvideobuffer.html#unmap)（ ）函数释放映射内存。

返回一个指针映射内存区域，或一个空指针，如果映射失败。在映射内存区域的字节大小的返回_numBytes_和线步幅在_bytesPerLine_。

当访问数据不再需要，一定要[unmap](qabstractvideobuffer.html#unmap)（）的缓冲液中。

**Note:**记录到被映射为只读存储器是不确定的，并且可能导致改变的共享数据。

**See also** [unmap](qabstractvideobuffer.html#unmap)（）和[mapMode](qabstractvideobuffer.html#mapMode)（ ） 。

```
MapMode QAbstractVideoBuffer.mapMode (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回视频缓冲器被映射英寸的模式

](qabstractvideobuffer.html#MapMode-enum)

[**See also**](qabstractvideobuffer.html#MapMode-enum) [map](qabstractvideobuffer.html#map)（ ） 。

```
QAbstractVideoBuffer.unmap (self)
```

这种方法是抽象的，应在任何子类中重新实现。

发布映射的内存[map](qabstractvideobuffer.html#map)（ ）函数

如果[MapMode](qabstractvideobuffer.html#MapMode-enum)包括[QAbstractVideoBuffer.WriteOnly](qabstractvideobuffer.html#MapMode-enum)标志，这将持续映射内存的当前内容到视频帧。

**See also** [map](qabstractvideobuffer.html#map)（ ） 。