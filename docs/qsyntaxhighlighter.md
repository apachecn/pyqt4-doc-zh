# QSyntaxHighlighter Class Reference

## [[QtGui](index.htm) module]

该QSyntaxHighlighter类允许你定义语法高亮规则，除了可以使用类来查询文档的当前格式或用户数据。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QTextEdit parent)`
*   `__init__ (self, QTextDocument parent)`
*   `__init__ (self, QObject parent)`
*   `QTextBlock currentBlock (self)`
*   `int currentBlockState (self)`
*   `QTextBlockUserData currentBlockUserData (self)`
*   `QTextDocument document (self)`
*   `QTextCharFormat format (self, int pos)`
*   `highlightBlock (self, QString text)`
*   `int previousBlockState (self)`
*   `rehighlight (self)`
*   `rehighlightBlock (self, QTextBlock block)`
*   `setCurrentBlockState (self, int newState)`
*   `setCurrentBlockUserData (self, QTextBlockUserData data)`
*   `setDocument (self, QTextDocument doc)`
*   `setFormat (self, int start, int count, QTextCharFormat format)`
*   `setFormat (self, int start, int count, QColor color)`
*   `setFormat (self, int start, int count, QFont font)`

* * *

## Detailed Description

该QSyntaxHighlighter类允许你定义语法高亮规则，除了可以使用类来查询文档的当前格式或用户数据。

该QSyntaxHighlighter类是实现一个基类[QTextEdit](qtextedit.html)语法荧光笔。语法highligher自动突出显示文本的部分在[QTextEdit](qtextedit.html)，或更一般地在一个[QTextDocument](qtextdocument.html)。当用户以特定的格式（例如源代码）输入文字，并帮助用户读取文本并识别语法错误语法荧光笔经常被使用。

提供自己的语法高亮，你必须继承QSyntaxHighlighter和重新实现[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（ ） 。

当您创建您的QSyntaxHighlighter子类的实例，传递给它[QTextEdit](qtextedit.html) or [QTextDocument](qtextdocument.html)您想要的语法高亮被应用到。例如：

```
 [QTextEdit](qtextedit.html) *editor = new [QTextEdit](qtextedit.html);
 MyHighlighter *highlighter = new MyHighlighter(editor->document());

```

在此之后你[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（ ）函数将自动被调用时必要的。使用您的[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（ ）函数（如设置字体和颜色）套用格式来传递给它的文本。 QSyntaxHighlighter提供[setFormat](qsyntaxhighlighter.html#setFormat)（）函数，它适用于一个给定的[QTextCharFormat](qtextcharformat.html)对当前文本块。例如：

```
 void MyHighlighter.highlightBlock(const [QString](qstring.html) &text)
 {
     [QTextCharFormat](qtextcharformat.html) myClassFormat;
     myClassFormat.setFontWeight([QFont](qfont.html).Bold);
     myClassFormat.setForeground([Qt](qt.html).darkMagenta);
     [QString](qstring.html) pattern = "\\bMy[A-Za-z]+\\b";

     [QRegExp](qregexp.html) expression(pattern);
     int index = text.indexOf(expression);
     while (index >= 0) {
         int length = expression.matchedLength();
         setFormat(index, length, myClassFormat);
         index = text.indexOf(expression, index + length);
     }
 }

