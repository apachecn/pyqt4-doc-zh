# QFontComboBox Class Reference

## [[QtGui](index.htm) module]

该QFontComboBox widget是一个组合框，让用户选择字体系列。[More...](#details)

继承[QComboBox](qcombobox.html)。

### Types

*   `enum FontFilter { AllFonts, ScalableFonts, NonScalableFonts, MonospacedFonts, ProportionalFonts }`
*   `class **[FontFilters](index.htm)**`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `QFont currentFont (self)`
*   `bool event (self, QEvent e)`
*   `FontFilters fontFilters (self)`
*   `setCurrentFont (self, QFont f)`
*   `setFontFilters (self, FontFilters filters)`
*   `setWritingSystem (self, QFontDatabase.WritingSystem)`
*   `QSize sizeHint (self)`
*   `QFontDatabase.WritingSystem writingSystem (self)`

### Qt Signals

*   `void currentFontChanged (const QFont&)`

* * *

## Detailed Description

该QFontComboBox widget是一个组合框，让用户选择字体系列。

组合框填入的字体系列名称，如宋体，黑体，和Times New Roman字母顺序列表。家族名称显示使用实际的字体在可能的情况。对于字体，如符号，这里的名字是不能表示在字体本身，显示的字体的样本旁姓。

QFontComboBox经常用在工具条，在用结合[QComboBox](qcombobox.html)用于控制字体大小和两个[QToolButton](qtoolbutton.html)S代表粗体和斜体。

当用户选择一个新的字体，该[currentFontChanged](qfontcombobox.html#currentFontChanged)（ ）信号除了发射[currentIndexChanged](qcombobox.html#currentIndexChanged)（ ） 。

Call [setWritingSystem](qfontcombobox.html#writingSystem-prop)（ ）来告诉QFontComboBox仅显示支持一个给定的文字系统字体，[setFontFilters](qfontcombobox.html#fontFilters-prop)（）来过滤掉某些类型的字体作为例如非可缩放字体或等宽字体。

![Screenshot of QFontComboBox on Windows XP](../img/windowsxp-fontcombobox.png)

* * *

## Type Documentation

```
QFontComboBox.FontFilter
```

这个枚举可用于仅在字体组合框中显示某些类型的字体。

| Constant | Value | Description |
| --- | --- | --- |
| `QFontComboBox.AllFonts` | `0` | 显示所有字体 |
| `QFontComboBox.ScalableFonts` | `0x1` | 显示可缩放字体 |
| `QFontComboBox.NonScalableFonts` | `0x2` | 显示非可缩放字体 |
| `QFontComboBox.MonospacedFonts` | `0x4` | 显示等宽字体 |
| `QFontComboBox.ProportionalFonts` | `0x8` | 显示比例字体 |

该FontFilters类型是一个typedef为[QFlags](index.htm)\u003cFontFilter\u003e 。它存储FontFilter值的或组合。

* * *

## Method Documentation

```
QFontComboBox.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个组合框的字体用给定的_parent_。

```
QFont QFontComboBox.currentFont (self)
```

[

```
bool QFontComboBox.event (self, QEvent e)
```

](qfont.html)

[从重新实现](qfont.html)[QObject.event](qobject.html#event)（ ） 。

```
FontFilters QFontComboBox.fontFilters (self)
```

[

```
QFontComboBox.setCurrentFont (self, QFont f)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentFont(const QFont&)`。

```
QFontComboBox.setFontFilters (self, FontFilters filters)
```

```
QFontComboBox.setWritingSystem (self, QFontDatabase.WritingSystem)
```

](index.htm)

```
QSize QFontComboBox.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QFontDatabase.WritingSystem QFontComboBox.writingSystem (self)
```

[

* * *

## Qt Signal Documentation

```
void currentFontChanged (const QFont&)
```

这是该信号的默认超载。

这个信号被发射时的当前字体的变化，与新_font_。

](qfontdatabase.html#WritingSystem-enum)

[**See also**](qfontdatabase.html#WritingSystem-enum) [currentFont](qfontcombobox.html#currentFont-prop)。