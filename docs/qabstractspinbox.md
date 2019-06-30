# QAbstractSpinBox Class Reference

## [[QtGui](index.htm) module]

该QAbstractSpinBox类提供了一个纺纱器和一个行编辑，以显示值。[More...](#details)

继承[QWidget](qwidget.html)。

通过继承[QDateTimeEdit](qdatetimeedit.html)，[QDoubleSpinBox](qdoublespinbox.html)和[QSpinBox](qspinbox.html)。

### Types

*   `enum ButtonSymbols { UpDownArrows, PlusMinus, NoButtons }`
*   `enum CorrectionMode { CorrectToPreviousValue, CorrectToNearestValue }`
*   `class **[StepEnabled](index.htm)**`
*   `enum StepEnabledFlag { StepNone, StepUpEnabled, StepDownEnabled }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `Qt.Alignment alignment (self)`
*   `ButtonSymbols buttonSymbols (self)`
*   `changeEvent (self, QEvent e)`
*   `clear (self)`
*   `closeEvent (self, QCloseEvent e)`
*   `contextMenuEvent (self, QContextMenuEvent e)`
*   `CorrectionMode correctionMode (self)`
*   `bool event (self, QEvent event)`
*   `QString input fixup (self, QString input)`
*   `fixup (self, QString input)`
*   `focusInEvent (self, QFocusEvent e)`
*   `focusOutEvent (self, QFocusEvent e)`
*   `bool hasAcceptableInput (self)`
*   `bool hasFrame (self)`
*   `hideEvent (self, QHideEvent e)`
*   `initStyleOption (self, QStyleOptionSpinBox option)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery)`
*   `interpretText (self)`
*   `bool isAccelerated (self)`
*   `bool isReadOnly (self)`
*   `bool keyboardTracking (self)`
*   `keyPressEvent (self, QKeyEvent e)`
*   `keyReleaseEvent (self, QKeyEvent e)`
*   `QLineEdit lineEdit (self)`
*   `QSize minimumSizeHint (self)`
*   `mouseMoveEvent (self, QMouseEvent e)`
*   `mousePressEvent (self, QMouseEvent e)`
*   `mouseReleaseEvent (self, QMouseEvent e)`
*   `paintEvent (self, QPaintEvent e)`
*   `resizeEvent (self, QResizeEvent e)`
*   `selectAll (self)`
*   `setAccelerated (self, bool on)`
*   `setAlignment (self, Qt.Alignment flag)`
*   `setButtonSymbols (self, ButtonSymbols bs)`
*   `setCorrectionMode (self, CorrectionMode cm)`
*   `setFrame (self, bool)`
*   `setKeyboardTracking (self, bool kt)`
*   `setLineEdit (self, QLineEdit e)`
*   `setReadOnly (self, bool r)`
*   `setSpecialValueText (self, QString s)`
*   `setWrapping (self, bool w)`
*   `showEvent (self, QShowEvent e)`
*   `QSize sizeHint (self)`
*   `QString specialValueText (self)`
*   `stepBy (self, int steps)`
*   `stepDown (self)`
*   `StepEnabled stepEnabled (self)`
*   `stepUp (self)`
*   `QString text (self)`
*   `timerEvent (self, QTimerEvent e)`
*   `(QValidator.State, QString input, int pos) validate (self, QString input, int pos)`
*   `(QValidator.State, int pos) validate (self, QString input, int pos)`
*   `wheelEvent (self, QWheelEvent e)`
*   `bool wrapping (self)`

### Qt Signals

*   `void editingFinished ()`

* * *

## Detailed Description

该QAbstractSpinBox类提供了一个纺纱器和一个行编辑，以显示值。

这个类被设计成一个共同的超类的小部件一样[QSpinBox](qspinbox.html)，[QDoubleSpinBox](qdoublespinbox.html)和[QDateTimeEdit](qdatetimeedit.html)

下面是类的主要属性：

1.  [text](qabstractspinbox.html#text-prop)：表示显示在QAbstractSpinBox的文本。
2.  [alignment](qabstractspinbox.html#alignment-prop)：在QAbstractSpinBox文本的对齐方式。
3.  [wrapping](qabstractspinbox.html#wrapping-prop)：无论QAbstractSpinBox从最小值换到最大值，正相反。

QAbstractSpinBox提供了一个虚拟[stepBy](qabstractspinbox.html#stepBy)每当用户触发一个步骤（）函数被调用。这个函数接受一个整数值来表示多少步拍摄。例如压制[Qt.Key_Down](qt.html#Key-enum)将触发调用stepBy （-1 ） 。

QAbstractSpinBox还提供了一个虚函数[stepEnabled](qabstractspinbox.html#stepEnabled)（ ）来判断是否加强向上/向下是允许在任何时候。该函数返回一个bitset[StepEnabled](qabstractspinbox.html#StepEnabledFlag-enum)。

* * *

## Type Documentation

```
QAbstractSpinBox.ButtonSymbols
```

该枚举类型描述了可以在旋转框中显示的按钮的符号。

![](../img/qspinbox-updown.png) ![](../img/qspinbox-plusminus.png)

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractSpinBox.UpDownArrows` | `0` | 小箭头的经典款式。 |
| `QAbstractSpinBox.PlusMinus` | `1` | **+**和**-**符号。 |
| `QAbstractSpinBox.NoButtons` | `2` | 不显示按钮。 |

