# QStyleOptionTitleBar Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionTitleBar类是用来描述参数用于绘制标题栏。[More...](#details)

继承[QStyleOptionComplex](qstyleoptioncomplex.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionTitleBar other)`

### Members

*   `QIcon **[icon](qstyleoptiontitlebar.html#icon-var)**`
*   `QString **[text](qstyleoptiontitlebar.html#text-var)**`
*   `Qt.WindowFlags **[titleBarFlags](qstyleoptiontitlebar.html#titleBarFlags-var)**`
*   `int **[titleBarState](qstyleoptiontitlebar.html#titleBarState-var)**`

* * *

## Detailed Description

该QStyleOptionTitleBar类是用来描述参数用于绘制标题栏。

QStyleOptionTitleBar包含的所有信息，[QStyle](qstyle.html)功能需要绘制的标题栏[QMdiSubWindow](qmdisubwindow.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionTitleBar.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTitleBar.Type` | `SO_TitleBar` | 风格选择该类型提供（[SO_TitleBar](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiontitlebar.html#StyleOptionVersion-enum)。

```
QStyleOptionTitleBar.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTitleBar.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontitlebar.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionTitleBar.__init__ (self)
```

构造一个[QStyleOptionTitleBar](qstyleoptiontitlebar.html)，初始化成员变量，它们的默认值。

```
QStyleOptionTitleBar.__init__ (self, QStyleOptionTitleBar other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
QIcon icon
```

[

这个变量保存为标题栏中的图标。

默认值是一个空的图标，即与既不是像素图，也不是一个文件名的图标。

```
QString text
```

这个变量保存标题栏的文本。

默认值是一个空字符串。

](qicon.html)

```
Qt.WindowFlags titleBarFlags
```

[

这个变量保存的窗口部件标记的标题栏。

](index.htm)

[缺省值是](index.htm)[Qt.Widget](qt.html#WindowType-enum)。

**See also** [Qt.WindowFlags](qt.html#WindowType-enum)。

```
int titleBarState
```

这个变量保存在标题栏的状态。

这基本上是底层的窗口小部件的窗口状态。默认值是0。

**See also** [QWidget.windowState](qwidget.html#windowState)（ ） 。