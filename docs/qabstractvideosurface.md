# QAbstractVideoSurface Class Reference

## [[QtMultimedia](index.htm) module]

该QAbstractVideoSurface类是视频演示表面的基类。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum Error { NoError, UnsupportedFormatError, IncorrectFormatError, StoppedError, ResourceError }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `Error error (self)`
*   `bool isActive (self)`
*   `bool isFormatSupported (self, QVideoSurfaceFormat format)`
*   `QVideoSurfaceFormat nearestFormat (self, QVideoSurfaceFormat format)`
*   `bool present (self, QVideoFrame frame)`
*   `setError (self, Error error)`
*   `bool start (self, QVideoSurfaceFormat format)`
*   `stop (self)`
*   `list-of-QVideoFrame.PixelFormat supportedPixelFormats (self, QAbstractVideoBuffer.HandleType type = QAbstractVideoBuffer.NoHandle)`
*   `QVideoSurfaceFormat surfaceFormat (self)`

### Qt Signals

*   `void activeChanged (bool)`
*   `void supportedFormatsChanged ()`
*   `void surfaceFormatChanged (const QVideoSurfaceFormat&)`

* * *

## Detailed Description

该QAbstractVideoSurface类是视频演示表面的基类。

该QAbstractVideoSurface类定义了视频制作者用它来与视频演示表面互操作的标准接口。它不应该被直接实例化。相反，你应该继承它来创建新的视频表面。

一种视频表面呈现格式相同的帧，其中每个帧的格式与开始演示时供给的流格式兼容的连续流。