```

一些语法可以跨越数个文字块结构。例如，一个C + +的语法高亮显示应该能够应付`/``*...*``/`多行注释。为了应对这些情况下，有必要知道以前的文本块的结束状态（例如“在注释” ） 。

在你的[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（）实现可以使用查询以前的文本块的结束状态[previousBlockState](qsyntaxhighlighter.html#previousBlockState)（）函数。解析模块后，您可以使用保存最后状态[setCurrentBlockState](qsyntaxhighlighter.html#setCurrentBlockState)（ ） 。

该[currentBlockState](qsyntaxhighlighter.html#currentBlockState)（）和[previousBlockState](qsyntaxhighlighter.html#previousBlockState)（ ）函数返回一个int值。如果没有状态设置，返回值为-1 。您可以指定任何其他值使用，以确定任何给定的状态[setCurrentBlockState](qsyntaxhighlighter.html#setCurrentBlockState)（）函数。一旦状态被设定在[QTextBlock](qtextblock.html)保持该值直到它被设置重新设置或直到文本的相应段落被删除。

例如，如果你正在写一个简单的C + +语法高亮，你可能会指定1来表示“在注释” ：

```
 [QTextCharFormat](qtextcharformat.html) multiLineCommentFormat;
 multiLineCommentFormat.setForeground([Qt](qt.html).red);

 [QRegExp](qregexp.html) startExpression("/\\*");
 [QRegExp](qregexp.html) endExpression("\\*/");

 setCurrentBlockState(0);

 int startIndex = 0;
 if (previousBlockState() != 1)
     startIndex = text.indexOf(startExpression);

 while (startIndex >= 0) {
    int endIndex = text.indexOf(endExpression, startIndex);
    int commentLength;
    if (endIndex == -1) {
        setCurrentBlockState(1);
        commentLength = text.length() - startIndex;
    } else {
        commentLength = endIndex - startIndex
                        + endExpression.matchedLength();
    }
    setFormat(startIndex, commentLength, multiLineCommentFormat);
    startIndex = text.indexOf(startExpression,
                              startIndex + commentLength);
 }

```

在上面的例子中，我们首先设置当前块的状态为0。然后，如果前面的程序段中的注释结束，我们从当前块的开头higlight （`startIndex = 0`） 。否则，我们搜索给定的起始表达。如果指定的结束表达式不能在文本块中被发现，我们通过调用改变当前块的状态[setCurrentBlockState](qsyntaxhighlighter.html#setCurrentBlockState)（ ） ，并确保该块的其馀部分是higlighted 。

此外，您可以使用查询当前格式和用户数据[format](qsyntaxhighlighter.html#format)（）和[currentBlockUserData](qsyntaxhighlighter.html#currentBlockUserData)（ ）分别为功能。您还可以将用户的数据使用附加到当前文本块[setCurrentBlockUserData](qsyntaxhighlighter.html#setCurrentBlockUserData)（）函数。[QTextBlockUserData](qtextblockuserdata.html)可以用来存储自定义设置。在语法高亮的情况下，特别是有趣的，因为缓存中存储的信息，你可以找出在分析段落的文字。有关示例，请参见[setCurrentBlockUserData](qsyntaxhighlighter.html#setCurrentBlockUserData)（ ）的文档。

* * *

## Method Documentation

```
QSyntaxHighlighter.__init__ (self, QTextEdit parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSyntaxHighlighter](qsyntaxhighlighter.html)用给定的_parent_。

```
QSyntaxHighlighter.__init__ (self, QTextDocument parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSyntaxHighlighter](qsyntaxhighlighter.html)并在安装它_parent_。指定[QTextDocument](qtextdocument.html)也成为了车主[QSyntaxHighlighter](qsyntaxhighlighter.html)。

```
QSyntaxHighlighter.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSyntaxHighlighter](qsyntaxhighlighter.html)并在安装它_parent_的[QTextDocument](qtextdocument.html)。指定[QTextEdit](qtextedit.html)也成为了车主[QSyntaxHighlighter](qsyntaxhighlighter.html)。

```
QTextBlock QSyntaxHighlighter.currentBlock (self)
```

[

返回当前文本块。

此功能被引入Qt的4.4 。

```
int QSyntaxHighlighter.currentBlockState (self)
```

返回当前文本块的状态。如果未设置任何值，则返回值为-1 。

](qtextblock.html)

