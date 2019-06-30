# QUndoGroup Class Reference

## [[QtGui](index.htm) module]

该QUndoGroup类是一组[QUndoStack](qundostack.html)对象。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QUndoStack activeStack (self)`
*   `addStack (self, QUndoStack stack)`
*   `bool canRedo (self)`
*   `bool canUndo (self)`
*   `QAction createRedoAction (self, QObject parent, QString prefix = QString())`
*   `QAction createUndoAction (self, QObject parent, QString prefix = QString())`
*   `bool isClean (self)`
*   `redo (self)`
*   `QString redoText (self)`
*   `removeStack (self, QUndoStack stack)`
*   `setActiveStack (self, QUndoStack stack)`
*   `list-of-QUndoStack stacks (self)`
*   `undo (self)`
*   `QString undoText (self)`

### Qt Signals

*   `void activeStackChanged (QUndoStack *)`
*   `void canRedoChanged (bool)`
*   `void canUndoChanged (bool)`
*   `void cleanChanged (bool)`
*   `void indexChanged (int)`
*   `void redoTextChanged (const QString&)`
*   `void undoTextChanged (const QString&)`

* * *

## Detailed Description

该QUndoGroup类是一组[QUndoStack](qundostack.html)对象。

对于Qt的撤消框架的概述，请参阅[overview](index.htm)。

一个应用程序通常有多个撤消堆栈，每一个打开的文档。与此同时，应用程序通常有一个撤消操作和一个重做动作，这会触发撤消或重做的活动文档。

QUndoGroup是一组[QUndoStack](qundostack.html)物，其中之一可以是活动的。它有一个[undo](qundogroup.html#undo)（）和[redo](qundogroup.html#redo)（）槽，它调用[QUndoStack.undo](qundostack.html#undo)（）和[QUndoStack.redo](qundostack.html#redo)（ ）为活动堆栈。它还具有功能[createUndoAction](qundogroup.html#createUndoAction)（）和[createRedoAction](qundogroup.html#createRedoAction)（ ） 。这些函数返回的动作相同的行为方式的那些返回[QUndoStack.createUndoAction](qundostack.html#createUndoAction)（）和[QUndoStack.createRedoAction](qundostack.html#createRedoAction)活动堆栈的（） 。

堆栈被添加到一个组[addStack](qundogroup.html#addStack)（ ）中，用去除[removeStack](qundogroup.html#removeStack)（ ） 。堆栈是隐式添加到组时，同组创建为其父[QObject](qobject.html)。

这是程序员的责任来指定堆栈积极通过调用[QUndoStack.setActive](qundostack.html#active-prop)（ ） ，通常当相关文档窗口接收焦点。活动堆栈也可与设置[setActiveStack](qundogroup.html#setActiveStack)（） ，并且通过返回[activeStack](qundogroup.html#activeStack)（ ） 。

当一个堆栈使用添加到组[addStack](qundogroup.html#addStack)（ ） ，该组不采取栈的所有权。这意味着在堆栈必须单独从组中删除。当一个堆栈被删除，它会自动从组中删除。堆栈只能属于一个组。将它添加到另一个组将导致它从以前的组中删除。

一个QUndoGroup也是有用会同[QUndoView](qundoview.html)。如果[QUndoView](qundoview.html)设置为观看利用一组[QUndoView.setGroup](qundoview.html#setGroup)（ ） ，它会自动更新以显示当前堆栈。

* * *

## Method Documentation

```
QUndoGroup.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个空的[QUndoGroup](qundogroup.html)与父对象_parent_。

