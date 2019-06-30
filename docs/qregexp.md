# QRegExp Class Reference

## [[QtCore](index.htm) module]

使用正则表达式类负责提供模式匹配。[More...](#details)

### Types

*   `enum CaretMode { CaretAtZero, CaretAtOffset, CaretWontMatch }`
*   `enum PatternSyntax { RegExp, RegExp2, Wildcard, FixedString, WildcardUnix, W3CXmlSchema11 }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString pattern, Qt.CaseSensitivity cs = Qt.CaseSensitive, PatternSyntax syntax = QRegExp.RegExp)`
*   `__init__ (self, QRegExp rx)`
*   `QString cap (self, int nth = 0)`
*   `int captureCount (self)`
*   `QStringList capturedTexts (self)`
*   `Qt.CaseSensitivity caseSensitivity (self)`
*   `QString errorString (self)`
*   `bool exactMatch (self, QString str)`
*   `int indexIn (self, QString str, int offset = 0, CaretMode caretMode = QRegExp.CaretAtZero)`
*   `bool isEmpty (self)`
*   `bool isMinimal (self)`
*   `bool isValid (self)`
*   `int lastIndexIn (self, QString str, int offset = -1, CaretMode caretMode = QRegExp.CaretAtZero)`
*   `int matchedLength (self)`
*   `int numCaptures (self)`
*   `QString pattern (self)`
*   `PatternSyntax patternSyntax (self)`
*   `int pos (self, int nth = 0)`
*   `setCaseSensitivity (self, Qt.CaseSensitivity cs)`
*   `setMinimal (self, bool minimal)`
*   `setPattern (self, QString pattern)`
*   `setPatternSyntax (self, PatternSyntax syntax)`
*   `swap (self, QRegExp other)`

### Static Methods

*   `QString escape (QString str)`

### Special Methods

*   `bool __eq__ (self, QRegExp rx)`
*   `bool __ne__ (self, QRegExp rx)`
*   `str __repr__ (self)`

* * *

## Detailed Description

使用正则表达式类负责提供模式匹配。

正则表达式，或“正则表达式” ，是在一个文本字符串匹配的模式。这在许多情况下是有用的，例如，

| Validation | A regexp can test whether a substring meets some criteria, e.g. is an integer or contains no whitespace. |
| Searching | A regexp provides more powerful pattern matching than simple substring matching, e.g., match one of the words _mail_, _letter_ or _correspondence_, but none of the words _email_, _mailman_, _mailer_, _letterbox_, etc. |
| Search and Replace | A regexp can replace all occurrences of a substring with a different substring, e.g., replace all occurrences of _&_ with _&amp;_ except where the _&_ is already followed by an _amp;_. |
| String Splitting | A regexp can be used to identify where a string should be split apart, e.g. splitting tab-delimited strings. |

简要介绍了正则表达式给出， Qt的正则表达式语言，一些例子，函数文档本身的描述。 QRegExp是仿照Perl的正则表达式语言。它完全支持Unicode 。 QRegExp也可以使用更简单的，_wildcard mode_类似于在命令shell中的功能。使用QRegExp的语法规则可以被改变[setPatternSyntax](qregexp.html#setPatternSyntax)（ ） 。特别是，该模式的语法可以被设置为[QRegExp.FixedString](qregexp.html#PatternSyntax-enum)，这意味着要匹配的模式被解释为一个普通的字符串，即特殊字符（如反斜线）不会逃脱。

在正则表达式一个很好的文本_Mastering Regular Expressions_（第三版）由Jeffrey EF Friedl的，国际标准书号0-596-52812-4 。

### Introduction

正则表达式是由表情，量词，并断言建立起来。最简单的表达式是一个字符，例如**x** or **5**。表达式也可以是一组方括号括起来的字符。**[ABCD]**将匹配**A**或**B**或**C**或**D**。我们可以这样写相同的表达式为**[A-D]**，以及以消痰匹配英文字母的任何下水管局字母写成**[A-Z]**。

量词指定事件表达式必须匹配的数量。**x{1,1}**意味着匹配一个且只有一个**x**。**x{1,5}**表示匹配序列**x**包含至少一个字符**x**但不超过五个。

请注意，在一般的正则表达式不能用于检查平衡括号或标籤。例如，正则表达式可以被写入到一个匹配HTML开始`&lt;b&gt;`及其关闭`&lt;/b&gt;`如果`&lt;b&gt;`标籤不能嵌套，但如果`&lt;b&gt;`标籤是嵌套的，即同样的正则表达式将匹配一开口`&lt;b&gt;`用错误的结束标记`&lt;/b&gt;`。对于片段`&lt;b&gt;bold &lt;b&gt;bolder&lt;/b&gt;&lt;/b&gt;`中，第一`&lt;b&gt;`将与第一个匹配`&lt;/b&gt;`，这是不正确的。但是，可以编写一个正则表达式，将正确匹配嵌套的括号或标籤，但只有当嵌套级别的数量是固定的和已知的。如果嵌套级别的数量是不固定的和已知的，它是不可能写，不会失败的一个正则表达式。

假设我们希望有一个正则表达式来取值范围为0 〜99的整数相匹配。至少有一个数字是必需的，所以我们开始与表达**[0-9]{1,1}**，它匹配单个数字只出现一次。这个正则表达式在范围0到9的整数匹配。要匹配整数高达99 ，增加出现的最大数量为2，所以正则表达式变得**[0-9]{1,2}**。此正则表达式满足原来的要求相匹配的整数0至99 ，但它也将匹配出现在字符串中的中间整数。如果我们想匹配的整数是整个字符串，必须用锚断言，**^**（插入符号）和**$**（美元） 。何时**^**是一个正则表达式的第一个字符，这意味着正则表达式必须从字符串的开头匹配。何时**$**是正则表达式的最后一个字符，则表示正则表达式必须匹配到字符串的结尾。正则表达式变得**^[0-9]{1,2}$**。需要注意的是断言，例如**^**和**$**，不匹配的字符串中的字符，但位置。

如果你看到其他地方所描述的正则表达式，它们可能看起来从此处显示的不同。这是因为有些字符集和一些量词是如此普遍，他们被赋予特殊的符号来表示它们。**[0-9]**可以替换的符号**\d**。量词完全匹配出现一次，**{1,1}**，可以被替换的表达式本身，即**x{1,1}**是一样的**x**。所以我们的0至99的匹配可以写成**^\d{1,2}$**。它也可以写成**^\d\d{0,1}$**，即_From the start of the string, match a digit, followed immediately by 0 or 1 digits_。在实践中，这将被写为**^\d\d?$**。该**?**是简写的量词**{0,1}**，即0或1出现。**?**使一个表达式可选。正则表达式**^\d\d?$** means _From the beginning of the string, match one digit, followed immediately by 0 or 1 more digit, followed immediately by end of string_。

写一个正则表达式匹配一个单词'邮件'的_or_'信'_or_“对应”，但不匹配词都包含这些用语，例如， “电子邮件” ， “邮差”，“邮件”和“信箱” ，开始用正则表达式匹配'邮件'的。充分表达，正则表达式是**m{1,1}a{1,1}i{1,1}l{1,1}**，但由于字符表达式是由自动定量**{1,1}**，我们可以简化对正则表达式**mail**，即一个'M'后跟一个'a '后跟一个'i'后跟一个'L' 。现在我们可以使用竖线**|**，这意味着**or**，包括其他两个词，所以我们的正则表达式匹配任意的三个词的变**mail|letter|correspondence**。匹配'邮件'**or**'信'**or**'对应' 。虽然这个规则表达式将与要匹配的三个词之一，它也将匹配，我们不想匹配的话，比如， “电子邮件” 。要防止正则表达式匹配从不受欢迎的词汇，我们必须告诉它在字边界开始和结束比赛。首先，我们附上我们的正则表达式中括号，**(mail|letter|correspondence)**。括号组表达式在一起，他们确定，我们希望将正则表达式的一部分[capture](#capturing-text)。括在括号中的表达式允许我们使用它作为在更复杂的正则表达式的组件。这也让我们审视这三个词实际上是匹配的。给力的比赛开始和结束的单词边界，我们附上了正则表达式中**\b** _word boundary_声明：**\b(mail|letter|correspondence)\b**。现在正则表达式的意思是：_Match a word boundary, followed by the regexp in parentheses, followed by a word boundary_。该**\b**断言匹配_position_在正则表达式，而不是一个_character_。字边界是任何非单词字符，如空格，换行符或字符串的开头或结尾。

如果我们要使用HTML实体替换符号字符**&amp;**，正则表达式匹配是根本**&**。但是，这也正则表达式将匹配已经转换为HTML实体＆符号。我们想要替换只能尚未其次是＆符号**amp;**。对于这一点，我们需要的负预测先行断言，**(?!**[__](index.html)**)**。正则表达式可以被写成**&(?!amp;)**，即_Match an ampersand that is_ **not** _followed by_ **amp;**。

如果我们要计算'埃里克'和'的Eirik '的所有在字符串中出现，两个有效的解决方案**\b(Eric|Eirik)\b**和**\bEi?ri[ck]\b**。单词边界断言'\ B'是必须避免含有任一名称匹配单词，例如： “爱立信” 。请注意，第二个正则表达式匹配更多的拼写比我们想： '埃里克'，'埃里克'，' Eiric '和'的Eirik ' 。

一些上面讨论的实施例是在实施[code examples](#code-examples)一节。

### Characters and Abbreviations for Sets of Characters

| Element | Meaning |
| --- | --- |
| **c** | A character represents itself unless it has a special regexp meaning. e.g. **c** matches the character _c_. |
| **\c** | A character that follows a backslash matches the character itself, except as specified below. e.g., To match a literal caret at the beginning of a string, write **\^**. |
| **\a** | Matches the ASCII bell (BEL, 0x07). |
| **\f** | Matches the ASCII form feed (FF, 0x0C). |
| **\n** | Matches the ASCII line feed (LF, 0x0A, Unix newline). |
| **\r** | Matches the ASCII carriage return (CR, 0x0D). |
| **\t** | Matches the ASCII horizontal tab (HT, 0x09). |
| **\v** | Matches the ASCII vertical tab (VT, 0x0B). |
| **\x_hhhh_** | Matches the Unicode character corresponding to the hexadecimal number _hhhh_ (between 0x0000 and 0xFFFF). |
| **\0_ooo_** (i.e., \zero _ooo_) | matches the ASCII/Latin1 character for the octal number _ooo_ (between 0 and 0377). |
| **. (dot)** | Matches any character (including newline). |
| **\d** | Matches a digit ([QChar.isDigit](qchar.html#isDigit)()). |
| **\D** | Matches a non-digit. |
| **\s** | Matches a whitespace character ([QChar.isSpace](qchar.html#isSpace)()). |
| **\S** | Matches a non-whitespace character. |
| **\w** | Matches a word character ([QChar.isLetterOrNumber](qchar.html#isLetterOrNumber)(), [QChar.isMark](qchar.html#isMark)(), or '[_](index.html)'). |
| **\W** | Matches a non-word character. |
| **\_n_** | The _n_-th [backreference](#backreferences), e.g. \1, \2, etc. |

**Note:**在C + +编译器把反斜杠在字符串中。要包括**\**在一个正则表达式，输入两次，即`\\`。要匹配反斜杠字符本身，进入它的四倍，即`\\\\`。

### Sets of Characters

方括号的意思是匹配包含在方括号内的任何字符。上述字符集的缩写可以出现在一个字符在方括号中设置。除字符集的缩写和以下两个例外，字符没有在方括号中的特殊含义。

| **^** | The caret negates the character set if it occurs as the first character (i.e. immediately after the opening square bracket). **[abc]** matches 'a' or 'b' or 'c', but **[^abc]** matches anything _but_ 'a' or 'b' or 'c'. |
| **-** | The dash indicates a range of characters. **[W-Z]** matches 'W' or 'X' or 'Y' or 'Z'. |

使用预定义的字符集的缩写比使用字符更便携的范围跨平台和语言。例如，**[0-9]**符合西方字母一个数字，但**\d**匹配一个数字_any_字母表。

注：在其他的正则表达式的文档，字符集通常被称为“字符类” 。

### Quantifiers

默认情况下，一个表达式将自动被量化**{1,1}**的，即它应该发生一次。在下面的列表中，**_E_**代表表达。一个表达式是一个字符，或简称为一组字符或一组方括号中的字符，或者在括号中的表达式。

| **_E_?** | Matches zero or one occurrences of _E_. This quantifier means _The previous expression is optional_, because it will match whether or not the expression is found. **_E_?** is the same as **_E_{0,1}**. e.g., **dents?** matches 'dent' or 'dents'. |
| **_E_+** | Matches one or more occurrences of _E_. **_E_+** is the same as **_E_{1,}**. e.g., **0+** matches '0', '00', '000', etc. |
| **_E_*** | Matches zero or more occurrences of _E_. It is the same as **_E_{0,}**. The ***** quantifier is often used in error where **+** should be used. For example, if **\s*$** is used in an expression to match strings that end in whitespace, it will match every string because **\s*$** means _Match zero or more whitespaces followed by end of string_. The correct regexp to match strings that have at least one trailing whitespace character is **\s+$**. |
| **_E_{n}** | Matches exactly _n_ occurrences of _E_. **_E_{n}** is the same as repeating _E_ _n_ times. For example, **x{5}** is the same as **xxxxx**. It is also the same as **_E_{n,n}**, e.g. **x{5,5}**. |
| **_E_{n,}** | Matches at least _n_ occurrences of _E_. |
| **_E_{,m}** | Matches at most _m_ occurrences of _E_. **_E_{,m}** is the same as **_E_{0,m}**. |
| **_E_{n,m}** | Matches at least _n_ and at most _m_ occurrences of _E_. |

要应用一个量词的不仅仅是前面的字符，使用括号字符组一起在一个表达式。例如，**tag+**匹配一个'T'后跟一个'a '后跟至少有一个“G” ，而**(tag)+**匹配至少一个出现'标籤'的。

注：量词通常是“贪婪” 。他们总是匹配尽可能多的文本，因为他们可以。例如，**0+**第一个零匹配后找到的第一个零和所有连续的零。应用到'20005 ' ，它matches'2&lt;u&gt;000&lt;/u&gt;5 ' 。量词可以由非贪婪，见[setMinimal](qregexp.html#setMinimal)（ ） 。

### Capturing Text

括号让我们组元素结合在一起，使我们能够量化和捕捉它们。例如，如果我们有表达**mail|letter|correspondence**匹配我们知道，一个串_one_的匹配的话，但没有哪一个。使用括号使我们能够“捕获”无论是匹配的范围内，所以如果我们使用**(mail|letter|correspondence)**和相匹配的字符串，这个正则表达式“我给你发一些电子邮件” ，我们可以使用[cap](qregexp.html#cap)（）或[capturedTexts](qregexp.html#capturedTexts)（）函数来提取匹配的字符，在这种情况下， “邮件” 。

我们可以在正则表达式本身中使用捕获的文本。要引用我们使用捕获的文本_backreferences_这是从1索引，一样的[cap](qregexp.html#cap)（ ） 。例如，我们可以使用一个字符串搜索重复的单词**\b(\w+)\W+\1\b**这意味着匹配一个单词边界后跟后跟后跟相同的文字作为第一个括号表达式后跟一个单词边界的一个或多个非单词字符中的一个或多个单词字符。

如果我们要纯粹使用括号进行分组，而不是用于捕捉，我们可以使用非捕获的语法，如**(?:green|blue)**。非捕获括号开始' （ ： '和结束'）' 。在这个例子中，我们要么匹配'绿色'或'蓝色'，但我们不捕获匹配，所以我们只知道我们是否匹配，但没有哪种颜色，我们居然发现。使用非捕获括号比使用捕获括号，因为正则表达式引擎必须少做簿记更有效率。

捕捉和非捕获括号可以嵌套。

由于历史原因，量词（例如*****）适用于捕获括号更“贪婪”比其他的量词。例如，**a*(a*)**将匹配“ AAA”帽（ 1 ） == “AAA” 。这种行为是从什么其他的正则表达式引擎做的（值得注意的是， Perl的）不同。为了获得更为直观的捕捉行为，请指定[QRegExp.RegExp2](qregexp.html#PatternSyntax-enum)到QRegExp构造函数或调用setPatternSyntax （[QRegExp.RegExp2](qregexp.html#PatternSyntax-enum)） 。

当匹配的数量不能预先确定，一个常见的成语是使用[cap](qregexp.html#cap)（）在一个循环。例如：

```
 QRegExp rx("(\\d+)");
 [QString](qstring.html) str = "Offsets: 12 14 99 231 7";
 [QStringList](qstringlist.html) list;
 int pos = 0;

 while ((pos = rx.indexIn(str, pos)) != -1) {
     list << rx.cap(1);
     pos += rx.matchedLength();
 }
 // list: ["12", "14", "99", "231", "7"]

```

### Assertions

断言做出了一些文字语句，他们出现在正则表达式，但它们不匹配任何字符的地步。在下面的列表中**_E_**代表任意表达式。

| **^** | The caret signifies the beginning of the string. If you wish to match a literal `^` you must escape it by writing `\\^`. For example, **^#include** will only match strings which _begin_ with the characters '#include'. (When the caret is the first character of a character set it has a special meaning, see [Sets of Characters](#sets-of-characters).) |
| **$** | The dollar signifies the end of the string. For example **\d\s*$** will match strings which end with a digit optionally followed by whitespace. If you wish to match a literal `$` you must escape it by writing `\\$`. |
| **\b** | A word boundary. For example the regexp **\bOK\b** means match immediately after a word boundary (e.g. start of string or whitespace) the letter 'O' then the letter 'K' immediately before another word boundary (e.g. end of string or whitespace). But note that the assertion does not actually match any whitespace so if we write **(\bOK\b)** and we have a match it will only contain 'OK' even if the string is "It's &lt;u&gt;OK&lt;/u&gt; now". |
| **\B** | A non-word boundary. This assertion is true wherever **\b** is false. For example if we searched for **\Bon\B** in "Left on" the match would fail (space and end of string aren't non-word boundaries), but it would match in "t&lt;u&gt;on&lt;/u&gt;ne". |
| **(?=_E_)** | Positive lookahead. This assertion is true if the expression matches at this point in the regexp. For example, **const(?=\s+char)** matches 'const' whenever it is followed by 'char', as in 'static &lt;u&gt;const&lt;/u&gt; char *'. (Compare with **const\s+char**, which matches 'static &lt;u&gt;const char&lt;/u&gt; *'.) |
| **(?!_E_)** | Negative lookahead. This assertion is true if the expression does not match at this point in the regexp. For example, **const(?!\s+char)** matches 'const' _except_ when it is followed by 'char'. |

### Wildcard Matching

大多数命令shell ，如_bash_ or _cmd.exe_支持“文件通配符”使用通配符来标识一组文件的能力。该[setPatternSyntax](qregexp.html#setPatternSyntax)（ ）函数用于正则表达式和通配符模式之间切换。通配符匹配是比全正则表达式更简单，只有四个特点：

| **c** | Any character represents itself apart from those mentioned below. Thus **c** matches the character _c_. |
| **?** | Matches any single character. It is the same as **.** in full regexps. |
| ***** | Matches zero or more of any characters. It is the same as **.*** in full regexps. |
| **[...]** | Sets of characters can be represented in square brackets, similar to full regexps. Within the character class, like outside, backslash has no special meaning. |

在该模式中通配符，通配符不能逃脱。在该模式[WildcardUnix](qregexp.html#PatternSyntax-enum)，字符“\”转义通配符。

例如，如果我们在通配符模式，并有包含文件名的字符串，我们可以用识别HTML文件***.html**。这将匹配零个或多个字符后面跟着一个点后面'H' ， 'T' ， 'm'和'L' 。

要测试的一个通配符表达式，使用一个字符串[exactMatch](qregexp.html#exactMatch)（ ） 。例如：

```
 QRegExp rx("*.txt");
 rx.setPatternSyntax(QRegExp.Wildcard);
 rx.exactMatch("README.txt");        // returns true
 rx.exactMatch("welcome.txt.bak");   // returns false

```

### Notes for Perl Users

大多数通过Perl的支持的字符类缩写是由QRegExp支持，请参阅[characters and abbreviations for sets of characters](#characters-and-abbreviations-for-sets-of-characters)。

在QRegExp ，除了字符类中，`^`始终表示字符串的开始，所以符号标识必须始终逃脱，除非用于这一目的。在Perl中插入符号的含义有所不同自动将不同的地方发生这样逃脱它很少是必要的。这同样适用于`$`这在QRegExp始终表示字符串的结束。

QRegExp的量词是一样的Perl的贪婪量词（但见[note above](#greedy-quantifiers)） 。非贪婪匹配，不能应用到单个量词，但可以适用于所有模式的量词。例如，要匹配的Perl的正则表达式**ro+?m**要求：

```
 QRegExp rx("ro+m");
 rx.setMinimal(true);

```

Perl的等效`/i`选项setCaseSensitivity （[Qt.CaseInsensitive](qt.html#CaseSensitivity-enum)） 。

Perl的`/g`选项可以使用来模拟[loop](#cap-in-a-loop)。

在QRegExp**.**匹配任何字符，因此所有的QRegExp正则表达式有Perl的等效`/s`选项。 QRegExp没有一个等同于Perl的`/m`选项，但这可以通过把输入到线路或通过用正则表达式，搜索换行符循环不同的方式，例如被模拟。

因为QRegExp为导向的字符串，没有\ A ， \ Z或\ Ž断言。不支持的\ G断言，但可以在一个循环来模拟。

Perl的$ ＆是帽（ 0 ）或[capturedTexts](qregexp.html#capturedTexts)（） [0]。有没有QRegExp等值$ ` ， $ '或$ + 。 Perl的捕获变量， $ 1，$ 2，...对应于盖（1 ）或[capturedTexts](qregexp.html#capturedTexts)（ ） [1] ，帽（ 2 ）或[capturedTexts](qregexp.html#capturedTexts)（）[ 2]等

要替换的模式使用[QString.replace](qstring.html#replace)（ ） 。

Perl的扩展`/x`不支持的语法，也不是指令，例如（ ？ ⅰ），或正则表达式的评论，例如（ ？ ＃注释） 。另一方面，C + +的表示字符串的规则可以用来实现相同的：

```
 QRegExp mark("\\b"      // word boundary
               "[Mm]ark" // the word we want to match
             );

```

两个零宽度的正序和零宽度负预测先行断言（ ？ =模式）和（ ？ ！模式）都具有相同的语法和Perl的支持。不支持Perl的向后断言， “独立”的子表达式和条件表达式。

非捕获括号也支持，具有相同的（ ： ？模式）语法。

See [QString.split](qstring.html#split)（）和[QStringList.join](qstringlist.html#join)（）的等值Perl的分割和结合功能。

注：因为C + +转换\的，他们必须写_twice_在代码中，例如**\b**必须写**\\b**。

### Code Examples

```
 QRegExp rx("^\\d\\d?$");    // match integers 0 to 99
 rx.indexIn("123");          // returns -1 (no match)
 rx.indexIn("-6");           // returns -1 (no match)
 rx.indexIn("6");            // returns 0 (matched as position 0)

```

第三个字符串匹配'&lt;u&gt;6&lt;/u&gt;' 。这是一个简单的验证正则表达式的取值范围为0 〜99的整数。

```
 QRegExp rx("^\\S+$");       // match strings without whitespace
 rx.indexIn("Hello world");  // returns -1 (no match)
 rx.indexIn("This_is-OK");   // returns 0 (matched at position 0)

```

第二个字符串匹配'&lt;u&gt;This_is-OK&lt;/u&gt;' 。我们已经使用的字符集的缩写'\ S' （非空白）和锚相匹配的不含空格的字符串。

在下面的例子中，我们匹配包含'邮件'或'信'或'对应'字符串，但只匹配整个单词，即没有“电子邮件”

```
 QRegExp rx("\\b(mail|letter|correspondence)\\b");
 rx.indexIn("I sent you an email");     // returns -1 (no match)
 rx.indexIn("Please write the letter"); // returns 17

```

第二个字符串匹配“请写&lt;u&gt;letter&lt;/u&gt;。 “这个词'信'是还抓获（因为括号） ，我们可以看到文字，我们已经捕获像这样：

```
 [QString](qstring.html) captured = rx.cap(1); // captured == "letter"

```

这将从第一组捕获括号（计数捕获左圆括号从左到右）捕获文本。括号是从1 ，因为帽计数（ 0 ）是整个匹配正则表达式（相当于'＆'在大多数正则表达式引擎） 。

```
 QRegExp rx("&(?!amp;)");      // match ampersands but not &amp;
 [QString](qstring.html) line1 = "This & that";
 line1.replace(rx, "&amp;");
 // line1 == "This &amp; that"
 [QString](qstring.html) line2 = "His &amp; hers & theirs";
 line2.replace(rx, "&amp;");
 // line2 == "His &amp; hers &amp; theirs"

```

在这里，我们已经通过了QRegExp到[QString](qstring.html)的替换（ ）函数来更换新的文本匹配的文本。

```
 [QString](qstring.html) str = "One Eric another Eirik, and an Ericsson. "
               "How many Eiriks, Eric?";
 QRegExp rx("\\b(Eric|Eirik)\\b"); // match Eric or Eirik
 int pos = 0;    // where we are in the string
 int count = 0;  // how many Eric and Eirik's we've counted
 while (pos >= 0) {
     pos = rx.indexIn(str, pos);
     if (pos >= 0) {
         ++pos;      // move along in str
         ++count;    // count our Eric or Eirik
     }
 }

```

我们使用了[indexIn](qregexp.html#indexIn)（ ）函数将字符串中的正则表达式匹配反复。请注意，而不是向前移动一个字符在一个时间，`pos++`我们可以写`pos += rx.matchedLength()`跳过已经匹配的字符串。伯爵将等于3 ，配套“一&lt;u&gt;Eric&lt;/u&gt;另一&lt;u&gt;Eirik&lt;/u&gt;以及爱立信。有多少Eiriks ，&lt;u&gt;Eric&lt;/u&gt;？“ ，它不匹配'爱立信'或' Eiriks '，因为它们不是由非单词边界为界。

一个常见的使用正则表达式的是分隔的数据行拆分为它们的组件领域。

```
 str = "Nokia Corporation\tqt.nokia.com\tNorway";
 [QString](qstring.html) company, web, country;
 rx.setPattern("^([^\t]+)\t([^\t]+)\t([^\t]+)$");
 if (rx.indexIn(str) != -1) {
     company = rx.cap(1);
     web = rx.cap(2);
     country = rx.cap(3);
 }

```

在这个例子中我们输入行的格式为公司名称，网址和国家。不幸的是，正则表达式是相当长的，而不是非常灵活 - 该代码将打破，如果我们添加更多的字段。一个更简单和更好的解决办法是寻找分隔符， '\ T'在这种情况下，走周围的文字。该[QString.split](qstring.html#split)（ ）函数可以接受一个分隔字符串或正则表达式作为参数，并相应的分割字符串。

```
 [QStringList](qstringlist.html) field = str.split("\t");

```

在此领域[ 0 ]是该公司，现场​​[1]的网址等。

模仿一个外壳的匹配，我们可以使用通配符模式。

```
 QRegExp rx("*.html");
 rx.setPatternSyntax(QRegExp.Wildcard);
 rx.exactMatch("index.html");                // returns true
 rx.exactMatch("default.htm");               // returns false
 rx.exactMatch("readme.txt");                // returns false

```

通配符匹配可能是因为它的简单方便，但任何通配符正则表达式可以使用完整的正则表达式来定义，例如：**.*\.html$**。请注意，我们不能同时匹配`.html`和`.htm`带通配符的文件，除非我们使用***.htm***这也将匹配' test.html.bak “ 。一个完整的正则表达式为我们提供了我们所需要的精度，**.*\.html?$**。

QRegExp可以使用不区分大小写匹配情况[setCaseSensitivity](qregexp.html#setCaseSensitivity)（ ） ，并可以使用非贪婪匹配，请参阅[setMinimal](qregexp.html#setMinimal)（ ） 。默认情况下QRegExp采用全正则表达式，但是这可以通过改变[setWildcard](index.htm#setWildcard)（ ） 。搜索可以向前[indexIn](qregexp.html#indexIn)（ ）或向后[lastIndexIn](qregexp.html#lastIndexIn)（ ） 。捕获的文本可以使用访问[capturedTexts](qregexp.html#capturedTexts)（ ），它返回所有捕获的字符串的字符串列表，或者使用[cap](qregexp.html#cap)（ ），它返回捕获的字符串给定的索引。该[pos](qregexp.html#pos)（ ）函数接受一个匹配索引，并返回那里的比赛作出（或-1，如果没有匹配）在字符串中的位置。

* * *

## Type Documentation

```
QRegExp.CaretMode
```

该CaretMode枚举定义插入符的不同含义（**^**）在正则表达式。可能的值有：

| Constant | Value | Description |
| --- | --- | --- |
| `QRegExp.CaretAtZero` | `0` | 插入符号对应于索引0中搜索字符串。 |
| `QRegExp.CaretAtOffset` | `1` | 插入符号对应于开始搜索的偏移量。 |
| `QRegExp.CaretWontMatch` | `2` | 插入符号永远不匹配。 |

```
QRegExp.PatternSyntax
```

语法用于解释该图案的含义。

| Constant | Value | Description |
| --- | --- | --- |
| `QRegExp.RegExp` | `0` | 丰富的Perl类似的模式匹配语法。这是默认的。 |
| `QRegExp.RegExp2` | `3` | 喜欢的RegExp ，但与[greedy quantifiers](qregexp.html#greedy-quantifiers)。这将是默认的Qt 5 。 （在Qt 4.2中引入）。 |
| `QRegExp.Wildcard` | `1` | 这提供了“文件通配符”类似于使用的砲弹（命令解释器）一个简单的模式匹配的语法。看[Wildcard Matching](qregexp.html#wildcard-matching)。 |
| `QRegExp.WildcardUnix` | `4` | 这类似于通配符而是一个Unix外壳的行为。通配符可以用转义字符“ \ ” 。 |
| `QRegExp.FixedString` | `2` | 模式是固定字符串。这相当于使用了RegExp模式上，所有的元字符进行转义字符串使用[escape](qregexp.html#escape)（ ） 。 |
| `QRegExp.W3CXmlSchema11` | `5` | 该模式是一个正则表达式由W3C的XML Schema 1.1规范定义。 |

**See also** [setPatternSyntax](qregexp.html#setPatternSyntax)（ ） 。

* * *

## Method Documentation

```
QRegExp.__init__ (self)
```

构造一个空的正则表达式。

**See also** [isValid](qregexp.html#isValid)（）和[errorString](qregexp.html#errorString)（ ） 。

```
QRegExp.__init__ (self, QString pattern, Qt.CaseSensitivity cs = Qt.CaseSensitive, PatternSyntax syntax = QRegExp.RegExp)
```

构造一个正则表达式对象为给定的_pattern_字符串。该模式必须使用通配符表示法，如果给予_syntax_ is [Wildcard](qregexp.html#PatternSyntax-enum)，默认为[RegExp](qregexp.html#PatternSyntax-enum)。该模式是区分大小写的，除非_cs_ is [Qt.CaseInsensitive](qt.html#CaseSensitivity-enum)。匹配是贪婪的（最大） ，但可以通过调用改变[setMinimal](qregexp.html#setMinimal)（ ） 。

**See also** [setPattern](qregexp.html#setPattern)（ ）[setCaseSensitivity](qregexp.html#setCaseSensitivity)（）和[setPatternSyntax](qregexp.html#setPatternSyntax)（ ） 。

```
QRegExp.__init__ (self, QRegExp rx)
```

构造一个正则表达式的一个副本_rx_。

**See also** [operator=](qregexp.html#operator-eq)（ ） 。

```
QString QRegExp.cap (self, int nth = 0)
```

返回由捕获的文本_nth_子表达式。在整场比赛的索引为0和括号的子表达式有索引从1开始（不包括非捕获括号） 。

```
 [QRegExp](qregexp.html) rxlen("(\\d+)(?:\\s*)(cm|inch)");
 int pos = rxlen.indexIn("Length: 189cm");
 if (pos > -1) {
     [QString](qstring.html) value = rxlen.cap(1); // "189"
     [QString](qstring.html) unit = rxlen.cap(2);  // "cm"
     // ...
 }

```

匹配由帽元件（ ）的顺序如下所示。第一个元素，帽（ 0 ） ，是整个匹配的字符串。每个后续元素对应到下一个捕获打开左括号。因此盖（ 1 ）是第一个捕获的括号的文本，帽（ 2 ）是第二的文本，等等。

**See also** [capturedTexts](qregexp.html#capturedTexts)（）和[pos](qregexp.html#pos)（ ） 。

```
int QRegExp.captureCount (self)
```

返回包含在正则表达式捕获的数量。

此功能被引入Qt的4.6 。

```
QStringList QRegExp.capturedTexts (self)
```

返回捕获的文本字符串的列表。

该列表中的第一个字符串是整个匹配的字符串。每个后续的列表元素包含了匹配正则表达式的（捕获）子表达式的字符串。

例如：

```
 [QRegExp](qregexp.html) rx("(\\d+)(\\s*)(cm|inch(es)?)");
 int pos = rx.indexIn("Length: 36 inches");
 [QStringList](qstringlist.html) list = rx.capturedTexts();
 // list is now ("36 inches", "36", " ", "inches", "es")

```

上面的例子还捕捉可能存在的元素，但我们有没有兴趣。这个问题可以通过使用非捕获括号来解决：

```
 [QRegExp](qregexp.html) rx("(\\d+)(?:\\s*)(cm|inch(?:es)?)");
 int pos = rx.indexIn("Length: 36 inches");
 [QStringList](qstringlist.html) list = rx.capturedTexts();
 // list is now ("36 inches", "36", "inches")

```

需要注意的是，如果你想遍历列表，你应该遍历一个副本，如

```
 [QStringList](qstringlist.html) list = rx.capturedTexts();
 [QStringList](qstringlist.html).iterator it = list.begin();
 while (it != list.end()) {
     myProcessing(*it);
     ++it;
 }

```

一些正则表达式可以匹配一个不确定的次数。例如，如果输入字符串为“偏移： 12 14 99 231 7 ”和正则表达式，`rx`，是**(\d+)+**，我们希望让所有的数字相匹配的列表。但是，调用后`rx.indexIn(str)`， capturedTexts （ ）将返回列表中（ “12” ， “12” ） ，即在整场比赛是“ 12”和第一个子表达式匹配的是“12” 。正确的方法是使用[cap](qregexp.html#cap)在（）[loop](qregexp.html#cap-in-a-loop)。

在字符串列表中元素的顺序如下。第一个元素是整个匹配的字符串。每个后续元素对应到下一个捕获打开左括号。因此capturedTexts （ ） [1]是第一个捕获的括号， capturedTexts （ ） [ 2 ]是第二等（相当于$ 1，$ 2，等等，在其他一些正则表达式语言）文本的文本。

**See also** [cap](qregexp.html#cap)（）和[pos](qregexp.html#pos)（ ） 。

```
Qt.CaseSensitivity QRegExp.caseSensitivity (self)
```

[](qt.html#CaseSensitivity-enum)

[Returns](qt.html#CaseSensitivity-enum) [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)如果设置了RegExp是敏感匹配的情况下，否则返回[Qt.CaseInsensitive](qt.html#CaseSensitivity-enum)。

**See also** [setCaseSensitivity](qregexp.html#setCaseSensitivity)（ ）[patternSyntax](qregexp.html#patternSyntax)（ ）[pattern](qregexp.html#pattern)（）和[isMinimal](qregexp.html#isMinimal)（ ） 。

```
QString QRegExp.errorString (self)
```

返回解释了为什么一个正则表达式模式无效的情况下是一个文本字符串，否则返回“没有发生错误” 。

**See also** [isValid](qregexp.html#isValid)（ ） 。

```
QString QRegExp.escape (QString str)
```

返回字符串_str_与每一个正则表达式的特殊字符用反斜杠转义。特殊字符$ ​​， （ ， ） ， * ， + ， ， ， [ ， ， ] ， ^ ， ？ { ， |和} 。

例如：

```
 s1 = [QRegExp](qregexp.html).escape("bingo");   // s1 == "bingo"
 s2 = [QRegExp](qregexp.html).escape("f(x)");    // s2 == "f\\(x\\)"

```

此功能是动态构造的正则表达式模式有用：

```
 [QRegExp](qregexp.html) rx("(" + [QRegExp](qregexp.html).escape(name) +
            "|" + [QRegExp](qregexp.html).escape(alias) + ")");

```

**See also** [setPatternSyntax](qregexp.html#setPatternSyntax)（ ） 。

```
bool QRegExp.exactMatch (self, QString str)
```

返回True如果_str_精确匹配这个正则表达式，否则返回False 。您可以决定如何将字符串的多少是相匹配的调用[matchedLength](qregexp.html#matchedLength)（ ） 。

对于一个给定的正则表达式的字符串R，完全匹配（ “R” ）是indexIn （ “ ^ R $ ” ），因为完全匹配相当于（ ）有效地封闭了正则表达式在字符串和字符串锚年底开始，除了它设置[matchedLength](qregexp.html#matchedLength)（ ）不同。

例如，如果正则表达式是**blue**，然后完全匹配（ ）只适用于输入返回True`blue`。对于输入`bluebell`，`blutak`和`lightblue`，完全匹配（ ）返回False ，并[matchedLength](qregexp.html#matchedLength)（ ）将返回4,3和0分别。

虽然常量，这个函数集[matchedLength](qregexp.html#matchedLength)（ ）[capturedTexts](qregexp.html#capturedTexts)（）和[pos](qregexp.html#pos)（ ） 。

**See also** [indexIn](qregexp.html#indexIn)（）和[lastIndexIn](qregexp.html#lastIndexIn)（ ） 。

```
int QRegExp.indexIn (self, QString str, int offset = 0, CaretMode caretMode = QRegExp.CaretAtZero)
```

试图找到一个匹配_str_从位置_offset_（默认为0 ） 。如果_offset_为-1，搜索从最后一个字符，如果-2 ，在倒数第二个字符，等等。

返回第一个匹配，或者-1的位置，如果没有匹配。

该_caretMode_参数可以被用来指示是否**^**应该匹配在索引0或_offset_。

你可能更愿意使用[QString.indexOf](qstring.html#indexOf)（ ）[QString.contains](qstring.html#contains)（） ，或什至[QStringList.filter](qstringlist.html#filter)（ ） 。要替换的匹配使用[QString.replace](qstring.html#replace)（ ） 。

例如：

```
 [QString](qstring.html) str = "offsets: 1.23 .50 71.00 6.00";
 [QRegExp](qregexp.html) rx("\\d*\\.\\d+");    // primitive floating point matching
 int count = 0;
 int pos = 0;
 while ((pos = rx.indexIn(str, pos)) != -1) {
     ++count;
     pos += rx.matchedLength();
 }
 // pos will be 9, 14, 18 and finally 24; count will end up as 4

```

虽然常量，这个函数集[matchedLength](qregexp.html#matchedLength)（ ）[capturedTexts](qregexp.html#capturedTexts)（）和[pos](qregexp.html#pos)（ ） 。

如果[QRegExp](qregexp.html)是一个通配符表达式（见[setPatternSyntax](qregexp.html#setPatternSyntax)（ ） ），并希望测试对整个通配符表达式，使用一个字符串[exactMatch](qregexp.html#exactMatch)（代替此功能） 。

**See also** [lastIndexIn](qregexp.html#lastIndexIn)（）和[exactMatch](qregexp.html#exactMatch)（ ） 。

```
bool QRegExp.isEmpty (self)
```

返回True如果该模式字符串为空，否则返回False 。

如果你打电话[exactMatch](qregexp.html#exactMatch)（ ）与空字符串的空模式将返回True，否则它，因为它工作在整个字符串返回False 。如果你打电话[indexIn](qregexp.html#indexIn)（ ）对空模式_any_字符串将返回起始位置的偏移（默认为0 ） ，因为空模式在字符串的开头匹配的“空虚” 。在这种情况下返回的匹配的长度[matchedLength](qregexp.html#matchedLength)（）为0。

See [QString.isEmpty](qstring.html#isEmpty)（ ） 。

```
bool QRegExp.isMinimal (self)
```

返回True如果已启用最小的（非贪婪）匹配，否则返回False 。

**See also** [caseSensitivity](qregexp.html#caseSensitivity)（）和[setMinimal](qregexp.html#setMinimal)（ ） 。

```
bool QRegExp.isValid (self)
```

返回True如果正则表达式是有效的，否则返回False 。无效的正则表达式永远不匹配。

该模式**[a-z**是无效的模式的一个例子，因为它缺少结束括号。

请注意，一个正则表达式的有效性也可能依赖于通配符标志的设置，例如***.html**是一种有效的通配符正则表达式，但无效的正则表达式满。

**See also** [errorString](qregexp.html#errorString)（ ） 。

```
int QRegExp.lastIndexIn (self, QString str, int offset = -1, CaretMode caretMode = QRegExp.CaretAtZero)
```

试图找到向后在比赛中_str_从位置_offset_。如果_offset_为-1 （默认） ，搜索从最后一个字符，如果-2 ，在倒数第二个字符，等等。

返回第一个匹配，或者-1的位置，如果没有匹配。

该_caretMode_参数可以被用来指示是否**^**应该匹配在索引0或_offset_。

虽然常量，这个函数集[matchedLength](qregexp.html#matchedLength)（ ）[capturedTexts](qregexp.html#capturedTexts)（）和[pos](qregexp.html#pos)（ ） 。

**Warning:**反向搜索比正向搜索要慢很多。

**See also** [indexIn](qregexp.html#indexIn)（）和[exactMatch](qregexp.html#exactMatch)（ ） 。

```
int QRegExp.matchedLength (self)
```

返回最后一个匹配的字符串，或-1的长度，如果没有匹配。

**See also** [exactMatch](qregexp.html#exactMatch)（ ）[indexIn](qregexp.html#indexIn)（）和[lastIndexIn](qregexp.html#lastIndexIn)（ ） 。

```
int QRegExp.numCaptures (self)
```

```
QString QRegExp.pattern (self)
```

返回正则表达式的模式字符串。该模式具有下列正则表达式语法或通配符语法，这取决于[patternSyntax](qregexp.html#patternSyntax)（ ） 。

**See also** [setPattern](qregexp.html#setPattern)（ ）[patternSyntax](qregexp.html#patternSyntax)（）和[caseSensitivity](qregexp.html#caseSensitivity)（ ） 。

```
PatternSyntax QRegExp.patternSyntax (self)
```

[](qregexp.html#PatternSyntax-enum)

[返回所使用的正则表达式的语法。默认值是](qregexp.html#PatternSyntax-enum)[QRegExp.RegExp](qregexp.html#PatternSyntax-enum)。

**See also** [setPatternSyntax](qregexp.html#setPatternSyntax)（ ）[pattern](qregexp.html#pattern)（）和[caseSensitivity](qregexp.html#caseSensitivity)（ ） 。

```
int QRegExp.pos (self, int nth = 0)
```

返回的位置_nth_在搜索字符串捕获的文本。如果_nth_为0 （默认值） ， POS （ ）返回整个匹配的位置。

例如：

```
 [QRegExp](qregexp.html) rx("/([a-z]+)/([a-z]+)");
 rx.indexIn("Output /dev/null");   // returns 7 (position of /dev/null)
 rx.pos(0);                        // returns 7 (position of /dev/null)
 rx.pos(1);                        // returns 8 (position of dev)
 rx.pos(2);                        // returns 12 (position of null)

```

对于零长度匹配， POS （ ）总是返回-1 。 （例如，如果盖（ 4 ）将返回一个空字符串， POS （ 4 ）返回-1。 ）这是实现的一个特点。

**See also** [cap](qregexp.html#cap)（）和[capturedTexts](qregexp.html#capturedTexts)（ ） 。

```
QRegExp.setCaseSensitivity (self, Qt.CaseSensitivity cs)
```

设置区分大小写匹配_cs_。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)，**\.txt$** matches `readme.txt`但不`README.TXT`。

**See also** [caseSensitivity](qregexp.html#caseSensitivity)（ ）[setPatternSyntax](qregexp.html#setPatternSyntax)（ ）[setPattern](qregexp.html#setPattern)（）和[setMinimal](qregexp.html#setMinimal)（ ） 。

```
QRegExp.setMinimal (self, bool minimal)
```

启用或禁用最小匹配。如果_minimal_是假的，匹配是贪婪的（最大），这是默认的。

例如，假设我们有输入字符串：“我们必须\u003cb\u003e粗体\u003c / b\u003e中，非常\u003cb\u003e粗体\u003c / B\u003e ！ ”并且图案**&lt;b&gt;.*&lt;/b&gt;**。用默认的贪婪（最大）的匹配，与之匹配的是“我们必须&lt;u&gt;&lt;b&gt;bold&lt;/b&gt;, very &lt;b&gt;bold&lt;/b&gt;&lt;/u&gt;！ “，但以最小的（非贪婪）匹配时，第一场比赛是： ”我们必须&lt;u&gt;&lt;b&gt;bold&lt;/b&gt;&lt;/u&gt;，非常\u003cB\u003e \u003c / B\u003e大胆！ “，而第二场比赛是”我们必须\u003cb\u003e粗体\u003c / b\u003e中，很&lt;u&gt;&lt;b&gt;bold&lt;/b&gt;&lt;/u&gt;！ “ 。在实践中，我们可能会使用该模式**&lt;b&gt;[^&lt;]*&lt;/b&gt;**相反，尽管这仍然会为嵌套标记失败。

**See also** [minimal](index.htm#minimal)（）和[setCaseSensitivity](qregexp.html#setCaseSensitivity)（ ） 。

```
QRegExp.setPattern (self, QString pattern)
```

模式字符串设置为_pattern_。区分大小写，通配符，和最小的匹配选项不会改变。

**See also** [pattern](qregexp.html#pattern)（ ）[setPatternSyntax](qregexp.html#setPatternSyntax)（）和[setCaseSensitivity](qregexp.html#setCaseSensitivity)（ ） 。

```
QRegExp.setPatternSyntax (self, PatternSyntax syntax)
```

设置语法模式的正则表达式。默认值是[QRegExp.RegExp](qregexp.html#PatternSyntax-enum)。

Setting _syntax_至[QRegExp.Wildcard](qregexp.html#PatternSyntax-enum)让简单的壳状[wildcard matching](qregexp.html#wildcard-matching)。例如，**r*.txt**字符串匹配`readme.txt`在通配符模式，但不匹配`readme`。

Setting _syntax_至[QRegExp.FixedString](qregexp.html#PatternSyntax-enum)表示该图案被解释为一个简单的字符串。特殊字符（如反斜杠）不需要进行转义即可。

**See also** [patternSyntax](qregexp.html#patternSyntax)（ ）[setPattern](qregexp.html#setPattern)（ ）[setCaseSensitivity](qregexp.html#setCaseSensitivity)（）和[escape](qregexp.html#escape)（ ） 。

```
QRegExp.swap (self, QRegExp other)
```

掉期的正则表达式_other_与此正则表达式。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
bool QRegExp.__eq__ (self, QRegExp rx)
```

```
bool QRegExp.__ne__ (self, QRegExp rx)
```

```
str QRegExp.__repr__ (self)
```