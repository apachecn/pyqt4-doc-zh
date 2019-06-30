# QTextItem Class Reference

## [[QtGui](index.htm) module]

该QTextItem类提供了所有在自定义绘图引擎绘制文本所需的信息。[More...](#details)

### Types

*   `enum RenderFlag { RightToLeft, Overline, Underline, StrikeOut }`
*   `class **[RenderFlags](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextItem)`
*   `float ascent (self)`
*   `float descent (self)`
*   `QFont font (self)`
*   `RenderFlags renderFlags (self)`
*   `QString text (self)`
*   `float width (self)`

* * *

## Detailed Description

该QTextItem类提供了所有在自定义绘图引擎绘制文本所需的信息。

当你重新实现自己的绘图引擎，你必须重新实现[QPaintEngine.drawTextItem](qpaintengine.html#drawTextItem)（ ） ，一个函数，它接受一个QTextItem作为它的一个参数。

* * *

## Type Documentation

```
QTextItem.RenderFlag
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextItem.RightToLeft` | `0x1` | 呈现由右至左的文本。 |
| `QTextItem.Overline` | `0x10` | 涂料上面的文字行。 |
| `QTextItem.Underline` | `0x20` | 涂料在文本下一条线。 |
| `QTextItem.StrikeOut` | `0x40` | 通过文字描绘出线条。 |

该RenderFlags类型是一个typedef为[QFlags](index.htm)\u003cRenderFlag\u003e 。它存储RenderFlag值的或组合。

* * *

## Method Documentation

```
QTextItem.__init__ (self)
```

```
QTextItem.__init__ (self, QTextItem)
```

```
float QTextItem.ascent (self)
```

对应于[ascent](qfontmetrics.html#ascent)的一段文字所绘制的。

```
float QTextItem.descent (self)
```

对应于[descent](qfontmetrics.html#descent)的一段文字所绘制的。

```
QFont QTextItem.font (self)
```

[

返回应该被用来绘制文本的字体。

](qfont.html)

```
RenderFlags QTextItem.renderFlags (self)
```

[

返回用于渲染的标志。

```
QString QTextItem.text (self)
```

返回一个应绘制的文本。

```
float QTextItem.width (self)
```

指定要绘制的文本的总宽度。

](index.htm)