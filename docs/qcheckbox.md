# QCheckBox Class Reference

## [[QtGui](index.htm) module]

该QCheckBox控件提供了一个文本标籤的复选框。[More...](#details)

继承[QAbstractButton](qabstractbutton.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QString text, QWidget parent = None)`
*   `Qt.CheckState checkState (self)`
*   `checkStateSet (self)`
*   `bool event (self, QEvent e)`
*   `bool hitButton (self, QPoint pos)`
*   `initStyleOption (self, QStyleOptionButton option)`
*   `bool isTristate (self)`
*   `QSize minimumSizeHint (self)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `nextCheckState (self)`
*   `paintEvent (self, QPaintEvent)`
*   `setCheckState (self, Qt.CheckState state)`
*   `setTristate (self, bool on = True)`
*   `QSize sizeHint (self)`

### Qt Signals

*   `void stateChanged (int)`

* * *

## Detailed Description

该QCheckBox控件提供了一个文本标籤的复选框。

一个QCheckBox是一个选项按钮，可以打开（选中）或关闭（未选中） 。复选框通常用于表示可以启用或禁用，而不会影响其他应用程序的功能，但不同类型的行为可以实施。例如，一个[QButtonGroup](qbuttongroup.html)可以用来检查组在逻辑上的按钮，允许独家复选框。但是，[QButtonGroup](qbuttongroup.html)不提供任何视觉表示。

下面进一步的图像显示了独家及非独家复选框之间的差异。

| ![](../img/checkboxes-exclusive.png) | ![](../img/checkboxes-non-exclusive.png) |

每当一个复选框被选中或清除它发出的信号[stateChanged](qcheckbox.html#stateChanged)（ ） 。连接到这个信号，如果你想每次复选框的状态发生改变来触发一个动作。您可以使用[isChecked](qabstractbutton.html#checked-prop)（ ）来查询一个复选框是否被选中。

除了通常的选中和未选中状态， QCheckBox选择提供第三状态表示“没有变化” 。每当你需要给用户既不检查也不是取消选中的复选框的选择，这是很有用的。如果您需要这第三状态，与启用[setTristate](qcheckbox.html#tristate-prop)（） ，并使用[checkState](qcheckbox.html#checkState)（ ）查询当前的切换状态。

一样[QPushButton](qpushbutton.html)，一个复选框显示文本和可选的小图标。该图标设置[setIcon](qabstractbutton.html#icon-prop)（ ） 。该文本可以在构造函数或设置[setText](qabstractbutton.html#text-prop)（ ） 。快捷键可以通过首选字符与前面的符号来指定。例如：

```
 QCheckBox *checkbox = new QCheckBox("C&ase sensitive", this);

```

在这个例子中，快捷键是_Alt+A_。请参阅[QShortcut](qshortcut.html#mnemonic)有关详细信息的文档（显示的实际符号，使用“\u0026\u0026” ） 。

重要的继承功能：[text](qabstractbutton.html#text-prop)（ ）[setText](qabstractbutton.html#text-prop)（ ）[text](qabstractbutton.html#text-prop)（ ）[pixmap](index.htm#pixmap)（ ）[setPixmap](index.htm#setPixmap)（ ）[accel](index.htm#accel)（ ）[setAccel](index.htm#setAccel)（ ）[isToggleButton](index.htm#isToggleButton)（ ）[setDown](qabstractbutton.html#down-prop)（ ）[isDown](qabstractbutton.html#down-prop)（ ）[isOn](index.htm#isOn)（ ）[checkState](qcheckbox.html#checkState)（ ）[autoRepeat](qabstractbutton.html#autoRepeat-prop)（ ） ， isExclusiveToggle （ ） ，[group](qabstractbutton.html#group)（ ）[setAutoRepeat](qabstractbutton.html#autoRepeat-prop)（ ）[toggle](qabstractbutton.html#toggle)（ ）[pressed](qabstractbutton.html#pressed)（ ）[released](qabstractbutton.html#released)（ ）[clicked](qabstractbutton.html#clicked)（ ）[toggled](qabstractbutton.html#toggled)（ ）[checkState](qcheckbox.html#checkState)（）和[stateChanged](qcheckbox.html#stateChanged)（ ） 。

| ![Screenshot of a Macintosh style checkbox](../img/macintosh-checkbox.png) | A checkbox shown in the [Macintosh widget style](index.htm). |
| ![Screenshot of a Windows XP style checkbox](../img/windows-checkbox.png) | A checkbox shown in the [Windows XP widget style](index.htm). |
| ![Screenshot of a Plastique style checkbox](../img/plastique-checkbox.png) | A checkbox shown in the [Plastique widget style](index.htm). |

* * *

## Method Documentation

```
QCheckBox.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个复选框与给定_parent_，但没有文字。

_parent_到传递[QAbstractButton](qabstractbutton.html)构造函数。

```
QCheckBox.__init__ (self, QString text, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个复选框与给定_parent_和_text_。

_parent_到传递[QAbstractButton](qabstractbutton.html)构造函数。

```
Qt.CheckState QCheckBox.checkState (self)
```

[](qt.html#CheckState-enum)

[返回复选框的选中状态。如果您不需要三态的支持，您还可以使用](qt.html#CheckState-enum)[QAbstractButton.isChecked](qabstractbutton.html#checked-prop)（ ）返回一个布尔值。

**See also** [setCheckState](qcheckbox.html#setCheckState)（）和[Qt.CheckState](qt.html#CheckState-enum)。

```
QCheckBox.checkStateSet (self)
```

从重新实现[QAbstractButton.checkStateSet](qabstractbutton.html#checkStateSet)（ ） 。

```
bool QCheckBox.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QCheckBox.hitButton (self, QPoint pos)
```

从重新实现[QAbstractButton.hitButton](qabstractbutton.html#hitButton)（ ） 。

```
QCheckBox.initStyleOption (self, QStyleOptionButton option)
```

初始化_option_与其它的值[QCheckBox](qcheckbox.html)。这种方法对于那些需要子类有用[QStyleOptionButton](qstyleoptionbutton.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
bool QCheckBox.isTristate (self)
```

```
QSize QCheckBox.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

此功能被引入Qt的4.8 。

```
QCheckBox.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QCheckBox.nextCheckState (self)
```

从重新实现[QAbstractButton.nextCheckState](qabstractbutton.html#nextCheckState)（ ） 。

```
QCheckBox.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QCheckBox.setCheckState (self, Qt.CheckState state)
```

设置复选框的选中状态，以_state_。如果您不需要三态的支持，您还可以使用[QAbstractButton.setChecked](qabstractbutton.html#checked-prop)（ ） ，它接受一个布尔值。

**See also** [checkState](qcheckbox.html#checkState)（）和[Qt.CheckState](qt.html#CheckState-enum)。

```
QCheckBox.setTristate (self, bool on = True)
```

```
QSize QCheckBox.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

* * *

## Qt Signal Documentation

```
void stateChanged (int)
```

这是该信号的默认超载。

这个信号被发射时该复选框的状态发生变化，即每当用户选中或取消选中它。

_state_包含复选框的新[Qt.CheckState](qt.html#CheckState-enum)。