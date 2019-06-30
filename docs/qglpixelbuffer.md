# QGLPixelBuffer Class Reference

## [[QtOpenGL](index.htm) module]

该QGLPixelBuffer类封装了一个OpenGL pbuffer的。[More...](#details)

继承[QPaintDevice](qpaintdevice.html)。

### Methods

*   `__init__ (self, QSize size, QGLFormat format = QGLFormat.defaultFormat(), QGLWidget shareWidget = None)`
*   `__init__ (self, int width, int height, QGLFormat format = QGLFormat.defaultFormat(), QGLWidget shareWidget = None)`
*   `int bindTexture (self, QImage image, int target = GL_TEXTURE_2D)`
*   `int bindTexture (self, QPixmap pixmap, int target = GL_TEXTURE_2D)`
*   `int bindTexture (self, QString fileName)`
*   `bool bindToDynamicTexture (self, int texture)`
*   `deleteTexture (self, int texture_id)`
*   `int devType (self)`
*   `bool doneCurrent (self)`
*   `drawTexture (self, QRectF target, int textureId, int textureTarget = GL_TEXTURE_2D)`
*   `drawTexture (self, QPointF point, int textureId, int textureTarget = GL_TEXTURE_2D)`
*   `QGLFormat format (self)`
*   `int generateDynamicTexture (self)`
*   `int handle (self)`
*   `bool isValid (self)`
*   `bool makeCurrent (self)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric metric)`
*   `QPaintEngine paintEngine (self)`
*   `releaseFromDynamicTexture (self)`
*   `QSize size (self)`
*   `QImage toImage (self)`
*   `updateDynamicTexture (self, int texture_id)`

### Static Methods

*   `bool hasOpenGLPbuffers ()`

* * *

## Detailed Description

该QGLPixelBuffer类封装了一个OpenGL pbuffer的。

渲染到pbuffer的通常情况下用完整的硬件加速。这可以比渲染成显着更快[QPixmap](qpixmap.html)。

有三种方法来使用这个类：

1.  **We can draw into the pbuffer and convert it to a [QImage](qimage.html) using [toImage](qglpixelbuffer.html#toImage)().**这通常比调用更快[QGLWidget.renderPixmap](qglwidget.html#renderPixmap)（ ） 。
2.  **We can draw into the pbuffer and copy the contents into an OpenGL texture using [updateDynamicTexture](qglpixelbuffer.html#updateDynamicTexture)().**这使我们能够创建与pbuffer的支持所有的系统动态纹理和作品。
3.  **On systems that support it, we can bind the pbuffer to an OpenGL texture.**纹理将自动更新时， pbuffer的内容发生变化，不再需要额外的复制操作。这仅支持在Windows和Mac OS X系统，提供了`render_texture`扩展名。需要注意的是在Windows下，一个多采样pbuffer的不能与结合使用`render_texture`扩展名。如果一个多重采样pbuffer的在Windows下所要求的`render_texture`扩展关闭该pbuffer的。

### Threading

由于Qt的4.8的，有可能使用的是渲染成QGLPixelBuffer[QPainter](qpainter.html)在一个单独的线程。需要注意的是OpenGL的2.0或OpenGL ES 2.0的是需要这种合作。此外， X11下，有必要设置[Qt.AA_X11InitThreads](qt.html#ApplicationAttribute-enum)应用属性。

pbuffers的是通过对OpenGL提供`pbuffer`扩展;调用hasOpenGLPbuffer （ ） ，以找出是否为系统提供pbuffers的。

* * *

## Method Documentation

```
QGLPixelBuffer.__init__ (self, QSize size, QGLFormat format = QGLFormat.defaultFormat(), QGLWidget shareWidget = None)
```

构造给定一个OpenGL pbuffer的_size_。如果没有_format_被指定，则[default format](qglformat.html#defaultFormat)被使用。如果_shareWidget_参数指向一个有效的[QGLWidget](qglwidget.html)，该pbuffer的将共享其上下文_shareWidget_。

如果您打算在这个pbuffer的绑定为一个动态纹理的宽度和高度组件`size`必须是两个（例如， 512× 128）的权力。

**See also** [size](qglpixelbuffer.html#size)（）和[format](qglpixelbuffer.html#format)（ ） 。

```
QGLPixelBuffer.__init__ (self, int width, int height, QGLFormat format = QGLFormat.defaultFormat(), QGLWidget shareWidget = None)
```

这是一个重载函数。

构造一个OpenGL pbuffer的同_width_和_height_。如果没有_format_被指定，则[default format](qglformat.html#defaultFormat)被使用。如果_shareWidget_参数指向一个有效的[QGLWidget](qglwidget.html)，该pbuffer的将共享其上下文_shareWidget_。

如果您打算在这个pbuffer的绑定为一个动态纹理的宽度和高度组件`size`必须是两个（例如， 512× 128）的权力。

**See also** [size](qglpixelbuffer.html#size)（）和[format](qglpixelbuffer.html#format)（ ） 。

```
int QGLPixelBuffer.bindTexture (self, QImage image, int target = GL_TEXTURE_2D)
```

生成和二维GL纹理绑定到当前上下文的基础上，_image_。所生成的纹理ID被返回，并且可以被用于在以后glBindTexture （）调用。

该_target_参数指定纹理目标。

相当于调用[QGLContext.bindTexture](qglcontext.html#bindTexture)（ ） 。

**See also** [deleteTexture](qglpixelbuffer.html#deleteTexture)（ ） 。

```
int QGLPixelBuffer.bindTexture (self, QPixmap pixmap, int target = GL_TEXTURE_2D)
```

这是一个重载函数。

生成并根据绑定一个2D GL纹理_pixmap_。

相当于调用[QGLContext.bindTexture](qglcontext.html#bindTexture)（ ） 。

**See also** [deleteTexture](qglpixelbuffer.html#deleteTexture)（ ） 。

```
int QGLPixelBuffer.bindTexture (self, QString fileName)
```

这是一个重载函数。

读取DirectDrawSurface （ DDS ）压缩文件_fileName_并从它生成一个二维GL纹理。

相当于调用[QGLContext.bindTexture](qglcontext.html#bindTexture)（ ） 。

**See also** [deleteTexture](qglpixelbuffer.html#deleteTexture)（ ） 。

```
bool QGLPixelBuffer.bindToDynamicTexture (self, int texture)
```

通过绑定指定的质感_texture_id_该pbuffer的。成功时返回TRUE ，否则返回False 。

纹理必须是相同的尺寸和格式的pbuffer的的。

要解除绑定纹理，呼叫[releaseFromDynamicTexture](qglpixelbuffer.html#releaseFromDynamicTexture)（ ） 。虽然质地是绑定的，它会自动更新时， pbuffer的内容发生变化，不再需要额外的复制操作。

例如：

```
 [QGLPixelBuffer](qglpixelbuffer.html) pbuffer(...);
 ...
 pbuffer.makeCurrent();
 GLuint dynamicTexture = pbuffer.generateDynamicTexture();
 pbuffer.bindToDynamicTexture(dynamicTexture);
 ...
 pbuffer.releaseFromDynamicTexture();

```

**Warning:**该函数使用`render_texture`扩展，这是目前没有在X11下的支持。在所有的系统（包括X11）的作品另一种方法是手动使用pbuffer的内容复制到一个纹理[updateDynamicTexture](qglpixelbuffer.html#updateDynamicTexture)（ ） 。

**Warning:**对于bindToDynamicTexture （ ）调用成功，在Mac OS X上， pbuffer的需要一个共享的情况下，即[QGLPixelBuffer](qglpixelbuffer.html)必须以份额小部件来创建。

**See also** [generateDynamicTexture](qglpixelbuffer.html#generateDynamicTexture)（）和[releaseFromDynamicTexture](qglpixelbuffer.html#releaseFromDynamicTexture)（ ） 。

```
QGLPixelBuffer.deleteTexture (self, int texture_id)
```

去除所确定的纹理_texture_id_从纹理高速缓存。

相当于调用[QGLContext.deleteTexture](qglcontext.html#deleteTexture)（ ） 。

```
int QGLPixelBuffer.devType (self)
```

```
bool QGLPixelBuffer.doneCurrent (self)
```

是没有上下文的当前OpenGL上下文。成功时返回TRUE ，否则返回False 。

```
QGLPixelBuffer.drawTexture (self, QRectF target, int textureId, int textureTarget = GL_TEXTURE_2D)
```

绘制给定的质感，_textureId_向给定目标矩形，_target_在OpenGL的模型空间。该_textureTarget_应该是一个2D纹理的目标。

等同于相应的[QGLContext.drawTexture](qglcontext.html#drawTexture)（ ） 。

此功能被引入Qt的4.4 。

```
QGLPixelBuffer.drawTexture (self, QPointF point, int textureId, int textureTarget = GL_TEXTURE_2D)
```

绘制给定的质感，_textureId_，在给定的_point_在OpenGL的模型空间。该textureTarget参数应该是一个2D纹理的目标。

等同于相应的[QGLContext.drawTexture](qglcontext.html#drawTexture)（ ） 。

此功能被引入Qt的4.4 。

```
QGLFormat QGLPixelBuffer.format (self)
```

[

返回pbuffer的格式。该格式可以是从被请求的不同。

```
int QGLPixelBuffer.generateDynamicTexture (self)
```

](qglformat.html)

[生成并结合一个2D GL的手感是大小相同的pbuffer的，并返回该纹理的ID。这可与结合使用](qglformat.html)[bindToDynamicTexture](qglpixelbuffer.html#bindToDynamicTexture)（）和[updateDynamicTexture](qglpixelbuffer.html#updateDynamicTexture)（ ） 。

**See also** [size](qglpixelbuffer.html#size)（ ） 。

```
int QGLPixelBuffer.handle (self)
```

返回本机pbuffer的句柄。

```
bool QGLPixelBuffer.hasOpenGLPbuffers ()
```

返回True如果OpenGL的`pbuffer`扩展出现在这个系统上，否则返回False 。

```
bool QGLPixelBuffer.isValid (self)
```

返回True如果pbuffer的是有效的，否则返回False 。

```
bool QGLPixelBuffer.makeCurrent (self)
```

使得这个pbuffer的当前OpenGL渲染上下文。成功时返回TRUE ，否则返回False 。

**See also** [QGLContext.makeCurrent](qglcontext.html#makeCurrent)（）和[doneCurrent](qglpixelbuffer.html#doneCurrent)（ ） 。

```
int QGLPixelBuffer.metric (self, QPaintDevice.PaintDeviceMetric metric)
```

从重新实现[QPaintDevice.metric](qpaintdevice.html#metric)（ ） 。

```
QPaintEngine QGLPixelBuffer.paintEngine (self)
```

[](qpaintengine.html)

[从重新实现](qpaintengine.html)[QPaintDevice.paintEngine](qpaintdevice.html#paintEngine)（ ） 。

```
QGLPixelBuffer.releaseFromDynamicTexture (self)
```

发布任何以前绑定的质感pbuffer的。

**See also** [bindToDynamicTexture](qglpixelbuffer.html#bindToDynamicTexture)（ ） 。

```
QSize QGLPixelBuffer.size (self)
```

[

返回pbuffer的大小。

](qsize.html)

```
QImage QGLPixelBuffer.toImage (self)
```

[](qimage.html)

[返回pbuffer的内容作为](qimage.html)[QImage](qimage.html)。

```
QGLPixelBuffer.updateDynamicTexture (self, int texture_id)
```

与指定复制pbuffer的内容到纹理_texture_id_。

纹理必须是相同的尺寸和格式的pbuffer的的。

例如：

```
 [QGLPixelBuffer](qglpixelbuffer.html) pbuffer(...);
 ...
 pbuffer.makeCurrent();
 GLuint dynamicTexture = pbuffer.generateDynamicTexture();
 ...
 pbuffer.updateDynamicTexture(dynamicTexture);

```

在支持Windows和Mac OS X系统的替代`render_texture`分机是用[bindToDynamicTexture](qglpixelbuffer.html#bindToDynamicTexture)（）来获取纹理的动态更新。

**See also** [generateDynamicTexture](qglpixelbuffer.html#generateDynamicTexture)（）和[bindToDynamicTexture](qglpixelbuffer.html#bindToDynamicTexture)（ ） 。