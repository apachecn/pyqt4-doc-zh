# QVideoSurfaceFormat Class Reference

## [[QtMultimedia](index.htm) module]

该QVideoSurfaceFormat类指定视频演示表面的流格式。[More...](#details)

### Types

*   `enum Direction { TopToBottom, BottomToTop }`
*   `enum YCbCrColorSpace { YCbCr_Undefined, YCbCr_BT601, YCbCr_BT709, YCbCr_xvYCC601, YCbCr_xvYCC709, YCbCr_JPEG }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSize size, QVideoFrame.PixelFormat format, QAbstractVideoBuffer.HandleType type = QAbstractVideoBuffer.NoHandle)`
*   `__init__ (self, QVideoSurfaceFormat format)`
*   `int frameHeight (self)`
*   `float frameRate (self)`
*   `QSize frameSize (self)`
*   `int frameWidth (self)`
*   `QAbstractVideoBuffer.HandleType handleType (self)`
*   `bool isValid (self)`
*   `QSize pixelAspectRatio (self)`
*   `QVideoFrame.PixelFormat pixelFormat (self)`
*   `QVariant property (self, str name)`
*   `list-of-QByteArray propertyNames (self)`
*   `Direction scanLineDirection (self)`
*   `setFrameRate (self, float rate)`
*   `setFrameSize (self, QSize size)`
*   `setFrameSize (self, int width, int height)`
*   `setPixelAspectRatio (self, QSize ratio)`
*   `setPixelAspectRatio (self, int width, int height)`
*   `setProperty (self, str name, QVariant value)`
*   `setScanLineDirection (self, Direction direction)`
*   `setViewport (self, QRect viewport)`
*   `setYCbCrColorSpace (self, YCbCrColorSpace colorSpace)`
*   `QSize sizeHint (self)`
*   `QRect viewport (self)`
*   `YCbCrColorSpace yCbCrColorSpace (self)`

### Special Methods

*   `bool __eq__ (self, QVideoSurfaceFormat format)`
*   `bool __ne__ (self, QVideoSurfaceFormat format)`

* * *

## Detailed Description

该QVideoSurfaceFormat类指定视频演示表面的流格式。

视频表面呈现的视频帧流。表面的形式描述了帧的类型，并确定应如何呈现。

需要设置一个视频表面上的视频信息流的核心属性是由给定的像素格式[pixelFormat](qvideosurfaceformat.html#pixelFormat)（ ） ，并给出了框架尺寸[frameSize](qvideosurfaceformat.html#frameSize)（ ） 。

如果表面是用一帧的把手表面的格式呈现的帧也将包括由给定的一个句柄类型[handleType](qvideosurfaceformat.html#handleType)（）函数。

实际上是显示在视频面一帧的区域是通过在给定[viewport](qvideosurfaceformat.html#viewport)（ ） 。甲流可具有视口比一帧的整个区域减去，以允许视频比视频帧的最接近的最佳尺寸。例如一帧的宽度可以延伸，使得每个扫描行的开始是8字节对齐的。

其他常见的属性是[pixelAspectRatio](qvideosurfaceformat.html#pixelAspectRatio)（ ）[scanLineDirection](qvideosurfaceformat.html#scanLineDirection)（）和[frameRate](qvideosurfaceformat.html#frameRate)（ ） 。另外一个数据流可以具有所列的dynamicPropertyNames一些额外类型的特定属性（）函数，并且可以使用被访问的[property](qvideosurfaceformat.html#property)（）和[setProperty](qvideosurfaceformat.html#setProperty)（）函数。

* * *

## Type Documentation

```
QVideoSurfaceFormat.Direction
```

列举的视频扫描线的布局方向。

| Constant | Value | Description |
| --- | --- | --- |
| `QVideoSurfaceFormat.TopToBottom` | `0` | 扫描线被布置在框架的顶部向底部。 |
| `QVideoSurfaceFormat.BottomToTop` | `1` | 扫描线被布置在框架的底部到顶部。 |

```
QVideoSurfaceFormat.YCbCrColorSpace
```

列举了视频帧的Y'CbCr的色彩空间。

| Constant | Value | Description |
| --- | --- | --- |
| `QVideoSurfaceFormat.YCbCr_Undefined` | `0` | 未指定的色彩空间。 |
| `QVideoSurfaceFormat.YCbCr_BT601` | `1` | 由ITU -R BT.601建议与Y值的范围从16到235 ，和CB / CR范围从16到240定义的Y'CbCr的色彩空间。用于标准清晰度视频。 |
| `QVideoSurfaceFormat.YCbCr_BT709` | `2` | 由ITU- R BT.709具有相同的值定义的Y'CbCr的色彩空间范围内YCbCr_BT601 。用于高清晰度电视。 |
| `QVideoSurfaceFormat.YCbCr_xvYCC601` | `3` | 同的数值范围的BT.601颜色空间扩大到0 〜255。它是落后的。兼容与BT.601和使用外BT.601范围值来表示更广泛的色彩范围。 |
| `QVideoSurfaceFormat.YCbCr_xvYCC709` | `4` | 同的数值范围的BT.709颜色空间扩大到0 〜255。 |
| `QVideoSurfaceFormat.YCbCr_JPEG` | `5` | 在JPEG文件中使用的全范围Y'CbCr的色彩空间。 |

* * *

## Method Documentation

```
QVideoSurfaceFormat.__init__ (self)
```

构造一个空的视频流格式。

```
QVideoSurfaceFormat.__init__ (self, QSize size, QVideoFrame.PixelFormat format, QAbstractVideoBuffer.HandleType type = QAbstractVideoBuffer.NoHandle)
```

Contructs流的描述，它接收的数据流_type_缓冲区与给定的框架_size_和像素_format_。

```
QVideoSurfaceFormat.__init__ (self, QVideoSurfaceFormat format)
```

构造的副本_other_。

```
int QVideoSurfaceFormat.frameHeight (self)
```

返回帧中的视频流的高度。

```
float QVideoSurfaceFormat.frameRate (self)
```

返回以每秒帧数的视频流的帧速率。

**See also** [setFrameRate](qvideosurfaceformat.html#setFrameRate)（ ） 。

```
QSize QVideoSurfaceFormat.frameSize (self)
```

[

返回视频流中的帧的大小。

](qsize.html)

[**See also**](qsize.html) [setFrameSize](qvideosurfaceformat.html#setFrameSize)（ ）[frameWidth](qvideosurfaceformat.html#frameWidth)（）和[frameHeight](qvideosurfaceformat.html#frameHeight)（ ） 。

```
int QVideoSurfaceFormat.frameWidth (self)
```

返回视频流中帧的宽度。

**See also** [frameSize](qvideosurfaceformat.html#frameSize)（）和[frameHeight](qvideosurfaceformat.html#frameHeight)（ ） 。

```
QAbstractVideoBuffer.HandleType QVideoSurfaceFormat.handleType (self)
```

[

返回表面采用提呈本帧数据处理的类型。

](qabstractvideobuffer.html#HandleType-enum)

[如果句柄类型是](qabstractvideobuffer.html#HandleType-enum)[QAbstractVideoBuffer.NoHandle](qabstractvideobuffer.html#HandleType-enum)缓冲区与任何句柄类型是有效的，只要它们能[mapped](qabstractvideobuffer.html#map)与[QAbstractVideoBuffer.ReadOnly](qabstractvideobuffer.html#MapMode-enum)标志。如果handleType （）不是[QAbstractVideoBuffer.NoHandle](qabstractvideobuffer.html#HandleType-enum)然后缓冲区的句柄类型是相同的，该表面的格式。

```
bool QVideoSurfaceFormat.isValid (self)
```

如果识别的视频格式，表面具有有效像素格式和帧大小。

返回True如果该格式是有效的，否则为False。

```
QSize QVideoSurfaceFormat.pixelAspectRatio (self)
```

[

返回视频流的像素宽高比。

](qsize.html)

[**See also**](qsize.html) [setPixelAspectRatio](qvideosurfaceformat.html#setPixelAspectRatio)（ ） 。

```
QVideoFrame.PixelFormat QVideoSurfaceFormat.pixelFormat (self)
```

[

返回视频流中的帧的像素格式。

```
QVariant QVideoSurfaceFormat.property (self, str name)
```

传回的视频格式的值_name_属性。

](qvideoframe.html#PixelFormat-enum)

[**See also**](qvideoframe.html#PixelFormat-enum) [setProperty](qvideosurfaceformat.html#setProperty)（ ） 。

```
list-of-QByteArray QVideoSurfaceFormat.propertyNames (self)
```

传回的视频格式动态属性名称的列表。

```
Direction QVideoSurfaceFormat.scanLineDirection (self)
```

[

返回扫描线的方向。

](qvideosurfaceformat.html#Direction-enum)

[**See also**](qvideosurfaceformat.html#Direction-enum) [setScanLineDirection](qvideosurfaceformat.html#setScanLineDirection)（ ） 。

```
QVideoSurfaceFormat.setFrameRate (self, float rate)
```

设置框架_rate_在帧每秒的视频流。

**See also** [frameRate](qvideosurfaceformat.html#frameRate)（ ） 。

```
QVideoSurfaceFormat.setFrameSize (self, QSize size)
```

设置帧的大小在视频流中，以_size_。

这将重置[viewport](qvideosurfaceformat.html#viewport)（）来填满整个画面。

**See also** [frameSize](qvideosurfaceformat.html#frameSize)（ ） 。

```
QVideoSurfaceFormat.setFrameSize (self, int width, int height)
```

这是一个重载函数。

设置_width_和_height_的帧中的视频流。

这将重置[viewport](qvideosurfaceformat.html#viewport)（）来填满整个画面。

```
QVideoSurfaceFormat.setPixelAspectRatio (self, QSize ratio)
```

设置一个视频流的像素宽高比_ratio_。

**See also** [pixelAspectRatio](qvideosurfaceformat.html#pixelAspectRatio)（ ） 。

```
QVideoSurfaceFormat.setPixelAspectRatio (self, int width, int height)
```

这是一个重载函数。

设置_horizontal_和_vertical_的视频流的像素宽高比的元素。

```
QVideoSurfaceFormat.setProperty (self, str name, QVariant value)
```

设置视频格式的_name_属性为_value_。

**See also** [property](qvideosurfaceformat.html#property)（ ） 。

```
QVideoSurfaceFormat.setScanLineDirection (self, Direction direction)
```

设置_direction_的扫描线。

**See also** [scanLineDirection](qvideosurfaceformat.html#scanLineDirection)（ ） 。

```
QVideoSurfaceFormat.setViewport (self, QRect viewport)
```

设置一个视频流的视口_viewport_。

**See also** [viewport](qvideosurfaceformat.html#viewport)（ ） 。

```
QVideoSurfaceFormat.setYCbCrColorSpace (self, YCbCrColorSpace colorSpace)
```

设置Y'CbCr的颜色_space_的视频流。它仅用于与原始YUV帧类型。

**See also** [yCbCrColorSpace](qvideosurfaceformat.html#yCbCrColorSpace)（ ） 。

```
QSize QVideoSurfaceFormat.sizeHint (self)
```

[

返回视频流像素的建议的大小。

这是根据该像素纵横比缩放的视口的大小。

](qsize.html)

```
QRect QVideoSurfaceFormat.viewport (self)
```

[

返回视频流的视口。

视口是实际显示一个视频帧的区域。

默认情况下，视口复盖整个帧。

](qrect.html)

[**See also**](qrect.html) [setViewport](qvideosurfaceformat.html#setViewport)（ ） 。

```
YCbCrColorSpace QVideoSurfaceFormat.yCbCrColorSpace (self)
```

[

返回视频流的Y'CbCr的色彩空间。

](qvideosurfaceformat.html#YCbCrColorSpace-enum)

[**See also**](qvideosurfaceformat.html#YCbCrColorSpace-enum) [setYCbCrColorSpace](qvideosurfaceformat.html#setYCbCrColorSpace)（ ） 。

```
bool QVideoSurfaceFormat.__eq__ (self, QVideoSurfaceFormat format)
```

```
bool QVideoSurfaceFormat.__ne__ (self, QVideoSurfaceFormat format)
```