# QStyleOptionTabBarBaseV2 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionTabBarBaseV2类用于描述一个标籤栏的基础上，即一部分标籤栏通常有重叠。[More...](#details)

继承[QStyleOptionTabBarBase](qstyleoptiontabbarbase.html)。

### Types

*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionTabBarBaseV2 other)`
*   `__init__ (self, QStyleOptionTabBarBase other)`

### Members

*   `bool **[documentMode](qstyleoptiontabbarbasev2.html#documentMode-var)**`

* * *

## Detailed Description

该QStyleOptionTabBarBaseV2类用于描述一个标籤栏的基础上，即一部分标籤栏通常有重叠。

[QStyleOptionTabBarBase](qstyleoptiontabbarbase.html)包含的所有信息，[QStyle](qstyle.html)功能需要绘制标籤栏的基础。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionTabBarBaseV2.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTabBarBaseV2.Version` | `2` | 2 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontabbarbase.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionTabBarBaseV2.__init__ (self)
```

构建[QStyleOptionTabBarBaseV2](qstyleoptiontabbarbasev2.html)，初始化成员vaiables为它们的默认值。

```
QStyleOptionTabBarBaseV2.__init__ (self, QStyleOptionTabBarBaseV2 other)
```

构造的副本_other_。

```
QStyleOptionTabBarBaseV2.__init__ (self, QStyleOptionTabBarBase other)
```

构造的副本_other_。

* * *

## Member Documentation

```
bool documentMode
```

这个变量保存的tabbar是否在文件模式。

默认值是False ;