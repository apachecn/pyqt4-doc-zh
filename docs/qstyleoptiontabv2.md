# QStyleOptionTabV2 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionTabV2类是用来描述绘制在Qt的4.1或以上标籤必要的参数。[More...](#details)

继承[QStyleOptionTab](qstyleoptiontab.html)。

通过继承[QStyleOptionTabV3](qstyleoptiontabv3.html)。

### Types

*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionTabV2 other)`
*   `__init__ (self, QStyleOptionTab other)`

### Members

*   `QSize **[iconSize](qstyleoptiontabv2.html#iconSize-var)**`

* * *

## Detailed Description

该QStyleOptionTabV2类是用来描述绘制在Qt的4.1或以上标籤必要的参数。

该QStyleOptionTabV2类的实例有[type](qstyleoption.html#type-varx) [SO_Tab](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)2 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

如果您创建自己的[QStyle](qstyle.html)子类，你应该同时处理[QStyleOptionTab](qstyleoptiontab.html)和QStyleOptionTabV2 。实现这一目标的方法之一是使用QStyleOptionTabV2拷贝构造函数。例如：

```
     if (const [QStyleOptionTab](qstyleoptiontab.html) *tabOption =
            qstyleoption_cast<const [QStyleOptionTab](qstyleoptiontab.html) *>(option)) {
         QStyleOptionTabV2 tabV2(*tabOption);

         // draw the tab using tabV2
    }

```

在上面的例子：如果`tabOption`的版本为1时，额外的构件（[iconSize](qstyleoptiontabv2.html#iconSize-var)）将被设定为无效的大小为`tabV2`。如果`tabOption`的版本是2 ，构造函数会简单地复制`tab`的[iconSize](qstyleoptiontabv2.html#iconSize-var)。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionTabV2.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTabV2.Version` | `2` | 2 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontab.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionTabV2.__init__ (self)
```

构造一个[QStyleOptionTabV2](qstyleoptiontabv2.html)。

```
QStyleOptionTabV2.__init__ (self, QStyleOptionTabV2 other)
```

构造的一个副本_other_样式选项。

```
QStyleOptionTabV2.__init__ (self, QStyleOptionTab other)
```

构造一个[QStyleOptionTabV2](qstyleoptiontabv2.html)副本_other_它可以是风格的选择[QStyleOptionTabV2](qstyleoptiontabv2.html) or [QStyleOptionTab](qstyleoptiontab.html)类型。

如果其他样式选项的版本是1 ，新样式选项的`iconSize`被设置为无效值。如果它的版本为2时，其`iconSize`值被简单地复制到新的样式选项。

* * *

## Member Documentation

```
QSize iconSize
```

[

这个变量保存了图标的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小;使用[QStyle.pixelMetric](qstyle.html#pixelMetric)（）来查找默认的图标大小的标籤条。

**See also** [QTabBar.iconSize](qtabbar.html#iconSize-prop)（ ） 。