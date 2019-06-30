# QStyleOptionComboBox Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionComboBox类是用来描述参数绘制一个组合框。[More...](#details)

继承[QStyleOptionComplex](qstyleoptioncomplex.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionComboBox other)`

### Members

*   `QIcon **[currentIcon](qstyleoptioncombobox.html#currentIcon-var)**`
*   `QString **[currentText](qstyleoptioncombobox.html#currentText-var)**`
*   `bool **[editable](qstyleoptioncombobox.html#editable-var)**`
*   `bool **[frame](qstyleoptioncombobox.html#frame-var)**`
*   `QSize **[iconSize](qstyleoptioncombobox.html#iconSize-var)**`
*   `QRect **[popupRect](qstyleoptioncombobox.html#popupRect-var)**`

* * *

## Detailed Description

该QStyleOptionComboBox类是用来描述参数绘制一个组合框。

[QStyleOptionButton](qstyleoptionbutton.html)包含的所有信息，[QStyle](qstyle.html)功能需要绘制[QComboBox](qcombobox.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionComboBox.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionComboBox.Type` | `SO_ComboBox` | 风格选择该类型提供（[SO_ComboBox](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptioncombobox.html#StyleOptionVersion-enum)。

```
QStyleOptionComboBox.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionComboBox.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptioncombobox.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionComboBox.__init__ (self)
```

创建[QStyleOptionComboBox](qstyleoptioncombobox.html)，初始化成员变量，它们的默认值。

```
QStyleOptionComboBox.__init__ (self, QStyleOptionComboBox other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
QIcon currentIcon
```

[

这个变量保存在组合框的当前项目的图标。

默认值是一个空的图标，即与既不是像素图，也不是一个文件名的图标。

```
QString currentText
```

这个变量保存的文本组合框的当前项目。

默认值是一个空字符串。

```
bool editable
```

这个变量保存了组合框是否为可编辑还是不行。

默认值是False

](qicon.html)

[**See also**](qicon.html) [QComboBox.isEditable](qcombobox.html#editable-prop)（ ） 。

```
bool frame
```

这个变量保存在组合框中是否有一个框架。

默认值是True 。

```
QSize iconSize
```

[

这个变量保存图标大小组合框的当前项目。

](qsize.html)

[缺省值是](qsize.html)[QSize](qsize.html)（ -1，-1） ，即，一个无效的大小。

```
QRect popupRect
```

[

这个变量保存在弹出的矩形组合框。

默认值是空的矩形，即用宽度和高度设置为0的矩形。

这个变量是当前未使用。您可以放心地忽略它。

](qrect.html)

[**See also**](qrect.html) [QStyle.SC_ComboBoxListBoxPopup](qstyle.html#SubControl-enum)。