# QMouseEvent Class Reference

## [[QtGui](index.htm) module]

该QMouseEvent类包含描述一个鼠标事件参数。[More...](#details)

继承[QInputEvent](qinputevent.html)。

### Methods

*   `__init__ (self, QEvent.Type type, QPoint pos, Qt.MouseButton button, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers)`
*   `__init__ (self, QEvent.Type type, QPoint pos, QPoint globalPos, Qt.MouseButton button, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers)`
*   `__init__ (self, QMouseEvent)`
*   `Qt.MouseButton button (self)`
*   `Qt.MouseButtons buttons (self)`
*   `QPoint globalPos (self)`
*   `int globalX (self)`
*   `int globalY (self)`
*   `bool hasExtendedInfo (self)`
*   `QPoint pos (self)`
*   `QPointF posF (self)`
*   `int x (self)`
*   `int y (self)`

* * *

## Detailed Description

该QMouseEvent类包含描述一个鼠标事件参数。

被按下时，一个鼠标按钮或窗口小部件内释放，或当鼠标光标移动的鼠标事件发生。

只有当鼠标按钮被按下时，除非鼠标跟踪已启用将发生的鼠标移动事件[QWidget.setMouseTracking](qwidget.html#mouseTracking-prop)（ ） 。

Qt的自动获取当鼠标按钮被一个widget里面按下鼠标，小工具将继续接收鼠标事件，直到最后释放鼠标按钮。

鼠标事件包含一个特殊的接受标志，指示接收者是否愿意事件。你应该调用[ignore](qevent.html#ignore)（ ）如果鼠标事件不是由您的Widget处理。鼠标事件被传播到父控件链，直到一个小部件接受它[accept](qevent.html#accept)（ ） ，或者一个事件过滤器会消耗它。

**Note:**如果鼠标事件被传播到[widget](qwidget.html)对于这[Qt.WA_NoMousePropagation](qt.html#WidgetAttribute-enum)已定，即鼠标事件将不会被进一步传播到父控件链。

键盘修饰键的状态，可以通过调用被发现[modifiers()](qinputevent.html#modifiers)功能，从继承[QInputEvent](qinputevent.html)。

该功能[pos](qmouseevent.html#pos)（ ）[x](qmouseevent.html#x)（）和[y](qmouseevent.html#y)相对的（ ）给光标所在位置到该接收鼠标事件的小部件。如果移动部件作为鼠标事件的结果，请使用返回的全球地位[globalPos](qmouseevent.html#globalPos)（ ）避免震动运动。

该[QWidget.setEnabled](qwidget.html#enabled-prop)（）函数可以被用来使能或禁止鼠标和键盘事件为一个部件。

重新实现[QWidget](qwidget.html)事件处理程序，[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ）[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ）[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（）和[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（）来接收自己的小部件的鼠标事件。

* * *

## Method Documentation

```
QMouseEvent.__init__ (self, QEvent.Type type, QPoint pos, Qt.MouseButton button, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers)
```

构造一个鼠标事件的对象。

该_type_参数必须是一个[QEvent.MouseButtonPress](qevent.html#Type-enum)，[QEvent.MouseButtonRelease](qevent.html#Type-enum)，[QEvent.MouseButtonDblClick](qevent.html#Type-enum)或[QEvent.MouseMove](qevent.html#Type-enum)。

该_position_是鼠标光标的位置相对于接收部件。该_button_导致事件被给定为从一个值[Qt.MouseButton](qt.html#MouseButton-enum)枚举。如果该事件_type_ is [MouseMove](qevent.html#Type-enum)，对于此事件的相应按钮[Qt.NoButton](qt.html#MouseButton-enum)。鼠标和键盘状态在事件发生时被指定_buttons_和_modifiers_。

该[globalPos](qmouseevent.html#globalPos)（）被初始化为[QCursor.pos](qcursor.html#pos)（），这可能不适合。使用其他构造函数来显式地指定的国际地位。

```
QMouseEvent.__init__ (self, QEvent.Type type, QPoint pos, QPoint globalPos, Qt.MouseButton button, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers)
```

构造一个鼠标事件的对象。

该_type_参数必须是[QEvent.MouseButtonPress](qevent.html#Type-enum)，[QEvent.MouseButtonRelease](qevent.html#Type-enum)，[QEvent.MouseButtonDblClick](qevent.html#Type-enum)或[QEvent.MouseMove](qevent.html#Type-enum)。

该_pos_是鼠标光标的位置相对于接收部件。在全局坐标光标的位置由指定的_globalPos_。该_button_导致事件被给定为从一个值[Qt.MouseButton](qt.html#MouseButton-enum)枚举。如果该事件_type_ is [MouseMove](qevent.html#Type-enum)，对于此事件的相应按钮[Qt.NoButton](qt.html#MouseButton-enum)。_buttons_是在事件发生时所有按键的状态，_modifiers_所有键盘功能键的状态。

```
QMouseEvent.__init__ (self, QMouseEvent)
```

```
Qt.MouseButton QMouseEvent.button (self)
```

[

返回引发事件的按钮。

](qt.html#MouseButton-enum)

[注意，返回的值总是](qt.html#MouseButton-enum)[Qt.NoButton](qt.html#MouseButton-enum)对于鼠标移动事件。

**See also** [buttons](qmouseevent.html#buttons)（）和[Qt.MouseButton](qt.html#MouseButton-enum)。

```
Qt.MouseButtons QMouseEvent.buttons (self)
```

[](index.htm)

[返回生成事件时，该按钮的状态。按钮状态是组合](index.htm)[Qt.LeftButton](qt.html#MouseButton-enum)，[Qt.RightButton](qt.html#MouseButton-enum)，[Qt.MidButton](qt.html#MouseButton-enum)使用OR运算符。对于鼠标移动事件，这是按下所有按钮。对于鼠标按下，然后双击事件，这包括引发事件的按钮。对于鼠标释放事件这不包括引发事件的按钮。

**See also** [button](qmouseevent.html#button)（）和[Qt.MouseButton](qt.html#MouseButton-enum)。

```
QPoint QMouseEvent.globalPos (self)
```

[](qpoint.html)

[返回鼠标光标的全球地位_at the time of the event_。这是很重要的异步窗口系统，例如X11 。每当你在响应鼠标事件四处移动你的部件， globalPos （ ）可以从当前指针位置不同，很多](qpoint.html)[QCursor.pos](qcursor.html#pos)（ ），并从QWidget.mapToGlobal （[pos](qmouseevent.html#pos)（））。

**See also** [globalX](qmouseevent.html#globalX)（）和[globalY](qmouseevent.html#globalY)（ ） 。

```
int QMouseEvent.globalX (self)
```

返回在事件发生时鼠标光标的全局x位置。

**See also** [globalY](qmouseevent.html#globalY)（）和[globalPos](qmouseevent.html#globalPos)（ ） 。

```
int QMouseEvent.globalY (self)
```

返回在事件发生时鼠标光标的全球y位置。

**See also** [globalX](qmouseevent.html#globalX)（）和[globalPos](qmouseevent.html#globalPos)（ ） 。

```
bool QMouseEvent.hasExtendedInfo (self)
```

```
QPoint QMouseEvent.pos (self)
```

[

返回鼠标光标的位置，相对于接收到的事件的插件。

](qpoint.html)

[如果移动部件作为鼠标事件的结果，请使用返回的全球地位](qpoint.html)[globalPos](qmouseevent.html#globalPos)（ ）避免震动运动。

**See also** [x](qmouseevent.html#x)（ ）[y](qmouseevent.html#y)（）和[globalPos](qmouseevent.html#globalPos)（ ） 。

```
QPointF QMouseEvent.posF (self)
```

[](qpointf.html)

[返回的鼠标光标的位置](qpointf.html)[QPointF](qpointf.html)，相对于接收到的事件的插件。

如果移动部件作为鼠标事件的结果，请使用返回的全球地位[globalPos](qmouseevent.html#globalPos)（ ）避免震动运动。

此功能被引入Qt的4.4 。

**See also** [x](qmouseevent.html#x)（ ）[y](qmouseevent.html#y)（ ）[pos](qmouseevent.html#pos)（）和[globalPos](qmouseevent.html#globalPos)（ ） 。

```
int QMouseEvent.x (self)
```

返回鼠标光标的x位置，相对于接收到的事件的插件。

**See also** [y](qmouseevent.html#y)（）和[pos](qmouseevent.html#pos)（ ） 。

```
int QMouseEvent.y (self)
```

返回鼠标光标的y位置，相对于接收事件的窗口小部件。

**See also** [x](qmouseevent.html#x)（）和[pos](qmouseevent.html#pos)（ ） 。