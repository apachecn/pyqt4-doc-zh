# QRegExpValidator Class Reference

## [[QtGui](index.htm) module]

该QRegExpValidator类是用来检查与正则表达式的字符串。[More...](#details)

继承[QValidator](qvalidator.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QRegExp rx, QObject parent = None)`
*   `QRegExp regExp (self)`
*   `setRegExp (self, QRegExp rx)`
*   `(QValidator.State, QString input, int pos) validate (self, QString input, int pos)`
*   `(QValidator.State, int pos) validate (self, QString input, int pos)`

* * *

## Detailed Description

该QRegExpValidator类是用来检查与正则表达式的字符串。

QRegExpValidator使用正则表达式（正则表达式）来确定一个输入字符串是否是[Acceptable](qvalidator.html#State-enum)，[Intermediate](qvalidator.html#State-enum)或[Invalid](qvalidator.html#State-enum)。当QRegExpValidator构造正则表达式可以被提供，或者在稍后的时间。

当QRegExpValidator判断一个字符串是否是[Acceptable](qvalidator.html#State-enum)还是不行，正则表达式被视为其与字符串断言的启动开始（**^**），并用绳子断言年底结束（**$**） ;匹配是对整个输入字符串，或者从给定的位置，如果开始位置大于零给出。

如果一个字符串的前缀[Acceptable](qvalidator.html#State-enum)串，它被认为是[Intermediate](qvalidator.html#State-enum)。例如， “ ”和“A”是[Intermediate](qvalidator.html#State-enum)为正则表达式**[A-Z][0-9]**（而“[_](index.html)“将是[Invalid](qvalidator.html#State-enum)） 。

对于简要介绍了Qt的正则表达式引擎，请参阅[QRegExp](qregexp.html)。

使用示例：

```
 // regexp: optional '-' followed by between 1 and 3 digits
 [QRegExp](qregexp.html) rx("-?\\d{1,3}");
 [QValidator](qvalidator.html) *validator = new QRegExpValidator(rx, this);

 [QLineEdit](qlineedit.html) *edit = new [QLineEdit](qlineedit.html)(this);
 edit->setValidator(validator);

```

下面，我们提出校验器的一些例子。在实践中，它们通常会被一个小部件如在上面的例子有关。

```
 // integers 1 to 9999
 [QRegExp](qregexp.html) rx("[1-9]\\d{0,3}");
 // the validator treats the regexp as "^[1-9]\\d{0,3}$"
 QRegExpValidator v(rx, 0);
 [QString](qstring.html) s;
 int pos = 0;

 s = "0";     v.validate(s, pos);    // returns Invalid
 s = "12345"; v.validate(s, pos);    // returns Invalid
 s = "1";     v.validate(s, pos);    // returns Acceptable

 rx.setPattern("\\S+");            // one or more non-whitespace characters
 v.setRegExp(rx);
 s = "myfile.txt";  v.validate(s, pos); // Returns Acceptable
 s = "my file.txt"; v.validate(s, pos); // Returns Invalid

 // A, B or C followed by exactly five digits followed by W, X, Y or Z
 rx.setPattern("[A-C]\\d{5}[W-Z]");
 v.setRegExp(rx);
 s = "a12345Z"; v.validate(s, pos);        // Returns Invalid
 s = "A12345Z"; v.validate(s, pos);        // Returns Acceptable
 s = "B12";     v.validate(s, pos);        // Returns Intermediate

 // match most 'readme' files
 rx.setPattern("read\\S?me(\.(txt|asc|1st))?");
 rx.setCaseSensitive(false);
 v.setRegExp(rx);
 s = "readme";      v.validate(s, pos); // Returns Acceptable
 s = "README.1ST";  v.validate(s, pos); // Returns Acceptable
 s = "read me.txt"; v.validate(s, pos); // Returns Invalid
 s = "readm";       v.validate(s, pos); // Returns Intermediate

```

* * *

## Method Documentation

```
QRegExpValidator.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个验证用_parent_对象接受任何字符串（包括空单）为有效。

```
QRegExpValidator.__init__ (self, QRegExp rx, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个验证用_parent_对象接受匹配正则表达式的字符串_rx_。

本场比赛是针对整个字符串，例如如果设置了RegExp是**[A-Fa-f0-9]+**这将被视为**^[A-Fa-f0-9]+$**。

```
QRegExp QRegExpValidator.regExp (self)
```

[

```
QRegExpValidator.setRegExp (self, QRegExp rx)
```

```
(QValidator.State, QString input, int pos) QRegExpValidator.validate (self, QString input, int pos)
```

](qregexp.html)

[从重新实现](qregexp.html)[QValidator.validate](qvalidator.html#validate)（ ） 。

Returns [Acceptable](qvalidator.html#State-enum)如果_input_匹配的正则表达式为这个校验器，[Intermediate](qvalidator.html#State-enum)如果它匹配的部分（即可能是一个有效的匹配，如果其他有效字符添加） ，及[Invalid](qvalidator.html#State-enum)如果_input_不匹配。

该_pos_参数被设置为的长度_input_参数。

例如，如果正则表达式是**\w\d\d**（单词字符，数字，数字），那么“ A57 ”是[Acceptable](qvalidator.html#State-enum)， “ E5 ”是[Intermediate](qvalidator.html#State-enum)和“ 9 ”的[Invalid](qvalidator.html#State-enum)。

**See also** [QRegExp.exactMatch](qregexp.html#exactMatch)（ ） 。

```
(QValidator.State, int pos) QRegExpValidator.validate (self, QString input, int pos)
```