# QGLFramebufferObjectFormat Class Reference

## [[QtOpenGL](index.htm) module]

该QGLFramebufferObjectFormat类指定一个OpenGL帧缓冲区对象的格式。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QGLFramebufferObjectFormat other)`
*   `QGLFramebufferObject.Attachment attachment (self)`
*   `int internalTextureFormat (self)`
*   `bool mipmap (self)`
*   `int samples (self)`
*   `setAttachment (self, QGLFramebufferObject.Attachment attachment)`
*   `setInternalTextureFormat (self, int internalTextureFormat)`
*   `setMipmap (self, bool enabled)`
*   `setSamples (self, int samples)`
*   `setTextureTarget (self, int target)`
*   `int textureTarget (self)`

### Special Methods

*   `bool __eq__ (self, QGLFramebufferObjectFormat other)`
*   `bool __ne__ (self, QGLFramebufferObjectFormat other)`

* * *

## Detailed Description

该QGLFramebufferObjectFormat类指定一个OpenGL帧缓冲区对象的格式。

一个帧缓冲对象有几个特点：

*   [Number of samples per pixels.](qglframebufferobjectformat.html#setSamples)
*   [Depth and/or stencil attachments.](qglframebufferobjectformat.html#setAttachment)
*   [Texture target.](qglframebufferobjectformat.html#setTextureTarget)
*   [Internal texture format.](qglframebufferobjectformat.html#setInternalTextureFormat)

请注意，所需的附件每像素采样或数可能不是由硬件驱动程序的支持。通话[QGLFramebufferObject.format](qglframebufferobject.html#format)（ ）创建后[QGLFramebufferObject](qglframebufferobject.html)找到用于创建帧缓冲对象的确切格式。

* * *

## Method Documentation

```
QGLFramebufferObjectFormat.__init__ (self)
```

创建[QGLFramebufferObjectFormat](qglframebufferobjectformat.html)对象，用于指定一个OpenGL帧缓冲区对象的格式。

默认情况下，格式规定，没有附件，质感目标非多重采样帧缓冲区对象`GL_TEXTURE_2D`和内部格式`GL_RGBA8`。基于OpenGL / ES系统，默认的内部格式是`GL_RGBA`。

**See also** [samples](qglframebufferobjectformat.html#samples)（ ）[attachment](qglframebufferobjectformat.html#attachment)（）和[internalTextureFormat](qglframebufferobjectformat.html#internalTextureFormat)（ ） 。

```
QGLFramebufferObjectFormat.__init__ (self, QGLFramebufferObjectFormat other)
```

构造的副本_other_。

```
QGLFramebufferObject.Attachment QGLFramebufferObjectFormat.attachment (self)
```

[](qglframebufferobject.html#Attachment-enum)

[返回附加到帧缓冲区对象的深度和模具缓冲器的配置。默认值是](qglframebufferobject.html#Attachment-enum)[QGLFramebufferObject.NoAttachment](qglframebufferobject.html#Attachment-enum)。

**See also** [setAttachment](qglframebufferobjectformat.html#setAttachment)（ ） 。

```
int QGLFramebufferObjectFormat.internalTextureFormat (self)
```

返回一个帧缓冲对象的纹理或多重采样帧缓冲区对象的颜色缓冲区的内部格式。默认值是`GL_RGBA8`在桌面OpenGL系统和`GL_RGBA`基于OpenGL / ES系统。

**See also** [setInternalTextureFormat](qglframebufferobjectformat.html#setInternalTextureFormat)（ ） 。

```
bool QGLFramebufferObjectFormat.mipmap (self)
```

如果纹理映射已启用，则返回True 。

此功能被引入Qt的4.8 。

**See also** [setMipmap](qglframebufferobjectformat.html#setMipmap)（ ） 。

```
int QGLFramebufferObjectFormat.samples (self)
```

返回每个像素的样本数，如果一个帧缓冲区对象是一个多重采样帧缓冲区对象。否则，返回0 。默认值是0。

**See also** [setSamples](qglframebufferobjectformat.html#setSamples)（ ） 。

```
QGLFramebufferObjectFormat.setAttachment (self, QGLFramebufferObject.Attachment attachment)
```

设置一个帧缓冲对象的附件配置_attachment_。

**See also** [attachment](qglframebufferobjectformat.html#attachment)（ ） 。

```
QGLFramebufferObjectFormat.setInternalTextureFormat (self, int internalTextureFormat)
```

设置一个帧缓冲对象的纹理或多重采样帧缓冲区对象的颜色缓冲区的内部格式_internalTextureFormat_。

**See also** [internalTextureFormat](qglframebufferobjectformat.html#internalTextureFormat)（ ） 。

```
QGLFramebufferObjectFormat.setMipmap (self, bool enabled)
```

使纹理映射，如果_enabled_为True，否则禁用它。

纹理映射默认情况下禁用。

如果纹理映射已启用，更多的内存将被分配给mipmap级别。该mipmap级别可以通过绑定的质地和调用glGenerateMipmap （ ）进行更新。纹理映射不能启用多重采样帧缓冲对象。

此功能被引入Qt的4.8 。

**See also** [mipmap](qglframebufferobjectformat.html#mipmap)（）和[QGLFramebufferObject.texture](qglframebufferobject.html#texture)（ ） 。

```
QGLFramebufferObjectFormat.setSamples (self, int samples)
```

设置每个像素的样本的多重采样帧缓冲区对象的数量，以_samples_。 0的默认样本数代表一个普通的非多重采样帧缓冲区对象。

如果不支持硬件每个像素的样本的期望量则​​每个像素的样本的最大数目将被使用。需要注意的是多重采样帧缓冲对象不能被绑定为纹理。此外，该`GL_EXT_framebuffer_multisample`扩展需要创建每像素多于一个样本的帧缓冲。

**See also** [samples](qglframebufferobjectformat.html#samples)（ ） 。

```
QGLFramebufferObjectFormat.setTextureTarget (self, int target)
```

设置纹理对象附加到帧缓冲对象的纹理_target_。忽略多重采样帧缓冲对象。

**See also** [textureTarget](qglframebufferobjectformat.html#textureTarget)（）和[samples](qglframebufferobjectformat.html#samples)（ ） 。

```
int QGLFramebufferObjectFormat.textureTarget (self)
```

返回质感目标附加到帧缓冲区对象的质感。忽略多重采样帧缓冲对象。默认值是`GL_TEXTURE_2D`。

**See also** [setTextureTarget](qglframebufferobjectformat.html#setTextureTarget)（）和[samples](qglframebufferobjectformat.html#samples)（ ） 。

```
bool QGLFramebufferObjectFormat.__eq__ (self, QGLFramebufferObjectFormat other)
```

```
bool QGLFramebufferObjectFormat.__ne__ (self, QGLFramebufferObjectFormat other)
```