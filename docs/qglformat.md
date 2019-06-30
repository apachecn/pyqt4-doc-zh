# QGLFormat Class Reference

## [[QtOpenGL](index.htm) module]

该QGLFormat类指定一个OpenGL渲染上下文的显示格式。[More...](#details)

### Types

*   `enum OpenGLContextProfile { NoProfile, CoreProfile, CompatibilityProfile }`
*   `enum OpenGLVersionFlag { OpenGL_Version_None, OpenGL_Version_1_1, OpenGL_Version_1_2, OpenGL_Version_1_3, ..., OpenGL_ES_Version_2_0 }`
*   `class **[OpenGLVersionFlags](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QGL.FormatOptions options, int plane = 0)`
*   `__init__ (self, QGLFormat other)`
*   `bool accum (self)`
*   `int accumBufferSize (self)`
*   `bool alpha (self)`
*   `int alphaBufferSize (self)`
*   `int blueBufferSize (self)`
*   `bool depth (self)`
*   `int depthBufferSize (self)`
*   `bool directRendering (self)`
*   `bool doubleBuffer (self)`
*   `int greenBufferSize (self)`
*   `bool hasOverlay (self)`
*   `int majorVersion (self)`
*   `int minorVersion (self)`
*   `int plane (self)`
*   `OpenGLContextProfile profile (self)`
*   `int redBufferSize (self)`
*   `bool rgba (self)`
*   `bool sampleBuffers (self)`
*   `int samples (self)`
*   `setAccum (self, bool enable)`
*   `setAccumBufferSize (self, int size)`
*   `setAlpha (self, bool enable)`
*   `setAlphaBufferSize (self, int size)`
*   `setBlueBufferSize (self, int size)`
*   `setDepth (self, bool enable)`
*   `setDepthBufferSize (self, int size)`
*   `setDirectRendering (self, bool enable)`
*   `setDoubleBuffer (self, bool enable)`
*   `setGreenBufferSize (self, int size)`
*   `setOption (self, QGL.FormatOptions opt)`
*   `setOverlay (self, bool enable)`
*   `setPlane (self, int plane)`
*   `setProfile (self, OpenGLContextProfile profile)`
*   `setRedBufferSize (self, int size)`
*   `setRgba (self, bool enable)`
*   `setSampleBuffers (self, bool enable)`
*   `setSamples (self, int numSamples)`
*   `setStencil (self, bool enable)`
*   `setStencilBufferSize (self, int size)`
*   `setStereo (self, bool enable)`
*   `setSwapInterval (self, int interval)`
*   `setVersion (self, int major, int minor)`
*   `bool stencil (self)`
*   `int stencilBufferSize (self)`
*   `bool stereo (self)`
*   `int swapInterval (self)`
*   `bool testOption (self, QGL.FormatOptions opt)`

### Static Methods

*   `QGLFormat defaultFormat ()`
*   `QGLFormat defaultOverlayFormat ()`
*   `bool hasOpenGL ()`
*   `bool hasOpenGLOverlays ()`
*   `OpenGLVersionFlags openGLVersionFlags ()`
*   `setDefaultFormat (QGLFormat f)`
*   `setDefaultOverlayFormat (QGLFormat f)`

### Special Methods

*   `bool __eq__ (self, QGLFormat)`
*   `bool __ne__ (self, QGLFormat)`

* * *

## Detailed Description

该QGLFormat类指定一个OpenGL渲染上下文的显示格式。

一种显示格式有几个特点：

*   [Double or single buffering.](qglformat.html#setDoubleBuffer)
*   [Depth buffer.](qglformat.html#setDepth)
*   [RGBA or color index mode.](qglformat.html#setRgba)
*   [Alpha channel.](qglformat.html#setAlpha)
*   [Accumulation buffer.](qglformat.html#setAccum)
*   [Stencil buffer.](qglformat.html#setStencil)
*   [Stereo buffers.](qglformat.html#setStereo)
*   [Direct rendering.](qglformat.html#setDirectRendering)
*   [Presence of an overlay.](qglformat.html#setOverlay)
*   [Plane of an overlay.](qglformat.html#setPlane)
*   [Multisample buffers.](qglformat.html#setSampleBuffers)

您也可以指定首选位深度的颜色缓冲，深度缓冲，阿尔法缓冲，缓冲的积累以及与功能模板缓冲区：[setRedBufferSize](qglformat.html#setRedBufferSize)（ ）[setGreenBufferSize](qglformat.html#setGreenBufferSize)（ ）[setBlueBufferSize](qglformat.html#setBlueBufferSize)（ ）[setDepthBufferSize](qglformat.html#setDepthBufferSize)（ ）[setAlphaBufferSize](qglformat.html#setAlphaBufferSize)（ ）[setAccumBufferSize](qglformat.html#setAccumBufferSize)（）和[setStencilBufferSize](qglformat.html#setStencilBufferSize)（ ） 。

请注意，即使您指定你喜欢一个32位深度缓冲（如带setDepthBufferSize （ 32 ） ） ，选择该格式可能不具有一个32位的深度缓冲区，即使有可用的带有32位深度缓冲的格式。主要的原因是系统依赖采摘算法在不同的平台上是如何工作的，以及一些格式选项可能有优先级比别人高。

您可以创建和告诉QGLFormat对象，你想从一个OpenGL渲染上下文是什么渲染选项。

OpenGL驱动程序或硬件加速的可能或可能不支持高级功能，例如alpha通道或立体视。如果您要求一些功能，驱动器/硬件不提供当你创建一个[QGLWidget](qglwidget.html)，你会得到一个渲染上下文的功能最接近的子集。

有不同的方式来定义一个渲染上下文的显示特性。一个是创建一个QGLFormat并使其成为默认为整个应用程序：

```
 QGLFormat fmt;
 fmt.setAlpha(true);
 fmt.setStereo(true);
 QGLFormat.setDefaultFormat(fmt);

```

或者，您可以创建一个对象时指定所需的格式的[QGLWidget](qglwidget.html)子类：

```
 QGLFormat fmt;
 fmt.setDoubleBuffer(false);                 // single buffer
 fmt.setDirectRendering(false);              // software rendering
 MyGLWidget* myWidget = new MyGLWidget(fmt, ...);

```

窗口小部件被创建之后，你可以找出其中所要求的功能的系统能够提供：

```
 QGLFormat fmt;
 fmt.setOverlay(true);
 fmt.setStereo(true);
 MyGLWidget* myWidget = new MyGLWidget(fmt, ...);
 if (!myWidget->format().stereo()) {
     // ok, goggles off
     if (!myWidget->format().hasOverlay()) {
         qFatal("Cool hardware required");
     }
 }

```

OpenGL是Silicon Graphics公司在美国和其他国家的商标。

* * *

## Type Documentation

```
QGLFormat.OpenGLContextProfile
```

这个枚举变量描述了可以为上下文实现的OpenGL 3.2或更高版本中指定的OpenGL上下文配置文件。这些配置文件是从OpenGL ES的配置文件不同。

| Constant | Value | Description |
| --- | --- | --- |
| `QGLFormat.NoProfile` | `0` | OpenGL的版本比3.2更低。 |
| `QGLFormat.CoreProfile` | `1` | 不推荐使用的功能在OpenGL 3.0版无法使用。 |
| `QGLFormat.CompatibilityProfile` | `2` | 从早期的OpenGL版本功能可用。 |

这个枚举被引入或修改的Qt 4.7 。

```
QGLFormat.OpenGLVersionFlag
```

这个枚举变量描述了各种OpenGL版本是由Qt的认可。使用[QGLFormat.openGLVersionFlags](qglformat.html#openGLVersionFlags)（ ）函数来确定哪些版本的在运行时支持​​。

| Constant | Value | Description |
| --- | --- | --- |
| `QGLFormat.OpenGL_Version_None` | `0x00000000` | 如果没有OpenGL是或者没有OpenGL上下文是最新的。 |
| `QGLFormat.OpenGL_Version_1_1` | `0x00000001` | OpenGL版本1.1或更高版本存在。 |
| `QGLFormat.OpenGL_Version_1_2` | `0x00000002` | OpenGL版本1.2或更高版本存在。 |
| `QGLFormat.OpenGL_Version_1_3` | `0x00000004` | OpenGL版本1.3或更高版本存在。 |
| `QGLFormat.OpenGL_Version_1_4` | `0x00000008` | OpenGL版本1.4或更高版本存在。 |
| `QGLFormat.OpenGL_Version_1_5` | `0x00000010` | OpenGL版本1.5或更高版本存在。 |
| `QGLFormat.OpenGL_Version_2_0` | `0x00000020` | OpenGL版本2.0或更高版本存在。请注意， 2.0版支持1.5版的所有功能。 |
| `QGLFormat.OpenGL_Version_2_1` | `0x00000040` | OpenGL的2.1或更高版本的存在。 |
| `QGLFormat.OpenGL_Version_3_0` | `0x00001000` | OpenGL版本3.0或更高版本存在。 |
| `QGLFormat.OpenGL_Version_3_1` | `0x00002000` | OpenGL的3.1或更高的版本存在。需要注意的是OpenGL的3.1或更高版本不一定支持3.0版和更低的所有功能。 |
| `QGLFormat.OpenGL_Version_3_2` | `0x00004000` | OpenGL版本3.2或更高版本存在。 |
| `QGLFormat.OpenGL_Version_3_3` | `0x00008000` | OpenGL版本3.3或更高版本存在。 |
| `QGLFormat.OpenGL_Version_4_0` | `0x00010000` | OpenGL版本4.0或更高版本存在。 |
| `QGLFormat.OpenGL_ES_CommonLite_Version_1_0` | `0x00000100` | 的OpenGL ES 1.0版通用精简版或更高版本存在。 |
| `QGLFormat.OpenGL_ES_Common_Version_1_0` | `0x00000080` | OpenGL ES的1.0版本通用或更高版本存在。 Common文件支持常见的精简版的所有功能。 |
| `QGLFormat.OpenGL_ES_CommonLite_Version_1_1` | `0x00000400` | 的OpenGL ES 1.1版通用精简版或更高版本存在。 |
| `QGLFormat.OpenGL_ES_Common_Version_1_1` | `0x00000200` | OpenGL ES的1.1版本通用或更高版本存在。 Common文件支持常见的精简版的所有功能。 |
| `QGLFormat.OpenGL_ES_Version_2_0` | `0x00000800` | 的OpenGL ES 2.0或更高版本存在。需要注意的是OpenGL ES的2.0版本不支持的OpenGL ES 1.x的所有功能所以，如果OpenGL_ES_Version_2_0返回，返回没有的ES 1.x的标志。 |

另请参阅[http://www.opengl.org](http://www.opengl.org/)关于OpenGL的不同版本的更多信息。

这个枚举被引入或修改的Qt 4.2 。

该OpenGLVersionFlags类型是一个typedef为[QFlags](index.htm)\u003cOpenGLVersionFlag\u003e 。它存储OpenGLVersionFlag值的或组合。

**See also** [openGLVersionFlags](qglformat.html#openGLVersionFlags)（ ） 。

* * *

## Method Documentation

```
QGLFormat.__init__ (self)
```

构造一个[QGLFormat](qglformat.html)用下面的默认设置对象：

*   [Double buffer:](qglformat.html#setDoubleBuffer) Enabled.
*   [Depth buffer:](qglformat.html#setDepth) Enabled.
*   [RGBA:](qglformat.html#setRgba) Enabled (i.e., color index disabled).
*   [Alpha channel:](qglformat.html#setAlpha) Disabled.
*   [Accumulator buffer:](qglformat.html#setAccum) Disabled.
*   [Stencil buffer:](qglformat.html#setStencil) Enabled.
*   [Stereo:](qglformat.html#setStereo) Disabled.
*   [Direct rendering:](qglformat.html#setDirectRendering) Enabled.
*   [Overlay:](qglformat.html#setOverlay) Disabled.
*   [Plane:](qglformat.html#setPlane) 0 (i.e., normal plane).
*   [Multisample buffers:](qglformat.html#setSampleBuffers) Disabled.

```
QGLFormat.__init__ (self, QGL.FormatOptions options, int plane = 0)
```

创建[QGLFormat](qglformat.html)对象，它是当前的一个副本[defaultFormat](qglformat.html#defaultFormat)（ ） 。

If _options_不为0 ，则默认格式是由特定的格式选项修改。该_options_参数应该是[QGL.FormatOption](qgl.html#FormatOption-enum)值OR'ed在一起。

这个构造函数可以很容易地从指定的派生类一定想要的格式[QGLWidget](qglwidget.html)例如：

```
 // The rendering in MyGLWidget depends on using
 // stencil buffer and alpha channel
 MyGLWidget.MyGLWidget([QWidget](qwidget.html)* parent)
     : [QGLWidget](qglwidget.html)([QGLFormat](qglformat.html)(QGL.StencilBuffer | QGL.AlphaChannel), parent)
 {
     if (!format().stencil())
         qWarning("Could not get stencil buffer; results will be suboptimal");
     if (!format().alpha())
         qWarning("Could not get alpha channel; results will be suboptimal");
     ...
 }

```

请注意，有[QGL.FormatOption](qgl.html#FormatOption-enum)值开启和关闭都，如格式设置[QGL.DepthBuffer](qgl.html#FormatOption-enum)和[QGL.NoDepthBuffer](qgl.html#FormatOption-enum)，[QGL.DirectRendering](qgl.html#FormatOption-enum)和[QGL.IndirectRendering](qgl.html#FormatOption-enum)等。

该_plane_参数默认为0 ，并且是这种格式应该与相关的平面。并非所有的OpenGL实现支持复盖/衬底渲染的飞机。

**See also** [defaultFormat](qglformat.html#defaultFormat)（ ）[setOption](qglformat.html#setOption)（）和[setPlane](qglformat.html#setPlane)（ ） 。

```
QGLFormat.__init__ (self, QGLFormat other)
```

构造的副本_other_。

```
bool QGLFormat.accum (self)
```

返回True如果累积缓冲器被启用，否则返回False 。积累缓冲区默认是禁用的。

**See also** [setAccum](qglformat.html#setAccum)（）和[setAccumBufferSize](qglformat.html#setAccumBufferSize)（ ） 。

```
int QGLFormat.accumBufferSize (self)
```

返回累积缓冲区的大小。

**See also** [setAccumBufferSize](qglformat.html#setAccumBufferSize)（ ）[accum](qglformat.html#accum)（）和[setAccum](qglformat.html#setAccum)（ ） 。

```
bool QGLFormat.alpha (self)
```

返回True如果在framebuffer的阿尔法缓冲启用，否则返回False 。阿尔法缓冲默认情况下禁用。

**See also** [setAlpha](qglformat.html#setAlpha)（）和[setAlphaBufferSize](qglformat.html#setAlphaBufferSize)（ ） 。

```
int QGLFormat.alphaBufferSize (self)
```

返回阿尔法缓冲区大小。

**See also** [alpha](qglformat.html#alpha)（ ）[setAlpha](qglformat.html#setAlpha)（）和[setAlphaBufferSize](qglformat.html#setAlphaBufferSize)（ ） 。

```
int QGLFormat.blueBufferSize (self)
```

返回蓝色的缓冲区大小。

这个函数中引入了Qt 4.2中。

**See also** [setBlueBufferSize](qglformat.html#setBlueBufferSize)（ ） 。

```
QGLFormat QGLFormat.defaultFormat ()
```

[](qglformat.html)

[返回默认](qglformat.html)[QGLFormat](qglformat.html)应用程序。所有[QGLWidget](qglwidget.html)除非指定了其他格式的创建使用这种格式的对象，如当它们被构造。

如果没有特殊的默认格式已设定使用[setDefaultFormat](qglformat.html#setDefaultFormat)（） ，默认格式是相同的，与建立[QGLFormat](qglformat.html#QGLFormat)（ ） 。

**See also** [setDefaultFormat](qglformat.html#setDefaultFormat)（ ） 。

```
QGLFormat QGLFormat.defaultOverlayFormat ()
```

[](qglformat.html)

[返回默认](qglformat.html)[QGLFormat](qglformat.html)对于叠加背景。

默认叠加格式为：

*   [Double buffer:](qglformat.html#setDoubleBuffer) Disabled.
*   [Depth buffer:](qglformat.html#setDepth) Disabled.
*   [RGBA:](qglformat.html#setRgba) Disabled (i.e., color index enabled).
*   [Alpha channel:](qglformat.html#setAlpha) Disabled.
*   [Accumulator buffer:](qglformat.html#setAccum) Disabled.
*   [Stencil buffer:](qglformat.html#setStencil) Disabled.
*   [Stereo:](qglformat.html#setStereo) Disabled.
*   [Direct rendering:](qglformat.html#setDirectRendering) Enabled.
*   [Overlay:](qglformat.html#setOverlay) Disabled.
*   [Multisample buffers:](qglformat.html#setSampleBuffers) Disabled.
*   [Plane:](qglformat.html#setPlane) 1 (i.e., first overlay plane).

**See also** [setDefaultOverlayFormat](qglformat.html#setDefaultOverlayFormat)（）和[setDefaultFormat](qglformat.html#setDefaultFormat)（ ） 。

```
bool QGLFormat.depth (self)
```

返回True如果深度缓冲被启用，否则返回False 。深度缓存是默认启用的。

**See also** [setDepth](qglformat.html#setDepth)（）和[setDepthBufferSize](qglformat.html#setDepthBufferSize)（ ） 。

```
int QGLFormat.depthBufferSize (self)
```

返回深度缓冲区的大小。

**See also** [depth](qglformat.html#depth)（ ）[setDepth](qglformat.html#setDepth)（）和[setDepthBufferSize](qglformat.html#setDepthBufferSize)（ ） 。

```
bool QGLFormat.directRendering (self)
```

返回True如果直接渲染启用，否则返回False 。

直接渲染是默认启用的。

**See also** [setDirectRendering](qglformat.html#setDirectRendering)（ ） 。

```
bool QGLFormat.doubleBuffer (self)
```

返回True如果双缓冲使能，否则返回False 。双缓冲是默认启用的。

**See also** [setDoubleBuffer](qglformat.html#setDoubleBuffer)（ ） 。

```
int QGLFormat.greenBufferSize (self)
```

返回绿化缓冲区大小。

这个函数中引入了Qt 4.2中。

**See also** [setGreenBufferSize](qglformat.html#setGreenBufferSize)（ ） 。

```
bool QGLFormat.hasOpenGL ()
```

返回True如果窗口系统有任何的OpenGL支持，否则返回False 。

**Warning:**此函数不能被调用，直到[QApplication](qapplication.html)对象被创建。

```
bool QGLFormat.hasOpenGLOverlays ()
```

返回True如果窗口系统支持OpenGL复盖，否则返回False 。

**Warning:**此函数不能被调用，直到[QApplication](qapplication.html)对象被创建。

```
bool QGLFormat.hasOverlay (self)
```

返回True如果复盖面已启用，否则返回False 。

复盖默认是禁用的。

**See also** [setOverlay](qglformat.html#setOverlay)（ ） 。

```
int QGLFormat.majorVersion (self)
```

返回OpenGL的主要版本。

此功能被引入Qt的4.7 。

**See also** [setVersion](qglformat.html#setVersion)（）和[minorVersion](qglformat.html#minorVersion)（ ） 。

```
int QGLFormat.minorVersion (self)
```

返回OpenGL的次要版本。

此功能被引入Qt的4.7 。

**See also** [setVersion](qglformat.html#setVersion)（）和[majorVersion](qglformat.html#majorVersion)（ ） 。

```
OpenGLVersionFlags QGLFormat.openGLVersionFlags ()
```

[

标识，在运行时，它的OpenGL是由当前平台支持的版本。

请注意，如果OpenGL版本1.5的支持，也支持它的前辈（即1.4版，下） 。识别特定功能​​的支持，如多纹理，测试中首次引入的功能的版本（即版本在多纹理的情况下1.3） ，以适应运行时平台的最大可能的组。

](index.htm)

[此功能需要一个有效的当前的OpenGL上下文中工作，否则它会返回](index.htm)[OpenGL_Version_None](qglformat.html#OpenGLVersionFlag-enum)。

这个函数中引入了Qt 4.2中。

**See also** [hasOpenGL](qglformat.html#hasOpenGL)（）和[hasOpenGLOverlays](qglformat.html#hasOpenGLOverlays)（ ） 。

```
int QGLFormat.plane (self)
```

返回此格式的平面。默认为正常格式是0，这意味着在正常平面。默认为复盖格式是1 ，这是第一个复盖面。

**See also** [setPlane](qglformat.html#setPlane)（）和[defaultOverlayFormat](qglformat.html#defaultOverlayFormat)（ ） 。

```
OpenGLContextProfile QGLFormat.profile (self)
```

[

返回OpenGL上下文配置文件。

此功能被引入Qt的4.7 。

](qglformat.html#OpenGLContextProfile-enum)

[**See also**](qglformat.html#OpenGLContextProfile-enum) [setProfile](qglformat.html#setProfile)（ ） 。

```
int QGLFormat.redBufferSize (self)
```

返回红色的缓冲区大小。

这个函数中引入了Qt 4.2中。

**See also** [setRedBufferSize](qglformat.html#setRedBufferSize)（ ） 。

```
bool QGLFormat.rgba (self)
```

返回True如果RGBA颜色模式设置。返回False，如果颜色索引模式设置。默认的色彩模式是RGBA 。

**See also** [setRgba](qglformat.html#setRgba)（ ） 。

```
bool QGLFormat.sampleBuffers (self)
```

返回True如果多重采样缓冲支持允许，否则返回False 。

多重采样缓冲区默认是禁用的。

**See also** [setSampleBuffers](qglformat.html#setSampleBuffers)（ ） 。

```
int QGLFormat.samples (self)
```

返回每个像素的样本多重采样时启用的数量。默认情况下，最高的样本数是可被使用。

**See also** [setSampleBuffers](qglformat.html#setSampleBuffers)（ ）[sampleBuffers](qglformat.html#sampleBuffers)（）和[setSamples](qglformat.html#setSamples)（ ） 。

```
QGLFormat.setAccum (self, bool enable)
```

If _enable_是真正的使积累缓冲，否则将禁用积累缓冲区。

积累缓冲区默认是禁用的。

积累缓冲区用于创建模糊效果和多重曝光。

**See also** [accum](qglformat.html#accum)（）和[setAccumBufferSize](qglformat.html#setAccumBufferSize)（ ） 。

```
QGLFormat.setAccumBufferSize (self, int size)
```

设置首选累加缓冲器的大小，其中_size_是比特深度的每个RGBA分量。

**See also** [accum](qglformat.html#accum)（ ）[setAccum](qglformat.html#setAccum)（）和[accumBufferSize](qglformat.html#accumBufferSize)（ ） 。

```
QGLFormat.setAlpha (self, bool enable)
```

If _enable_是真的让阿尔法缓冲，否则将禁用阿尔法缓冲区。

阿尔法缓冲默认情况下禁用。

阿尔法缓冲器通常用于实现透明性或半透明性。 RGBA中的A指定像素的透明度。

**See also** [alpha](qglformat.html#alpha)（）和[setAlphaBufferSize](qglformat.html#setAlphaBufferSize)（ ） 。

```
QGLFormat.setAlphaBufferSize (self, int size)
```

设置优选的α缓冲区的大小为_size_。此功能允许隐式的alpha通道。

**See also** [setRedBufferSize](qglformat.html#setRedBufferSize)（ ）[setGreenBufferSize](qglformat.html#setGreenBufferSize)（）和[alphaBufferSize](qglformat.html#alphaBufferSize)（ ） 。

```
QGLFormat.setBlueBufferSize (self, int size)
```

设置首选蓝色的缓冲区大小_size_。

这个函数中引入了Qt 4.2中。

**See also** [blueBufferSize](qglformat.html#blueBufferSize)（ ）[setRedBufferSize](qglformat.html#setRedBufferSize)（ ）[setGreenBufferSize](qglformat.html#setGreenBufferSize)（）和[setAlphaBufferSize](qglformat.html#setAlphaBufferSize)（ ） 。

```
QGLFormat.setDefaultFormat (QGLFormat f)
```

设置新的默认[QGLFormat](qglformat.html)为应用程序_f_。例如，要设置单缓冲为默认，而不是双缓冲，你的main（）中可能包含这样的代码：

```
 [QApplication](qapplication.html) a(argc, argv);
 [QGLFormat](qglformat.html) f;
 f.setDoubleBuffer(false);
 [QGLFormat](qglformat.html).setDefaultFormat(f);

```

**See also** [defaultFormat](qglformat.html#defaultFormat)（ ） 。

```
QGLFormat.setDefaultOverlayFormat (QGLFormat f)
```

设置新的默认[QGLFormat](qglformat.html)为复盖到上下文_f_。这个格式被用于每当一个[QGLWidget](qglwidget.html)与一个格式创建的[hasOverlay](qglformat.html#hasOverlay)（ ）启用。

例如，要获得双重缓冲的复盖范围内（如果有的话） ，使用如下代码：

```
 [QGLFormat](qglformat.html) f = [QGLFormat](qglformat.html).defaultOverlayFormat();
 f.setDoubleBuffer(true);
 [QGLFormat](qglformat.html).setDefaultOverlayFormat(f);

```

像往常一样，你可以创建小部件的底层OpenGL的系统是否能够提供所要求的规格后发现：

```
 // ...continued from above
 MyGLWidget* myWidget = new MyGLWidget([QGLFormat](qglformat.html)(QGL.HasOverlay), ...);
 if (myWidget->format().hasOverlay()) {
     // Yes, we got an overlay, let's check _its_ format:
     [QGLContext](qglcontext.html)* olContext = myWidget->overlayContext();
     if (olContext->format().doubleBuffer())
         ; // yes, we got a double buffered overlay
     else
         ; // no, only single buffered overlays are available
 }

```

**See also** [defaultOverlayFormat](qglformat.html#defaultOverlayFormat)（ ） 。

```
QGLFormat.setDepth (self, bool enable)
```

If _enable_是真正的使深度缓冲区，否则禁用深度缓冲。

深度缓存是默认启用的。

深度缓冲（或Z缓冲）的目的是去除隐藏的表面。像素的基础上，以观众的距离分配的Z值。具有高Z值的像素更靠近观看者比具有低Z值的像素。此信息用于决定是否要绘制的像素或没有。

**See also** [depth](qglformat.html#depth)（）和[setDepthBufferSize](qglformat.html#setDepthBufferSize)（ ） 。

```
QGLFormat.setDepthBufferSize (self, int size)
```

设置最小深度缓冲区的大小为_size_。

**See also** [depthBufferSize](qglformat.html#depthBufferSize)（ ）[setDepth](qglformat.html#setDepth)（）和[depth](qglformat.html#depth)（ ） 。

```
QGLFormat.setDirectRendering (self, bool enable)
```

If _enable_是真的，可直接渲染，否则禁止直接渲染。

直接渲染是默认启用的。

启用此选项将使绕过OpenGL的底层窗口系统，并直接从硬件渲染到屏幕上，如果这是支持的系统。

**See also** [directRendering](qglformat.html#directRendering)（ ） 。

```
QGLFormat.setDoubleBuffer (self, bool enable)
```

If _enable_是真正的集双缓冲，否则设置一个缓冲。

双缓冲是默认启用的。

双缓冲就是图形呈现在屏幕外的缓冲区，而不是直接到屏幕上的技术。当绘图完成时，程序调用一个swapBuffers （）函数来交换与缓冲器中的画面的内容。其结果是无闪烁画图，常常更好的性能。

需要注意的是单缓冲环境目前不支持与EGL 。

**See also** [doubleBuffer](qglformat.html#doubleBuffer)（ ）[QGLContext.swapBuffers](qglcontext.html#swapBuffers)（）和[QGLWidget.swapBuffers](qglwidget.html#swapBuffers)（ ） 。

```
QGLFormat.setGreenBufferSize (self, int size)
```

设置首选的绿色缓冲区大小_size_。

这个函数中引入了Qt 4.2中。

**See also** [greenBufferSize](qglformat.html#greenBufferSize)（ ）[setRedBufferSize](qglformat.html#setRedBufferSize)（ ）[setBlueBufferSize](qglformat.html#setBlueBufferSize)（）和[setAlphaBufferSize](qglformat.html#setAlphaBufferSize)（ ） 。

```
QGLFormat.setOption (self, QGL.FormatOptions opt)
```

设置格式选项_opt_。

**See also** [testOption](qglformat.html#testOption)（ ） 。

```
QGLFormat.setOverlay (self, bool enable)
```

If _enable_是真的让一个复盖面，否则禁止复盖面。

启用复盖面会造成[QGLWidget](qglwidget.html)创建一个复盖面的附加上下文。请参阅[QGLWidget](qglwidget.html)文档了解更多信息。

**See also** [hasOverlay](qglformat.html#hasOverlay)（ ） 。

```
QGLFormat.setPlane (self, int plane)
```

所要求的平面设置为_plane_。 0是正常的平面中， 1是第一复盖面， 2是第二复盖面等; -1，-2等是底层平面。

请注意，相对于其他格式规范，飞机规格将完全匹配。这意味着，如果你指定一个平面底层OpenGL的系统不能提供，一个[invalid](qglwidget.html#isValid) [QGLWidget](qglwidget.html)将被创建。

**See also** [plane](qglformat.html#plane)（ ） 。

```
QGLFormat.setProfile (self, OpenGLContextProfile profile)
```

设置OpenGL上下文配置文件_profile_。该_profile_如果所请求的OpenGL版本小于3.2被忽略。

此功能被引入Qt的4.7 。

**See also** [profile](qglformat.html#profile)（ ） 。

```
QGLFormat.setRedBufferSize (self, int size)
```

设置首选红色的缓冲区大小_size_。

这个函数中引入了Qt 4.2中。

**See also** [redBufferSize](qglformat.html#redBufferSize)（ ）[setGreenBufferSize](qglformat.html#setGreenBufferSize)（ ）[setBlueBufferSize](qglformat.html#setBlueBufferSize)（）和[setAlphaBufferSize](qglformat.html#setAlphaBufferSize)（ ） 。

```
QGLFormat.setRgba (self, bool enable)
```

If _enable_是真正的集RGBA模式。如果_enable_是假套颜色索引模式。

默认的色彩模式是RGBA 。

RGBA是大多数的OpenGL应用程序的首选模式。在RGBA颜色模式指定的颜色为红+绿+蓝+阿尔法四胞胎。

在颜色索引模式中指定一个索引颜色查找表。

**See also** [rgba](qglformat.html#rgba)（ ） 。

```
QGLFormat.setSampleBuffers (self, bool enable)
```

If _enable_诚然，一个GL上下文与多重采样缓冲支持回升，否则忽略。

**See also** [sampleBuffers](qglformat.html#sampleBuffers)（ ）[setSamples](qglformat.html#setSamples)（）和[samples](qglformat.html#samples)（ ） 。

```
QGLFormat.setSamples (self, int numSamples)
```

设置每个像素的样本的首选号码时，多重采样已启用_numSamples_。默认情况下，最多可用样本的使用。

**See also** [setSampleBuffers](qglformat.html#setSampleBuffers)（ ）[sampleBuffers](qglformat.html#sampleBuffers)（）和[samples](qglformat.html#samples)（ ） 。

```
QGLFormat.setStencil (self, bool enable)
```

If _enable_是真正的使模板缓冲，否则将禁用模板缓存。

模板缓冲区是默认启用的。

模板缓冲区口罩绘图区域的某些部分，这样蒙面零件不上绘制。

**See also** [stencil](qglformat.html#stencil)（）和[setStencilBufferSize](qglformat.html#setStencilBufferSize)（ ） 。

```
QGLFormat.setStencilBufferSize (self, int size)
```

设置首选模板缓冲区大小_size_。

**See also** [stencilBufferSize](qglformat.html#stencilBufferSize)（ ）[setStencil](qglformat.html#setStencil)（）和[stencil](qglformat.html#stencil)（ ） 。

```
QGLFormat.setStereo (self, bool enable)
```

If _enable_是真的让立体声缓冲，否则将禁用立体声缓冲。

立体声缓冲默认情况下禁用。

立体声缓冲提供额外的颜色缓冲区生成左眼和右眼的图像。

**See also** [stereo](qglformat.html#stereo)（ ） 。

```
QGLFormat.setSwapInterval (self, int interval)
```

设置首选的交换​​间隔。这可用于同步的GL绘图成一个系统的窗口，以在屏幕的垂直刷新。设置一个_interval_值为0将关闭垂直同步刷新关闭，大于0的任何值将变为垂直同步的。

在Windows和X11下，其中`WGL_EXT_swap_control`和`GLX_SGI_video_sync`扩展的使用，_interval_参数可被用来设定显示之前将发生缓冲交换的视频帧的最小数目。实际上，在设置_interval_10 ，意味着将有每一个缓冲区交换之间的10个垂直回扫。

在Windows下的`WGL_EXT_swap_control`扩展名必须存在，而且在X11下的`GLX_SGI_video_sync`扩展名必须存在。

这个函数中引入了Qt 4.2中。

**See also** [swapInterval](qglformat.html#swapInterval)（ ） 。

```
QGLFormat.setVersion (self, int major, int minor)
```

设置OpenGL版本到_major_和_minor_号码。如果所请求的OpenGL版本兼容的情况下不能创建，与1.x版本兼容的上下文被创建来代替。

此功能被引入Qt的4.7 。

**See also** [majorVersion](qglformat.html#majorVersion)（）和[minorVersion](qglformat.html#minorVersion)（ ） 。

```
bool QGLFormat.stencil (self)
```

返回True如果模板缓存被启用，否则返回False 。模板缓冲区是默认启用的。

**See also** [setStencil](qglformat.html#setStencil)（）和[setStencilBufferSize](qglformat.html#setStencilBufferSize)（ ） 。

```
int QGLFormat.stencilBufferSize (self)
```

返回模板缓冲区大小。

**See also** [stencil](qglformat.html#stencil)（ ）[setStencil](qglformat.html#setStencil)（）和[setStencilBufferSize](qglformat.html#setStencilBufferSize)（ ） 。

```
bool QGLFormat.stereo (self)
```

返回True如果立体声缓冲使能，否则返回False 。立体声缓冲默认情况下禁用。

**See also** [setStereo](qglformat.html#setStereo)（ ） 。

```
int QGLFormat.swapInterval (self)
```

返回当前设置的交换间隔。如果设定的时间间隔交换不支持在系统总帐实现返回-1。

这个函数中引入了Qt 4.2中。

**See also** [setSwapInterval](qglformat.html#setSwapInterval)（ ） 。

```
bool QGLFormat.testOption (self, QGL.FormatOptions opt)
```

返回True如果格式选项_opt_被置位，否则返回False 。

**See also** [setOption](qglformat.html#setOption)（ ） 。

```
bool QGLFormat.__eq__ (self, QGLFormat)
```

```
bool QGLFormat.__ne__ (self, QGLFormat)
```