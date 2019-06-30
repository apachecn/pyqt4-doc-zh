# QUndoCommand Class Reference

## [[QtGui](index.htm) module]

该QUndoCommand类是所有的命令存储在基类[QUndoStack](qundostack.html)。[More...](#details)

### Methods

*   `__init__ (self, QUndoCommand parent = None)`
*   `__init__ (self, QString text, QUndoCommand parent = None)`
*   `QString actionText (self)`
*   `QUndoCommand child (self, int index)`
*   `int childCount (self)`
*   `int id (self)`
*   `bool mergeWith (self, QUndoCommand other)`
*   `redo (self)`
*   `setText (self, QString text)`
*   `QString text (self)`
*   `undo (self)`

* * *

## Detailed Description

该QUndoCommand类是所有的命令存储在基类[QUndoStack](qundostack.html)。

对于Qt的复原框架的概述，请参阅[overview document](index.htm)。

一个QUndoCommand代表文档中的单个编辑操作，例如，插入或删除一个文本编辑器文本块。 QUndoCommand可以申请更改的文件与[redo](qundocommand.html#redo)（）和撤销与变更[undo](qundocommand.html#undo)（ ） 。在实现这些功能必须在派生类中提供。

```
 class AppendText : public QUndoCommand
 {
 public:
     AppendText([QString](qstring.html) *doc, const [QString](qstring.html) &text)
         : m_document(doc), m_text(text) { setText("append text"); }
     virtual void undo()
         { m_document->chop(m_text.length()); }
     virtual void redo()
         { m_document->append(m_text); }
 private:
     [QString](qstring.html) *m_document;
     [QString](qstring.html) m_text;
 };

```

一个QUndoCommand都有一个关联的[text](qundocommand.html#text)（ ） 。这是一个短字符串描述该命令功能。它是用来更新堆栈的撤消的文本属性和重复动作，见[QUndoStack.createUndoAction](qundostack.html#createUndoAction)（）和[QUndoStack.createRedoAction](qundostack.html#createRedoAction)（ ） 。

QUndoCommand对象由堆栈他们被压入资。[QUndoStack](qundostack.html)删除的命令，如果它已被撤消和一个新的命令被推动。例如：

```
 MyCommand *command1 = new MyCommand();
 stack->push(command1);
 MyCommand *command2 = new MyCommand();
 stack->push(command2);

 stack->undo();

 MyCommand *command3 = new MyCommand();
 stack->push(command3); // command2 gets deleted

```

实际上，当命令被按下时，它成为堆栈上的最顶层的命令。

为了支持命令压缩， QUndoCommand有[id](qundocommand.html#id)（ ）和虚拟功能[mergeWith](qundocommand.html#mergeWith)（ ） 。这些功能所使用的[QUndoStack.push](qundostack.html#push)（ ） 。

为了支持宏命令，一个QUndoCommand对象可以有任意数量的子命令。撤消或重做父的命令会让孩子命令撤消或重做。命令可以在构造函数中显式地指定给父母。在这种情况下，该命令将被父所拥有。

在这种情况下，父通常是一个空命令，因为它不提供它自己的实现的[undo](qundocommand.html#undo)（）和[redo](qundocommand.html#redo)（ ） 。相反，它使用这些功能的基本实现，它只是简单的调用[undo](qundocommand.html#undo)（）或[redo](qundocommand.html#redo)（ ）在它的所有子项。家长应，然而，有一个有意义的[text](qundocommand.html#text)（ ） 。

```
 QUndoCommand *insertRed = new QUndoCommand(); // an empty command
 insertRed->setText("insert red text");

 new InsertText(document, idx, text, insertRed); // becomes child of insertRed
 new SetColor(document, idx, text.length(), [Qt](qt.html).red, insertRed);

 stack.push(insertRed);

```

另一种方式来创建宏是使用便利的功能[QUndoStack.beginMacro](qundostack.html#beginMacro)（）和[QUndoStack.endMacro](qundostack.html#endMacro)（ ） 。

* * *

## Method Documentation

```
QUndoCommand.__init__ (self, QUndoCommand parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QUndoCommand](qundocommand.html)与父对象_parent_。

If _parent_不为0 ，则该命令被添加到父节点的子列表。父命令则拥有这个命令将在其析构函数删除它。

**See also** [~QUndoCommand](qundocommand.html#dtor.QUndoCommand)（ ） 。

```
QUndoCommand.__init__ (self, QString text, QUndoCommand parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QUndoCommand](qundocommand.html)与给定对象_parent_和_text_。

If _parent_不为0 ，则该命令被添加到父节点的子列表。父命令则拥有这个命令将在其析构函数删除它。

**See also** [~QUndoCommand](qundocommand.html#dtor.QUndoCommand)（ ） 。

```
QString QUndoCommand.actionText (self)
```

返回描述了这个命令做了简短的文本字符串，例如， “插入文字” 。

该文本时使用的堆栈的撤消的文本属性和重复动作被更新。

此功能被引入Qt的4.8 。

**See also** [text](qundocommand.html#text)（ ）[setText](qundocommand.html#setText)（ ）[QUndoStack.createUndoAction](qundostack.html#createUndoAction)（）和[QUndoStack.createRedoAction](qundostack.html#createRedoAction)（ ） 。

```
QUndoCommand QUndoCommand.child (self, int index)
```

[

在返回的子命令_index_。

此功能被引入Qt的4.4 。

](qundocommand.html)

[**See also**](qundocommand.html) [childCount](qundocommand.html#childCount)（）和[QUndoStack.command](qundostack.html#command)（ ） 。

```
int QUndoCommand.childCount (self)
```

返回此命令子命令的数量。

此功能被引入Qt的4.4 。

**See also** [child](qundocommand.html#child)（ ） 。

```
int QUndoCommand.id (self)
```

返回此命令的ID 。

命令ID用来在命令压缩。它必须是一个整数独此命令的类，或者-1如果命令不支持压缩。

如果命令支持压缩这个函数必须在派生类中重写以返回正确的ID 。基实现返回-1 。

[QUndoStack.push](qundostack.html#push)（）将只尝试合并两个命令，如果它们具有相同的ID，并且该ID不是-1。

**See also** [mergeWith](qundocommand.html#mergeWith)（）和[QUndoStack.push](qundostack.html#push)（ ） 。

```
bool QUndoCommand.mergeWith (self, QUndoCommand other)
```

尝试与合并这个命令_command_。成功时返回TRUE ，否则返回False 。

如果这个函数返回True，则调用此命令的[redo](qundocommand.html#redo)（ ）必须具有相同的效果，既重做这个命令和_command_。同样，调用此命令的[undo](qundocommand.html#undo)（ ）必须具有相同的效果撤消_command_与此命令。

[QUndoStack](qundostack.html)只会尝试合并两个命令，如果他们有相同的id ，而id是不是-1 。

默认实现返回False 。

```
 bool AppendText.mergeWith(const [QUndoCommand](qundocommand.html) *other)
 {
     if (other->id() != id()) // make sure other is also an AppendText command
         return false;
     m_text += static_cast<const AppendText*>(other)->m_text;
     return true;
 }

```

**See also** [id](qundocommand.html#id)（）和[QUndoStack.push](qundostack.html#push)（ ） 。

```
QUndoCommand.redo (self)
```

适用变更的文件。这个函数必须在派生类中实现。调用[QUndoStack.push](qundostack.html#push)（ ）[QUndoStack.undo](qundostack.html#undo)（）或[QUndoStack.redo](qundostack.html#redo)从这个函数（ ）导致未定义beahavior 。

默认实现调用重做（ ）对所有的子命令。

**See also** [undo](qundocommand.html#undo)（ ） 。

```
QUndoCommand.setText (self, QString text)
```

设置为命令的文本_text_规定。

指定文本应描述了这个命令的作用很短的用户可读的字符串。

如果你需要有两个不同的字符串[text](qundocommand.html#text)（）和[actionText](qundocommand.html#actionText)（ ） ，将它们分开为“\ n ” ，并传递到这个函数。即使你在开发过程中不使用此功能的英文字符串，你仍然可以让翻译使用两个不同的字符串，以匹配特定语言的需求。所描述的特征和​​功能[actionText](qundocommand.html#actionText)（ ）是因为Qt的4.8可用。

**See also** [text](qundocommand.html#text)（ ）[actionText](qundocommand.html#actionText)（ ）[QUndoStack.createUndoAction](qundostack.html#createUndoAction)（）和[QUndoStack.createRedoAction](qundostack.html#createRedoAction)（ ） 。

```
QString QUndoCommand.text (self)
```

返回描述了这个命令做了简短的文本字符串，例如， “插入文字” 。

该文本是用于项目的名称[QUndoView](qundoview.html)。

**See also** [actionText](qundocommand.html#actionText)（ ）[setText](qundocommand.html#setText)（ ）[QUndoStack.createUndoAction](qundostack.html#createUndoAction)（）和[QUndoStack.createRedoAction](qundostack.html#createRedoAction)（ ） 。

```
QUndoCommand.undo (self)
```

恢复一个变化到文档中。撤消（）被调用后，文件的状态应该是和以前一样[redo](qundocommand.html#redo)（ ）被调用。这个函数必须在派生类中实现。调用[QUndoStack.push](qundostack.html#push)（ ）[QUndoStack.undo](qundostack.html#undo)（）或[QUndoStack.redo](qundostack.html#redo)从这个函数（ ）导致未定义beahavior 。

默认实现调用撤消（ ）上的所有子命令的顺序相反。

**See also** [redo](qundocommand.html#redo)（ ） 。