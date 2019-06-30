# QTextBoundaryFinder Class Reference

## [[QtCore](index.htm) module]

该QTextBoundaryFinder类提供了查找Unicode文本的边界在一个字符串的方法。[More...](#details)

### Types

*   `enum BoundaryReason { NotAtBoundary, StartWord, EndWord }`
*   `class **[BoundaryReasons](index.htm)**`
*   `enum BoundaryType { Grapheme, Word, Line, Sentence }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextBoundaryFinder other)`
*   `__init__ (self, BoundaryType type, QString string)`
*   `BoundaryReasons boundaryReasons (self)`
*   `bool isAtBoundary (self)`
*   `bool isValid (self)`
*   `int position (self)`
*   `setPosition (self, int position)`
*   `QString string (self)`
*   `toEnd (self)`
*   `int toNextBoundary (self)`
*   `int toPreviousBoundary (self)`
*   `toStart (self)`
*   `BoundaryType type (self)`

* * *

## Detailed Description

该QTextBoundaryFinder类提供了查找Unicode文本的边界在一个字符串的方法。

QTextBoundaryFinder可以发现Unicode文本的边界在一个字符串中，类似的Unicode文本边界规范（见http://www.unicode.org/reports/tr29/tr29-11.html ） 。

QTextBoundaryFinder可以在一个操作[QString](qstring.html)在这取决于价值四种可能的方式_BoundaryType_。

Unicode字符是什么单位的用户认为作为语言的字符或基本单元构成这里称为字字集群。这两个Unicode字符' A'+分音符做，例如形成一个字形集群作为用户他们认为作为一个字符，但它是由两个Unicode代码点来表示这种情况。

字边界是有定位什么语言认为是一个单词的开始和结束。

换行符边界的地方给一个换行符可能发生和句子边界将显示整个句子的开头和结尾可能的地方。

在字符串的第一个位置始终是一个有效的边界，指的是位置的第一个字符之前。在字符串的长度的最后一个位置也是有效的，最后一个字符之后指的位置。

* * *

## Type Documentation

```
QTextBoundaryFinder.BoundaryReason
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextBoundaryFinder.NotAtBoundary` | `0` | 边界取景器是不是在边界位置。 |
| `QTextBoundaryFinder.StartWord` | `1` | 边界取景器是在一个单词的开头。 |
| `QTextBoundaryFinder.EndWord` | `2` | 边界取景器是在一个字的结尾。 |

该BoundaryReasons类型是一个typedef为[QFlags](index.htm)\u003cBoundaryReason\u003e 。它存储BoundaryReason值的或组合。

```
QTextBoundaryFinder.BoundaryType
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextBoundaryFinder.Grapheme` | `0` | 发现一个字形这是最小的边界。它包括字母，点状标记，数字等。 |
| `QTextBoundaryFinder.Word` | `1` | 找到一个词。 |
| `QTextBoundaryFinder.Line` | `2` | 查找打破文本分成多行可能的位置。 |
| `QTextBoundaryFinder.Sentence` | `3` | 找到句子的界限。这些措施包括句号，问号等。 |

* * *

## Method Documentation

```
QTextBoundaryFinder.__init__ (self)
```

构造一个无效的[QTextBoundaryFinder](qtextboundaryfinder.html)对象。

```
QTextBoundaryFinder.__init__ (self, QTextBoundaryFinder other)
```

副本[QTextBoundaryFinder](qtextboundaryfinder.html)反对，_other_。

```
QTextBoundaryFinder.__init__ (self, BoundaryType type, QString string)
```

创建[QTextBoundaryFinder](qtextboundaryfinder.html)对象_type_操作上_string_。

```
BoundaryReasons QTextBoundaryFinder.boundaryReasons (self)
```

[

返回到所选择的当前位置为界的原因边界取景器。

```
bool QTextBoundaryFinder.isAtBoundary (self)
```

](index.htm)

[返回True如果对象的](index.htm)[position](qtextboundaryfinder.html#position)（ ）是目前一个有效的文本边界。

```
bool QTextBoundaryFinder.isValid (self)
```

返回True如果文字边界发现者是有效的，否则返回False 。默认[QTextBoundaryFinder](qtextboundaryfinder.html)是无效的。

```
int QTextBoundaryFinder.position (self)
```

返回的当前位置[QTextBoundaryFinder](qtextboundaryfinder.html)。

的范围是从0 （在字符串的开头）到字符串包容的长度。

**See also** [setPosition](qtextboundaryfinder.html#setPosition)（ ） 。

```
QTextBoundaryFinder.setPosition (self, int position)
```

设置的当前位置[QTextBoundaryFinder](qtextboundaryfinder.html)至_position_。

If _position_是出界，它必将唯一有效的位置。在这种情况下，有效的位置是从0到字符串包的长度。

**See also** [position](qtextboundaryfinder.html#position)（ ） 。

```
QString QTextBoundaryFinder.string (self)
```

返回字符串的[QTextBoundaryFinder](qtextboundaryfinder.html)对象运行在。

```
QTextBoundaryFinder.toEnd (self)
```

移动取景到字符串的结尾。这相当于setPosition方法（和string.length （））。

**See also** [setPosition](qtextboundaryfinder.html#setPosition)（）和[position](qtextboundaryfinder.html#position)（ ） 。

```
int QTextBoundaryFinder.toNextBoundary (self)
```

移动[QTextBoundaryFinder](qtextboundaryfinder.html)到下一个边界位置，并返回该位置。

返回-1，如果没有下边界。

```
int QTextBoundaryFinder.toPreviousBoundary (self)
```

移动[QTextBoundaryFinder](qtextboundaryfinder.html)先前的边界位置，并返回该位置。

返回-1，如果没有以前的边界。

```
QTextBoundaryFinder.toStart (self)
```

移动取景器的字符串的开头。这相当于setPosition方法（0）。

**See also** [setPosition](qtextboundaryfinder.html#setPosition)（）和[position](qtextboundaryfinder.html#position)（ ） 。

```
BoundaryType QTextBoundaryFinder.type (self)
```

[](qtextboundaryfinder.html#BoundaryType-enum)

[返回的类型](qtextboundaryfinder.html#BoundaryType-enum)[QTextBoundaryFinder](qtextboundaryfinder.html)。