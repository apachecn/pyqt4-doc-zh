# QTest Class Reference

## [[QtTest](index.htm) module]

该QTEST命名空间包含所有相关的功能和声明[QTestLib](index.htm#qtestlib)工具。[More...](#details)

### Types

*   `enum KeyAction { Press, Release, Click }`
*   `enum MouseAction { MousePress, MouseRelease, MouseClick, MouseDClick, MouseMove }`

### Static Methods

*   `keyClick (QWidget widget, Qt.Key key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `keyClick (QWidget widget, str key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `keyClicks (QWidget widget, QString sequence, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `keyEvent (KeyAction action, QWidget widget, Qt.Key key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `keyEvent (KeyAction action, QWidget widget, str ascii, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `keyPress (QWidget widget, Qt.Key key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `keyPress (QWidget widget, str key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `keyRelease (QWidget widget, Qt.Key key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `keyRelease (QWidget widget, str key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)`
*   `mouseClick (QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers modifier = 0, QPoint pos = QPoint(), int delay = -1)`
*   `mouseDClick (QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers modifier = 0, QPoint pos = QPoint(), int delay = -1)`
*   `mouseEvent (MouseAction action, QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers stateKey, QPoint pos, int delay = -1)`
*   `mouseMove (QWidget widget, QPoint pos = QPoint(), int delay = -1)`
*   `mousePress (QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers modifier = 0, QPoint pos = QPoint(), int delay = -1)`
*   `mouseRelease (QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers modifier = 0, QPoint pos = QPoint(), int delay = -1)`
*   `qSleep (int ms)`
*   `qWait (int ms)`
*   `bool qWaitForWindowShown (QWidget window)`

* * *

## Detailed Description

该QTEST命名空间包含所有相关的功能和声明[QTestLib](index.htm#qtestlib)工具。

请参阅[QTestLib Manual](index.htm)文档以获取有关如何编写单元测试的信息。

* * *

## Type Documentation

```
QTest.KeyAction
```

这个枚举变量描述了密钥处理可能的操作。

| Constant | Value | Description |
| --- | --- | --- |
| `QTest.Press` | `0` | 该键被按下。 |
| `QTest.Release` | `1` | 键被释放。 |
| `QTest.Click` | `2` | 关键是点击（按下并释放） 。 |

```
QTest.MouseAction
```

这个枚举变量描述了鼠标处理可能的操作。

| Constant | Value | Description |
| --- | --- | --- |
| `QTest.MousePress` | `0` | 鼠标按钮被按下。 |
| `QTest.MouseRelease` | `1` | 释放鼠标按钮。 |
| `QTest.MouseClick` | `2` | 单击鼠标按钮（按下并释放） 。 |
| `QTest.MouseDClick` | `3` | 鼠标按钮双击时（按下并释放两次） 。 |
| `QTest.MouseMove` | `4` | 将鼠标指针移动。 |

* * *

## Method Documentation

```
QTest.keyClick (QWidget widget, Qt.Key key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

模拟点击的_key_具有可选_modifier_上一个_widget_。如果_delay_大于0 ，则测试将等待_delay_毫秒。

示例：

```
 [QTest](qtest.html).keyClick(myWidget, [Qt](qt.html).Key_Escape);

 [QTest](qtest.html).keyClick(myWidget, [Qt](qt.html).Key_Escape, [Qt](qt.html).ShiftModifier, 200);

```

上面第一个例子模拟点击`escape`关键`myWidget`没有任何键盘功能键和无延迟。第二个例子模拟点击`shift-escape`上`myWidget`用试验的以下200毫秒的延迟。

**See also** [QTest.keyClicks](qtest.html#keyClicks)（ ） 。

```
QTest.keyClick (QWidget widget, str key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

这是一个重载函数。

模拟点击的_key_具有可选_modifier_上一个_widget_。如果_delay_大于0 ，则测试将等待_delay_毫秒。

例如：

```
 [QTest](qtest.html).keyClick(myWidget, 'a');

```

上面的例子中模拟点击`a`上`myWidget`没有任何键盘功能键和没有测试的延迟。

**See also** [QTest.keyClicks](qtest.html#keyClicks)（ ） 。

```
QTest.keyClicks (QWidget widget, QString sequence, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

模拟点击一个_sequence_上一个键_widget_。任选地，一个键盘_modifier_可以被指定，以及一个_delay_（以毫秒为单位）每个键击之前的测试。

例如：

```
 [QTest](qtest.html).keyClicks(myWidget, "hello world");

```

上面的例子中模拟点击代表的“ Hello World”的键序列`myWidget`没有任何键盘功能键和没有测试的延迟。

**See also** [QTest.keyClick](qtest.html#keyClick)（ ） 。

```
QTest.keyEvent (KeyAction action, QWidget widget, Qt.Key key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

发送一个Qt的关键事件_widget_用给定的_key_和一个相关的_action_。任选地，一个键盘_modifier_可以被指定，以及一个_delay_（以毫秒为单位）发送事件之前的测试。

```
QTest.keyEvent (KeyAction action, QWidget widget, str ascii, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

这是一个重载函数。

发送一个Qt的关键事件_widget_用给定的键_ascii_和一个相关的_action_。任选地，一个键盘_modifier_可以被指定，以及一个_delay_（以毫秒为单位）发送事件之前的测试。

```
QTest.keyPress (QWidget widget, Qt.Key key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

模拟按下一个_key_具有可选_modifier_上一个_widget_。如果_delay_大于0 ，则测试将等待_delay_毫秒。

**Note:**在某些时候，你应该使用松开按键[keyRelease](qtest.html#keyRelease)（ ） 。

**See also** [QTest.keyRelease](qtest.html#keyRelease)（）和[QTest.keyClick](qtest.html#keyClick)（ ） 。

```
QTest.keyPress (QWidget widget, str key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

这是一个重载函数。

模拟按下一个_key_具有可选_modifier_上一个_widget_。如果_delay_大于0 ，则测试将等待_delay_毫秒。

**Note:**在某些时候，你应该使用松开按键[keyRelease](qtest.html#keyRelease)（ ） 。

**See also** [QTest.keyRelease](qtest.html#keyRelease)（）和[QTest.keyClick](qtest.html#keyClick)（ ） 。

```
QTest.keyRelease (QWidget widget, Qt.Key key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

模拟释放_key_具有可选_modifier_上一个_widget_。如果_delay_大于0 ，则测试将等待_delay_毫秒。

**See also** [QTest.keyPress](qtest.html#keyPress)（）和[QTest.keyClick](qtest.html#keyClick)（ ） 。

```
QTest.keyRelease (QWidget widget, str key, Qt.KeyboardModifiers modifier = Qt.NoModifier, int delay = -1)
```

这是一个重载函数。

模拟释放_key_具有可选_modifier_上一个_widget_。如果_delay_大于0 ，则测试将等待_delay_毫秒。

**See also** [QTest.keyClick](qtest.html#keyClick)（ ） 。

```
QTest.mouseClick (QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers modifier = 0, QPoint pos = QPoint(), int delay = -1)
```

模拟点击鼠标_button_具有可选_modifier_上一个_widget_。点击的位置被定义为_pos_，默认位置是widget的中心。如果_delay_被指定，测试将等待指定的毫秒金额前按下并释放按钮之前。

**See also** [QTest.mousePress](qtest.html#mousePress)（）和[QTest.mouseRelease](qtest.html#mouseRelease)（ ） 。

```
QTest.mouseDClick (QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers modifier = 0, QPoint pos = QPoint(), int delay = -1)
```

模拟双击鼠标_button_具有可选_modifier_上一个_widget_。点击的位置被定义为_pos_，默认位置是widget的中心。如果_delay_被指定，测试将等待指定的毫秒数量每次按下和释放之前。

**See also** [QTest.mouseClick](qtest.html#mouseClick)（ ） 。

```
QTest.mouseEvent (MouseAction action, QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers stateKey, QPoint pos, int delay = -1)
```

```
QTest.mouseMove (QWidget widget, QPoint pos = QPoint(), int delay = -1)
```

将鼠标指针移动到_widget_。如果_pos_没有指定，将鼠标指针移动到窗口小部件的中心。如果_delay_（以毫秒为单位）给出，测试将移动鼠标指针前等待。

```
QTest.mousePress (QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers modifier = 0, QPoint pos = QPoint(), int delay = -1)
```

模拟按下鼠标_button_具有可选_modifier_上一个_widget_。该位置被定义为_pos_，默认位置是widget的中心。如果_delay_被指定，测试将等待指定的毫秒金额按前。

**See also** [QTest.mouseRelease](qtest.html#mouseRelease)（）和[QTest.mouseClick](qtest.html#mouseClick)（ ） 。

```
QTest.mouseRelease (QWidget widget, Qt.MouseButton button, Qt.KeyboardModifiers modifier = 0, QPoint pos = QPoint(), int delay = -1)
```

模拟松开鼠标_button_具有可选_modifier_上一个_widget_。释放的位置被定义为_pos_，默认位置是widget的中心。如果_delay_被指定，测试将等待指定的毫秒量释放按钮之前。

**See also** [QTest.mousePress](qtest.html#mousePress)（）和[QTest.mouseClick](qtest.html#mouseClick)（ ） 。

```
QTest.qSleep (int ms)
```

休眠_ms_毫秒，阻止执行的测试。 qSleep （ ）不会做任何事件处理，并留下您的测试反应迟钝。网络通信可能会超时而睡。使用[qWait](qtest.html#qWait)（ ）做非阻塞睡觉。

_ms_必须大于0 。

**Note:**该qSleep （ ）函数调用任一`nanosleep()`在UNIX或`Sleep()`上的窗口，因此时间在qSleep使用了（）的精度依赖于操作系统。

例如：

```
 [QTest](qtest.html).qSleep(250);

```

**See also** [qWait](qtest.html#qWait)（ ） 。

```
QTest.qWait (int ms)
```

等待_ms_毫秒。在等待时，事件将被处理，你的测试将保持响应用户界面事件或网络通信。

例如：

```
 int i = 0;
 while (myNetworkServerNotResponding() && i++ < 50)
     [QTest](qtest.html).qWait(250);

```

上面的代码将等待，直到网络服务器响应最多约12.5秒。

**See also** [QTest.qSleep](qtest.html#qSleep)（ ） 。

```
bool QTest.qWaitForWindowShown (QWidget window)
```

等待，直到_window_显示在屏幕上。这主要是异步系统，如X11 ，其中一个窗口将被映射被要求出示自己在屏幕上后，屏幕一段时间非常有用。返回True。

例如：

```
 [QWidget](qwidget.html) widget;
 widget.show();
 [QTest](qtest.html).qWaitForWindowShown(&widget);

```

此功能被引入Qt的4.6 。