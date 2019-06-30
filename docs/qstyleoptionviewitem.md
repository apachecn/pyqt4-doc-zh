# QStyleOptionViewItem Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionViewItem类是用来描述用来绘制在视图控件的项目的参数。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionViewItemV2](qstyleoptionviewitemv2.html)。

### Types

*   `enum Position { Left, Right, Top, Bottom }`
*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionViewItem other)`

### Members

*   `Qt.Alignment **[decorationAlignment](qstyleoptionviewitem.html#decorationAlignment-var)**`
*   `Position **[decorationPosition](qstyleoptionviewitem.html#decorationPosition-var)**`
*   `QSize **[decorationSize](qstyleoptionviewitem.html#decorationSize-var)**`
*   `Qt.Alignment **[displayAlignment](qstyleoptionviewitem.html#displayAlignment-var)**`
*   `QFont **[font](qstyleoptionviewitem.html#font-var)**`
*   `bool **[showDecorationSelected](qstyleoptionviewitem.html#showDecorationSelected-var)**`
*   `Qt.TextElideMode **[textElideMode](qstyleoptionviewitem.html#textElideMode-var)**`

* * *

## Detailed Description

该QStyleOptionViewItem类是用来描述用来绘制在视图控件的项目的参数。

QStyleOptionViewItem包含的所有信息，[QStyle](qstyle.html)功能需要绘制的项目Qt的模型/视图类。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionViewItem.Position
```

这个枚举变量描述该项目的装饰的位置。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionViewItem.Left` | `0` | 在文字的左边。 |
| `QStyleOptionViewItem.Right` | `1` | 在文字的权利。 |
| `QStyleOptionViewItem.Top` | `2` | 上面的文字。 |
| `QStyleOptionViewItem.Bottom` | `3` | 下面的文字。 |

**See also** [decorationPosition](qstyleoptionviewitem.html#decorationPosition-var)。

```
QStyleOptionViewItem.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionViewItem.Type` | `SO_ViewItem` | 风格选择该类型提供（[SO_ViewItem](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionviewitem.html#StyleOptionVersion-enum)。

```
QStyleOptionViewItem.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionViewItem.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionviewitem.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionViewItem.__init__ (self)
```

构造一个[QStyleOptionViewItem](qstyleoptionviewitem.html)，初始化成员变量，它们的默认值。

```
QStyleOptionViewItem.__init__ (self, QStyleOptionViewItem other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
Qt.Alignment decorationAlignment
```

[

这个变量保存该项目的装修的对齐方式。

](index.htm)

[缺省值是](index.htm)[Qt.AlignLeft](qt.html#AlignmentFlag-enum)。

```
Position decorationPosition
```

[

这个变量保存该项目的装饰的位置。

](qstyleoptionviewitem.html#Position-enum)

[缺省值是](qstyleoptionviewitem.html#Position-enum)[Left](qstyleoptionviewitem.html#Position-enum)。

**See also** [Position](qstyleoptionviewitem.html#Position-enum)。

```
QSize decorationSize
```

[

这个变量保存该项目的装修的大小。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小。

**See also** [decorationAlignment](qstyleoptionviewitem.html#decorationAlignment-var)和[decorationPosition](qstyleoptionviewitem.html#decorationPosition-var)。

```
Qt.Alignment displayAlignment
```

[

这个变量保存了项目的显示值的对齐方式。

](index.htm)

[缺省值是](index.htm)[Qt.AlignLeft](qt.html#AlignmentFlag-enum)。

```
QFont font
```

[

这个变量保存用于该项目的字体。

默认情况下，应用程序的默认字体。

](qfont.html)

[**See also**](qfont.html) [QFont](qfont.html)。

```
bool showDecorationSelected
```

这个变量保存是否装修应在选定的项目被高亮显示。

如果该选项设置为True ，在选定的项目分支和任何的装饰应该强调，这表明该项目被选中，否则，没有高亮是必需的。默认值是False 。

**See also** [QStyle.SH_ItemView_ShowDecorationSelected](qstyle.html#StyleHint-enum)和[QAbstractItemView](qabstractitemview.html)。

```
Qt.TextElideMode textElideMode
```

[

这个变量保存省略号的地方应为文本太长，以适应项目补充说。

](qt.html#TextElideMode-enum)

[缺省值是](qt.html#TextElideMode-enum)[Qt.ElideMiddle](qt.html#TextElideMode-enum)即省略号出现在文本的中间。

**See also** [Qt.TextElideMode](qt.html#TextElideMode-enum)和[QStyle.SH_ItemView_EllipsisLocation](qstyle.html#StyleHint-enum)。