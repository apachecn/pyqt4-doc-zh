# QStyleOptionFrameV2 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionFrameV2类是用来描述用于绘制Qt中4.1或更高的帧所必需的参数。[More...](#details)

继承[QStyleOptionFrame](qstyleoptionframe.html)。

通过继承[QStyleOptionFrameV3](qstyleoptionframev3.html)。

### Types

*   `enum FrameFeature { None, Flat }`
*   `class **[FrameFeatures](index.htm)**`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionFrameV2 other)`
*   `__init__ (self, QStyleOptionFrame other)`

### Members

*   `FrameFeatures **[features](qstyleoptionframev2.html#features-var)**`

* * *

## Detailed Description

该QStyleOptionFrameV2类是用来描述用于绘制Qt中4.1或更高的帧所必需的参数。

QStyleOptionFrameV2继承[QStyleOptionFrame](qstyleoptionframe.html)这是用于绘制几个内置的Qt部件，包括[QFrame](qframe.html)，[QGroupBox](qgroupbox.html)，[QLineEdit](qlineedit.html)和[QMenu](qmenu.html)。

该QStyleOptionFrameV2类的实例有[type](qstyleoption.html#type-varx) [SO_Frame](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)2 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

如果您创建自己的[QStyle](qstyle.html)子类，你应该同时处理[QStyleOptionFrame](qstyleoptionframe.html)和QStyleOptionFrameV2 。实现这一目标的方法之一是使用QStyleOptionFrameV2拷贝构造函数。例如：

```
     [QStyleOptionFrame](qstyleoptionframe.html) *option;

     if (const [QStyleOptionFrame](qstyleoptionframe.html) *frameOption =
            qstyleoption_cast<const [QStyleOptionFrame](qstyleoptionframe.html) *>(option)) {
         QStyleOptionFrameV2 frameOptionV2(*frameOption);

         // draw the frame using frameOptionV2
     }

```

在上面的例子：如果`frameOption`的版本号是1，[FrameFeature](qstyleoptionframev2.html#FrameFeature-enum)被设置为[None](qstyleoptionframev2.html#FrameFeature-enum)为`frameOptionV2`。如果`frameOption`的版本是2 ，构造函数会简单地复制`frameOption`的[FrameFeature](qstyleoptionframev2.html#FrameFeature-enum)值。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionFrameV2.FrameFeature
```

这个枚举变量描述了不同类型的功能框可以有。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionFrameV2.None` | `0x00` | 表示正常帧。 |
| `QStyleOptionFrameV2.Flat` | `0x01` | 表示一个平面框架。 |

该FrameFeatures类型是一个typedef为[QFlags](index.htm)\u003cFrameFeature\u003e 。它存储FrameFeature值的或组合。

```
QStyleOptionFrameV2.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionFrameV2.Version` | `2` | 2 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionframe.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionFrameV2.__init__ (self)
```

构造一个[QStyleOptionFrameV2](qstyleoptionframev2.html)对象。

```
QStyleOptionFrameV2.__init__ (self, QStyleOptionFrameV2 other)
```

构造一个[QStyleOptionFrameV2](qstyleoptionframev2.html)副本_other_样式选项。

```
QStyleOptionFrameV2.__init__ (self, QStyleOptionFrame other)
```

构造一个[QStyleOptionFrameV2](qstyleoptionframev2.html)副本_other_它可以是风格的选择[QStyleOptionFrameV2](qstyleoptionframev2.html) or [QStyleOptionFrame](qstyleoptionframe.html)类型。

如果_other_风格选择的版本是1 ，新样式选项的[FrameFeature](qstyleoptionframev2.html#FrameFeature-enum)值被设置为[QStyleOptionFrameV2.None](qstyleoptionframev2.html#FrameFeature-enum)。如果它的版本为2时，其[FrameFeature](qstyleoptionframev2.html#FrameFeature-enum)值被简单地复制到新的样式选项。

**See also** [version](qstyleoption.html#version-var)。

* * *

## Member Documentation

```
FrameFeatures features
```

[

这个变量保存的描述这个框架的功能的按位或。

](index.htm)

[**See also**](index.htm) [FrameFeature](qstyleoptionframev2.html#FrameFeature-enum)。