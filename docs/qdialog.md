# QDialog Class Reference

## [[QtGui](index.htm) module]

对了QDialog类是对话框窗口的基类。[More...](#details)

继承[QWidget](qwidget.html)。

通过继承[QAbstractPrintDialog](qabstractprintdialog.html)，[QColorDialog](qcolordialog.html)，[QErrorMessage](qerrormessage.html)，[QFileDialog](qfiledialog.html)，[QFontDialog](qfontdialog.html)，[QInputDialog](qinputdialog.html)，[QMessageBox](qmessagebox.html)，[QPageSetupDialog](qpagesetupdialog.html)，[QPrintPreviewDialog](qprintpreviewdialog.html)，[QProgressDialog](qprogressdialog.html)和[QWizard](qwizard.html)。

### Types

*   `enum DialogCode { Rejected, Accepted }`

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `accept (self)`
*   `closeEvent (self, QCloseEvent)`
*   `contextMenuEvent (self, QContextMenuEvent)`
*   `done (self, int)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `int exec_ (self)`
*   `QWidget extension (self)`
*   `bool isSizeGripEnabled (self)`
*   `keyPressEvent (self, QKeyEvent)`
*   `QSize minimumSizeHint (self)`
*   `open (self)`
*   `Qt.Orientation orientation (self)`
*   `reject (self)`
*   `resizeEvent (self, QResizeEvent)`
*   `int result (self)`
*   `setExtension (self, QWidget extension)`
*   `setModal (self, bool modal)`
*   `setOrientation (self, Qt.Orientation orientation)`
*   `setResult (self, int r)`
*   `setSizeGripEnabled (self, bool)`
*   `setVisible (self, bool visible)`
*   `showEvent (self, QShowEvent)`
*   `showExtension (self, bool)`
*   `QSize sizeHint (self)`

### Qt Signals

*   `void accepted ()`
*   `void finished (int)`
*   `void rejected ()`

* * *

## Detailed Description

对了QDialog类是对话框窗口的基类。

一个对话窗口是顶层窗口主要用于短期任务和简要沟通与用户。 QDialogs可能是模式或无模式。 QDialogs可以提供一个[return value](#return)，并且它们可以有[default buttons](#default)。 QDialogs还可以有一个[QSizeGrip](qsizegrip.html)在他们的右下角，使用[setSizeGripEnabled](qdialog.html#sizeGripEnabled-prop)（ ） 。

注意的QDialog （并具有类型的任何其它部件`Qt.Dialog`）使用父控件稍微不同于其他类的Qt 。对话始终是一个顶级窗口部件，但是如果它有父，其默认位置是集中在父母的顶层widget的顶部（如果不是顶级本身） 。它也将共享父的任务栏条目。

使用的过载[QWidget.setParent](qwidget.html#setParent)（ ）函数来改变了QDialog部件的所有权。此功能可以让您显式地设置重设父控件的窗口标志;使用重载函数将清除窗口标志指定为插件的窗口 - 系统属性（尤其是它会重置[Qt.Dialog](qt.html#WindowType-enum)标志） 。

### Modal Dialogs

A **modal**对话框是一个对话框，输入块在同一应用程序的其他可见窗口。用来向用户请求一个文件名，或者用于设置应用优选项对话框通常是模态的。对话框可以[application modal](qt.html#WindowModality-enum)（缺省值）或[window modal](qt.html#WindowModality-enum)。

当打开一个应用程序的模态对话框，用户必须完成与对话互动，并关闭它才可以访问任何其他窗口的应用程序。窗口模式对话框只阻止访问与对话相关的窗口，允许用户继续使用其他窗口的应用程序。

显示一个模式对话框的最常用的方法是调用它的[exec_](qdialog.html#exec)（）函数。当用户关闭该对话框，[exec_](qdialog.html#exec)（）将提供一个有用的[return value](#return)。通常情况下，要获得对话框关闭并返回相应的值，我们连接默认按钮，如：**OK**，到[accept](qdialog.html#accept)（ ）插槽和一个**Cancel**按钮，将[reject](qdialog.html#reject)（）槽。另外，您可以拨打[done](qdialog.html#done)（ ）插槽`Accepted` or `Rejected`。

另一种方法是调用setModal （真）或[setWindowModality](qwidget.html#windowModality-prop)（），然后[show](qwidget.html#show)（ ） 。不像[exec_](qdialog.html#exec)（ ）[show](qwidget.html#show)（ ）立即返回控制给调用者。调用setModal （真）对进度对话框，用户必须具有与对话框交互的能力，例如特别有用取消长时间运行的操作。如果你使用[show](qwidget.html#show)（）和setModal （真）一起进行长时间的操作，则必须调用[QApplication.processEvents](qcoreapplication.html#processEvents)（）周期性地在加工过程中，使用户能够与对话交互。 （见[QProgressDialog](qprogressdialog.html)。 ）

### Modeless Dialogs

A **modeless**对话框是独立的在同一个应用程序运行与其他窗口的对话框。在文字处理器中查找和替换对话框是无模式往往以允许用户同时与应用程序的主窗口和对话框进行交互。

无模式对话框显示使用[show](qwidget.html#show)（），它立即将控制返回给调用者。

如果你调用[show()](qwidget.html#show)躲在一个对话框功能后，对话框会显示在原来的位置。这是因为，窗口管理器决定的位置，但没有明确地由程序员放置窗口。为了保持已移动用户对话框的位置，保存其位置的[closeEvent()](qwidget.html#closeEvent)处理程序，然后将对话框的位置，再次显示它。

### Default Button

对话的_default_按钮是按下的，当用户按下Enter键（返回）按钮。此按钮是用来表示用户接受对话框的设置，并要关闭对话框。使用[QPushButton.setDefault](qpushbutton.html#default-prop)（ ）[QPushButton.isDefault](qpushbutton.html#default-prop)（）和[QPushButton.autoDefault](qpushbutton.html#autoDefault-prop)（ ）来设置和控制对话框中的默认按钮。

### Escape Key

如果用户按下Esc键在对话框中，[QDialog.reject](qdialog.html#reject)（ ）将被调用。这将导致窗口关闭：该[close event](qcloseevent.html)不能[ignored](qevent.html#ignore)。

### Extensibility

可扩展性是显示在对话框中两种方法的能力：一个局部对话框，显示最常用的选项，以及一个完整的对话框，显示所有选项。通常情况下一个可扩展的对话框最初显示为部分对话，但与**More**切换按钮。如果用户按下**More**按钮，对话框已展开。该[Extension Example](index.htm)展示了如何使用Qt来实现可扩展的对话框。

### Return Value (Modal Dialogs)

模态对话框通常在需要返回值的情况下，例如使用以指示用户是否按下**OK** or **Cancel**。一个对话框可以通过调用被关闭[accept](qdialog.html#accept)（）或[reject](qdialog.html#reject)（）槽，并[exec_](qdialog.html#exec)（ ）将返回`Accepted` or `Rejected`（如适用） 。该[exec_](qdialog.html#exec)（ ）调用返回对话框的结果。该结果也可从[result](qdialog.html#result)（ ）如果对话框没有被破坏。

为了修改对话框的亲密行为，您可以重新实现的功能[accept](qdialog.html#accept)（ ）[reject](qdialog.html#reject)（）或[done](qdialog.html#done)（ ） 。该[closeEvent()](qwidget.html#closeEvent)函数只应重新实现保存对话框的位置或复盖标准接近或拒绝的行为。

### Code Examples

模态对话框：

```
 void EditorWindow.countWords()
 {
     WordCountDialog dialog(this);
     dialog.setWordCount(document().wordCount());
     dialog.exec();
 }

```

无模式对话框：

```
 void EditorWindow.find()
 {
     if (!findDialog) {
         findDialog = new FindDialog(this);
         connect(findDialog, SIGNAL(findNext()), this, SLOT(findNext()));
     }

     findDialog->show();
     findDialog->raise();
     findDialog->activateWindow();
 }

```

* * *

## Type Documentation

```
QDialog.DialogCode
```

由模态对话框的返回值。

| Constant | Value |
| --- | --- |
| `QDialog.Accepted` | `1` |
| `QDialog.Rejected` | `0` |

* * *

## Method Documentation

```
QDialog.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造与家长的对话_parent_。

对话始终是一个顶级窗口部件，但是如果它有父，其默认位置是集中在母公司的顶部。它也将共享父的任务栏条目。

窗口部件标记_f_到传递[QWidget](qwidget.html)构造函数。如果，例如，你不想这是什么按钮，在对话框的标题栏，通[Qt.WindowTitleHint](qt.html#WindowType-enum)|[Qt.WindowSystemMenuHint](qt.html#WindowType-enum)在_f_。

**See also** [QWidget.setWindowFlags](qwidget.html#windowFlags-prop)（ ） 。

```
QDialog.accept (self)
```

这种方法也是一个Qt槽与C + +的签名`void accept()`。

隐藏模式对话框并且设置结果代码`Accepted`。

**See also** [reject](qdialog.html#reject)（）和[done](qdialog.html#done)（ ） 。

```
QDialog.closeEvent (self, QCloseEvent)
```

从重新实现[QWidget.closeEvent](qwidget.html#closeEvent)（ ） 。

```
QDialog.contextMenuEvent (self, QContextMenuEvent)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
QDialog.done (self, int)
```

这种方法也是一个Qt槽与C + +的签名`void done(int)`。

关闭对话框，并将其结果代码_r_。如果显示此对话框[exec_](qdialog.html#exec)（ ） ， （）完成将导致本地事件循环来完成，并[exec_](qdialog.html#exec)（ ）返回_r_。

与[QWidget.close](qwidget.html#close)（ ） ， （）完成删除的对话框，如果[Qt.WA_DeleteOnClose](qt.html#WidgetAttribute-enum)标志被设置。如果对话框是应用程序的主窗口部件，应用程序终止。如果对话框是最后一个窗口关闭后，[QApplication.lastWindowClosed](qapplication.html#lastWindowClosed)（）信号被发射。

**See also** [accept](qdialog.html#accept)（ ）[reject](qdialog.html#reject)（ ）[QApplication.activeWindow](qapplication.html#activeWindow)（）和[QApplication.quit](qcoreapplication.html#quit)（ ） 。

```
bool QDialog.eventFilter (self, QObject, QEvent)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
int QDialog.exec_ (self)
```

这种方法也是一个Qt槽与C + +的签名`int exec()`。

显示该对话框的[modal dialog](qdialog.html#modal-dialogs)，阻塞，直到用户关闭它。该函数返回一个[DialogCode](qdialog.html#DialogCode-enum)结果。

如果对话是[application modal](qt.html#WindowModality-enum)，用户不能在同一应用程序的任何其他窗口交互，直到他们关闭对话框。如果对话是[window modal](qt.html#WindowModality-enum)，只与父窗口的交互被阻塞，而对话是开放的。默认情况下，对话框是应用程序模式。

**See also** [open](qdialog.html#open)（ ）[show](qwidget.html#show)（ ）[result](qdialog.html#result)（）和[setWindowModality](qwidget.html#windowModality-prop)（ ） 。

```
QWidget QDialog.extension (self)
```

[

```
bool QDialog.isSizeGripEnabled (self)
```

```
QDialog.keyPressEvent (self, QKeyEvent)
```

](qwidget.html)

[从重新实现](qwidget.html)[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QSize QDialog.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QDialog.open (self)
```

这种方法也是一个Qt槽与C + +的签名`void open()`。

显示该对话框的[window modal dialog](qdialog.html#modal-dialogs)，立即返回。

此功能被引入Qt的4.5 。

**See also** [exec_](qdialog.html#exec)（ ）[show](qwidget.html#show)（ ）[result](qdialog.html#result)（）和[setWindowModality](qwidget.html#windowModality-prop)（ ） 。

```
Qt.Orientation QDialog.orientation (self)
```

[

```
QDialog.reject (self)
```

这种方法也是一个Qt槽与C + +的签名`void reject()`。

隐藏模式对话框并且设置结果代码`Rejected`。

](qt.html#Orientation-enum)

[**See also**](qt.html#Orientation-enum) [accept](qdialog.html#accept)（）和[done](qdialog.html#done)（ ） 。

```
QDialog.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
int QDialog.result (self)
```

一般而言返回模式对话框的结果代码，`Accepted` or `Rejected`。

**Note:**从使用时[QMessageBox](qmessagebox.html)实例结果代码类型是[QMessageBox.StandardButton](qmessagebox.html#StandardButton-enum)

不要调用此函数与构建对话[Qt.WA_DeleteOnClose](qt.html#WidgetAttribute-enum)属性。

**See also** [setResult](qdialog.html#setResult)（ ） 。

```
QDialog.setExtension (self, QWidget extension)
```

该_extension_说法有它的所有权转移给Qt的。

```
QDialog.setModal (self, bool modal)
```

```
QDialog.setOrientation (self, Qt.Orientation orientation)
```

```
QDialog.setResult (self, int r)
```

设置模式对话框的结果代码_i_。

**Note:**我们建议您通过使用定义的值之一[QDialog.DialogCode](qdialog.html#DialogCode-enum)。

**See also** [result](qdialog.html#result)（ ） 。

```
QDialog.setSizeGripEnabled (self, bool)
```

```
QDialog.setVisible (self, bool visible)
```

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

```
QDialog.showEvent (self, QShowEvent)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QDialog.showExtension (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void showExtension(bool)`。

```
QSize QDialog.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

* * *

## Qt Signal Documentation

```
void accepted ()
```

这是该信号的默认超载。

当对话框已接受由用户或通过调用这个信号被发射[accept](qdialog.html#accept)（）或[done](qdialog.html#done)（）与[QDialog.Accepted](qdialog.html#DialogCode-enum)的说法。

注意，此信号是_not_隐藏的对话框时发出[hide](qwidget.html#hide)（ ）或者其setVisible （假） 。这包括删除对话框，而它是可见的。

这个函数是Qt 4.1中引入。

**See also** [finished](qdialog.html#finished)（）和[rejected](qdialog.html#rejected)（ ） 。

```
void finished (int)
```

这是该信号的默认超载。

这个信号被发射时，对话框的_result_码已经被设置，或者由用户或通过调用[done](qdialog.html#done)（ ）[accept](qdialog.html#accept)（） ，或[reject](qdialog.html#reject)（ ） 。

注意，此信号是_not_隐藏的对话框时发出[hide](qwidget.html#hide)（ ）或者其setVisible （假） 。这包括删除对话框，而它是可见的。

这个函数是Qt 4.1中引入。

**See also** [accepted](qdialog.html#accepted)（）和[rejected](qdialog.html#rejected)（ ） 。

```
void rejected ()
```

这是该信号的默认超载。

当对话框被拒绝或者由用户或通过调用这个信号被发射[reject](qdialog.html#reject)（）或[done](qdialog.html#done)（）与[QDialog.Rejected](qdialog.html#DialogCode-enum)的说法。

注意，此信号是_not_隐藏的对话框时发出[hide](qwidget.html#hide)（ ）或者其setVisible （假） 。这包括删除对话框，而它是可见的。

这个函数是Qt 4.1中引入。

**See also** [finished](qdialog.html#finished)（）和[accepted](qdialog.html#accepted)（ ） 。