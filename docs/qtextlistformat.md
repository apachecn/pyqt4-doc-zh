# QTextListFormat Class Reference

## [[QtGui](index.htm) module]

该QTextListFormat类提供的格式设置信息列表[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextFormat](qtextformat.html)。

### Types

*   `enum Style { ListDisc, ListCircle, ListSquare, ListDecimal, ..., ListUpperRoman }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextListFormat)`
*   `int indent (self)`
*   `bool isValid (self)`
*   `QString numberPrefix (self)`
*   `QString numberSuffix (self)`
*   `setIndent (self, int aindent)`
*   `setNumberPrefix (self, QString np)`
*   `setNumberSuffix (self, QString ns)`
*   `setStyle (self, Style astyle)`
*   `Style style (self)`

* * *

## Detailed Description

该QTextListFormat类提供的格式设置信息列表[QTextDocument](qtextdocument.html)。

列表是由一个或多个项，表示为文本块。该列表的格式指定的项目在列表中出现。特别是，它确定每个项目的缩进和样式。

的项目的缩进是一个整数值，使得每个项被从左边界由一定量的偏移量。该值与读[indent](qtextlistformat.html#indent)（ ），并设置用[setIndent](qtextlistformat.html#setIndent)（ ） 。

用来装饰每个项目的样式设置与[setStyle](qtextlistformat.html#setStyle)（ ），并且可以读取与该[style](qtextlistformat.html#style)（）函数。该样式控制的要点，并用于列表中的项目编号方案的类型。请注意，使用十进制编号方案列表从1开始，而不是0开始计数。

样式属性可以设置为进一步配置列表项的外观，例如，在[ListNumberPrefix](qtextformat.html#Property-enum)和[ListNumberSuffix](qtextformat.html#Property-enum)属性可以被使用，以便它们显示为（1 ），（2 ），（3 ）等来定制在一个有序列表中使用的数字：

```
 QTextListFormat listFormat;

 listFormat.setStyle(QTextListFormat.ListDecimal);
 listFormat.setNumberPrefix("(");
 listFormat.setNumberSuffix(")");

 cursor.insertList(listFormat);

```

* * *

## Type Documentation

```
QTextListFormat.Style
```

这个枚举描述用来装饰清单项目符号：

| Constant | Value | Description |
| --- | --- | --- |
| `QTextListFormat.ListDisc` | `-1` | 实心圆 |
| `QTextListFormat.ListCircle` | `-2` | 空圈 |
| `QTextListFormat.ListSquare` | `-3` | 一个填充的正方形 |
| `QTextListFormat.ListDecimal` | `-4` | 按升序排列十进制值 |
| `QTextListFormat.ListLowerAlpha` | `-5` | 按字母顺序排列小写拉丁字符 |
| `QTextListFormat.ListUpperAlpha` | `-6` | 按字母顺序排列大写拉丁字符 |
| `QTextListFormat.ListLowerRoman` | `-7` | 小写罗马数字（截至4999项仅支持） |
| `QTextListFormat.ListUpperRoman` | `-8` | 大写罗马数字（截至4999项仅支持） |

* * *

## Method Documentation

```
QTextListFormat.__init__ (self)
```

构造一个新的列表格式的对象。

```
QTextListFormat.__init__ (self, QTextListFormat)
```

```
int QTextListFormat.indent (self)
```

返回列表格式的缩进。压痕乘以[QTextDocument.indentWidth](qtextdocument.html#indentWidth-prop)财产得到有效的缩进以像素为单位。

**See also** [setIndent](qtextlistformat.html#setIndent)（ ） 。

```
bool QTextListFormat.isValid (self)
```

返回True如果此列表的格式是有效的，否则返回False 。

```
QString QTextListFormat.numberPrefix (self)
```

返回列表格式的号码前缀。

此功能被引入Qt的4.8 。

**See also** [setNumberPrefix](qtextlistformat.html#setNumberPrefix)（ ） 。

```
QString QTextListFormat.numberSuffix (self)
```

返回列表格式的数字后缀。

此功能被引入Qt的4.8 。

**See also** [setNumberSuffix](qtextlistformat.html#setNumberSuffix)（ ） 。

```
QTextListFormat.setIndent (self, int aindent)
```

设置列表格式的_indentation_。压痕乘以[QTextDocument.indentWidth](qtextdocument.html#indentWidth-prop)财产得到有效的缩进以像素为单位。

**See also** [indent](qtextlistformat.html#indent)（ ） 。

```
QTextListFormat.setNumberPrefix (self, QString np)
```

设置列表格式的号码前缀由指定的字符串_numberPrefix_。这可以用于所有排序的列表类型。它不会对未排序的列表类型的任何影响。

默认前缀是一个空字符串。

此功能被引入Qt的4.8 。

**See also** [numberPrefix](qtextlistformat.html#numberPrefix)（ ） 。

```
QTextListFormat.setNumberSuffix (self, QString ns)
```

设置列表格式的数字后缀由指定的字符串_numberSuffix_。这可以用于所有排序的列表类型。它不会对未排序的列表类型的任何影响。

默认的后缀是“ 。”

此功能被引入Qt的4.8 。

**See also** [numberSuffix](qtextlistformat.html#numberSuffix)（ ） 。

```
QTextListFormat.setStyle (self, Style astyle)
```

设置列表格式的_style_。

**See also** [style](qtextlistformat.html#style)（）和[Style](qtextlistformat.html#Style-enum)。

```
Style QTextListFormat.style (self)
```

[

返回列表格式的风格。

](qtextlistformat.html#Style-enum)

[**See also**](qtextlistformat.html#Style-enum) [setStyle](qtextlistformat.html#setStyle)（）和[Style](qtextlistformat.html#Style-enum)。