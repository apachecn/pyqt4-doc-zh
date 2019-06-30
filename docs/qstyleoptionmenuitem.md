# QStyleOptionMenuItem Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionMenuItem类是用来描述所必需的绘制的菜单项的参数。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

### Types

*   `enum CheckType { NotCheckable, Exclusive, NonExclusive }`
*   `enum MenuItemType { Normal, DefaultItem, Separator, SubMenu, ..., EmptyArea }`
*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionMenuItem other)`

### Members

*   `bool **[checked](qstyleoptionmenuitem.html#checked-var)**`
*   `CheckType **[checkType](qstyleoptionmenuitem.html#checkType-var)**`
*   `QFont **[font](qstyleoptionmenuitem.html#font-var)**`
*   `QIcon **[icon](qstyleoptionmenuitem.html#icon-var)**`
*   `int **[maxIconWidth](qstyleoptionmenuitem.html#maxIconWidth-var)**`
*   `bool **[menuHasCheckableItems](qstyleoptionmenuitem.html#menuHasCheckableItems-var)**`
*   `MenuItemType **[menuItemType](qstyleoptionmenuitem.html#menuItemType-var)**`
*   `QRect **[menuRect](qstyleoptionmenuitem.html#menuRect-var)**`
*   `int **[tabWidth](qstyleoptionmenuitem.html#tabWidth-var)**`
*   `QString **[text](qstyleoptionmenuitem.html#text-var)**`

* * *

## Detailed Description

该QStyleOptionMenuItem类是用来描述所必需的绘制的菜单项的参数。

QStyleOptionMenuItem包含的所有信息，[QStyle](qstyle.html)功能需要从绘制菜单项[QMenu](qmenu.html)。它也被用于绘制其他菜单相关的部件。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionMenuItem.CheckType
```

此枚举是用来表示一个复选标记是否应该被绘制的项目，或者即使它应该在所有绘制。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionMenuItem.NotCheckable` | `0` | 该项目是不是可复。 |
| `QStyleOptionMenuItem.Exclusive` | `1` | 该项目是独家检查项目（如单选按钮） 。 |
| `QStyleOptionMenuItem.NonExclusive` | `2` | 该项目是一个非排他性的检查项目（如复选框） 。 |

**See also** [checkType](qstyleoptionmenuitem.html#checkType-var)，[QAction.checkable](qaction.html#checkable-prop)，[QAction.checked](qaction.html#checked-prop)和[QActionGroup.exclusive](qactiongroup.html#exclusive-prop)。

```
QStyleOptionMenuItem.MenuItemType
```

这个枚举表示该结构描述了菜单项的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionMenuItem.Normal` | `0` | 一个正常的菜单项。 |
| `QStyleOptionMenuItem.DefaultItem` | `1` | 菜单项是默认操作与指定的[QMenu.defaultAction](qmenu.html#defaultAction)（ ） 。 |
| `QStyleOptionMenuItem.Separator` | `2` | 一个菜单分隔符。 |
| `QStyleOptionMenuItem.SubMenu` | `3` | 表示该菜单项指向一个子菜单。 |
| `QStyleOptionMenuItem.Scroller` | `4` | 一个弹出式菜单滚动条（目前只用于在Mac OS X ） 。 |
| `QStyleOptionMenuItem.TearOff` | `5` | 为菜单可撕式手柄。 |
| `QStyleOptionMenuItem.Margin` | `6` | 菜单的利润率。 |
| `QStyleOptionMenuItem.EmptyArea` | `7` | 菜单的空白区域。 |

**See also** [menuItemType](qstyleoptionmenuitem.html#menuItemType-var)。

```
QStyleOptionMenuItem.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionMenuItem.Type` | `SO_MenuItem` | 风格选择该类型提供（[SO_MenuItem](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionmenuitem.html#StyleOptionVersion-enum)。

```
QStyleOptionMenuItem.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionMenuItem.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionmenuitem.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionMenuItem.__init__ (self)
```

构造一个[QStyleOptionMenuItem](qstyleoptionmenuitem.html)，初始化成员变量，它们的默认值。

```
QStyleOptionMenuItem.__init__ (self, QStyleOptionMenuItem other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
bool checked
```

这个变量保存是否在菜单项被选中与否。

默认值是False 。

```
CheckType checkType
```

[

这个变量保存菜单项的选中标记的类型。

](qstyleoptionmenuitem.html#CheckType-enum)

[缺省值是](qstyleoptionmenuitem.html#CheckType-enum)[NotCheckable](qstyleoptionmenuitem.html#CheckType-enum)。

**See also** [CheckType](qstyleoptionmenuitem.html#CheckType-enum)。

```
QFont font
```

[

这个变量保存用于菜单项文本的字体。

这是应该用于绘制文本菜单减去快捷的字体。快捷方式是使用画家的字体通常被绘制。默认情况下，应用程序的默认字体。

](qfont.html)

```
QIcon icon
```

[

这个变量保存为菜单项的图标。

默认值是一个空的图标，即与既不是像素图，也不是一个文件名的图标。

```
int maxIconWidth
```

这个变量保存的最大宽度图标在菜单项的图标。

这可以被用于绘制图标到正确的位置或适当的对准件。该变量必须设置无论菜单项是否有一个图标。默认值是0。

```
bool menuHasCheckableItems
```

这个变量保存菜单是否作为一个整体具有辨认的物品或没有。

默认值是True 。

如果此选项设置为False ，然后在菜单没有辨认的项目。这使得它可以用于图形用户界面风格，以节省一些横向空间，通常会被用于检查列。

](qicon.html)

```
MenuItemType menuItemType
```

[

这个变量保存菜单项的类型。

](qstyleoptionmenuitem.html#MenuItemType-enum)

[缺省值是](qstyleoptionmenuitem.html#MenuItemType-enum)[Normal](qstyleoptionmenuitem.html#MenuItemType-enum)。

**See also** [MenuItemType](qstyleoptionmenuitem.html#MenuItemType-enum)。

```
QRect menuRect
```

[

这个变量保存了整个菜单的矩形。

默认值是空的矩形，即用宽度和高度设置为0的矩形。

```
int tabWidth
```

这个变量保存的标籤宽度为菜单项。

该选项卡的宽度是菜单项的文本和快捷之间的距离。默认值是0。

```
QString text
```

这个变量保存的文本菜单项。

需要注意的是文本格式是这样的“菜单文本**\t**快捷方式“ 。

如果菜单项没有一个快捷方式，它只会包含菜单项的文本。默认值是一个空字符串。

](qrect.html)