[**See also**](qtextblock.html) [setCurrentBlockState](qsyntaxhighlighter.html#setCurrentBlockState)（ ） 。

```
QTextBlockUserData QSyntaxHighlighter.currentBlockUserData (self)
```

[](qtextblockuserdata.html)

[返回](qtextblockuserdata.html)[QTextBlockUserData](qtextblockuserdata.html)反对先前附加到当前文本块。

**See also** [QTextBlock.userData](qtextblock.html#userData)（）和[setCurrentBlockUserData](qsyntaxhighlighter.html#setCurrentBlockUserData)（ ） 。

```
QTextDocument QSyntaxHighlighter.document (self)
```

[](qtextdocument.html)

[返回](qtextdocument.html)[QTextDocument](qtextdocument.html)在这本语法高亮显示已安装。

**See also** [setDocument](qsyntaxhighlighter.html#setDocument)（ ） 。

```
QTextCharFormat QSyntaxHighlighter.format (self, int pos)
```

[

返回格式，_position_里面的语法高亮显示当前的文本块。

](qtextcharformat.html)

[**See also**](qtextcharformat.html) [setFormat](qsyntaxhighlighter.html#setFormat)（ ） 。

```
QSyntaxHighlighter.highlightBlock (self, QString text)
```

这种方法是抽象的，应在任何子类中重新实现。

亮点给定的文本块。这个功能是由富文本引擎在必要时调用，即对已改变的文本块。

提供自己的语法高亮，你必须继承[QSyntaxHighlighter](qsyntaxhighlighter.html)并重新实现highlightBlock （ ） 。在你重新实现，你应该分析该区块的_text_和呼叫[setFormat](qsyntaxhighlighter.html#setFormat)（）视需要来应用你需要的任何字体和颜色的变化。例如：

```
 void MyHighlighter.highlightBlock(const [QString](qstring.html) &text)
 {
     [QTextCharFormat](qtextcharformat.html) myClassFormat;
     myClassFormat.setFontWeight([QFont](qfont.html).Bold);
     myClassFormat.setForeground([Qt](qt.html).darkMagenta);
     [QString](qstring.html) pattern = "\\bMy[A-Za-z]+\\b";

     [QRegExp](qregexp.html) expression(pattern);
     int index = text.indexOf(expression);
     while (index >= 0) {
         int length = expression.matchedLength();
         setFormat(index, length, myClassFormat);
         index = text.indexOf(expression, index + length);
      }
  }

```

一些语法可以跨越数个文字块结构。例如，一个C + +的语法高亮显示应该能够应付`/``*...*``/`多行注释。为了应对这些情况下，有必要知道以前的文本块的结束状态（例如“在注释” ） 。

在你的highlightBlock （）实现可以使用查询以前的文本块的结束状态[previousBlockState](qsyntaxhighlighter.html#previousBlockState)（）函数。解析模块后，您可以使用保存最后状态[setCurrentBlockState](qsyntaxhighlighter.html#setCurrentBlockState)（ ） 。

该[currentBlockState](qsyntaxhighlighter.html#currentBlockState)（）和[previousBlockState](qsyntaxhighlighter.html#previousBlockState)（ ）函数返回一个int值。如果没有状态设置，返回值为-1 。您可以指定任何其他值使用，以确定任何给定的状态[setCurrentBlockState](qsyntaxhighlighter.html#setCurrentBlockState)（）函数。一旦状态被设定在[QTextBlock](qtextblock.html)保持该值直到它被设置重新设置或直到文本的相应段落被删除。

例如，如果你正在写一个简单的C + +语法高亮，你可能会指定1来表示“在注释” 。对于结束的评论最好设置1使用setCurrentBlockState的中间，和其他几款最好设置0文本块。在你的解析代码，如果返回值[previousBlockState](qsyntaxhighlighter.html#previousBlockState)（）是1 ，你，直到你达到收盘突出显示文本作为一个C + +注释`*``/`。

**See also** [previousBlockState](qsyntaxhighlighter.html#previousBlockState)（ ）[setFormat](qsyntaxhighlighter.html#setFormat)（）和[setCurrentBlockState](qsyntaxhighlighter.html#setCurrentBlockState)（ ） 。

```
int QSyntaxHighlighter.previousBlockState (self)
```

返回文本块的结尾状态前，以语法高亮显示的当前块。如果先前未设置任何值，则返回值为-1 。

**See also** [highlightBlock](qsyntaxhighlighter.html#highlightBlock)（）和[setCurrentBlockState](qsyntaxhighlighter.html#setCurrentBlockState)（ ） 。

```
QSyntaxHighlighter.rehighlight (self)
```

这种方法也是一个Qt槽与C + +的签名`void rehighlight()`。

重新应用突出显示整个文档。

这个函数中引入了Qt 4.2中。

**See also** [rehighlightBlock](qsyntaxhighlighter.html#rehighlightBlock)（ ） 。

```
QSyntaxHighlighter.rehighlightBlock (self, QTextBlock block)
```

这种方法也是一个Qt槽与C + +的签名`void rehighlightBlock(const QTextBlock&)`。

重新应用突出显示给定的[QTextBlock](qtextblock.html) _block_。

此功能被引入Qt的4.6 。

**See also** [rehighlight](qsyntaxhighlighter.html#rehighlight)（ ） 。

```
QSyntaxHighlighter.setCurrentBlockState (self, int newState)
```

设置当前文本块的状态_newState_。

**See also** [currentBlockState](qsyntaxhighlighter.html#currentBlockState)（）和[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（ ） 。

```
QSyntaxHighlighter.setCurrentBlockUserData (self, QTextBlockUserData data)
```

重视给定的_data_以目前的文本块。所有权被传递到下面的文本文件，即提供[QTextBlockUserData](qtextblockuserdata.html)如果相应的文本块被删除的对象将被删除。

[QTextBlockUserData](qtextblockuserdata.html)可以用来存储自定义设置。在语法高亮的情况下，特别是有趣的，因为缓存中存储的信息，你可以找出在分析段落的文字。

例如在解析文本，你可以保持您遇到的（ ' { [ （'之类的）括号字符轨道，并存储它们的相对位置和实际[QChar](qchar.html)在源自一个简单的类[QTextBlockUserData](qtextblockuserdata.html)：

```
 struct ParenthesisInfo
 {
     [QChar](qchar.html) char;
     int position;
 };

 struct BlockData : public [QTextBlockUserData](qtextblockuserdata.html)
 {
     [QVector](index.htm)<ParenthesisInfo> parentheses;
 };

```

期间，在相关编辑器的光标导航，你可以问当前[QTextBlock](qtextblock.html)（使用检索到的[QTextCursor.block](qtextcursor.html#block)（ ）函数），如果它有一个用户数据对象集，并将其转换为你的`BlockData`对象。然后，您可以检查当前光标位置与先前录制的括号位置相匹配，并根据括号（打开或关闭）的类型，找到同一级别的下一个左或右括号。

通过这种方式，你可以做一个直观的括号匹配和高亮显示从当前光标位置到匹配的括号。这使得它更容易发现缺少括号中的代码，并寻找到对应的打开/关闭括号编辑括号密集型代码的时候。

**See also** [currentBlockUserData](qsyntaxhighlighter.html#currentBlockUserData)（）和[QTextBlock.setUserData](qtextblock.html#setUserData)（ ） 。

```
QSyntaxHighlighter.setDocument (self, QTextDocument doc)
```

安装语法高亮在给定的[QTextDocument](qtextdocument.html) _doc_。一[QSyntaxHighlighter](qsyntaxhighlighter.html)只能用于同一个文档的时间。

**See also** [document](qsyntaxhighlighter.html#document)（ ） 。

```
QSyntaxHighlighter.setFormat (self, int start, int count, QTextCharFormat format)
```

此功能适用于语法高亮显示当前的文本块（即传递给文本[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（）函数） 。

指定_format_从应用到文本_start_对的长度位置_count_字符（如果_count_是0 ，没有采取任何措施） 。在设置的格式属性_format_被合并在显示时间直接存储在文档中的格式信息，例如先前设置[QTextCursor](qtextcursor.html)的功能。需要注意的是文件本身并没有发生变化，通过这个功能设置的格式。

**See also** [format](qsyntaxhighlighter.html#format)（）和[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（ ） 。

```
QSyntaxHighlighter.setFormat (self, int start, int count, QColor color)
```

这是一个重载函数。

指定_color_从应用于当前文本块_start_对的长度位置_count_字符。

当前文本块的其他属性，例如字体和背景颜色，被重置为默认值。

**See also** [format](qsyntaxhighlighter.html#format)（）和[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（ ） 。

```
QSyntaxHighlighter.setFormat (self, int start, int count, QFont font)
```

这是一个重载函数。

指定_font_从应用于当前文本块_start_对的长度位置_count_字符。

当前文本块的其他属性，例如字体和背景颜色，被重置为默认值。

**See also** [format](qsyntaxhighlighter.html#format)（）和[highlightBlock](qsyntaxhighlighter.html#highlightBlock)（ ） 。