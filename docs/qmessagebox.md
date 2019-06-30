# QMessageBox Class Reference

## [[QtGui](index.htm) module]

该QMessageBox提示类提供通知用户或询问用户问题，并接收应答模式对话框。[More...](#details)

继承[QDialog](qdialog.html)。

### Types

*   `enum ButtonRole { InvalidRole, AcceptRole, RejectRole, DestructiveRole, ..., ApplyRole }`
*   `enum Icon { NoIcon, Information, Warning, Critical, Question }`
*   `enum StandardButton { NoButton, Ok, Save, SaveAll, ..., ButtonMask }`
*   `class **[StandardButtons](index.htm)**`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, Icon icon, QString title, QString text, StandardButtons buttons = QMessageBox.NoButton, QWidget parent = None, Qt.WindowFlags flags = Qt.Dialog|Qt.MSWindowsFixedSizeDialogHint)`
*   `__init__ (self, QString title, QString text, Icon icon, int button0, int button1, int button2, QWidget parent = None, Qt.WindowFlags flags = Qt.Dialog|Qt.MSWindowsFixedSizeDialogHint)`
*   `addButton (self, QAbstractButton button, ButtonRole role)`
*   `QPushButton addButton (self, QString text, ButtonRole role)`
*   `QPushButton addButton (self, StandardButton button)`
*   `QAbstractButton button (self, StandardButton which)`
*   `ButtonRole buttonRole (self, QAbstractButton button)`
*   `list-of-QAbstractButton buttons (self)`
*   `QString buttonText (self, int button)`
*   `changeEvent (self, QEvent)`
*   `QAbstractButton clickedButton (self)`
*   `closeEvent (self, QCloseEvent)`
*   `QPushButton defaultButton (self)`
*   `QString detailedText (self)`
*   `QAbstractButton escapeButton (self)`
*   `bool event (self, QEvent e)`
*   `Icon icon (self)`
*   `QPixmap iconPixmap (self)`
*   `QString informativeText (self)`
*   `keyPressEvent (self, QKeyEvent)`
*   `open (self)`
*   `open (self, QObject receiver, SLOT()SLOT() member)`
*   `open (self, callable receiver)`
*   `removeButton (self, QAbstractButton button)`
*   `resizeEvent (self, QResizeEvent)`
*   `setButtonText (self, int button, QString)`
*   `setDefaultButton (self, QPushButton button)`
*   `setDefaultButton (self, StandardButton button)`
*   `setDetailedText (self, QString text)`
*   `setEscapeButton (self, QAbstractButton button)`
*   `setEscapeButton (self, StandardButton button)`
*   `setIcon (self, Icon)`
*   `setIconPixmap (self, QPixmap)`
*   `setInformativeText (self, QString text)`
*   `setStandardButtons (self, StandardButtons buttons)`
*   `setText (self, QString)`
*   `setTextFormat (self, Qt.TextFormat)`
*   `setWindowModality (self, Qt.WindowModality windowModality)`
*   `setWindowTitle (self, QString title)`
*   `showEvent (self, QShowEvent)`
*   `QSize sizeHint (self)`
*   `StandardButton standardButton (self, QAbstractButton button)`
*   `StandardButtons standardButtons (self)`
*   `QString text (self)`
*   `Qt.TextFormat textFormat (self)`

### Static Methods

*   `about (QWidget parent, QString caption, QString text)`
*   `aboutQt (QWidget parent, QString title = QString())`
*   `StandardButton critical (QWidget parent, QString title, QString text, StandardButtons buttons = QMessageBox.Ok, StandardButton defaultButton = QMessageBox.NoButton)`
*   `int critical (QWidget parent, QString title, QString text, int button0, int button1, int button2 = 0)`
*   `int critical (QWidget parent, QString title, QString text, QString button0Text, QString button1Text = QString(), QString button2Text = QString(), int defaultButtonNumber = 0, int escapeButtonNumber = -1)`
*   `StandardButton information (QWidget parent, QString title, QString text, StandardButtons buttons = QMessageBox.Ok, StandardButton defaultButton = QMessageBox.NoButton)`
*   `int information (QWidget parent, QString title, QString text, int button0, int button1 = 0, int button2 = 0)`
*   `int information (QWidget parent, QString title, QString text, QString button0Text, QString button1Text = QString(), QString button2Text = QString(), int defaultButtonNumber = 0, int escapeButtonNumber = -1)`
*   `StandardButton question (QWidget parent, QString title, QString text, StandardButtons buttons = QMessageBox.Ok, StandardButton defaultButton = QMessageBox.NoButton)`
*   `int question (QWidget parent, QString title, QString text, int button0, int button1 = 0, int button2 = 0)`
*   `int question (QWidget parent, QString title, QString text, QString button0Text, QString button1Text = QString(), QString button2Text = QString(), int defaultButtonNumber = 0, int escapeButtonNumber = -1)`
*   `QPixmap standardIcon (Icon icon)`
*   `StandardButton warning (QWidget parent, QString title, QString text, StandardButtons buttons = QMessageBox.Ok, StandardButton defaultButton = QMessageBox.NoButton)`
*   `int warning (QWidget parent, QString title, QString text, int button0, int button1, int button2 = 0)`
*   `int warning (QWidget parent, QString title, QString text, QString button0Text, QString button1Text = QString(), QString button2Text = QString(), int defaultButtonNumber = 0, int escapeButtonNumber = -1)`

### Qt Signals

*   `void buttonClicked (QAbstractButton *)`

* * *

## Detailed Description

该QMessageBox提示类提供通知用户或询问用户问题，并接收应答模式对话框。

一个消息框显示一个主[text](qmessagebox.html#text-prop)要提醒用户的情况下，一[informative text](qmessagebox.html#informativeText-prop)进一步解释警报或询问用户问题，以及一个可选的[detailed text](qmessagebox.html#detailedText-prop)到如果用户请求它提供甚至更多的数据。一个消息框还可以显示[icon](qmessagebox.html#icon-prop)和[standard buttons](qmessagebox.html#standardButtons-prop)用于接受用户的响应。

提供两个API使用QMessageBox提示，该物业为基础的API ，和静态函数。调用的静态功能之一是简单的方法，但它比使用基于属性的API，弹性较差，其结果是不够丰富。使用基于属性的API被推荐。

### The Property-based API

使用该物业的API ，构建QMessageBox提示的实例，设置所需的属性和调用[exec_](qmessagebox.html#exec)（ ）来显示讯息。最简单的配置是仅设置[message text](qmessagebox.html#text-prop)属性。

```
 QMessageBox msgBox;
 msgBox.setText("The document has been modified.");
 msgBox.exec_();

