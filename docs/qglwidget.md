# QGLWidget Class Reference

## [[QtOpenGL](index.htm) module]

该的QGLWidget类是一个小部件的绘制OpenGL图形。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None, QGLWidget shareWidget = None, Qt.WindowFlags flags = 0)`
*   `__init__ (self, QGLContext context, QWidget parent = None, QGLWidget shareWidget = None, Qt.WindowFlags flags = 0)`
*   `__init__ (self, QGLFormat format, QWidget parent = None, QGLWidget shareWidget = None, Qt.WindowFlags flags = 0)`
*   `bool autoBufferSwap (self)`
*   `int bindTexture (self, QImage image, int target = GL_TEXTURE_2D, int format = GL_RGBA)`
*   `int bindTexture (self, QPixmap pixmap, int target = GL_TEXTURE_2D, int format = GL_RGBA)`
*   `int bindTexture (self, QString fileName)`
*   `int bindTexture (self, QImage image, int target, int format, QGLContext.BindOptions options)`
*   `int bindTexture (self, QPixmap pixmap, int target, int format, QGLContext.BindOptions options)`
*   `QGLColormap colormap (self)`
*   `QGLContext context (self)`
*   `deleteTexture (self, int tx_id)`
*   `doneCurrent (self)`
*   `bool doubleBuffer (self)`
*   `drawTexture (self, QRectF target, int textureId, int textureTarget = GL_TEXTURE_2D)`
*   `drawTexture (self, QPointF point, int textureId, int textureTarget = GL_TEXTURE_2D)`
*   `bool event (self, QEvent)`
*   `int fontDisplayListBase (self, QFont font, int listBase = 2000)`
*   `QGLFormat format (self)`
*   `glDraw (self)`
*   `glInit (self)`
*   `QImage grabFrameBuffer (self, bool withAlpha = False)`
*   `initializeGL (self)`
*   `initializeOverlayGL (self)`
*   `bool isSharing (self)`
*   `bool isValid (self)`
*   `makeCurrent (self)`
*   `makeOverlayCurrent (self)`
*   `QGLContext overlayContext (self)`
*   `QPaintEngine paintEngine (self)`
*   `paintEvent (self, QPaintEvent)`
*   `paintGL (self)`
*   `paintOverlayGL (self)`
*   `qglClearColor (self, QColor c)`
*   `qglColor (self, QColor c)`
*   `QPixmap renderPixmap (self, int width = 0, int height = 0, bool useContext = False)`
*   `renderText (self, int x, int y, QString str, QFont font = QFont(), int listBase = 2000)`
*   `renderText (self, float x, float y, float z, QString str, QFont font = QFont(), int listBase = 2000)`
*   `resizeEvent (self, QResizeEvent)`
*   `resizeGL (self, int w, int h)`
*   `resizeOverlayGL (self, int w, int h)`
*   `setAutoBufferSwap (self, bool on)`
*   `setColormap (self, QGLColormap map)`
*   `setContext (self, QGLContext context, QGLContext shareContext = None, bool deleteOldContext = True)`
*   `setFormat (self, QGLFormat format)`
*   `setMouseTracking (self, bool enable)`
*   `swapBuffers (self)`
*   `updateGL (self)`
*   `updateOverlayGL (self)`

### Static Methods

*   `QImage convertToGLFormat (QImage img)`

* * *

## Detailed Description

该的QGLWidget类是一个小部件的绘制OpenGL图形。

的QGLWidget提供的功能显示集成到Qt应用OpenGL图形。它使用起来非常简单。你从它继承并使用子像任何其他[QWidget](qwidget.html)，但你必须使用之间的选择[QPainter](qpainter.html)和标准的OpenGL渲染命令。

QGLWidget的规定，你可以在你的子类重新实现来执行典型任务的OpenGL三种简便的虚函数：

*   [paintGL](qglwidget.html#paintGL)() - Renders the OpenGL scene. Gets called whenever the widget needs to be updated.
*   [resizeGL](qglwidget.html#resizeGL)() - Sets up the OpenGL viewport, projection, etc. Gets called whenever the widget has been resized (and also when it is shown for the first time because all newly created widgets get a resize event automatically).
*   [initializeGL](qglwidget.html#initializeGL)() - Sets up the OpenGL rendering context, defines display lists, etc. Gets called once before the first time [resizeGL](qglwidget.html#resizeGL)() or [paintGL](qglwidget.html#paintGL)() is called.

下面是一个如何的QGLWidget子类可能看起来粗线条：

```
 class MyGLDrawer : public QGLWidget
 {
     Q_OBJECT        // must include this if you use Qt signals/slots

 public:
     MyGLDrawer([QWidget](qwidget.html) *parent)
         : QGLWidget(parent) {}

 protected:

     void initializeGL()
     {
         // Set up the rendering context, define display lists etc.:
         ...
         glClearColor(0.0, 0.0, 0.0, 0.0);
         glEnable(GL_DEPTH_TEST);
         ...
     }

     void resizeGL(int w, int h)
     {
         // setup viewport, projection etc.:
         glViewport(0, 0, (GLint)w, (GLint)h);
         ...
         glFrustum(...);
         ...
     }

     void paintGL()
     {
         // draw the scene:
         ...
         glRotatef(...);
         glMaterialfv(...);
         glBegin(GL_QUADS);
         glVertex3f(...);
         glVertex3f(...);
         ...
         glEnd();
         ...
     }

 };

