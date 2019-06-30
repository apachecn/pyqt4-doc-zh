# QCursor Class Reference

## [[QtGui](index.htm) module]

该QCursor类提供一个鼠标光标具有任意形状。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, Qt.CursorShape shape)`
*   `__init__ (self, QBitmap bitmap, QBitmap mask, int hotX = -1, int hotY = -1)`
*   `__init__ (self, QPixmap pixmap, int hotX = -1, int hotY = -1)`
*   `__init__ (self, QCursor cursor)`
*   `__init__ (self, QVariant variant)`
*   `QBitmap bitmap (self)`
*   `QPoint hotSpot (self)`
*   `QBitmap mask (self)`
*   `QPixmap pixmap (self)`
*   `setShape (self, Qt.CursorShape newShape)`
*   `Qt.CursorShape shape (self)`

### Static Methods

*   `QPoint pos ()`
*   `setPos (int x, int y)`
*   `setPos (QPoint p)`

* * *

## Detailed Description

A [Qt.CursorShape](qt.html#CursorShape-enum)可用于每当一个[QCursor](qcursor.html)预计。

该QCursor类提供一个鼠标光标具有任意形状。

这个类主要用来创建与特定的小部件关联的鼠标光标，并获取和设置鼠标光标的位置。

Qt拥有一系列标准光标形状，而是根据你也可以自定义光标形状[QBitmap](qbitmap.html)，口罩和热点。

一个游标，窗口小部件，使用相关联[QWidget.setCursor](qwidget.html#cursor-prop)（ ） 。以一个游标的所有部件（通常为很短的时间内） ，使用关联[QApplication.setOverrideCursor](qapplication.html#setOverrideCursor)（ ） 。

要设置光标形状的使用[QCursor.setShape](qcursor.html#setShape)（ ）或使用QCursor构造函数需要的形状作为参数，也可以使用在定义的预定义光标中的一个[Qt.CursorShape](qt.html#CursorShape-enum)枚举。

如果你想创建一个游标与自己的位图，或者使用QCursor构造函数，它接受一个位图和口罩或这需要一个像素图作为参数的构造函数。

设置或获取鼠标光标的位置使用静态方法[QCursor.pos](qcursor.html#pos)（）和[QCursor.setPos](qcursor.html#setPos)（ ） 。

**Note:**这是可能的前创建QCursor[QApplication](qapplication.html)，但它不是只是作为一个佔位之后创建一个真正的QCursor有用[QApplication](qapplication.html)。尝试使用之前创建的QCursor[QApplication](qapplication.html)会导致系统崩溃。

### A Note for X11 Users

在X11上， Qt支持[Xcursor](http://www.xfree86.org/4.3.0/Xcursor.3.html)库，它允许全彩色图标主题。下表显示了用于每个游标名[Qt.CursorShape](qt.html#CursorShape-enum)值。如果游标不能使用下面的名称被发现，一个标准的X11光标将被代替使用。注： X11并没有对所有可能提供适当的游标[Qt.CursorShape](qt.html#CursorShape-enum)值。这可能是一些游标将取自Xcursor主题，而另一些将使用的内部位图的光标。

| Shape | [Qt.CursorShape](qt.html#CursorShape-enum) Value | Cursor Name | Shape | [Qt.CursorShape](qt.html#CursorShape-enum) Value | Cursor Name |
| --- | --- | --- | --- | --- | --- |
| ![](../img/cursor-arrow.png) | [Qt.ArrowCursor](qt.html#CursorShape-enum) | `left_ptr` | ![](../img/cursor-sizev.png) | [Qt.SizeVerCursor](qt.html#CursorShape-enum) | `size_ver` |
| ![](../img/cursor-uparrow.png) | [Qt.UpArrowCursor](qt.html#CursorShape-enum) | `up_arrow` | ![](../img/cursor-sizeh.png) | [Qt.SizeHorCursor](qt.html#CursorShape-enum) | `size_hor` |
| ![](../img/cursor-cross.png) | [Qt.CrossCursor](qt.html#CursorShape-enum) | `cross` | ![](../img/cursor-sizeb.png) | [Qt.SizeBDiagCursor](qt.html#CursorShape-enum) | `size_bdiag` |
| ![](../img/cursor-ibeam.png) | [Qt.IBeamCursor](qt.html#CursorShape-enum) | `ibeam` | ![](../img/cursor-sizef.png) | [Qt.SizeFDiagCursor](qt.html#CursorShape-enum) | `size_fdiag` |
| ![](../img/cursor-wait.png) | [Qt.WaitCursor](qt.html#CursorShape-enum) | `wait` | ![](../img/cursor-sizeall.png) | [Qt.SizeAllCursor](qt.html#CursorShape-enum) | `size_all` |
| ![](../img/cursor-busy.png) | [Qt.BusyCursor](qt.html#CursorShape-enum) | `left_ptr_watch` | ![](../img/cursor-vsplit.png) | [Qt.SplitVCursor](qt.html#CursorShape-enum) | `split_v` |
| ![](../img/cursor-forbidden.png) | [Qt.ForbiddenCursor](qt.html#CursorShape-enum) | `forbidden` | ![](../img/cursor-hsplit.png) | [Qt.SplitHCursor](qt.html#CursorShape-enum) | `split_h` |
| ![](../img/cursor-hand.png) | [Qt.PointingHandCursor](qt.html#CursorShape-enum) | `pointing_hand` | ![](../img/cursor-openhand.png) | [Qt.OpenHandCursor](qt.html#CursorShape-enum) | `openhand` |
| ![](../img/cursor-whatsthis.png) | [Qt.WhatsThisCursor](qt.html#CursorShape-enum) | `whats_this` | ![](../img/cursor-closedhand.png) | [Qt.ClosedHandCursor](qt.html#CursorShape-enum) | `closedhand` |
|  | [Qt.DragMoveCursor](qt.html#CursorShape-enum) | `dnd-move` or `move` |  | [Qt.DragCopyCursor](qt.html#CursorShape-enum) | `dnd-copy` or `copy` |
|  | [Qt.DragLinkCursor](qt.html#CursorShape-enum) | `dnd-link` or `link` |

* * *

## Method Documentation

```
QCursor.__init__ (self)
```

构造一个游标默认的箭头形状。

```
QCursor.__init__ (self, Qt.CursorShape shape)
```

构造一个光标指定_shape_。

See [Qt.CursorShape](qt.html#CursorShape-enum)对于形状的列表。

**See also** [setShape](qcursor.html#setShape)（ ） 。

```
QCursor.__init__ (self, QBitmap bitmap, QBitmap mask, int hotX = -1, int hotY = -1)
```

构造一个自定义位图的光标。

_bitmap_和_mask_补位图。_hotX_和_hotY_定义游标的热点。

If _hotX_是否定的，它被设置为`bitmap().width()/2`。如果_hotY_是否定的，它被设置为`bitmap().height()/2`。

光标_bitmap_（B）和_mask_（M ）位组合是这样的：

*   B=1 and M=1 gives black.
*   B=0 and M=1 gives white.
*   B=0 and M=0 gives transparent.
*   B=1 and M=0 gives an XOR'd result under Windows, undefined results on all other platforms.

使用全局Qt的颜色[Qt.color0](qt.html#GlobalColor-enum)绘制0像素和[Qt.color1](qt.html#GlobalColor-enum)绘制1像素的位图。

有效的光标的大小取决于显示硬件（或底层窗口系统） 。我们建议采用32 ×32的游标，因为这个大小是所有平台都支持。有些平台还支持16×16 ， 48 ×480和64×64的游标。

**Note:**在Windows CE上，光标的大小是固定的。如果像素映像大于系统的大小，它会被缩放。

**See also** [QBitmap.QBitmap](qbitmap.html#QBitmap)（）和[QBitmap.setMask](qpixmap.html#setMask)（ ） 。

```
QCursor.__init__ (self, QPixmap pixmap, int hotX = -1, int hotY = -1)
```

构造一个自定义的像素图的光标。

_pixmap_是图像。这是通常给它一个口罩使用（集[QPixmap.setMask](qpixmap.html#setMask)（））。_hotX_和_hotY_定义游标的热点。

If _hotX_是否定的，它被设置为`pixmap().width()/2`。如果_hotY_是否定的，它被设置为`pixmap().height()/2`。

有效的光标的大小取决于显示硬件（或底层窗口系统） 。我们建议采用32 ×32的游标，因为这个大小是所有平台都支持。有些平台还支持16×16 ， 48 ×480和64×64的游标。

**Note:**在Windows CE上，光标的大小是固定的。如果像素映像大于系统的大小，它会被缩放。

**See also** [QPixmap.QPixmap](qpixmap.html#QPixmap)（）和[QPixmap.setMask](qpixmap.html#setMask)（ ） 。

```
QCursor.__init__ (self, QCursor cursor)
```

构造游标的副本_c_。

```
QCursor.__init__ (self, QVariant variant)
```

构造一个Qt光标从给定的Windows_cursor_。

**Warning:**此功能仅适用于Windows。

**See also** [handle](qcursor.html#handle)（ ） 。

```
QBitmap QCursor.bitmap (self)
```

[

返回光标的位图，或者0 ，如果它是标准的游标之一。

](qbitmap.html)

```
QPoint QCursor.hotSpot (self)
```

[

返回光标的热点，或（ 0 ， 0 ） ，如果它是标准的游标之一。

](qpoint.html)

```
QBitmap QCursor.mask (self)
```

[

返回光标的位图掩码，或者0 ，如果它是标准的游标之一。

](qbitmap.html)

```
QPixmap QCursor.pixmap (self)
```

[

返回游标像素图。这是唯一有效的，如果游标是一个像素图的光标。

](qpixmap.html)

```
QPoint QCursor.pos ()
```

[

返回光标（热点）在全球屏幕坐标的位置。

](qpoint.html)

[您可以致电](qpoint.html)[QWidget.mapFromGlobal](qwidget.html#mapFromGlobal)（）把它翻译出来给小部件的坐标。

**See also** [setPos](qcursor.html#setPos)（ ）[QWidget.mapFromGlobal](qwidget.html#mapFromGlobal)（）和[QWidget.mapToGlobal](qwidget.html#mapToGlobal)（ ） 。

```
QCursor.setPos (int x, int y)
```

移动光标（热点）向全球屏幕位置（_x_，_y_） 。

您可以致电[QWidget.mapToGlobal](qwidget.html#mapToGlobal)（ ）翻译小工具坐标转换为全局屏幕坐标。

**See also** [pos](qcursor.html#pos)（ ）[QWidget.mapFromGlobal](qwidget.html#mapFromGlobal)（）和[QWidget.mapToGlobal](qwidget.html#mapToGlobal)（ ） 。

```
QCursor.setPos (QPoint p)
```

这是一个重载函数。

移动光标（热点），以点在全局屏幕位置_p_。

```
QCursor.setShape (self, Qt.CursorShape newShape)
```

将光标设置到确定的形状_shape_。

See [Qt.CursorShape](qt.html#CursorShape-enum)为光标形状列表。

**See also** [shape](qcursor.html#shape)（ ） 。

```
Qt.CursorShape QCursor.shape (self)
```

[](qt.html#CursorShape-enum)

[返回光标形状标识符。返回值是一个](qt.html#CursorShape-enum)[Qt.CursorShape](qt.html#CursorShape-enum)枚举值（转换为int ） 。

**See also** [setShape](qcursor.html#setShape)（ ） 。