**See also** [addStack](qundogroup.html#addStack)（ ） 。

```
QUndoStack QUndoGroup.activeStack (self)
```

[

返回该组的活动堆栈。

如果没有堆叠的活跃，或者如果组为空，则该函数返回0 。

](qundostack.html)

[**See also**](qundostack.html) [setActiveStack](qundogroup.html#setActiveStack)（）和[QUndoStack.setActive](qundostack.html#active-prop)（ ） 。

```
QUndoGroup.addStack (self, QUndoStack stack)
```

添加_stack_这一组。本集团不会采取栈的所有权。增加堆栈的一组的另一种方式是通过指定组为堆栈的父[QObject](qobject.html)在[QUndoStack.QUndoStack](qundostack.html#QUndoStack)（ ） 。在这种情况下，堆叠时的组被删除被删除，在以通常的方式[QObjects](index.htm#qobjects)。

**See also** [removeStack](qundogroup.html#removeStack)（ ）[stacks](qundogroup.html#stacks)（）和[QUndoStack.QUndoStack](qundostack.html#QUndoStack)（ ） 。

```
bool QUndoGroup.canRedo (self)
```

返回活动堆栈的值[QUndoStack.canRedo](qundostack.html#canRedo)（ ） 。

如果没有堆叠的活跃，或者如果组是空的，这个函数返回False 。

**See also** [canUndo](qundogroup.html#canUndo)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
bool QUndoGroup.canUndo (self)
```

返回活动堆栈的值[QUndoStack.canUndo](qundostack.html#canUndo)（ ） 。

如果没有堆叠的活跃，或者如果组是空的，这个函数返回False 。

**See also** [canRedo](qundogroup.html#canRedo)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
QAction QUndoGroup.createRedoAction (self, QObject parent, QString prefix = QString())
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qaction.html)

[创建一个重做](qaction.html)[QAction](qaction.html)与父对象_parent_。

触发此动作将导致调用[QUndoStack.redo](qundostack.html#redo)（）在有源堆栈。这一行动的文本将永远是命令，将在下一呼叫重做文本[redo](qundogroup.html#redo)（ ） ，由前缀_prefix_。如果没有可用的重做命令，如果组为空或者如果没有一个栈的活跃，这个动作将被禁用。

If _prefix_为空，则默认模板“重做％ 1 ”是用来代替前缀。 Qt的4.8之前，前缀“重做”被默认使用。

**See also** [createUndoAction](qundogroup.html#createUndoAction)（ ）[canRedo](qundogroup.html#canRedo)（）和[QUndoCommand.text](qundocommand.html#text)（ ） 。

```
QAction QUndoGroup.createUndoAction (self, QObject parent, QString prefix = QString())
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qaction.html)

[创建一个撤消](qaction.html)[QAction](qaction.html)与父对象_parent_。

触发此动作将导致调用[QUndoStack.undo](qundostack.html#undo)（）在有源堆栈。这一行动的文本将永远是命令，将在下一呼叫撤消文本[undo](qundogroup.html#undo)（ ） ，由前缀_prefix_。如果没有可用的undo命令，如果组为空或者如果没有一个栈的活跃，这个动作将被禁用。

If _prefix_为空，则使用默认模板，而不是前缀“还原％ 1 ” 。 Qt的4.8之前，前缀“撤消”被默认使用。

**See also** [createRedoAction](qundogroup.html#createRedoAction)（ ）[canUndo](qundogroup.html#canUndo)（）和[QUndoCommand.text](qundocommand.html#text)（ ） 。

```
bool QUndoGroup.isClean (self)
```

返回活动堆栈的值[QUndoStack.isClean](qundostack.html#isClean)（ ） 。

如果没有堆叠的活跃，或者如果组是空的，这个函数返回True。

**See also** [setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
QUndoGroup.redo (self)
```

这种方法也是一个Qt槽与C + +的签名`void redo()`。

电话[QUndoStack.redo](qundostack.html#redo)（）在有源堆栈。

如果没有堆叠的活跃，或者如果组是空的，这个函数不执行任何操作。

**See also** [undo](qundogroup.html#undo)（ ）[canRedo](qundogroup.html#canRedo)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
QString QUndoGroup.redoText (self)
```

返回活动堆栈的值[QUndoStack.redoText](qundostack.html#redoText)（ ） 。

如果没有堆叠的活跃，或者如果组是空的，这个函数返回一个空字符串。

**See also** [undoText](qundogroup.html#undoText)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
QUndoGroup.removeStack (self, QUndoStack stack)
```

移除_stack_从本组。如果堆栈是活动堆栈组中，活动堆栈变为0 。

**See also** [addStack](qundogroup.html#addStack)（ ）[stacks](qundogroup.html#stacks)（）和[QUndoStack.~QUndoStack](qundostack.html#dtor.QUndoStack)（ ） 。

```
QUndoGroup.setActiveStack (self, QUndoStack stack)
```

这种方法也是一个Qt槽与C + +的签名`void setActiveStack(QUndoStack *)`。

设置这个组的主栈_stack_。

如果堆栈是不是该组的成员，这个函数不执行任何操作。

代名词调用[QUndoStack.setActive](qundostack.html#active-prop)（ ）上_stack_。

返回的行动[createUndoAction](qundogroup.html#createUndoAction)（）和[createRedoAction](qundogroup.html#createRedoAction)（）现在将表现在方法一样通过返回_stack_的[QUndoStack.createUndoAction](qundostack.html#createUndoAction)（）和[QUndoStack.createRedoAction](qundostack.html#createRedoAction)（ ） 。

**See also** [QUndoStack.setActive](qundostack.html#active-prop)（）和[activeStack](qundogroup.html#activeStack)（ ） 。

```
list-of-QUndoStack QUndoGroup.stacks (self)
```

返回该组堆叠的列表。

**See also** [addStack](qundogroup.html#addStack)（）和[removeStack](qundogroup.html#removeStack)（ ） 。

```
QUndoGroup.undo (self)
```

这种方法也是一个Qt槽与C + +的签名`void undo()`。

电话[QUndoStack.undo](qundostack.html#undo)（）在有源堆栈。

如果没有堆叠的活跃，或者如果组是空的，这个函数不执行任何操作。

**See also** [redo](qundogroup.html#redo)（ ）[canUndo](qundogroup.html#canUndo)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
QString QUndoGroup.undoText (self)
```

返回活动堆栈的值[QUndoStack.undoText](qundostack.html#undoText)（ ） 。

如果没有堆叠的活跃，或者如果组是空的，这个函数返回一个空字符串。

**See also** [redoText](qundogroup.html#redoText)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

* * *

## Qt Signal Documentation

```
void activeStackChanged (QUndoStack *)
```

这是该信号的默认超载。

这个信号被发射时该组的活动堆栈变化。这可能是因为[setActiveStack](qundogroup.html#setActiveStack)（）或[QUndoStack.setActive](qundostack.html#active-prop)（ ）被调用时，或者当活动堆栈的形式组中删除。_stack_是新的活动堆栈。如果没有堆栈处于活动状态，_stack_为0。

**See also** [setActiveStack](qundogroup.html#setActiveStack)（）和[QUndoStack.setActive](qundostack.html#active-prop)（ ） 。

```
void canRedoChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时的有效堆发射[QUndoStack.canRedoChanged](qundostack.html#canRedoChanged)（）或活动堆栈的变化。

_canRedo_是新的状态，则返回False活动堆栈为0 。

**See also** [QUndoStack.canRedoChanged](qundostack.html#canRedoChanged)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
void canUndoChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时的有效堆发射[QUndoStack.canUndoChanged](qundostack.html#canUndoChanged)（）或活动堆栈的变化。

_canUndo_是新的状态，则返回False活动堆栈为0 。

**See also** [QUndoStack.canUndoChanged](qundostack.html#canUndoChanged)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
void cleanChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时的有效堆发射[QUndoStack.cleanChanged](qundostack.html#cleanChanged)（）或活动堆栈的变化。

_clean_是新的状态，或者是当活动堆栈为0 。

**See also** [QUndoStack.cleanChanged](qundostack.html#cleanChanged)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
void indexChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的有效堆发射[QUndoStack.indexChanged](qundostack.html#indexChanged)（）或活动堆栈的变化。

_idx_为新的当前索引，或者0，如果活动堆栈为0 。

**See also** [QUndoStack.indexChanged](qundostack.html#indexChanged)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
void redoTextChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的有效堆发射[QUndoStack.redoTextChanged](qundostack.html#redoTextChanged)（）或活动堆栈的变化。

_redoText_是新的状态，或者一个空字符串，如果活动堆栈为0 。

**See also** [QUndoStack.redoTextChanged](qundostack.html#redoTextChanged)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。

```
void undoTextChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的有效堆发射[QUndoStack.undoTextChanged](qundostack.html#undoTextChanged)（）或活动堆栈的变化。

_undoText_是新的状态，或者一个空字符串，如果活动堆栈为0 。

**See also** [QUndoStack.undoTextChanged](qundostack.html#undoTextChanged)（）和[setActiveStack](qundogroup.html#setActiveStack)（ ） 。