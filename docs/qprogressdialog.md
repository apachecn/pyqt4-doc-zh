# QProgressDialog Class Reference

## [[QtGui](index.htm) module]

该QProgressDialog类提供了一个缓慢的操作进度的反馈。[More...](#details)

继承[QDialog](qdialog.html)。

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `__init__ (self, QString labelText, QString cancelButtonText, int minimum, int maximum, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `bool autoClose (self)`
*   `bool autoReset (self)`
*   `cancel (self)`
*   `changeEvent (self, QEvent)`
*   `closeEvent (self, QCloseEvent)`
*   `forceShow (self)`
*   `QString labelText (self)`
*   `int maximum (self)`
*   `int minimum (self)`
*   `int minimumDuration (self)`
*   `open (self)`
*   `open (self, QObject receiver, SLOT()SLOT() member)`
*   `open (self, callable receiver)`
*   `reset (self)`
*   `resizeEvent (self, QResizeEvent)`
*   `setAutoClose (self, bool b)`
*   `setAutoReset (self, bool b)`
*   `setBar (self, QProgressBar bar)`
*   `setCancelButton (self, QPushButton button)`
*   `setCancelButtonText (self, QString)`
*   `setLabel (self, QLabel label)`
*   `setLabelText (self, QString)`
*   `setMaximum (self, int maximum)`
*   `setMinimum (self, int minimum)`
*   `setMinimumDuration (self, int ms)`
*   `setRange (self, int minimum, int maximum)`
*   `setValue (self, int progress)`
*   `showEvent (self, QShowEvent e)`
*   `QSize sizeHint (self)`
*   `int value (self)`
*   `bool wasCanceled (self)`

### Qt Signals

*   `void canceled ()`

* * *

## Detailed Description

该QProgressDialog类提供了一个缓慢的操作进度的反馈。

使用进度对话框，让用户多长时间的操作是要采取一个指示，并证明该应用程序并没有被冻结。它也可以让用户有机会中止操作。

一个常见的问题与进度对话框是，它是很难知道什么时候使用它们;操作需要不同的时间在不同的硬件。 QProgressDialog提供了一个解决这个问题：它估计当时的操作将（基于时间的步骤） ，并只显示本身，如果这一估计是超越[minimumDuration](qprogressdialog.html#minimumDuration-prop)（ ） （4秒默认情况下） 。

使用[setMinimum](qprogressdialog.html#minimum-prop)（）和[setMaximum](qprogressdialog.html#maximum-prop)（ ）或构造函数来设置的“台阶”的数量在操作和调用[setValue](qprogressdialog.html#value-prop)（）作为操作进行。步数可以任意选择。它可以被复制的文件的个数，接收到的字节数，通过您的算法的主循环中，或一些其它合适的单元的迭代次数。进展开始于所设定的值[setMinimum](qprogressdialog.html#minimum-prop)（ ） ，和进度对话框显示，当你调用操作已完成[setValue](qprogressdialog.html#value-prop)（ ）与设定的值[setMaximum](qprogressdialog.html#maximum-prop)（ ）作为它的参数。

该对话框会自动复位，并在手术结束隐藏自身。使用[setAutoReset](qprogressdialog.html#autoReset-prop)（）和[setAutoClose](qprogressdialog.html#autoClose-prop)（）来更改此行为。请注意，如果您设置了新的最大值（使用[setMaximum](qprogressdialog.html#maximum-prop)（）或[setRange](qprogressdialog.html#setRange)（ ） ） ，等于您当前[value](qprogressdialog.html#value-prop)（ ） ，该对话框不会关闭不管。

有使用QProgressDialog的方式有两种：模式和无模式。

相对于无模式QProgressDialog ，模态QProgressDialog更容易使用的程序员。做的操作在一个循环中，调用[setValue](qprogressdialog.html#value-prop)（ ）间隔，并检查与取消[wasCanceled](qprogressdialog.html#wasCanceled-prop)（ ） 。例如：

```
     QProgressDialog progress("Copying files...", "Abort Copy", 0, numFiles, this);
     progress.setWindowModality([Qt](qt.html).WindowModal);

     for (int i = 0; i < numFiles; i++) {
         progress.setValue(i);

         if (progress.wasCanceled())
             break;
         //... copy one file
     }
     progress.setValue(numFiles);

```

无模式进度对话框是适用于那些发生在后台，用户能够与应用程序交互操作。这种操作通常是基于[QTimer](qtimer.html)（或[QObject.timerEvent](qobject.html#timerEvent)（）），[QSocketNotifier](qsocketnotifier.html)或[QUrlOperator](index.htm#qurloperator);或在单独的线程执行。一[QProgressBar](qprogressbar.html)在主窗口的状态栏往往是一种替代一个无模式进度对话框。

你必须要运行一个事件循环，连接[canceled](qprogressdialog.html#canceled)（）信号到一个槽，停止的操作，并且呼叫[setValue](qprogressdialog.html#value-prop)（ ）间隔。例如：

```
 // Operation constructor
 Operation.Operation([QObject](qobject.html) *parent)
     : [QObject](qobject.html)(parent), steps(0)
 {
     pd = new QProgressDialog("Operation in progress.", "Cancel", 0, 100);
     connect(pd, SIGNAL(canceled()), this, SLOT(cancel()));
     t = new [QTimer](qtimer.html)(this);
     connect(t, SIGNAL(timeout()), this, SLOT(perform()));
     t->start(0);
 }

 void Operation.perform()
 {
     pd->setValue(steps);
     //... perform one percent of the operation
     steps++;
     if (steps > pd->maximum())
         t->stop();
 }

 void Operation.cancel()
 {
     t->stop();
     //... cleanup
 }

```

在这两种模式的进度对话框可以通过使用自定义小部件更换子部件进行定制[setLabel](qprogressdialog.html#setLabel)（ ）[setBar](qprogressdialog.html#setBar)（）和[setCancelButton](qprogressdialog.html#setCancelButton)（ ） 。该功能[setLabelText](qprogressdialog.html#labelText-prop)（）和[setCancelButtonText](qprogressdialog.html#setCancelButtonText)（ ）设置显示的文本。

![A progress dialog shown in the Plastique widget style.](../img/plastique-progressdialog.png)

* * *

## Method Documentation

```
QProgressDialog.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个进度对话框。

默认设置：

*   The label text is empty.
*   The cancel button text is (translated) "Cancel".
*   minimum is 0;
*   maximum is 100

该_parent_参数是对话框的父控件。窗口部件标记，_f_，被传递到[QDialog.QDialog](qdialog.html#QDialog)（ ）构造函数。

**See also** [setLabelText](qprogressdialog.html#labelText-prop)（ ）[setCancelButtonText](qprogressdialog.html#setCancelButtonText)（ ）[setCancelButton](qprogressdialog.html#setCancelButton)（ ）[setMinimum](qprogressdialog.html#minimum-prop)（）和[setMaximum](qprogressdialog.html#maximum-prop)（ ） 。

```
QProgressDialog.__init__ (self, QString labelText, QString cancelButtonText, int minimum, int maximum, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个进度对话框。

该_labelText_是用来提醒什么进展了用户的文本。

该_cancelButtonText_是上显示了取消按钮的文本。如果的QString （）传递则不会取消显示按钮。

该_minimum_和_maximum_是在步凡本进度对话框显示正在进行的操作数。例如，如果操作是检查50个文件，则该值的最小值是0 ，最大值是50 。在检查的第一个文件，调用的setValue （ 0 ） 。当每个文件处理调用setValue方法（ 1 ） ， setValue方法（ 2 ）等，检查的最后一个文件后，终于调用setValue方法（ 50 ） 。

该_parent_参数是对话框的父窗口部件。父，_parent_和窗口部件标记，_f_，被传递到[QDialog.QDialog](qdialog.html#QDialog)（ ）构造函数。

**See also** [setLabelText](qprogressdialog.html#labelText-prop)（ ）[setLabel](qprogressdialog.html#setLabel)（ ）[setCancelButtonText](qprogressdialog.html#setCancelButtonText)（ ）[setCancelButton](qprogressdialog.html#setCancelButton)（ ）[setMinimum](qprogressdialog.html#minimum-prop)（）和[setMaximum](qprogressdialog.html#maximum-prop)（ ） 。

```
bool QProgressDialog.autoClose (self)
```

```
bool QProgressDialog.autoReset (self)
```

```
QProgressDialog.cancel (self)
```

这种方法也是一个Qt槽与C + +的签名`void cancel()`。

重置进度对话框。[wasCanceled](qprogressdialog.html#wasCanceled-prop)（ ）为真，直到进度对话框复位。进度对话框被隐藏。

```
QProgressDialog.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QProgressDialog.closeEvent (self, QCloseEvent)
```

从重新实现[QWidget.closeEvent](qwidget.html#closeEvent)（ ） 。

```
QProgressDialog.forceShow (self)
```

显示已经启动，如果它仍然隐藏算法后的对话框[minimumDuration](qprogressdialog.html#minimumDuration-prop)毫秒过去了。

**See also** [setMinimumDuration](qprogressdialog.html#minimumDuration-prop)（ ） 。

```
QString QProgressDialog.labelText (self)
```

```
int QProgressDialog.maximum (self)
```

```
int QProgressDialog.minimum (self)
```

```
int QProgressDialog.minimumDuration (self)
```

```
QProgressDialog.open (self)
```

这是一个重载函数。

在打开的对话框并连接其[accepted](qdialog.html#accepted)（）信号到由指定的槽_receiver_和_member_。

该信号会从插槽中断开时，关闭对话框。

此功能被引入Qt的4.5 。

```
QProgressDialog.open (self, QObject receiver, SLOT()SLOT() member)
```

```
QProgressDialog.open (self, callable receiver)
```

```
QProgressDialog.reset (self)
```

这种方法也是一个Qt槽与C + +的签名`void reset()`。

重置进度对话框。进度对话框被隐藏，如果[autoClose](qprogressdialog.html#autoClose-prop)（）是真实的。

**See also** [setAutoClose](qprogressdialog.html#autoClose-prop)（）和[setAutoReset](qprogressdialog.html#autoReset-prop)（ ） 。

```
QProgressDialog.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QProgressDialog.setAutoClose (self, bool b)
```

```
QProgressDialog.setAutoReset (self, bool b)
```

```
QProgressDialog.setBar (self, QProgressBar bar)
```

该_bar_说法有它的所有权转移给Qt的。

设置进度栏小工具，_bar_。进度对话框调整大小以适合。进度对话框需要的进度所有权_bar_这将在必要时不要使用在堆栈上分配一个进度条被删除，所以。

```
QProgressDialog.setCancelButton (self, QPushButton button)
```

该_button_说法有它的所有权转移给Qt的。

设置取消按钮，按钮，_cancelButton_。进度对话框需要这个按钮将被删除必要时的所有权，所以不要传递一个对象，它是在栈上的地址，即使用新的（）来创建按钮。如果传递0则没有取消按钮会显示。

**See also** [setCancelButtonText](qprogressdialog.html#setCancelButtonText)（ ） 。

```
QProgressDialog.setCancelButtonText (self, QString)
```

这种方法也是一个Qt槽与C + +的签名`void setCancelButtonText(const QString&)`。

设置取消按钮的文本_cancelButtonText_。如果文本被设置为的QString （ ），那么它会导致取消按钮被隐藏和删除。

**See also** [setCancelButton](qprogressdialog.html#setCancelButton)（ ） 。

```
QProgressDialog.setLabel (self, QLabel label)
```

该_label_说法有它的所有权转移给Qt的。

设置标籤_label_。进度对话框调整大小以适合。标籤变成了进度对话框，并拥有将被删除必要的时候，所以不要在栈上传递一个对象的地址。

**See also** [setLabelText](qprogressdialog.html#labelText-prop)（ ） 。

```
QProgressDialog.setLabelText (self, QString)
```

这种方法也是一个Qt槽与C + +的签名`void setLabelText(const QString&)`。

```
QProgressDialog.setMaximum (self, int maximum)
```

这种方法也是一个Qt槽与C + +的签名`void setMaximum(int)`。

```
QProgressDialog.setMinimum (self, int minimum)
```

这种方法也是一个Qt槽与C + +的签名`void setMinimum(int)`。

```
QProgressDialog.setMinimumDuration (self, int ms)
```

这种方法也是一个Qt槽与C + +的签名`void setMinimumDuration(int)`。

```
QProgressDialog.setRange (self, int minimum, int maximum)
```

将进度对话框的最小值和最大值_minimum_和_maximum_元。

If _maximum_小于_minimum_，_minimum_成为唯一的合法值。

如果当前值超出了新的范围，进度对话框会重设[reset](qprogressdialog.html#reset)（ ） 。

**See also** [minimum](qprogressdialog.html#minimum-prop)和[maximum](qprogressdialog.html#maximum-prop)。

```
QProgressDialog.setValue (self, int progress)
```

这种方法也是一个Qt槽与C + +的签名`void setValue(int)`。

```
QProgressDialog.showEvent (self, QShowEvent e)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QSize QProgressDialog.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

返回适合的进度对话框中的内容大小。进度对话框调整自身大小的要求，所以你不应该需要自己调用这个函数。

```
int QProgressDialog.value (self)
```

```
bool QProgressDialog.wasCanceled (self)
```

* * *

## Qt Signal Documentation

```
void canceled ()
```

这是该信号的默认超载。

被点击了取消按钮时，这个信号被发射。它被连接到[cancel](qprogressdialog.html#cancel)（）槽的默认。

**See also** [wasCanceled](qprogressdialog.html#wasCanceled-prop)（ ） 。