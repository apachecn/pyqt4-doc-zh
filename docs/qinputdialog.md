# QInputDialog Class Reference

## [[QtGui](index.htm) module]

该QInputDialog类提供了一个简单方便的对话框，从用户得到一个单一的值。[More...](#details)

继承[QDialog](qdialog.html)。

### Types

*   `enum InputDialogOption { NoButtons, UseListViewForComboBoxItems }`
*   `class **[InputDialogOptions](index.htm)**`
*   `enum InputMode { TextInput, IntInput, DoubleInput }`

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `QString cancelButtonText (self)`
*   `QStringList comboBoxItems (self)`
*   `done (self, int result)`
*   `int doubleDecimals (self)`
*   `float doubleMaximum (self)`
*   `float doubleMinimum (self)`
*   `float doubleValue (self)`
*   `InputMode inputMode (self)`
*   `int intMaximum (self)`
*   `int intMinimum (self)`
*   `int intStep (self)`
*   `int intValue (self)`
*   `bool isComboBoxEditable (self)`
*   `QString labelText (self)`
*   `QSize minimumSizeHint (self)`
*   `QString okButtonText (self)`
*   `open (self)`
*   `open (self, QObject receiver, SLOT()SLOT() member)`
*   `open (self, callable receiver)`
*   `InputDialogOptions options (self)`
*   `setCancelButtonText (self, QString text)`
*   `setComboBoxEditable (self, bool editable)`
*   `setComboBoxItems (self, QStringList items)`
*   `setDoubleDecimals (self, int decimals)`
*   `setDoubleMaximum (self, float max)`
*   `setDoubleMinimum (self, float min)`
*   `setDoubleRange (self, float min, float max)`
*   `setDoubleValue (self, float value)`
*   `setInputMode (self, InputMode mode)`
*   `setIntMaximum (self, int max)`
*   `setIntMinimum (self, int min)`
*   `setIntRange (self, int min, int max)`
*   `setIntStep (self, int step)`
*   `setIntValue (self, int value)`
*   `setLabelText (self, QString text)`
*   `setOkButtonText (self, QString text)`
*   `setOption (self, InputDialogOption option, bool on = True)`
*   `setOptions (self, InputDialogOptions options)`
*   `setTextEchoMode (self, QLineEdit.EchoMode mode)`
*   `setTextValue (self, QString text)`
*   `setVisible (self, bool visible)`
*   `QSize sizeHint (self)`
*   `bool testOption (self, InputDialogOption option)`
*   `QLineEdit.EchoMode textEchoMode (self)`
*   `QString textValue (self)`

### Static Methods

*   `(float, bool ok) getDouble (QWidget parent, QString title, QString label, float value = 0, float min = -2147483647, float max = 2147483647, int decimals = 1, Qt.WindowFlags flags = 0)`
*   `(int, bool ok) getInt (QWidget parent, QString title, QString label, int value = 0, int min = -2147483647, int max = 2147483647, int step = 1, Qt.WindowFlags flags = 0)`
*   `(int, bool ok) getInteger (QWidget parent, QString title, QString label, int value = 0, int min = -2147483647, int max = 2147483647, int step = 1, Qt.WindowFlags flags = 0)`
*   `(QString, bool ok) getItem (QWidget parent, QString title, QString label, QStringList list, int current = 0, bool editable = True, Qt.WindowFlags flags = 0)`
*   `(QString, bool ok) getItem (QWidget parent, QString title, QString label, QStringList list, int current, bool editable, Qt.WindowFlags flags, Qt.InputMethodHints inputMethodHints)`
*   `(QString, bool ok) getText (QWidget parent, QString title, QString label, QLineEdit.EchoMode mode = QLineEdit.Normal, QString text = QString(), Qt.WindowFlags flags = 0)`
*   `(QString, bool ok) getText (QWidget parent, QString title, QString label, QLineEdit.EchoMode mode, QString text, Qt.WindowFlags flags, Qt.InputMethodHints inputMethodHints)`

### Qt Signals

*   `void doubleValueChanged (double)`
*   `void doubleValueSelected (double)`
*   `void intValueChanged (int)`
*   `void intValueSelected (int)`
*   `void textValueChanged (const QString&)`
*   `void textValueSelected (const QString&)`

* * *

## Detailed Description

该QInputDialog类提供了一个简单方便的对话框，从用户得到一个单一的值。

输入值可以是一个字符串，一个数字或一个项目从一个列表中。一个标籤必须设置来告诉他们应该进入的用户。

提供了四个静态的便利功能：[getText](qinputdialog.html#getText)（ ）[getInt](qinputdialog.html#getInt)（ ）[getDouble](qinputdialog.html#getDouble)（）和[getItem](qinputdialog.html#getItem)（ ） 。所有的功能都可以以类似的方式被使用，例如：

```
     bool ok;
     [QString](qstring.html) text = QInputDialog.getText(this, tr("QInputDialog.getText()"),
                                          tr("User name:"), [QLineEdit](qlineedit.html).Normal,
                                          [QDir](qdir.html).home().dirName(), &ok);
     if (ok && !text.isEmpty())
         textLabel->setText(text);

```

该`ok`变量被设置为True，如果用户点击**OK**否则它被设置为False 。

![Input Dialogs](../img/inputdialogs.png)

该[Standard Dialogs](index.htm)示例显示了如何使用QInputDialog以及其他内置Qt对话框。

* * *

## Type Documentation

```
QInputDialog.InputDialogOption
```

此枚举指定影响的输入对话框的外观和感觉的各种选项。

| Constant | Value | Description |
| --- | --- | --- |
| `QInputDialog.NoButtons` | `0x00000001` | 不显示**OK**和**Cancel**按钮。 （有用的“现场对话” 。 ） |
| `QInputDialog.UseListViewForComboBoxItems` | `0x00000002` | 使用[QListView](qlistview.html)而不是一个不可编辑[QComboBox](qcombobox.html)用于显示设置的项[setComboBoxItems](qinputdialog.html#comboBoxItems-prop)（ ） 。 |

这个枚举被引入或修改的Qt 4.5 。

该InputDialogOptions类型是一个typedef为[QFlags](index.htm)\u003cInputDialogOption\u003e 。它存储InputDialogOption值的或组合。

**See also** [options](qinputdialog.html#options-prop)，[setOption](qinputdialog.html#setOption)（）和[testOption](qinputdialog.html#testOption)（ ） 。

```
QInputDialog.InputMode
```

该枚举描述输入的不同的模式，可以选择对于该对话框。

| Constant | Value | Description |
| --- | --- | --- |
| `QInputDialog.TextInput` | `0` | 用于输入文本字符串。 |
| `QInputDialog.IntInput` | `1` | 用于输入整数。 |
| `QInputDialog.DoubleInput` | `2` | 用于输入浮点数与双精度的准确性。 |

这个枚举被引入或修改的Qt 4.5 。

**See also** [inputMode](qinputdialog.html#inputMode-prop)。

* * *

## Method Documentation

```
QInputDialog.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的输入对话框与给定_parent_和窗口_flags_。

此功能被引入Qt的4.5 。

```
QString QInputDialog.cancelButtonText (self)
```

```
QStringList QInputDialog.comboBoxItems (self)
```

```
QInputDialog.done (self, int result)
```

从重新实现[QDialog.done](qdialog.html#done)（ ） 。

关闭对话框，并将其结果代码_result_。如果显示此对话框[exec_](qdialog.html#exec)（ ） ， （）完成将导致本地事件循环来完成，并[exec_](qdialog.html#exec)（ ）返回_result_。

**See also** [QDialog.done](qdialog.html#done)（ ） 。

```
int QInputDialog.doubleDecimals (self)
```

```
float QInputDialog.doubleMaximum (self)
```

```
float QInputDialog.doubleMinimum (self)
```

```
float QInputDialog.doubleValue (self)
```

```
(float, bool ok) QInputDialog.getDouble (QWidget parent, QString title, QString label, float value = 0, float min = -2147483647, float max = 2147483647, int decimals = 1, Qt.WindowFlags flags = 0)
```

静态方便的功能，从用户得到一个浮点数。

_title_是显示在对话框的标题栏中的文本。_label_是显示给用户的文本（它应该说些什么应该输入） 。_value_是该行编辑将被设置为默认的浮点数。_min_和_max_是最低和最高值，用户可以选择。_decimals_是的小数位数可能会有的最大数量。

If _ok_非空， *_ok_将被设置为True，如果用户按下**OK**并为False ，如果用户按下**Cancel**。该对话框的父_parent_。该对话框将是模式，并使用小工具_flags_。

该函数返回已被用户输入的浮点数。

使用这个静态函数是这样的：

```
     bool ok;
     double d = [QInputDialog](qinputdialog.html).getDouble(this, tr("QInputDialog.getDouble()"),
                                        tr("Amount:"), 37.56, -10000, 10000, 2, &ok);
     if (ok)
         doubleLabel->setText([QString](qstring.html)("$%1").arg(d));

```

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QInputDialog](qinputdialog.html)构造函数。

**See also** [getText](qinputdialog.html#getText)（ ）[getInt](qinputdialog.html#getInt)（）和[getItem](qinputdialog.html#getItem)（ ） 。

```
(int, bool ok) QInputDialog.getInt (QWidget parent, QString title, QString label, int value = 0, int min = -2147483647, int max = 2147483647, int step = 1, Qt.WindowFlags flags = 0)
```

静态方便的功能，从用户得到的整数输入。

_title_是显示在对话框的标题栏中的文本。_label_是显示给用户的文本（它应该说些什么应该输入） 。_value_是默认的整数，它的纺纱器将被设置。_min_和_max_是最低和最高值，用户可以选择。_step_是通过该值的变化作为用户的数量按压箭头按钮来递增或递减的值。

If _ok_非空*_ok_将被设置为True，如果用户按下**OK**并为False ，如果用户按下**Cancel**。该对话框的父_parent_。该对话框将是模式，并使用小工具_flags_。

如果成功，该函数返回已被用户输入的整数;失败，返回初始_value_。

使用这个静态函数是这样的：

```
     bool ok;
     int i = [QInputDialog](qinputdialog.html).getInt(this, tr("QInputDialog.getInteger()"),
                                  tr("Percentage:"), 25, 0, 100, 1, &ok);
     if (ok)
         integerLabel->setText(tr("%1%").arg(i));

```

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QInputDialog](qinputdialog.html)构造函数。

此功能被引入Qt的4.5 。

**See also** [getText](qinputdialog.html#getText)（ ）[getDouble](qinputdialog.html#getDouble)（）和[getItem](qinputdialog.html#getItem)（ ） 。

```
(int, bool ok) QInputDialog.getInteger (QWidget parent, QString title, QString label, int value = 0, int min = -2147483647, int max = 2147483647, int step = 1, Qt.WindowFlags flags = 0)
```

```
(QString, bool ok) QInputDialog.getItem (QWidget parent, QString title, QString label, QStringList list, int current = 0, bool editable = True, Qt.WindowFlags flags = 0)
```

静态方便的功能，让用户从一个字符串列表中选择一项。

_title_是显示在对话框的标题栏中的文本。_label_是显示给用户的文本（它应该说些什么应该输入） 。_items_是被插入到组合框的字符串列表。_current_是它应该是当前项的项的数目。_inputMethodHints_是输入法的提示，如果ComboBox可编辑和输入法被激活，将被使用。

If _editable_诚然，用户可以输入自己的文字，否则用户只能选择现有的项目之一。

If _ok_非空_*a_确定将被设置为True，如果用户按下**OK**并为False ，如果用户按下**Cancel**。该对话框的父_parent_。该对话框将是模式，并使用小工具_flags_。

这个函数返回当前项的文本，或者如果_editable_是真的，组合框的当前文本。

使用这个静态函数是这样的：

```
     [QStringList](qstringlist.html) items;
     items << tr("Spring") << tr("Summer") << tr("Fall") << tr("Winter");

     bool ok;
     [QString](qstring.html) item = [QInputDialog](qinputdialog.html).getItem(this, tr("QInputDialog.getItem()"),
                                          tr("Season:"), items, 0, false, &ok);
     if (ok && !item.isEmpty())
         itemLabel->setText(item);

```

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QInputDialog](qinputdialog.html)构造函数。

**See also** [getText](qinputdialog.html#getText)（ ）[getInt](qinputdialog.html#getInt)（）和[getDouble](qinputdialog.html#getDouble)（ ） 。

```
(QString, bool ok) QInputDialog.getItem (QWidget parent, QString title, QString label, QStringList list, int current, bool editable, Qt.WindowFlags flags, Qt.InputMethodHints inputMethodHints)
```

```
(QString, bool ok) QInputDialog.getText (QWidget parent, QString title, QString label, QLineEdit.EchoMode mode = QLineEdit.Normal, QString text = QString(), Qt.WindowFlags flags = 0)
```

静态方便的功能，从用户得到的字符串。

_title_是显示在对话框的标题栏中的文本。_label_是显示给用户的文本（它应该说些什么应该输入） 。_text_是这是摆在该行的编辑默认文本。_mode_是回波模式的行编辑将使用。_inputMethodHints_是输入法的提示，将用于在编辑插件如果一个输入法是活动的。

If _ok_非空_*a_确定将被设置为True，如果用户按下**OK**并为False ，如果用户按下**Cancel**。该对话框的父_parent_。该对话框将是模式，并使用指定部件_flags_。

如果接受了对话，这个函数返回在对话框的行编辑的文本。如果对话框被拒绝，空[QString](qstring.html)返回。

使用这个静态函数是这样的：

```
     bool ok;
     [QString](qstring.html) text = [QInputDialog](qinputdialog.html).getText(this, tr("QInputDialog.getText()"),
                                          tr("User name:"), [QLineEdit](qlineedit.html).Normal,
                                          [QDir](qdir.html).home().dirName(), &ok);
     if (ok && !text.isEmpty())
         textLabel->setText(text);

```

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QInputDialog](qinputdialog.html)构造函数。

**See also** [getInt](qinputdialog.html#getInt)（ ）[getDouble](qinputdialog.html#getDouble)（）和[getItem](qinputdialog.html#getItem)（ ） 。

```
(QString, bool ok) QInputDialog.getText (QWidget parent, QString title, QString label, QLineEdit.EchoMode mode, QString text, Qt.WindowFlags flags, Qt.InputMethodHints inputMethodHints)
```

```
InputMode QInputDialog.inputMode (self)
```

[

```
int QInputDialog.intMaximum (self)
```

```
int QInputDialog.intMinimum (self)
```

```
int QInputDialog.intStep (self)
```

```
int QInputDialog.intValue (self)
```

```
bool QInputDialog.isComboBoxEditable (self)
```

```
QString QInputDialog.labelText (self)
```

](qinputdialog.html#InputMode-enum)

```
QSize QInputDialog.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QString QInputDialog.okButtonText (self)
```

```
QInputDialog.open (self)
```

这是一个重载函数。

此功能连接它的信号之一，由指定的插槽_receiver_和_member_。具体的信号取决于在指定的参数_member_。它们是：

*   [textValueSelected](qinputdialog.html#textValueSelected)() if _member_ has a [QString](qstring.html) for its first argument.
*   [intValueSelected](qinputdialog.html#intValueSelected)() if _member_ has an int for its first argument.
*   [doubleValueSelected](qinputdialog.html#doubleValueSelected)() if _member_ has a double for its first argument.
*   [accepted](qdialog.html#accepted)() if _member_ has NO arguments.

该信号会从插槽中断开时，关闭对话框。

此功能被引入Qt的4.5 。

```
QInputDialog.open (self, QObject receiver, SLOT()SLOT() member)
```

```
QInputDialog.open (self, callable receiver)
```

```
InputDialogOptions QInputDialog.options (self)
```

[

```
QInputDialog.setCancelButtonText (self, QString text)
```

```
QInputDialog.setComboBoxEditable (self, bool editable)
```

```
QInputDialog.setComboBoxItems (self, QStringList items)
```

```
QInputDialog.setDoubleDecimals (self, int decimals)
```

```
QInputDialog.setDoubleMaximum (self, float max)
```

```
QInputDialog.setDoubleMinimum (self, float min)
```

```
QInputDialog.setDoubleRange (self, float min, float max)
```

](index.htm)

[设置在使用时，通过该对话框接受双精度浮点值的范围](index.htm)[DoubleInput](qinputdialog.html#InputMode-enum)模式，以最小的和由规定的最大数值_min_和_max_分别。

```
QInputDialog.setDoubleValue (self, float value)
```

```
QInputDialog.setInputMode (self, InputMode mode)
```

```
QInputDialog.setIntMaximum (self, int max)
```

```
QInputDialog.setIntMinimum (self, int min)
```

```
QInputDialog.setIntRange (self, int min, int max)
```

设置在使用时，通过该对话框接受整数的值的范围[IntInput](qinputdialog.html#InputMode-enum)模式，以最小的和由规定的最大数值_min_和_max_分别。

```
QInputDialog.setIntStep (self, int step)
```

```
QInputDialog.setIntValue (self, int value)
```

```
QInputDialog.setLabelText (self, QString text)
```

```
QInputDialog.setOkButtonText (self, QString text)
```

```
QInputDialog.setOption (self, InputDialogOption option, bool on = True)
```

设置给定_option_被启用，如果_on_是真的，否则，清除给定的_option_。

**See also** [options](qinputdialog.html#options-prop)和[testOption](qinputdialog.html#testOption)（ ） 。

```
QInputDialog.setOptions (self, InputDialogOptions options)
```

```
QInputDialog.setTextEchoMode (self, QLineEdit.EchoMode mode)
```

```
QInputDialog.setTextValue (self, QString text)
```

```
QInputDialog.setVisible (self, bool visible)
```

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

```
QSize QInputDialog.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
bool QInputDialog.testOption (self, InputDialogOption option)
```

返回True如果给定的_option_被启用，否则返回False 。

**See also** [options](qinputdialog.html#options-prop)和[setOption](qinputdialog.html#setOption)（ ） 。

```
QLineEdit.EchoMode QInputDialog.textEchoMode (self)
```

[

```
QString QInputDialog.textValue (self)
```

* * *

## Qt Signal Documentation

```
void doubleValueChanged (double)
```

这是该信号的默认超载。

这个信号被发射在对话框中每当double值的变化。被指定的当前值_value_。

](qlineedit.html#EchoMode-enum)

[当被用在输入对话框这个信号是唯一的相关](qlineedit.html#EchoMode-enum)[DoubleInput](qinputdialog.html#InputMode-enum)模式。

```
void doubleValueSelected (double)
```

这是该信号的默认超载。

每当用户在接受该对话框中选择一个双精度值这个信号被发射，例如，通过点击**OK**按钮。是由指定的所选值_value_。

当被用在输入对话框这个信号是唯一的相关[DoubleInput](qinputdialog.html#InputMode-enum)模式。

```
void intValueChanged (int)
```

这是该信号的默认超载。

这个信号被发射的对话框中，每当整数值的变化。被指定的当前值_value_。

当被用在输入对话框这个信号是唯一的相关[IntInput](qinputdialog.html#InputMode-enum)模式。

```
void intValueSelected (int)
```

这是该信号的默认超载。

每当用户通过接受对话框中选择一个整数值，这个信号被发射，例如，通过点击**OK**按钮。是由指定的所选值_value_。

当被用在输入对话框这个信号是唯一的相关[IntInput](qinputdialog.html#InputMode-enum)模式。

```
void textValueChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的文本字符串的对话框中改变。由指定当前字符串_text_。

当被用在输入对话框这个信号是唯一的相关[TextInput](qinputdialog.html#InputMode-enum)模式。

```
void textValueSelected (const QString&)
```

这是该信号的默认超载。

每当用户通过接受对话框中选择一个文本字符串这个信号被发射，例如，通过点击**OK**按钮。由指定的选定字符串_text_。

当被用在输入对话框这个信号是唯一的相关[TextInput](qinputdialog.html#InputMode-enum)模式。