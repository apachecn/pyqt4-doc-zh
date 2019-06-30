# QPrinter Class Reference

## [[QtGui](index.htm) module]

该QPrinter做类是涂料设备，油漆上的打印机。[More...](#details)

继承[QPaintDevice](qpaintdevice.html)。

### Types

*   `enum ColorMode { GrayScale, Color }`
*   `enum DuplexMode { DuplexNone, DuplexAuto, DuplexLongSide, DuplexShortSide }`
*   `enum Orientation { Portrait, Landscape }`
*   `enum OutputFormat { NativeFormat, PdfFormat, PostScriptFormat }`
*   `enum PageOrder { FirstPageFirst, LastPageFirst }`
*   `enum PageSize { A4, B5, Letter, Legal, ..., Custom }`
*   `enum PaperSource { OnlyOne, Lower, Middle, Manual, ..., MaxPageSource }`
*   `enum PrinterMode { ScreenResolution, PrinterResolution, HighResolution }`
*   `enum PrinterState { Idle, Active, Aborted, Error }`
*   `enum PrintRange { AllPages, Selection, PageRange, CurrentPage }`
*   `enum Unit { Millimeter, Point, Inch, Pica, ..., DevicePixel }`

### Methods

*   `__init__ (self, PrinterMode mode = QPrinter.ScreenResolution)`
*   `__init__ (self, QPrinterInfo printer, PrinterMode mode = QPrinter.ScreenResolution)`
*   `bool abort (self)`
*   `int actualNumCopies (self)`
*   `bool collateCopies (self)`
*   `ColorMode colorMode (self)`
*   `int copyCount (self)`
*   `QString creator (self)`
*   `QString docName (self)`
*   `bool doubleSidedPrinting (self)`
*   `DuplexMode duplex (self)`
*   `bool fontEmbeddingEnabled (self)`
*   `int fromPage (self)`
*   `bool fullPage (self)`
*   `(float left, float top, float right, float bottom) getPageMargins (self, Unit unit)`
*   `bool isValid (self)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric)`
*   `bool newPage (self)`
*   `int numCopies (self)`
*   `Orientation orientation (self)`
*   `QString outputFileName (self)`
*   `OutputFormat outputFormat (self)`
*   `PageOrder pageOrder (self)`
*   `QRect pageRect (self)`
*   `QRectF pageRect (self, Unit)`
*   `PageSize pageSize (self)`
*   `QPaintEngine paintEngine (self)`
*   `QRect paperRect (self)`
*   `QRectF paperRect (self, Unit)`
*   `PageSize paperSize (self)`
*   `QSizeF paperSize (self, Unit unit)`
*   `PaperSource paperSource (self)`
*   `QPrintEngine printEngine (self)`
*   `QString printerName (self)`
*   `QString printerSelectionOption (self)`
*   `PrinterState printerState (self)`
*   `QString printProgram (self)`
*   `PrintRange printRange (self)`
*   `int resolution (self)`
*   `setCollateCopies (self, bool collate)`
*   `setColorMode (self, ColorMode)`
*   `setCopyCount (self, int)`
*   `setCreator (self, QString)`
*   `setDocName (self, QString)`
*   `setDoubleSidedPrinting (self, bool enable)`
*   `setDuplex (self, DuplexMode duplex)`
*   `setEngines (self, QPrintEngine printEngine, QPaintEngine paintEngine)`
*   `setFontEmbeddingEnabled (self, bool enable)`
*   `setFromTo (self, int fromPage, int toPage)`
*   `setFullPage (self, bool)`
*   `setNumCopies (self, int)`
*   `setOrientation (self, Orientation)`
*   `setOutputFileName (self, QString)`
*   `setOutputFormat (self, OutputFormat format)`
*   `setPageMargins (self, float left, float top, float right, float bottom, Unit unit)`
*   `setPageOrder (self, PageOrder)`
*   `setPageSize (self, PageSize)`
*   `setPaperSize (self, PageSize)`
*   `setPaperSize (self, QSizeF paperSize, Unit unit)`
*   `setPaperSource (self, PaperSource)`
*   `setPrinterName (self, QString)`
*   `setPrinterSelectionOption (self, QString)`
*   `setPrintProgram (self, QString)`
*   `setPrintRange (self, PrintRange range)`
*   `setResolution (self, int)`
*   `list-of-int supportedResolutions (self)`
*   `bool supportsMultipleCopies (self)`
*   `int toPage (self)`

* * *

## Detailed Description

该QPrinter做类是涂料设备，油漆上的打印机。

这个设备代表了一系列的打印输出页，并且被用在几乎完全一样的方式与其他涂料设备，如[QWidget](qwidget.html)和[QPixmap](qpixmap.html)。提供一组额外的功能来管理设备特定的功能，如方向和分辨率，并逐步在文档中的页面，因为它是生成的。

直接打印在Windows或Mac OS X的打印机时， QPrinter则负责使用内置的打印机驱动程序。在X11上， QPrinter则负责使用[Common Unix Printing System (CUPS)](http://www.cups.org/)或标准Unix[lpr](http://www.ietf.org/rfc/rfc1179.txt#lpr)实用派的PostScript或PDF输出到打印机。作为替代，本[printProgram](qprinter.html#printProgram)（ ）函数可以用来指定命令或工具来使用，而不是系统默认的。

请注意，如纸张尺寸和分辨率上的一个无效的打印机设置参数是不确定的。您可以使用[QPrinter.isValid](qprinter.html#isValid)（）来更改任何参数之前验证这一点。

QPrinter做支持多个参数，其中大部分可以通过一个最终用户来改变[print dialog](qprintdialog.html)。在一般情况下， QPrinter做通过这些功能到底层[QPrintEngine](qprintengine.html)。

最重要的参数是：

*   [setOrientation](qprinter.html#setOrientation)() tells QPrinter which page orientation to use.
*   [setPaperSize](qprinter.html#setPaperSize)() tells QPrinter what paper size to expect from the printer.
*   [setResolution](qprinter.html#setResolution)() tells QPrinter what resolution you wish the printer to provide, in dots per inch (DPI).
*   [setFullPage](qprinter.html#setFullPage)() tells QPrinter whether you want to deal with the full page or just with the part the printer can draw on.
*   [setCopyCount](qprinter.html#setCopyCount)() tells QPrinter how many copies of the document it should print.

实际印刷开始之前许多这些功能只能叫（即前[QPainter.begin](qpainter.html#begin)（ ）被调用） 。这通常是有道理的，因为，例如，它是不可能的，当你中途印刷改变的份数。也有一些用户设置（通过打印机对话框），并且应用程序都应该遵守的一些设置。看[QAbstractPrintDialog](qabstractprintdialog.html)的文档了解更多信息。

When [QPainter.begin](qpainter.html#begin)（）被调用时，它运行在QPrinter做准备一个新的页面，从而使[QPainter](qpainter.html)要立即用于油漆中的第一页的文档。一旦第一个页面已经被画，[newPage](qprinter.html#newPage)（ ）可以调用请求一个新的空白页面上绘制，或[QPainter.end](qpainter.html#end)（ ）可以被调用来完成打印。第二页和之后的所有页面都通过调用准备[newPage](qprinter.html#newPage)（ ）它们都画前。

在文档的第一页也不需要在前面加上一个呼叫到[newPage](qprinter.html#newPage)（ ） 。你只需要调用[newPage](qprinter.html#newPage)（ ）后[QPainter.begin](qpainter.html#begin)（ ）如果你需要打印的文档的开头插入一个空白页。同样，调用[newPage](qprinter.html#newPage)（）中的文件的最后一页被涂之后，将导致附加到印刷文件的末尾的后空白页。

如果你想中止打印作业，[abort](qprinter.html#abort)（ ）将尽最大努力停止打印。它可能会取消整个作业或只是其中的一部分。

由于QPrinter做可以打印到任何[QPrintEngine](qprintengine.html)子类，它可以扩展打印支持通过子类化，以包括新类型的印刷子系统[QPrintEngine](qprintengine.html)并重新实现它的接口。

* * *

## Type Documentation

```
QPrinter.ColorMode
```

该枚举类型用于指示是否[QPrinter](qprinter.html)应该在颜色或不打印。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrinter.Color` | `1` | 彩色打印如果可用，否则是灰色的。 |
| `QPrinter.GrayScale` | `0` | 灰度打印，即使在彩色打印机。 |

```
QPrinter.DuplexMode
```

该枚举用于指示是否将发生在纸（单面或双面印刷），每个片材的一侧或两侧上印刷。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrinter.DuplexNone` | `0` | 单面（单面）打印只。 |
| `QPrinter.DuplexAuto` | `1` | 打印机的默认设置是用来判断双面打印是否被使用。 |
| `QPrinter.DuplexLongSide` | `2` | 每张纸的两面都用于印刷。将纸张翻过来的最长边的第二面打印之前 |
| `QPrinter.DuplexShortSide` | `3` | 每张纸的两面都用于印刷。将纸张翻过来的最短边的第二面打印之前 |

这个枚举被引入或修改的Qt 4.4 。

```
QPrinter.Orientation
```

该枚举类型（不要与混淆`Orientation`）被用来指定每个页面的方向。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrinter.Portrait` | `0` | 页面的高度大于它的宽度。 |
| `QPrinter.Landscape` | `1` | 该页面的宽度大于它的高度。 |

这种类型的交互[QPrinter.PaperSize](qprinter.html#PaperSize-enum)和[QPrinter.setFullPage](qprinter.html#setFullPage)（）来判断页面的最终尺寸提供给应用程序。

```
QPrinter.OutputFormat
```

的OutputFormat枚举用于描述的格式[QPrinter](qprinter.html)应该使用进行打印。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrinter.NativeFormat` | `0` | [QPrinter](qprinter.html)将使用由它运行的平台定义的方法打印输出。这种模式是默认的直接打印到打印机时。 |
| `QPrinter.PdfFormat` | `1` | [QPrinter](qprinter.html)会产生它的输出作为一个可搜索的PDF文件。这种模式是默认的打印到文件时。 |
| `QPrinter.PostScriptFormat` | `2` | [QPrinter](qprinter.html)将产生其输出作为在PostScript格式。 （此功能被引入的Qt 4.2 。 ） |

**See also** [outputFormat](qprinter.html#outputFormat)（ ）[setOutputFormat](qprinter.html#setOutputFormat)（）和[setOutputFileName](qprinter.html#setOutputFileName)（ ） 。

```
QPrinter.PageOrder
```

该枚举类型用于通过[QPrinter](qprinter.html)告诉应用程序如何打印。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrinter.FirstPageFirst` | `0` | 编号最小的页面应该先打印出来。 |
| `QPrinter.LastPageFirst` | `1` | 最高编号的页面应该先打印出来。 |

```
QPrinter.PageSize
```

```
QPrinter.PaperSource
```

该枚举类型指定了纸张来源[QPrinter](qprinter.html)是使用。[QPrinter](qprinter.html)不检查纸张来源是否可用;它只是使用这些信息来尝试并设置纸张来源。它是否将设置纸张来源取决于打印机是否具有特定源。

**Warning:**这是目前唯一实现适用于Windows 。

| Constant | Value |
| --- | --- |
| `QPrinter.Auto` | `6` |
| `QPrinter.Cassette` | `11` |
| `QPrinter.Envelope` | `4` |
| `QPrinter.EnvelopeManual` | `5` |
| `QPrinter.FormSource` | `12` |
| `QPrinter.LargeCapacity` | `10` |
| `QPrinter.LargeFormat` | `9` |
| `QPrinter.Lower` | `1` |
| `QPrinter.MaxPageSource` | `13` |
| `QPrinter.Middle` | `2` |
| `QPrinter.Manual` | `3` |
| `QPrinter.OnlyOne` | `0` |
| `QPrinter.Tractor` | `7` |
| `QPrinter.SmallFormat` | `8` |

```
QPrinter.PrinterMode
```

这个枚举变量描述模式的打印机应该工作。它基本上是预置了一定的分辨率和工作模式。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrinter.ScreenResolution` | `0` | 设置打印设备屏幕分辨率的分辨率。这具有很大的优势打印机上绘制时所获得的结果将在屏幕上可见的输出相匹配或多或少确切。这是最容易使用，在屏幕上和打印机上的字体度量标准是相同的。这是默认值。 ScreenResolution会产生低质量的输出比高分辨率，应该只用于草稿。 |
| `QPrinter.PrinterResolution` | `1` | 此值已弃用。是相当于ScreenResolution在Unix和高分辨率在Windows和Mac 。由于做ScreenResolution和高分辨率之间的区别，使用这个值可能会导致非便携式打印机的代码。 |
| `QPrinter.HighResolution` | `2` | 在Windows上，设置打印机分辨率，对于所使用的打印机定义。对于PostScript打印，设置PostScript驱动程序为1200 dpi的分辨率。 |

**Note:**当在呈现文本[QPrinter](qprinter.html)装置中，要认识到，文字的大小，当在指定的点，是独立于装置本身所指定的分辨率是重要的。因此，它可能是有用的，当结合文字与图形，以确保它们的相对大小是您所期望的指定以像素为单位的字体大小。

```
QPrinter.PrinterState
```

| Constant | Value |
| --- | --- |
| `QPrinter.Idle` | `0` |
| `QPrinter.Active` | `1` |
| `QPrinter.Aborted` | `2` |
| `QPrinter.Error` | `3` |

```
QPrinter.PrintRange
```

用于指定打印范围选择选项。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrinter.AllPages` | `0` | 所有网页应打印。 |
| `QPrinter.Selection` | `1` | 唯一的选择应打印。 |
| `QPrinter.PageRange` | `2` | 指定页面范围应打印。 |
| `QPrinter.CurrentPage` | `3` | 只有当前页面应该被打印出来。 |

**See also** [QAbstractPrintDialog.PrintRange](qabstractprintdialog.html#PrintRange-enum)。

```
QPrinter.Unit
```

该枚举类型用于指定的测量单位为页和纸张尺寸。

| Constant | Value |
| --- | --- |
| `QPrinter.Millimeter` | `0` |
| `QPrinter.Point` | `1` |
| `QPrinter.Inch` | `2` |
| `QPrinter.Pica` | `3` |
| `QPrinter.Didot` | `4` |
| `QPrinter.Cicero` | `5` |
| `QPrinter.DevicePixel` | `6` |

注意点和DevicePixel之间的差异。的点部被定义为一英寸的1/72th ，而DevicePixel单元是分辨率依赖，并基于实际的像素，或点，在打印机上。

这个枚举被引入或修改的Qt 4.4 。

* * *

## Method Documentation

```
QPrinter.__init__ (self, PrinterMode mode = QPrinter.ScreenResolution)
```

创建一个新的打印机对象与给定_mode_。

```
QPrinter.__init__ (self, QPrinterInfo printer, PrinterMode mode = QPrinter.ScreenResolution)
```

创建一个新的打印机对象与给定_printer_和_mode_。

此功能被引入Qt的4.4 。

```
bool QPrinter.abort (self)
```

中止当前印数。返回True如果印数已成功中止，[printerState](qprinter.html#printerState)（ ）将返回[QPrinter.Aborted](qprinter.html#PrinterState-enum)否则返回False 。

它并不总是可能中止打印作业。例如，所有的数据已经到打印机，但打印机不能或不愿当被问及取消作业。

```
int QPrinter.actualNumCopies (self)
```

```
bool QPrinter.collateCopies (self)
```

如果核对开启当选择多个副本上，则返回True 。如果它被关闭，当选择多个副本，则返回False 。当核对被关闭各个页面的打印将被重复的[numCopies](index.htm#numCopies)（ ） ，开始下一个页面之前量。随着整理打开的所有网页上这些网页下副本开始前被打印出来。

这个函数是Qt 4.1中引入。

**See also** [setCollateCopies](qprinter.html#setCollateCopies)（ ） 。

```
ColorMode QPrinter.colorMode (self)
```

[

返回当前颜色模式。

](qprinter.html#ColorMode-enum)

[**See also**](qprinter.html#ColorMode-enum) [setColorMode](qprinter.html#setColorMode)（ ） 。

```
int QPrinter.copyCount (self)
```

返回将要打印的份数。默认值是1。

此功能被引入Qt的4.7 。

**See also** [setCopyCount](qprinter.html#setCopyCount)（）和[supportsMultipleCopies](qprinter.html#supportsMultipleCopies)（ ） 。

```
QString QPrinter.creator (self)
```

返回创建文档的应用程序的名称。

**See also** [setCreator](qprinter.html#setCreator)（ ） 。

```
QString QPrinter.docName (self)
```

返回的文档名称。

**See also** [setDocName](qprinter.html#setDocName)（）和[QPrintEngine.PrintEnginePropertyKey](qprintengine.html#PrintEnginePropertyKey-enum)。

```
bool QPrinter.doubleSidedPrinting (self)
```

如果双面打印已启用，则返回True 。

目前这个选项只支持X11 。

这个函数中引入了Qt 4.2中。

**See also** [setDoubleSidedPrinting](qprinter.html#setDoubleSidedPrinting)（ ） 。

```
DuplexMode QPrinter.duplex (self)
```

[

返回当前的双工模式。

目前这个选项只支持X11 。

此功能被引入Qt的4.4 。

](qprinter.html#DuplexMode-enum)

[**See also**](qprinter.html#DuplexMode-enum) [setDuplex](qprinter.html#setDuplex)（ ） 。

```
bool QPrinter.fontEmbeddingEnabled (self)
```

如果字体嵌入已启用，则返回True 。

目前这个选项只支持X11 。

这个函数是Qt 4.1中引入。

**See also** [setFontEmbeddingEnabled](qprinter.html#setFontEmbeddingEnabled)（ ） 。

```
int QPrinter.fromPage (self)
```

返回第一页的范围为要打印的页数（在“从页”的设置） 。在文档中的页面会根据第一页第1页惯例编号。

默认情况下，此函数返回一个特殊值0 ，这意味着“从页面”设置为no 。

**Note:**如果fromPage （）和[toPage](qprinter.html#toPage)（ ）都返回0 ，这表明_the whole document will be printed_。

这个函数是Qt 4.1中引入。

**See also** [setFromTo](qprinter.html#setFromTo)（）和[toPage](qprinter.html#toPage)（ ） 。

```
bool QPrinter.fullPage (self)
```

如果打印机的坐标系的原点位于页面的角落，如果其为于可打印区域的边缘，则返回True 。

See [setFullPage](qprinter.html#setFullPage)（ ）了解详情和注意事项。

**See also** [setFullPage](qprinter.html#setFullPage)（）和[PaperSize](qprinter.html#PaperSize-enum)。

```
(float left, float top, float right, float bottom) QPrinter.getPageMargins (self, Unit unit)
```

返回页边距为这台打印机在_left_，_top_，_right_，_bottom_。返回的边界的单元与指定_unit_参数。

此功能被引入Qt的4.4 。

```
bool QPrinter.isValid (self)
```

返回True如果当前选择的打印机是系统有效的打印机，或者一个纯粹的PDF / PostScript打印机，否则返回False 。

为了检测其他故障检查的输出[QPainter.begin](qpainter.html#begin)（）或[QPrinter.newPage](qprinter.html#newPage)（ ） 。

```
     [QPrinter](qprinter.html) printer;
     printer.setOutputFormat([QPrinter](qprinter.html).PdfFormat);
     printer.setOutputFileName("/foobar/nonwritable.pdf");
     [QPainter](qpainter.html) painter;
     if (! painter.begin(&printer)) { // failed to open file
         qWarning("failed to open file, is it writable?");
         return 1;
     }
     painter.drawText(10, 10, "Test");
     if (! printer.newPage()) {
         qWarning("failed in flushing page to disk, disk full?");
         return 1;
     }
     painter.drawText(10, 10, "Test 2");
     painter.end();

```

此功能被引入Qt的4.4 。

**See also** [setPrinterName](qprinter.html#setPrinterName)（ ） 。

```
int QPrinter.metric (self, QPaintDevice.PaintDeviceMetric)
```

```
bool QPrinter.newPage (self)
```

告诉打印机退出当前页面，并继续打印在新页面上。返回True如果成功，否则返回False 。

在非活动呼叫NEWPAGE （ ）[QPrinter](qprinter.html)对象总是会失败。

```
int QPrinter.numCopies (self)
```

```
Orientation QPrinter.orientation (self)
```

[](qprinter.html#Orientation-enum)

[返回的方向设置。这是驱动程序相关的，但通常为](qprinter.html#Orientation-enum)[QPrinter.Portrait](qprinter.html#Orientation-enum)。

**See also** [setOrientation](qprinter.html#setOrientation)（ ） 。

```
QString QPrinter.outputFileName (self)
```

返回的输出文件的名称。默认情况下，这是一个空字符串（表示打印机不能打印到文件） 。

**See also** [setOutputFileName](qprinter.html#setOutputFileName)（）和[QPrintEngine.PrintEnginePropertyKey](qprintengine.html#PrintEnginePropertyKey-enum)。

```
OutputFormat QPrinter.outputFormat (self)
```

[

返回此打印机的输出格式。

这个函数是Qt 4.1中引入。

](qprinter.html#OutputFormat-enum)

[**See also**](qprinter.html#OutputFormat-enum) [setOutputFormat](qprinter.html#setOutputFormat)（ ） 。

```
PageOrder QPrinter.pageOrder (self)
```

[

返回当前页面顺序。

默认的页面顺序是`FirstPageFirst`。

](qprinter.html#PageOrder-enum)

[**See also**](qprinter.html#PageOrder-enum) [setPageOrder](qprinter.html#setPageOrder)（ ） 。

```
QRect QPrinter.pageRect (self)
```

[](qrect.html)

[返回该页面的矩形，这是通常比小](qrect.html)[paperRect](qprinter.html#paperRect)（ ），因为页面通常具有其边界和纸张之间的利润率。

返回的矩形的单元是[DevicePixel](qprinter.html#Unit-enum)。

**See also** [paperSize](qprinter.html#paperSize)（ ） 。

```
QRectF QPrinter.pageRect (self, Unit)
```

[](qrectf.html)

[返回页面的矩形_unit_;这通常比小](qrectf.html)[paperRect](qprinter.html#paperRect)（ ），因为页面通常具有其边界和纸张之间的利润率。

此功能被引入Qt的4.4 。

**See also** [paperSize](qprinter.html#paperSize)（ ） 。

```
PageSize QPrinter.pageSize (self)
```

[](qprinter.html#PageSize-enum)

```
QPaintEngine QPrinter.paintEngine (self)
```

[](qpaintengine.html)

[从重新实现](qpaintengine.html)[QPaintDevice.paintEngine](qpaintdevice.html#paintEngine)（ ） 。

返回打印机使用的绘图引擎。

```
QRect QPrinter.paperRect (self)
```

[](qrect.html)

[返回该纸的矩形，这是通常比大](qrect.html)[pageRect](qprinter.html#pageRect)（ ） 。

返回的矩形的单元是[DevicePixel](qprinter.html#Unit-enum)。

**See also** [pageRect](qprinter.html#pageRect)（ ） 。

```
QRectF QPrinter.paperRect (self, Unit)
```

[](qrectf.html)

[返回该论文的矩形_unit_;这通常比大](qrectf.html)[pageRect](qprinter.html#pageRect)（ ） 。

此功能被引入Qt的4.4 。

**See also** [pageRect](qprinter.html#pageRect)（ ） 。

```
PageSize QPrinter.paperSize (self)
```

[

返回打印机的纸张尺寸。默认值是驱动程序相关的。

此功能被引入Qt的4.4 。

](qprinter.html#PageSize-enum)

[**See also**](qprinter.html#PageSize-enum) [setPaperSize](qprinter.html#setPaperSize)（ ）[pageRect](qprinter.html#pageRect)（）和[paperRect](qprinter.html#paperRect)（ ） 。

```
QSizeF QPrinter.paperSize (self, Unit unit)
```

[

返回的纸张尺寸_unit_。

此功能被引入Qt的4.4 。

](qsizef.html)

[**See also**](qsizef.html) [setPaperSize](qprinter.html#setPaperSize)（ ） 。

```
PaperSource QPrinter.paperSource (self)
```

[

返回打印机的纸张来源。这是`Manual`或打印机托盘或纸盒。

](qprinter.html#PaperSource-enum)

[**See also**](qprinter.html#PaperSource-enum) [setPaperSource](qprinter.html#setPaperSource)（ ） 。

```
QPrintEngine QPrinter.printEngine (self)
```

[

返回所使用的打印机的打印引擎。

这个函数是Qt 4.1中引入。

```
QString QPrinter.printerName (self)
```

返回打印机的名称。这个值最初设置为默认打印机的名称。

](qprintengine.html)

[**See also**](qprintengine.html) [setPrinterName](qprinter.html#setPrinterName)（ ） 。

```
QString QPrinter.printerSelectionOption (self)
```

返回打印机选项选择字符串。这是仅在打印命令已经明确设置非常有用。

默认值（空字符串）意味着打印机应在与系统相关的方式来选择。

任何其他值意味着，给定的值应该被使用。

**Warning:**此功能不适用于Windows 。

**See also** [setPrinterSelectionOption](qprinter.html#setPrinterSelectionOption)（ ） 。

```
PrinterState QPrinter.printerState (self)
```

[

返回打印机的当前状态。这可能并不总是准确的（例如，如果打印机不具有报告其状态的操作系统的能力） 。

```
QString QPrinter.printProgram (self)
```

返回发送的打印输出到打印机上的节目的名称。

](qprinter.html#PrinterState-enum)

[默认是返回一个空字符串，这意味着](qprinter.html#PrinterState-enum)[QPrinter](qprinter.html)会自作聪明的系统相关的方式。在X11而已，你可以将它设置为不同的东西来使用特定的打印程序。在其他平台上，此方法返回一个空字符串。

**See also** [setPrintProgram](qprinter.html#setPrintProgram)（）和[setPrinterSelectionOption](qprinter.html#setPrinterSelectionOption)（ ） 。

```
PrintRange QPrinter.printRange (self)
```

[](qprinter.html#PrintRange-enum)

[返回的页面范围](qprinter.html#PrintRange-enum)[QPrinter](qprinter.html)。已经开通的打印设置对话框后，该函数返回用户选择的值。

这个函数是Qt 4.1中引入。

**See also** [setPrintRange](qprinter.html#setPrintRange)（ ） 。

```
int QPrinter.resolution (self)
```

返回打印机的当前假定号决议，载[setResolution](qprinter.html#setResolution)（）或由打印机驱动程序。

**See also** [setResolution](qprinter.html#setResolution)（ ） 。

```
QPrinter.setCollateCopies (self, bool collate)
```

设置了自动分页复选框的默认值将出现打印对话框的时候。如果_collate_是真的，它将使[setCollateCopiesEnabled](index.htm#setCollateCopiesEnabled)（ ） 。默认值是False 。此值将通过什么用户按下在打印对话框中进行更改。

这个函数是Qt 4.1中引入。

**See also** [collateCopies](qprinter.html#collateCopies)（ ） 。

```
QPrinter.setColorMode (self, ColorMode)
```

设置打印机的色彩模式_newColorMode_，它可以是`Color` or `GrayScale`。

**See also** [colorMode](qprinter.html#colorMode)（ ） 。

```
QPrinter.setCopyCount (self, int)
```

设置的份数被打印到_count_。

打印机驱动程序读取该设置并打印指定的副本数。

此功能被引入Qt的4.7 。

**See also** [copyCount](qprinter.html#copyCount)（）和[supportsMultipleCopies](qprinter.html#supportsMultipleCopies)（ ） 。

```
QPrinter.setCreator (self, QString)
```

设置创建该文件的应用程序的名称_creator_。

此功能仅适用于X11版本的Qt 。如果没有指定创作者的名字，创作者将被设置为“ QT”后面跟着一些版本号。

**See also** [creator](qprinter.html#creator)（ ） 。

```
QPrinter.setDocName (self, QString)
```

设置文件名_name_。

在X11上，文件名称是例如用作默认的输出文件名[QPrintDialog](qprintdialog.html)。请注意，该文件的名称不影响文件名如果打印机打印到文件。使用setOutputFile （）函数来实现这个。

**See also** [docName](qprinter.html#docName)（）和[QPrintEngine.PrintEnginePropertyKey](qprintengine.html#PrintEnginePropertyKey-enum)。

```
QPrinter.setDoubleSidedPrinting (self, bool enable)
```

启用双面打印，如果_doubleSided_为True，否则禁用它。

目前这个选项只支持X11 。

这个函数中引入了Qt 4.2中。

**See also** [doubleSidedPrinting](qprinter.html#doubleSidedPrinting)（ ） 。

```
QPrinter.setDuplex (self, DuplexMode duplex)
```

启用基于双面打印_duplex_模式。

目前这个选项只支持X11 。

此功能被引入Qt的4.4 。

**See also** [duplex](qprinter.html#duplex)（ ） 。

```
QPrinter.setEngines (self, QPrintEngine printEngine, QPaintEngine paintEngine)
```

此功能用于通过子类[QPrinter](qprinter.html)指定自定义打印和油漆引擎（_printEngine_和_paintEngine_，分别）。

[QPrinter](qprinter.html)不佔用发动机的所有权，所以你需要管理这些引擎的情况下自己。

请注意，改变发动机将重置打印机的状态和它的所有属性。

这个函数是Qt 4.1中引入。

**See also** [printEngine](qprinter.html#printEngine)（ ）[paintEngine](qprinter.html#paintEngine)（）和[setOutputFormat](qprinter.html#setOutputFormat)（ ） 。

```
QPrinter.setFontEmbeddingEnabled (self, bool enable)
```

启用或禁用字体嵌入视_enable_。

目前这个选项只支持X11 。

这个函数是Qt 4.1中引入。

**See also** [fontEmbeddingEnabled](qprinter.html#fontEmbeddingEnabled)（ ） 。

```
QPrinter.setFromTo (self, int fromPage, int toPage)
```

设置的要打印到复盖由指定号码的页面的页面范围_from_和_to_，其中_from_对应于该区域中的第一页和_to_对应于最后。

**Note:**在文档中的页面会根据第一页第1页惯例编号。然而，如果_from_和_to_都设置为0，则_whole document will be printed_。

此功能主要用于当你调用设置一个默认值，用户可以复盖在打印对话框[setup](index.htm#setup)（ ） 。

这个函数是Qt 4.1中引入。

**See also** [fromPage](qprinter.html#fromPage)（）和[toPage](qprinter.html#toPage)（ ） 。

```
QPrinter.setFullPage (self, bool)
```

If _fp_诚然，使绘画在整个页面的支持，否则将绘制限制在设备报告的可打印区域。

默认情况下，满页打印被禁用。在这种情况下，在原点[QPrinter](qprinter.html)的坐标系可打印区域的左上角重合。

如果整页打印启用时，的起源[QPrinter](qprinter.html)的坐标系统与纸本身的左上角重合。在这种情况下，[device metrics](qpaintdevice.html#PaintDeviceMetric-enum)由所指示将报告完全相同的尺寸[PaperSize](qprinter.html#PaperSize-enum)。它可能无法在整个物理页的打印，因为打印机的页边距的，因此应用程序必须考虑边缘本身。

**See also** [fullPage](qprinter.html#fullPage)（ ）[setPaperSize](qprinter.html#setPaperSize)（ ）[width](qpaintdevice.html#width)（ ）[height](qpaintdevice.html#height)（）和[Printing with Qt](index.htm)。

```
QPrinter.setNumCopies (self, int)
```

```
QPrinter.setOrientation (self, Orientation)
```

设置打印方向为_orientation_。

方向既可以是[QPrinter.Portrait](qprinter.html#Orientation-enum) or [QPrinter.Landscape](qprinter.html#Orientation-enum)。

打印机驱动程序读取使用指定的方向该设置并打印。

在Windows上，可以在打印时更改此选项，将生效从下一次调用[newPage](qprinter.html#newPage)（ ） 。

在Mac OS X ，在打印作业期间改变方向没有影响。

**See also** [orientation](qprinter.html#orientation)（ ） 。

```
QPrinter.setOutputFileName (self, QString)
```

设置输出文件的名称_fileName_。

设置为null或空名称（ 0或“” ）禁用打印到文件。设置一个非空的名字使打印到文件中。

这可以改变的值[outputFormat](qprinter.html#outputFormat)（ ） 。如果文件名的后缀“ 。 PS”的PostScript ，然后自动选择输出格式。如果文件名有“ PDF ”后缀的PDF生成。如果文件名有一个后缀不是“ PS”和“ PDF ”等，所使用的输出格式是一组与[setOutputFormat](qprinter.html#setOutputFormat)（ ） 。

[QPrinter](qprinter.html)使用Qt的跨平台的PostScript或PDF打印引擎分别。如果你可以在本地生产这种格式，例如Mac OS X可以从它的打印引擎生成PDF文件，设置输出格式返回给[NativeFormat](qprinter.html#OutputFormat-enum)。

**See also** [outputFileName](qprinter.html#outputFileName)（ ）[setOutputToFile](index.htm#setOutputToFile)（）和[setOutputFormat](qprinter.html#setOutputFormat)（ ） 。

```
QPrinter.setOutputFormat (self, OutputFormat format)
```

设置该打印机的输出格式_format_。

这个函数是Qt 4.1中引入。

**See also** [outputFormat](qprinter.html#outputFormat)（ ） 。

```
QPrinter.setPageMargins (self, float left, float top, float right, float bottom, Unit unit)
```

该函数设置_left_，_top_，_right_和_bottom_页边距为这台打印机。页边距的单位与指定_unit_参数。

此功能被引入Qt的4.4 。

```
QPrinter.setPageOrder (self, PageOrder)
```

设置页面顺序来_pageOrder_。

页面顺序可以是[QPrinter.FirstPageFirst](qprinter.html#PageOrder-enum) or [QPrinter.LastPageFirst](qprinter.html#PageOrder-enum)。该应用程序是负责读取页面顺序和相应的打印。

此功能是设置一个默认值，用户可以在打印对话框中复盖最有用。

此功能仅在X11下的支持。

**See also** [pageOrder](qprinter.html#pageOrder)（ ） 。

```
QPrinter.setPageSize (self, PageSize)
```

```
QPrinter.setPaperSize (self, PageSize)
```

设置打印机纸张大小_newPaperSize_如果支持的大小。其结果是不确定的，如果_newPaperSize_不被支持。

默认的纸张大小是取决于驱动程序。

此功能主要是用于设置一个默认值，用户可以在打印对话框中重写有用的。

此功能被引入Qt的4.4 。

**See also** [paperSize](qprinter.html#paperSize)（ ）[PaperSize](qprinter.html#PaperSize-enum)，[setFullPage](qprinter.html#setFullPage)（ ）[setResolution](qprinter.html#setResolution)（ ）[pageRect](qprinter.html#pageRect)（）和[paperRect](qprinter.html#paperRect)（ ） 。

```
QPrinter.setPaperSize (self, QSizeF paperSize, Unit unit)
```

设置纸张尺寸的基础上_paperSize_在_unit_。

此功能被引入Qt的4.4 。

**See also** [paperSize](qprinter.html#paperSize)（ ） 。

```
QPrinter.setPaperSource (self, PaperSource)
```

设置纸张来源设置为_source_。

仅适用于Windows ：该选项可以在打印时改变将生效从下一次调用[newPage](qprinter.html#newPage)（ ）

**See also** [paperSource](qprinter.html#paperSource)（ ） 。

```
QPrinter.setPrinterName (self, QString)
```

设置打印机名称_name_。

**See also** [printerName](qprinter.html#printerName)（）和[isValid](qprinter.html#isValid)（ ） 。

```
QPrinter.setPrinterSelectionOption (self, QString)
```

设置要使用的打印机_option_选择打印机。_option_为null （默认情况下这意味着Qt的应该是足够聪明，猜对），但它可以被设置为其他值使用特定的打印机选择选项。

如果选择打印机选项被改变，而在打印机处于活动状态，当前打印作业可能会或可能不会受到影响。

**Warning:**此功能不适用于Windows 。

**See also** [printerSelectionOption](qprinter.html#printerSelectionOption)（ ） 。

```
QPrinter.setPrintProgram (self, QString)
```

设置应该做的打印作业的程序的名称_printProg_。

在X11上，此功能将设置程序与PostScript输出打电话。在其他平台上，它没有任何效果。

**See also** [printProgram](qprinter.html#printProgram)（ ） 。

```
QPrinter.setPrintRange (self, PrintRange range)
```

设置打印范围选项是_range_。

这个函数是Qt 4.1中引入。

**See also** [printRange](qprinter.html#printRange)（ ） 。

```
QPrinter.setResolution (self, int)
```

要求打印机在打印_dpi_或在靠近_dpi_越好。

所返回该设置影响的坐标系统，例如[QPainter.viewport](qpainter.html#viewport)（ ） 。

这个函数必须在被调用[QPainter.begin](qpainter.html#begin)（ ）有在所有平台上的效果。

**See also** [resolution](qprinter.html#resolution)（）和[setPaperSize](qprinter.html#setPaperSize)（ ） 。

```
list-of-int QPrinter.supportedResolutions (self)
```

返回的决议（的点每英寸的整数的列表）清单打印机说它支持。

对于X11 ，所有的印刷是直接到后记，这个函数总是返回一个仅包含后记分辨率，即72 （ 72 dpi的一个项目列表 - 但见[PrinterMode](qprinter.html#PrinterMode-enum)） 。

```
bool QPrinter.supportsMultipleCopies (self)
```

返回True如果打印机支持打印在一个作业中的同一文档的多个副本，否则返回False。

在大多数系统中，这个函数将返回True 。但是，不支持CUPS的X11系统上，这个函数将返回False 。这意味着应用程序具有通过打印同一文档的要求的次数来处理的份数。

此功能被引入Qt的4.7 。

**See also** [setCopyCount](qprinter.html#setCopyCount)（）和[copyCount](qprinter.html#copyCount)（ ） 。

```
int QPrinter.toPage (self)
```

返回的最后一页，在一定范围内的要打印的页数（在“页面”的设置） 。在文档中的页面会根据第一页第1页惯例编号。

默认情况下，此函数返回一个特殊值0 ，意思是“页面”设置为no 。

**Note:** If [fromPage](qprinter.html#fromPage)（）和toPage （）都返回0 ，这表明_the whole document will be printed_。

程序员负责读取该设置并打印相应。

这个函数是Qt 4.1中引入。

**See also** [setFromTo](qprinter.html#setFromTo)（）和[fromPage](qprinter.html#fromPage)（ ） 。