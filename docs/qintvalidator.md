# QIntValidator Class Reference

## [[QtGui](index.htm) module]

该QIntValidator类提供了一个验证器，确保一个字符串包含一个指定范围内的有效整数。[More...](#details)

继承[QValidator](qvalidator.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, int bottom, int top, QObject parent = None)`
*   `int bottom (self)`
*   `QString input fixup (self, QString input)`
*   `fixup (self, QString input)`
*   `setBottom (self, int)`
*   `setRange (self, int bottom, int top)`
*   `setTop (self, int)`
*   `int top (self)`
*   `(QValidator.State, QString, int) validate (self, QString, int)`
*   `(QValidator.State, int) validate (self, QString, int)`

* * *

## Detailed Description

该QIntValidator类提供了一个验证器，确保一个字符串包含一个指定范围内的有效整数。

使用示例：

```
 [QValidator](qvalidator.html) *validator = new QIntValidator(100, 999, this);
 [QLineEdit](qlineedit.html) *edit = new [QLineEdit](qlineedit.html)(this);

 // the edit lineedit will only accept integers between 100 and 999
 edit->setValidator(validator);

```

下面，我们提出校验器的一些例子。在实践中，它们通常会被一个小部件如在上面的例子有关。

```
 [QString](qstring.html) str;
 int pos = 0;
 QIntValidator v(100, 900, this);

 str = "1";
 v.validate(str, pos);     // returns Intermediate
 str = "012";
 v.validate(str, pos);     // returns Intermediate

 str = "123";
 v.validate(str, pos);     // returns Acceptable
 str = "678";
 v.validate(str, pos);     // returns Acceptable

 str = "999";
 v.validate(str, pos);    // returns Intermediate

 str = "1234";
 v.validate(str, pos);     // returns Invalid
 str = "-123";
 v.validate(str, pos);     // returns Invalid
 str = "abc";
 v.validate(str, pos);     // returns Invalid
 str = "12cm";
 v.validate(str, pos);     // returns Invalid

```

注意，该值`999`返回中间。值组成的数字位数等于或小于最大值被认为是中间。这样做的目的是因为，可以防止一些是在范围中的位数不一定是最后一个数字类型的。这也意味着，一个中间数可以有前导零。

的最小值和最大值都设置在一个呼叫与[setRange](qintvalidator.html#setRange)（），或者单独用[setBottom](qintvalidator.html#bottom-prop)（）和[setTop](qintvalidator.html#top-prop)（ ） 。

QIntValidator使用其[locale](qvalidator.html#locale)（）来解释的数目。例如，在阿拉伯语语言环境， QIntValidator将接受阿拉伯数字。此外， QIntValidator始终保证接受了一些根据“C”区域设置。

* * *

## Method Documentation

```
QIntValidator.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个验证用_parent_对象，它接受所有的整数。

```
QIntValidator.__init__ (self, int bottom, int top, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个验证用_parent_，接受来自整数_minimum_至_maximum_包容性。

```
int QIntValidator.bottom (self)
```

```
QString input QIntValidator.fixup (self, QString input)
```

从重新实现[QValidator.fixup](qvalidator.html#fixup)（ ） 。

```
QIntValidator.fixup (self, QString input)
```

```
QIntValidator.setBottom (self, int)
```

```
QIntValidator.setRange (self, int bottom, int top)
```

设置验证程序的范围只接受之间的整数_bottom_和_top_包容性。

```
QIntValidator.setTop (self, int)
```

```
int QIntValidator.top (self)
```

```
(QValidator.State, QString, int) QIntValidator.validate (self, QString, int)
```

从重新实现[QValidator.validate](qvalidator.html#validate)（ ） 。

Returns [Acceptable](qvalidator.html#State-enum)如果_input_是在有效范围内的整数，[Intermediate](qvalidator.html#State-enum)如果_input_是一个整数的有效范围内的前缀，并[Invalid](qvalidator.html#State-enum)否则。

如果有效范围只包括正整数（例如， 32到100 ），并_input_是一个负整数，则无效返回。 （在另一方面，如果该范围包括负整数（例如，-100到-32 ）的和_input_是一个正整数，然后中间返回，因为用户可能只是键入减号（尤其是从右到左的语言） 。

```
 int pos = 0;

 s = "abc";
 v.validate(s, pos);    // returns Invalid

 s = "5";
 v.validate(s, pos);    // returns Intermediate

 s = "50";
 v.validate(s, pos);    // returns Acceptable

```

默认情况下，_pos_参数不使用此验证程序。

```
(QValidator.State, int) QIntValidator.validate (self, QString, int)
```