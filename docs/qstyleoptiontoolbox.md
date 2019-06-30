# QStyleOptionToolBox Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionToolBox类是用来描述所需要的绘图工具中的参数。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionToolBoxV2](qstyleoptiontoolboxv2.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionToolBox other)`

### Members

*   `QIcon **[icon](qstyleoptiontoolbox.html#icon-var)**`
*   `QString **[text](qstyleoptiontoolbox.html#text-var)**`

* * *

## Detailed Description

该QStyleOptionToolBox类是用来描述所需要的绘图工具中的参数。

QStyleOptionToolBox包含的所有信息，[QStyle](qstyle.html)功能需要绘制[QToolBox](qtoolbox.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionToolBox.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionToolBox.Type` | `SO_ToolBox` | 风格选择该类型提供（[SO_ToolBox](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiontoolbox.html#StyleOptionVersion-enum)。

```
QStyleOptionToolBox.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionToolBox.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontoolbox.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionToolBox.__init__ (self)
```

创建[QStyleOptionToolBox](qstyleoptiontoolbox.html)，初始化成员变量，它们的默认值。

```
QStyleOptionToolBox.__init__ (self, QStyleOptionToolBox other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
QIcon icon
```

[

这个变量保存了工具箱选项卡上的图标。

默认值是一个空的图标，即与既不是像素图，也不是一个文件名的图标。

```
QString text
```

这个变量保存的文本工具箱选项卡。

默认值是一个空字符串。

](qicon.html)