```

用户必须点击**OK**按钮来关闭消息框。 GUI的其馀部分被阻塞，直到消息框被驳回。

![](../img/msgbox1.png)

比只是提醒用户事件更好的办法是还询问用户该怎么办才好。存储在这个问题[informative text](qmessagebox.html#informativeText-prop)属性，并设置[standard buttons](qmessagebox.html#standardButtons-prop)属性设置为你想要的设置的用户响应的组按钮。这些按钮由合并指定的值[StandardButtons](qmessagebox.html#StandardButton-enum)使用按位OR运算符。对于按钮的显示顺序是依赖于平台的。例如，在Windows上，**Save**被显示到左侧**Cancel**，而在Mac OS上，顺序是相反的。

纪念你的标准按钮之一，是你的[default button](qmessagebox.html#defaultButton)。

```
 QMessageBox msgBox;
 msgBox.setText("The document has been modified.");
 msgBox.setInformativeText("Do you want to save your changes?");
 msgBox.setStandardButtons(QMessageBox.Save | QMessageBox.Discard | QMessageBox.Cancel);
 msgBox.setDefaultButton(QMessageBox.Save);
 int ret = msgBox.exec_();

```

这是推荐的做法 [Mac OS X Guidelines](http://developer.apple.com/library/mac/documentation/UserExperience/Conceptual/AppleHIGuidelines/Windows/Windows.html#//apple_ref/doc/uid/20000961-BABCAJID)。类似的准则适用于其他平台，但要注意方式的不同[informative text](qmessagebox.html#informativeText-prop)针对不同的平台进行处理。

![](../img/msgbox2.png)

该[exec_](qmessagebox.html#exec)（）槽返回[StandardButtons](qmessagebox.html#StandardButton-enum)单击的按钮的值。

```
 switch (ret) {
   case QMessageBox.Save:
       // Save was clicked
       break;
   case QMessageBox.Discard:
       // Don't Save was clicked
       break;
   case QMessageBox.Cancel:
       // Cancel was clicked
       break;
   default:
       // should never be reached
       break;
 }

