# QAbstractPrintDialog Class Reference

## [[QtGui](index.htm) module]

该QAbstractPrintDialog类提供了一个基实现，用于配置打印机的打印对话框。[More...](#details)

继承[QDialog](qdialog.html)。

通过继承[QPrintDialog](qprintdialog.html)。

### Types

*   `enum PrintDialogOption { None, PrintToFile, PrintSelection, PrintPageRange, ..., PrintCurrentPage }`
*   `class **[PrintDialogOptions](index.htm)**`
*   `enum PrintRange { AllPages, Selection, PageRange, CurrentPage }`

### Methods

*   `__init__ (self, QPrinter printer, QWidget parent = None)`
*   `addEnabledOption (self, PrintDialogOption option)`
*   `PrintDialogOptions enabledOptions (self)`
*   `int exec_ (self)`
*   `int fromPage (self)`
*   `bool isOptionEnabled (self, PrintDialogOption option)`
*   `int maxPage (self)`
*   `int minPage (self)`
*   `QPrinter printer (self)`
*   `PrintRange printRange (self)`
*   `setEnabledOptions (self, PrintDialogOptions options)`
*   `setFromTo (self, int fromPage, int toPage)`
*   `setMinMax (self, int min, int max)`
*   `setOptionTabs (self, list-of-QWidget tabs)`
*   `setPrintRange (self, PrintRange range)`
*   `int toPage (self)`

* * *

## Detailed Description

该QAbstractPrintDialog类提供了一个基实现，用于配置打印机的打印对话框。

这个类实现了用于自定义打印对话框中显示的设置getter和setter函数，但它不能直接使用。使用[QPrintDialog](qprintdialog.html)在你的应用程序中显示打印对话框。

在Symbian ，有打印的支持。因此，不应该在Symbian中使用此对话框。

* * *

## Type Documentation

```
QAbstractPrintDialog.PrintDialogOption
```

用于指定打印对话框的部分应该是可见的。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractPrintDialog.None` | `0x0000` | 没有一个选项被启用。 |
| `QAbstractPrintDialog.PrintToFile` | `0x0001` | 到文件选项打印已启用。 |
| `QAbstractPrintDialog.PrintSelection` | `0x0002` | 打印选择的选项被启用。 |
| `QAbstractPrintDialog.PrintPageRange` | `0x0004` | 页面范围选择的选项被启用。 |
| `QAbstractPrintDialog.PrintShowPageSize` | `0x0008` | 显示页面大小+页边距仅当启用此功能。 |
| `QAbstractPrintDialog.PrintCollateCopies` | `0x0010` | 启用了分页复印选项 |
| `QAbstractPrintDialog.PrintCurrentPage` | `0x0040` | 打印当前页面的选项被启用（该值是在4.7推出。 ） |

这个值是过时的，不执行任何操作，因为Qt的4.5 ：

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractPrintDialog.DontUseSheet` | `0x0020` | 在Qt的早期版本中，[exec_](qabstractprintdialog.html#exec)（ ）打印对话框将创建一个表在默认情况下被赋予了一个对话框父。这不再是在Qt的4.5的支持。如果你想使用表，使用[QPrintDialog.open](qprintdialog.html#open)（ ）来代替。 |

该PrintDialogOptions类型是一个typedef为[QFlags](index.htm)\u003cPrintDialogOption\u003e 。它存储PrintDialogOption值的或组合。

```
QAbstractPrintDialog.PrintRange
```

用于指定打印范围选择选项。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractPrintDialog.AllPages` | `0` | 所有网页应打印。 |
| `QAbstractPrintDialog.Selection` | `1` | 唯一的选择应打印。 |
| `QAbstractPrintDialog.PageRange` | `2` | 指定页面范围应打印。 |
| `QAbstractPrintDialog.CurrentPage` | `3` | 只有当前可见的页面应该被打印出来。 （这个值被引入4.7 。 ） |

**See also** [QPrinter.PrintRange](qprinter.html#PrintRange-enum)。

* * *

## Method Documentation

```
QAbstractPrintDialog.__init__ (self, QPrinter printer, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个抽象的打印对话框_printer_同_parent_作为父控件。

```
QAbstractPrintDialog.addEnabledOption (self, PrintDialogOption option)
```

```
PrintDialogOptions QAbstractPrintDialog.enabledOptions (self)
```

[

```
int QAbstractPrintDialog.exec_ (self)
```

这种方法是抽象的，应在任何子类中重新实现。

这个虚函数被调用，弹出对话框。它必须重新实现在子类中。

```
int QAbstractPrintDialog.fromPage (self)
```

返回要打印默认情况下在第一页，此值设置为0 。

```
bool QAbstractPrintDialog.isOptionEnabled (self, PrintDialogOption option)
```

```
int QAbstractPrintDialog.maxPage (self)
```

返回最大页面中的页面范围。由于Qt的4.4的，这个函数返回INT_MAX默认。以前的版本中返回的缺省值为1 。

```
int QAbstractPrintDialog.minPage (self)
```

返回最小的页面在页面范围。默认情况下，该值设置为1 。

](index.htm)

```
QPrinter QAbstractPrintDialog.printer (self)
```

[

返回此对话框打印机上操作打印机。

](qprinter.html)

```
PrintRange QAbstractPrintDialog.printRange (self)
```

[

返回打印范围。

](qabstractprintdialog.html#PrintRange-enum)

[**See also**](qabstractprintdialog.html#PrintRange-enum) [setPrintRange](qabstractprintdialog.html#setPrintRange)（ ） 。

```
QAbstractPrintDialog.setEnabledOptions (self, PrintDialogOptions options)
```

```
QAbstractPrintDialog.setFromTo (self, int fromPage, int toPage)
```

设定范围在打印对话框是从_from_至_to_。

```
QAbstractPrintDialog.setMinMax (self, int min, int max)
```

设置页面范围这个对话框是从_min_至_max_。这也使[PrintPageRange](qabstractprintdialog.html#PrintDialogOption-enum)选项。

```
QAbstractPrintDialog.setOptionTabs (self, list-of-QWidget tabs)
```

设置小部件列表作为_tabs_要显示打印对话框上，如果支持的话。

目前这个选项只支持X11 。

设置选项卡将其所有权转移到打印对话框。

此功能被引入Qt的4.4 。

```
QAbstractPrintDialog.setPrintRange (self, PrintRange range)
```

设置打印范围选项是_range_。

**See also** [printRange](qabstractprintdialog.html#printRange)（ ） 。

```
int QAbstractPrintDialog.toPage (self)
```

返回最后一个要打印的页面。默认情况下，该值设置为0 。