# QStyleOptionToolButton Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionToolButton类是用来描述的参数绘制工具按钮。[More...](#details)

继承[QStyleOptionComplex](qstyleoptioncomplex.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`
*   `enum ToolButtonFeature { None, Arrow, Menu, PopupDelay, MenuButtonPopup, HasMenu }`
*   `class **[ToolButtonFeatures](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionToolButton other)`

### Members

*   `Qt.ArrowType **[arrowType](qstyleoptiontoolbutton.html#arrowType-var)**`
*   `ToolButtonFeatures **[features](qstyleoptiontoolbutton.html#features-var)**`
*   `QFont **[font](qstyleoptiontoolbutton.html#font-var)**`
*   `QIcon **[icon](qstyleoptiontoolbutton.html#icon-var)**`
*   `QSize **[iconSize](qstyleoptiontoolbutton.html#iconSize-var)**`
*   `QPoint **[pos](qstyleoptiontoolbutton.html#pos-var)**`
*   `QString **[text](qstyleoptiontoolbutton.html#text-var)**`
*   `Qt.ToolButtonStyle **[toolButtonStyle](qstyleoptiontoolbutton.html#toolButtonStyle-var)**`

* * *

## Detailed Description

该QStyleOptionToolButton类是用来描述的参数绘制工具按钮。

QStyleOptionToolButton包含的所有信息，[QStyle](qstyle.html)功能需要绘制[QToolButton](qtoolbutton.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionToolButton.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionToolButton.Type` | `SO_ToolButton` | 风格选择该类型提供（[SO_ToolButton](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiontoolbutton.html#StyleOptionVersion-enum)。

```
QStyleOptionToolButton.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionToolButton.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontoolbutton.html#StyleOptionType-enum)。

```
QStyleOptionToolButton.ToolButtonFeature
```

描述了一个工具按钮可以具有的各种功能。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionToolButton.None` | `0x00` | 一个正常的工具按钮。 |
| `QStyleOptionToolButton.Arrow` | `0x01` | 工具按钮是一个箭头。 |
| `QStyleOptionToolButton.Menu` | `0x04` | 工具按钮有一个菜单。 |
| `QStyleOptionToolButton.PopupDelay` | `0x08` | 有一个延迟，以显示菜单。 |
| `QStyleOptionToolButton.HasMenu` | `0x10` | 该按钮有一个弹出式菜单。 |
| `QStyleOptionToolButton.MenuButtonPopup` | `Menu` | 该按钮应显示一个箭头来指示菜单是否存在。 |

该ToolButtonFeatures类型是一个typedef为[QFlags](index.htm)\u003cToolButtonFeature\u003e 。它存储ToolButtonFeature值的或组合。

**See also** [features](qstyleoptiontoolbutton.html#features-var)，[QToolButton.toolButtonStyle](qtoolbutton.html#toolButtonStyle-prop)（）和[QToolButton.popupMode](qtoolbutton.html#popupMode-prop)（ ） 。

* * *

## Method Documentation

```
QStyleOptionToolButton.__init__ (self)
```

构造一个[QStyleOptionToolButton](qstyleoptiontoolbutton.html)，初始化成员变量，它们的默认值。

```
QStyleOptionToolButton.__init__ (self, QStyleOptionToolButton other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
Qt.ArrowType arrowType
```

[

这个变量保存的箭头工具按钮的方向。

](qt.html#ArrowType-enum)

[此值仅用于](qt.html#ArrowType-enum)[features](qstyleoptiontoolbutton.html#features-var)包括[Arrow](qstyleoptiontoolbutton.html#ToolButtonFeature-enum)。缺省值是[Qt.DownArrow](qt.html#ArrowType-enum)。

```
ToolButtonFeatures features
```

[

这个变量保存的工具按钮的功能，一个OR组合。

](index.htm)

[缺省值是](index.htm)[None](qstyleoptiontoolbutton.html#ToolButtonFeature-enum)。

**See also** [ToolButtonFeature](qstyleoptiontoolbutton.html#ToolButtonFeature-enum)。

```
QFont font
```

[

这个变量保存了用于文本的字体。

](qfont.html)

[此值仅用于](qfont.html)[toolButtonStyle](qstyleoptiontoolbutton.html#toolButtonStyle-var) is [Qt.ToolButtonTextUnderIcon](qt.html#ToolButtonStyle-enum)，[Qt.ToolButtonTextBesideIcon](qt.html#ToolButtonStyle-enum)或[Qt.ToolButtonTextOnly](qt.html#ToolButtonStyle-enum)。默认情况下，应用程序的默认字体。

```
QIcon icon
```

[

这个变量保存了工具按钮的图标。

默认值是一个空的图标，即与既不是像素图，也不是一个文件名的图标。

](qicon.html)

[**See also**](qicon.html) [iconSize](qstyleoptiontoolbutton.html#iconSize-var)。

```
QSize iconSize
```

[

这个变量保存的工具按钮图标的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小。

```
QPoint pos
```

[

这个变量保存工具按钮的位置。

默认值是空点，即（ 0,0）

```
QString text
```

这个变量保存工具按钮的文本。

](qpoint.html)

[此值仅用于](qpoint.html)[toolButtonStyle](qstyleoptiontoolbutton.html#toolButtonStyle-var) is [Qt.ToolButtonTextUnderIcon](qt.html#ToolButtonStyle-enum)，[Qt.ToolButtonTextBesideIcon](qt.html#ToolButtonStyle-enum)或[Qt.ToolButtonTextOnly](qt.html#ToolButtonStyle-enum)。默认值是一个空字符串。

```
Qt.ToolButtonStyle toolButtonStyle
```

[

这个变量保存一个Qt.ToolButtonStyle值描述工具按钮的外观。

](qt.html#ToolButtonStyle-enum)

[缺省值是](qt.html#ToolButtonStyle-enum)[Qt.ToolButtonIconOnly](qt.html#ToolButtonStyle-enum)。

**See also** [QToolButton.toolButtonStyle](qtoolbutton.html#toolButtonStyle-prop)（ ） 。