# QGL Class Reference

## [[QtOpenGL](index.htm) module]

该QGL命名空间指定了Qt的OpenGL模块中使用的其他标识符。[More...](#details)

### Types

*   `enum FormatOption { DoubleBuffer, DepthBuffer, Rgba, AlphaChannel, ..., NoDeprecatedFunctions }`
*   `class **[FormatOptions](index.htm)**`

### Static Methods

*   `setPreferredPaintEngine (QPaintEngine.Type engineType)`

* * *

## Detailed Description

该QGL命名空间指定了Qt的OpenGL模块中使用的其他标识符。

* * *

## Type Documentation

```
QGL.FormatOption
```

此枚举指定可用于配置OpenGL上下文的格式选项。这些是使用设置[QGLFormat.setOption](qglformat.html#setOption)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QGL.DoubleBuffer` | `0x0001` | 指定使用双缓冲的。 |
| `QGL.DepthBuffer` | `0x0002` | 允许使用深度缓冲的。 |
| `QGL.Rgba` | `0x0004` | 指定的上下文中应该使用的RGBA作为其像素格式。 |
| `QGL.AlphaChannel` | `0x0008` | 允许使用alpha通道的。 |
| `QGL.AccumBuffer` | `0x0010` | 允许使用的累加缓冲器。 |
| `QGL.StencilBuffer` | `0x0020` | 允许使用模板缓冲区。 |
| `QGL.StereoBuffers` | `0x0040` | 支持使用立体声缓冲器具有可视化的硬件使用。 |
| `QGL.DirectRendering` | `0x0080` | 指定上下文被用于直接渲染到显示器。 |
| `QGL.HasOverlay` | `0x0100` | 允许使用重叠的。 |
| `QGL.SampleBuffers` | `0x0200` | 允许使用样本缓冲区。 |
| `QGL.DeprecatedFunctions` | `0x0400` | 允许使用过时的功能为OpenGL 3.x的上下文。启用了弃用功能的上下文被称为OpenGL规范一个完整的上下文。 |
| `QGL.SingleBuffer` | `DoubleBuffer&lt;&lt;16` | 指定使用一个单一的缓冲液中，相对于双缓冲器。 |
| `QGL.NoDepthBuffer` | `DepthBuffer&lt;&lt;16` | 禁止使用深度缓冲的。 |
| `QGL.ColorIndex` | `Rgba&lt;&lt;16` | 指定的上下文中应该使用的颜色索引作为其像素格式。 |
| `QGL.NoAlphaChannel` | `AlphaChannel&lt;&lt;16` | 禁止使用Alpha通道。 |
| `QGL.NoAccumBuffer` | `AccumBuffer&lt;&lt;16` | 禁止使用积累的缓冲区。 |
| `QGL.NoStencilBuffer` | `StencilBuffer&lt;&lt;16` | 禁止使用模板缓冲区。 |
| `QGL.NoStereoBuffers` | `StereoBuffers&lt;&lt;16` | 禁止使用立体声缓冲区。 |
| `QGL.IndirectRendering` | `DirectRendering&lt;&lt;16` | 指定该上下文被用于间接渲染到一个缓冲区中。 |
| `QGL.NoOverlay` | `HasOverlay&lt;&lt;16` | 禁止使用重叠的。 |
| `QGL.NoSampleBuffers` | `SampleBuffers&lt;&lt;16` | 禁止使用样本缓冲区。 |
| `QGL.NoDeprecatedFunctions` | `DeprecatedFunctions&lt;&lt;16` | 禁止使用过时的功能为OpenGL 3.x的上下文。禁用过时的功能的情况下被调用OpenGL规范向前兼容的上下文。 |

该FormatOptions类型是一个typedef为[QFlags](index.htm)\u003cFormatOption\u003e 。它存储FormatOption值的或组合。

**See also** [Sample Buffers Example](index.htm)。

* * *

## Method Documentation

```
QGL.setPreferredPaintEngine (QPaintEngine.Type engineType)
```

设置用于绘制到首选的OpenGL绘图引擎[QGLWidget](qglwidget.html)，[QGLPixelBuffer](qglpixelbuffer.html)和[QGLFramebufferObject](qglframebufferobject.html)与目标[QPainter](qpainter.html)Qt中。

该_engineType_参数指定了GL的发动机使用的。只`QPaintEngine.OpenGL`和`QPaintEngine.OpenGL2`是有效的参数传递给该函数。所有其他值将被忽略。

默认情况下，`QPaintEngine.OpenGL2`引擎时使用GL / GLES 2.0版是可用的，否则`QPaintEngine.OpenGL`被使用。

**Warning:**此功能之前，必须调用[QApplication](qapplication.html)构造函数被调用。

此功能被引入Qt的4.6 。