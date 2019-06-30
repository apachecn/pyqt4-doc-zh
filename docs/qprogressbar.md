# QProgressBar Class Reference

## [[QtGui](index.htm) module]

该QProgressBar部件提供水平或垂直进度条。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum Direction { TopToBottom, BottomToTop }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `Qt.Alignment alignment (self)`
*   `bool event (self, QEvent e)`
*   `QString format (self)`
*   `initStyleOption (self, QStyleOptionProgressBar option)`
*   `bool invertedAppearance (self)`
*   `bool isTextVisible (self)`
*   `int maximum (self)`
*   `int minimum (self)`
*   `QSize minimumSizeHint (self)`
*   `Qt.Orientation orientation (self)`
*   `paintEvent (self, QPaintEvent)`
*   `reset (self)`
*   `setAlignment (self, Qt.Alignment alignment)`
*   `setFormat (self, QString format)`
*   `setInvertedAppearance (self, bool invert)`
*   `setMaximum (self, int maximum)`
*   `setMinimum (self, int minimum)`
*   `setOrientation (self, Qt.Orientation)`
*   `setRange (self, int minimum, int maximum)`
*   `setTextDirection (self, Direction textDirection)`
*   `setTextVisible (self, bool visible)`
*   `setValue (self, int value)`
*   `QSize sizeHint (self)`
*   `QString text (self)`
*   `Direction textDirection (self)`
*   `int value (self)`

### Qt Signals

*   `void valueChanged (int)`

* * *

## Detailed Description

该QProgressBar部件提供水平或垂直进度条。

一个进度条是用来给用户的操作的进度指示，并安抚他们的应用程序仍在运行。

进度栏所使用的概念_steps_。你设置它通过指定最小和最大可能的步长值，它会显示的步骤已经完成的百分比，当你以后给它当前的步长值。该百分比除以进度计算（[value](qprogressbar.html#value-prop)（） - [minimum](qprogressbar.html#minimum-prop)（） ）除以[maximum](qprogressbar.html#maximum-prop)（） - [minimum](qprogressbar.html#minimum-prop)（ ） 。

您可以指定最小和最大步数与[setMinimum](qprogressbar.html#minimum-prop)（）和setMaximum 。的步骤的当前数量设置与[setValue](qprogressbar.html#value-prop)（ ） 。进度条可以倒到开头与[reset](qprogressbar.html#reset)（ ） 。

如果最小和最大两个都设置为0 ，指示条显示了一个忙閒指示，而不是步骤的百分比。使用时，这是有用的，例如，[QFtp](qftp.html) or [QNetworkAccessManager](qnetworkaccessmanager.html)下载项目时，他们无法确定正在下载的项目的大小。

| ![Screenshot of a Macintosh style progress bar](../img/macintosh-progressbar.png) | A progress bar shown in the Macintosh widget style. |
| ![Screenshot of a Windows XP style progress bar](../img/windowsxp-progressbar.png) | A progress bar shown in the Windows XP widget style. |
| ![Screenshot of a Plastique style progress bar](../img/plastique-progressbar.png) | A progress bar shown in the Plastique widget style. |

* * *

## Type Documentation

```
QProgressBar.Direction
```

指定的阅读方向[text](qprogressbar.html#text-prop)垂直进度条。

| Constant | Value | Description |
| --- | --- | --- |
| `QProgressBar.TopToBottom` | `0` | 该文本顺时针旋转90度。 |
| `QProgressBar.BottomToTop` | `1` | 文本逆时针旋转90度。 |

请注意，文字是否绘制取决于风格。目前CDE ， CleanLooks ，Motif和PLASTIQUE绘制文本。 Mac，Windows和WindowsXP的风格没有。

这个枚举被引入或修改的Qt 4.1 。

**See also** [textDirection](qprogressbar.html#textDirection-prop)。

* * *

## Method Documentation

```
QProgressBar.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个进度条给定的_parent_。

默认情况下，最小步长值被设置为0 ，最大值为100。

**See also** [setRange](qprogressbar.html#setRange)（ ） 。

```
Qt.Alignment QProgressBar.alignment (self)
```

[

```
bool QProgressBar.event (self, QEvent e)
```

](index.htm)

[从重新实现](index.htm)[QObject.event](qobject.html#event)（ ） 。

```
QString QProgressBar.format (self)
```

```
QProgressBar.initStyleOption (self, QStyleOptionProgressBar option)
```

初始化_option_与其它的值[QProgressBar](qprogressbar.html)。当他们需要一个这种方法是有用的子类[QStyleOptionProgressBar](qstyleoptionprogressbar.html) or [QStyleOptionProgressBarV2](qstyleoptionprogressbarv2.html)，但不希望在所有的信息填写自己。此功能将检查的版本[QStyleOptionProgressBar](qstyleoptionprogressbar.html)并填写了附加价值[QStyleOptionProgressBarV2](qstyleoptionprogressbarv2.html)。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
bool QProgressBar.invertedAppearance (self)
```

```
bool QProgressBar.isTextVisible (self)
```

```
int QProgressBar.maximum (self)
```

```
int QProgressBar.minimum (self)
```

```
QSize QProgressBar.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
Qt.Orientation QProgressBar.orientation (self)
```

[

```
QProgressBar.paintEvent (self, QPaintEvent)
```

](qt.html#Orientation-enum)

[从重新实现](qt.html#Orientation-enum)[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QProgressBar.reset (self)
```

这种方法也是一个Qt槽与C + +的签名`void reset()`。

重置进度条。进度条“倒带”，并表示没有任何进展。

```
QProgressBar.setAlignment (self, Qt.Alignment alignment)
```

```
QProgressBar.setFormat (self, QString format)
```

```
QProgressBar.setInvertedAppearance (self, bool invert)
```

```
QProgressBar.setMaximum (self, int maximum)
```

这种方法也是一个Qt槽与C + +的签名`void setMaximum(int)`。

```
QProgressBar.setMinimum (self, int minimum)
```

这种方法也是一个Qt槽与C + +的签名`void setMinimum(int)`。

```
QProgressBar.setOrientation (self, Qt.Orientation)
```

这种方法也是一个Qt槽与C + +的签名`void setOrientation(Qt::Orientation)`。

```
QProgressBar.setRange (self, int minimum, int maximum)
```

将进度条的最大值和最小值来_minimum_和_maximum_分别。

If _maximum_小于_minimum_，_minimum_成为唯一的合法值。

如果当前值超出了新的范围，进度条带复位[reset](qprogressbar.html#reset)（ ） 。

**See also** [minimum](qprogressbar.html#minimum-prop)和[maximum](qprogressbar.html#maximum-prop)。

```
QProgressBar.setTextDirection (self, Direction textDirection)
```

```
QProgressBar.setTextVisible (self, bool visible)
```

```
QProgressBar.setValue (self, int value)
```

这种方法也是一个Qt槽与C + +的签名`void setValue(int)`。

```
QSize QProgressBar.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QString QProgressBar.text (self)
```

```
Direction QProgressBar.textDirection (self)
```

[

```
int QProgressBar.value (self)
```

* * *

## Qt Signal Documentation

```
void valueChanged (int)
```

这是该信号的默认超载。

当进度条改变显示的值这个信号被发射。_value_是通过进度条显示的新值。

](qprogressbar.html#Direction-enum)