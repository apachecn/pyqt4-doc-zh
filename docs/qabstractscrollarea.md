# QAbstractScrollArea Class Reference

## [[QtGui](index.htm) module]

该QAbstractScrollArea中小工具提供了点播滚动条滚动的区域。[More...](#details)

继承[QFrame](qframe.html)。

通过继承[QAbstractItemView](qabstractitemview.html)，[QGraphicsView](qgraphicsview.html)，[QMdiArea](qmdiarea.html)，[QPlainTextEdit](qplaintextedit.html)，[QScrollArea](qscrollarea.html)和[QTextEdit](qtextedit.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `addScrollBarWidget (self, QWidget widget, Qt.Alignment alignment)`
*   `contextMenuEvent (self, QContextMenuEvent)`
*   `QWidget cornerWidget (self)`
*   `dragEnterEvent (self, QDragEnterEvent)`
*   `dragLeaveEvent (self, QDragLeaveEvent)`
*   `dragMoveEvent (self, QDragMoveEvent)`
*   `dropEvent (self, QDropEvent)`
*   `bool event (self, QEvent)`
*   `QScrollBar horizontalScrollBar (self)`
*   `Qt.ScrollBarPolicy horizontalScrollBarPolicy (self)`
*   `keyPressEvent (self, QKeyEvent)`
*   `QSize maximumViewportSize (self)`
*   `QSize minimumSizeHint (self)`
*   `mouseDoubleClickEvent (self, QMouseEvent)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `paintEvent (self, QPaintEvent)`
*   `resizeEvent (self, QResizeEvent)`
*   `list-of-QWidget scrollBarWidgets (self, Qt.Alignment alignment)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `setCornerWidget (self, QWidget widget)`
*   `setHorizontalScrollBar (self, QScrollBar scrollbar)`
*   `setHorizontalScrollBarPolicy (self, Qt.ScrollBarPolicy)`
*   `setupViewport (self, QWidget viewport)`
*   `setVerticalScrollBar (self, QScrollBar scrollbar)`
*   `setVerticalScrollBarPolicy (self, Qt.ScrollBarPolicy)`
*   `setViewport (self, QWidget widget)`
*   `setViewportMargins (self, int left, int top, int right, int bottom)`
*   `setViewportMargins (self, QMargins margins)`
*   `QSize sizeHint (self)`
*   `QScrollBar verticalScrollBar (self)`
*   `Qt.ScrollBarPolicy verticalScrollBarPolicy (self)`
*   `QWidget viewport (self)`
*   `bool viewportEvent (self, QEvent)`
*   `wheelEvent (self, QWheelEvent)`

* * *

## Detailed Description

该QAbstractScrollArea中小工具提供了点播滚动条滚动的区域。

QAbstractScrollArea中是一个滚动区域的低级别的抽象。该区域提供了一个中央部件称为视口，其中，所述区域中的内容将被滚动（即，内容的可见部分在视口中呈现） 。

旁边的视口是一个垂直滚动条，以下是一个水平滚动条。当所有的区域的内容适合在视口中，每个滚动条可以是可见还是隐藏取决于滚动条的[Qt.ScrollBarPolicy](qt.html#ScrollBarPolicy-enum)。当一个隐藏滚动条，视口扩展，以涵盖所有可用空间。当一个滚动条再次变为可见，视口缩小，以腾出空间给滚动条。

这是可能的预定周围的视口边缘区域，看[setViewportMargins](qabstractscrollarea.html#setViewportMargins)（ ） 。该功能主要是用来放置一个[QHeaderView](qheaderview.html)小工具上方或旁边的滚动区域。 QAbstractScrollArea中的子类应实现的利润。

当继承QAbstractScrollArea中，你需要做到以下几点：

*   Control the scroll bars by setting their range, value, page step, and tracking their movements.
*   Draw the contents of the area in the viewport according to the values of the scroll bars.
*   Handle events received by the viewport in [viewportEvent](qabstractscrollarea.html#viewportEvent)() - notably resize events.
*   Use `viewport-&gt;update()` to update the contents of the viewport instead of [update()](qwidget.html#update) as all painting operations take place on the viewport.

随着滚动条政策[Qt.ScrollBarAsNeeded](qt.html#ScrollBarPolicy-enum)（默认值） ， QAbstractScrollArea中显示滚动条时，他们提供了一个非零滚动范围，否则隐藏它们。

每当视口接收到一个resize事件或内容的大小变化的滚动条和视口应更新。视口还需要当滚动条值的变化被更新。滚动条的初始值时的区域接收到新的内容经常被设置。

我们举一个简单的例子，在此我们实现了一个滚动区域，可以滚动任何[QWidget](qwidget.html)。我们做插件的视口的孩子，这样，我们就不必计算控件绘制的哪一部分，但可以简单地移动小部件[QWidget.move](qwidget.html#pos-prop)（ ） 。当区域内容或视口大小的变化，我们做以下：

```
     [QSize](qsize.html) areaSize = viewport()->size();
     [QSize](qsize.html)  widgetSize = widget->size();

     verticalScrollBar()->setPageStep(areaSize.height());
     horizontalScrollBar()->setPageStep(areaSize.width());
     verticalScrollBar()->setRange(0, widgetSize.height() - areaSize.height());
     horizontalScrollBar()->setRange(0, widgetSize.width() - areaSize.width());
     updateWidgetPosition();

```

当滚动条改变的值，我们需要更新的窗口小部件的位置，也就是说，找到小部件是在视口中要绘制的部分：

```
     int hvalue = horizontalScrollBar()->value();
     int vvalue = verticalScrollBar()->value();
     [QPoint](qpoint.html) topLeft = viewport()->rect().topLeft();

     widget->move(topLeft.x() - hvalue, topLeft.y() - vvalue);

```

为了跟踪滚动条的动作，重新实现虚函数[scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（ ） 。为了微调滚动行为，连接到滚动条的[QAbstractSlider.actionTriggered](qabstractslider.html#actionTriggered)（）信号，并调整[QAbstractSlider.sliderPosition](qabstractslider.html#sliderPosition-prop)如你所愿。

为方便起见， QAbstractScrollArea中，使在虚拟提供的所有视口的事件[viewportEvent](qabstractscrollarea.html#viewportEvent)（）处理。[QWidget](qwidget.html)的专门的处理程序重新映射到的情况下，这是有道理的视口的事件。在重新映射专门的处理程序是：[paintEvent](qabstractscrollarea.html#paintEvent)（ ）[mousePressEvent](qabstractscrollarea.html#mousePressEvent)（ ）[mouseReleaseEvent](qabstractscrollarea.html#mouseReleaseEvent)（ ）[mouseDoubleClickEvent](qabstractscrollarea.html#mouseDoubleClickEvent)（ ）[mouseMoveEvent](qabstractscrollarea.html#mouseMoveEvent)（ ）[wheelEvent](qabstractscrollarea.html#wheelEvent)（ ）[dragEnterEvent](qabstractscrollarea.html#dragEnterEvent)（ ）[dragMoveEvent](qabstractscrollarea.html#dragMoveEvent)（ ）[dragLeaveEvent](qabstractscrollarea.html#dragLeaveEvent)（ ）[dropEvent](qabstractscrollarea.html#dropEvent)（ ）[contextMenuEvent](qabstractscrollarea.html#contextMenuEvent)（）和[resizeEvent](qabstractscrollarea.html#resizeEvent)（ ） 。

[QScrollArea](qscrollarea.html)，它继承QAbstractScrollArea中，提供了平滑滚动的任何[QWidget](qwidget.html)（即，窗口小部件是由像素滚动的像素） 。你只需要继承QAbstractScrollArea中，如果你需要更专业的行为。这是，例如，真实的，如果区域的整个内容是不适合于被绘制在[QWidget](qwidget.html)或者，如果你不想平滑滚动。

* * *

## Method Documentation

```
QAbstractScrollArea.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个视口。

该_parent_参数被发送到[QWidget](qwidget.html)构造函数。

```
QAbstractScrollArea.addScrollBarWidget (self, QWidget widget, Qt.Alignment alignment)
```

该_widget_说法有它的所有权转移给Qt的。

添加_widget_作为一个滚动条控件在被指定的位置_alignment_。

滚动条的窗口小部件显示旁边的水平或垂直滚动条，并可以置于其两侧。如果你想滚动条控件在始终可见，设置scrollBarPolicy为相应的滚动条`AlwaysOn`。

_alignment_必须是1 Qt.Alignleft的和[Qt.AlignRight](qt.html#AlignmentFlag-enum)，它映射到水平滚动条，或[Qt.AlignTop](qt.html#AlignmentFlag-enum)和[Qt.AlignBottom](qt.html#AlignmentFlag-enum)，它映射到垂直滚动条。

滚动条控件可以通过重新养育的小工具或删除其删除。它也有可能隐藏有一个小部件[QWidget.hide](qwidget.html#hide)（ ）

滚动条控件将被调整，以适应滚动条的几何形状为当前样式。下面介绍的滚动条部件的水平滚动条上的情况：

小部件的高度将被设置为相匹配的滚动条的高度。控制部件的宽度，使用QWidget.setMinimumWidth和QWidget.setMaximumWidth ，或实施[QWidget.sizeHint](qwidget.html#sizeHint-prop)（）和set水平尺寸的政策。如果你想有一个方形小部件，请致电QStyle.pixelMetric （[QStyle.PM_ScrollBarExtent](qstyle.html#PixelMetric-enum)），并设置宽度为这个值。

这个函数中引入了Qt 4.2中。

**See also** [scrollBarWidgets](qabstractscrollarea.html#scrollBarWidgets)（ ） 。

```
QAbstractScrollArea.contextMenuEvent (self, QContextMenuEvent)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

此事件处理程序可以重新实现在子类中获得上下文菜单事件的[viewport](qabstractscrollarea.html#viewport)（ ）小部件。该事件被传递中_e_。

**See also** [QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
QWidget QAbstractScrollArea.cornerWidget (self)
```

[

返回在两个滚动条之间的拐角处小部件。

默认情况下，无角小部件存在。

这个函数中引入了Qt 4.2中。

](qwidget.html)

[**See also**](qwidget.html) [setCornerWidget](qabstractscrollarea.html#setCornerWidget)（ ） 。

```
QAbstractScrollArea.dragEnterEvent (self, QDragEnterEvent)
```

从重新实现[QWidget.dragEnterEvent](qwidget.html#dragEnterEvent)（ ） 。

此事件处理程序可以重新实现在子类中接收拖动输入事件（传入_event_） ，用于[viewport](qabstractscrollarea.html#viewport)（ ）小部件。

**See also** [QWidget.dragEnterEvent](qwidget.html#dragEnterEvent)（ ） 。

```
QAbstractScrollArea.dragLeaveEvent (self, QDragLeaveEvent)
```

从重新实现[QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

此事件处理程序可以重新实现在子类中接收拖动假事件（传入_event_） ，用于[viewport](qabstractscrollarea.html#viewport)（ ）小部件。

**See also** [QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

```
QAbstractScrollArea.dragMoveEvent (self, QDragMoveEvent)
```

从重新实现[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

此事件处理程序可以重新实现在子类中接收拖动移动事件（传入_event_） ，用于[viewport](qabstractscrollarea.html#viewport)（ ）小部件。

**See also** [QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

```
QAbstractScrollArea.dropEvent (self, QDropEvent)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

此事件处理程序可以重新实现在子类中接收拖放事件（传入_event_） ，用于[viewport](qabstractscrollarea.html#viewport)（ ）小部件。

**See also** [QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

```
bool QAbstractScrollArea.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

这是主要的事件处理程序[QAbstractScrollArea](qabstractscrollarea.html)窗口小部件（_not_滚动区域[viewport](qabstractscrollarea.html#viewport)（））。指定_event_是，可能需要将其转换为相应的类视其类型而一个普通的事件对象。

**See also** [QEvent.type](qevent.html#type)（ ） 。

```
QScrollBar QAbstractScrollArea.horizontalScrollBar (self)
```

[

返回水平滚动条。

](qscrollbar.html)

[**See also**](qscrollbar.html) [setHorizontalScrollBar](qabstractscrollarea.html#setHorizontalScrollBar)（ ）[horizontalScrollBarPolicy](qabstractscrollarea.html#horizontalScrollBarPolicy-prop)和[verticalScrollBar](qabstractscrollarea.html#verticalScrollBar)（ ） 。

```
Qt.ScrollBarPolicy QAbstractScrollArea.horizontalScrollBarPolicy (self)
```

[

```
QAbstractScrollArea.keyPressEvent (self, QKeyEvent)
```

](qt.html#ScrollBarPolicy-enum)

[从重新实现](qt.html#ScrollBarPolicy-enum)[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

这个函数被调用的键盘事件_e_当按键发生。它可以处理上一页，下一页，向上，向下，向左和向右，并忽略所有其他按键。

```
QSize QAbstractScrollArea.maximumViewportSize (self)
```

[

返回视口的大小，犹如滚动条没有有效的滚动范围。

](qsize.html)

```
QSize QAbstractScrollArea.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QAbstractScrollArea.mouseDoubleClickEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

此事件处理程序可以重新实现在子类中接收鼠标双击事件的[viewport](qabstractscrollarea.html#viewport)（ ）小部件。该事件被传递中_e_。

**See also** [QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QAbstractScrollArea.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

此事件处理程序可以重新实现在子类中接收鼠标移动事件的[viewport](qabstractscrollarea.html#viewport)（ ）小部件。该事件被传递中_e_。

**See also** [QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QAbstractScrollArea.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

此事件处理程序可以重新实现在子类中接收鼠标按下事件的[viewport](qabstractscrollarea.html#viewport)（ ）小部件。该事件被传递中_e_。

**See also** [QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QAbstractScrollArea.mouseReleaseEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

此事件处理程序可以重新实现在子类中接收鼠标释放事件的[viewport](qabstractscrollarea.html#viewport)（ ）小部件。该事件被传递中_e_。

**See also** [QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QAbstractScrollArea.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

此事件处理程序可以重新实现在子类来接收绘制事件（在传递_event_） ，用于[viewport](qabstractscrollarea.html#viewport)（ ）小部件。

**Note:**如果你打开一个画家，一定要打开它的[viewport](qabstractscrollarea.html#viewport)（ ） 。

**See also** [QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QAbstractScrollArea.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

此事件处理程序可以重新实现在子类中获得的resize事件（传入_event_） ，用于[viewport](qabstractscrollarea.html#viewport)（ ）小部件。

当resizeEvent （ ）被调用时，视口已经拥有了新的几何体：它的新的大小是通过访问[QResizeEvent.size](qresizeevent.html#size)（ ）函数，并通过旧的大小[QResizeEvent.oldSize](qresizeevent.html#oldSize)（ ） 。

**See also** [QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
list-of-QWidget QAbstractScrollArea.scrollBarWidgets (self, Qt.Alignment alignment)
```

返回当前设置的滚动条窗口小部件的列表。_alignment_可以是四个位置标记的任何组合。

这个函数中引入了Qt 4.2中。

**See also** [addScrollBarWidget](qabstractscrollarea.html#addScrollBarWidget)（ ） 。

```
QAbstractScrollArea.scrollContentsBy (self, int dx, int dy)
```

当滚动条被移动这个虚拟处理器被调用_dx_，_dy_，因此视域的内容应该相应地滚动。

默认实现调用[update](qwidget.html#update)（）对整个[viewport](qabstractscrollarea.html#viewport)（ ） ，子类可以重新实现此处理函数优化的目的，或者 - 像[QScrollArea](qscrollarea.html) - 以小部件移动内容。参数_dx_和_dy_都是为了方便起见，让类知道多少，应该进行滚动（很有用，例如做像素变化时） 。您可能一样好忽略这些值，并直接移动到的位置的滚动条显示。

以编程方式滚动调用这个函数是一个错误，使用滚动条来代替（例如，通过调用[QScrollBar.setValue](qabstractslider.html#value-prop)（ ）直接） 。

```
QAbstractScrollArea.setCornerWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置两个滚动条之间的小部件在角落里为_widget_。

您可能还需要滚动条模式中的至少一个设置为`AlwaysOn`。

路过0显示没有插件的角落里。

以前的任何角落widget被隐藏。

您可致电setCornerWidget （ ）使用相同的部件在不同的时间。

这里设置的所有部件将由滚动区域，当它被摧毁，除非你单独reparent小部件设置一些其他角落部件（或0 ）后删除。

任何_newly_自定义插件应该没有电流父。

默认情况下，无角小部件存在。

这个函数中引入了Qt 4.2中。

**See also** [cornerWidget](qabstractscrollarea.html#cornerWidget)（ ）[horizontalScrollBarPolicy](qabstractscrollarea.html#horizontalScrollBarPolicy-prop)和[horizontalScrollBarPolicy](qabstractscrollarea.html#horizontalScrollBarPolicy-prop)。

```
QAbstractScrollArea.setHorizontalScrollBar (self, QScrollBar scrollbar)
```

该_scrollbar_说法有它的所有权转移给Qt的。

替换现有的水平滚动条_scrollBar_，并设置新的滚动条上的所有前滚动条的滑块性能。前者滚动条，然后删除。

[QAbstractScrollArea](qabstractscrollarea.html)已经默认提供水平和垂直滚动条。你可以调用这个函数来与自己的自定义滚动条替换默认的水平滚动条。

这个函数中引入了Qt 4.2中。

**See also** [horizontalScrollBar](qabstractscrollarea.html#horizontalScrollBar)（）和[setVerticalScrollBar](qabstractscrollarea.html#setVerticalScrollBar)（ ） 。

```
QAbstractScrollArea.setHorizontalScrollBarPolicy (self, Qt.ScrollBarPolicy)
```

```
QAbstractScrollArea.setupViewport (self, QWidget viewport)
```

这种方法也是一个Qt槽与C + +的签名`void setupViewport(QWidget *)`。

这个槽被调用者[QAbstractScrollArea](qabstractscrollarea.html)后setViewport （_viewport_）被调用。在子类重新实现此功能[QAbstractScrollArea](qabstractscrollarea.html)初始化新_viewport_之前就被采用。

**See also** [setViewport](qabstractscrollarea.html#setViewport)（ ） 。

```
QAbstractScrollArea.setVerticalScrollBar (self, QScrollBar scrollbar)
```

该_scrollbar_说法有它的所有权转移给Qt的。

替换现有的垂直滚动条_scrollBar_，并设置新的滚动条上的所有前滚动条的滑块性能。前者滚动条，然后删除。

[QAbstractScrollArea](qabstractscrollarea.html)已经默认提供垂直和水平滚动条。你可以调用这个函数来与自己的自定义滚动条替换默认的垂直滚动条。

这个函数中引入了Qt 4.2中。

**See also** [verticalScrollBar](qabstractscrollarea.html#verticalScrollBar)（）和[setHorizontalScrollBar](qabstractscrollarea.html#setHorizontalScrollBar)（ ） 。

```
QAbstractScrollArea.setVerticalScrollBarPolicy (self, Qt.ScrollBarPolicy)
```

```
QAbstractScrollArea.setViewport (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置要在给定的视_widget_。该[QAbstractScrollArea](qabstractscrollarea.html)将采取的特定所有权_widget_。

If _widget_为0时，[QAbstractScrollArea](qabstractscrollarea.html)将分配一个新的[QWidget](qwidget.html)比如为视口。

这个函数中引入了Qt 4.2中。

**See also** [viewport](qabstractscrollarea.html#viewport)（ ） 。

```
QAbstractScrollArea.setViewportMargins (self, int left, int top, int right, int bottom)
```

周围设置滚动区域的边距_left_，_top_，_right_和_bottom_。这是用于诸如电子表格“锁定”的行和列是有用的。边际空间留白;放小部件在未使用的区域。

注意，该功能通常被称为由[QTreeView](qtreeview.html)和[QTableView](qtableview.html)，所以利润必须由实施[QAbstractScrollArea](qabstractscrollarea.html)子类。另外，如果子类是在项目视图中使用，他们不应该调用这个函数。

默认情况下所有的利润都为零。

```
QAbstractScrollArea.setViewportMargins (self, QMargins margins)
```

Sets _margins_周围的滚动区域。这是用于诸如电子表格“锁定”的行和列是有用的。边际空间留白;放小部件在未使用的区域。

默认情况下所有的利润都为零。

此功能被引入Qt的4.6 。

```
QSize QAbstractScrollArea.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QScrollBar QAbstractScrollArea.verticalScrollBar (self)
```

[

返回垂直滚动条。

](qscrollbar.html)

[**See also**](qscrollbar.html) [setVerticalScrollBar](qabstractscrollarea.html#setVerticalScrollBar)（ ）[verticalScrollBarPolicy](qabstractscrollarea.html#verticalScrollBarPolicy-prop)和[horizontalScrollBar](qabstractscrollarea.html#horizontalScrollBar)（ ） 。

```
Qt.ScrollBarPolicy QAbstractScrollArea.verticalScrollBarPolicy (self)
```

[](qt.html#ScrollBarPolicy-enum)

```
QWidget QAbstractScrollArea.viewport (self)
```

[

返回视口部件。

](qwidget.html)

[使用](qwidget.html)[QScrollArea.widget](qscrollarea.html#widget)（ ）函数来检索视角构件的内容。

**See also** [setViewport](qabstractscrollarea.html#setViewport)（）和[QScrollArea.widget](qscrollarea.html#widget)（ ） 。

```
bool QAbstractScrollArea.viewportEvent (self, QEvent)
```

主要的事件处理程序的滚动区域（[viewport](qabstractscrollarea.html#viewport)（ ）小部件） 。它处理_event_指定的，并可以由子类调用，以提供合理的默认行为。

返回True，表示该事件已处理的事件系统，且不需要进一步处理，否则返回False，表示该事件应进一步传播。

您可以在子类中重新实现这个功能，但是我们建议您使用一个专门的事件处理程序来代替。

专门处理程序视口的事件是：[paintEvent](qabstractscrollarea.html#paintEvent)（ ）[mousePressEvent](qabstractscrollarea.html#mousePressEvent)（ ）[mouseReleaseEvent](qabstractscrollarea.html#mouseReleaseEvent)（ ）[mouseDoubleClickEvent](qabstractscrollarea.html#mouseDoubleClickEvent)（ ）[mouseMoveEvent](qabstractscrollarea.html#mouseMoveEvent)（ ）[wheelEvent](qabstractscrollarea.html#wheelEvent)（ ）[dragEnterEvent](qabstractscrollarea.html#dragEnterEvent)（ ）[dragMoveEvent](qabstractscrollarea.html#dragMoveEvent)（ ）[dragLeaveEvent](qabstractscrollarea.html#dragLeaveEvent)（ ）[dropEvent](qabstractscrollarea.html#dropEvent)（ ）[contextMenuEvent](qabstractscrollarea.html#contextMenuEvent)（）和[resizeEvent](qabstractscrollarea.html#resizeEvent)（ ） 。

```
QAbstractScrollArea.wheelEvent (self, QWheelEvent)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

此事件处理程序可以在子类来接收滚轮事件的重新实现[viewport](qabstractscrollarea.html#viewport)（ ）小部件。该事件被传递中_e_。

**See also** [QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。