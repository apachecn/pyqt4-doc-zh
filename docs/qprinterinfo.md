# QPrinterInfo Class Reference

## [[QtGui](index.htm) module]

该QPrinterInfo类可以访问有关现有打印机的信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPrinterInfo src)`
*   `__init__ (self, QPrinter printer)`
*   `bool isDefault (self)`
*   `bool isNull (self)`
*   `QString printerName (self)`
*   `list-of-QPrinter.PageSize supportedPaperSizes (self)`

### Static Methods

*   `list-of-QPrinterInfo availablePrinters ()`
*   `QPrinterInfo defaultPrinter ()`

* * *

## Detailed Description

该QPrinterInfo类可以访问有关现有打印机的信息。

使用静态函数生成QPrinterInfo对象的列表。列表中的每个QPrinterInfo对象表示一台打印机，可查询的名称，支持的纸张尺寸，以及它是否是默认打印机。

* * *

## Method Documentation

```
QPrinterInfo.__init__ (self)
```

构造一个空[QPrinterInfo](qprinterinfo.html)对象。

**See also** [isNull](qprinterinfo.html#isNull)（ ） 。

```
QPrinterInfo.__init__ (self, QPrinterInfo src)
```

构造的副本_other_。

此功能被引入Qt的4.8 。

```
QPrinterInfo.__init__ (self, QPrinter printer)
```

构造一个[QPrinterInfo](qprinterinfo.html)从对象_printer_。

```
list-of-QPrinterInfo QPrinterInfo.availablePrinters ()
```

返回系统上的可用打印机的列表。

```
QPrinterInfo QPrinterInfo.defaultPrinter ()
```

[

返回系统上的默认打印机。

](qprinterinfo.html)

[返回值应该使用进行检查](qprinterinfo.html)[isNull](qprinterinfo.html#isNull)（ ）在使用之前，如果没有默认打印机。

**See also** [isNull](qprinterinfo.html#isNull)（ ） 。

```
bool QPrinterInfo.isDefault (self)
```

返回此打印机是否为默认打印机。

```
bool QPrinterInfo.isNull (self)
```

返回是否该[QPrinterInfo](qprinterinfo.html)对象持有打印机定义。

空[QPrinterInfo](qprinterinfo.html)对象可能会导致例如由主叫[defaultPrinter](qprinterinfo.html#defaultPrinter)（ ）当有在系统上没有打印机。

```
QString QPrinterInfo.printerName (self)
```

返回该打印机的名称。

**See also** [QPrinter.setPrinterName](qprinter.html#setPrinterName)（ ） 。

```
list-of-QPrinter.PageSize QPrinterInfo.supportedPaperSizes (self)
```

打印机返回支持的纸张尺寸的列表。

不是所有的打印机驱动程序支持这个查询，所以列表可能是空的。在Mac OS X 10.3 ，该函数总是返回一个空列表。

此功能被引入Qt的4.4 。