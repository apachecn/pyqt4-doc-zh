# QPageSetupDialog Class Reference

## [[QtGui](index.htm) module]

该QPageSetupDialog类提供了对打印机的页面相关的选项配置对话框。[More...](#details)

继承[QDialog](qdialog.html)。

### Types

*   `enum PageSetupDialogOption { DontUseSheet }`
*   `class **[PageSetupDialogOptions](index.htm)**`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QPrinter printer, QWidget parent = None)`
*   `addEnabledOption (self, PageSetupDialogOption option)`
*   `PageSetupDialogOptions enabledOptions (self)`
*   `int exec_ (self)`
*   `bool isOptionEnabled (self, PageSetupDialogOption option)`
*   `open (self)`
*   `open (self, QObject receiver, SLOT()SLOT() member)`
*   `open (self, callable receiver)`
*   `PageSetupDialogOptions options (self)`
*   `QPrinter printer (self)`
*   `setEnabledOptions (self, PageSetupDialogOptions options)`
*   `setOption (self, PageSetupDialogOption option, bool on = True)`
*   `setOptions (self, PageSetupDialogOptions options)`
*   `bool testOption (self, PageSetupDialogOption option)`

* * *

## Detailed Description

该QPageSetupDialog类提供了对打印机的页面相关的选项配置对话框。

在Windows和Mac OS X使用的是原生页面设置对话框实现的页面设置对话框。

请注意，在Windows和Mac OS X的自定义纸张尺寸将不会反映在本机页面设置对话框。此外，自定义页边距的设置[QPrinter](qprinter.html)不会在原生的Mac OS X的页面设置对话框显示。

在Symbian ，有打印的支持。因此，不应该在Symbian中使用此对话框。

* * *

## Type Documentation

```
QPageSetupDialog.PageSetupDialogOption
```

用于指定选项的页面设置对话框

这个值是过时的，不执行任何操作，因为Qt的4.5 ：

| Constant | Value | Description |
| --- | --- | --- |
| `QPageSetupDialog.DontUseSheet` | `0x00000001` | 在以前的版本[QDialog.exec](qdialog.html#exec)（ ）在页面设置对话框中会创建一个表在默认情况下，如果被赋予了一个对话框父。这不再是在Qt 4.5的支持。如果你想使用表，使用[QPageSetupDialog.open](qpagesetupdialog.html#open)（ ）来代替。 |

这个枚举被引入或修改的Qt 4.4 。

该PageSetupDialogOptions类型是一个typedef为[QFlags](index.htm)\u003cPageSetupDialogOption\u003e 。它存储PageSetupDialogOption值的或组合。

* * *

## Method Documentation

```
QPageSetupDialog.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个配置页面设置对话框_printer_同_parent_作为父控件。

```
QPageSetupDialog.__init__ (self, QPrinter printer, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个配置一个默认构造的一个页面设置对话框[QPrinter](qprinter.html)同_parent_作为父控件。

此功能被引入Qt的4.5 。

**See also** [printer](qpagesetupdialog.html#printer)（ ） 。

```
QPageSetupDialog.addEnabledOption (self, PageSetupDialogOption option)
```

```
PageSetupDialogOptions QPageSetupDialog.enabledOptions (self)
```

[

```
int QPageSetupDialog.exec_ (self)
```

```
bool QPageSetupDialog.isOptionEnabled (self, PageSetupDialogOption option)
```

```
QPageSetupDialog.open (self)
```

这是一个重载函数。

](index.htm)

[在打开的对话框并连接其](index.htm)[accepted](qdialog.html#accepted)（）信号到由指定的槽_receiver_和_member_。

该信号会从插槽中断开时，关闭对话框。

此功能被引入Qt的4.5 。

```
QPageSetupDialog.open (self, QObject receiver, SLOT()SLOT() member)
```

```
QPageSetupDialog.open (self, callable receiver)
```

```
PageSetupDialogOptions QPageSetupDialog.options (self)
```

[](index.htm)

```
QPrinter QPageSetupDialog.printer (self)
```

[](qprinter.html)

[返回传递给打印机](qprinter.html)[QPageSetupDialog](qpagesetupdialog.html)构造函数。

```
QPageSetupDialog.setEnabledOptions (self, PageSetupDialogOptions options)
```

```
QPageSetupDialog.setOption (self, PageSetupDialogOption option, bool on = True)
```

设置给定_option_被启用，如果_on_是真的，否则，清除给定的_option_。

**See also** [options](qpagesetupdialog.html#options-prop)和[testOption](qpagesetupdialog.html#testOption)（ ） 。

```
QPageSetupDialog.setOptions (self, PageSetupDialogOptions options)
```

```
bool QPageSetupDialog.testOption (self, PageSetupDialogOption option)
```

返回True如果给定的_option_被启用，否则返回False 。

**See also** [options](qpagesetupdialog.html#options-prop)和[setOption](qpagesetupdialog.html#setOption)（ ） 。