**See also** [QAbstractSpinBox.buttonSymbols](qabstractspinbox.html#buttonSymbols-prop)。

```
QAbstractSpinBox.CorrectionMode
```

该枚举类型描述模式的纺纱器将用来纠正[Intermediate](qvalidator.html#State-enum)如果编辑结束值。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractSpinBox.CorrectToPreviousValue` | `0` | 纺纱器将恢复到最后的有效价值。 |
| `QAbstractSpinBox.CorrectToNearestValue` | `1` | 纺纱器将恢复到最接近的有效值。 |

**See also** [correctionMode](qabstractspinbox.html#correctionMode-prop)。

```
QAbstractSpinBox.StepEnabledFlag
```

| Constant | Value |
| --- | --- |
| `QAbstractSpinBox.StepNone` | `0x00` |
| `QAbstractSpinBox.StepUpEnabled` | `0x01` |
| `QAbstractSpinBox.StepDownEnabled` | `0x02` |

该StepEnabled类型是一个typedef为[QFlags](index.htm)\u003cStepEnabledFlag\u003e 。它存储StepEnabledFlag值的或组合。

* * *

## Method Documentation

```
QAbstractSpinBox.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个抽象的纺纱用给定的_parent_使用默认[wrapping](qabstractspinbox.html#wrapping-prop)和[alignment](qabstractspinbox.html#alignment-prop)属性。

```
Qt.Alignment QAbstractSpinBox.alignment (self)
```

[](index.htm)

```
ButtonSymbols QAbstractSpinBox.buttonSymbols (self)
```

[

```
QAbstractSpinBox.changeEvent (self, QEvent e)
```

](qabstractspinbox.html#ButtonSymbols-enum)

[从重新实现](qabstractspinbox.html#ButtonSymbols-enum)[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QAbstractSpinBox.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

清除所有文本，但前缀和后缀的lineedit 。

```
QAbstractSpinBox.closeEvent (self, QCloseEvent e)
```

从重新实现[QWidget.closeEvent](qwidget.html#closeEvent)（ ） 。

```
QAbstractSpinBox.contextMenuEvent (self, QContextMenuEvent e)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
CorrectionMode QAbstractSpinBox.correctionMode (self)
```

[

```
bool QAbstractSpinBox.event (self, QEvent event)
```

](qabstractspinbox.html#CorrectionMode-enum)

[从重新实现](qabstractspinbox.html#CorrectionMode-enum)[QObject.event](qobject.html#event)（ ） 。

```
QString input QAbstractSpinBox.fixup (self, QString input)
```

这个虚函数被调用的[QAbstractSpinBox](qabstractspinbox.html)如果_input_不验证，[QValidator.Acceptable](qvalidator.html#State-enum)返回时，按下或[interpretText](qabstractspinbox.html#interpretText)（）被调用。它会尝试改变文本，以便它是有效的。重新实现在各个子类。

```
QAbstractSpinBox.fixup (self, QString input)
```

```
QAbstractSpinBox.focusInEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
QAbstractSpinBox.focusOutEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
bool QAbstractSpinBox.hasAcceptableInput (self)
```

```
bool QAbstractSpinBox.hasFrame (self)
```

```
QAbstractSpinBox.hideEvent (self, QHideEvent e)
```

从重新实现[QWidget.hideEvent](qwidget.html#hideEvent)（ ） 。

```
QAbstractSpinBox.initStyleOption (self, QStyleOptionSpinBox option)
```

初始化_option_与其它的值[QSpinBox](qspinbox.html)。当他们需要一个这种方法是有用的子类[QStyleOptionSpinBox](qstyleoptionspinbox.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QVariant QAbstractSpinBox.inputMethodQuery (self, Qt.InputMethodQuery)
```

从重新实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
QAbstractSpinBox.interpretText (self)
```

这个函数把数值输入框的文字。如果该值已经从去年的解释改变了它会发出信号。

```
bool QAbstractSpinBox.isAccelerated (self)
```

```
bool QAbstractSpinBox.isReadOnly (self)
```

```
bool QAbstractSpinBox.keyboardTracking (self)
```

```
QAbstractSpinBox.keyPressEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

这个函数处理键盘输入。

下面的键被特别处理：

| Enter/Return | This will reinterpret the text and emit a signal even if the value has not changed since last time a signal was emitted. |
| Up | This will invoke stepBy(1) |
| Down | This will invoke stepBy(-1) |
| Page up | This will invoke stepBy(10) |
| Page down | This will invoke stepBy(-10) |

```
QAbstractSpinBox.keyReleaseEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ） 。

```
QLineEdit QAbstractSpinBox.lineEdit (self)
```

[

这个函数返回一个指针，指向旋转框的行编辑。

](qlineedit.html)

[**See also**](qlineedit.html) [setLineEdit](qabstractspinbox.html#setLineEdit)（ ） 。

```
QSize QAbstractSpinBox.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QAbstractSpinBox.mouseMoveEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QAbstractSpinBox.mousePressEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QAbstractSpinBox.mouseReleaseEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QAbstractSpinBox.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QAbstractSpinBox.resizeEvent (self, QResizeEvent e)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QAbstractSpinBox.selectAll (self)
```

这种方法也是一个Qt槽与C + +的签名`void selectAll()`。

选择在纺纱除了前缀和后缀的所有文本。

```
QAbstractSpinBox.setAccelerated (self, bool on)
```

```
QAbstractSpinBox.setAlignment (self, Qt.Alignment flag)
```

```
QAbstractSpinBox.setButtonSymbols (self, ButtonSymbols bs)
```

```
QAbstractSpinBox.setCorrectionMode (self, CorrectionMode cm)
```

```
QAbstractSpinBox.setFrame (self, bool)
```

```
QAbstractSpinBox.setKeyboardTracking (self, bool kt)
```

```
QAbstractSpinBox.setLineEdit (self, QLineEdit e)
```

该_e_说法有它的所有权转移给Qt的。

设置纺纱是的行编辑_lineEdit_而不是当前行编辑控件。_lineEdit_不能为0 。

[QAbstractSpinBox](qabstractspinbox.html)采用新lineEdit的所有权

If [QLineEdit.validator](qlineedit.html#validator)（ ）为_lineEdit_返回0 ，纺纱器的内部验证器将上线的编辑设置。

**See also** [lineEdit](qabstractspinbox.html#lineEdit)（ ） 。

```
QAbstractSpinBox.setReadOnly (self, bool r)
```

```
QAbstractSpinBox.setSpecialValueText (self, QString s)
```

```
QAbstractSpinBox.setWrapping (self, bool w)
```

```
QAbstractSpinBox.showEvent (self, QShowEvent e)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QSize QAbstractSpinBox.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QString QAbstractSpinBox.specialValueText (self)
```

```
QAbstractSpinBox.stepBy (self, int steps)
```

只要用户触发了一步虚函数时被调用。该_steps_参数表示要走多少步拍摄，如压制[Qt.Key_Down](qt.html#Key-enum)将触发一个呼叫到stepBy （-1 ），而压[Qt.Key_Prior](qt.html#Key-enum)将触发调用stepBy （ 10 ） 。

如果子类[QAbstractSpinBox](qabstractspinbox.html)你必须重新实现此功能。注意，这个函数被调用，即使所得到的值将是最小值和最大值的范围之外。这是这个函数的任务来处理这些情况。

```
QAbstractSpinBox.stepDown (self)
```

这种方法也是一个Qt槽与C + +的签名`void stepDown()`。

下台一linestep调用这个插槽是类似于调用stepBy （-1 ） ;

**See also** [stepBy](qabstractspinbox.html#stepBy)（）和[stepUp](qabstractspinbox.html#stepUp)（ ） 。

```
StepEnabled QAbstractSpinBox.stepEnabled (self)
```

[

虚拟函数，确定是否步进上下是合法的在任何给定时间。

](index.htm)

[向上箭头将被描绘成禁止，除非（ stepEnabled （ ​​） ＆](index.htm)[StepUpEnabled](qabstractspinbox.html#StepEnabledFlag-enum)！） = 0 。

默认实现将返回（[StepUpEnabled](qabstractspinbox.html#StepEnabledFlag-enum)|[StepDownEnabled](qabstractspinbox.html#StepEnabledFlag-enum)） ，如果包装被打开。否则它会返回[StepDownEnabled](qabstractspinbox.html#StepEnabledFlag-enum)如果值是\u003e最小（ ）与OR'ed[StepUpEnabled](qabstractspinbox.html#StepEnabledFlag-enum)如果值\u003c最大（ ） 。

如果子类[QAbstractSpinBox](qabstractspinbox.html)您将需要重新实现这个函数。

**See also** [QSpinBox.minimum](qspinbox.html#minimum-prop)（ ）[QSpinBox.maximum](qspinbox.html#maximum-prop)（）和[wrapping](qabstractspinbox.html#wrapping-prop)（ ） 。

```
QAbstractSpinBox.stepUp (self)
```

这种方法也是一个Qt槽与C + +的签名`void stepUp()`。

台阶由一个linestep调用这个插槽是类似于调用stepBy （ 1 ） ;

**See also** [stepBy](qabstractspinbox.html#stepBy)（）和[stepDown](qabstractspinbox.html#stepDown)（ ） 。

```
QString QAbstractSpinBox.text (self)
```

```
QAbstractSpinBox.timerEvent (self, QTimerEvent e)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
(QValidator.State, QString input, int pos) QAbstractSpinBox.validate (self, QString input, int pos)
```

这个虚函数被调用的[QAbstractSpinBox](qabstractspinbox.html)以确定是否_input_是有效的。该_pos_参数表示字符串中的位置。重新实现在各个子类。

```
(QValidator.State, int pos) QAbstractSpinBox.validate (self, QString input, int pos)
```

```
QAbstractSpinBox.wheelEvent (self, QWheelEvent e)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

```
bool QAbstractSpinBox.wrapping (self)
```

* * *

## Qt Signal Documentation

```
void editingFinished ()
```

这是该信号的默认超载。

这个信号被发射编辑完成。这种情况发生在纺纱器失去焦点时按Enter键。