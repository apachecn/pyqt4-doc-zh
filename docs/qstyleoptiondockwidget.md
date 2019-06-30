# QStyleOptionDockWidget Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionDockWidget类是用来描述的参数绘制坞部件。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionDockWidgetV2](qstyleoptiondockwidgetv2.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionDockWidget other)`

### Members

*   `bool **[closable](qstyleoptiondockwidget.html#closable-var)**`
*   `bool **[floatable](qstyleoptiondockwidget.html#floatable-var)**`
*   `bool **[movable](qstyleoptiondockwidget.html#movable-var)**`
*   `QString **[title](qstyleoptiondockwidget.html#title-var)**`

* * *

## Detailed Description

该QStyleOptionDockWidget类是用来描述的参数绘制坞部件。

QStyleOptionDockWidget包含的所有信息，[QStyle](qstyle.html)功能需要借助像图形元素[QDockWidget](qdockwidget.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionDockWidget.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionDockWidget.Type` | `SO_DockWidget` | 风格选择该类型提供（[SO_DockWidget](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiondockwidget.html#StyleOptionVersion-enum)。

```
QStyleOptionDockWidget.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionDockWidget.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiondockwidget.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionDockWidget.__init__ (self)
```

构造一个[QStyleOptionDockWidget](qstyleoptiondockwidget.html)，初始化成员变量的默认值。

```
QStyleOptionDockWidget.__init__ (self, QStyleOptionDockWidget other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
bool closable
```

这个变量保存了被告席窗口是否关闭的。

默认值是True 。

```
bool floatable
```

这个变量保存了被告席窗口是否为浮动。

默认值是True 。

```
bool movable
```

这个变量保存了被告席窗口是否是可移动的。

默认值是False 。

```
QString title
```

这个变量保存了被告席窗口的标题。

默认值是一个空字符串。