# QWheelEvent Class Reference

## [[QtGui](index.htm) module]

该QWheelEvent类包含描述一个滚轮事件参数。[More...](#details)

继承[QInputEvent](qinputevent.html)。

### Methods

*   `__init__ (self, QPoint pos, int delta, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers, Qt.Orientation orientation = Qt.Vertical)`
*   `__init__ (self, QPoint pos, QPoint globalPos, int delta, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers, Qt.Orientation orientation = Qt.Vertical)`
*   `__init__ (self, QWheelEvent)`
*   `Qt.MouseButtons buttons (self)`
*   `int delta (self)`
*   `QPoint globalPos (self)`
*   `int globalX (self)`
*   `int globalY (self)`
*   `Qt.Orientation orientation (self)`
*   `QPoint pos (self)`
*   `int x (self)`
*   `int y (self)`

* * *

## Detailed Description

该QWheelEvent类包含描述一个滚轮事件参数。

轮事件被发送到插件的鼠标光标下的，但如果该插件不处理该事件它们被发送到聚焦部件。旋转距离由提供[delta](qwheelevent.html#delta)（ ） 。该功能[pos](qwheelevent.html#pos)（）和[globalPos](qwheelevent.html#globalPos)（ ）在事件发生时返回鼠标光标的位置。

车轮事件中包含一个特殊的接受标志，指示接收者是否愿意事件。你应该调用[ignore](qevent.html#ignore)（ ）如果你不处理滚轮事件，这保证了它会被发送到父控件。

该[QWidget.setEnabled](qwidget.html#enabled-prop)（）函数可以被用来使能或禁止鼠标和键盘事件为一个部件。

该事件处理程序[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ）接收滚轮事件。

* * *

## Method Documentation

```
QWheelEvent.__init__ (self, QPoint pos, int delta, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers, Qt.Orientation orientation = Qt.Vertical)
```

构造一个滚轮事件对象。

的位置，_pos_，是将鼠标光标的窗口小部件中的位置。该[globalPos](qwheelevent.html#globalPos)（）被初始化为[QCursor.pos](qcursor.html#pos)（），它是通常，但并不总是正确的。如果你需要明确地指定全局位置使用其他构造函数。

该_buttons_在描述事件时的鼠标按钮的状态，_delta_包含旋转的距离，_modifiers_保持键盘修饰符标志的事件的时间，并_orient_持有车轮的方向。

**See also** [pos](qwheelevent.html#pos)（ ）[delta](qwheelevent.html#delta)（）和[state](index.htm#state)（ ） 。

```
QWheelEvent.__init__ (self, QPoint pos, QPoint globalPos, int delta, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers, Qt.Orientation orientation = Qt.Vertical)
```

构造一个滚轮事件对象。

该_pos_提供的窗口小部件中的鼠标光标的位置。在全局坐标的位置由指定的_globalPos_。_delta_包含旋转的距离，_modifiers_保持键盘修饰符标志的事件的时间，并_orient_持有车轮的方向。

**See also** [pos](qwheelevent.html#pos)（ ）[globalPos](qwheelevent.html#globalPos)（ ）[delta](qwheelevent.html#delta)（）和[state](index.htm#state)（ ） 。

```
QWheelEvent.__init__ (self, QWheelEvent)
```

```
Qt.MouseButtons QWheelEvent.buttons (self)
```

[

返回鼠标的状态时，事件发生。

```
int QWheelEvent.delta (self)
```

返回该轮转动时的距离，在一定程度的八分。正值表示滚轮是向前旋转远离用户，负值表示滚轮被向后旋转朝向用户。

大多数类型的鼠标，步长为15度工作，在这种情况下，增量值是120的倍数，即， 120个单位* 1/ 8 = 15度。

然而，一些小鼠具有较高分辨率的车轮和发送δ值是小于120单位（小于15度）。为了支持这种可能性，您可以累计从事件添加增量值，直到120的值为止，然后滚动窗口小部件，也可以部分地滚动窗口小部件响应每个滚轮事件。

例如：

](index.htm)

```
 void MyWidget.wheelEvent(QWheelEvent *event)
 {
     int numDegrees = event->delta() / 8;
     int numSteps = numDegrees / 15;

     if (event->orientation() == [Qt](qt.html).Horizontal) {
         scrollHorizontally(numSteps);
     } else {
         scrollVertically(numSteps);
     }
     event->accept();
 }

```

```
QPoint QWheelEvent.globalPos (self)
```

[](qpoint.html)

[返回鼠标指针的全球地位_at the time of the event_。这是很重要的异步窗口系统，如X11 ，每当你在响应鼠标事件， globalPos左右移动你的widget （ ）可以从返回当前光标位置不同，很多](qpoint.html)[QCursor.pos](qcursor.html#pos)（ ） 。

**See also** [globalX](qwheelevent.html#globalX)（）和[globalY](qwheelevent.html#globalY)（ ） 。

```
int QWheelEvent.globalX (self)
```

返回在事件发生时鼠标光标的全局x位置。

**See also** [globalY](qwheelevent.html#globalY)（）和[globalPos](qwheelevent.html#globalPos)（ ） 。

```
int QWheelEvent.globalY (self)
```

返回在事件发生时鼠标光标的全球y位置。

**See also** [globalX](qwheelevent.html#globalX)（）和[globalPos](qwheelevent.html#globalPos)（ ） 。

```
Qt.Orientation QWheelEvent.orientation (self)
```

[

返回车轮的方向。

](qt.html#Orientation-enum)

```
QPoint QWheelEvent.pos (self)
```

[

返回到该接收到的事件的插件光标相对于鼠标的位置。

](qpoint.html)

[如果您在响应鼠标事件四处移动你的小部件，使用](qpoint.html)[globalPos](qwheelevent.html#globalPos)（代替此功能） 。

**See also** [x](qwheelevent.html#x)（ ）[y](qwheelevent.html#y)（）和[globalPos](qwheelevent.html#globalPos)（ ） 。

```
int QWheelEvent.x (self)
```

返回鼠标光标的x位置，相对于接收到的事件的插件。

**See also** [y](qwheelevent.html#y)（）和[pos](qwheelevent.html#pos)（ ） 。

```
int QWheelEvent.y (self)
```

返回鼠标光标的y位置，相对于接收事件的窗口小部件。

**See also** [x](qwheelevent.html#x)（）和[pos](qwheelevent.html#pos)（ ） 。