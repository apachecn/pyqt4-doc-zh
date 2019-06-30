# QStyleOptionTabBarBase Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionTabBarBase类用于描述一个标籤栏的基础上，即一部分标籤栏通常有重叠。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionTabBarBaseV2](qstyleoptiontabbarbasev2.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionTabBarBase other)`

### Members

*   `QRect **[selectedTabRect](qstyleoptiontabbarbase.html#selectedTabRect-var)**`
*   `QTabBar.Shape **[shape](qstyleoptiontabbarbase.html#shape-var)**`
*   `QRect **[tabBarRect](qstyleoptiontabbarbase.html#tabBarRect-var)**`

* * *

## Detailed Description

该QStyleOptionTabBarBase类用于描述一个标籤栏的基础上，即一部分标籤栏通常有重叠。

QStyleOptionTabBarBase包含的所有信息，[QStyle](qstyle.html)功能需要绘制标籤栏的基础。注意，这仅绘制为一个独立的[QTabBar](qtabbar.html)（一个不是的一部分[QTabWidget](qtabwidget.html)） 。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionTabBarBase.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTabBarBase.Type` | `SO_TabBarBase` | 风格选择该类型提供（[SO_TabBarBase](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiontabbarbase.html#StyleOptionVersion-enum)。

```
QStyleOptionTabBarBase.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTabBarBase.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontabbarbase.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionTabBarBase.__init__ (self)
```

构建[QStyleOptionTabBarBase](qstyleoptiontabbarbase.html)，初始化成员vaiables为它们的默认值。

```
QStyleOptionTabBarBase.__init__ (self, QStyleOptionTabBarBase other)
```

构造的副本_other_。

* * *

## Member Documentation

```
QRect selectedTabRect
```

[

这个变量保存包含所选选项卡的矩形。

](qrect.html)

[这个矩形被包含在](qrect.html)[tabBarRect](qstyleoptiontabbarbase.html#tabBarRect-var)。默认值是空的矩形，即用宽度和高度设置为0的矩形。

```
QTabBar.Shape shape
```

[

这个变量保存在标籤栏的形状。

](qtabbar.html#Shape-enum)

[缺省值是](qtabbar.html#Shape-enum)[QTabBar.RoundedNorth](qtabbar.html#Shape-enum)。

```
QRect tabBarRect
```

[

这个变量保存一个包含所有标籤的矩形。

默认值是空的矩形，即用宽度和高度设置为0的矩形。

](qrect.html)