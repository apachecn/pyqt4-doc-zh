# QGLFramebufferObject Class Reference

## [[QtOpenGL](index.htm) module]

该QGLFramebufferObject类封装了一个OpenGL帧缓冲区对象。[More...](#details)

继承[QPaintDevice](qpaintdevice.html)。

### Types

*   `enum Attachment { NoAttachment, CombinedDepthStencil, Depth }`

### Methods

*   `__init__ (self, QSize size, int target = GL_TEXTURE_2D)`
*   `__init__ (self, int width, int height, int target = GL_TEXTURE_2D)`
*   `__init__ (self, QSize size, Attachment attachment, int target = GL_TEXTURE_2D, int internalFormat = GL_RGBA8)`
*   `__init__ (self, int width, int height, Attachment attachment, int target = GL_TEXTURE_2D, int internalFormat = GL_RGBA8)`
*   `__init__ (self, QSize size, QGLFramebufferObjectFormat format)`
*   `__init__ (self, int width, int height, QGLFramebufferObjectFormat format)`
*   `Attachment attachment (self)`
*   `bool bind (self)`
*   `drawTexture (self, QRectF target, int textureId, int textureTarget = GL_TEXTURE_2D)`
*   `drawTexture (self, QPointF point, int textureId, int textureTarget = GL_TEXTURE_2D)`
*   `QGLFramebufferObjectFormat format (self)`
*   `int handle (self)`
*   `bool isBound (self)`
*   `bool isValid (self)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric metric)`
*   `QPaintEngine paintEngine (self)`
*   `bool release (self)`
*   `QSize size (self)`
*   `int texture (self)`
*   `QImage toImage (self)`

### Static Methods

*   `blitFramebuffer (QGLFramebufferObject target, QRect targetRect, QGLFramebufferObject source, QRect sourceRect, int buffers = GL_COLOR_BUFFER_BIT, int filter = GL_NEAREST)`
*   `bool hasOpenGLFramebufferBlit ()`
*   `bool hasOpenGLFramebufferObjects ()`

* * *

## Detailed Description

该QGLFramebufferObject类封装了一个OpenGL帧缓冲区对象。

该QGLFramebufferObject类封装了一个OpenGL帧缓冲区对象，由定义`GL_EXT_framebuffer_object`扩展名。此外，它提供了一种渲染表面，可以涂在用[QPainter](qpainter.html)，呈现给使用本地GL调用，或两者兼而有之。这种表面可以在自己的GL绘图代码的约束，并作为一个普通的纹理。默认情况下， QGLFramebufferObject类生成一个2D GL纹理（使用`GL_TEXTURE_2D`目标） ，它是用来作为内部渲染对象。

**It is important to have a current GL context when creating a QGLFramebufferObject, otherwise initialization will fail.**

OpenGL的帧缓冲对象和pbuffers的（见[QGLPixelBuffer](qglpixelbuffer.html)）都可以用来渲染到屏幕外表面，但也有许多与使用帧缓冲区对象而不是pbuffers的优点：

1.  一个帧缓冲对象不需要一个单独的渲染上下文，因此切换渲染目标时不会发生上下文切换。存在参与切换目标的开销，但一般它比上下文切换到一个pbuffer的便宜。
2.  渲染到动态纹理（即渲染到纹理功能）适用于所有平台。没有必要做明确的副本从一个渲染缓冲区调用到一个纹理，因为有必要对那些不支持系统`render_texture`扩展名。
3.  它可以连接多个渲染缓冲区（或纹理对象）到相同的帧缓冲区对象，并呈现给所有的人都没有做上下文切换。
4.  OpenGL的帧缓冲扩展是一个纯粹的GL扩展，不依赖于系统WGL ，鳄鱼卹，或GLX部分。这使得使用帧缓冲对象更便于携带。

当使用一个[QPainter](qpainter.html)画一个QGLFramebufferObject的QGLFramebufferObject与创建时要注意[CombinedDepthStencil](qglframebufferobject.html#Attachment-enum)附件[QPainter](qpainter.html)要能正确呈现。请注意，您需要使用绘图时创建每像素多于一个样本的QGLFramebufferObject对原语进行反锯齿[QPainter](qpainter.html)。要创建一个多重采样帧缓冲区对象，你应该使用采取QGLFramebufferObject参数的构造函数之一，并设置QGLFramebufferObject.samples （）属性设置为一个非零值。

当画到QGLFramebufferObject使用[QPainter](qpainter.html)，目前GL上下文的状态将由绘图引擎进行修改，以反映其需求。应用程序不应依赖于GL状态被重置到其原始条件，特别是目前的着色器程序，吉尔口中，纹理单元和绘图模式。

对于多重采样帧缓冲对象的颜色渲染在创建缓冲区，否则创建具有指定目标的质感纹理。色彩渲染缓冲器或纹理将具有指定的内部格式，并且将被绑定到`GL_COLOR_ATTACHMENT0`附件中的帧缓冲区对象。

如果你想使用一个帧缓冲对象启用多重采样作为纹理，你首先需要从它复制到使用QGLContext.blitFramebuffer （ ）一个普通帧缓冲区对象。

### Threading

由于Qt的4.8的，有可能用来绘制成QGLFramebufferObject一个[QPainter](qpainter.html)在一个单独的线程。需要注意的是OpenGL的2.0或OpenGL ES 2.0的是需要这种合作。此外， X11下，有必要设置[Qt.AA_X11InitThreads](qt.html#ApplicationAttribute-enum)应用属性。

* * *

## Type Documentation

```
QGLFramebufferObject.Attachment
```

该枚举类型是用来配置连接到帧缓冲对象被创建时，它的深度和模板缓冲区。

| Constant | Value | Description |
| --- | --- | --- |
| `QGLFramebufferObject.NoAttachment` | `0` | 没有附件被添加到帧缓冲区对象。需要注意的是渲染到帧缓冲区对象，没有任何深度或模板缓冲区时， OpenGL的深度和模板测试将无法正常工作。这是默认值。 |
| `QGLFramebufferObject.CombinedDepthStencil` | `1` | 如果`GL_EXT_packed_depth_stencil`扩展目前，结合深度和模板缓存连接。如果扩展名不存在，只有深度缓冲区连接。 |
| `QGLFramebufferObject.Depth` | `2` | 深度缓冲连接到帧缓冲区对象。 |

这个枚举被引入或修改的Qt 4.3 。

**See also** [attachment](qglframebufferobject.html#attachment)（ ） 。

* * *

## Method Documentation

```
QGLFramebufferObject.__init__ (self, QSize size, int target = GL_TEXTURE_2D)
```

构造一个OpenGL帧缓冲区对象和一个2D GL纹理结合到大小的缓冲_size_。纹理被绑定到`GL_COLOR_ATTACHMENT0`针对在帧缓冲对象。

该_target_参数用于指定总帐质感目标。默认的目标是`GL_TEXTURE_2D`。请记住，`GL_TEXTURE_2D`纹理必须有2宽度和高度（如256×512个）的功率，除非你正在使用的OpenGL 2.0或更高版本。

默认情况下，没有深度和模板缓冲区连接。这种行为可以使用重载的构造函数之一进行切换。

默认的内部纹理格式是`GL_RGBA8`对于桌面OpenGL ，和`GL_RGBA`为OpenGL / ES 。

你有一个当前的GL上下文创建时设置是很重要的[QGLFramebufferObject](qglframebufferobject.html)，否则初始化将失败。

**See also** [size](qglframebufferobject.html#size)（ ）[texture](qglframebufferobject.html#texture)（）和[attachment](qglframebufferobject.html#attachment)（ ） 。

```
QGLFramebufferObject.__init__ (self, int width, int height, int target = GL_TEXTURE_2D)
```

这是一个重载函数。

构造一个OpenGL帧缓冲区对象和GL 2D纹理绑定到给定缓冲区_width_和_height_。

**See also** [size](qglframebufferobject.html#size)（）和[texture](qglframebufferobject.html#texture)（ ） 。

```
QGLFramebufferObject.__init__ (self, QSize size, Attachment attachment, int target = GL_TEXTURE_2D, int internalFormat = GL_RGBA8)
```

这是一个重载函数。

构造给定一个OpenGL帧缓冲区对象_size_基于所提供的_format_。

```
QGLFramebufferObject.__init__ (self, int width, int height, Attachment attachment, int target = GL_TEXTURE_2D, int internalFormat = GL_RGBA8)
```

这是一个重载函数。

构造给定一个OpenGL帧缓冲区对象_width_和_height_基于所提供的_format_。

```
QGLFramebufferObject.__init__ (self, QSize size, QGLFramebufferObjectFormat format)
```

这是一个重载函数。

构造一个OpenGL帧缓冲区对象和纹理绑定到给定缓冲区_width_和_height_。

该_attachment_参数描述了深度/模板缓存配置，_target_纹理和目标_internal_format_内部纹理格式。默认质感的目标是`GL_TEXTURE_2D`，而默认的内部格式是`GL_RGBA8`桌面OpenGL和`GL_RGBA`为OpenGL / ES 。

**See also** [size](qglframebufferobject.html#size)（ ）[texture](qglframebufferobject.html#texture)（）和[attachment](qglframebufferobject.html#attachment)（ ） 。

```
QGLFramebufferObject.__init__ (self, int width, int height, QGLFramebufferObjectFormat format)
```

这是一个重载函数。

构造一个OpenGL帧缓冲区对象和纹理绑定到给定缓冲区_size_。

该_attachment_参数描述了深度/模板缓存配置，_target_纹理和目标_internal_format_内部纹理格式。默认质感的目标是`GL_TEXTURE_2D`，而默认的内部格式是`GL_RGBA8`桌面OpenGL和`GL_RGBA`为OpenGL / ES 。

**See also** [size](qglframebufferobject.html#size)（ ）[texture](qglframebufferobject.html#texture)（）和[attachment](qglframebufferobject.html#attachment)（ ） 。

```
Attachment QGLFramebufferObject.attachment (self)
```

[

返回附加到该帧缓冲区对象的深度和模具缓冲器的状态。

```
bool QGLFramebufferObject.bind (self)
```

从默认的开关渲染，窗口提供系统的framebuffer来此帧缓冲区对象。成功时返回真，否则返回False。

](qglframebufferobject.html#Attachment-enum)

[**See also**](qglframebufferobject.html#Attachment-enum) [release](qglframebufferobject.html#release)（ ） 。

```
QGLFramebufferObject.blitFramebuffer (QGLFramebufferObject target, QRect targetRect, QGLFramebufferObject source, QRect sourceRect, int buffers = GL_COLOR_BUFFER_BIT, int filter = GL_NEAREST)
```

从位块传输_sourceRect_矩形的_source_帧缓冲区对象的_targetRect_矩形的_target_帧缓冲区对象。

If _source_ or _target_是0 ，则默认帧缓冲区将被用于一个帧缓冲对象作为源或目标，而不是分别。

该_buffers_参数应该包括任何组合的掩模`GL_COLOR_BUFFER_BIT`，`GL_DEPTH_BUFFER_BIT`和`GL_STENCIL_BUFFER_BIT`。任何未在源和目标缓冲器呈现两个缓冲器类型被忽略。

该_sourceRect_和_targetRect_矩形可以有不同的大小，在这种情况_buffers_不应该包含`GL_DEPTH_BUFFER_BIT` or `GL_STENCIL_BUFFER_BIT`。该_filter_参数应该被设置为`GL_LINEAR` or `GL_NEAREST`以及指定是否线性的或最接近的内插时，执行缩放应该被使用。

If _source_等于_target_副本相同的缓冲区内进行。结果是不确定的，如果源和目标矩形重叠，并且具有不同的尺寸。的大小也必须相同，如果任何帧缓冲的对象是多重采样的帧缓冲区。

请注意，如果启用了剪刀测试将限制位块传输的区域。

此功能不会有任何影响，除非[hasOpenGLFramebufferBlit](qglframebufferobject.html#hasOpenGLFramebufferBlit)（ ）返回True 。

此功能被引入Qt的4.6 。

**See also** [hasOpenGLFramebufferBlit](qglframebufferobject.html#hasOpenGLFramebufferBlit)（ ） 。

```
QGLFramebufferObject.drawTexture (self, QRectF target, int textureId, int textureTarget = GL_TEXTURE_2D)
```

绘制给定的质感，_textureId_向给定目标矩形，_target_在OpenGL的模型空间。该_textureTarget_应该是一个2D纹理的目标。

帧缓冲对象应该调用这个函数时的约束。

等同于相应的[QGLContext.drawTexture](qglcontext.html#drawTexture)（ ） 。

此功能被引入Qt的4.4 。

```
QGLFramebufferObject.drawTexture (self, QPointF point, int textureId, int textureTarget = GL_TEXTURE_2D)
```

绘制给定的质感，_textureId_，在给定的_point_在OpenGL的模型空间。该_textureTarget_应该是一个2D纹理的目标。

帧缓冲对象应该调用这个函数时的约束。

等同于相应的[QGLContext.drawTexture](qglcontext.html#drawTexture)（ ） 。

此功能被引入Qt的4.4 。

```
QGLFramebufferObjectFormat QGLFramebufferObject.format (self)
```

[

返回此帧缓冲区对象的格式。

```
int QGLFramebufferObject.handle (self)
```

返回此帧缓冲区对象的GL帧缓冲对象句柄（由返回`glGenFrameBuffersEXT()`功能）。这个句柄可以被用来连接新的图像或缓冲区的帧缓冲。用户是负责清理和销毁这些对象。

```
bool QGLFramebufferObject.hasOpenGLFramebufferBlit ()
```

返回True如果OpenGL的`GL_EXT_framebuffer_blit`扩展出现在这个系统上，否则返回False 。

此功能被引入Qt的4.6 。

](qglframebufferobjectformat.html)

[**See also**](qglframebufferobjectformat.html) [blitFramebuffer](qglframebufferobject.html#blitFramebuffer)（ ） 。

```
bool QGLFramebufferObject.hasOpenGLFramebufferObjects ()
```

返回True如果OpenGL的`GL_EXT_framebuffer_object`扩展出现在这个系统上，否则返回False 。

```
bool QGLFramebufferObject.isBound (self)
```

如果帧缓冲区对象当前绑定到一个上下文，否则返回False ，则返回True 。

此功能被引入Qt的4.5 。

```
bool QGLFramebufferObject.isValid (self)
```

返回True如果帧缓冲对象是有效的。

如果初始化进程失败时，使用者将一个无效缓存到帧缓冲区对象，或者两种宽度/高度的非功率被指定为纹理大小，如果纹理是目标帧缓冲可以成为无效`GL_TEXTURE_2D`。两条限制非电力不适用，如果OpenGL版本为2.0或更高版本，或者如果GL_ARB_texture_non_power_of_two扩展存在。

帧缓冲也可以成为无效的，如果[QGLContext](qglcontext.html)该帧缓存创建内被破坏，并且没有其他共享的上下文，可以采取在帧缓冲区的所有权。

```
int QGLFramebufferObject.metric (self, QPaintDevice.PaintDeviceMetric metric)
```

从重新实现[QPaintDevice.metric](qpaintdevice.html#metric)（ ） 。

```
QPaintEngine QGLFramebufferObject.paintEngine (self)
```

[](qpaintengine.html)

[从重新实现](qpaintengine.html)[QPaintDevice.paintEngine](qpaintdevice.html#paintEngine)（ ） 。

```
bool QGLFramebufferObject.release (self)
```

切换渲染回默认的，窗口提供系统的framebuffer 。成功时返回真，否则返回False。

**See also** [bind](qglframebufferobject.html#bind)（ ） 。

```
QSize QGLFramebufferObject.size (self)
```

[

返回附加到该帧缓冲区对象的纹理的大小。

```
int QGLFramebufferObject.texture (self)
```

返回纹理ID为连接作为默认渲染目标在此帧缓冲区对象的质感。这种质地的id可以在自己的总帐代码绑定作为一个正常的质感。

如果一个多重采样帧缓冲区对象被使用，那么从这个函数返回的值将是无效的。

](qsize.html)

```
QImage QGLFramebufferObject.toImage (self)
```

[](qimage.html)

[返回此帧缓冲区对象的内容作为](qimage.html)[QImage](qimage.html)。