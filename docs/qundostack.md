# QUndoStack Class Reference

## [[QtGui](index.htm) module]

该QUndoStack类是一个堆栈的[QUndoCommand](qundocommand.html)对象。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `beginMacro (self, QString text)`
*   `bool canRedo (self)`
*   `bool canUndo (self)`
*   `int cleanIndex (self)`
*   `clear (self)`
*   `QUndoCommand command (self, int index)`
*   `int count (self)`
*   `QAction createRedoAction (self, QObject parent, QString prefix = QString())`
*   `QAction createUndoAction (self, QObject parent, QString prefix = QString())`
*   `endMacro (self)`
*   `int index (self)`
*   `bool isActive (self)`
*   `bool isClean (self)`
*   `push (self, QUndoCommand cmd)`
*   `redo (self)`
*   `QString redoText (self)`
*   `setActive (self, bool active = True)`
*   `setClean (self)`
*   `setIndex (self, int idx)`
*   `setUndoLimit (self, int limit)`
*   `QString text (self, int idx)`
*   `undo (self)`
*   `int undoLimit (self)`
*   `QString undoText (self)`

### Special Methods

*   `__len__ (self)`

### Qt Signals

*   `void canRedoChanged (bool)`
*   `void canUndoChanged (bool)`
*   `void cleanChanged (bool)`
*   `void indexChanged (int)`
*   `void redoTextChanged (const QString&)`
*   `void undoTextChanged (const QString&)`

* * *

## Detailed Description

该QUndoStack类是一个堆栈的[QUndoCommand](qundocommand.html)对象。

对于Qt的复原框架的概述，请参阅[overview document](index.htm)。

一个撤消堆栈保持堆栈已应用于文档的命令。

