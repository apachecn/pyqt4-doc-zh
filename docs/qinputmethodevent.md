# QInputMethodEvent Class Reference

## [[QtGui](index.htm) module]

该QInputMethodEvent类提供了输入法的事件参数。[More...](#details)

继承[QEvent](qevent.html)。

### Types

*   `class **[Attribute](index.htm)**`
*   `enum AttributeType { TextFormat, Cursor, Language, Ruby, Selection }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString preeditText, list-of-QInputMethodEvent.Attribute attributes)`
*   `__init__ (self, QInputMethodEvent other)`
*   `list-of-QInputMethodEvent.Attribute attributes (self)`
*   `QString commitString (self)`
*   `QString preeditString (self)`
*   `int replacementLength (self)`
*   `int replacementStart (self)`
*   `setCommitString (self, QString commitString, int from = 0, int length = 0)`

* * *

## Detailed Description

该QInputMethodEvent类提供了输入法的事件参数。

输入法事件发送到窗口部件时，输入法来输入文本的小工具。输入法被广泛用于输入文字与非拉丁字母的语言。

请注意，创建自定义的文本编辑窗口部件时，该[Qt.WA_InputMethodEnabled](qt.html#WidgetAttribute-enum)窗口属性必须显式设置（使用[QWidget.setAttribute](qwidget.html#setAttribute)（ ）函数） ，以便接收输入方法事件。

该事件感兴趣的人谁不想能正确处理复杂的文字输入语言的键盘输入部件的作者。在这样的语言的文本输入通常是三个步骤：

1.  **Starting to Compose**

    当用户按下键盘上的第一键，输入上下文被创建。该输入上下文将包含键入的字符的字符串。

2.  **Composing**

    随着按下每一个新键，输入法将尝试创建一个匹配的字符串输入的文字至今被称为预编辑字符串。而输入上下文活动时，用户可以只将光标移动属于该输入上下文内的字符串。

3.  **Completing**

    在一些点，用户将激活一个用户接口部件（可能使用特定的键），其中它们可以从许多匹配他们已经输入到目前为止文本字符串的选择。用户可以确认他们的选择取消输入，在这两种情况下的输入上下文将被关闭。

QInputMethodEvent模型这三个阶段，并转移到正确渲染中间结果所需的信息。一个QInputMethodEvent有两个主要参数：[preeditString](qinputmethodevent.html#preeditString)（）和[commitString](qinputmethodevent.html#commitString)（ ） 。该[preeditString](qinputmethodevent.html#preeditString)（ ）参数提供了当前活动的预编辑字符串。该[commitString](qinputmethodevent.html#commitString)（）的参数给出了应该被添加到（或更换的零件）的编辑控件的文本的文本。它通常是输入操作的结果，并具有直接的预编辑字符串之前，要被插入到该小部件文本。

如果[commitString](qinputmethodevent.html#commitString)（ ）应该更换的编辑器中的文字部分，[replacementLength](qinputmethodevent.html#replacementLength)（）将包含要被替换的字符数。[replacementStart](qinputmethodevent.html#replacementStart)（）包含在该字符将相对从预编辑字符串的开始取代了位置。

一些属性控制预编辑字符串的视觉外观（文本的视觉外观的预编辑字符串外仅由部件控制） 。该[AttributeType](qinputmethodevent.html#AttributeType-enum)枚举描述了可设置不同的属性。

一个类实现[QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（）或[QGraphicsItem.inputMethodEvent](qgraphicsitem.html#inputMethodEvent)（ ）至少应该理解和尊敬[TextFormat](qinputmethodevent.html#AttributeType-enum)和[Cursor](qinputmethodevent.html#AttributeType-enum)属性。

因为输入方法需要能够从部件或图形项查询某些属性，子类还必须实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（）和[QGraphicsItem.inputMethodQuery](qgraphicsitem.html#inputMethodQuery)（） ，分别为。

当接收到一个输入法事件，文本组件必须执行以下步骤：

1.  如果控件已选定的文本，选定文本应该得到消除。
2.  删除文本的起始处[replacementStart](qinputmethodevent.html#replacementStart)（ ）与长度[replacementLength](qinputmethodevent.html#replacementLength)（）和由它代替[commitString](qinputmethodevent.html#commitString)（ ） 。如果[replacementLength](qinputmethodevent.html#replacementLength)（ ）为0，[replacementStart](qinputmethodevent.html#replacementStart)（）给出的插入位置[commitString](qinputmethodevent.html#commitString)（ ） 。

    当进行置换预先编辑字符串的区域将被忽略，从而替代从-1开始为2的长度将预编辑字符串，之后的第一个字符之前删除的最后一个字符，并直接将预编辑字符串前插入提交字符串。

    如果小部件工具撤消/重做，这种操作被添加到撤消堆栈中。

3.  如果没有当前预编辑字符串，插入[preeditString](qinputmethodevent.html#preeditString)（ ）在当前光标位置，否则与此事件收到一个取代以前preeditString 。

    如果小部件工具撤消/重做时，[preeditString](qinputmethodevent.html#preeditString)（ ）不应该影响撤消/重做栈以任何方式。

    窗口小部件应检查属性列表应用到预编辑字符串。它具有至少了解的[TextFormat](qinputmethodevent.html#AttributeType-enum)和游标属性和指定渲染它们。

* * *

## Type Documentation

```
QInputMethodEvent.AttributeType
```

| Constant | Value | Description |
| --- | --- | --- |
| `QInputMethodEvent.TextFormat` | `0` | A [QTextCharFormat](qtextcharformat.html)对预编辑字符串由start和length指定的一部分。值包含一个[QVariant](qvariant.html)类型[QTextFormat](qtextformat.html)指定这部分的预编辑字符串的渲染。应该有至多有一个格式的预编辑字符串的每一个部分。如果几个是在字符串中指定的任何字符的行为是未定义的。一个符合标准的实现必须至少兑现格式的backgroundColor ，文字颜色及加底线的属性。 |
| `QInputMethodEvent.Cursor` | `1` | 如果设置，光标应显示预编辑字符串内的位置开始。长度变量确定光标是否可见或不可见。如果长度为0的光标是不可见的。如果值是一个[QVariant](qvariant.html)类型[QColor](qcolor.html)这种颜色将用于渲染光标，否则周围文本的颜色将被使用。应该有每个事件最多只有一个光标属性。如果几个指定的行为是未定义的。 |
| `QInputMethodEvent.Language` | `2` | 变体包含一个[QLocale](qlocale.html)对象指定预编辑字符串的某一部分的语言。应该有至多有一个语言的预编辑字符串的每一个部分设置。如果几个是在字符串中指定的任何字符的行为是未定义的。 |
| `QInputMethodEvent.Ruby` | `3` | 红宝石文本预编辑字符串的一部分。应该有对预编辑字符串的每一个部分最多有一个红宝石的文本集。如果几个是在字符串中指定的任何字符的行为是未定义的。 |
| `QInputMethodEvent.Selection` | `4` | 如果设置，编辑光标应该被移动到编辑器中的文本内容中的指定位置。与此相反`Cursor`，这个属性不能在预先编辑文字工作，但对周围的文字。光标将后移至提交字符串一直致力于，并预先编辑字符串将设在新的编辑位置。的开始位置指定新的位置和长度可变，可用于设置从该点起进行选择。该值是未使用的。 |

**See also** [Attribute](index.htm)。

* * *

## Method Documentation

```
QInputMethodEvent.__init__ (self)
```

构造类型的事件[QEvent.InputMethod](qevent.html#Type-enum)。该[attributes](qinputmethodevent.html#attributes)（ ）[preeditString](qinputmethodevent.html#preeditString)（ ）[commitString](qinputmethodevent.html#commitString)（ ）[replacementStart](qinputmethodevent.html#replacementStart)（）和[replacementLength](qinputmethodevent.html#replacementLength)（ ）被初始化为默认值。

**See also** [setCommitString](qinputmethodevent.html#setCommitString)（ ） 。

```
QInputMethodEvent.__init__ (self, QString preeditText, list-of-QInputMethodEvent.Attribute attributes)
```

Construcs类型的事件[QEvent.InputMethod](qevent.html#Type-enum)。预编辑文本设置为_preeditText_的属性_attributes_。

该[commitString](qinputmethodevent.html#commitString)（ ）[replacementStart](qinputmethodevent.html#replacementStart)（）和[replacementLength](qinputmethodevent.html#replacementLength)（）值可以使用设置[setCommitString](qinputmethodevent.html#setCommitString)（ ） 。

**See also** [preeditString](qinputmethodevent.html#preeditString)（）和[attributes](qinputmethodevent.html#attributes)（ ） 。

```
QInputMethodEvent.__init__ (self, QInputMethodEvent other)
```

构造的副本_other_。

```
list-of-QInputMethodEvent.Attribute QInputMethodEvent.attributes (self)
```

返回传递到属性列表[QInputMethodEvent](qinputmethodevent.html)构造函数。的属性控制在预编辑字符串的视觉外观（文字的视觉外观的预编辑字符串以外仅由部件控制）。

**See also** [preeditString](qinputmethodevent.html#preeditString)（）和[Attribute](index.htm)。

```
QString QInputMethodEvent.commitString (self)
```

返回应该被添加到（或更换的零件）的编辑控件的文本。它通常是输入操作的结果，并具有直接的预编辑字符串之前，要被插入到该小部件文本。

**See also** [setCommitString](qinputmethodevent.html#setCommitString)（ ）[preeditString](qinputmethodevent.html#preeditString)（ ）[replacementStart](qinputmethodevent.html#replacementStart)（）和[replacementLength](qinputmethodevent.html#replacementLength)（ ） 。

```
QString QInputMethodEvent.preeditString (self)
```

返回预编辑文本，即文本的用户开始编辑它。

**See also** [commitString](qinputmethodevent.html#commitString)（）和[attributes](qinputmethodevent.html#attributes)（ ） 。

```
int QInputMethodEvent.replacementLength (self)
```

返回被替换的预编辑字符串中的字符数。

**See also** [replacementStart](qinputmethodevent.html#replacementStart)（）和[setCommitString](qinputmethodevent.html#setCommitString)（ ） 。

```
int QInputMethodEvent.replacementStart (self)
```

返回字符将被相对的预编辑字符串的开始取代了位置。

**See also** [replacementLength](qinputmethodevent.html#replacementLength)（）和[setCommitString](qinputmethodevent.html#setCommitString)（ ） 。

```
QInputMethodEvent.setCommitString (self, QString commitString, int from = 0, int length = 0)
```

提交字符串设置为_commitString_。

提交的字符串是一个应该被添加到（或更换的零件）的编辑控件的文本。它通常是输入操作的结果，并具有直接的预编辑字符串之前，要被插入到该小部件文本。

如果提交的字符串应该替换的编辑器中的文字部分，_replaceLength_指定要被替换的字符数。_replaceFrom_指定在哪个字符被从相对的预编辑字符串的开始取代了位置。

**See also** [commitString](qinputmethodevent.html#commitString)（ ）[replacementStart](qinputmethodevent.html#replacementStart)（）和[replacementLength](qinputmethodevent.html#replacementLength)（ ） 。