```

为了给用户更多的信息，以帮助他回答这个问题，设置[detailed text](qmessagebox.html#detailedText-prop)属性。如果[detailed text](qmessagebox.html#detailedText-prop)属性设置，**Show Details...**将显示按钮。

![](../img/msgbox3.png)

点击**Show Details...**按钮将显示详细的文字。

![](../img/msgbox4.png)

#### Rich Text and the Text Format Property

该[detailed text](qmessagebox.html#detailedText-prop)属性总是被解释为纯文本。该[main text](qmessagebox.html#text-prop)和[informative text](qmessagebox.html#informativeText-prop)性能可以是纯文本或富文本。这些字符串是根据所设定的解释[text format](qmessagebox.html#textFormat-prop)属性。默认设置为[auto-text](qt.html#TextFormat-enum)。

请注意，对于包含XML的元字符的一些纯文本字符串，自动文本[rich text detection test](qt.html#mightBeRichText)可能会失败，从而导致你的纯文本字符串被错误地解释为富文本。在这些罕见的情况下，使用[Qt.convertFromPlainText](qt.html#convertFromPlainText)（ ）到您的纯文本字符串转换为等效的视觉丰富的文本字符串，或将[text format](qmessagebox.html#textFormat-prop)属性明确与[setTextFormat](qmessagebox.html#textFormat-prop)（ ） 。

#### Severity Levels and the Icon and Pixmap Properties

QMessageBox提示支持四种预定义的消息严重级别，或消息类型，这真的只是不同的预定义的图标，他们每场演出。通过设置指定四个预定义的消息类型之一的[icon](qmessagebox.html#icon-prop)属性的一个[predefined icons](qmessagebox.html#Icon-enum)。以下规则的指导方针：

| ![](../img/qmessagebox-quest.png) | [Question](qmessagebox.html#Icon-enum) | For asking a question during normal operations. |
| ![](../img/qmessagebox-info.png) | [Information](qmessagebox.html#Icon-enum) | For reporting information about normal operations. |
| ![](../img/qmessagebox-warn.png) | [Warning](qmessagebox.html#Icon-enum) | For reporting non-critical errors. |
| ![](../img/qmessagebox-crit.png) | [Critical](qmessagebox.html#Icon-enum) | For reporting critical errors. |

[Predefined icons](qmessagebox.html#Icon-enum)不受QMessageBox提示定义的，而是由式提供。缺省值是[No Icon](qmessagebox.html#Icon-enum)。该消息框，否则相同的所有案件。当使用一个标准的图标，推荐使用表中的一个，或者使用建议您使用平台的风格准则之一。如果没有一个标准的图标是适合你的消息框，你可以通过设置使用自定义图标[icon pixmap](qmessagebox.html#iconPixmap-prop)财产，而不是设置[icon](qmessagebox.html#icon-prop)属性。

总之，要设置一个图标，用_either_ [setIcon](qmessagebox.html#icon-prop)（ ）为标准图标之一，_or_ [setIconPixmap](qmessagebox.html#iconPixmap-prop)（）为一个自定义图标。

### The Static Functions API

建立消息框与静态函数的API，虽然方便，比使用基于属性的API，弹性较差，因为静态函数签名缺少用于设置参数[informative text](qmessagebox.html#informativeText-prop)和[detailed text](qmessagebox.html#detailedText-prop)属性。一个工作围绕这一直使用`title`参数为消息框正文及`text`参数为消息框翔实的文字。因为这具有使一个不太可读的消息框的明显缺点，平台指引不建议这样做。该_Microsoft Windows User Interface Guidelines_建议使用[application name](qcoreapplication.html#applicationName-prop)作为[window's title](qmessagebox.html#setWindowTitle)，这意味着，如果你有除了你的主文本的信息文本，你必须将它连接到`text`参数。

注意，静态函数签名，相对于它们的键参数，而现在用于设置改变[standard buttons](qmessagebox.html#standardButtons-prop)和[default button](qmessagebox.html#defaultButton)。

静态函数可用于创建[information](qmessagebox.html#information)（ ）[question](qmessagebox.html#question)（ ）[warning](qmessagebox.html#warning)（）和[critical](qmessagebox.html#critical)（ ）消息框。

```
 int ret = QMessageBox.warning(this, tr("My Application"),
                                tr("The document has been modified.\n"
                                   "Do you want to save your changes?"),
                                QMessageBox.Save | QMessageBox.Discard
                                | QMessageBox.Cancel,
                                QMessageBox.Save);

```

该[Standard Dialogs](index.htm)示例显示了如何使用QMessageBox提示和其他内置Qt对话框。

### Advanced Usage

如果[standard buttons](qmessagebox.html#StandardButton-enum)不够灵活，你的消息框，您可以使用[addButton](qmessagebox.html#addButton)（ ）过载，需要一个文本和一个ButtonRoleto添加自定义按钮。该[ButtonRole](qmessagebox.html#ButtonRole-enum)所使用QMessageBox提示来确定屏幕上的按钮的顺序（它根据平台而异）。您可以测试的价值[clickedButton](qmessagebox.html#clickedButton)（ ）调用后[exec_](qmessagebox.html#exec)（ ） 。例如，

```
 QMessageBox msgBox;
 [QPushButton](qpushbutton.html) *connectButton = msgBox.addButton(tr("Connect"), QMessageBox.ActionRole);
 [QPushButton](qpushbutton.html) *abortButton = msgBox.addButton(QMessageBox.Abort);

 msgBox.exec_();

 if (msgBox.clickedButton() == connectButton) {
     // connect
 } else if (msgBox.clickedButton() == abortButton) {
     // abort
 }

