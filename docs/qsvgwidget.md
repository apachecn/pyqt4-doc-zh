# QSvgWidget Class Reference

## [[QtSvg](index.htm) module]

该QSvgWidget类提供了用于显示可缩放矢量图形（SVG ）文件的内容一个小部件。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QString file, QWidget parent = None)`
*   `load (self, QString file)`
*   `load (self, QByteArray contents)`
*   `paintEvent (self, QPaintEvent event)`
*   `QSvgRenderer renderer (self)`
*   `QSize sizeHint (self)`

* * *

## Detailed Description

该QSvgWidget类提供了用于显示可缩放矢量图形（SVG ）文件的内容一个小部件。

这个类使开发人员能够显示SVG图形旁边标准的部件，用于在大致相同的方式为[QLabel](qlabel.html)用于显示文本和位图图像。

因为QSvgWidget是的一个子类[QWidget](qwidget.html)，SVG图纸所使用的显示器的特性呈现。更多的控制可以在渲染过程中的行使[QSvgRenderer](qsvgrenderer.html)类，因为这可以用来作画到其他绘图设备，如[QImage](qimage.html)和[QGLWidget](qglwidget.html)。可以用以下方式获得所使用的插件的渲染[renderer](qsvgwidget.html#renderer)（）函数。

每个QSvgWidget可以用SVG文件的文件名构成，或者它们可以在没有一个特定的文件，以使被构造和一个可以在以后提供。该[load](qsvgwidget.html#load)（ ）函数提供了两种不同的方式来加载一个SVG文件：他们接受一个SVG文件或任一文件名[QByteArray](qbytearray.html)包含SVG文件的序列化的XML表示形式。

默认情况下，窗口小部件提供了一个尺寸暗示以反映它显示图形的大小。如果没有数据被加载时，窗口小部件提供默认[QWidget](qwidget.html)尺寸暗示。继承这个类，并重新实现[sizeHint](qsvgwidget.html#sizeHint)（ ）如果你需要自定义此行为。

* * *

## Method Documentation

```
QSvgWidget.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的SVG显示小部件与给定_parent_。

```
QSvgWidget.__init__ (self, QString file, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的SVG显示小部件与给定_parent_并加载指定的内容_file_。

```
QSvgWidget.load (self, QString file)
```

这种方法也是一个Qt槽与C + +的签名`void load(const QString&)`。

加载指定的SVG内容_file_和更新部件。

```
QSvgWidget.load (self, QByteArray contents)
```

这种方法也是一个Qt槽与C + +的签名`void load(const QByteArray&)`。

加载指定的SVG格式_contents_和更新部件。

```
QSvgWidget.paintEvent (self, QPaintEvent event)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QSvgRenderer QSvgWidget.renderer (self)
```

[

返回用于显示widget的内容的渲染。

](qsvgrenderer.html)

```
QSize QSvgWidget.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。