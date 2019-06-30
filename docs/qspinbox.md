# QSpinBox Class Reference

## [[QtGui](index.htm) module]

该QSpinBox类提供了一个微调框控件。[More...](#details)

继承[QAbstractSpinBox](qabstractspinbox.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `QString cleanText (self)`
*   `bool event (self, QEvent e)`
*   `QString str fixup (self, QString str)`
*   `fixup (self, QString str)`
*   `int maximum (self)`
*   `int minimum (self)`
*   `QString prefix (self)`
*   `setMaximum (self, int max)`
*   `setMinimum (self, int min)`
*   `setPrefix (self, QString p)`
*   `setRange (self, int min, int max)`
*   `setSingleStep (self, int val)`
*   `setSuffix (self, QString s)`
*   `setValue (self, int val)`
*   `int singleStep (self)`
*   `QString suffix (self)`
*   `QString textFromValue (self, int v)`
*   `(QValidator.State, QString input, int pos) validate (self, QString input, int pos)`
*   `(QValidator.State, int pos) validate (self, QString input, int pos)`
*   `int value (self)`
*   `int valueFromText (self, QString text)`

### Qt Signals

*   `void valueChanged (int)`
*   `void valueChanged (const QString&)`

* * *

## Detailed Description

该QSpinBox类提供了一个微调框控件。

QSpinBox是专门用来处理整数和值（例如，月份名称）的离散套;使用[QDoubleSpinBox](qdoublespinbox.html)浮点值。

QSpinBox允许用户通过点击向上/向下键或按上/下键盘上的增加/减少当前显示的值来选择一个值。用户也可以输入值手动。旋转框支持整数值，但可以扩展到使用不同的字符串与[validate](qspinbox.html#validate)（ ）[textFromValue](qspinbox.html#textFromValue)（）和[valueFromText](qspinbox.html#valueFromText)（ ） 。

每次值更改QSpinBox放出[valueChanged](qspinbox.html#valueChanged)（ ）信号。电流值可与提取[value](qspinbox.html#value-prop)（ ），并设置用[setValue](qspinbox.html#value-prop)（ ） 。

点击向上/向下按钮，或者使用键盘快捷键的向上和向下箭头会增加或减少步大小的当前值[singleStep](qspinbox.html#singleStep-prop)（ ） 。如果你想改变这种行为，您可以重新实现虚函数[stepBy](qabstractspinbox.html#stepBy)（ ） 。的最低和最高值和步长可以使用构造函数之一被设置，并且可以用以后改变[setMinimum](qspinbox.html#minimum-prop)（ ）[setMaximum](qspinbox.html#maximum-prop)（）和[setSingleStep](qspinbox.html#singleStep-prop)（ ） 。

大多数旋转框是有方向性的，但QSpinBox也可以作为一个圆形的旋转框，即如果经营范围是0-99 ，电流值是99 ，点击“向上”将给0，如果[wrapping](qabstractspinbox.html#wrapping-prop)（ ）设置为True 。使用[setWrapping](qabstractspinbox.html#wrapping-prop)（ ） ，如果你想圆行为。

所显示的值可以预先考虑并附加任意的字符串表示，例如，货币或计量单位。看[setPrefix](qspinbox.html#prefix-prop)（）和[setSuffix](qspinbox.html#suffix-prop)（ ） 。在旋转框中的文本与检索[text](qabstractspinbox.html#text-prop)（） （包括任何[prefix](qspinbox.html#prefix-prop)（）和[suffix](qspinbox.html#suffix-prop)（）），或用[cleanText](qspinbox.html#cleanText-prop)（） （其具有不[prefix](qspinbox.html#prefix-prop)（ ），不[suffix](qspinbox.html#suffix-prop)（）和没有前导或尾随空白） 。

常常希望给用户一个特殊（通常默认）选择除数值的范围。看[setSpecialValueText](qabstractspinbox.html#specialValueText-prop)（）对于如何与QSpinBox做到这一点。

| ![Screenshot of a Windows XP spin box](../img/windowsxp-spinbox.png) | A spin box shown in the [Windows XP widget style](index.htm). |
| ![Screenshot of a Plastique spin box](../img/plastique-spinbox.png) | A spin box shown in the [Plastique widget style](index.htm). |
| ![Screenshot of a Macintosh spin box](../img/macintosh-spinbox.png) | A spin box shown in the [Macintosh widget style](index.htm). |

### Subclassing QSpinBox

如果使用[prefix](qspinbox.html#prefix-prop)（ ）[suffix](qspinbox.html#suffix-prop)（）和[specialValueText](qabstractspinbox.html#specialValueText-prop)（ ）不提供足够的控制，你的子类QSpinBox和重新实现[valueFromText](qspinbox.html#valueFromText)（）和[textFromValue](qspinbox.html#textFromValue)（ ） 。例如，下面是一个自定义的旋转框，允许用户输入图标大小（例如， “ 32× 32” ）的代码：

```
 int IconSizeSpinBox.valueFromText(const [QString](qstring.html) &text) const
 {
     [QRegExp](qregexp.html) regExp(tr("(\\d+)(\\s*[xx]\\s*\\d+)?"));

     if (regExp.exactMatch(text)) {
         return regExp.cap(1).toInt();
     } else {
         return 0;
     }
 }

 [QString](qstring.html) IconSizeSpinBox.textFromValue(int value) const
 {
     return tr("%1 x %1").arg(value);
 }

```

请参阅[Icons](index.htm)示例的完整源代码。

* * *

## Method Documentation

```
QSpinBox.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个微调框以0为最低值， 99为最高值，为1的步长值。的值被初始设置为0 。这是对父_parent_。

**See also** [setMinimum](qspinbox.html#minimum-prop)（ ）[setMaximum](qspinbox.html#maximum-prop)（）和[setSingleStep](qspinbox.html#singleStep-prop)（ ） 。

```
QString QSpinBox.cleanText (self)
```

```
bool QSpinBox.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QString str QSpinBox.fixup (self, QString str)
```

从重新实现[QAbstractSpinBox.fixup](qabstractspinbox.html#fixup)（ ） 。

```
QSpinBox.fixup (self, QString str)
```

```
int QSpinBox.maximum (self)
```

```
int QSpinBox.minimum (self)
```

```
QString QSpinBox.prefix (self)
```

```
QSpinBox.setMaximum (self, int max)
```

```
QSpinBox.setMinimum (self, int min)
```

```
QSpinBox.setPrefix (self, QString p)
```

```
QSpinBox.setRange (self, int min, int max)
```

便利的功能设置_minimum_和_maximum_值与一个函数调用。

```
 setRange(minimum, maximum);

```

相当于：

```
 setMinimum(minimum);
 setMaximum(maximum);

```

**See also** [minimum](qspinbox.html#minimum-prop)和[maximum](qspinbox.html#maximum-prop)。

```
QSpinBox.setSingleStep (self, int val)
```

```
QSpinBox.setSuffix (self, QString s)
```

```
QSpinBox.setValue (self, int val)
```

这种方法也是一个Qt槽与C + +的签名`void setValue(int)`。

```
int QSpinBox.singleStep (self)
```

```
QString QSpinBox.suffix (self)
```

```
QString QSpinBox.textFromValue (self, int v)
```

这个虚函数所使用的旋转框时，它需要显示给定的_value_。默认实现返回一个包含一个字符串_value_用印在标准方式[QWidget.locale](qwidget.html#locale-prop)（ ） 。 toString（）方法，但与千位分隔符去掉。重新实现可能返回任何东西。 （参见在详细描述中的示例。）

注意：[QSpinBox](qspinbox.html)不会调用此函数[specialValueText](qabstractspinbox.html#specialValueText-prop)（）和既不[prefix](qspinbox.html#prefix-prop)（ ）也不[suffix](qspinbox.html#suffix-prop)（ ）应包括在返回值。

如果你重新实现这一点，您可能还需要重新实现[valueFromText](qspinbox.html#valueFromText)（）和[validate](qspinbox.html#validate)（ ）

**See also** [valueFromText](qspinbox.html#valueFromText)（ ）[validate](qspinbox.html#validate)（）和[QLocale.groupSeparator](qlocale.html#groupSeparator)（ ） 。

```
(QValidator.State, QString input, int pos) QSpinBox.validate (self, QString input, int pos)
```

从重新实现[QAbstractSpinBox.validate](qabstractspinbox.html#validate)（ ） 。

```
(QValidator.State, int pos) QSpinBox.validate (self, QString input, int pos)
```

```
int QSpinBox.value (self)
```

```
int QSpinBox.valueFromText (self, QString text)
```

这个虚函数所使用的旋转框时，它需要解释_text_由用户输入的值。

这需要在一个非数字的方式显示数字显示框的值的子类需要重写本函数。

注意：[QSpinBox](qspinbox.html)手柄[specialValueText](qabstractspinbox.html#specialValueText-prop)（ ）分开，此功能只关心其他值。

**See also** [textFromValue](qspinbox.html#textFromValue)（）和[validate](qspinbox.html#validate)（ ） 。

* * *

## Qt Signal Documentation

```
void valueChanged (int)
```

这是该信号的默认超载。

这个信号被发射时旋转框的值被改变。新值的整数值传递_i_。

```
void valueChanged (const QString&)
```

这是一个重载函数。

新的值是逐字传递_text_没有[prefix](qspinbox.html#prefix-prop)（）或[suffix](qspinbox.html#suffix-prop)（ ） 。