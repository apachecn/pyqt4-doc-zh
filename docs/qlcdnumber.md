# QLCDNumber Class Reference

## [[QtGui](index.htm) module]

该QLCDNumber插件播放带有LCD一样数字的号码。[More...](#details)

继承[QFrame](qframe.html)。

### Types

*   `enum Mode { Hex, Dec, Oct, Bin }`
*   `enum SegmentStyle { Outline, Filled, Flat }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, int numDigits, QWidget parent = None)`
*   `bool checkOverflow (self, float num)`
*   `bool checkOverflow (self, int num)`
*   `int digitCount (self)`
*   `display (self, QString str)`
*   `display (self, float num)`
*   `display (self, int num)`
*   `bool event (self, QEvent e)`
*   `int intValue (self)`
*   `Mode mode (self)`
*   `int numDigits (self)`
*   `paintEvent (self, QPaintEvent)`
*   `SegmentStyle segmentStyle (self)`
*   `setBinMode (self)`
*   `setDecMode (self)`
*   `setDigitCount (self, int nDigits)`
*   `setHexMode (self)`
*   `setMode (self, Mode)`
*   `setNumDigits (self, int nDigits)`
*   `setOctMode (self)`
*   `setSegmentStyle (self, SegmentStyle)`
*   `setSmallDecimalPoint (self, bool)`
*   `QSize sizeHint (self)`
*   `bool smallDecimalPoint (self)`
*   `float value (self)`

### Qt Signals

*   `void overflow ()`

* * *

## Detailed Description

该QLCDNumber插件播放带有LCD一样数字的号码。

它可以在几乎任何大小显示的数字。它可以显示十进制，十六进制，八进制或二进制数。这是很容易使用连接到数据源[display](qlcdnumber.html#intValue-prop)（）槽，这是重载采取任何五个参数类型。

也有槽，以改变基[setMode](qlcdnumber.html#mode-prop)（）和小数点用[setSmallDecimalPoint](qlcdnumber.html#smallDecimalPoint-prop)（ ） 。

QLCDNumber放出[overflow](qlcdnumber.html#overflow)（）信号，当它被要求显示一些超出其范围。的范围被设置[setDigitCount](qlcdnumber.html#digitCount-prop)（），但[setSmallDecimalPoint](qlcdnumber.html#smallDecimalPoint-prop)（ ）也会影响它。如果显示器被设置为十六进制，八进制或二进制，则显示的整数的价值。

这些数字和其他符号可以证明： 0 / O ， 1 ， 2 ， 3 ， 4 ， 5 / S， 6 ， 7 ， 8 ， 9 /克，减，小数点， A，B， C， D，E ， F，H ， H，L ， O，P ， R，U ， U，Y ，结肠癌，度数符号（它被指定为字符串中的单引号）和空间。 QLCDNumber用于替换非法字符空格。

这是不可能的检索QLCDNumber对象的内容，虽然可以用获取的数值[value](qlcdnumber.html#value-prop)（ ） 。如果你真的需要的文本，我们建议您连接的饲料的信号[display](qlcdnumber.html#intValue-prop)（ ）插槽移到另一个插槽，以及与存储该值在那里。

顺便说一句， QLCDNumber是对Qt的非常古老的部分，追踪它的历史可以追溯到上一个BASIC程序 [Sinclair Spectrum](http://www.nvg.ntnu.no/sinclair/computers/zxspectrum/zxspectrum.htm)。

| ![Screenshot of a Motif style LCD number widget](../img/motif-lcdnumber.png) ![Screenshot of a CDE style LCD number widget](../img/cde-lcdnumber.png) ![Screenshot of a Windows style LCD number widget](../img/windows-lcdnumber.png) ![Screenshot of a Windows XP style LCD number widget](../img/windowsxp-lcdnumber.png) ![Screenshot of a Macintosh style LCD number widget](../img/macintosh-lcdnumber.png) ![Screenshot of a Plastique style LCD number widget](../img/plastique-lcdnumber.png) |
| LCD number widgets shown in various widget styles (from left to right): [Motif](index.htm), [CDE](index.htm), [Windows](index.htm), [Windows XP](index.htm), [Macintosh](index.htm), [Plastique](index.htm). |

* * *

## Type Documentation

```
QLCDNumber.Mode
```

这种类型决定了数字显示。

| Constant | Value | Description |
| --- | --- | --- |
| `QLCDNumber.Hex` | `0` | 十六进制 |
| `QLCDNumber.Dec` | `1` | 十进制 |
| `QLCDNumber.Oct` | `2` | 八进制 |
| `QLCDNumber.Bin` | `3` | 二进制 |

如果显示器被设置为十六进制，八进制或二进制，则显示的整数的价值。

```
QLCDNumber.SegmentStyle
```

这种类型的确定的视觉外观[QLCDNumber](qlcdnumber.html)小工具。

| Constant | Value | Description |
| --- | --- | --- |
| `QLCDNumber.Outline` | `0` | 给出升高的部段填充的背景色。 |
| `QLCDNumber.Filled` | `1` | 让凸起部分填充有WindowText的颜色。 |
| `QLCDNumber.Flat` | `2` | 给出的平直段填充有WindowText的颜色。 |

* * *

## Method Documentation

```
QLCDNumber.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个液晶数，设置的位数为5，底座为十进制，小数点模式，以“小”和框架风格，凸起的方块。该[segmentStyle](qlcdnumber.html#segmentStyle-prop)（ ）被设置为`Outline`。

该_parent_参数被传递到[QFrame](qframe.html)构造函数。

**See also** [setDigitCount](qlcdnumber.html#digitCount-prop)（）和[setSmallDecimalPoint](qlcdnumber.html#smallDecimalPoint-prop)（ ） 。

```
QLCDNumber.__init__ (self, int numDigits, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个液晶数，设定的位数来_numDigits_，基地为十进制，小数点模式，以“小”和框架风格，凸起的方块。该[segmentStyle](qlcdnumber.html#segmentStyle-prop)（ ）被设置为`Filled`。

该_parent_参数被传递到[QFrame](qframe.html)构造函数。

**See also** [setDigitCount](qlcdnumber.html#digitCount-prop)（）和[setSmallDecimalPoint](qlcdnumber.html#smallDecimalPoint-prop)（ ） 。

```
bool QLCDNumber.checkOverflow (self, float num)
```

返回True如果_num_太大，会显示整，否则返回False 。

**See also** [display](qlcdnumber.html#intValue-prop)（ ）[digitCount](qlcdnumber.html#digitCount-prop)（）和[smallDecimalPoint](qlcdnumber.html#smallDecimalPoint-prop)（ ） 。

```
bool QLCDNumber.checkOverflow (self, int num)
```

这是一个重载函数。

返回True如果_num_太大，会显示整，否则返回False 。

**See also** [display](qlcdnumber.html#intValue-prop)（ ）[digitCount](qlcdnumber.html#digitCount-prop)（）和[smallDecimalPoint](qlcdnumber.html#smallDecimalPoint-prop)（ ） 。

```
int QLCDNumber.digitCount (self)
```

```
QLCDNumber.display (self, QString str)
```

```
QLCDNumber.display (self, float num)
```

```
QLCDNumber.display (self, int num)
```

```
bool QLCDNumber.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QLCDNumber.intValue (self)
```

```
Mode QLCDNumber.mode (self)
```

[

```
int QLCDNumber.numDigits (self)
```

```
QLCDNumber.paintEvent (self, QPaintEvent)
```

](qlcdnumber.html#Mode-enum)

[从重新实现](qlcdnumber.html#Mode-enum)[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
SegmentStyle QLCDNumber.segmentStyle (self)
```

[

```
QLCDNumber.setBinMode (self)
```

调用调用setMode （ BIN） 。提供了方便（例如，用于连接按钮吧） 。

](qlcdnumber.html#SegmentStyle-enum)

[**See also**](qlcdnumber.html#SegmentStyle-enum) [setMode](qlcdnumber.html#mode-prop)（ ）[setHexMode](qlcdnumber.html#setHexMode)（ ）[setDecMode](qlcdnumber.html#setDecMode)（ ）[setOctMode](qlcdnumber.html#setOctMode)（）和[mode](qlcdnumber.html#mode-prop)（ ） 。

```
QLCDNumber.setDecMode (self)
```

调用调用setMode （十二月） 。提供了方便（例如，用于连接按钮吧） 。

**See also** [setMode](qlcdnumber.html#mode-prop)（ ）[setHexMode](qlcdnumber.html#setHexMode)（ ）[setOctMode](qlcdnumber.html#setOctMode)（ ）[setBinMode](qlcdnumber.html#setBinMode)（）和[mode](qlcdnumber.html#mode-prop)（ ） 。

```
QLCDNumber.setDigitCount (self, int nDigits)
```

```
QLCDNumber.setHexMode (self)
```

调用调用setMode （十六进制） 。提供了方便（例如，用于连接按钮吧） 。

**See also** [setMode](qlcdnumber.html#mode-prop)（ ）[setDecMode](qlcdnumber.html#setDecMode)（ ）[setOctMode](qlcdnumber.html#setOctMode)（ ）[setBinMode](qlcdnumber.html#setBinMode)（）和[mode](qlcdnumber.html#mode-prop)（ ） 。

```
QLCDNumber.setMode (self, Mode)
```

```
QLCDNumber.setNumDigits (self, int nDigits)
```

```
QLCDNumber.setOctMode (self)
```

调用调用setMode （十月） 。提供了方便（例如，用于连接按钮吧） 。

**See also** [setMode](qlcdnumber.html#mode-prop)（ ）[setHexMode](qlcdnumber.html#setHexMode)（ ）[setDecMode](qlcdnumber.html#setDecMode)（ ）[setBinMode](qlcdnumber.html#setBinMode)（）和[mode](qlcdnumber.html#mode-prop)（ ） 。

```
QLCDNumber.setSegmentStyle (self, SegmentStyle)
```

```
QLCDNumber.setSmallDecimalPoint (self, bool)
```

```
QSize QLCDNumber.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
bool QLCDNumber.smallDecimalPoint (self)
```

```
float QLCDNumber.value (self)
```

* * *

## Qt Signal Documentation

```
void overflow ()
```

这是该信号的默认超载。

这个信号被发射时的[QLCDNumber](qlcdnumber.html)被要求显示一个太大的数字或过长的字符串。

这是从来没有发出[setDigitCount](qlcdnumber.html#digitCount-prop)（ ） 。