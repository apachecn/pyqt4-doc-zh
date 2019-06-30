# QGLContext Class Reference

## [[QtOpenGL](index.htm) module]

该QGLContext类封装了一个OpenGL渲染上下文。[More...](#details)

### Types

*   `enum BindOption { NoBindOption, InvertedYBindOption, MipmapBindOption, PremultipliedAlphaBindOption, LinearFilteringBindOption, DefaultBindOption }`
*   `class **[BindOptions](index.htm)**`

### Methods

*   `__init__ (self, QGLFormat format, QPaintDevice device)`
*   `int bindTexture (self, QImage image, int target = GL_TEXTURE_2D, int format = GL_RGBA)`
*   `int bindTexture (self, QPixmap pixmap, int target = GL_TEXTURE_2D, int format = GL_RGBA)`
*   `int bindTexture (self, QString fileName)`
*   `int bindTexture (self, QImage image, int target, int format, BindOptions options)`
*   `int bindTexture (self, QPixmap pixmap, int target, int format, BindOptions options)`
*   `bool chooseContext (self, QGLContext shareContext = None)`
*   `sip.voidptr chooseVisual (self)`
*   `bool create (self, QGLContext shareContext = None)`
*   `deleteTexture (self, int tx_id)`
*   `QPaintDevice device (self)`
*   `bool deviceIsPixmap (self)`
*   `doneCurrent (self)`
*   `drawTexture (self, QRectF target, int textureId, int textureTarget = GL_TEXTURE_2D)`
*   `drawTexture (self, QPointF point, int textureId, int textureTarget = GL_TEXTURE_2D)`
*   `QGLFormat format (self)`
*   `generateFontDisplayLists (self, QFont fnt, int listBase)`
*   `sip.voidptr getProcAddress (self, QString proc)`
*   `bool initialized (self)`
*   `bool isSharing (self)`
*   `bool isValid (self)`
*   `makeCurrent (self)`
*   `QColor overlayTransparentColor (self)`
*   `QGLFormat requestedFormat (self)`
*   `reset (self)`
*   `setFormat (self, QGLFormat format)`
*   `setInitialized (self, bool on)`
*   `setWindowCreated (self, bool on)`
*   `swapBuffers (self)`
*   `bool windowCreated (self)`

### Static Methods

*   `bool areSharing (QGLContext context1, QGLContext context2)`
*   `QGLContext currentContext ()`
*   `setTextureCacheLimit (int size)`
*   `int textureCacheLimit ()`

* * *

## Detailed Description

该QGLContext类封装了一个OpenGL渲染上下文。

一个OpenGL渲染上下文是一套完整的OpenGL状态变量。渲染上下文的[format](qgl.html#FormatOption-enum)被设置在构造，但它也可以购买与设置[setFormat](qglcontext.html#setFormat)（ ） 。这实际上是设置格式选项由返回[format](qglcontext.html#format)（）;你要的选项被退回[requestedFormat](qglcontext.html#requestedFormat)（ ） 。请注意，在一个QGLContext对象已建成，实际OpenGL上下文必须通过显式调用创建的[create()](qglcontext.html#create)功能。该[makeCurrent](qglcontext.html#makeCurrent)（）函数使得这方面的当前呈现上下文。您可以_no_使用上下文电流[doneCurrent](qglcontext.html#doneCurrent)（ ） 。该[reset](qglcontext.html#reset)（ ）函数将重置上下文，并使其无效。

你可以检查上下文的物业，如[isValid](qglcontext.html#isValid)（ ）[isSharing](qglcontext.html#isSharing)（ ）[initialized](qglcontext.html#initialized)（ ）[windowCreated](qglcontext.html#windowCreated)（）和[overlayTransparentColor](qglcontext.html#overlayTransparentColor)（ ） 。

如果你使用双缓冲可以使用换用离屏缓冲屏幕内容[swapBuffers](qglcontext.html#swapBuffers)（ ） 。

请注意， QGLContext是不[thread-safe](index.htm#thread-safe)。

* * *

## Type Documentation

```
QGLContext.BindOption
```

一组选项来决定如何使用绑定纹理[bindTexture](qglcontext.html#bindTexture)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QGLContext.NoBindOption` | `0x0000` | 不要做任何事情，直通传递的质感。 |
| `QGLContext.InvertedYBindOption` | `0x0001` | 指定纹理应该翻转X轴，以使纹理坐标0,0对应于左上角。反相纹理意味着一个深层副本之前上传。 |
| `QGLContext.MipmapBindOption` | `0x0002` | 指定[bindTexture](qglcontext.html#bindTexture)（ ）应该生成贴图。如果GL实现支持`GL_SGIS_generate_mipmap`扩展，贴图将自动为纹理生成。 MIP贴图一代只支持了`GL_TEXTURE_2D`目标。 |
| `QGLContext.PremultipliedAlphaBindOption` | `0x0004` | 指定图像应使用预乘alpha上传并做了相应的转换。 |
| `QGLContext.LinearFilteringBindOption` | `0x0008` | 指定纹理过滤应设置为GL_LINEAR 。默认值是GL_NEAREST 。如果MIP贴图也被启用，过滤将被设置为GL_LINEAR_MIPMAP_LINEAR 。 |
| `QGLContext.DefaultBindOption` | `LinearFilteringBindOption &#124; InvertedYBindOption &#124; MipmapBindOption` | 在Qt 4.5和更早的版本，[bindTexture](qglcontext.html#bindTexture)（ ）将镜像图像，并自动生成贴图。此选项可帮助保护这种默认行为。 |

通过使用从像素图X11选择它是否可以在像素映射绑定倒挂与否。

用于涂料引擎，表明像素图应该沿着边用像素图/图像进行内存管理，它从，如茎在他们破坏安装钩子。

这个枚举被引入或修改的Qt 4.6 。

该BINDOPTIONS类型是一个typedef为[QFlags](index.htm)\u003cBindOption\u003e 。它存储BindOption值的或组合。

* * *

## Method Documentation

```
QGLContext.__init__ (self, QGLFormat format, QPaintDevice device)
```

构造一个OpenGL上下文给定的_format_它指定为上下文多个显示选项。

如果底层的OpenGL / Window系统不能满足所有要求的功能_format_，的特征最接近的子集将被使用。创建后，[format](qglcontext.html#format)（ ）方法将返回所得到的实际格式。

需要注意的是后一[QGLContext](qglcontext.html)对象被创建，[create](qglcontext.html#create)（ ）必须显式地调用来创建实际的OpenGL上下文。上下文会[invalid](qglcontext.html#isValid)如果它是不能够获得GL上下文的。

**See also** [format](qglcontext.html#format)（）和[isValid](qglcontext.html#isValid)（ ） 。

```
bool QGLContext.areSharing (QGLContext context1, QGLContext context2)
```

返回True如果_context1_和_context2_分享他们吉尔资源，如纹理，着色器程序等，否则返回False 。

此功能被引入Qt的4.6 。

```
int QGLContext.bindTexture (self, QImage image, int target = GL_TEXTURE_2D, int format = GL_RGBA)
```

生成和二维GL纹理绑定到当前上下文的基础上，_image_。生成的纹理ID被返回，并且可以在以后使用中`glBindTexture()`电话。

该_target_参数指定纹理目标。默认的目标是`GL_TEXTURE_2D`。

该_format_参数设置纹理的内部格式。默认格式为`GL_RGBA`。

绑定_options_是一组用来决定如何将纹理绑定到上下文选项。

生成的纹理缓存，所以多次调用bindTexture （ ）具有相同[QImage](qimage.html)将返回相同的纹理ID 。

请注意，我们假设为glPixelStore （）和glPixelTransfer （ ）参数的默认值。

此功能被引入Qt的4.6 。

**See also** [deleteTexture](qglcontext.html#deleteTexture)（ ） 。

```
int QGLContext.bindTexture (self, QPixmap pixmap, int target = GL_TEXTURE_2D, int format = GL_RGBA)
```

这是一个重载函数。

读取压缩的纹理文件_fileName_并从它生成一个二维GL纹理。

此功能可以加载DirectDrawSurface （ DDS）纹理的DXT1 ， DXT3和DXT5 DDS格式，如果`GL_ARB_texture_compression`和`GL_EXT_texture_compression_s3tc`扩展的支持。

自从4.6.1 ，在ETC1格式的纹理可以，如果被加载`GL_OES_compressed_ETC1_RGB8_texture`扩展支持与ETC1纹理已被封装在PVR的容器格式。另外，在PVRTC2和PVRTC4格式的纹理可以被加载，如果`GL_IMG_texture_compression_pvrtc`支持扩展。

**See also** [deleteTexture](qglcontext.html#deleteTexture)（ ） 。

```
int QGLContext.bindTexture (self, QString fileName)
```

生成和二维GL纹理绑定到当前上下文的基础上，_image_。生成的纹理ID被返回，并且可以在以后使用中`glBindTexture()`电话。

这是一个重载函数。

```
int QGLContext.bindTexture (self, QImage image, int target, int format, BindOptions options)
```

这是一个重载函数。

生成并根据绑定一个2D GL纹理_pixmap_。

```
int QGLContext.bindTexture (self, QPixmap pixmap, int target, int format, BindOptions options)
```

这是一个重载函数。

生成和二维GL纹理绑定到当前上下文的基础上，_pixmap_。

此功能被引入Qt的4.6 。

```
bool QGLContext.chooseContext (self, QGLContext shareContext = None)
```

这个半内部函数被[create](qglcontext.html#create)（ ） 。它创建了一个与系统相关的OpenGL手柄相匹配的[format](qglcontext.html#format)的（ ）_shareContext_尽可能密切，返回True，如果成功则返回False合适的手柄找不到。

在Windows上，它调用虚函数[choosePixelFormat](qglcontext.html#choosePixelFormat)（），它找到一个匹配的像素格式标识符。在X11上，它调用虚函数[chooseVisual](qglcontext.html#chooseVisual)（），它找到一个恰当的X视觉。在其他平台上也可能有不同的工作。

```
sip.voidptr QGLContext.chooseVisual (self)
```

**X11 only:**这个虚函数试图找到一个可视化的格式相匹配，减少了需求，如果原来的请求不能得到满足。

该算法降低了格式的要求是相当简单的头脑，所以在你的子类中重写此方法，如果你的应用程序有视觉上的选择spcific要求。

**See also** [chooseContext](qglcontext.html#chooseContext)（ ） 。

```
bool QGLContext.create (self, QGLContext shareContext = None)
```

创建GL上下文。返回True ，如果它是成功地创造在构造函数中指定的绘图设备上的有效GL渲染上下文，否则返回False （即上下文是无效的） 。

创建成功后，[format](qglcontext.html#format)（ ）返回集合的创建GL渲染上下文的功能。

If _shareContext_指向一个有效的[QGLContext](qglcontext.html)，此方法将尝试建立这样的背景下，并与OpenGL显示列表和纹理对象共享_shareContext_。请注意，这可能会失败，如果两个上下文有不同的[formats](qglcontext.html#format)。使用[isSharing](qglcontext.html#isSharing)（） ，以查看是否共享将发挥作用。

**Warning:**实现注意事项： C + +的类成员初始化通常发生在类的构造函数。[QGLContext](qglcontext.html)是一个例外，因为它必须是简单定制。虚函数[chooseContext](qglcontext.html#chooseContext)（ ） （和[chooseVisual](qglcontext.html#chooseVisual)（ ）用于X11）可以在子类中被重新实现来选择特定的上下文。问题是，虚函数没有正确施工过程中调用（尽管这是正确的C + + ）因为C + +构造的类层次结构从下往上。出于这个原因，我们需要一个create（ ）函数。

**See also** [chooseContext](qglcontext.html#chooseContext)（ ）[format](qglcontext.html#format)（）和[isValid](qglcontext.html#isValid)（ ） 。

```
QGLContext QGLContext.currentContext ()
```

[

返回当前上下文，即任何OpenGL命令将当前被定向的上下文。返回0，如果没有上下文是最新的。

](qglcontext.html)

[**See also**](qglcontext.html) [makeCurrent](qglcontext.html#makeCurrent)（ ） 。

```
QGLContext.deleteTexture (self, int tx_id)
```

去除所确定的纹理_id_从纹理高速缓存，并呼吁glDeleteTextures （）来从上下文中删除的质感。

**See also** [bindTexture](qglcontext.html#bindTexture)（ ） 。

```
QPaintDevice QGLContext.device (self)
```

[

返回漆设备这方面设置。

](qpaintdevice.html)

[**See also**](qpaintdevice.html) [QGLContext.QGLContext](qglcontext.html#QGLContext)（ ） 。

```
bool QGLContext.deviceIsPixmap (self)
```

返回True如果这个上下文的绘图设备是像素图，否则返回False 。

```
QGLContext.doneCurrent (self)
```

不作任何GL上下文的当前上下文。通常情况下，你不需要调用此函数;[QGLContext](qglcontext.html)调用它是必要的。

```
QGLContext.drawTexture (self, QRectF target, int textureId, int textureTarget = GL_TEXTURE_2D)
```

此功能支持以下用例：

*   On OpenGL and OpenGL ES 1.x it draws the given texture, _textureId_, to the given target rectangle, _target_, in OpenGL model space. The _textureTarget_ should be a 2D texture target.
*   On OpenGL and OpenGL ES 2.x, if a painter is active, not inside a beginNativePainting / endNativePainting block, and uses the engine with type [QPaintEngine.OpenGL2](qpaintengine.html#Type-enum), the function will draw the given texture, _textureId_, to the given target rectangle, _target_, respecting the current painter state. This will let you draw a texture with the clip, transform, render hints, and composition mode set by the painter. Note that the texture target needs to be GL_TEXTURE_2D for this use case, and that this is the only supported use case under OpenGL ES 2.x.

此功能被引入Qt的4.4 。

```
QGLContext.drawTexture (self, QPointF point, int textureId, int textureTarget = GL_TEXTURE_2D)
```

此功能支持以下用例：

*   By default it draws the given texture, _textureId_, at the given _point_ in OpenGL model space. The _textureTarget_ should be a 2D texture target.
*   If a painter is active, not inside a beginNativePainting / endNativePainting block, and uses the engine with type [QPaintEngine.OpenGL2](qpaintengine.html#Type-enum), the function will draw the given texture, _textureId_, at the given _point_, respecting the current painter state. This will let you draw a texture with the clip, transform, render hints, and composition mode set by the painter. Note that the texture target needs to be GL_TEXTURE_2D for this use case.

**Note:**这个功能没有在任何版本的OpenGL ES的支持。

此功能被引入Qt的4.4 。

```
QGLFormat QGLContext.format (self)
```

[

返回得到的（这可能是要求什么的一个子集）的帧缓冲格式。

](qglformat.html)

[**See also**](qglformat.html) [setFormat](qglcontext.html#setFormat)（）和[requestedFormat](qglcontext.html#requestedFormat)（ ） 。

```
QGLContext.generateFontDisplayLists (self, QFont fnt, int listBase)
```

```
sip.voidptr QGLContext.getProcAddress (self, QString proc)
```

返回一个函数指针传递的GL扩展功能_proc_。如果不能获得一个指向函数返回0。

```
bool QGLContext.initialized (self)
```

返回True如果这方面已经初始化，也就是说，如果[QGLWidget.initializeGL](qglwidget.html#initializeGL)（ ）已在其上被执行，否则返回False 。

**See also** [setInitialized](qglcontext.html#setInitialized)（ ） 。

```
bool QGLContext.isSharing (self)
```

返回True如果这方面是与另一个共享其GL上下文[QGLContext](qglcontext.html)，否则返回假。需要注意的是上下文共享可能不会上下文不同格式之间的支持。

```
bool QGLContext.isValid (self)
```

返回True如果一个GL渲染上下文已经成功创建，否则返回False 。

```
QGLContext.makeCurrent (self)
```

使得此背景下，当前的OpenGL渲染上下文。你叫所有的GL函数在这样的背景下运作，直到另一个方面是由电流。

在一些非常罕见的情况下，底层调用可能会失败。如果发生这种情况的错误信息输出到stderr 。

```
QColor QGLContext.overlayTransparentColor (self)
```

[](qcolor.html)

[如果这方面是一个复盖面的有效范围内，则返回飞机的透明色。否则返回一个{](qcolor.html)[QColor.isValid](qcolor.html#isValid)（） } {无效}颜色。

返回[QColor](qcolor.html)对象将一般工作，只有当作为参数传递如预期[QGLWidget.qglColor](qglwidget.html#qglColor)（）或[QGLWidget.qglClearColor](qglwidget.html#qglClearColor)（ ） 。在某些情况下它也可以用于绘制透明的图形用[QPainter](qpainter.html)。

```
QGLFormat QGLContext.requestedFormat (self)
```

[](qglformat.html)

[返回的帧缓冲格式最初是要求在构造函数或](qglformat.html)[setFormat](qglcontext.html#setFormat)（ ） 。

**See also** [format](qglcontext.html#format)（ ） 。

```
QGLContext.reset (self)
```

重设背景，并使其无效。

**See also** [create](qglcontext.html#create)（）和[isValid](qglcontext.html#isValid)（ ） 。

```
QGLContext.setFormat (self, QGLFormat format)
```

设置_format_此上下文。上下文是[reset](qglcontext.html#reset)。

Call [create](qglcontext.html#create)（）来创建一个新的GL上下文，试图以匹配新的格式。

```
 [QGLContext](qglcontext.html) *cx;
 //  ...
 [QGLFormat](qglformat.html) f;
 f.setStereo(true);
 cx->setFormat(f);
 if (!cx->create())
     exit(); // no OpenGL support, or cannot render on the specified paintdevice
 if (!cx->format().stereo())
     exit(); // could not create stereo context

```

**See also** [format](qglcontext.html#format)（ ）[reset](qglcontext.html#reset)（）和[create](qglcontext.html#create)（ ） 。

```
QGLContext.setInitialized (self, bool on)
```

If _on_是真正的上下文被初始化，即QGLContext.setInitialized （ ）被调用就可以了。如果_on_是假的情况下没有被初始化。

**See also** [initialized](qglcontext.html#initialized)（ ） 。

```
QGLContext.setTextureCacheLimit (int size)
```

该函数设置限制的纹理缓存到_size_，表示以KB为单位。

默认情况下，缓存限制为大约64 MB的。

**See also** [textureCacheLimit](qglcontext.html#textureCacheLimit)（ ） 。

```
QGLContext.setWindowCreated (self, bool on)
```

If _on_是真正的上下文已为其创建一个窗口。如果_on_是假的无窗已为上下文中创建。

**See also** [windowCreated](qglcontext.html#windowCreated)（ ） 。

```
QGLContext.swapBuffers (self)
```

掉期，一个离屏缓冲屏幕内容。只有当上下文是在双缓冲模式。

**See also** [QGLFormat.setDoubleBuffer](qglformat.html#setDoubleBuffer)（ ） 。

```
int QGLContext.textureCacheLimit ()
```

返回以KB为单位的当前纹理缓存限制。

**See also** [setTextureCacheLimit](qglcontext.html#setTextureCacheLimit)（ ） 。

```
bool QGLContext.windowCreated (self)
```

如果一个窗口已经被用于这样的背景下建立的，则返回True ，否则返回False 。

**See also** [setWindowCreated](qglcontext.html#setWindowCreated)（ ） 。