# QDial Class Reference

## [[QtGui](index.htm) module]

该QDial类提供了一个圆形范围控制（如速度计或电位器） 。[More...](#details)

继承[QAbstractSlider](qabstractslider.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `bool event (self, QEvent e)`
*   `initStyleOption (self, QStyleOptionSlider option)`
*   `QSize minimumSizeHint (self)`
*   `mouseMoveEvent (self, QMouseEvent me)`
*   `mousePressEvent (self, QMouseEvent me)`
*   `mouseReleaseEvent (self, QMouseEvent me)`
*   `bool notchesVisible (self)`
*   `int notchSize (self)`
*   `float notchTarget (self)`
*   `paintEvent (self, QPaintEvent pe)`
*   `resizeEvent (self, QResizeEvent re)`
*   `setNotchesVisible (self, bool visible)`
*   `setNotchTarget (self, float target)`
*   `setWrapping (self, bool on)`
*   `QSize sizeHint (self)`
*   `sliderChange (self, QAbstractSlider.SliderChange change)`
*   `bool wrapping (self)`

* * *

## Detailed Description

该QDial类提供了一个圆形范围控制（如速度计或电位器） 。

当用户需要的程序可定义的范围内控制值QDial被使用，并且该范围内任一环绕（例如，具有测量从0到359度的角度）或对话框布局需要一个方形小部件。

由于QDial从继承[QAbstractSlider](qabstractslider.html)，表盘的行为以类似的方式，以一[slider](qslider.html)。何时[wrapping](qdial.html#wrapping-prop)（ ）为False（默认设置）有一个滑块和转盘之间没有真正的区别。他们都有着相同的信号，槽和成员函数。哪一个你使用依赖于你的用户的期望和对应用程序的类型。

表盘最初发出[valueChanged](qabstractslider.html#valueChanged)（ ）连续信号，同时将滑块移动，你可以把它通过禁用不经常发出的信号[tracking](qabstractslider.html#tracking-prop)属性。该[sliderMoved](qabstractslider.html#sliderMoved)（ ）信号被连续发射，即使跟踪被禁用。

表盘还发出[sliderPressed](qabstractslider.html#sliderPressed)（）和[sliderReleased](qabstractslider.html#sliderReleased)（ ）信号，当鼠标按钮被按下和释放。注意，在表盘的值可以改变而不被发射的这些信号，因为键盘和轮也可用于改变该值。

不同的是滑块， QDial试图画出一个“好”若干缺口，而不是每行一步。如果可能的话，吸入槽口的数量是每行的步骤1 ，但如果没有足够的像素绘制的每一个， QDial将跳过缺口，试图绘制均匀的组（例如，通过绘制每第二个或第三个缺口） 。

像滑块，拨盘使[QAbstractSlider](qabstractslider.html) functions [setValue](qabstractslider.html#value-prop)（ ）[addLine](index.htm#addLine)（ ）[subtractLine](index.htm#subtractLine)（ ）[addPage](index.htm#addPage)（）和[subtractPage](index.htm#subtractPage)（ ）可作为插槽。

拨号键盘界面相当简单：**left**/**up**和**right**/**down**箭头键调整拨号的[value](qabstractslider.html#value-prop)由定义[singleStep](qabstractslider.html#singleStep-prop)，**Page Up**和**Page Down**由定义[pageStep](qabstractslider.html#pageStep-prop)和**Home**和**End**键的值设置为所定义的[minimum](qabstractslider.html#minimum-prop)和[maximum](qabstractslider.html#maximum-prop)值。

如果您使用鼠标滚轮来调整拨号，增量值由较小值确定[wheelScrollLines](qapplication.html#wheelScrollLines-prop)由multipled[singleStep](qabstractslider.html#singleStep-prop)和[pageStep](qabstractslider.html#pageStep-prop)。

| ![Screenshot of a dial in the Plastique widget style](../img/plastique-dial.png) | ![Screenshot of a dial in the Windows XP widget style](../img/windowsxp-dial.png) | ![Screenshot of a dial in the Macintosh widget style](../img/macintosh-dial.png) |
| Dials shown in various widget styles (from left to right): [Plastique](index.htm), [Windows XP](index.htm), [Macintosh](index.htm). |

* * *

## Method Documentation

```
QDial.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个拨号。

该_parent_参数被发送到[QAbstractSlider](qabstractslider.html)构造函数。

```
bool QDial.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QDial.initStyleOption (self, QStyleOptionSlider option)
```

初始化_option_与其它的值[QDial](qdial.html)。当他们需要一个这种方法是有用的子类[QStyleOptionSlider](qstyleoptionslider.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QSize QDial.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QDial.mouseMoveEvent (self, QMouseEvent me)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QDial.mousePressEvent (self, QMouseEvent me)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QDial.mouseReleaseEvent (self, QMouseEvent me)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
bool QDial.notchesVisible (self)
```

```
int QDial.notchSize (self)
```

```
float QDial.notchTarget (self)
```

```
QDial.paintEvent (self, QPaintEvent pe)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QDial.resizeEvent (self, QResizeEvent re)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QDial.setNotchesVisible (self, bool visible)
```

这种方法也是一个Qt槽与C + +的签名`void setNotchesVisible(bool)`。

```
QDial.setNotchTarget (self, float target)
```

```
QDial.setWrapping (self, bool on)
```

这种方法也是一个Qt槽与C + +的签名`void setWrapping(bool)`。

```
QSize QDial.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QDial.sliderChange (self, QAbstractSlider.SliderChange change)
```

从重新实现[QAbstractSlider.sliderChange](qabstractslider.html#sliderChange)（ ） 。

```
bool QDial.wrapping (self)
```