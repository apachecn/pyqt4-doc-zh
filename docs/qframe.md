# QFrame Class Reference

## [[QtGui](index.htm) module]

该QFrame类是基类的小部件，可以有一个框架。[More...](#details)

继承[QWidget](qwidget.html)。

通过继承[QAbstractScrollArea](qabstractscrollarea.html)，[QLabel](qlabel.html)，[QLCDNumber](qlcdnumber.html)，[QSplitter](qsplitter.html)，[QStackedWidget](qstackedwidget.html)和[QToolBox](qtoolbox.html)。

### Types

*   `enum Shadow { Plain, Raised, Sunken }`
*   `enum Shape { NoFrame, Box, Panel, WinPanel, ..., StyledPanel }`
*   `enum StyleMask { Shadow_Mask, Shape_Mask }`

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `changeEvent (self, QEvent)`
*   `drawFrame (self, QPainter)`
*   `bool event (self, QEvent e)`
*   `QRect frameRect (self)`
*   `Shadow frameShadow (self)`
*   `Shape frameShape (self)`
*   `int frameStyle (self)`
*   `int frameWidth (self)`
*   `int lineWidth (self)`
*   `int midLineWidth (self)`
*   `paintEvent (self, QPaintEvent)`
*   `setFrameRect (self, QRect)`
*   `setFrameShadow (self, Shadow)`
*   `setFrameShape (self, Shape)`
*   `setFrameStyle (self, int)`
*   `setLineWidth (self, int)`
*   `setMidLineWidth (self, int)`
*   `QSize sizeHint (self)`

* * *

## Detailed Description

该QFrame类是基类的小部件，可以有一个框架。

[QMenu](qmenu.html)使用它来“养”周围的屏幕上方的菜单。[QProgressBar](qprogressbar.html)有一个“沉没”的样子。[QLabel](qlabel.html)具有平坦的外观。像这样的小部件的帧可以被改变。

```
 [QLabel](qlabel.html) label(...);
 label.setFrameStyle(QFrame.Panel | QFrame.Raised);
 label.setLineWidth(2);

 [QProgressBar](qprogressbar.html) pbar(...);
 label.setFrameStyle(QFrame.NoFrame);

```

该QFrame类也可以直接使用，无需任何内容创建简单的佔位符框架。

边框样式是由一个指定的[frame shape](qframe.html#Shape-enum)和[shadow style](qframe.html#Shadow-enum)是，用于在视觉上的帧从周围的部件中分离出来。这些属性可以设置一起使用[setFrameStyle](qframe.html#setFrameStyle)（）函数和读取[frameStyle](qframe.html#frameStyle)（ ） 。

该框架形状[NoFrame](qframe.html#Shape-enum)，[Box](qframe.html#Shape-enum)，[Panel](qframe.html#Shape-enum)，[StyledPanel](qframe.html#Shape-enum)，[HLine](qframe.html#Shape-enum)和[VLine](qframe.html#Shape-enum);阴影样式[Plain](qframe.html#Shadow-enum)，[Raised](qframe.html#Shadow-enum)和[Sunken](qframe.html#Shadow-enum)。

一帧小部件都有描述边框的厚度三个属性：[lineWidth](qframe.html#lineWidth-prop)，[midLineWidth](qframe.html#midLineWidth-prop)和[frameWidth](qframe.html#frameWidth-prop)。

*   The line width is the width of the frame border. It can be modified to customize the frame's appearance.
*   The mid-line width specifies the width of an extra line in the middle of the frame, which uses a third color to obtain a special 3D effect. Notice that a mid-line is only drawn for [Box](qframe.html#Shape-enum), [HLine](qframe.html#Shape-enum) and [VLine](qframe.html#Shape-enum) frames that are raised or sunken.
*   The frame width is determined by the frame style, and the [frameWidth](qframe.html#frameWidth-prop)() function is used to obtain the value defined for the style used.

该帧的帧和内容之间的边缘可以与被定制[QWidget.setContentsMargins](qwidget.html#setContentsMargins)（）函数。

该表显示了一些款式和线宽的组合：

![Table of frame styles](../img/frames.png)

* * *

## Type Documentation

```
QFrame.Shadow
```

该枚举类型定义了用于给一个3D效果的帧阴影的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QFrame.Plain` | `0x0010` | 框架和内容，出现与周围环境水平;绘制使用的调色板[QPalette.WindowText](qpalette.html#ColorRole-enum)颜色（无任何3D效果） |
| `QFrame.Raised` | `0x0020` | 框架和内容出现上调;使用当前颜色组的光与暗的颜色绘制3D凸起线 |
| `QFrame.Sunken` | `0x0030` | 框架和内容出现凹陷，使用当前颜色组的光与暗的颜色绘制一个三维线沉没 |

阴影交互[QFrame.Shape](qframe.html#Shape-enum)时，[lineWidth](qframe.html#lineWidth-prop)（ ）和[midLineWidth](qframe.html#midLineWidth-prop)（ ） 。看到在主类文件的帧的图片。

**See also** [QFrame.Shape](qframe.html#Shape-enum)，[lineWidth](qframe.html#lineWidth-prop)（）和[midLineWidth](qframe.html#midLineWidth-prop)（ ） 。

```
QFrame.Shape
```

这个枚举类型定义框架提供的形状。

| Constant | Value | Description |
| --- | --- | --- |
| `QFrame.NoFrame` | `0` | [QFrame](qframe.html)借鉴什么 |
| `QFrame.Box` | `0x0001` | [QFrame](qframe.html)周围绘制其内容的盒子 |
| `QFrame.Panel` | `0x0002` | [QFrame](qframe.html)绘制一个面板，使内容出现凸起或凹陷 |
| `QFrame.StyledPanel` | `0x0006` | 绘制一个矩形面板，一看就是取决于当前图形用户界面风格。它可以凸起或凹陷。 |
| `QFrame.HLine` | `0x0004` | [QFrame](qframe.html)绘制一条水平线，没有帧（作为分隔符有用） |
| `QFrame.VLine` | `0x0005` | [QFrame](qframe.html)绘制了框架没有一条垂直线（如分离器很有用） |
| `QFrame.WinPanel` | `0x0003` | 绘制一个矩形面板可以凸起或凹陷的像那些在Windows 2000。指定此形状设置线宽为2像素。 WinPanel提供了一种用于兼容性。对于GUI风格的独立性，我们建议使用StyledPanel代替。 |

当它不叫[QStyle](qstyle.html)，外形与互动[QFrame.Shadow](qframe.html#Shadow-enum)时，[lineWidth](qframe.html#lineWidth-prop)（ ）和[midLineWidth](qframe.html#midLineWidth-prop)（ ）创建的总成绩。看到在主类文件的帧的图片。

**See also** [QFrame.Shadow](qframe.html#Shadow-enum)，[QFrame.style](qwidget.html#style)（）和[QStyle.drawPrimitive](qstyle.html#drawPrimitive)（ ） 。

```
QFrame.StyleMask
```

该枚举定义了可以用来提取的两个组成部分的两个常数[frameStyle](qframe.html#frameStyle)（）：

| Constant | Value | Description |
| --- | --- | --- |
| `QFrame.Shadow_Mask` | `0x00f0` | 该[Shadow](qframe.html#Shadow-enum)的一部分[frameStyle](qframe.html#frameStyle)（ ） |
| `QFrame.Shape_Mask` | `0x000f` | 该[Shape](qframe.html#Shape-enum)的一部分[frameStyle](qframe.html#frameStyle)（ ） |

通常情况下，你并不需要使用这些，因为[frameShadow](qframe.html#frameShadow-prop)（）和[frameShape](qframe.html#frameShape-prop)（ ）已提取[Shadow](qframe.html#Shadow-enum)和[Shape](qframe.html#Shape-enum)部分[frameStyle](qframe.html#frameStyle)（ ） 。

**See also** [frameStyle](qframe.html#frameStyle)（）和[setFrameStyle](qframe.html#setFrameStyle)（ ） 。

* * *

## Method Documentation

```
QFrame.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个框架部件与框架样式[NoFrame](qframe.html#Shape-enum)和一个1像素边框宽度。

该_parent_和_f_参数被传递到[QWidget](qwidget.html)构造函数。

```
QFrame.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QFrame.drawFrame (self, QPainter)
```

```
bool QFrame.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QRect QFrame.frameRect (self)
```

[](qrect.html)

```
Shadow QFrame.frameShadow (self)
```

[](qframe.html#Shadow-enum)

```
Shape QFrame.frameShape (self)
```

[

```
int QFrame.frameStyle (self)
```

返回框架风格。

](qframe.html#Shape-enum)

[缺省值是](qframe.html#Shape-enum)[QFrame.Plain](qframe.html#Shadow-enum)。

**See also** [setFrameStyle](qframe.html#setFrameStyle)（ ）[frameShape](qframe.html#frameShape-prop)（）和[frameShadow](qframe.html#frameShadow-prop)（ ） 。

```
int QFrame.frameWidth (self)
```

```
int QFrame.lineWidth (self)
```

```
int QFrame.midLineWidth (self)
```

```
QFrame.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QFrame.setFrameRect (self, QRect)
```

```
QFrame.setFrameShadow (self, Shadow)
```

```
QFrame.setFrameShape (self, Shape)
```

```
QFrame.setFrameStyle (self, int)
```

设置框架样式_style_。

该_style_是按位或一个框的形状和框架阴影样式之间。看到在主类文件的帧的图片。

在框架形状在给定的[QFrame.Shape](qframe.html#Shape-enum)并且在阴影样式[QFrame.Shadow](qframe.html#Shadow-enum)。

如果一个中等宽度小于指定0越大，附加线的绘制[Raised](qframe.html#Shadow-enum) or [Sunken](qframe.html#Shadow-enum) [Box](qframe.html#Shape-enum)，[HLine](qframe.html#Shape-enum)和[VLine](qframe.html#Shape-enum)帧。当前颜色组的中间色用于绘制中间线。

**See also** [frameStyle](qframe.html#frameStyle)（ ） 。

```
QFrame.setLineWidth (self, int)
```

```
QFrame.setMidLineWidth (self, int)
```

```
QSize QFrame.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。