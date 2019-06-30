# QStyleOptionTabV3 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionTabV3类是用来描述绘制在Qt的4.5或以上标籤必要的参数。[More...](#details)

继承[QStyleOptionTabV2](qstyleoptiontabv2.html)。

### Types

*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionTabV3 other)`
*   `__init__ (self, QStyleOptionTabV2 other)`
*   `__init__ (self, QStyleOptionTab other)`

### Members

*   `bool **[documentMode](qstyleoptiontabv3.html#documentMode-var)**`
*   `QSize **[leftButtonSize](qstyleoptiontabv3.html#leftButtonSize-var)**`
*   `QSize **[rightButtonSize](qstyleoptiontabv3.html#rightButtonSize-var)**`

* * *

## Detailed Description

该QStyleOptionTabV3类是用来描述绘制在Qt的4.5或以上标籤必要的参数。

该QStyleOptionTabV3类的实例有[type](qstyleoption.html#type-varx) [SO_Tab](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)3 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

如果您创建自己的[QStyle](qstyle.html)子类，你应该同时处理[QStyleOptionTab](qstyleoptiontab.html)，[QStyleOptionTabV2](qstyleoptiontabv2.html)和QStyleOptionTabV3 。实现这一目标的方法之一是使用QStyleOptionTabV3拷贝构造函数。例如：

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
QStyleOptionTabV3.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTabV3.Version` | `3` | 3 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontab.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionTabV3.__init__ (self)
```

构造一个[QStyleOptionTabV3](qstyleoptiontabv3.html)。

```
QStyleOptionTabV3.__init__ (self, QStyleOptionTabV3 other)
```

构造的一个副本_other_样式选项。

```
QStyleOptionTabV3.__init__ (self, QStyleOptionTabV2 other)
```

构造的一个副本_other_样式选项。

```
QStyleOptionTabV3.__init__ (self, QStyleOptionTab other)
```

构造一个[QStyleOptionTabV3](qstyleoptiontabv3.html)副本_other_它可以是风格的选择[QStyleOptionTabV3](qstyleoptiontabv3.html)，[QStyleOptionTabV2](qstyleoptiontabv2.html) or [QStyleOptionTab](qstyleoptiontab.html)类型。

如果其他样式选项的版本为1或2 ，新的样式选项的`leftButtonSize`和`rightButtonSize`被设置为无效值。如果它的版本为3时，其`leftButtonSize`和`rightButtonSize`值被简单地复制到新样式选项。

* * *

## Member Documentation

```
bool documentMode
```

这个变量保存的tabbar是否在文件模式。

默认值是False ;

```
QSize leftButtonSize
```

[

这个变量保存在标籤左侧插件的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小;

```
QSize rightButtonSize
```

[

这个变量保存在标籤右侧插件的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小;