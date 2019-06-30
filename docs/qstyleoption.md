# QStyleOption Class Reference

## [[QtGui](index.htm) module]

该QStyleOption类存储所使用的参数[QStyle](qstyle.html)功能。[More...](#details)

通过继承[QStyleOptionButton](qstyleoptionbutton.html)，[QStyleOptionComplex](qstyleoptioncomplex.html)，[QStyleOptionDockWidget](qstyleoptiondockwidget.html)，[QStyleOptionFocusRect](qstyleoptionfocusrect.html)，[QStyleOptionFrame](qstyleoptionframe.html)，[QStyleOptionGraphicsItem](qstyleoptiongraphicsitem.html)，[QStyleOptionHeader](qstyleoptionheader.html)，[QStyleOptionMenuItem](qstyleoptionmenuitem.html)，[QStyleOptionProgressBar](qstyleoptionprogressbar.html)，[QStyleOptionRubberBand](qstyleoptionrubberband.html)，[QStyleOptionTab](qstyleoptiontab.html)，[QStyleOptionTabBarBase](qstyleoptiontabbarbase.html)，[QStyleOptionTabWidgetFrame](qstyleoptiontabwidgetframe.html)，[QStyleOptionToolBar](qstyleoptiontoolbar.html)，[QStyleOptionToolBox](qstyleoptiontoolbox.html)和[QStyleOptionViewItem](qstyleoptionviewitem.html)。

### Types

*   `enum OptionType { SO_Default, SO_FocusRect, SO_Button, SO_Tab, ..., SO_CustomBase }`
*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self, int version = QStyleOption.Version, int type = QStyleOption.SO_Default)`
*   `__init__ (self, QStyleOption other)`
*   `init (self, QWidget w)`
*   `initFrom (self, QWidget w)`

### Members

*   `Qt.LayoutDirection **[direction](qstyleoption.html#direction-var)**`
*   `QFontMetrics **[fontMetrics](qstyleoption.html#fontMetrics-var)**`
*   `QPalette **[palette](qstyleoption.html#palette-var)**`
*   `QRect **[rect](qstyleoption.html#rect-var)**`
*   `QStyle.State **[state](qstyleoption.html#state-var)**`
*   `int **[type](qstyleoption.html#type-var)**`
*   `int **[version](qstyleoption.html#version-var)**`

* * *

## Detailed Description

该QStyleOption类存储所使用的参数[QStyle](qstyle.html)功能。

QStyleOption及其子类包含的所有信息，[QStyle](qstyle.html)功能需要绘制的图形元素。

出于性能方面的原因，也有一些成员函数和访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

的调用者[QStyle](qstyle.html)功能通常在栈上创建QStyleOption对象。这种结合Qt的广泛使用[implicit sharing](index.htm)对于类型如[QString](qstring.html)，[QPalette](qpalette.html)和[QColor](qcolor.html)确保没有内存分配不必要的发生。

下面的代码片段显示了如何使用特定QStyleOption子类来绘制一个按钮：

```
 void MyPushButton.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     [QStyleOptionButton](qstyleoptionbutton.html) option;
     option.initFrom(this);
     option.state = isDown() ? [QStyle](qstyle.html).State_Sunken : [QStyle](qstyle.html).State_Raised;
     if (isDefault())
         option.features |= [QStyleOptionButton](qstyleoptionbutton.html).DefaultButton;
     option.text = text();
     option.icon = icon();

     [QPainter](qpainter.html) painter(this);
     style()->drawControl([QStyle](qstyle.html).CE_PushButton, &option, &painter, this);
 }

```

在我们的例子中，控制是一个[QStyle.CE_PushButton](qstyle.html#ControlElement-enum)，并根据该[QStyle.drawControl](qstyle.html#drawControl)（ ）文档对应的类是[QStyleOptionButton](qstyleoptionbutton.html)。

当重新实现[QStyle](qstyle.html)它接受一个QStyleOption参数功能，你经常需要转换QStyleOption到一个子类。为安全起见，你可以使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ），以确保该指针的类型是正确的。例如：

```
 void MyStyle.drawPrimitive(PrimitiveElement element,
                             const QStyleOption *option,
                             [QPainter](qpainter.html) *painter,
                             const [QWidget](qwidget.html) *widget)
 {
     if (element == PE_FrameFocusRect) {
         const [QStyleOptionFocusRect](qstyleoptionfocusrect.html) *focusRectOption =
                 qstyleoption_cast<const [QStyleOptionFocusRect](qstyleoptionfocusrect.html) *>(option);
         if (focusRectOption) {
             // ...
         }
     }
     // ...
 }

```

该[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）函数将返回0，如果该对象，其中`option`点是正确的类型。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOption.OptionType
```

此枚举在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOption.SO_Button` | `2` | [QStyleOptionButton](qstyleoptionbutton.html) |
| `QStyleOption.SO_ComboBox` | ？ | [QStyleOptionComboBox](qstyleoptioncombobox.html) |
| `QStyleOption.SO_Complex` | `0xf0000` | [QStyleOptionComplex](qstyleoptioncomplex.html) |
| `QStyleOption.SO_Default` | `0` | [QStyleOption](qstyleoption.html) |
| `QStyleOption.SO_DockWidget` | `10` | [QStyleOptionDockWidget](qstyleoptiondockwidget.html) |
| `QStyleOption.SO_FocusRect` | `1` | [QStyleOptionFocusRect](qstyleoptionfocusrect.html) |
| `QStyleOption.SO_Frame` | `5` | [QStyleOptionFrame](qstyleoptionframe.html) [QStyleOptionFrameV2](qstyleoptionframev2.html) |
| `QStyleOption.SO_GraphicsItem` | `17` | [QStyleOptionGraphicsItem](qstyleoptiongraphicsitem.html) |
| `QStyleOption.SO_GroupBox` | ？ | [QStyleOptionGroupBox](qstyleoptiongroupbox.html) |
| `QStyleOption.SO_Header` | `8` | [QStyleOptionHeader](qstyleoptionheader.html) |
| `QStyleOption.SO_MenuItem` | `4` | [QStyleOptionMenuItem](qstyleoptionmenuitem.html) |
| `QStyleOption.SO_ProgressBar` | `6` | [QStyleOptionProgressBar](qstyleoptionprogressbar.html) [QStyleOptionProgressBarV2](qstyleoptionprogressbarv2.html) |
| `QStyleOption.SO_RubberBand` | `15` | [QStyleOptionRubberBand](qstyleoptionrubberband.html) |
| `QStyleOption.SO_SizeGrip` | ？ | [QStyleOptionSizeGrip](qstyleoptionsizegrip.html) |
| `QStyleOption.SO_Slider` | ？ | [QStyleOptionSlider](qstyleoptionslider.html) |
| `QStyleOption.SO_SpinBox` | ？ | [QStyleOptionSpinBox](qstyleoptionspinbox.html) |
| `QStyleOption.SO_Tab` | `3` | [QStyleOptionTab](qstyleoptiontab.html) |
| `QStyleOption.SO_TabBarBase` | `14` | [QStyleOptionTabBarBase](qstyleoptiontabbarbase.html) |
| `QStyleOption.SO_TabWidgetFrame` | `13` | [QStyleOptionTabWidgetFrame](qstyleoptiontabwidgetframe.html) |
| `QStyleOption.SO_TitleBar` | ？ | [QStyleOptionTitleBar](qstyleoptiontitlebar.html) |
| `QStyleOption.SO_ToolBar` | `16` | [QStyleOptionToolBar](qstyleoptiontoolbar.html) |
| `QStyleOption.SO_ToolBox` | `7` | [QStyleOptionToolBox](qstyleoptiontoolbox.html) |
| `QStyleOption.SO_ToolButton` | ？ | [QStyleOptionToolButton](qstyleoptiontoolbutton.html) |
| `QStyleOption.SO_ViewItem` | `12` | [QStyleOptionViewItem](qstyleoptionviewitem.html)（在采访中使用） |

下面的值用于自定义控件：

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOption.SO_CustomBase` | `0xf00` | 保留自定义QStyleOptions ;所有自定义的控件的值必须高于这个值 |
| `QStyleOption.SO_ComplexCustomBase` | `0xf000000` | 保留自定义QStyleOptions ;所有自定义复杂的控件的值必须高于这个值 |

一些样式选项用于各种[Qt3Support](index.htm)控制：

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOption.SO_Q3DockWindow` | `9` | [QStyleOptionQ3DockWindow](index.htm) |
| `QStyleOption.SO_Q3ListView` | ？ | [QStyleOptionQ3ListView](index.htm) |
| `QStyleOption.SO_Q3ListViewItem` | `11` | [QStyleOptionQ3ListViewItem](index.htm) |

**See also** [type](qstyleoption.html#type-varx)。

```
QStyleOption.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOption.Type` | `SO_Default` | 风格选择该类型提供（[SO_Default](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoption.html#StyleOptionVersion-enum)。

```
QStyleOption.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOption.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoption.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOption.__init__ (self, int version = QStyleOption.Version, int type = QStyleOption.SO_Default)
```

构造一个[QStyleOption](qstyleoption.html)用指定的_version_和_type_。

该版本具有没有特殊含义[QStyleOption](qstyleoption.html)它可以用于由子类不同版本的相同选项类型之间进行区分。

该[state](qstyleoption.html#state-var)成员变量被初始化为[QStyle.State_None](qstyle.html#StateFlag-enum)。

**See also** [version](qstyleoption.html#version-var)和[type](qstyleoption.html#type-varx)。

```
QStyleOption.__init__ (self, QStyleOption other)
```

构造的副本_other_。

```
QStyleOption.init (self, QWidget w)
```

```
QStyleOption.initFrom (self, QWidget w)
```

初始化[state](qstyleoption.html#state-var)，[direction](qstyleoption.html#direction-var)，[rect](qstyleoption.html#rect-var)，[palette](qstyleoption.html#palette-var)和[fontMetrics](qstyleoption.html#fontMetrics-var)基于所指定的成员变量_widget_。

这是一个方便的功能，成员变量也可以手动初始化。

这个函数是Qt 4.1中引入。

**See also** [QWidget.layoutDirection](qwidget.html#layoutDirection-prop)（ ）[QWidget.rect](qwidget.html#rect-prop)（ ）[QWidget.palette](qwidget.html#palette-prop)（）和[QWidget.fontMetrics](qwidget.html#fontMetrics)（ ） 。

* * *

## Member Documentation

```
Qt.LayoutDirection direction
```

[

这个变量保存绘制控件中的文本时，应该使用文本布局方向。

](qt.html#LayoutDirection-enum)

[默认情况下，布局方向](qt.html#LayoutDirection-enum)[Qt.LeftToRight](qt.html#LayoutDirection-enum)。

**See also** [initFrom](qstyleoption.html#initFrom)（ ） 。

```
QFontMetrics fontMetrics
```

[

这个变量保存绘制控件中的文本时，应使用的字体度量。

默认情况下，应用程序的默认字体。

](qfontmetrics.html)

[**See also**](qfontmetrics.html) [initFrom](qstyleoption.html#initFrom)（ ） 。

```
QPalette palette
```

[

这个变量保存绘画的控制时，应使用的调色板。

默认情况下，应用程序的默认调色板使用。

](qpalette.html)

[**See also**](qpalette.html) [initFrom](qstyleoption.html#initFrom)（ ） 。

```
QRect rect
```

[

这个变量保存了应被用于各种计算和画的面积。

](qrect.html)

[这可以有不同类型的元素不同的含义。例如，对于一](qrect.html)[QStyle.CE_PushButton](qstyle.html#ControlElement-enum)元件便对整个按钮的矩形区域，而对于一个[QStyle.CE_PushButtonLabel](qstyle.html#ControlElement-enum)元素它也不过为按钮标籤的区域。

默认值是空的矩形，即用宽度和高度设置为0的矩形。

**See also** [initFrom](qstyleoption.html#initFrom)（ ） 。

```
QStyle.State state
```

[

这个变量保存所绘制控件时使用的风格标志。

](index.htm)

[缺省值是](index.htm)[QStyle.State_None](qstyle.html#StateFlag-enum)。

**See also** [initFrom](qstyleoption.html#initFrom)（ ）[QStyle.drawPrimitive](qstyle.html#drawPrimitive)（ ）[QStyle.drawControl](qstyle.html#drawControl)（ ）[QStyle.drawComplexControl](qstyle.html#drawComplexControl)（）和[QStyle.State](qstyle.html#StateFlag-enum)。

```
int type
```

```
int version
```

这个变量保存样式选项的版本。

这个值可以由子类用于实现扩展不会破坏兼容性。如果使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ）函数，你通常并不需要检查它。

默认值是1。