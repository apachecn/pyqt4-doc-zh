# QKeyEvent Class Reference

## [[QtGui](index.htm) module]

该QKeyEvent类描述了一个关键事件。[More...](#details)

继承[QInputEvent](qinputevent.html)。

### Methods

*   `__init__ (self, QEvent.Type type, int key, Qt.KeyboardModifiers modifiers, QString text = QString(), bool autorep = False, int count = 1)`
*   `__init__ (self, QKeyEvent)`
*   `int count (self)`
*   `bool isAutoRepeat (self)`
*   `int key (self)`
*   `bool matches (self, QKeySequence.StandardKey key)`
*   `Qt.KeyboardModifiers modifiers (self)`
*   `int nativeModifiers (self)`
*   `int nativeScanCode (self)`
*   `int nativeVirtualKey (self)`
*   `QString text (self)`

### Special Methods

*   `bool __eq__ (self, QKeySequence.StandardKey key)`
*   `__len__ (self)`
*   `bool __ne__ (self, QKeySequence.StandardKey key)`

* * *

## Detailed Description

该QKeyEvent类描述了一个关键事件。

当按键按下或释放键事件发送到窗口小部件与键盘输入焦点。

一个关键的事件包含一个特殊的接受标志，指示接收者是否将处理按键事件。你应该调用[ignore](qevent.html#ignore)（ ）如果键按下或释放事件不是由您的Widget处理。一个关键的事件被传播到父控件链，直到一个小部件接受它[accept](qevent.html#accept)（ ）或事件过滤器会消耗它。多媒体键的按键事件在默认情况下忽略。你应该调用[accept](qevent.html#accept)（）如果你的widget处理这些事件。

该QWidget.setEnable （）函数可以被用来使能或禁止鼠标和键盘事件为一个部件。

该事件处理程序[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ）[QWidget.keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ）[QGraphicsItem.keyPressEvent](qgraphicsitem.html#keyPressEvent)（）和[QGraphicsItem.keyReleaseEvent](qgraphicsitem.html#keyReleaseEvent)（ ）接收按键事件。

* * *

## Method Documentation

```
QKeyEvent.__init__ (self, QEvent.Type type, int key, Qt.KeyboardModifiers modifiers, QString text = QString(), bool autorep = False, int count = 1)
```

构造一个关键的事件对象。

该_type_参数必须是[QEvent.KeyPress](qevent.html#Type-enum)，[QEvent.KeyRelease](qevent.html#Type-enum)或[QEvent.ShortcutOverride](qevent.html#Type-enum)。

诠释_key_对于代码[Qt.Key](qt.html#Key-enum)该事件循环应该倾听。如果_key_为0时，该事件是不是一个已知的密钥的结果，例如，它可能是一个写作顺序或键盘宏的结果。该_modifiers_保持键盘功能键，并在给定_text_是，密钥生成的Unicode文本。如果_autorep_是真的，[isAutoRepeat](qkeyevent.html#isAutoRepeat)（ ）将是真实的。_count_是参与事件的键的数目。

```
QKeyEvent.__init__ (self, QKeyEvent)
```

```
int QKeyEvent.count (self)
```

返回与此事件相关的键的数目。如果[text](qkeyevent.html#text)（ ）不是空的，这简直是字符串的长度。

**See also** [Qt.WA_KeyCompression](qt.html#WidgetAttribute-enum)。

```
bool QKeyEvent.isAutoRepeat (self)
```

返回True如果此事件来自一个自动重复键，如果它来自一个初始的按键返回False。

注意，如果事件是一个多键压缩事件的部分原因是自动重复，这个函数可以返回True或False不定。

```
int QKeyEvent.key (self)
```

返回按下或释放的键的代码。

See [Qt.Key](qt.html#Key-enum)供的键盘代码的列表。这些代码是独立于底层窗口系统。请注意，这个函数不资本和非大写字母区分，使用[text](qkeyevent.html#text)（ ）函数（返回按键产生的Unicode文本）用于这一目的。

0或值[Qt.Key_unknown](qt.html#Key-enum)表示该事件是不是一个已知的密钥的结果，例如，它可能是一个写作顺序，键盘宏，或者由于关键事件的压缩的结果。

**See also** [Qt.WA_KeyCompression](qt.html#WidgetAttribute-enum)。

```
bool QKeyEvent.matches (self, QKeySequence.StandardKey key)
```

如果关键事件的给定标准匹配，则返回True_key_否则返回False 。

这个函数中引入了Qt 4.2中。

```
Qt.KeyboardModifiers QKeyEvent.modifiers (self)
```

[

返回立即存在的事件发生后，键盘修饰符标志。

**Warning:**此功能不能总是可信的。用户可以通过同时按下混淆**Shift**键同时释放其中的一个，例如。

](index.htm)

[**See also**](index.htm) [QApplication.keyboardModifiers](qapplication.html#keyboardModifiers)（ ） 。

```
int QKeyEvent.nativeModifiers (self)
```

返回一个关键的事件的本地修饰符。如果关键事件中不包含此数据，则返回0 。

注意：本机调节剂可以是0 ，即使键事件包含的扩展信息。

这个函数中引入了Qt 4.2中。

```
int QKeyEvent.nativeScanCode (self)
```

返回键事件的本机扫描码。如果关键事件中不包含此数据，则返回0 。

注：本机扫描码可能为0 ，即使关键事件包含的扩展信息。

注意：在Mac OS / X ，这个功能是没有用的，因为没有办法从碳或可可得到扫描码。该函数总是返回1（或0的情况下上面所解释的） 。

这个函数中引入了Qt 4.2中。

```
int QKeyEvent.nativeVirtualKey (self)
```

返回本机的虚拟键或按键事件的键对称。如果关键事件中不包含此数据，则返回0 。

注意：本机虚拟键可以是0 ，即使键事件包含的扩展信息。

这个函数中引入了Qt 4.2中。

```
QString QKeyEvent.text (self)
```

返回Unicode文本，这个密钥生成。返回的文本可以在修饰键，如Shift键，控制，Alt和梅塔，被按下或释放的情况下，一个空字符串。在这种情况下[key](qkeyevent.html#key)（ ）将包含一个有效的值。

**See also** [Qt.WA_KeyCompression](qt.html#WidgetAttribute-enum)。

```
bool QKeyEvent.__eq__ (self, QKeySequence.StandardKey key)
```

```
 QKeyEvent.__len__ (self)
```

```
bool QKeyEvent.__ne__ (self, QKeySequence.StandardKey key)
```