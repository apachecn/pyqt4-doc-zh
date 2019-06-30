# QPrintEngine Class Reference

## [[QtGui](index.htm) module]

该QPrintEngine类定义一个接口，用于如何[QPrinter](qprinter.html)交互与给定的打印子系统。[More...](#details)

### Types

*   `enum PrintEnginePropertyKey { PPK_CollateCopies, PPK_ColorMode, PPK_Creator, PPK_DocumentName, ..., PPK_CustomBase }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPrintEngine)`
*   `bool abort (self)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric)`
*   `bool newPage (self)`
*   `QPrinter.PrinterState printerState (self)`
*   `QVariant property (self, PrintEnginePropertyKey key)`
*   `setProperty (self, PrintEnginePropertyKey key, QVariant value)`

* * *

## Detailed Description

该QPrintEngine类定义一个接口，用于如何[QPrinter](qprinter.html)交互与给定的打印子系统。

创建您自己的打印引擎时常见的情况是从两个派生[QPaintEngine](qpaintengine.html)和QPrintEngine 。打印引擎的各种性质都给予[property](qprintengine.html#property)（ ），并设置用[setProperty](qprintengine.html#setProperty)（ ） 。

* * *

## Type Documentation

```
QPrintEngine.PrintEnginePropertyKey
```

该枚举用于打印引擎之间的通信性能和[QPrinter](qprinter.html)。一个属性可能会或可能不会被给定的打印引擎的支持。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrintEngine.PPK_CollateCopies` | `0` | 一个布尔值，表示打印输出是否应该整理与否。 |
| `QPrintEngine.PPK_ColorMode` | `1` | 指[QPrinter.ColorMode](qprinter.html#ColorMode-enum)，无论是彩色还是黑白。 |
| `QPrintEngine.PPK_Creator` | `2` | 一个字符串，描述了文档的创建者。 |
| `QPrintEngine.PPK_Duplex` | `21` | 一个布尔值，指示是否应该用于打印输出的打印机纸张的两面。 |
| `QPrintEngine.PPK_DocumentName` | `3` | 一个字符串，描述在后台打印程序的文件名。 |
| `QPrintEngine.PPK_FontEmbedding` | `19` | 一个布尔值，表示该文档的字体数据是否应该被嵌入在发送到打印机的数据。 |
| `QPrintEngine.PPK_FullPage` | `4` | 一个布尔值，说明如果打印机应该是整页或没有。 |
| `QPrintEngine.PPK_NumberOfCopies` | `5` | 已过时。一个整数，指定打印份数。使用PPK_CopyCount代替。 |
| `QPrintEngine.PPK_Orientation` | `6` | 指定[QPrinter.Orientation](qprinter.html#Orientation-enum)值。 |
| `QPrintEngine.PPK_OutputFileName` | `7` | 输出文件名作为一个字符串。一个空的文件名表示打印机不能打印到文件。 |
| `QPrintEngine.PPK_PageOrder` | `8` | 指定[QPrinter.PageOrder](qprinter.html#PageOrder-enum)值。 |
| `QPrintEngine.PPK_PageRect` | `9` | A [QRect](qrect.html)指定页面的矩形 |
| `QPrintEngine.PPK_PageSize` | `10` | 已过时。使用PPK_PaperSize代替。 |
| `QPrintEngine.PPK_PaperRect` | `11` | A [QRect](qrect.html)指定纸张的矩形。 |
| `QPrintEngine.PPK_PaperSource` | `12` | 指定[QPrinter.PaperSource](qprinter.html#PaperSource-enum)值。 |
| `QPrintEngine.PPK_PaperSources` | `22` | 指定多于一个[QPrinter.PaperSource](qprinter.html#PaperSource-enum)值。 |
| `QPrintEngine.PPK_PaperSize` | `PPK_PageSize` | 指定[QPrinter.PaperSize](qprinter.html#PaperSize-enum)值。 |
| `QPrintEngine.PPK_PrinterName` | `13` | 一个字符串，指定打印机的名称。 |
| `QPrintEngine.PPK_PrinterProgram` | `14` | 一个字符串，指定用于打印的打印机程序的名称， |
| `QPrintEngine.PPK_Resolution` | `15` | 一个整数描述每英寸点数为这台打印机。 |
| `QPrintEngine.PPK_SelectionOption` | `16` |   |
| `QPrintEngine.PPK_SupportedResolutions` | `17` | 整数列表[QVariants](index.htm#qvariants)描述一组打印机有支持的分辨率。 |
| `QPrintEngine.PPK_SuppressSystemPrintStatus` | `20` | 打压展示印刷进步的内置对话框。由于4.1本只有在Mac OS X，其中，在默认情况下，会显示一个状态对话框的效果。 |
| `QPrintEngine.PPK_WindowsPageSize` | `18` | 一个整数，指定在Windows上DM_PAPER条目。 |
| `QPrintEngine.PPK_CustomPaperSize` | `23` | A [QSizeF](qsizef.html)在指定自定义纸张尺寸[QPrinter.Point](qprinter.html#Unit-enum)单元。 |
| `QPrintEngine.PPK_PageMargins` | `24` | A [QList](index.htm)\u003c[QVariant](qvariant.html)\u003e包含左，上，右，下边距值。 |
| `QPrintEngine.PPK_CopyCount` | `25` | 一个整数，指定要打印的副本数。 |
| `QPrintEngine.PPK_SupportsMultipleCopies` | `26` | 一个布尔值，表示打印机是否支持打印多份在一个作业。 |
| `QPrintEngine.PPK_CustomBase` | `0xff00` | 为扩展的基础。 |

* * *

## Method Documentation

```
QPrintEngine.__init__ (self)
```

```
QPrintEngine.__init__ (self, QPrintEngine)
```

```
bool QPrintEngine.abort (self)
```

这种方法是抽象的，应在任何子类中重新实现。

指示打印引擎，中止打印处理。成功返回True ，否则返回False 。

```
int QPrintEngine.metric (self, QPaintDevice.PaintDeviceMetric)
```

这种方法是抽象的，应在任何子类中重新实现。

返回度量给定的_id_。

```
bool QPrintEngine.newPage (self)
```

这种方法是抽象的，应在任何子类中重新实现。

指示打印引擎启动一个新的页面。返回True如果打印机能够创建新的页面，否则返回False 。

```
QPrinter.PrinterState QPrintEngine.printerState (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回正在使用的打印引擎的打印机的当前状态。

```
QVariant QPrintEngine.property (self, PrintEnginePropertyKey key)
```

这种方法是抽象的，应在任何子类中重新实现。

返回由指定的打印引擎的财产_key_。

](qprinter.html#PrinterState-enum)

[**See also**](qprinter.html#PrinterState-enum) [setProperty](qprintengine.html#setProperty)（ ） 。

```
QPrintEngine.setProperty (self, PrintEnginePropertyKey key, QVariant value)
```

这种方法是抽象的，应在任何子类中重新实现。

设置由指定的打印引擎的财产_key_为给定的_value_。

**See also** [property](qprintengine.html#property)（ ） 。