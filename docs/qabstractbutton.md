# QAbstractButton Class Reference

## [[QtGui](index.htm) module]

该QAbstractButton类是按钮控件的抽象基类，提供了常见的按键功能。[More...](#details)

继承[QWidget](qwidget.html)。

通过继承[QCheckBox](qcheckbox.html)，[QPushButton](qpushbutton.html)，[QRadioButton](qradiobutton.html)和[QToolButton](qtoolbutton.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `animateClick (self, int msecs = 100)`
*   `bool autoExclusive (self)`
*   `bool autoRepeat (self)`
*   `int autoRepeatDelay (self)`
*   `int autoRepeatInterval (self)`
*   `changeEvent (self, QEvent e)`
*   `checkStateSet (self)`
*   `click (self)`
*   `bool event (self, QEvent e)`
*   `focusInEvent (self, QFocusEvent e)`
*   `focusOutEvent (self, QFocusEvent e)`
*   `QButtonGroup group (self)`
*   `bool hitButton (self, QPoint pos)`
*   `QIcon icon (self)`
*   `QSize iconSize (self)`
*   `bool isCheckable (self)`
*   `bool isChecked (self)`
*   `bool isDown (self)`
*   `keyPressEvent (self, QKeyEvent e)`
*   `keyReleaseEvent (self, QKeyEvent e)`
*   `mouseMoveEvent (self, QMouseEvent e)`
*   `mousePressEvent (self, QMouseEvent e)`
*   `mouseReleaseEvent (self, QMouseEvent e)`
*   `nextCheckState (self)`
*   `paintEvent (self, QPaintEvent e)`
*   `setAutoExclusive (self, bool)`
*   `setAutoRepeat (self, bool)`
*   `setAutoRepeatDelay (self, int)`
*   `setAutoRepeatInterval (self, int)`
*   `setCheckable (self, bool)`
*   `setChecked (self, bool)`
*   `setDown (self, bool)`
*   `setIcon (self, QIcon icon)`
*   `setIconSize (self, QSize size)`
*   `setShortcut (self, QKeySequence key)`
*   `setText (self, QString text)`
*   `QKeySequence shortcut (self)`
*   `QString text (self)`
*   `timerEvent (self, QTimerEvent e)`
*   `toggle (self)`

### Qt Signals

*   `void clicked (bool = 0)`
*   `void pressed ()`
*   `void released ()`
*   `void toggled (bool)`

* * *

## Detailed Description

该QAbstractButton类是按钮控件的抽象基类，提供了常见的按键功能。

这个类实现了一个_abstract_按钮。这个类处理用户动作的子类，并指定该按钮的绘制方式。

QAbstractButton提供了两个按键和可复（切换）按钮的支持。辨认的按钮在实施[QRadioButton](qradiobutton.html)和[QCheckBox](qcheckbox.html)类。按钮是在实施[QPushButton](qpushbutton.html)和[QToolButton](qtoolbutton.html)类，这些还提供切换行为，如果需要的话。

任何按钮可以显示一个包含标籤文本和图标。[setText](qabstractbutton.html#text-prop)（ ）设置文本;[setIcon](qabstractbutton.html#icon-prop)（）设置的图标。如果被禁用的按钮，其标籤更改为给按钮“已禁用”的外观。

如果按钮是一个按钮的文本包含一个连字号（ '＆' ）的字符串， QAbstractButton会自动创建一个快捷键。例如：

```
 [QPushButton](qpushbutton.html) *button = new [QPushButton](qpushbutton.html)(tr("Ro&ck && Roll"), this);

```

该**Alt+C**快捷方式被分配给该按钮时，即，当用户按下**Alt+C**该按钮将调用[animateClick](qabstractbutton.html#animateClick)（ ） 。请参阅[QShortcut](qshortcut.html#mnemonic)有关详细信息的文档（显示的实际符号，使用“\u0026\u0026” ） 。

您还可以使用设置自定义快捷键[setShortcut](qabstractbutton.html#shortcut-prop)（）函数。这主要是针对那些没有任何文字按钮非常有用，因为它们没有自动的快捷方式。

```
 button->setIcon([QIcon](qicon.html)(":/../img/print.png"));
 button->setShortcut(tr("Alt+F7"));

```

所有Qt提供的按钮（[QPushButton](qpushbutton.html)，[QToolButton](qtoolbutton.html)，[QCheckBox](qcheckbox.html)和[QRadioButton](qradiobutton.html)）可以同时显示[text](qabstractbutton.html#text-prop)和[icons](qabstractbutton.html#icon-prop)。

A键可在对话框中的默认按钮是由提供[QPushButton.setDefault](qpushbutton.html#default-prop)（）和[QPushButton.setAutoDefault](qpushbutton.html#autoDefault-prop)（ ） 。

QAbstractButton提供了最常用的按钮的状态：

*   [isDown](qabstractbutton.html#down-prop)() indicates whether the button is _pressed_ down.
*   [isChecked](qabstractbutton.html#checked-prop)() indicates whether the button is _checked_. Only checkable buttons can be checked and unchecked (see below).
*   [isEnabled](qwidget.html#enabled-prop)() indicates whether the button can be pressed by the user. **Note:** As opposed to other widgets, buttons derived from QAbstractButton accepts mouse and context menu events when disabled.
*   [setAutoRepeat](qabstractbutton.html#autoRepeat-prop)() sets whether the button will auto-repeat if the user holds it down. [autoRepeatDelay](qabstractbutton.html#autoRepeatDelay-prop) and [autoRepeatInterval](qabstractbutton.html#autoRepeatInterval-prop) define how auto-repetition is done.
*   [setCheckable](qabstractbutton.html#checkable-prop)() sets whether the button is a toggle button or not.

之间的差[isDown](qabstractbutton.html#down-prop)（）和[isChecked](qabstractbutton.html#checked-prop)（）如下。当用户点击切换按钮来检查它，按钮是第一_pressed_然后释放到_checked_状态。当用户再次单击它（取消选中它） ，按钮首先移动到_pressed_状态，然后到_unchecked_状态（[isChecked](qabstractbutton.html#checked-prop)（）和[isDown](qabstractbutton.html#down-prop)（ ）都是假的） 。

QAbstractButton提供四个信号：

1.  [pressed](qabstractbutton.html#pressed)（ ）当按下鼠标左键，当鼠标指针在按钮内发出。
2.  [released](qabstractbutton.html#released)（ ）当释放鼠标左键发射。
3.  [clicked](qabstractbutton.html#clicked)（）时，当第一次按下，然后释放按钮，当快捷键被键入时，或者当发射[click](qabstractbutton.html#click)（）或[animateClick](qabstractbutton.html#animateClick)（）被调用。
4.  [toggled](qabstractbutton.html#toggled)（ ）被发射时的切换按钮的状态发生改变。

子类QAbstractButton ，你必须重新实现至少[paintEvent](qabstractbutton.html#paintEvent)（ ）来绘制按钮的轮廓和它的文本或像素图。通常建议重新实现[sizeHint](qwidget.html#sizeHint-prop)（ ）为好，有时[hitButton](qabstractbutton.html#hitButton)（ ） （判断按下一个按钮是否在按钮内） 。对于有两个以上的国家（如三态按钮）按钮，您也必须重新实现[checkStateSet](qabstractbutton.html#checkStateSet)（）和[nextCheckState](qabstractbutton.html#nextCheckState)（ ） 。

* * *

## Method Documentation

```
QAbstractButton.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个抽象的按钮与_parent_。

```
QAbstractButton.animateClick (self, int msecs = 100)
```

这种方法也是一个Qt槽与C + +的签名`void animateClick(int = 100)`。

执行一个动画点击：按钮被按下马上，并释放_msec_毫秒后（默认为100毫秒） 。

再次调用此功能的按钮被释放之前将复位释放定时器。

与点击相关的所有信号都发出适当。

这个函数不执行任何操作，如果该按钮是[disabled.](qwidget.html#enabled-prop)

**See also** [click](qabstractbutton.html#click)（ ） 。

```
bool QAbstractButton.autoExclusive (self)
```

```
bool QAbstractButton.autoRepeat (self)
```

```
int QAbstractButton.autoRepeatDelay (self)
```

```
int QAbstractButton.autoRepeatInterval (self)
```

```
QAbstractButton.changeEvent (self, QEvent e)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QAbstractButton.checkStateSet (self)
```

这种虚拟处理器被调用时[setChecked](qabstractbutton.html#checked-prop)（ ）被调用，除非它是从内部调用[nextCheckState](qabstractbutton.html#nextCheckState)（ ） 。它允许子类重新设置他们的中间按钮状态。

**See also** [nextCheckState](qabstractbutton.html#nextCheckState)（ ） 。

```
QAbstractButton.click (self)
```

这种方法也是一个Qt槽与C + +的签名`void click()`。

进行点击。

所有与点击相关的一般信号被发射（如适用） 。如果按钮是可复，按钮的状态翻转。

这个函数不执行任何操作，如果该按钮是[disabled.](qwidget.html#enabled-prop)

**See also** [animateClick](qabstractbutton.html#animateClick)（ ） 。

```
bool QAbstractButton.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QAbstractButton.focusInEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
QAbstractButton.focusOutEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
QButtonGroup QAbstractButton.group (self)
```

[

返回此按钮所属的组。

](qbuttongroup.html)

[如果按钮没有任何一个成员](qbuttongroup.html)[QButtonGroup](qbuttongroup.html)，这个函数返回0 。

**See also** [QButtonGroup](qbuttongroup.html)。

```
bool QAbstractButton.hitButton (self, QPoint pos)
```

返回True如果_pos_是可点击的按钮矩形内，否则返回False 。

默认情况下，可点击区域是整个窗口部件。子类可以重新实现此功能，以提供不同形状和尺寸的可点击区域的支持。

```
QIcon QAbstractButton.icon (self)
```

[](qicon.html)

```
QSize QAbstractButton.iconSize (self)
```

[

```
bool QAbstractButton.isCheckable (self)
```

```
bool QAbstractButton.isChecked (self)
```

```
bool QAbstractButton.isDown (self)
```

```
QAbstractButton.keyPressEvent (self, QKeyEvent e)
```

](qsize.html)

[从重新实现](qsize.html)[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QAbstractButton.keyReleaseEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ） 。

```
QAbstractButton.mouseMoveEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QAbstractButton.mousePressEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QAbstractButton.mouseReleaseEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QAbstractButton.nextCheckState (self)
```

一个按钮被点击时，这个虚拟处理器被调用。默认实现调用setChecked （ ！[isChecked](qabstractbutton.html#checked-prop)（）） ，如果按钮[isCheckable](qabstractbutton.html#checkable-prop)（ ） 。它可以让子类实现中间按钮状态。

**See also** [checkStateSet](qabstractbutton.html#checkStateSet)（ ） 。

```
QAbstractButton.paintEvent (self, QPaintEvent e)
```

这种方法是抽象的，应在任何子类中重新实现。

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QAbstractButton.setAutoExclusive (self, bool)
```

```
QAbstractButton.setAutoRepeat (self, bool)
```

```
QAbstractButton.setAutoRepeatDelay (self, int)
```

```
QAbstractButton.setAutoRepeatInterval (self, int)
```

```
QAbstractButton.setCheckable (self, bool)
```

```
QAbstractButton.setChecked (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setChecked(bool)`。

```
QAbstractButton.setDown (self, bool)
```

```
QAbstractButton.setIcon (self, QIcon icon)
```

```
QAbstractButton.setIconSize (self, QSize size)
```

这种方法也是一个Qt槽与C + +的签名`void setIconSize(const QSize&)`。

```
QAbstractButton.setShortcut (self, QKeySequence key)
```

```
QAbstractButton.setText (self, QString text)
```

```
QKeySequence QAbstractButton.shortcut (self)
```

[

```
QString QAbstractButton.text (self)
```

```
QAbstractButton.timerEvent (self, QTimerEvent e)
```

](qkeysequence.html)

[从重新实现](qkeysequence.html)[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QAbstractButton.toggle (self)
```

这种方法也是一个Qt槽与C + +的签名`void toggle()`。

切换可检查的按钮的状态。

**See also** [checked](qabstractbutton.html#checked-prop)。

* * *

## Qt Signal Documentation

```
void clicked (bool = 0)
```

这是该信号的默认超载。

当按钮被激活（即按下然后释放当鼠标光标在按钮内） ，当快捷键键入，或者当这个信号被发射[click](qabstractbutton.html#click)（）或[animateClick](qabstractbutton.html#animateClick)（）被调用。值得注意的是，该信号是_not_如果你调用发出[setDown](qabstractbutton.html#down-prop)（ ）[setChecked](qabstractbutton.html#checked-prop)（）或[toggle](qabstractbutton.html#toggle)（ ） 。

如果按钮是可复，_checked_如果是按钮被选中真的，还是假的，如果按钮处于未选中状态。

**See also** [pressed](qabstractbutton.html#pressed)（ ）[released](qabstractbutton.html#released)（）和[toggled](qabstractbutton.html#toggled)（ ） 。

```
void pressed ()
```

这是该信号的默认超载。

当按钮被按下时，这个信号被发射。

**See also** [released](qabstractbutton.html#released)（）和[clicked](qabstractbutton.html#clicked)（ ） 。

```
void released ()
```

这是该信号的默认超载。

当按钮被释放这个信号被发射。

**See also** [pressed](qabstractbutton.html#pressed)（ ）[clicked](qabstractbutton.html#clicked)（）和[toggled](qabstractbutton.html#toggled)（ ） 。

```
void toggled (bool)
```

这是该信号的默认超载。

这个信号被发射时可检查的按钮改变其状态。_checked_如果是按钮被选中真的，还是假的，如果按钮处于未选中状态。

这可能是一个用户操作的结果，[click](qabstractbutton.html#click)（）槽的激活，或因为[setChecked](qabstractbutton.html#checked-prop)（ ）被调用。

在专属按钮组按钮的状态更新这个信号被发射之前。这意味着，槽可以在任一“关”的信号，或通过其状态已经改变的组中的按钮发出的“接通”信号采取行动。

例如，一个插槽，反应由新检出的按钮，但是它忽略来自已被取消选中使用下面的图案可以被实现按钮信号发射的信号：

```
 void MyWidget.reactToToggle(bool checked)
 {
    if (checked) {
       // Examine the new button states.
       ...
    }
 }

```

可以使用创建按钮组[QButtonGroup](qbuttongroup.html)类，并更新到按钮状态与监视[QButtonGroup.buttonClicked](qbuttongroup.html#buttonClicked)（）信号。

**See also** [checked](qabstractbutton.html#checked-prop)和[clicked](qabstractbutton.html#clicked)（ ） 。