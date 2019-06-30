# QShortcutEvent Class Reference

## [[QtGui](index.htm) module]

该QShortcutEvent类提供了产生一个事件当用户按下一个键组合。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QKeySequence key, int id, bool ambiguous = False)`
*   `__init__ (self, QShortcutEvent)`
*   `bool isAmbiguous (self)`
*   `QKeySequence key (self)`
*   `int shortcutId (self)`

* * *

## Detailed Description

该QShortcutEvent类提供了产生一个事件当用户按下一个键组合。

通常你不需要直接使用这个类;[QShortcut](qshortcut.html)提供了更高级别的接口来处理快捷键。

* * *

## Method Documentation

```
QShortcutEvent.__init__ (self, QKeySequence key, int id, bool ambiguous = False)
```

构造一个快捷事件对于给定的_key_按，与相关联的[QShortcut](qshortcut.html)ID_id_。

_ambiguous_指定是否有一个以上的[QShortcut](qshortcut.html)对于相同的键序列。

```
QShortcutEvent.__init__ (self, QShortcutEvent)
```

```
bool QShortcutEvent.isAmbiguous (self)
```

返回True如果触发事件的按键顺序是模糊的。

**See also** [QShortcut.activatedAmbiguously](qshortcut.html#activatedAmbiguously)（ ） 。

```
QKeySequence QShortcutEvent.key (self)
```

[

返回触发事件的键序列。

```
int QShortcutEvent.shortcutId (self)
```

](qkeysequence.html)

[返回的标识](qkeysequence.html)[QShortcut](qshortcut.html)对象为其生成此事件。

**See also** [QShortcut.id](qshortcut.html#id)（ ） 。