```

### Default and Escape Keys

默认按钮（即按钮激活时，**Enter**被按下）可以使用被指定[setDefaultButton](qmessagebox.html#setDefaultButton)（ ） 。如果没有指定一个缺省按钮， QMessageBox提示试图找到一个基于所述[button roles](qmessagebox.html#ButtonRole-enum)在消息框中使用的按钮。

逃生按钮（按钮激活时，**Esc**被按下）可以使用被指定[setEscapeButton](qmessagebox.html#setEscapeButton)（ ） 。如果未指定逃跑按钮， QMessageBox提示尝试使用这些规则，以找到一个：

1.  如果只有一个按钮，它是激活的按钮时**Esc**被按下。
2.  如果有一个[Cancel](qmessagebox.html#StandardButton-enum)按钮，它是激活按钮时**Esc**被按下。
3.  如果恰好有一个按钮有两种[the Reject role](qmessagebox.html#ButtonRole-enum)或[the No role](qmessagebox.html#ButtonRole-enum)，它是在按钮被激活时**Esc**被按下。

当不能使用这些规则，按确定的逃生按钮**Esc**没有任何影响。

* * *

## Type Documentation

```
QMessageBox.ButtonRole
```

该枚举描述了可用于描述按键在按钮框的作用。这些角色的组合作为标志用来形容他们的行为的不同方面。

| Constant | Value | Description |
| --- | --- | --- |
| `QMessageBox.InvalidRole` | `-1` | 该按钮是无效的。 |
| `QMessageBox.AcceptRole` | `0` | 单击该按钮被接受的对话框（如确定）。 |
| `QMessageBox.RejectRole` | `1` | 单击该按钮会导致被拒绝的对话框（例如取消） 。 |
| `QMessageBox.DestructiveRole` | `2` | 单击该按钮会导致破坏性的变化（例如，用于舍弃变更） ，然后关闭对话框。 |
| `QMessageBox.ActionRole` | `3` | 单击该按钮使更改对话框中的元素。 |
| `QMessageBox.HelpRole` | `4` | 该按钮可点击，请求帮助。 |
| `QMessageBox.YesRole` | `5` | 该按钮是一个“是”形按钮。 |
| `QMessageBox.NoRole` | `6` | 该按钮是一个“无”形按钮。 |
| `QMessageBox.ApplyRole` | `8` | 按钮适用电流的变化。 |
| `QMessageBox.ResetRole` | `7` | 按钮重置对话框的字段默认值。 |

**See also** [StandardButton](qmessagebox.html#StandardButton-enum)。

```
QMessageBox.Icon
```

该枚举具有下列值：

| Constant | Value | Description |
| --- | --- | --- |
| `QMessageBox.NoIcon` | `0` | 消息框没有任何图标。 |
| `QMessageBox.Question` | `4` | 一个图标表明该消息是问一个问题。 |
| `QMessageBox.Information` | `1` | 一个图标，表示该消息是没有什么两样的。 |
| `QMessageBox.Warning` | `2` | 一个图标指示该消息是一个警告，但也可以处理。 |
| `QMessageBox.Critical` | `3` | 一个图标指示该消息表示一个严重的问题。 |

```
QMessageBox.StandardButton
```

这些枚举描述了标准按钮标志。每个按钮都有一个定义[ButtonRole](qmessagebox.html#ButtonRole-enum)。

| Constant | Value | Description |
| --- | --- | --- |
| `QMessageBox.Ok` | `0x00000400` | 与定义的一个“OK”按钮[AcceptRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Open` | `0x00002000` | 与定义的“打开”按钮[AcceptRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Save` | `0x00000800` | 与定义的“保存”按钮[AcceptRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Cancel` | `0x00400000` | “取消”的按钮定义[RejectRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Close` | `0x00200000` | 与定义的“关闭”按钮[RejectRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Discard` | `0x00800000` | A“放弃”或“不保存”按钮，根据不同的平台上，与定义[DestructiveRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Apply` | `0x02000000` | 一个“应用”的定义的按钮[ApplyRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Reset` | `0x04000000` | “复位”的定义的按钮[ResetRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.RestoreDefaults` | `0x08000000` | A“还原为默认值”的定义的按钮[ResetRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Help` | `0x01000000` | 与定义的“帮助”按钮[HelpRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.SaveAll` | `0x00001000` | 与定义的“全部保存”按钮[AcceptRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Yes` | `0x00004000` | 与定义的“Yes”按钮[YesRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.YesToAll` | `0x00008000` | 与定义的“全是”按钮[YesRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.No` | `0x00010000` | 与定义的“否”按钮[NoRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.NoToAll` | `0x00020000` | 与定义的“全否”按钮[NoRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Abort` | `0x00040000` | 与定义的“中止”按钮[RejectRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Retry` | `0x00080000` | 与定义的“重试”按钮[AcceptRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.Ignore` | `0x00100000` | 一个“忽略”的定义的按钮[AcceptRole](qmessagebox.html#ButtonRole-enum)。 |
| `QMessageBox.NoButton` | `0x00000000` | 无效的按钮。 |

下面的值已过时：

| Constant | Value | Description |
| --- | --- | --- |
| `QMessageBox.YesAll` | `YesToAll` | 使用YesToAll代替。 |
| `QMessageBox.NoAll` | `NoToAll` | 改用NoToAll 。 |
| `QMessageBox.Default` | `0x00000100` | 使用`defaultButton`的说法[information](qmessagebox.html#information)（ ）[warning](qmessagebox.html#warning)（ ）等来代替，或致电[setDefaultButton](qmessagebox.html#setDefaultButton)（ ） 。 |
| `QMessageBox.Escape` | `0x00000200` | Call [setEscapeButton](qmessagebox.html#setEscapeButton)（ ）来代替。 |
| `QMessageBox.FlagMask` | `0x00000300` |   |
| `QMessageBox.ButtonMask` | `~FlagMask` |   |

这个枚举被引入或修改的Qt 4.2 。

该StandardButtons类型是一个typedef为[QFlags](index.htm)\u003cStandardButton\u003e 。它存储StandardButton值的或组合。

**See also** [ButtonRole](qmessagebox.html#ButtonRole-enum)和[standardButtons](qmessagebox.html#standardButtons-prop)。

* * *

## Method Documentation

```
QMessageBox.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个消息框，没有文字，没有任何按键。_parent_被传递到[QDialog](qdialog.html)构造函数。

在Mac OS X ，如果你希望你的消息框显示为[Qt.Sheet](qt.html#WindowType-enum)其_parent_，设置消息框的[window modality](qmessagebox.html#setWindowModality)至[Qt.WindowModal](qt.html#WindowModality-enum)或者使用[open](qmessagebox.html#open)（ ） 。否则，消息框将是一个标准的对话框。

```
QMessageBox.__init__ (self, Icon icon, QString title, QString text, StandardButtons buttons = QMessageBox.NoButton, QWidget parent = None, Qt.WindowFlags flags = Qt.Dialog|Qt.MSWindowsFixedSizeDialogHint)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个消息框，用给定的_icon_，_title_，_text_和标准_buttons_。标准或自定义按钮可以在任何时候使用加[addButton](qmessagebox.html#addButton)（ ） 。该_parent_和_f_参数被传递到[QDialog](qdialog.html)构造函数。

该消息框是一个[application modal](qt.html#WindowModality-enum)对话框。

在Mac OS X中，如果_parent_不为0 ，你希望你的消息框显示为[Qt.Sheet](qt.html#WindowType-enum)该父，设置消息框的[window modality](qmessagebox.html#setWindowModality)至[Qt.WindowModal](qt.html#WindowModality-enum)（默认值） 。否则，消息框将是一个标准的对话框。

**See also** [setWindowTitle](qmessagebox.html#setWindowTitle)（ ）[setText](qmessagebox.html#text-prop)（ ）[setIcon](qmessagebox.html#icon-prop)（）和[setStandardButtons](qmessagebox.html#standardButtons-prop)（ ） 。

```
QMessageBox.__init__ (self, QString title, QString text, Icon icon, int button0, int button1, int button2, QWidget parent = None, Qt.WindowFlags flags = Qt.Dialog|Qt.MSWindowsFixedSizeDialogHint)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
QMessageBox.about (QWidget parent, QString caption, QString text)
```

显示一个简单的关于与标题框_title_和文本_text_。关于对话框的父_parent_。

关于（ ）会在四个地点合适的图标：

1.  它喜欢[parent-&gt;icon()](qwidget.html#windowIcon-prop)如果存在。
2.  如果不是，它会尝试包含顶级窗口部件_parent_。
3.  如果失败，它会尝试[active window.](qapplication.html#activeWindow)
4.  作为最后的手段，它使用的信息图标。

关于对话框上有标注为“确定”的单一按钮。在Mac OS X中，关于对话框弹出时为无模式窗口，在其他平台上，它是目前应用程序模式。

**See also** [QWidget.windowIcon](qwidget.html#windowIcon-prop)（）和[QApplication.activeWindow](qapplication.html#activeWindow)（ ） 。

```
QMessageBox.aboutQt (QWidget parent, QString title = QString())
```

显示关于Qt的一个简单的消息框，用给定的_title_并集中在_parent_（如果_parent_不为0 ） 。该消息包括对Qt的正在使用的应用程序的版本号。

这是纳入有用**Help**一个应用程序的菜单，如图中[Menus](index.htm)例子。

[QApplication](qapplication.html)提供此功能的插槽。

在Mac OS X中，关于对话框弹出时为无模式窗口，在其他平台上，它是目前应用程序模式。

**See also** [QApplication.aboutQt](qapplication.html#aboutQt)（ ） 。

```
QMessageBox.addButton (self, QAbstractButton button, ButtonRole role)
```

该_button_说法有它的所有权转移给Qt的。

将给定_button_与指定的消息框_role_。

这个函数中引入了Qt 4.2中。

**See also** [removeButton](qmessagebox.html#removeButton)（ ）[button](qmessagebox.html#button)（）和[setStandardButtons](qmessagebox.html#standardButtons-prop)（ ） 。

```
QPushButton QMessageBox.addButton (self, QString text, ButtonRole role)
```

[

这是一个重载函数。

创建一个按钮，用给定的_text_，把它添加到指定的消息框_role_，并将其返回。

这个函数中引入了Qt 4.2中。

](qpushbutton.html)

```
QPushButton QMessageBox.addButton (self, StandardButton button)
```

[

这是一个重载函数。

增加了一个标准_button_到消息框，如果它是有效的话，返回按钮。

这个函数中引入了Qt 4.2中。

](qpushbutton.html)

[**See also**](qpushbutton.html) [setStandardButtons](qmessagebox.html#standardButtons-prop)（ ） 。

```
QAbstractButton QMessageBox.button (self, StandardButton which)
```

[

返回对应于标准按钮的指针_which_，或者0，如果标准按钮不能在此消息框存在。

这个函数中引入了Qt 4.2中。

](qabstractbutton.html)

[**See also**](qabstractbutton.html) [standardButtons](qmessagebox.html#standardButtons-prop)和[standardButton](qmessagebox.html#standardButton)（ ） 。

```
ButtonRole QMessageBox.buttonRole (self, QAbstractButton button)
```

[](qmessagebox.html#ButtonRole-enum)

[返回指定按钮的作用_button_。这个函数返回](qmessagebox.html#ButtonRole-enum)[InvalidRole](qmessagebox.html#ButtonRole-enum)如果_button_为0或还没有被添加到消息框。

此功能被引入Qt的4.5 。

**See also** [buttons](qmessagebox.html#buttons)（）和[addButton](qmessagebox.html#addButton)（ ） 。

```
list-of-QAbstractButton QMessageBox.buttons (self)
```

返回所有已添加到消息框按钮的列表。

此功能被引入Qt的4.5 。

**See also** [buttonRole](qmessagebox.html#buttonRole)（ ）[addButton](qmessagebox.html#addButton)（）和[removeButton](qmessagebox.html#removeButton)（ ） 。

```
QString QMessageBox.buttonText (self, int button)
```

```
QMessageBox.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QAbstractButton QMessageBox.clickedButton (self)
```

[](qabstractbutton.html)

[返回由用户，或0点击，如果用户击中按钮**Esc**键和无](qabstractbutton.html)[escape button](qmessagebox.html#setEscapeButton)设置。

If [exec_](qmessagebox.html#exec)（ ）没有被调用尚未返回0。

例如：

```
 [QMessageBox](qmessagebox.html) messageBox(this);
 [QAbstractButton](qabstractbutton.html) *disconnectButton =
       messageBox.addButton(tr("Disconnect"), [QMessageBox](qmessagebox.html).ActionRole);
 ...
 messageBox.exec_();
 if (messageBox.clickedButton() == disconnectButton) {
     ...
 }

```

这个函数中引入了Qt 4.2中。

**See also** [standardButton](qmessagebox.html#standardButton)（）和[button](qmessagebox.html#button)（ ） 。

```
QMessageBox.closeEvent (self, QCloseEvent)
```

从重新实现[QWidget.closeEvent](qwidget.html#closeEvent)（ ） 。

```
StandardButton QMessageBox.critical (QWidget parent, QString title, QString text, StandardButtons buttons = QMessageBox.Ok, StandardButton defaultButton = QMessageBox.NoButton)
```

[

打开一个重要的消息框，用给定的_title_和_text_在指定的前_parent_小工具。

](qmessagebox.html#StandardButton-enum)

[标准_buttons_添加到消息框。_defaultButton_指定用于当按钮**Enter**被按下。_defaultButton_必须提及的是在给定的一个按钮_buttons_。如果_defaultButton_ is](qmessagebox.html#StandardButton-enum) [QMessageBox.NoButton](qmessagebox.html#StandardButton-enum)，[QMessageBox](qmessagebox.html)自动选择一个合适的默认值。

返回被点击的标准按钮的标识。如果**Esc**被按下而，[escape button](qmessagebox.html#default-and-escape-keys)返回。

该消息框是一个[application modal](qt.html#WindowModality-enum)对话框。

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QMessageBox](qmessagebox.html)构造函数。

这个函数中引入了Qt 4.2中。

**See also** [question](qmessagebox.html#question)（ ）[warning](qmessagebox.html#warning)（）和[information](qmessagebox.html#information)（ ） 。

```
int QMessageBox.critical (QWidget parent, QString title, QString text, int button0, int button1, int button2 = 0)
```

```
int QMessageBox.critical (QWidget parent, QString title, QString text, QString button0Text, QString button1Text = QString(), QString button2Text = QString(), int defaultButtonNumber = 0, int escapeButtonNumber = -1)
```

```
QPushButton QMessageBox.defaultButton (self)
```

[](qpushbutton.html)

[返回按钮应该是这样的消息框的](qpushbutton.html)[default button](qpushbutton.html#default-prop)。返回0，如果是没有设置默认按钮。

这个函数中引入了Qt 4.2中。

**See also** [setDefaultButton](qmessagebox.html#setDefaultButton)（ ）[addButton](qmessagebox.html#addButton)（）和[QPushButton.setDefault](qpushbutton.html#default-prop)（ ） 。

```
QString QMessageBox.detailedText (self)
```

```
QAbstractButton QMessageBox.escapeButton (self)
```

[

返回逃跑时被按下了启动按钮。

](qabstractbutton.html)

[默认情况下，](qabstractbutton.html)[QMessageBox](qmessagebox.html)尝试自动检测逃生按钮，如下所示：

1.  如果只有一个键，它是由逸出按钮。
2.  如果有一个[Cancel](qmessagebox.html#StandardButton-enum)按钮，它是由退出按钮。
3.  在Mac OS X只，如果恰好有一个按钮的作用[QMessageBox.RejectRole](qmessagebox.html#ButtonRole-enum)，它是由退出按钮。

如果不能自动检测到一个转义按钮，按下**Esc**没有任何影响。

这个函数中引入了Qt 4.2中。

**See also** [setEscapeButton](qmessagebox.html#setEscapeButton)（）和[addButton](qmessagebox.html#addButton)（ ） 。

```
bool QMessageBox.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
Icon QMessageBox.icon (self)
```

[](qmessagebox.html#Icon-enum)

```
QPixmap QMessageBox.iconPixmap (self)
```

[](qpixmap.html)

```
StandardButton QMessageBox.information (QWidget parent, QString title, QString text, StandardButtons buttons = QMessageBox.Ok, StandardButton defaultButton = QMessageBox.NoButton)
```

[

打开一个信息的消息框与给定_title_和_text_在指定的前_parent_小工具。

](qmessagebox.html#StandardButton-enum)

[标准_buttons_添加到消息框。_defaultButton_指定用于当按钮**Enter**被按下。_defaultButton_必须提及的是在给定的一个按钮_buttons_。如果_defaultButton_ is](qmessagebox.html#StandardButton-enum) [QMessageBox.NoButton](qmessagebox.html#StandardButton-enum)，[QMessageBox](qmessagebox.html)自动选择一个合适的默认值。

返回被点击的标准按钮的标识。如果**Esc**被按下而，[escape button](qmessagebox.html#default-and-escape-keys)返回。

该消息框是一个[application modal](qt.html#WindowModality-enum)对话框。

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QMessageBox](qmessagebox.html)构造函数。

这个函数中引入了Qt 4.2中。

**See also** [question](qmessagebox.html#question)（ ）[warning](qmessagebox.html#warning)（）和[critical](qmessagebox.html#critical)（ ） 。

```
int QMessageBox.information (QWidget parent, QString title, QString text, int button0, int button1 = 0, int button2 = 0)
```

```
int QMessageBox.information (QWidget parent, QString title, QString text, QString button0Text, QString button1Text = QString(), QString button2Text = QString(), int defaultButtonNumber = 0, int escapeButtonNumber = -1)
```

```
QString QMessageBox.informativeText (self)
```

```
QMessageBox.keyPressEvent (self, QKeyEvent)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QMessageBox.open (self)
```

这是一个重载函数。

在打开的对话框并连接其[finished](qdialog.html#finished)（）或[buttonClicked](qmessagebox.html#buttonClicked)（）信号到由指定的槽_receiver_和_member_。如果在槽_member_有一个指针，它的第一个参数的连接是[buttonClicked](qmessagebox.html#buttonClicked)（ ），否则该连接是[finished](qdialog.html#finished)（ ） 。

该信号会从插槽中断开时，关闭对话框。

```
QMessageBox.open (self, QObject receiver, SLOT()SLOT() member)
```

```
QMessageBox.open (self, callable receiver)
```

```
StandardButton QMessageBox.question (QWidget parent, QString title, QString text, StandardButtons buttons = QMessageBox.Ok, StandardButton defaultButton = QMessageBox.NoButton)
```

[

打开一个疑问消息框，用给定的_title_和_text_在指定的前_parent_小工具。

](qmessagebox.html#StandardButton-enum)

[标准_buttons_添加到消息框。_defaultButton_指定用于当按钮**Enter**被按下。_defaultButton_必须提及的是在给定的一个按钮_buttons_。如果_defaultButton_ is](qmessagebox.html#StandardButton-enum) [QMessageBox.NoButton](qmessagebox.html#StandardButton-enum)，[QMessageBox](qmessagebox.html)自动选择一个合适的默认值。

返回被点击的标准按钮的标识。如果**Esc**被按下而，[escape button](qmessagebox.html#default-and-escape-keys)返回。

该消息框是一个[application modal](qt.html#WindowModality-enum)对话框。

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QMessageBox](qmessagebox.html)构造函数。

这个函数中引入了Qt 4.2中。

**See also** [information](qmessagebox.html#information)（ ）[warning](qmessagebox.html#warning)（）和[critical](qmessagebox.html#critical)（ ） 。

```
int QMessageBox.question (QWidget parent, QString title, QString text, int button0, int button1 = 0, int button2 = 0)
```

```
int QMessageBox.question (QWidget parent, QString title, QString text, QString button0Text, QString button1Text = QString(), QString button2Text = QString(), int defaultButtonNumber = 0, int escapeButtonNumber = -1)
```

```
QMessageBox.removeButton (self, QAbstractButton button)
```

该_button_争论

移除_button_从而不删除它的按钮盒。

这个函数中引入了Qt 4.2中。

**See also** [addButton](qmessagebox.html#addButton)（）和[setStandardButtons](qmessagebox.html#standardButtons-prop)（ ） 。

```
QMessageBox.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QMessageBox.setButtonText (self, int button, QString)
```

```
QMessageBox.setDefaultButton (self, QPushButton button)
```

设置消息框的[default button](qpushbutton.html#default-prop)至_button_。

这个函数中引入了Qt 4.2中。

**See also** [defaultButton](qmessagebox.html#defaultButton)（ ）[addButton](qmessagebox.html#addButton)（）和[QPushButton.setDefault](qpushbutton.html#default-prop)（ ） 。

```
QMessageBox.setDefaultButton (self, StandardButton button)
```

设置消息框的[default button](qpushbutton.html#default-prop)至_button_。

此功能被引入Qt的4.3 。

**See also** [addButton](qmessagebox.html#addButton)（）和[QPushButton.setDefault](qpushbutton.html#default-prop)（ ） 。

```
QMessageBox.setDetailedText (self, QString text)
```

```
QMessageBox.setEscapeButton (self, QAbstractButton button)
```

设置被激活​​按钮时**Escape**键被按下_button_。

这个函数中引入了Qt 4.2中。

**See also** [escapeButton](qmessagebox.html#escapeButton)（ ）[addButton](qmessagebox.html#addButton)（）和[clickedButton](qmessagebox.html#clickedButton)（ ） 。

```
QMessageBox.setEscapeButton (self, StandardButton button)
```

设置被激活​​的按钮时，**Escape**键被按下_button_。

此功能被引入Qt的4.3 。

**See also** [addButton](qmessagebox.html#addButton)（）和[clickedButton](qmessagebox.html#clickedButton)（ ） 。

```
QMessageBox.setIcon (self, Icon)
```

```
QMessageBox.setIconPixmap (self, QPixmap)
```

```
QMessageBox.setInformativeText (self, QString text)
```

```
QMessageBox.setStandardButtons (self, StandardButtons buttons)
```

```
QMessageBox.setText (self, QString)
```

```
QMessageBox.setTextFormat (self, Qt.TextFormat)
```

```
QMessageBox.setWindowModality (self, Qt.WindowModality windowModality)
```

该功能的阴影[QWidget.setWindowModality](qwidget.html#windowModality-prop)（ ） 。

设置消息框的样式，以_windowModality_。

在Mac OS X中，如果模式设置为[Qt.WindowModal](qt.html#WindowModality-enum)并且该消息框有父，则消息框将是一个[Qt.Sheet](qt.html#WindowType-enum)，否则，消息框将是一个标准的对话框。

这个函数中引入了Qt 4.2中。

```
QMessageBox.setWindowTitle (self, QString title)
```

该功能的阴影[QWidget.setWindowTitle](qwidget.html#windowTitle-prop)（ ） 。

设置消息框的标题_title_。在Mac OS X ，窗口标题将被忽略（如需要Mac OS X的指引） 。

这个函数中引入了Qt 4.2中。

```
QMessageBox.showEvent (self, QShowEvent)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QSize QMessageBox.sizeHint (self)
```

[](qsize.html)

```
StandardButton QMessageBox.standardButton (self, QAbstractButton button)
```

[](qmessagebox.html#StandardButton-enum)

[返回对应于给定的标准按钮枚举值_button_或](qmessagebox.html#StandardButton-enum)[NoButton](qmessagebox.html#StandardButton-enum)如果给定的_button_不是一个标准的按钮。

这个函数中引入了Qt 4.2中。

**See also** [button](qmessagebox.html#button)（）和[standardButtons](qmessagebox.html#standardButtons-prop)（ ） 。

```
StandardButtons QMessageBox.standardButtons (self)
```

[](index.htm)

```
QPixmap QMessageBox.standardIcon (Icon icon)
```

[

```
QString QMessageBox.text (self)
```

](qpixmap.html)

```
Qt.TextFormat QMessageBox.textFormat (self)
```

[](qt.html#TextFormat-enum)

```
StandardButton QMessageBox.warning (QWidget parent, QString title, QString text, StandardButtons buttons = QMessageBox.Ok, StandardButton defaultButton = QMessageBox.NoButton)
```

[

打开一个警告消息框与给定_title_和_text_在指定的前_parent_小工具。

](qmessagebox.html#StandardButton-enum)

[标准_buttons_添加到消息框。_defaultButton_指定用于当按钮**Enter**被按下。_defaultButton_必须提及的是在给定的一个按钮_buttons_。如果_defaultButton_ is](qmessagebox.html#StandardButton-enum) [QMessageBox.NoButton](qmessagebox.html#StandardButton-enum)，[QMessageBox](qmessagebox.html)自动选择一个合适的默认值。

返回被点击的标准按钮的标识。如果**Esc**被按下而，[escape button](qmessagebox.html#default-and-escape-keys)返回。

该消息框是一个[application modal](qt.html#WindowModality-enum)对话框。

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QMessageBox](qmessagebox.html)构造函数。

这个函数中引入了Qt 4.2中。

**See also** [question](qmessagebox.html#question)（ ）[information](qmessagebox.html#information)（）和[critical](qmessagebox.html#critical)（ ） 。

```
int QMessageBox.warning (QWidget parent, QString title, QString text, int button0, int button1, int button2 = 0)
```

```
int QMessageBox.warning (QWidget parent, QString title, QString text, QString button0Text, QString button1Text = QString(), QString button2Text = QString(), int defaultButtonNumber = 0, int escapeButtonNumber = -1)
```

* * *

## Qt Signal Documentation

```
void buttonClicked (QAbstractButton *)
```

这是该信号的默认超载。

每当一个按钮被点击里面的这个信号被发射[QMessageBox](qmessagebox.html)。被点击在返回的按钮_button_。