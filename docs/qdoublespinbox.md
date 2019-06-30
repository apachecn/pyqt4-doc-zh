# QDoubleSpinBox Class Reference

## [[QtGui](index.htm) module]

该QDoubleSpinBox类提供了一个微调框小部件，需要增加一倍。[More...](#details)

继承[QAbstractSpinBox](qabstractspinbox.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `QString cleanText (self)`
*   `int decimals (self)`
*   `QString str fixup (self, QString str)`
*   `fixup (self, QString str)`
*   `float maximum (self)`
*   `float minimum (self)`
*   `QString prefix (self)`
*   `setDecimals (self, int prec)`
*   `setMaximum (self, float max)`
*   `setMinimum (self, float min)`
*   `setPrefix (self, QString p)`
*   `setRange (self, float min, float max)`
*   `setSingleStep (self, float val)`
*   `setSuffix (self, QString s)`
*   `setValue (self, float val)`
*   `float singleStep (self)`
*   `QString suffix (self)`
*   `QString textFromValue (self, float v)`
*   `(QValidator.State, QString input, int pos) validate (self, QString input, int pos)`
*   `(QValidator.State, int pos) validate (self, QString input, int pos)`
*   `float value (self)`
*   `float valueFromText (self, QString text)`

### Qt Signals

*   `void valueChanged (double)`
*   `void valueChanged (const QString&)`

* * *

## Detailed Description

该QDoubleSpinBox类提供了一个微调框小部件，需要增加一倍。

QDoubleSpinBox允许用户通过单击向上和向下按钮或按向上或向下的键盘上增加或减少当前显示的值来选择一个值。用户也可以输入值手动。旋转框支持双精度值，但可以扩展到使用不同的字符串与[validate](qdoublespinbox.html#validate)（ ）[textFromValue](qdoublespinbox.html#textFromValue)（）和[valueFromText](qdoublespinbox.html#valueFromText)（ ） 。

每次值更改QDoubleSpinBox放出[valueChanged](qdoublespinbox.html#valueChanged)（）信号。电流值可与提取[value](qdoublespinbox.html#value-prop)（ ），并设置用[setValue](qdoublespinbox.html#value-prop)（ ） 。

注： QDoubleSpinBox将数字四舍五入，使他们能够与当前的精确显示。与小数一个QDoubleSpinBox设置为2 ，调用的setValue （ 2.555 ）会导致[value](qdoublespinbox.html#value-prop)（ ）返回2.56 。

单击向上和向下按钮，或者使用键盘快捷键的向上和向下箭头来增加或减少步大小的当前值[singleStep](qdoublespinbox.html#singleStep-prop)（ ） 。如果你想改变这种行为，您可以重新实现虚函数[stepBy](qabstractspinbox.html#stepBy)（ ） 。的最低和最高值和步长可以使用构造函数之一被设置，并且可以用以后改变[setMinimum](qdoublespinbox.html#minimum-prop)（ ）[setMaximum](qdoublespinbox.html#maximum-prop)（）和[setSingleStep](qdoublespinbox.html#singleStep-prop)（ ） 。纺纱器有2位小数默认的精度，但这个可以通过改变[setDecimals](qdoublespinbox.html#decimals-prop)（ ） 。

大多数旋转框是有方向性的，但QDoubleSpinBox也可以作为一个圆形的旋转框，即如果经营范围是0.0-99.9 ，电流值是99.9 ，点击“向上”将给0，如果[wrapping](qabstractspinbox.html#wrapping-prop)（ ）设置为True 。使用[setWrapping](qabstractspinbox.html#wrapping-prop)（ ） ，如果你想圆行为。

所显示的值可以预先考虑并附加任意的字符串表示，例如，货币或计量单位。看[setPrefix](qdoublespinbox.html#prefix-prop)（）和[setSuffix](qdoublespinbox.html#suffix-prop)（ ） 。在旋转框中的文本与检索[text](qabstractspinbox.html#text-prop)（） （包括任何[prefix](qdoublespinbox.html#prefix-prop)（）和[suffix](qdoublespinbox.html#suffix-prop)（）），或用[cleanText](qdoublespinbox.html#cleanText-prop)（） （其具有不[prefix](qdoublespinbox.html#prefix-prop)（ ），不[suffix](qdoublespinbox.html#suffix-prop)（）和没有前导或尾随空白） 。

常常希望给用户一个特殊（通常默认）选择除数值的范围。看[setSpecialValueText](qabstractspinbox.html#specialValueText-prop)（）对于如何与QDoubleSpinBox做到这一点。

* * *

## Method Documentation

```
QDoubleSpinBox.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个具有0.0为最低值和99.99一个微调框为最大值，为1.0，步长值和2位小数精度。该值最初设置为0.00 。旋转方块已定_parent_。

**See also** [setMinimum](qdoublespinbox.html#minimum-prop)（ ）[setMaximum](qdoublespinbox.html#maximum-prop)（）和[setSingleStep](qdoublespinbox.html#singleStep-prop)（ ） 。

```
QString QDoubleSpinBox.cleanText (self)
```

```
int QDoubleSpinBox.decimals (self)
```

```
QString str QDoubleSpinBox.fixup (self, QString str)
```

从重新实现[QAbstractSpinBox.fixup](qabstractspinbox.html#fixup)（ ） 。

```
QDoubleSpinBox.fixup (self, QString str)
```

```
float QDoubleSpinBox.maximum (self)
```

```
float QDoubleSpinBox.minimum (self)
```

```
QString QDoubleSpinBox.prefix (self)
```

```
QDoubleSpinBox.setDecimals (self, int prec)
```

```
QDoubleSpinBox.setMaximum (self, float max)
```

```
QDoubleSpinBox.setMinimum (self, float min)
```

```
QDoubleSpinBox.setPrefix (self, QString p)
```

```
QDoubleSpinBox.setRange (self, float min, float max)
```

便利的功能设置_minimum_和_maximum_值与一个函数调用。

注意：最大和最小值将被舍入到匹配小数属性。

```
 setRange(minimum, maximum);

```

相当于：

```
 setMinimum(minimum);
 setMaximum(maximum);

```

**See also** [minimum](qdoublespinbox.html#minimum-prop)和[maximum](qdoublespinbox.html#maximum-prop)。

```
QDoubleSpinBox.setSingleStep (self, float val)
```

```
QDoubleSpinBox.setSuffix (self, QString s)
```

```
QDoubleSpinBox.setValue (self, float val)
```

这种方法也是一个Qt槽与C + +的签名`void setValue(double)`。

```
float QDoubleSpinBox.singleStep (self)
```

```
QString QDoubleSpinBox.suffix (self)
```

```
QString QDoubleSpinBox.textFromValue (self, float v)
```

这个虚函数所使用的旋转框时，它需要显示给定的_value_。默认实现返回一个包含一个字符串_value_使用印刷[QWidget.locale](qwidget.html#locale-prop)（ ） 。的toString （_value_，[QLatin1Char](qlatin1char.html)（ “F” ） ，[decimals](qdoublespinbox.html#decimals-prop)（ ） ），并会删除的千位分隔符。重新实现可能返回任何东西。

注意：[QDoubleSpinBox](qdoublespinbox.html)不会调用此函数[specialValueText](qabstractspinbox.html#specialValueText-prop)（）和既不[prefix](qdoublespinbox.html#prefix-prop)（ ）也不[suffix](qdoublespinbox.html#suffix-prop)（ ）应包括在返回值。

如果你重新实现这一点，您可能还需要重新实现[valueFromText](qdoublespinbox.html#valueFromText)（ ） 。

**See also** [valueFromText](qdoublespinbox.html#valueFromText)（）和[QLocale.groupSeparator](qlocale.html#groupSeparator)（ ） 。

```
(QValidator.State, QString input, int pos) QDoubleSpinBox.validate (self, QString input, int pos)
```

从重新实现[QAbstractSpinBox.validate](qabstractspinbox.html#validate)（ ） 。

```
(QValidator.State, int pos) QDoubleSpinBox.validate (self, QString input, int pos)
```

```
float QDoubleSpinBox.value (self)
```

```
float QDoubleSpinBox.valueFromText (self, QString text)
```

这个虚函数所使用的旋转框时，它需要解释_text_由用户输入的值。

这需要在一个非数字的方式显示数字显示框的值的子类需要重写本函数。

注意：[QDoubleSpinBox](qdoublespinbox.html)手柄[specialValueText](qabstractspinbox.html#specialValueText-prop)（ ）分开，此功能只关心其他值。

**See also** [textFromValue](qdoublespinbox.html#textFromValue)（）和[validate](qdoublespinbox.html#validate)（ ） 。

* * *

## Qt Signal Documentation

```
void valueChanged (double)
```

这是该信号的默认超载。

这个信号被发射时旋转框的值被改变。新的值传递_d_。

```
void valueChanged (const QString&)
```

这是一个重载函数。

新的值是逐字传递_text_没有[prefix](qdoublespinbox.html#prefix-prop)（）或[suffix](qdoublespinbox.html#suffix-prop)（ ） 。