新的命令使用压入堆栈[push](qundostack.html#push)（ ） 。命令可以撤消和重做的使用[undo](qundostack.html#undo)（）和[redo](qundostack.html#redo)（ ） ，或通过触发返回的行动[createUndoAction](qundostack.html#createUndoAction)（）和[createRedoAction](qundostack.html#createRedoAction)（ ） 。

QUndoStack跟踪的_current_命令。这是将由下一个呼叫要执行的命令[redo](qundostack.html#redo)（ ） 。这个命令的指数是由返回[index](qundostack.html#index)（ ） 。编辑的对象的状态可以卷向前或向后使用[setIndex](qundostack.html#setIndex)（ ） 。如果堆栈最上面的命令已经被重做，[index](qundostack.html#index)（ ）等于[count](qundostack.html#count)（ ） 。

QUndoStack提供支持撤消和重做操作，命令压缩，命令宏和支持的概念_clean state_。

### Undo and Redo Actions

QUndoStack提供方便的撤销和重做[QAction](qaction.html)对象，它们可以被插入到一个菜单或工具栏上。当命令被撤消或重做， QUndoStack更新这些行动的文本属性，以反映什么样的变化，他们将触发。当没有命令可用于撤消或重做的动作也被禁用。这些行动是由返回[QUndoStack.createUndoAction](qundostack.html#createUndoAction)（）和[QUndoStack.createRedoAction](qundostack.html#createRedoAction)（ ） 。

### Command Compression and Macros

当几个命令可以被压缩成可以撤消一个命令，并在重做一个单一的操作命令压缩是非常有用的。例如，当用户在文本编辑字符时，一个新的命令被创建。这个命令插入字符插入到文档中光标所在的位置。但是，对于用户更加方便，能够撤消或重做整个单词，句子或段落打字。命令压缩使这些单字符命令合并到其中插入或删除文本部分的单一命令。欲了解更多信息，请参见[QUndoCommand.mergeWith](qundocommand.html#mergeWith)（）和[push](qundostack.html#push)（ ） 。

命令宏命令，所有这一切都是撤消和重做一次过的序列。命令宏被赋予一个命令子命令列表创建的。撤消或重做父的命令会让孩子命令撤消或重做。命令宏可以显式的指定在一个父级要创建[QUndoCommand](qundocommand.html)构造函数，或者使用的方便功能[beginMacro](qundostack.html#beginMacro)（）和[endMacro](qundostack.html#endMacro)（ ） 。

虽然压缩命令和宏似乎有同样的效果给用户，他们往往有不同的用途中的应用程序。执行的微小变化到一个文件的命令可以有效地压缩，如果没有必要单独地记录它们，并且如果只有较大的变化是相关的用户。然而，对于需要被单独记录的，或者是那些不能被压缩的命令，这是很有用的宏，以提供更方便的用户体验，同时保持每个命令的记录。

### Clean State

QUndoStack支持的清洁状态的概念。当文件被保存到磁盘，堆栈可以使用被标记为干净[setClean](qundostack.html#setClean)（ ） 。只要堆栈通过撤销和重做命令返回到这个状态，它发出的信号[cleanChanged](qundostack.html#cleanChanged)（ ） 。当堆栈离开干净的状态，这个信号被发射也。这个信号通常是用来启用和禁用应用程序中保存的动作，并更新文档的标题，以反映它包含未保存的更改。

* * *

## Method Documentation

```
QUndoStack.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空撤消堆栈与父_parent_。该协议栈将首先在干净的状态。如果_parent_是[QUndoGroup](qundogroup.html)对象，堆栈会自动添加到组中。

**See also** [push](qundostack.html#push)（ ） 。

```
QUndoStack.beginMacro (self, QString text)
```

开始一个宏命令组成与给定_text_描述。

由指定的描述一个空的命令_text_被压入堆栈。压入堆栈上的任何后续命令将被追加到空命令的孩子，直到[endMacro](qundostack.html#endMacro)（）被调用。

调用beginMacro （）和[endMacro](qundostack.html#endMacro)（ ）可以嵌套，但每次调用beginMacro （ ）必须有匹配的调用[endMacro](qundostack.html#endMacro)（ ） 。

虽然宏组成，堆栈被禁用。这意味着：

*   [indexChanged](qundostack.html#indexChanged)() and [cleanChanged](qundostack.html#cleanChanged)() are not emitted,
*   [canUndo](qundostack.html#canUndo)() and [canRedo](qundostack.html#canRedo)() return false,
*   calling [undo](qundostack.html#undo)() or [redo](qundostack.html#redo)() has no effect,
*   the undo/redo actions are disabled.

堆栈是可用的，适当的信号被发射时，[endMacro](qundostack.html#endMacro)（）被调用用于最外层的宏。

```
 stack.beginMacro("insert red text");
 stack.push(new InsertText(document, idx, text));
 stack.push(new SetColor(document, idx, text.length(), [Qt](qt.html).red));
 stack.endMacro(); // indexChanged() is emitted

```

这段代码等同于：

```
 [QUndoCommand](qundocommand.html) *insertRed = new [QUndoCommand](qundocommand.html)(); // an empty command
 insertRed->setText("insert red text");

 new InsertText(document, idx, text, insertRed); // becomes child of insertRed
 new SetColor(document, idx, text.length(), [Qt](qt.html).red, insertRed);

 stack.push(insertRed);

```

**See also** [endMacro](qundostack.html#endMacro)（ ） 。

```
bool QUndoStack.canRedo (self)
```

返回True如果有可用的重做命令，否则返回False 。

如果堆栈为空或者栈顶的命令已经被重做这个函数返回False 。

代名词[index](qundostack.html#index)（）==[count](qundostack.html#count)（ ） 。

**See also** [index](qundostack.html#index)（）和[canUndo](qundostack.html#canUndo)（ ） 。

```
bool QUndoStack.canUndo (self)
```

返回True如果有可用撤消命令，否则返回False 。

这个函数返回False，如果堆栈为空，或者如果堆栈底部的命令已被撤销。

代名词[index](qundostack.html#index)（）== 0 。

**See also** [index](qundostack.html#index)（）和[canRedo](qundostack.html#canRedo)（ ） 。

```
int QUndoStack.cleanIndex (self)
```

返回干净的索引。这是该指数在这[setClean](qundostack.html#setClean)（ ）被调用。

堆栈可能没有一个干净的索引。出现这种情况，如果一个文件被保存，一些命令被撤消，那么一个新的命令被按下。自[push](qundostack.html#push)（ ）删除所有推新命令之前未完成的指令，堆栈不能返回到干净的状态了。在这种情况下，该函数返回-1 。

**See also** [isClean](qundostack.html#isClean)（）和[setClean](qundostack.html#setClean)（ ） 。

```
QUndoStack.clear (self)
```

清除命令堆栈删除其上的所有命令，并返回堆栈到干净的状态。

命令都不会撤消或重做;编辑的对象的状态保持不变。

此功能通常用于当该文件的内容被放弃。

**See also** [QUndoStack](qundostack.html#QUndoStack)（ ） 。

```
QUndoCommand QUndoStack.command (self, int index)
```

[

在返回一个const指针，指向命令_index_。

这个函数返回一个const指针，因为修改的命令，一旦被压入堆栈和执行的，几乎总是会导致文档的状态的腐败，如果命令是后来撤消或重做。

此功能被引入Qt的4.4 。

](qundocommand.html)

[**See also**](qundocommand.html) [QUndoCommand.child](qundocommand.html#child)（ ） 。

```
int QUndoStack.count (self)
```

返回命令的堆栈数。宏命令都算作一个命令。

**See also** [index](qundostack.html#index)（ ）[setIndex](qundostack.html#setIndex)（）和[command](qundostack.html#command)（ ） 。

```
QAction QUndoStack.createRedoAction (self, QObject parent, QString prefix = QString())
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qaction.html)

[创建一个重做](qaction.html)[QAction](qaction.html)与给定对象_parent_。

触发此动作将导致调用[redo](qundostack.html#redo)（ ） 。这个动作的文本命令，将在下一呼叫重做文本[redo](qundostack.html#redo)（ ） ，前缀由指定的_prefix_。如果没有可用的重做命令，这个动作将被禁用。

If _prefix_为空，则默认模板“重做％ 1 ”是用来代替前缀。 Qt的4.8之前，前缀“重做”被默认使用。

**See also** [createUndoAction](qundostack.html#createUndoAction)（ ）[canRedo](qundostack.html#canRedo)（）和[QUndoCommand.text](qundocommand.html#text)（ ） 。

```
QAction QUndoStack.createUndoAction (self, QObject parent, QString prefix = QString())
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qaction.html)

[创建一个撤消](qaction.html)[QAction](qaction.html)与给定对象_parent_。

触发此动作将导致调用[undo](qundostack.html#undo)（ ） 。这个动作的文本将在下一呼叫撤消命令的文本[undo](qundostack.html#undo)（ ） ，前缀由指定的_prefix_。如果没有可用的undo命令，这个动作将被禁用。

If _prefix_为空，则使用默认模板，而不是前缀“还原％ 1 ” 。 Qt的4.8之前，前缀“撤消”被默认使用。

**See also** [createRedoAction](qundostack.html#createRedoAction)（ ）[canUndo](qundostack.html#canUndo)（）和[QUndoCommand.text](qundocommand.html#text)（ ） 。

```
QUndoStack.endMacro (self)
```

结束一个宏命令组成。

如果是这样的最外层的宏在一组嵌套的宏，该功能会发出[indexChanged](qundostack.html#indexChanged)（ ）一旦整个宏命令。

**See also** [beginMacro](qundostack.html#beginMacro)（ ） 。

```
int QUndoStack.index (self)
```

返回当前指令的索引。这是将要到下一个调用执行的命令[redo](qundostack.html#redo)（ ） 。它并不总是在堆栈中最上面的命令，因为一些命令可能已被撤消。

**See also** [setIndex](qundostack.html#setIndex)（ ）[undo](qundostack.html#undo)（ ）[redo](qundostack.html#redo)（）和[count](qundostack.html#count)（ ） 。

```
bool QUndoStack.isActive (self)
```

```
bool QUndoStack.isClean (self)
```

如果堆栈是在干净的状态，返回True，否则返回False 。

**See also** [setClean](qundostack.html#setClean)（）和[cleanIndex](qundostack.html#cleanIndex)（ ） 。

```
QUndoStack.push (self, QUndoCommand cmd)
```

该_cmd_说法有它的所有权转移给Qt的。

Pushes _cmd_在堆栈上或与最近执行的命令将其合并。在任一情况下，执行时_cmd_通过调用其[redo](qundostack.html#redo)（）函数。

If _cmd_的ID不是-1，如果ID是相同的最近执行的命令的，[QUndoStack](qundostack.html)将尝试通过调用合并两个命令[QUndoCommand.mergeWith](qundocommand.html#mergeWith)（ ）在最近执行的命令。如果[QUndoCommand.mergeWith](qundocommand.html#mergeWith)（ ）返回True ，_cmd_被删除。

在所有其他情况下，_cmd_简直是压入堆栈。

如果命令之前被撤销_cmd_被按下时，电流指令和它上面的所有命令都被删除。故_cmd_总是最终被堆栈中的最顶层。

一旦命令被按下时，堆栈采用它的所有权。有没有getter方法​​返回的命令，因为它修改它已经被执行后，将几乎总是导致文档的状态的腐败。

**See also** [QUndoCommand.id](qundocommand.html#id)（）和[QUndoCommand.mergeWith](qundocommand.html#mergeWith)（ ） 。

```
QUndoStack.redo (self)
```

这种方法也是一个Qt槽与C + +的签名`void redo()`。

通过调用重做当前命令[QUndoCommand.redo](qundocommand.html#redo)（ ） 。增加当前命令索引。

如果堆栈为空，或者如果堆栈顶部的命令已经被重做，这个函数不执行任何操作。

**See also** [undo](qundostack.html#undo)（）和[index](qundostack.html#index)（ ） 。

```
QString QUndoStack.redoText (self)
```

返回的命令，将在下一呼叫重做文本[redo](qundostack.html#redo)（ ） 。

**See also** [QUndoCommand.actionText](qundocommand.html#actionText)（）和[undoText](qundostack.html#undoText)（ ） 。

```
QUndoStack.setActive (self, bool active = True)
```

这种方法也是一个Qt槽与C + +的签名`void setActive(bool = 1)`。

```
QUndoStack.setClean (self)
```

这种方法也是一个Qt槽与C + +的签名`void setClean()`。

标记堆栈干净并发出[cleanChanged](qundostack.html#cleanChanged)（）如果堆栈是不是已经干净了。

每当通过使用撤销/的堆栈恢复到这个状态重做命令，它发出的信号[cleanChanged](qundostack.html#cleanChanged)（ ） 。当堆栈离开干净的状态，这个信号被发射也。

**See also** [isClean](qundostack.html#isClean)（）和[cleanIndex](qundostack.html#cleanIndex)（ ） 。

```
QUndoStack.setIndex (self, int idx)
```

这种方法也是一个Qt槽与C + +的签名`void setIndex(int)`。

反复调用[undo](qundostack.html#undo)（）或[redo](qundostack.html#redo)（ ），直到当前命令指数达到_idx_。此功能可用于滚动文档的状态向前向后。[indexChanged](qundostack.html#indexChanged)（）被发射一次。

**See also** [index](qundostack.html#index)（ ）[count](qundostack.html#count)（ ）[undo](qundostack.html#undo)（）和[redo](qundostack.html#redo)（ ） 。

```
QUndoStack.setUndoLimit (self, int limit)
```

```
QString QUndoStack.text (self, int idx)
```

在索引返回的命令的文本_idx_。

**See also** [beginMacro](qundostack.html#beginMacro)（ ） 。

```
QUndoStack.undo (self)
```

这种方法也是一个Qt槽与C + +的签名`void undo()`。

通过调用撤消当前命令下面的命令[QUndoCommand.undo](qundocommand.html#undo)（ ） 。减少当前命令索引。

如果堆栈是空的，或者如果堆栈底部的命令已被撤销，该函数不起作用。

**See also** [redo](qundostack.html#redo)（）和[index](qundostack.html#index)（ ） 。

```
int QUndoStack.undoLimit (self)
```

```
QString QUndoStack.undoText (self)
```

返回的命令，将在下一呼叫撤消文本[undo](qundostack.html#undo)（ ） 。

**See also** [QUndoCommand.actionText](qundocommand.html#actionText)（）和[redoText](qundostack.html#redoText)（ ） 。

```
 QUndoStack.__len__ (self)
```

* * *

## Qt Signal Documentation

```
void canRedoChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时的值[canRedo](qundostack.html#canRedo)（）的变化。它是用来启用或禁用通过返回重做动作[createRedoAction](qundostack.html#createRedoAction)（ ） 。_canRedo_指定的新值。

```
void canUndoChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时的值[canUndo](qundostack.html#canUndo)（）的变化。它是用来启用或禁用通过返回的撤消操作[createUndoAction](qundostack.html#createUndoAction)（ ） 。_canUndo_指定的新值。

```
void cleanChanged (bool)
```

这是该信号的默认超载。

每当堆栈进入或离开干净的状态这个信号被发射。如果_clean_诚然，堆栈是在一个干净的状态，否则这个信号表明，它已经离开了干净的状态。

**See also** [isClean](qundostack.html#isClean)（）和[setClean](qundostack.html#setClean)（ ） 。

```
void indexChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的命令修改文档的状态。这发生在一个命令撤消或重做。当一个宏命令撤消或重做，或[setIndex](qundostack.html#setIndex)（）被调用时，这个信号被发射一次。

_idx_指定当前命令，即索引。这将是到下一个调用执行的命令[redo](qundostack.html#redo)（ ） 。

**See also** [index](qundostack.html#index)（）和[setIndex](qundostack.html#setIndex)（ ） 。

```
void redoTextChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的值[redoText](qundostack.html#redoText)（）的变化。它是用来更新由返回重做动作的text属性[createRedoAction](qundostack.html#createRedoAction)（ ） 。_redoText_指定新文本。

```
void undoTextChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的值[undoText](qundostack.html#undoText)（）的变化。它是用来更新返回的撤消操作的text属性[createUndoAction](qundostack.html#createUndoAction)（ ） 。_undoText_指定新文本。