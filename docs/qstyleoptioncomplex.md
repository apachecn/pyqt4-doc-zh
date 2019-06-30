# QStyleOptionComplex Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionComplex类用于认为是所有复杂的控制参数。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionComboBox](qstyleoptioncombobox.html)，[QStyleOptionGroupBox](qstyleoptiongroupbox.html)，[QStyleOptionSizeGrip](qstyleoptionsizegrip.html)，[QStyleOptionSlider](qstyleoptionslider.html)，[QStyleOptionSpinBox](qstyleoptionspinbox.html)，[QStyleOptionTitleBar](qstyleoptiontitlebar.html)和[QStyleOptionToolButton](qstyleoptiontoolbutton.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self, int version = QStyleOptionComplex.Version, int type = QStyleOption.SO_Complex)`
*   `__init__ (self, QStyleOptionComplex other)`

### Members

*   `QStyle.SubControls **[activeSubControls](qstyleoptioncomplex.html#activeSubControls-var)**`
*   `QStyle.SubControls **[subControls](qstyleoptioncomplex.html#subControls-var)**`

* * *

## Detailed Description

该QStyleOptionComplex类用于认为是所有复杂的控制参数。

此类不用于自身。相反，它是用来推导其它复杂的控制选项，例如[QStyleOptionSlider](qstyleoptionslider.html)和[QStyleOptionSpinBox](qstyleoptionspinbox.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionComplex.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionComplex.Type` | `SO_Complex` | 风格选择该类型提供（[SO_Complex](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptioncomplex.html#StyleOptionVersion-enum)。

```
QStyleOptionComplex.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionComplex.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptioncomplex.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionComplex.__init__ (self, int version = QStyleOptionComplex.Version, int type = QStyleOption.SO_Complex)
```

构造一个[QStyleOptionComplex](qstyleoptioncomplex.html)指定的_type_和_version_，初始化成员变量的默认值。此构造函数通常被称为子类。

```
QStyleOptionComplex.__init__ (self, QStyleOptionComplex other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
QStyle.SubControls activeSubControls
```

[](index.htm)

[这个变量保存的按位或](index.htm)[sub-controls](qstyle.html#SubControl-enum)这是活动的复杂控制。

缺省值是[QStyle.SC_None](qstyle.html#SubControl-enum)。

**See also** [QStyle.SubControl](qstyle.html#SubControl-enum)。

```
QStyle.SubControls subControls
```

[](index.htm)

[这个变量保存的按位或](index.htm)[sub-controls](qstyle.html#SubControl-enum)要绘制的复杂的控制。

缺省值是[QStyle.SC_All](qstyle.html#SubControl-enum)。

**See also** [QStyle.SubControl](qstyle.html#SubControl-enum)。