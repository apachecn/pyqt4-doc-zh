# QStyleOptionTabWidgetFrame Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionTabWidgetFrame类用于描述参数周围绘制一个标籤插件的框架。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionTabWidgetFrameV2](qstyleoptiontabwidgetframev2.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionTabWidgetFrame other)`

### Members

*   `QSize **[leftCornerWidgetSize](qstyleoptiontabwidgetframe.html#leftCornerWidgetSize-var)**`
*   `int **[lineWidth](qstyleoptiontabwidgetframe.html#lineWidth-var)**`
*   `int **[midLineWidth](qstyleoptiontabwidgetframe.html#midLineWidth-var)**`
*   `QSize **[rightCornerWidgetSize](qstyleoptiontabwidgetframe.html#rightCornerWidgetSize-var)**`
*   `QTabBar.Shape **[shape](qstyleoptiontabwidgetframe.html#shape-var)**`
*   `QSize **[tabBarSize](qstyleoptiontabwidgetframe.html#tabBarSize-var)**`

* * *

## Detailed Description

该QStyleOptionTabWidgetFrame类用于描述参数周围绘制一个标籤插件的框架。

QStyleOptionTabWidgetFrame包含的所有信息，[QStyle](qstyle.html)功能需要借助周围的边框[QTabWidget](qtabwidget.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionTabWidgetFrame.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTabWidgetFrame.Type` | `SO_TabWidgetFrame` | 风格选择该类型提供（[SO_TabWidgetFrame](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiontabwidgetframe.html#StyleOptionVersion-enum)。

```
QStyleOptionTabWidgetFrame.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTabWidgetFrame.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontabwidgetframe.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionTabWidgetFrame.__init__ (self)
```

构造一个[QStyleOptionTabWidgetFrame](qstyleoptiontabwidgetframe.html)，初始化成员变量，它们的默认值。

```
QStyleOptionTabWidgetFrame.__init__ (self, QStyleOptionTabWidgetFrame other)
```

构造的副本_other_。

* * *

## Member Documentation

```
QSize leftCornerWidgetSize
```

[

这个变量保存了左拐角部件的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小。

```
int lineWidth
```

这个变量保存线宽绘制面板。

默认值是0。

```
int midLineWidth
```

这个变量保存中间线宽绘制面板。

中期线的宽度通常是用在拉伸凹陷或凸起的帧。默认值是0。

```
QSize rightCornerWidgetSize
```

[

这个变量保存了右拐角窗口小部件的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小。

```
QTabBar.Shape shape
```

[

这个变量保存用于绘制选项卡的标籤形状。

](qtabbar.html#Shape-enum)

[缺省值是](qtabbar.html#Shape-enum)[QTabBar.RoundedNorth](qtabbar.html#Shape-enum)。

```
QSize tabBarSize
```

[

这个变量保存在标籤栏的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小。