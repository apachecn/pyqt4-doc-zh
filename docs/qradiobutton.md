# QRadioButton Class Reference

## [[QtGui](index.htm) module]

该QRadioButton小工具提供了一个文本标籤的单选按钮。[More...](#details)

继承[QAbstractButton](qabstractbutton.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QString text, QWidget parent = None)`
*   `bool event (self, QEvent e)`
*   `bool hitButton (self, QPoint)`
*   `initStyleOption (self, QStyleOptionButton button)`
*   `QSize minimumSizeHint (self)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `paintEvent (self, QPaintEvent)`
*   `QSize sizeHint (self)`

* * *

## Detailed Description

该QRadioButton小工具提供了一个文本标籤的单选按钮。

一个QRadioButton是一个选项按钮，可以打开（选中）或关闭（未选中） 。单选按钮通常与选择了“一对多”呈现给用户。在一组单选按钮，在同一时间只有一个单选按钮可以检查，如果用户选择另一个按钮，则之前选中的按钮被关闭。

单选按钮[autoExclusive](qabstractbutton.html#autoExclusive-prop)在默认情况下。如果自动独家启用，属于同一个父控件单选按钮的行为，好像他们是同一个专属按钮组的一部分。如果需要多个专属按钮组对属于同一个父部件单选按钮，把它们放到一个[QButtonGroup](qbuttongroup.html)。

每当一个按钮打开或关闭它发出的[toggled](qabstractbutton.html#toggled)（）信号。连接到这个信号，如果你希望每次触发一个动作按钮的状态发生改变。使用[isChecked](qabstractbutton.html#checked-prop)（）以查看是否已选择了一个特定的按钮。

一样[QPushButton](qpushbutton.html)，单选按钮显示文本和可选的小图标。该图标设置[setIcon](qabstractbutton.html#icon-prop)（ ） 。该文本可以在构造函数或设置[setText](qabstractbutton.html#text-prop)（ ） 。快捷键可以首选使用的字符在文本中的＆符号前面的指定。例如：

```
 QRadioButton *button = new QRadioButton("Search from the &cursor", this);

```

在这个例子中，快捷键是_Alt+c_。请参阅[QShortcut](qshortcut.html#mnemonic)有关详细信息的文档（显示的实际符号，使用“\u0026\u0026” ） 。

重要继承的成员：[text](qabstractbutton.html#text-prop)（ ）[setText](qabstractbutton.html#text-prop)（ ）[text](qabstractbutton.html#text-prop)（ ）[setDown](qabstractbutton.html#down-prop)（ ）[isDown](qabstractbutton.html#down-prop)（ ）[autoRepeat](qabstractbutton.html#autoRepeat-prop)（ ）[group](qabstractbutton.html#group)（ ）[setAutoRepeat](qabstractbutton.html#autoRepeat-prop)（ ）[toggle](qabstractbutton.html#toggle)（ ）[pressed](qabstractbutton.html#pressed)（ ）[released](qabstractbutton.html#released)（ ）[clicked](qabstractbutton.html#clicked)（）和[toggled](qabstractbutton.html#toggled)（ ） 。

| ![Screenshot of a Plastique radio button](../img/plastique-radiobutton.png) | A radio button shown in the [Plastique widget style](index.htm). |
| ![Screenshot of a Windows XP radio button](../img/windows-radiobutton.png) | A radio button shown in the [Windows XP widget style](index.htm). |
| ![Screenshot of a Macintosh radio button](../img/macintosh-radiobutton.png) | A radio button shown in the [Macintosh widget style](index.htm). |

* * *

## Method Documentation

```
QRadioButton.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个单选按钮，用给定的_parent_，但没有文字或像素图。

该_parent_参数被传递到[QAbstractButton](qabstractbutton.html)构造函数。

```
QRadioButton.__init__ (self, QString text, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个单选按钮，用给定的_parent_和_text_字符串。

该_parent_参数被传递到[QAbstractButton](qabstractbutton.html)构造函数。

```
bool QRadioButton.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QRadioButton.hitButton (self, QPoint)
```

从重新实现[QAbstractButton.hitButton](qabstractbutton.html#hitButton)（ ） 。

```
QRadioButton.initStyleOption (self, QStyleOptionButton button)
```

初始化_option_与其它的值[QRadioButton](qradiobutton.html)。当他们需要一个这种方法是有用的子类[QStyleOptionButton](qstyleoptionbutton.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QSize QRadioButton.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

此功能被引入Qt的4.8 。

```
QRadioButton.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QRadioButton.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QSize QRadioButton.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。