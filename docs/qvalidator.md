# QValidator Class Reference

## [[QtGui](index.htm) module]

该QValidator类提供了输入文本的验证。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QDoubleValidator](qdoublevalidator.html)，[QIntValidator](qintvalidator.html)和[QRegExpValidator](qregexpvalidator.html)。

### Types

*   `enum State { Invalid, Intermediate, Acceptable }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QString input fixup (self, QString input)`
*   `fixup (self, QString)`
*   `QLocale locale (self)`
*   `setLocale (self, QLocale locale)`
*   `(State, QString, int) validate (self, QString, int)`
*   `(State, int) validate (self, QString, int)`

* * *

## Detailed Description

该QValidator类提供了输入文本的验证。

类本身是抽象的。两个子类，[QIntValidator](qintvalidator.html)和[QDoubleValidator](qdoublevalidator.html)，提供基本的数值范围检查，并[QRegExpValidator](qregexpvalidator.html)使用自定义的正则表达式提供了一般的检查。

如果内置的验证是不够的，你可以继承QValidator 。这个类有两个虚函数：[validate](qvalidator.html#validate)（）和[fixup](qvalidator.html#fixup)（ ） 。

[validate](qvalidator.html#validate)（ ）必须由每个子类实现。它返回[Invalid](qvalidator.html#State-enum)，[Intermediate](qvalidator.html#State-enum) or [Acceptable](qvalidator.html#State-enum)根据其参数是否有效（有效的子类的定义） 。

这三种状态需要一些解释。一个[Invalid](qvalidator.html#State-enum)字符串是_clearly_无效。[Intermediate](qvalidator.html#State-enum)是不太明显的：有效性的概念难以适用时该字符串是不完整的（仍在编辑） 。 QValidator定义[Intermediate](qvalidator.html#State-enum)作为一个字符串，既不是明显无效，也不接受作为最终结果的财产。[Acceptable](qvalidator.html#State-enum)表示该字符串是可接受作为最终结果。有人可能会说，任何字符串，它是一个项目在一个合理的中间状态[Acceptable](qvalidator.html#State-enum)字符串是[Intermediate](qvalidator.html#State-enum)。

下面是一些例子：

*   For a line edit that accepts integers from 10 to 1000 inclusive, 42 and 123 are [Acceptable](qvalidator.html#State-enum), the empty string and 5 are [Intermediate](qvalidator.html#State-enum), and "asdf" and 1114 is [Invalid](qvalidator.html#State-enum).
*   For an editable combobox that accepts URLs, any well-formed URL is [Acceptable](qvalidator.html#State-enum), "http://example.com/," is [Intermediate](qvalidator.html#State-enum) (it might be a cut and paste action that accidentally took in a comma at the end), the empty string is [Intermediate](qvalidator.html#State-enum) (the user might select and delete all of the text in preparation for entering a new URL) and "http:///./" is [Invalid](qvalidator.html#State-enum).
*   For a spin box that accepts lengths, "11cm" and "1in" are [Acceptable](qvalidator.html#State-enum), "11" and the empty string are [Intermediate](qvalidator.html#State-enum), and "http://example.com" and "hour" are [Invalid](qvalidator.html#State-enum).

[fixup](qvalidator.html#fixup)（ ）用于验证，可以修复一些用户错误。默认实现不执行任何操作。[QLineEdit](qlineedit.html)例如，将调用[fixup](qvalidator.html#fixup)（ ）如果用户按下Enter键（或Return ）和内容目前无效。这允许[fixup](qvalidator.html#fixup)（ ）函数执行一些魔法使的一个机会[Invalid](qvalidator.html#State-enum)串[Acceptable](qvalidator.html#State-enum)。

一个验证器有一个区域，设置[setLocale](qvalidator.html#setLocale)（ ） 。它通常被用来解析本地化数据。例如，[QIntValidator](qintvalidator.html)和[QDoubleValidator](qdoublevalidator.html)用它来解析整数和双精度的本地化表示。

QValidator通常用于[QLineEdit](qlineedit.html)，[QSpinBox](qspinbox.html)和[QComboBox](qcombobox.html)。

* * *

## Type Documentation

```
QValidator.State
```

这个枚举类型定义了一个验证字符串可以存在的状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QValidator.Invalid` | `0` | 该字符串是_clearly_无效。 |
| `QValidator.Intermediate` | `1` | 该字符串是一个合理的中间值。 |
| `QValidator.Acceptable` | `2` | 该字符串是可以接受的最终结果，即它是有效的。 |

* * *

## Method Documentation

```
QValidator.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

建立验证程序。该_parent_参数被传递到[QObject](qobject.html)构造函数。

```
QString input QValidator.fixup (self, QString input)
```

这个函数试图改变_input_根据该验证器的规则是有效的。它必须不会导致一个有效的字符串：这个函数的调用者必须重新测试后，默认不做任何事情。

此函数的重新实现可以改变_input_即使他们不出示有效的字符串。例如， ISBN校验器可能需要删除每一个字符，除了数字和“ - ” ，即使结果仍然没有有效的ISBN ，一个姓验证器可能会想从字符串的开头和结尾删除空格，即使得到的字符串是不是在接受姓氏列表。

```
QValidator.fixup (self, QString)
```

```
QLocale QValidator.locale (self)
```

[

返回locale的验证。语言环境是默认初始化为相同的QLocale （ ） 。

](qlocale.html)

[**See also**](qlocale.html) [setLocale](qvalidator.html#setLocale)（）和[QLocale.QLocale](qlocale.html#QLocale)（ ） 。

```
QValidator.setLocale (self, QLocale locale)
```

设置_locale_将要使用的验证器。除非setLocale的被调用，验证程序将使用默认的语言环境与集[QLocale.setDefault](qlocale.html#setDefault)（ ） 。如果默认语言环境尚未确定，它是操作系统的语言环境。

**See also** [locale](qvalidator.html#locale)（）和[QLocale.setDefault](qlocale.html#setDefault)（ ） 。

```
(State, QString, int) QValidator.validate (self, QString, int)
```

这种方法是抽象的，应在任何子类中重新实现。

这个虚函数返回[Invalid](qvalidator.html#State-enum)如果_input_是无效的，根据这个验证的规则，[Intermediate](qvalidator.html#State-enum)如果它很可能是多一点的编辑将使得输入可接受的（例如，在用户键入“4”到它接受10〜 99的整数窗口小部件） ，和[Acceptable](qvalidator.html#State-enum)如果输入是有效的。

该功能可以同时改变_input_和_pos_（光标位置），如果需要的话。

```
(State, int) QValidator.validate (self, QString, int)
```

这种方法是抽象的，应在任何子类中重新实现。