# QToolTip Class Reference

## [[QtGui](index.htm) module]

该QToolTip类提供工具提示（气球帮助）任何部件。[More...](#details)

### Methods

*   `__init__ (self, QToolTip)`

### Static Methods

*   `QFont font ()`
*   `hideText ()`
*   `bool isVisible ()`
*   `QPalette palette ()`
*   `setFont (QFont)`
*   `setPalette (QPalette)`
*   `showText (QPoint pos, QString text, QWidget widget = None)`
*   `showText (QPoint pos, QString text, QWidget w, QRect rect)`
*   `QString text ()`

* * *

## Detailed Description

该QToolTip类提供工具提示（气球帮助）任何部件。

尖端是一个简短的一段文字，提醒小工具的功能的用户。它被画在马上一个与众不同的黑色在黄色的色彩组合给定位置下方。尖端可以是任何[rich text](qtextedit.html)格式化字符串。

在工具提示中显示的富文本是隐式自动换行，除非有不同的规定`&lt;p style='white-space:pre'&gt;`。

设置控件的工具提示最简单和最常用的方法是通过调用其[QWidget.setToolTip](qwidget.html#toolTip-prop)（）函数。

另外，也可以显示不同的工具提示小窗口的不同区域，通过使用[QHelpEvent](qhelpevent.html)类型[QEvent.ToolTip](qevent.html#Type-enum)。拦截在你的widget的帮助事件[event()](qwidget.html#event)函数和调用[QToolTip.showText](qtooltip.html#showText)（ ）与要显示的文本。该[Tooltips](index.htm)例子说明了这种技术。

如果您呼叫[QToolTip.hideText](qtooltip.html#hideText)（） ，或[QToolTip.showText](qtooltip.html#showText)（ ）一个空字符串，作为一个结果[ToolTip](qevent.html#Type-enum)事件你也应该调用[ignore()](qevent.html#ignore)该事件，以表示你不想启动任何提示的具体模式。

需要注意的是，如果你想显示工具提示中的项目视图，模型/视图结构提供的功能来设置项的工具提示，例如，在[QTableWidgetItem.setToolTip](qtablewidgetitem.html#setToolTip)（）函数。不过，如果你想提供一个项目视图自定义工具提示，您必须截取的帮助事件[QAbstractItemView.viewportEvent](qabstractitemview.html#viewportEvent)（ ）函数，并自己处理。

默认的工具提示的颜色和字体可以被定制[setPalette](qtooltip.html#setPalette)（）和[setFont](qtooltip.html#setFont)（ ） 。当工具提示目前正在展出，[isVisible](qtooltip.html#isVisible)（ ）返回True，[text](qtooltip.html#text)（ ）当前可见的文本。

**Note:**工具提示使用的颜色不活跃组[QPalette](qpalette.html)，因为工具提示未激活的窗口。

* * *

## Method Documentation

```
QToolTip.__init__ (self, QToolTip)
```

```
QFont QToolTip.font ()
```

[

返回用于渲染工具提示的字体。

这个函数中引入了Qt 4.2中。

](qfont.html)

[**See also**](qfont.html) [setFont](qtooltip.html#setFont)（ ） 。

```
QToolTip.hideText ()
```

隐藏工具提示。这是一样的调用[showText](qtooltip.html#showText)（ ）用一个空字符串。

这个函数中引入了Qt 4.2中。

**See also** [showText](qtooltip.html#showText)（ ） 。

```
bool QToolTip.isVisible ()
```

如果这是提示当前显示返回True。

此功能被引入Qt的4.4 。

**See also** [showText](qtooltip.html#showText)（ ） 。

```
QPalette QToolTip.palette ()
```

[

返回用于渲染工具提示的调色板。

](qpalette.html)

[**Note:**工具提示使用的颜色不活跃组](qpalette.html)[QPalette](qpalette.html)，因为工具提示未激活的窗口。

**See also** [setPalette](qtooltip.html#setPalette)（ ） 。

```
QToolTip.setFont (QFont)
```

设置_font_用于渲染工具提示。

这个函数中引入了Qt 4.2中。

**See also** [font](qtooltip.html#font)（ ） 。

```
QToolTip.setPalette (QPalette)
```

设置_palette_用于渲染工具提示。

**Note:**工具提示使用的颜色不活跃组[QPalette](qpalette.html)，因为工具提示未激活的窗口。

这个函数中引入了Qt 4.2中。

**See also** [palette](qtooltip.html#palette)（ ） 。

```
QToolTip.showText (QPoint pos, QString text, QWidget widget = None)
```

Shows _text_作为一个工具提示，与全球地位_pos_作为兴趣点。工具提示会显示有一个特定的平台从这个兴趣点偏移来。

如果您指定一个非空的矩形一角将尽快当你移动你的光标移出该区域的隐藏。

该_rect_是在你与指定窗口小部件的坐标_w_。如果_rect_是不是空的，你必须指定一个小部件。否则，这个参数可以是0 ，但它是用来确定多头系统相应的屏幕。

If _text_是空的刀尖是隐藏的。如果文本是相同的当前显示工具提示，针尖将_not_移动。您可以先躲在一角有一个空的文本，然后显示在新的位置，新尖强制移动。

```
QToolTip.showText (QPoint pos, QString text, QWidget w, QRect rect)
```

这是一个重载函数。

这类似于调用QToolTip.showText （_pos_，_text_，_w_，查阅QRect （））

```
QString QToolTip.text ()
```

返回的提示文本，如果提示是可见的，或一个空字符串，如果一个工具提示是不可见的。

此功能被引入Qt的4.4 。