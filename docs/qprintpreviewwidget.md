# QPrintPreviewWidget Class Reference

## [[QtGui](index.htm) module]

该QPrintPreviewWidget类提供了一个小工具可以预览页面布局打印输出。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum ViewMode { SinglePageView, FacingPagesView, AllPagesView }`
*   `enum ZoomMode { CustomZoom, FitToWidth, FitInView }`

### Methods

*   `__init__ (self, QPrinter printer, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `int currentPage (self)`
*   `fitInView (self)`
*   `fitToWidth (self)`
*   `int numPages (self)`
*   `QPrinter.Orientation orientation (self)`
*   `int pageCount (self)`
*   `print_ (self)`
*   `setAllPagesViewMode (self)`
*   `setCurrentPage (self, int pageNumber)`
*   `setFacingPagesViewMode (self)`
*   `setLandscapeOrientation (self)`
*   `setOrientation (self, QPrinter.Orientation orientation)`
*   `setPortraitOrientation (self)`
*   `setSinglePageViewMode (self)`
*   `setViewMode (self, ViewMode viewMode)`
*   `setVisible (self, bool visible)`
*   `setZoomFactor (self, float zoomFactor)`
*   `setZoomMode (self, ZoomMode zoomMode)`
*   `updatePreview (self)`
*   `ViewMode viewMode (self)`
*   `float zoomFactor (self)`
*   `zoomIn (self, float factor = 1.1)`
*   `ZoomMode zoomMode (self)`
*   `zoomOut (self, float factor = 1.1)`

### Qt Signals

*   `void paintRequested (QPrinter *)`
*   `void previewChanged ()`

* * *

## Detailed Description

该QPrintPreviewWidget类提供了一个小工具可以预览页面布局打印输出。

[QPrintPreviewDialog](qprintpreviewdialog.html)使用QPrintPreviewWidget内部，并QPrintPreviewWidget的目的是使得有可能以嵌入的预览到其它部件。这也使得它能够围绕它一个不同的用户界面比默认设置有[QPrintPreviewDialog](qprintpreviewdialog.html)。

使用QPrintPreviewWidget很简单：

1.  创建QPrintPreviewWidget

    通过传递一个现有的构造QPrintPreviewWidget要么[QPrinter](qprinter.html)对象，或者已QPrintPreviewWidget创建构建的默认[QPrinter](qprinter.html)反对你。

2.  连接[paintRequested](qprintpreviewwidget.html#paintRequested)（）信号到一个槽。

    当插件需要产生一组预览页面，一个[paintRequested](qprintpreviewwidget.html#paintRequested)（）信号将被从部件射出。槽连接到这个信号，并绘制到[QPrinter](qprinter.html)通过在作为信号参数。通话[QPrinter.newPage](qprinter.html#newPage)（） ，以在预览启动一个新的页面。

* * *

## Type Documentation

```
QPrintPreviewWidget.ViewMode
```

此枚举是用来描述在预览窗口小部件的视图模式。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrintPreviewWidget.SinglePageView` | `0` | A模式，其中单页在预览中查看。 |
| `QPrintPreviewWidget.FacingPagesView` | `1` | 凡在预览中的对开页面被观看的模式。 |
| `QPrintPreviewWidget.AllPagesView` | `2` | 凡在预览所有页面中查看视图模式。 |

```
QPrintPreviewWidget.ZoomMode
```

该枚举用于描述在预览窗口小部件的缩放模式。

| Constant | Value | Description |
| --- | --- | --- |
| `QPrintPreviewWidget.CustomZoom` | `0` | 变焦被设置为自定义缩放值。 |
| `QPrintPreviewWidget.FitToWidth` | `1` | 这种模式下的当前页面适合于该视图的宽度。 |
| `QPrintPreviewWidget.FitInView` | `2` | 这种模式在当前页的视图内适合。 |

* * *

## Method Documentation

```
QPrintPreviewWidget.__init__ (self, QPrinter printer, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QPrintPreviewWidget](qprintpreviewwidget.html)基于_printer_并与_parent_作为父控件。窗口部件标记_flags_到传递[QWidget](qwidget.html)构造函数。

**See also** [QWidget.setWindowFlags](qwidget.html#windowFlags-prop)（ ） 。

```
QPrintPreviewWidget.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

这是一个重载函数。

这将导致[QPrintPreviewWidget](qprintpreviewwidget.html)创建构造内部，默认[QPrinter](qprinter.html)对象，该对象将被用于生成预览。

```
int QPrintPreviewWidget.currentPage (self)
```

返回当前浏览的页面的预览。

**See also** [setCurrentPage](qprintpreviewwidget.html#setCurrentPage)（ ） 。

```
QPrintPreviewWidget.fitInView (self)
```

这种方法也是一个Qt槽与C + +的签名`void fitInView()`。

这是一个方便的功能，是与调用`setZoomMode(QPrintPreviewWidget.FitInView)`。

```
QPrintPreviewWidget.fitToWidth (self)
```

这种方法也是一个Qt槽与C + +的签名`void fitToWidth()`。

这是一个方便的功能，是与调用`setZoomMode(QPrintPreviewWidget.FitToWidth)`。

```
int QPrintPreviewWidget.numPages (self)
```

```
QPrinter.Orientation QPrintPreviewWidget.orientation (self)
```

[](qprinter.html#Orientation-enum)

[返回预览的当前方向。从该值是](qprinter.html#Orientation-enum)[QPrinter](qprinter.html)与预览相关联的对象。

**See also** [setOrientation](qprintpreviewwidget.html#setOrientation)（ ） 。

```
int QPrintPreviewWidget.pageCount (self)
```

返回在预览的页数。

此功能被引入Qt的4.6 。

```
QPrintPreviewWidget.print_ (self)
```

这种方法也是一个Qt槽与C + +的签名`void print()`。

打印预览与预览相关联的打印机。

```
QPrintPreviewWidget.setAllPagesViewMode (self)
```

这种方法也是一个Qt槽与C + +的签名`void setAllPagesViewMode()`。

这是一个方便的功能，是与调用`setViewMode(QPrintPreviewWidget.AllPagesView)`。

```
QPrintPreviewWidget.setCurrentPage (self, int pageNumber)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentPage(int)`。

设置在预览当前页面。这将导致以跳到开头_page_。

**See also** [currentPage](qprintpreviewwidget.html#currentPage)（ ） 。

```
QPrintPreviewWidget.setFacingPagesViewMode (self)
```

这种方法也是一个Qt槽与C + +的签名`void setFacingPagesViewMode()`。

这是一个方便的功能，是与调用`setViewMode(QPrintPreviewWidget.FacingPagesView)`。

```
QPrintPreviewWidget.setLandscapeOrientation (self)
```

这种方法也是一个Qt槽与C + +的签名`void setLandscapeOrientation()`。

这是一个方便的功能，是与调用`setOrientation(QPrinter.Landscape)`。

```
QPrintPreviewWidget.setOrientation (self, QPrinter.Orientation orientation)
```

这种方法也是一个Qt槽与C + +的签名`void setOrientation(QPrinter::Orientation)`。

设置当前的取向_orientation_。此值将在设置[QPrinter](qprinter.html)与预览相关联的对象。

**See also** [orientation](qprintpreviewwidget.html#orientation)（ ） 。

```
QPrintPreviewWidget.setPortraitOrientation (self)
```

这种方法也是一个Qt槽与C + +的签名`void setPortraitOrientation()`。

这是一个方便的功能，是与调用`setOrientation(QPrinter.Portrait)`。

```
QPrintPreviewWidget.setSinglePageViewMode (self)
```

这种方法也是一个Qt槽与C + +的签名`void setSinglePageViewMode()`。

这是一个方便的功能，是与调用`setViewMode(QPrintPreviewWidget.SinglePageView)`。

```
QPrintPreviewWidget.setViewMode (self, ViewMode viewMode)
```

这种方法也是一个Qt槽与C + +的签名`void setViewMode(QPrintPreviewWidget::ViewMode)`。

设置视图模式_mode_。默认视图模式[SinglePageView](qprintpreviewwidget.html#ViewMode-enum)。

**See also** [viewMode](qprintpreviewwidget.html#viewMode)（ ） 。

```
QPrintPreviewWidget.setVisible (self, bool visible)
```

这种方法也是一个Qt槽与C + +的签名`void setVisible(bool)`。

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

```
QPrintPreviewWidget.setZoomFactor (self, float zoomFactor)
```

这种方法也是一个Qt槽与C + +的签名`void setZoomFactor(qreal)`。

设置视图的缩放因子_factor_。例如，值1.0表示缩放的观点，这大约是认为不会对纸张的尺寸。 0.5的值将减半视图的大小，而2.0的值将增加一倍视图的大小。

**See also** [zoomFactor](qprintpreviewwidget.html#zoomFactor)（ ） 。

```
QPrintPreviewWidget.setZoomMode (self, ZoomMode zoomMode)
```

这种方法也是一个Qt槽与C + +的签名`void setZoomMode(QPrintPreviewWidget::ZoomMode)`。

设置缩放模式_zoomMode_。默认缩放模式[FitInView](qprintpreviewwidget.html#ZoomMode-enum)。

**See also** [zoomMode](qprintpreviewwidget.html#zoomMode)（ ）[viewMode](qprintpreviewwidget.html#viewMode)（）和[setViewMode](qprintpreviewwidget.html#setViewMode)（ ） 。

```
QPrintPreviewWidget.updatePreview (self)
```

这种方法也是一个Qt槽与C + +的签名`void updatePreview()`。

这个函数更新预览，这会导致[paintRequested](qprintpreviewwidget.html#paintRequested)（）信号被发射。

```
ViewMode QPrintPreviewWidget.viewMode (self)
```

[](qprintpreviewwidget.html#ViewMode-enum)

[返回当前视图模式。默认视图模式](qprintpreviewwidget.html#ViewMode-enum)[SinglePageView](qprintpreviewwidget.html#ViewMode-enum)。

**See also** [setViewMode](qprintpreviewwidget.html#setViewMode)（ ） 。

```
float QPrintPreviewWidget.zoomFactor (self)
```

返回视图的缩放因子。

**See also** [setZoomFactor](qprintpreviewwidget.html#setZoomFactor)（ ） 。

```
QPrintPreviewWidget.zoomIn (self, float factor = 1.1)
```

这种方法也是一个Qt槽与C + +的签名`void zoomIn(qreal = 1.1)`。

缩放当前视图中所_factor_。为默认值_factor_是1.1 ，这意味着该视图将被缩小了10 ％ 。

```
ZoomMode QPrintPreviewWidget.zoomMode (self)
```

[

返回当前的缩放模式。

](qprintpreviewwidget.html#ZoomMode-enum)

[**See also**](qprintpreviewwidget.html#ZoomMode-enum) [setZoomMode](qprintpreviewwidget.html#setZoomMode)（ ）[viewMode](qprintpreviewwidget.html#viewMode)（）和[setViewMode](qprintpreviewwidget.html#setViewMode)（ ） 。

```
QPrintPreviewWidget.zoomOut (self, float factor = 1.1)
```

这种方法也是一个Qt槽与C + +的签名`void zoomOut(qreal = 1.1)`。

缩放当前视图由_factor_。为默认值_factor_是1.1 ，这意味着该视图将增加10 ％，按比例缩小。

* * *

## Qt Signal Documentation

```
void paintRequested (QPrinter *)
```

这是该信号的默认超载。

当预览窗口小部件需要产生一组预览页面这个信号被发射。_printer_与此预览插件的打印机相关联。

```
void previewChanged ()
```

这是该信号的默认超载。

这个信号被发射时在预览窗口部件已经改变了一些内部状态，如取向。