像素的列表格式的表面可呈现由给定[supportedPixelFormats](qabstractvideosurface.html#supportedPixelFormats)（）函数，并且[isFormatSupported](qabstractvideosurface.html#isFormatSupported)（）函数将测试是否受支持的视频格式表面。如果不支持的格式[nearestFormat](qabstractvideosurface.html#nearestFormat)（）函数可能能够提供一个类似的格式。例如，如果一个表面上支持固定的分辨率可能暗示包含提呈之决议案的最小支持的分辨率。

该[start](qabstractvideosurface.html#start)（ ）函数接受一个支持的格式，使视频的表面。一旦开始了表面会开始显示它接收的帧[present](qabstractvideosurface.html#present)（）函数。表面可持有，直到一个新的框架，提出或流停止时的参考，提出了视频帧的缓冲区。该[stop](qabstractvideosurface.html#stop)（ ）函数将禁用表面和发布任何视频缓冲其持有的引用。

* * *

## Type Documentation

```
QAbstractVideoSurface.Error
```

该枚举描述了可以通过返回的错误[error](qabstractvideosurface.html#error)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractVideoSurface.NoError` | `0` | 未发生错误。 |
| `QAbstractVideoSurface.UnsupportedFormatError` | `1` | 不支持的视频格式。 |
| `QAbstractVideoSurface.IncorrectFormatError` | `2` | 一个视频帧是不与该表面的格式不兼容。 |
| `QAbstractVideoSurface.StoppedError` | `3` | 表面尚未启动。 |
| `QAbstractVideoSurface.ResourceError` | `4` | 表面无法分配一些资源。 |

* * *

## Method Documentation

```
QAbstractVideoSurface.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个视频面与给定_parent_。

```
Error QAbstractVideoSurface.error (self)
```

[

返回所发生的最后一个错误。

](qabstractvideosurface.html#Error-enum)

[如果表面不](qabstractvideosurface.html#Error-enum)[start](qabstractvideosurface.html#start)（ ） ，或意外停止此功能可以被调用来发现什么错误发生。

**See also** [setError](qabstractvideosurface.html#setError)（ ） 。

```
bool QAbstractVideoSurface.isActive (self)
```

表示视频表面是否已经启动。

返回True如果表面已经启动，否则返回False 。

```
bool QAbstractVideoSurface.isFormatSupported (self, QVideoSurfaceFormat format)
```

测试一个视频面_format_以确定是否一个面都能接受。

如果格式是由表面支撑，否则为False ，则返回True 。

```
QVideoSurfaceFormat QAbstractVideoSurface.nearestFormat (self, QVideoSurfaceFormat format)
```

[

返回一个支持的视频格式的表面，类似于_format_。

](qvideosurfaceformat.html)

[类似的表面格式是一个具有相同](qvideosurfaceformat.html)[pixel format](qvideosurfaceformat.html#pixelFormat)和[handle type](qvideosurfaceformat.html#handleType)但在其他一些特性是不同的。例如，如果有就限制[frame sizes](qvideosurfaceformat.html#frameSize)视频表面可以接受它可能意味着一种格式具有较大的帧大小和[viewport](qvideosurfaceformat.html#viewport)原始帧尺寸的大小。

如果已支持的格式也将原样返回，或如果没有类似支持的格式无效的格式将被退回。

```
bool QAbstractVideoSurface.present (self, QVideoFrame frame)
```

这种方法是抽象的，应在任何子类中重新实现。

提出了一个视频_frame_。

返回True如果在发生错误的帧被提出，并假的。

不是所有的表面将被阻塞，直到一个帧的显示已经完成。如果调用前一帧的呈现完成之前无阻塞表面上调用存在（ ）可能会失败。在这种情况下，直到它有机会处理事件的表面可能不会返回到就绪状态。

如果存在（ ）失败因任何其他原因，表面会立即进入停止状态和[error](qabstractvideosurface.html#error)（ ）值将被设置。

视频表面必须处于启动状态的存在（ ）成功，和视频帧的格式必须与当前的视频表面格式兼容。

**See also** [error](qabstractvideosurface.html#error)（ ） 。

```
QAbstractVideoSurface.setError (self, Error error)
```

设置的值[error](qabstractvideosurface.html#error)（）来_error_。

**See also** [error](qabstractvideosurface.html#error)（ ） 。

```
bool QAbstractVideoSurface.start (self, QVideoSurfaceFormat format)
```

开始视频表面呈现_format_帧。

如果表面已经开始，并且假，如果发生错误，则返回True 。

**See also** [isActive](qabstractvideosurface.html#isActive)（）和[stop](qabstractvideosurface.html#stop)（ ） 。

```
QAbstractVideoSurface.stop (self)
```

停止视频表面呈现帧并释放所收购的任何资源[start](qabstractvideosurface.html#start)（ ） 。

**See also** [isActive](qabstractvideosurface.html#isActive)（）和[start](qabstractvideosurface.html#start)（ ） 。

```
list-of-QVideoFrame.PixelFormat QAbstractVideoSurface.supportedPixelFormats (self, QAbstractVideoBuffer.HandleType type = QAbstractVideoBuffer.NoHandle)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的像素格式的视频表面可呈现为一个给定的句柄列表_type_。

像素格式返回的[QAbstractVideoBuffer.NoHandle](qabstractvideobuffer.html#HandleType-enum)类型是有效的，可以映射到只读模式的任何缓冲区。

这是第一个在列表中的类型可以被假定为更快的渲染。

```
QVideoSurfaceFormat QAbstractVideoSurface.surfaceFormat (self)
```

[

返回视频表面的格式。

* * *

## Qt Signal Documentation

```
void activeChanged (bool)
```

这是该信号的默认超载。

信号的_active_视频表面状态发生了变化。

](qvideosurfaceformat.html)

[**See also**](qvideosurfaceformat.html) [isActive](qabstractvideosurface.html#isActive)（ ）[start](qabstractvideosurface.html#start)（）和[stop](qabstractvideosurface.html#stop)（ ） 。

```
void supportedFormatsChanged ()
```

这是该信号的默认超载。

该组由视频表面支持的格式发生了变化的信号。

**See also** [supportedPixelFormats](qabstractvideosurface.html#supportedPixelFormats)（）和[isFormatSupported](qabstractvideosurface.html#isFormatSupported)（ ） 。

```
void surfaceFormatChanged (const QVideoSurfaceFormat&)
```

这是该信号的默认超载。

所配置的信号_format_的一个视频表面发生了变化。

**See also** [surfaceFormat](qabstractvideosurface.html#surfaceFormat)（）和[start](qabstractvideosurface.html#start)（ ） 。