```

如果你需要从触发比其他地方重绘[paintGL](qglwidget.html#paintGL)（ ）（一个典型的例子，当使用的是[timers](qtimer.html)动画场景） ，你应该调用widget的[updateGL](qglwidget.html#updateGL)（）函数。

Widget的OpenGL渲染上下文是由电流时[paintGL](qglwidget.html#paintGL)（ ）[resizeGL](qglwidget.html#resizeGL)（） ，或[initializeGL](qglwidget.html#initializeGL)（）被调用。如果你需要从其他地方（例如，在你的widget的构造函数或在自己的油漆函数）调用标准的OpenGL API函数，你必须调用[makeCurrent](qglwidget.html#makeCurrent)（ ）第一。

的QGLWidget提供用于请求新显示器[format](qglformat.html)你也可以创建小部件定制渲染[contexts](qglcontext.html)。

你也可以分享OpenGL显示列表的QGLWidget对象之间（见的QGLWidget构造的细节的文档）。

请注意，Windows ，下[QGLContext](qglcontext.html)属于的QGLWidget有当的QGLWidget被重设父重新创建。这是由于在Windows平台上的局限性必要的。这很可能会导致问题的那些子类，并安装自己的用户[QGLContext](qglcontext.html)上的QGLWidget 。它可以解决此问题通过把QGLWidget的一个虚拟部件内，然后重定父级的虚拟窗口小部件，而不是QGLWidget的。这将侧步完全的问题，这也是我们建议对于需要这类功能的用户。

在Mac OS X中，当Qt的是建立与可可的支持，一个的QGLWidget不能放在ontop的本身任何同级部件。这是由于可可API中的限制和不支持的苹果。

### Overlays

如果复盖层由底层系统所支持的的QGLWidget创建在除了正常的上下文中的GL复盖范围内。

如果你想使用背景画面，您在指定它[format](qglformat.html)。 （注：复盖必须传递给构造函数的QGLWidget的格式要求。 ）你的GL小工具还应该实现一些虚拟方法或全部：

*   [paintOverlayGL](qglwidget.html#paintOverlayGL)()
*   [resizeOverlayGL](qglwidget.html#resizeOverlayGL)()
*   [initializeOverlayGL](qglwidget.html#initializeOverlayGL)()

这些方法中以相同的方式工作，因为正常[paintGL](qglwidget.html#paintGL)（ ）等函数，不同之处在于，当复盖范围内由目前他们将被调用。你可以明确地使复盖范围内的电流通过[makeOverlayCurrent](qglwidget.html#makeOverlayCurrent)（ ） ，你可以直接通过调用访问复盖范围内（例如，要求其透明色）[overlayContext](qglwidget.html#overlayContext)（ ） 。

X服务器上，其中缺省视觉是在复盖面，非GL Qt的窗也可以用于复盖层。

### Painting Techniques

如上所述，子类的QGLWidget来呈现以下列方式纯三维内容：

*   Reimplement the [QGLWidget.initializeGL](qglwidget.html#initializeGL)() and [QGLWidget.resizeGL](qglwidget.html#resizeGL)() to set up the OpenGL state and provide a perspective transformation.
*   Reimplement [QGLWidget.paintGL](qglwidget.html#paintGL)() to paint the 3D scene, calling only OpenGL functions to draw on the widget.

它也可以绘制2D图形到的QGLWidget子类中，有必要重新实现[QGLWidget.paintEvent](qglwidget.html#paintEvent)（ ）并执行以下操作：

*   Construct a [QPainter](qpainter.html) object.
*   Initialize it for use on the widget with the [QPainter.begin](qpainter.html#begin)() function.
*   Draw primitives using [QPainter](qpainter.html)'s member functions.
*   Call [QPainter.end](qpainter.html#end)() to finish painting.

对3D内容的顶部Overpainting 2D内容需要一点更多的努力。一种方法来执行此操作示于[Overpainting](index.htm)例子。

### Threading

由于Qt的4.8版本，这样做螺纹GL渲染的支持进行了改进。有迹象表明，我们目前支持三种情况：

*   1\. Buffer swapping in a thread.

    交换缓冲区的双缓冲上下文可以是同步，锁定调用这可能是一个代价高昂的操作在一些GL实现。尤其是等嵌入式设备。这不是最佳的有CPU空转而GPU是做一个缓冲区交换。在这种情况下，它是可以做到的渲染在主线程并执行实际的缓冲区交换在一个单独的线程。这可以通过以下步骤来完成：

    1 。通话[doneCurrent](qglwidget.html#doneCurrent)（ ）的时候，渲染完成后，主线程。

    2 。通知交换的线程，它可以抓住的上下文。

    3 。使在交换线程渲染上下文电流[makeCurrent](qglwidget.html#makeCurrent)（ ），然后调用[swapBuffers](qglwidget.html#swapBuffers)（ ） 。

    4 。通话[doneCurrent](qglwidget.html#doneCurrent)（ ）在交换线，并通知主线程的交换完成。

    这样做将释放主线程，以便它可以继续使用，例如，处理UI事件或网络请求。即使是涉及上下文交换，相对于具有主线程等待而GPU完成交换操作也可能是优选的。注意，这是高度依赖于实现。

*   2\. Texture uploading in a thread.

    做质地上传在一个线程可能是应用处理大量需要被显示的，例如像一个图片库的图像应用程序非常有用。这是通过对现有的受支持Qt中[bindTexture](qglwidget.html#bindTexture)（ ） API 。这样做的一个简单的方法是创建两个共享QGLWidgets 。一个是由当前在主界面线程，而其它是由当前在纹理上传线程。在上传线程窗口小部件从未显示，它仅用于与主线程共享的纹理。对于通过绑定每一个纹理[bindTexture](qglwidget.html#bindTexture)（ ） ，通知主线程，以便它可以开始使用了质感。

*   3\. Using [QPainter](qpainter.html) to draw into a QGLWidget in a thread.

    在Qt 4.8 ，它可以用来绘制成的QGLWidget一个[QPainter](qpainter.html)在一个单独的线程。注意，这也可能QGLPixelBuffers和QGLFramebufferObjects 。由于这是唯一支持在GL 2绘图引擎， OpenGL的2.0或OpenGL ES 2.0是必需的。

    QGLWidgets只能在主界面线程被创建。这意味着调用[doneCurrent](qglwidget.html#doneCurrent)（ ）是需要从主线程释放GL上下文之前，小部件可以被另一个线程被捲入。此外，主界面线程将派遣调整大小和油漆事件到的QGLWidget时，小部件的大小时，或它的一部分将暴露在外或需要重绘。因此，有必要来处理这些事件，因为里面的QGLWidget的默认实现将尽力使的QGLWidget的背景电流，这将再次与渲染到小部件的任何线程干扰。重新实现[QGLWidget.paintEvent](qglwidget.html#paintEvent)（）和[QGLWidget.resizeEvent](qglwidget.html#resizeEvent)（ ）通知渲染线程，一个调整大小或更新是必要的，并注意不要调用基类的实现。如果要渲染一个动画，它可能没有必要处理Paint事件，因为在所有的渲染线程正在做定期更新。那么这将是足以重新实现[QGLWidget.paintEvent](qglwidget.html#paintEvent)（ ）什么也不做。

因为这样做线程渲染时一般规则：注意，绑定和在不同的线程释放上下文必须由用户进行同步。一个GL渲染上下文只能是当前一个线程在任何时候。如果您尝试打开一个[QPainter](qpainter.html)上的QGLWidget和窗口小部件的渲染上下文是当前在另一个线程，它会失败。

需要注意的是X11下，有必要设置[Qt.AA_X11InitThreads](qt.html#ApplicationAttribute-enum)应用程序的属性，使X11的库和GLX调用线程安全的，否则上述情况将会失败。

除了这一点，使用一个单独的线程原料GL调用呈现支持。

_OpenGL is a trademark of Silicon Graphics, Inc. in the United States and other countries._

* * *

## Method Documentation

```
QGLWidget.__init__ (self, QWidget parent = None, QGLWidget shareWidget = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个OpenGL窗口小部件与_parent_小工具。

该[default format](qglformat.html#defaultFormat)被使用。窗口小部件会[invalid](qglwidget.html#isValid)如果系统中没有[OpenGL support](qglformat.html#hasOpenGL)。

该_parent_和widget标志，_f_，参数被传递到[QWidget](qwidget.html)构造函数。

If _shareWidget_是一个有效的[QGLWidget](qglwidget.html)，这个widget会分享OpenGL的显示列表和纹理与对象_shareWidget_。但是，如果_shareWidget_而这个小工具有不同的[formats](qglwidget.html#format)，共享可能是不可能的。您可以检查共享是否有效通过调用[isSharing](qglwidget.html#isSharing)（ ） 。

OpenGL的渲染状态等的初始化应通过重写来完成的[initializeGL](qglwidget.html#initializeGL)（）函数，而不是在你的构造[QGLWidget](qglwidget.html)子类。

**See also** [QGLFormat.defaultFormat](qglformat.html#defaultFormat)（）和[Textures Example](index.htm)。

```
QGLWidget.__init__ (self, QGLContext context, QWidget parent = None, QGLWidget shareWidget = None, Qt.WindowFlags flags = 0)
```

该_context_说法有它的所有权转移给Qt的。

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个OpenGL窗口小部件与父_parent_。

该_context_参数是一个指向[QGLContext](qglcontext.html)你希望绑定到这个小工具。这使您可以通过在自己的[QGLContext](qglcontext.html)子类。

窗口小部件会[invalid](qglwidget.html#isValid)如果系统中没有[OpenGL support](qglformat.html#hasOpenGL)。

该_parent_和widget标志，_f_，参数被传递到[QWidget](qwidget.html)构造函数。

If _shareWidget_是一个有效的[QGLWidget](qglwidget.html)，这个widget会分享OpenGL的显示列表和纹理与对象_shareWidget_。但是，如果_shareWidget_而这个小工具有不同的[formats](qglwidget.html#format)，共享可能是不可能的。您可以检查共享是否有效通过调用[isSharing](qglwidget.html#isSharing)（ ） 。

OpenGL的渲染状态等的初始化应通过重写来完成的[initializeGL](qglwidget.html#initializeGL)（）函数，而不是在你的构造[QGLWidget](qglwidget.html)子类。

**See also** [QGLFormat.defaultFormat](qglformat.html#defaultFormat)（）和[isValid](qglwidget.html#isValid)（ ） 。

```
QGLWidget.__init__ (self, QGLFormat format, QWidget parent = None, QGLWidget shareWidget = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个OpenGL窗口小部件与父_parent_。

该_format_参数指定所需[rendering options](qglformat.html)。如果底层的OpenGL / Window系统不能满足所有要求的功能_format_，的特征最接近的子集将被使用。创建后，[format](qglwidget.html#format)（ ）方法将返回所得到的实际格式。

窗口小部件会[invalid](qglwidget.html#isValid)如果系统中没有[OpenGL support](qglformat.html#hasOpenGL)。

该_parent_和widget标志，_f_，参数被传递到[QWidget](qwidget.html)构造函数。

If _shareWidget_是一个有效的[QGLWidget](qglwidget.html)，这个widget会分享OpenGL的显示列表和纹理与对象_shareWidget_。但是，如果_shareWidget_而这个小工具有不同的[formats](qglwidget.html#format)，共享可能是不可能的。您可以检查共享是否有效通过调用[isSharing](qglwidget.html#isSharing)（ ） 。

OpenGL的渲染状态等的初始化应通过重写来完成的[initializeGL](qglwidget.html#initializeGL)（）函数，而不是在你的构造[QGLWidget](qglwidget.html)子类。

**See also** [QGLFormat.defaultFormat](qglformat.html#defaultFormat)（）和[isValid](qglwidget.html#isValid)（ ） 。

```
bool QGLWidget.autoBufferSwap (self)
```

返回True如果部件是做自动GL缓冲交换，否则返回False 。

**See also** [setAutoBufferSwap](qglwidget.html#setAutoBufferSwap)（ ） 。

```
int QGLWidget.bindTexture (self, QImage image, int target = GL_TEXTURE_2D, int format = GL_RGBA)
```

调用QGLContext ： bindTexture （_image_，_target_，_format_）对当前设置环境。

**See also** [deleteTexture](qglwidget.html#deleteTexture)（ ） 。

```
int QGLWidget.bindTexture (self, QPixmap pixmap, int target = GL_TEXTURE_2D, int format = GL_RGBA)
```

调用QGLContext ： bindTexture （_pixmap_，_target_，_format_）对当前设置环境。

**See also** [deleteTexture](qglwidget.html#deleteTexture)（ ） 。

```
int QGLWidget.bindTexture (self, QString fileName)
```

这是一个重载函数。

绑定_options_是一组用来决定如何将纹理绑定到上下文选项。

此功能被引入Qt的4.6 。

```
int QGLWidget.bindTexture (self, QImage image, int target, int format, QGLContext.BindOptions options)
```

这是一个重载函数。

生成和二维GL纹理绑定到当前上下文的基础上，_pixmap_。所生成的纹理ID被返回，并且可以在使用

绑定_options_是一组用来决定如何将纹理绑定到上下文选项。

此功能被引入Qt的4.6 。

```
int QGLWidget.bindTexture (self, QPixmap pixmap, int target, int format, QGLContext.BindOptions options)
```

这是一个重载函数。

调用QGLContext.bindTexture （_fileName_）对当前设置环境。

**See also** [deleteTexture](qglwidget.html#deleteTexture)（ ） 。

```
QGLColormap QGLWidget.colormap (self)
```

[

返回色图这个小工具。

通常它是一个可以安装不同的色彩映射表只有顶层窗口部件。要求的子插件的颜色表将返回颜色映射为孩子的顶级窗口部件。

](qglcolormap.html)

[如果没有颜色表已设置这个小工具的](qglcolormap.html)[QGLColormap](qglcolormap.html)返回的将是空的。

**See also** [setColormap](qglwidget.html#setColormap)（）和[QGLColormap.isEmpty](qglcolormap.html#isEmpty)（ ） 。

```
QGLContext QGLWidget.context (self)
```

[

返回这个窗口部件的背景下。

](qglcontext.html)

[这是可能的情况下是无效的（参见](qglcontext.html)[isValid](qglwidget.html#isValid)（）） ，例如，如果底层的硬件不支持所请求的格式属性。

```
QImage QGLWidget.convertToGLFormat (QImage img)
```

[](qimage.html)

[将图像转换_img_到预期的OpenGL函数，如glTexImage2D （ ）的未命名格式。返回的图像是不能用作](qimage.html)[QImage](qimage.html)，但[QImage.width](qimage.html#width)（ ）[QImage.height](qimage.html#height)（）和[QImage.bits](qimage.html#bits)（ ）可用于与OpenGL的。使用的GL格式`GL_RGBA`。

```
QGLWidget.deleteTexture (self, int tx_id)
```

调用QGLContext.deleteTexture （_id_）对当前设置环境。

**See also** [bindTexture](qglwidget.html#bindTexture)（ ） 。

```
QGLWidget.doneCurrent (self)
```

不作任何GL上下文的当前上下文。通常情况下，你不需要调用此函数;[QGLContext](qglcontext.html)调用它是必要的。然而，也可能是在多线程环境中是有用的。

```
bool QGLWidget.doubleBuffer (self)
```

返回True如果包含的GL渲染上下文具有双缓冲，否则返回False 。

**See also** [QGLFormat.doubleBuffer](qglformat.html#doubleBuffer)（ ） 。

```
QGLWidget.drawTexture (self, QRectF target, int textureId, int textureTarget = GL_TEXTURE_2D)
```

调用相应的[QGLContext.drawTexture](qglcontext.html#drawTexture)（ ）与_target_，_textureId_和_textureTarget_这个小工具的上下文。

此功能被引入Qt的4.4 。

```
QGLWidget.drawTexture (self, QPointF point, int textureId, int textureTarget = GL_TEXTURE_2D)
```

调用相应的[QGLContext.drawTexture](qglcontext.html#drawTexture)（ ）与_point_，_textureId_和_textureTarget_这个小工具的上下文。

此功能被引入Qt的4.4 。

```
bool QGLWidget.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QGLWidget.fontDisplayListBase (self, QFont font, int listBase = 2000)
```

```
QGLFormat QGLWidget.format (self)
```

[

返回所包含GL渲染上下文的格式。

](qglformat.html)

[**See also**](qglformat.html) [setFormat](index.htm#setFormat)（ ） 。

```
QGLWidget.glDraw (self)
```

执行虚拟函数[paintGL](qglwidget.html#paintGL)（ ） 。

窗口小部件的渲染上下文将成为当前上下文和[initializeGL](qglwidget.html#initializeGL)（） ，如果它尚未被称为将被调用。

```
QGLWidget.glInit (self)
```

OpenGL的初始化这个小工具的上下文。调用虚函数[initializeGL](qglwidget.html#initializeGL)（ ） 。

```
QImage QGLWidget.grabFrameBuffer (self, bool withAlpha = False)
```

[

返回帧缓冲器的图像。如果_withAlpha_是真正的alpha通道被包括在内。

根据您的硬件，就可以明确选择调用此函数之前用glReadBuffer （ ）调用抢的颜色缓冲区。

```
QGLWidget.initializeGL (self)
```

](qimage.html)

[在第一次调用之前，这个虚函数被调用一次](qimage.html)[paintGL](qglwidget.html#paintGL)（）或[resizeGL](qglwidget.html#resizeGL)（） ，然后一旦每当插件已被分配一个新[QGLContext](qglcontext.html)。重新实现它的一个子类。

这个功能应该设置任何所需的OpenGL上下文渲染标志，定义显示列表等。

有不需要调用[makeCurrent](qglwidget.html#makeCurrent)（ ），因为这已经完成时，此函数被调用。

```
QGLWidget.initializeOverlayGL (self)
```

这个虚拟函数用于以相同的方式作为[initializeGL](qglwidget.html#initializeGL)（）不同的是它运行在widget的复盖范围内，而不是widget的主要方面。这意味着， initializeOverlayGL （）的第一次调用之前被调用一次[paintOverlayGL](qglwidget.html#paintOverlayGL)（）或[resizeOverlayGL](qglwidget.html#resizeOverlayGL)（ ） 。重新实现它的一个子类。

这个功能应该设置任何所需的OpenGL上下文渲染标志，定义显示列表等的复盖范围内。

有不需要调用[makeOverlayCurrent](qglwidget.html#makeOverlayCurrent)（ ），因为这已经完成时，此函数被调用。

```
bool QGLWidget.isSharing (self)
```

返回True如果这个小工具的GL上下文与另一GL上下文共享，否则返回假。上下文共享可能不是可能的，如果小窗口使用不同的格式。

**See also** [format](qglwidget.html#format)（ ） 。

```
bool QGLWidget.isValid (self)
```

返回True如果部件有一个有效的GL渲染上下文，否则返回False 。一个widget将是无效的，如果系统没有[OpenGL support](qglformat.html#hasOpenGL)。

```
QGLWidget.makeCurrent (self)
```

使得这个小工具的当前部件的OpenGL操作，即让widget的渲染上下文当前的OpenGL渲染上下文。

```
QGLWidget.makeOverlayCurrent (self)
```

使得这个小部件电流的复盖范围内。如果你需要发出OpenGL命令来复盖上下文之外使用此[initializeOverlayGL](qglwidget.html#initializeOverlayGL)（ ）[resizeOverlayGL](qglwidget.html#resizeOverlayGL)（）和[paintOverlayGL](qglwidget.html#paintOverlayGL)（ ） 。

什么都不做，如果这个部件有没有重叠。

**See also** [makeCurrent](qglwidget.html#makeCurrent)（ ） 。

```
QGLContext QGLWidget.overlayContext (self)
```

[

返回这个窗口部件，或者0的复盖范围内，如果该部件有没有重叠。

](qglcontext.html)

[**See also**](qglcontext.html) [context](qglwidget.html#context)（ ） 。

```
QPaintEngine QGLWidget.paintEngine (self)
```

[

```
QGLWidget.paintEvent (self, QPaintEvent)
```

](qpaintengine.html)

[从重新实现](qpaintengine.html)[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

在处理传入的paint事件_event_参数。会导致虚拟[paintGL](qglwidget.html#paintGL)（ ）函数被调用。

窗口小部件的渲染上下文将成为当前上下文和[initializeGL](qglwidget.html#initializeGL)（） ，如果它尚未被称为将被调用。

```
QGLWidget.paintGL (self)
```

这个虚函数被调用时的小部件需要被重画。重新实现它的一个子类。

有不需要调用[makeCurrent](qglwidget.html#makeCurrent)（ ），因为这已经完成时，此函数被调用。

```
QGLWidget.paintOverlayGL (self)
```

这个虚拟函数用于以相同的方式作为[paintGL](qglwidget.html#paintGL)（）不同的是它运行在widget的复盖范围内，而不是widget的主要方面。这意味着， paintOverlayGL （）被调用每当widget的复盖需要被重画。重新实现它的一个子类。

有不需要调用[makeOverlayCurrent](qglwidget.html#makeOverlayCurrent)（ ），因为这已经完成时，此函数被调用。

```
QGLWidget.qglClearColor (self, QColor c)
```

便利功能用于指定清算颜色的OpenGL。调用glClearColor （在RGBA模式）或glClearIndex （在颜色索引模式）的颜色_c_。适用于本部件GL上下文。

**See also** [qglColor](qglwidget.html#qglColor)（ ）[QGLContext.currentContext](qglcontext.html#currentContext)（）和[QColor](qcolor.html)。

```
QGLWidget.qglColor (self, QColor c)
```

便利功能用于指定绘图颜色的OpenGL。调用glColor4 （在RGBA模式）或glIndex （在颜色索引模式）的颜色_c_。适用于本部件GL上下文。

**Note:**此功能不支持基于OpenGL / ES 2.0的系统。

**See also** [qglClearColor](qglwidget.html#qglClearColor)（ ）[QGLContext.currentContext](qglcontext.html#currentContext)（）和[QColor](qcolor.html)。

```
QPixmap QGLWidget.renderPixmap (self, int width = 0, int height = 0, bool useContext = False)
```

[

呈现在一个像素映射当前场景，并返回像素图。

](qpixmap.html)

[您可以在可见和不可见使用这种方法](qpixmap.html)[QGLWidget](qglwidget.html)对象。

这个方法将创建一个像素图和临时[QGLContext](qglcontext.html)渲染的像素图。然后，它会调用[initializeGL](qglwidget.html#initializeGL)（ ）[resizeGL](qglwidget.html#resizeGL)（）和[paintGL](qglwidget.html#paintGL)（ ）在这种情况下。最后，小部件的原GL上下文恢复。

像素图的大小将_w_像素宽和_h_像素高，除非这些参数中的一个为0 （缺省值） ，在这种情况下，像素映像将具有相同尺寸的窗口小部件。

If _useContext_诚然，这个方法会尝试使用现有的GL上下文来渲染像素图更有效率。默认值为False 。仅使用真实的，如果你理解了风险。注意，在Windows下的临时上下文必须创建和使用_useContext_不支持参数。

复盖不会呈现到像素图。

如果GL渲染上下文和桌面有不同的位深度，其结果很可能会看起来令人惊讶。

请注意，创建显示列表中，视锥等的修改应该从内完成[initializeGL](qglwidget.html#initializeGL)（ ） 。如果不这样做，则临时[QGLContext](qglcontext.html)将无法正确初始化，并且呈现像素图可能不完整/损坏。

```
QGLWidget.renderText (self, int x, int y, QString str, QFont font = QFont(), int listBase = 2000)
```

呈现的字符串_str_这个小部件的GL上下文。

_x_和_y_在窗口坐标被指定，在该窗口的上部左角的原点。如果_font_没有被指定，当前设置的应用程序的字体将被用来呈现字符串。要改变呈现的文本的颜色，你可以使用glColor （ ）调用（或[qglColor](qglwidget.html#qglColor)（ ）便利功能） ，只是renderText （ ）调用之前。

该_listBase_参数已过时，将在Qt的未来版本中删除。

**Note:**此功能清除模板缓冲区。

**Note:**此功能不支持基于OpenGL / ES系统。

**Note:**此功能暂时禁用深度测试时绘制文本。

**Note:**此功能只能在内部使用[QPainter.beginNativePainting](qpainter.html#beginNativePainting)（）/[QPainter.endNativePainting](qpainter.html#endNativePainting)（ ）块，如果默认的OpenGL绘图引擎是[QPaintEngine.OpenGL](qpaintengine.html#Type-enum)。为了使[QPaintEngine.OpenGL](qpaintengine.html#Type-enum)默认的GL引擎，调用QGL.setPreferredPaintEngine （[QPaintEngine.OpenGL](qpaintengine.html#Type-enum)）前[QApplication](qapplication.html)构造函数。

[Overpaint](index.htm)同[QPainter.drawText](qpainter.html#drawText)（ ）来代替。

```
QGLWidget.renderText (self, float x, float y, float z, QString str, QFont font = QFont(), int listBase = 2000)
```

这是一个重载函数。

_x_，_y_和_z_被指定的场景或物体坐标相对于当前设置的投影和模型矩阵。如果要标注模型与文本标籤，并在标籤移动的模式，因为它旋转等，这可能是有用的

**Note:**此功能不支持基于OpenGL / ES系统。

**Note:**如果深度测试启用此函数被调用之前，那么绘制的文本将深度测试对那些已经被绘制在场景中的模型。使用`glDisable(GL_DEPTH_TEST)`之前调用这个函数来注释的模型，而无需深度测试的文本。

[Overpaint](index.htm)同[QPainter.drawText](qpainter.html#drawText)（ ）来代替。

```
QGLWidget.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

手柄调整所传递的事件_event_参数。调用虚函数[resizeGL](qglwidget.html#resizeGL)（ ） 。

```
QGLWidget.resizeGL (self, int w, int h)
```

这个虚函数被调用时的小部件已调整大小。新的大小被传递_width_和_height_。重新实现它的一个子类。

有不需要调用[makeCurrent](qglwidget.html#makeCurrent)（ ），因为这已经完成时，此函数被调用。

```
QGLWidget.resizeOverlayGL (self, int w, int h)
```

这个虚拟函数用于以相同的方式作为[paintGL](qglwidget.html#paintGL)（）不同的是它运行在widget的复盖范围内，而不是widget的主要方面。这意味着， resizeOverlayGL （）被调用时的小部件已调整大小。新的大小被传递_width_和_height_。重新实现它的一个子类。

有不需要调用[makeOverlayCurrent](qglwidget.html#makeOverlayCurrent)（ ），因为这已经完成时，此函数被调用。

```
QGLWidget.setAutoBufferSwap (self, bool on)
```

If _on_是真正的自动GL缓冲交换被打开，否则将被关闭。

If _on_是真实和小部件是使用双缓冲格式，背景和前景GL缓冲区会自动在每个被交换[paintGL](qglwidget.html#paintGL)（ ）调用。

缓冲区自动交换是默认。

**See also** [autoBufferSwap](qglwidget.html#autoBufferSwap)（ ）[doubleBuffer](qglwidget.html#doubleBuffer)（）和[swapBuffers](qglwidget.html#swapBuffers)（ ） 。

```
QGLWidget.setColormap (self, QGLColormap map)
```

设置颜色映射这个小工具到_cmap_。通常它是一种可以安装有色彩映射表仅顶层窗口小部件。

**See also** [colormap](qglwidget.html#colormap)（ ） 。

```
QGLWidget.setContext (self, QGLContext context, QGLContext shareContext = None, bool deleteOldContext = True)
```

该_context_说法有它的所有权转移给Qt的。

```
QGLWidget.setFormat (self, QGLFormat format)
```

```
QGLWidget.setMouseTracking (self, bool enable)
```

If _enable_是真的，那么鼠标跟踪被启用，否则将被禁用。

```
QGLWidget.swapBuffers (self)
```

掉期，一个离屏缓冲屏幕内容。这只是工作，如果widget的格式指定双缓冲模式。

通常情况下，没有必要显式调用这个函数，因为它是每个插件重绘后自动完成的，即每个时间后，[paintGL](qglwidget.html#paintGL)（ ）已经执行。

**See also** [doubleBuffer](qglwidget.html#doubleBuffer)（ ）[setAutoBufferSwap](qglwidget.html#setAutoBufferSwap)（）和[QGLFormat.setDoubleBuffer](qglformat.html#setDoubleBuffer)（ ） 。

```
QGLWidget.updateGL (self)
```

这种方法也是一个Qt槽与C + +的签名`void updateGL()`。

通过调用更新微件[glDraw](qglwidget.html#glDraw)（ ） 。

```
QGLWidget.updateOverlayGL (self)
```

这种方法也是一个Qt槽与C + +的签名`void updateOverlayGL()`。

更新微件的叠加（如果有的话） 。会导致虚函数[paintOverlayGL](qglwidget.html#paintOverlayGL)（）被执行。

窗口小部件的渲染上下文将成为当前上下文和[initializeGL](qglwidget.html#initializeGL)（） ，如果它尚未被称为将被调用。