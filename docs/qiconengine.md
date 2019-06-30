# QIconEngine Class Reference

## [[QtGui](index.htm) module]

该QIconEngine类提供了一个抽象基类[QIcon](qicon.html)渲染器。[More...](#details)

通过继承[QIconEngineV2](qiconenginev2.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIconEngine)`
*   `QSize actualSize (self, QSize size, QIcon.Mode mode, QIcon.State state)`
*   `addFile (self, QString fileName, QSize size, QIcon.Mode mode, QIcon.State state)`
*   `addPixmap (self, QPixmap pixmap, QIcon.Mode mode, QIcon.State state)`
*   `paint (self, QPainter painter, QRect rect, QIcon.Mode mode, QIcon.State state)`
*   `QPixmap pixmap (self, QSize size, QIcon.Mode mode, QIcon.State state)`

* * *

## Detailed Description

该QIconEngine类提供了一个抽象基类[QIcon](qicon.html)渲染器。

**Use [QIconEngineV2](qiconenginev2.html) instead.**

图标引擎提供的渲染功能，适用于[QIcon](qicon.html)。每个图标都有一个对应的图标引擎负责与所请求的大小，模式和状态绘制的图标。

该图标被渲染[paint](qiconengine.html#paint)（）函数，并且该图标可以另外作为与一个像素映射得到的[pixmap](qiconengine.html#pixmap)（ ）函数（默认的实现仅使用[paint](qiconengine.html#paint)（ ）来实现这一点） 。该[addPixmap](qiconengine.html#addPixmap)（）函数可用于新的像素映射添加到图标发动机，并用于通过[QIcon](qicon.html)添加专门定制的像素图。

该[paint](qiconengine.html#paint)（ ）[pixmap](qiconengine.html#pixmap)（）和[addPixmap](qiconengine.html#addPixmap)（ ）函数都是虚拟的，因此可以在QIconEngine的子类重新实现。

* * *

## Method Documentation

```
QIconEngine.__init__ (self)
```

```
QIconEngine.__init__ (self, QIconEngine)
```

```
QSize QIconEngine.actualSize (self, QSize size, QIcon.Mode mode, QIcon.State state)
```

[

返回该引擎提供所请求的图标的实际尺寸_size_，_mode_和_state_。默认实现返回给定_size_。

```
QIconEngine.addFile (self, QString fileName, QSize size, QIcon.Mode mode, QIcon.State state)
```

](qsize.html)

[通过所谓的](qsize.html)[QIcon.addFile](qicon.html#addFile)（ ） 。增加了一个专门的像素图从文件中给定的_fileName_，_size_，_mode_和_state_。默认的像素映射为基础的存储引擎提供的任何文件名，并将其加载，而不是使用缩放像素图，如果一个像素图的大小图标的要求的尺寸相匹配的需求上的像素图。实现可缩放的矢量格式自定义图标的引擎可以自由地忽略任何额外的文件。

```
QIconEngine.addPixmap (self, QPixmap pixmap, QIcon.Mode mode, QIcon.State state)
```

通过所谓的[QIcon.addPixmap](qicon.html#addPixmap)（ ） 。增加了一个专门的_pixmap_对于给定的_mode_和_state_。默认的像素映射为基础的存储引擎提供的任何像素图，并使用他们，而不是缩放的像素图，如果一个像素图的大小图标的要求的尺寸相匹配。实现可缩放的矢量格式自定义图标的引擎可以自由地忽略任何额外的像素图。

```
QIconEngine.paint (self, QPainter painter, QRect rect, QIcon.Mode mode, QIcon.State state)
```

这种方法是抽象的，应在任何子类中重新实现。

使用给定的_painter_绘制图标与所需_mode_和_state_成长方形_rect_。

```
QPixmap QIconEngine.pixmap (self, QSize size, QIcon.Mode mode, QIcon.State state)
```

[](qpixmap.html)

[返回图标与所需的像素图_size_，_mode_和_state_。默认实现创建一个新的像素映射和调用](qpixmap.html)[paint](qiconengine.html#paint)（）来填充它。