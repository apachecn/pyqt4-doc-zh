# QScrollArea Class Reference

## [[QtGui](index.htm) module]

该QScrollArea类提供了一个滚动视图到另一个部件。[More...](#details)

继承[QAbstractScrollArea](qabstractscrollarea.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `Qt.Alignment alignment (self)`
*   `ensureVisible (self, int x, int y, int xMargin = 50, int yMargin = 50)`
*   `ensureWidgetVisible (self, QWidget childWidget, int xMargin = 50, int yMargin = 50)`
*   `bool event (self, QEvent)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `bool focusNextPrevChild (self, bool next)`
*   `resizeEvent (self, QResizeEvent)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `setAlignment (self, Qt.Alignment)`
*   `setWidget (self, QWidget w)`
*   `setWidgetResizable (self, bool resizable)`
*   `QSize sizeHint (self)`
*   `QWidget takeWidget (self)`
*   `QWidget widget (self)`
*   `bool widgetResizable (self)`

* * *

## Detailed Description

该QScrollArea类提供了一个滚动视图到另一个部件。

一种涡旋式区域用于一帧中显示的子插件的内容。如果窗口部件超过该帧的大小，该视图可以提供滚动条，以使子部件的整个区域，可以被观看。孩子小部件必须被指定[setWidget](qscrollarea.html#setWidget)（ ） 。例如：

```
 [QLabel](qlabel.html) *imageLabel = new [QLabel](qlabel.html);
 [QImage](qimage.html) image("happyguy.png");
 imageLabel->setPixmap([QPixmap](qpixmap.html).fromImage(image));

 scrollArea = new QScrollArea;
 scrollArea->setBackgroundRole([QPalette](qpalette.html).Dark);
 scrollArea->setWidget(imageLabel);

```

上面的代码创建一个包含一个图像标籤的滚动区域（在下面的图片所示） 。当缩放该图像，该滚动区域可以提供必要的滚动条：

| ![](../img/qscrollarea-noscrollbars.png) | ![](../img/qscrollarea-onescrollbar.png) | ![](../img/qscrollarea-twoscrollbars.png) |

滚动条的外观取决于当前设置的[scroll bar policies](qt.html#ScrollBarPolicy-enum)。你可以控制使用从继承的功能滚动条的外观[QAbstractScrollArea](qabstractscrollarea.html)。

例如，您可以设置[QAbstractScrollArea.horizontalScrollBarPolicy](qabstractscrollarea.html#horizontalScrollBarPolicy-prop)和[QAbstractScrollArea.verticalScrollBarPolicy](qabstractscrollarea.html#verticalScrollBarPolicy-prop)属性。或者，如果你想要滚动条来动态地调整时的滚动区域的内容改变，则可以使用[horizontalScrollBar()](qabstractscrollarea.html#horizontalScrollBar)和[verticalScrollBar()](qabstractscrollarea.html#verticalScrollBar)功能（这使您可以访问滚动条），并设置每当滚动区域的内容改变滚动条的价值观，用[QScrollBar.setValue](qabstractslider.html#value-prop)（）函数。

您可以使用检索子插件的[widget](qscrollarea.html#widget)（）函数。该视图可以用来被调整大小与[setWidgetResizable](qscrollarea.html#widgetResizable-prop)（）函数。窗口小部件的取向可以与指定的[setAlignment](qscrollarea.html#alignment-prop)（ ） 。

两个便利的函数[ensureVisible](qscrollarea.html#ensureVisible)（）和[ensureWidgetVisible](qscrollarea.html#ensureWidgetVisible)（）保证的内容的特定区域是在视口内可见的，通过在必要时滚动的内容。

### Size Hints and Layouts

当使用一个滚动区域来显示一个自定义的窗口小部件的内容，它保证是重要的[size hint](qwidget.html#sizeHint-prop)儿童的插件被设置为一个合适的值。如果一个标准[QWidget](qwidget.html)用于子部件，它可能需要调用[QWidget.setMinimumSize](qwidget.html#minimumSize-prop)（）以确保该窗口小部件的内容被滚动区域内的正确显示。

如果一个滚动区域用于显示包含配置在布局子部件一个部件的内容，但要认识到，在布局的大小政策也将确定小窗口的大小是很重要的。如果你打算来动态改变布局的内容，这是特别有用的就知道了。在这种情况下，设置布局的[size constraint](qlayout.html#sizeConstraint-prop)属性之一，它提供的最小和/或布局的最大尺寸（例如，限制，[QLayout.SetMinAndMaxSize](qlayout.html#SizeConstraint-enum)）将导致滚动面积的大小进行更新时的布局变更的内容。

对于使用QScrollArea类的完整示例，请参见[Image Viewer](index.htm)例子。该示例显示了如何结合[QLabel](qlabel.html)和QScrollArea以显示图像。

* * *

## Method Documentation

```
QScrollArea.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造具有给定一个空的滚动区域_parent_。

**See also** [setWidget](qscrollarea.html#setWidget)（ ） 。

```
Qt.Alignment QScrollArea.alignment (self)
```

[

```
QScrollArea.ensureVisible (self, int x, int y, int xMargin = 50, int yMargin = 50)
```

滚动滚动区域的内容，使该点（_x_，_y_）是由以像素为单位指定页边距视口的区域内可见_xmargin_和_ymargin_。如果指定的点不能达到，其内容被滚动到最近的有效位置。两个边距的默认值是50个像素。

```
QScrollArea.ensureWidgetVisible (self, QWidget childWidget, int xMargin = 50, int yMargin = 50)
```

](index.htm)

[滚动滚动区域的内容，这样_childWidget_的](index.htm)[QScrollArea.widget](qscrollarea.html#widget)（ ）是通过以像素为单位指定页边距视口内可见_xmargin_和_ymargin_。如果指定的点不能达到，其内容被滚动到最近的有效位置。两个边距的默认值是50个像素。

这个函数中引入了Qt 4.2中。

```
bool QScrollArea.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QScrollArea.eventFilter (self, QObject, QEvent)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
bool QScrollArea.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QScrollArea.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QScrollArea.scrollContentsBy (self, int dx, int dy)
```

从重新实现[QAbstractScrollArea.scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（ ） 。

```
QScrollArea.setAlignment (self, Qt.Alignment)
```

```
QScrollArea.setWidget (self, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

设置滚动区域的_widget_。

该_widget_成为滚动区域的一个孩子，当滚动区域被删除或者当一个新的widget设定将被破坏。

widget的[autoFillBackground](qwidget.html#autoFillBackground-prop)属性将被设置为`true`。

如果滚动区域是可见的，当_widget_是说，你必须[show()](qwidget.html#show)它明确。

请注意，您必须添加的布局_widget_在打电话之前此功能，如果您以后添加吧，_widget_将不可见 - 无论何时你的[show()](qwidget.html#show)滚动区域。在这种情况下，你也可以不[show()](qwidget.html#show)该_widget_后来。

**See also** [widget](qscrollarea.html#widget)（ ） 。

```
QScrollArea.setWidgetResizable (self, bool resizable)
```

```
QSize QScrollArea.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QWidget QScrollArea.takeWidget (self)
```

[

该_QWidget_结果

消除了滚动区域的窗口小部件，并通过小部件的所有权给调用者。

](qwidget.html)

[**See also**](qwidget.html) [widget](qscrollarea.html#widget)（ ） 。

```
QWidget QScrollArea.widget (self)
```

[

返回滚动区域的窗口小部件，或者0，如果是没有的。

](qwidget.html)

[**See also**](qwidget.html) [setWidget](qscrollarea.html#setWidget)（ ） 。

```
bool QScrollArea.widgetResizable (self)
```