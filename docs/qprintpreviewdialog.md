# QPrintPreviewDialog Class Reference

## [[QtGui](index.htm) module]

该QPrintPreviewDialog类提供用于预览和配置页面布局打印输出的对话框。[More...](#details)

继承[QDialog](qdialog.html)。

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `__init__ (self, QPrinter printer, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `done (self, int result)`
*   `open (self)`
*   `open (self, QObject receiver, SLOT()SLOT() member)`
*   `open (self, callable receiver)`
*   `QPrinter printer (self)`
*   `setVisible (self, bool visible)`

### Qt Signals

*   `void paintRequested (QPrinter *)`

* * *

## Detailed Description

该QPrintPreviewDialog类提供用于预览和配置页面布局打印输出的对话框。

在您现有的应用程序中使用QPrintPreviewDialog很简单：

1.  创建QPrintPreviewDialog 。

    你可以构造一个QPrintPreviewDialog与现有[QPrinter](qprinter.html)对象，或者你可以有QPrintPreviewDialog为您创建一个，这将是系统默认的打印机。

2.  连接[paintRequested](qprintpreviewdialog.html#paintRequested)（）信号到一个槽。

    当对话需要产生一组预览页面，该[paintRequested](qprintpreviewdialog.html#paintRequested)（）信号将被发射。您可以使用完全相同的代码为实际印刷作为其生成的预览，包括调用[QPrinter.newPage](qprinter.html#newPage)（）以在预览启动一个新的页面。槽连接到[paintRequested](qprintpreviewdialog.html#paintRequested)（ ）信号，其中你画到[QPrinter](qprinter.html)对象，该对象被传递到插槽中。

3.  Call [exec_](qdialog.html#exec)（ ） 。

    Call [QPrintPreviewDialog.exec](qdialog.html#exec)（ ）来显示预览对话框。

在Symbian ，有打印的支持。因此，不应该在Symbian中使用此对话框。

* * *

## Method Documentation

```
QPrintPreviewDialog.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QPrintPreviewDialog](qprintpreviewdialog.html)基于_printer_并与_parent_作为父控件。窗口部件标记_flags_到传递[QWidget](qwidget.html)构造函数。

**See also** [QWidget.setWindowFlags](qwidget.html#windowFlags-prop)（ ） 。

```
QPrintPreviewDialog.__init__ (self, QPrinter printer, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

这是一个重载函数。

这将创建一个内部[QPrinter](qprinter.html)对象，该对象将使用系统默认的打印机。

```
QPrintPreviewDialog.done (self, int result)
```

从重新实现[QDialog.done](qdialog.html#done)（ ） 。

```
QPrintPreviewDialog.open (self)
```

这是一个重载函数。

在打开的对话框及其成品（ int）的信号连接到由指定的插槽_receiver_和_member_。

该信号会从插槽中断开时，关闭对话框。

此功能被引入Qt的4.5 。

```
QPrintPreviewDialog.open (self, QObject receiver, SLOT()SLOT() member)
```

```
QPrintPreviewDialog.open (self, callable receiver)
```

```
QPrinter QPrintPreviewDialog.printer (self)
```

[](qprinter.html)

[返回一个指针](qprinter.html)[QPrinter](qprinter.html)反对这个对话框是目前经营上。

```
QPrintPreviewDialog.setVisible (self, bool visible)
```

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

* * *

## Qt Signal Documentation

```
void paintRequested (QPrinter *)
```

这是该信号的默认超载。

这个信号被发射时的[QPrintPreviewDialog](qprintpreviewdialog.html)需要产生一组预览页面。

该_printer_如提供的是油漆的设备上，你应该描绘每个页面的内容，使用[QPrinter](qprinter.html)因为你会直接打印时，例如以同样的方式。