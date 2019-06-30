# QDropEvent Class Reference

## [[QtGui](index.htm) module]

该QDropEvent类提供当拖放动作完成它发送的事件。[More...](#details)

继承[QEvent](qevent.html)和[QMimeSource](qmimesource.html)。

通过继承[QDragMoveEvent](qdragmoveevent.html)。

### Methods

*   `__init__ (self, QPoint pos, Qt.DropActions actions, QMimeData data, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers, QEvent.Type type = QEvent.Drop)`
*   `__init__ (self, QDropEvent)`
*   `acceptProposedAction (self)`
*   `Qt.DropAction dropAction (self)`
*   `QByteArray encodedData (self, str)`
*   `str format (self, int n = 0)`
*   `Qt.KeyboardModifiers keyboardModifiers (self)`
*   `QMimeData mimeData (self)`
*   `Qt.MouseButtons mouseButtons (self)`
*   `QPoint pos (self)`
*   `Qt.DropActions possibleActions (self)`
*   `Qt.DropAction proposedAction (self)`
*   `bool provides (self, str)`
*   `setDropAction (self, Qt.DropAction action)`
*   `QWidget source (self)`

* * *

## Detailed Description

该QDropEvent类提供当拖放动作完成它发送的事件。

当一个widget[accepts drop events](qwidget.html#acceptDrops-prop)，它会收到此事件，如果它已经接受了最新的[QDragEnterEvent](qdragenterevent.html) or [QDragMoveEvent](qdragmoveevent.html)发送给它。

drop事件中包含一个建议的行动，可从[proposedAction](qdropevent.html#proposedAction)（ ） ，窗口小部件可以选择接受或忽略。如果操作可以通过小部件来处理，你应该调用[acceptProposedAction](qdropevent.html#acceptProposedAction)（）函数。由于建议的动作可以组合[Qt.DropAction](qt.html#DropAction-enum)值，它可能是有用要么选择这些值作为默认行为之一的，或要求用户选择自己喜欢的动作。

如果拟议的拖放操作是不适合的，也许是因为你的自定义窗口小部件不支持该操作，您可以使用任何的更换[possible drop actions](qdropevent.html#possibleActions)通过调用[setDropAction](qdropevent.html#setDropAction)（ ）与您的首选动作。如果设置的值不存在由返回值的按位或组合[possibleActions](qdropevent.html#possibleActions)（ ） ，默认的复制操作将被使用。一旦更换拖放操作已经设定，调用accept （ ）代替[acceptProposedAction](qdropevent.html#acceptProposedAction)（ ）来完成拖放操作。

该[mimeData](qdropevent.html#mimeData)（）函数提供的数据在一个滴在插件[QMimeData](qmimedata.html)对象。这包含了MIME类型，除了数据本身的数据的信息。

* * *

## Method Documentation

```
QDropEvent.__init__ (self, QPoint pos, Qt.DropActions actions, QMimeData data, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers, QEvent.Type type = QEvent.Drop)
```

构造有一定的下降事件_type_对应于一滴在由所指定的点_pos_在目标窗口部件的坐标系。

该_actions_指示哪些类型的拖放操作可以被执行，并且拖动数据被存储为MIME编码的数据_data_。

鼠标按钮和键盘功能键在下拉时的状态由指定_buttons_和_modifiers_。

```
QDropEvent.__init__ (self, QDropEvent)
```

```
QDropEvent.acceptProposedAction (self)
```

设置下拉动作要建议的行动。

**See also** [setDropAction](qdropevent.html#setDropAction)（ ）[proposedAction](qdropevent.html#proposedAction)（）和[accept](qevent.html#accept)（ ） 。

```
Qt.DropAction QDropEvent.dropAction (self)
```

[](qt.html#DropAction-enum)

[返回到由目标上的数据执行的操作。这可能与所提供的不同的行动](qt.html#DropAction-enum)[proposedAction](qdropevent.html#proposedAction)（）如果你已经调用[setDropAction](qdropevent.html#setDropAction)（ ）显式地选择一个拖放操作。

**See also** [setDropAction](qdropevent.html#setDropAction)（ ） 。

```
QByteArray QDropEvent.encodedData (self, str)
```

[

```
str QDropEvent.format (self, int n = 0)
```

](qbytearray.html)

```
Qt.KeyboardModifiers QDropEvent.keyboardModifiers (self)
```

[

返回按下的修改键。

](index.htm)

```
QMimeData QDropEvent.mimeData (self)
```

[

返回滴加在部件上和其相关联的MIME类型的信息的数据。

](qmimedata.html)

```
Qt.MouseButtons QDropEvent.mouseButtons (self)
```

[

返回按下的鼠标键..

](index.htm)

```
QPoint QDropEvent.pos (self)
```

[

返回在下拉作出的位置。

](qpoint.html)

```
Qt.DropActions QDropEvent.possibleActions (self)
```

[

返回的可能下降的动作或组合。

](index.htm)

[**See also**](index.htm) [dropAction](qdropevent.html#dropAction)（ ） 。

```
Qt.DropAction QDropEvent.proposedAction (self)
```

[

返回建议的拖放操作。

](qt.html#DropAction-enum)

[**See also**](qt.html#DropAction-enum) [dropAction](qdropevent.html#dropAction)（ ） 。

```
bool QDropEvent.provides (self, str)
```

```
QDropEvent.setDropAction (self, Qt.DropAction action)
```

设置_action_可以通过在目标上的数据进行的。用它来复盖[proposed action](qdropevent.html#proposedAction)与所述一个[possible actions](qdropevent.html#possibleActions)。

如果设置了下拉动作，是不是可能的动作之一，拖放操作将默认的复制操作。

一旦你提供一个替代拖放操作，调用accept （ ）代替[acceptProposedAction](qdropevent.html#acceptProposedAction)（ ） 。

**See also** [dropAction](qdropevent.html#dropAction)（ ） 。

```
QWidget QDropEvent.source (self)
```

[](qwidget.html)

[如果拖动操作的来源是在这个应用程序中的小工具，这个函数返回源，否则返回0 。操作的源是所述第一参数的](qwidget.html)[QDrag](qdrag.html)使用对象实例化的阻力。

如果拖动到自己，当你的widget需要特殊的行为，这是很有用的。

**See also** [QDrag.QDrag](qdrag.html#QDrag)（ ） 。