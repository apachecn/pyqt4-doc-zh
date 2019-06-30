# QStyleOptionButton Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionButton类是用来描述的参数绘制的按钮。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

### Types

*   `enum ButtonFeature { None, Flat, HasMenu, DefaultButton, AutoDefaultButton, CommandLinkButton }`
*   `class **[ButtonFeatures](index.htm)**`
*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionButton other)`

### Members

*   `ButtonFeatures **[features](qstyleoptionbutton.html#features-var)**`
*   `QIcon **[icon](qstyleoptionbutton.html#icon-var)**`
*   `QSize **[iconSize](qstyleoptionbutton.html#iconSize-var)**`
*   `QString **[text](qstyleoptionbutton.html#text-var)**`

* * *

## Detailed Description

该QStyleOptionButton类是用来描述的参数绘制的按钮。

QStyleOptionButton包含的所有信息，[QStyle](qstyle.html)功能需要借助像图形元素[QPushButton](qpushbutton.html)，[QCheckBox](qcheckbox.html)和[QRadioButton](qradiobutton.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionButton.ButtonFeature
```

这个枚举变量描述了不同类型的功能的按钮可以有。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionButton.None` | `0x00` | 表示正常按钮。 |
| `QStyleOptionButton.Flat` | `0x01` | 表示一个平面按钮。 |
| `QStyleOptionButton.HasMenu` | `0x02` | 表示该按钮有一个下拉菜单。 |
| `QStyleOptionButton.DefaultButton` | `0x04` | 表示该按钮是默认按钮。 |
| `QStyleOptionButton.AutoDefaultButton` | `0x08` | 表示该按钮是自动默认按钮。 |
| `QStyleOptionButton.CommandLinkButton` | `0x10` | 表示该按钮是Windows Vista的类型命令链接。 |

该ButtonFeatures类型是一个typedef为[QFlags](index.htm)\u003cButtonFeature\u003e 。它存储ButtonFeature值的或组合。

**See also** [features](qstyleoptionbutton.html#features-var)。

```
QStyleOptionButton.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionButton.Type` | `SO_Button` | 风格选择该类型提供（[SO_Button](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionbutton.html#StyleOptionVersion-enum)。

```
QStyleOptionButton.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionButton.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionbutton.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionButton.__init__ (self)
```

构造一个[QStyleOptionButton](qstyleoptionbutton.html)，初始化成员变量，它们的默认值。

```
QStyleOptionButton.__init__ (self, QStyleOptionButton other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
ButtonFeatures features
```

[

这个变量保存的描述这个按钮的功能，按位或。

](index.htm)

[**See also**](index.htm) [ButtonFeature](qstyleoptionbutton.html#ButtonFeature-enum)。

```
QIcon icon
```

[

这个变量保存按钮的图标。

默认值是一个空的图标，即与既不是像素图，也不是一个文件名的图标。

](qicon.html)

[**See also**](qicon.html) [iconSize](qstyleoptionbutton.html#iconSize-var)。

```
QSize iconSize
```

[

这个变量保存按钮的图标的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小。

```
QString text
```

这个变量保存按钮的文本。

默认值是一个空字符串。