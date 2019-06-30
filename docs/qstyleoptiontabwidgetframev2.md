# QStyleOptionTabWidgetFrameV2 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionTabWidgetFrameV2类用于描述参数周围绘制一个标籤插件的框架。[More...](#details)

继承[QStyleOptionTabWidgetFrame](qstyleoptiontabwidgetframe.html)。

### Types

*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionTabWidgetFrameV2 other)`
*   `__init__ (self, QStyleOptionTabWidgetFrame other)`

### Members

*   `QRect **[selectedTabRect](qstyleoptiontabwidgetframev2.html#selectedTabRect-var)**`
*   `QRect **[tabBarRect](qstyleoptiontabwidgetframev2.html#tabBarRect-var)**`

* * *

## Detailed Description

该QStyleOptionTabWidgetFrameV2类用于描述参数周围绘制一个标籤插件的框架。

QStyleOptionTabWidgetFrameV2包含的所有信息，[QStyle](qstyle.html)功能需要借助周围的边框[QTabWidget](qtabwidget.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionTabWidgetFrameV2.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTabWidgetFrameV2.Version` | `2` | 2 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontabwidgetframe.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionTabWidgetFrameV2.__init__ (self)
```

构造一个[QStyleOptionTabWidgetFrameV2](qstyleoptiontabwidgetframev2.html)，初始化成员变量，它们的默认值。

```
QStyleOptionTabWidgetFrameV2.__init__ (self, QStyleOptionTabWidgetFrameV2 other)
```

构造一个[QStyleOptionTabWidgetFrameV2](qstyleoptiontabwidgetframev2.html)副本_other_样式选项。

如果_other_风格选择的版本是1 ，新样式选项的[selectedTabRect](qstyleoptiontabwidgetframev2.html#selectedTabRect-var)和[tabBarRect](qstyleoptiontabwidgetframev2.html#tabBarRect-var)将包含null rects

**See also** [version](qstyleoption.html#version-var)。

```
QStyleOptionTabWidgetFrameV2.__init__ (self, QStyleOptionTabWidgetFrame other)
```

构造一个[QStyleOptionTabWidgetFrameV2](qstyleoptiontabwidgetframev2.html)副本_other_样式选项。

如果_other_风格选择的版本是1 ，新样式选项的[selectedTabRect](qstyleoptiontabwidgetframev2.html#selectedTabRect-var)和[tabBarRect](qstyleoptiontabwidgetframev2.html#tabBarRect-var)将包含null rects

**See also** [version](qstyleoption.html#version-var)。

* * *

## Member Documentation

```
QRect selectedTabRect
```

[

这个变量保存包含所选选项卡的矩形。

](qrect.html)

[这个矩形被包含在](qrect.html)[tabBarRect](qstyleoptiontabwidgetframev2.html#tabBarRect-var)。默认值是空的矩形，即用宽度和高度设置为0的矩形。

```
QRect tabBarRect
```

[

这个变量保存一个包含所有标籤的矩形。

默认值是空的矩形，即用宽度和高度设置为0的矩形。

](qrect.html)