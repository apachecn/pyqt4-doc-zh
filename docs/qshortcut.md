# QShortcut Class Reference

## [[QtGui](index.htm) module]

该QShortcut类用于创建键盘快捷键。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QWidget parent)`
*   `__init__ (self, QKeySequence key, QWidget parent, SLOT() member = 0, SLOT() ambiguousMember = 0, Qt.ShortcutContext context = Qt.WindowShortcut)`
*   `bool autoRepeat (self)`
*   `Qt.ShortcutContext context (self)`
*   `bool event (self, QEvent e)`
*   `int id (self)`
*   `bool isEnabled (self)`
*   `QKeySequence key (self)`
*   `QWidget parentWidget (self)`
*   `setAutoRepeat (self, bool on)`
*   `setContext (self, Qt.ShortcutContext context)`
*   `setEnabled (self, bool enable)`
*   `setKey (self, QKeySequence key)`
*   `setWhatsThis (self, QString text)`
*   `QString whatsThis (self)`

### Qt Signals

*   `void activated ()`
*   `void activatedAmbiguously ()`

* * *

## Detailed Description

该QShortcut类用于创建键盘快捷键。

该QShortcut类提供连接的键盘快捷键Qt的一种方式[signals and slots](index.htm#signals-and-slots)机制，使执行的快捷方式时，对象可以获知。快捷方式可以设置为包含必要说明的键盘快捷键的所有按键，包括修改键，如的状态**Shift**，**Ctrl**和**Alt**。

对某些小部件，使用' ＆ '在字符前面将自动为角色创建一个助记符（快捷方式） ，如： “ E＆ XIT ”，将创建快捷方式**Alt+X**（使用“\u0026\u0026”来显示实际的符号） 。窗口小部件可能会消耗并执行一个给定的快捷操作。在X11 ＆符号将不会显示和字符将被下划线。在Windows中，快捷方式通常不会直到用户按下显示**Alt**键，但是这是一种设置，用户可以改变。在Mac上，快捷键默认情况下禁用。通话[qt_set_sequence_auto_mnemonic](index.htm#qt_set_sequence_auto_mnemonic)（）来启用它们。但是，由于记忆的快捷方式不Aqua的指导方针适应， Qt会不显示快捷方式的字符加下划线。

对于使用的菜单的应用程序，它可以是更方便地使用在所提供的便利的功能[QMenu](qmenu.html)类，因为它们是创建指定键盘快捷键的菜单项。可替换地，快捷可以与其它类型的动作的相关[QAction](qaction.html)类。

创建用于特定插件的快捷方式的最简单方法是构造一个密钥序列的捷径。例如：

```
 shortcut = new QShortcut([QKeySequence](qkeysequence.html)(tr("Ctrl+O", "File|Open")),
                          parent);

```

当用户键入[key sequence](qkeysequence.html)对于给定的快捷方式，快捷方式的[activated](qshortcut.html#activated)（）信号被发射。 （在歧义的情况下，该[activatedAmbiguously](qshortcut.html#activatedAmbiguously)（ ）信号被发射。 ）的快捷方式“听了”通过Qt的事件循环时快捷的父控件接收事件。

一个快捷的按键顺序可以被设置[setKey](qshortcut.html#key-prop)（）和检索与[key](qshortcut.html#key-prop)（ ） 。快捷方式可以启用或禁用[setEnabled](qshortcut.html#enabled-prop)（ ） ，并且可以有“这是什么？ ”帮助文本与集[setWhatsThis](qshortcut.html#whatsThis-prop)（ ） 。

* * *

## Method Documentation

```
QShortcut.__init__ (self, QWidget parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QShortcut](qshortcut.html)为对象_parent_小工具。由于没有指定快捷键序列，该快捷方式将不会发出任何信号。

**See also** [setKey](qshortcut.html#key-prop)（ ） 。

```
QShortcut.__init__ (self, QKeySequence key, QWidget parent, SLOT() member = 0, SLOT() ambiguousMember = 0, Qt.ShortcutContext context = Qt.WindowShortcut)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QShortcut](qshortcut.html)为对象_parent_小工具。快捷操作其父，监听[QShortcutEvent](qshortcutevent.html)器匹配的_key_序列。根据事件的模糊性，快捷方式将调用_member_功能，或_ambiguousMember_功能，如果按键在快捷方式的_context_。

```
bool QShortcut.autoRepeat (self)
```

```
Qt.ShortcutContext QShortcut.context (self)
```

[

```
bool QShortcut.event (self, QEvent e)
```

```
int QShortcut.id (self)
```

返回快捷方式的ID 。

](qt.html#ShortcutContext-enum)

[**See also**](qt.html#ShortcutContext-enum) [QShortcutEvent.shortcutId](qshortcutevent.html#shortcutId)（ ） 。

```
bool QShortcut.isEnabled (self)
```

```
QKeySequence QShortcut.key (self)
```

[](qkeysequence.html)

```
QWidget QShortcut.parentWidget (self)
```

[

返回快捷方式的父控件。

```
QShortcut.setAutoRepeat (self, bool on)
```

```
QShortcut.setContext (self, Qt.ShortcutContext context)
```

```
QShortcut.setEnabled (self, bool enable)
```

```
QShortcut.setKey (self, QKeySequence key)
```

```
QShortcut.setWhatsThis (self, QString text)
```

```
QString QShortcut.whatsThis (self)
```

* * *

## Qt Signal Documentation

```
void activated ()
```

这是该信号的默认超载。

这个信号被发射当用户键入快捷方式的按键顺序。

](qwidget.html)

[**See also**](qwidget.html) [activatedAmbiguously](qshortcut.html#activatedAmbiguously)（ ） 。

```
void activatedAmbiguously ()
```

这是该信号的默认超载。

当一个键序列被键盘输入的字符，它是说，只要它的多个快捷方式启动匹配不明确。

当一个快捷方式的键序列完成后， activatedAmbiguously （ ）是在密钥序列仍然是模糊的（也就是说，它是一个或多个其它的快捷方式启动）发出。该[activated](qshortcut.html#activated)（）信号不被在此情况下发射的光。

**See also** [activated](qshortcut.html#activated)（ ） 。