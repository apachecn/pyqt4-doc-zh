# QSpacerItem Class Reference

## [[QtGui](index.htm) module]

该QSpacerItem类提供了一个布局空白。[More...](#details)

继承[QLayoutItem](qlayoutitem.html)。

### Methods

*   `__init__ (self, int w, int h, QSizePolicy.Policy hPolicy = QSizePolicy.Minimum, QSizePolicy.Policy vPolicy = QSizePolicy.Minimum)`
*   `__init__ (self, QSpacerItem)`
*   `changeSize (self, int w, int h, QSizePolicy.Policy hPolicy = QSizePolicy.Minimum, QSizePolicy.Policy vPolicy = QSizePolicy.Minimum)`
*   `Qt.Orientations expandingDirections (self)`
*   `QRect geometry (self)`
*   `bool isEmpty (self)`
*   `QSize maximumSize (self)`
*   `QSize minimumSize (self)`
*   `setGeometry (self, QRect)`
*   `QSize sizeHint (self)`
*   `QSpacerItem spacerItem (self)`

* * *

## Detailed Description

该QSpacerItem类提供了一个布局空白。

通常情况下，你不需要直接使用这个类。 Qt的内建布局管理器提供了以下功能操作在布局空：

| Class | Functions |
| --- | --- |
| [QHBoxLayout](qhboxlayout.html) | [addSpacing()](qboxlayout.html#addSpacing), [addStretch()](qboxlayout.html#addStretch), [insertSpacing()](qboxlayout.html#insertSpacing), [insertStretch()](qboxlayout.html#insertStretch) |
| [QGridLayout](qgridlayout.html) | [setRowMinimumHeight()](qgridlayout.html#setRowMinimumHeight), [setRowStretch()](qgridlayout.html#setRowStretch), [setColumnMinimumWidth()](qgridlayout.html#setColumnMinimumWidth), [setColumnStretch()](qgridlayout.html#setColumnStretch) |

* * *

## Method Documentation

```
QSpacerItem.__init__ (self, int w, int h, QSizePolicy.Policy hPolicy = QSizePolicy.Minimum, QSizePolicy.Policy vPolicy = QSizePolicy.Minimum)
```

构造一个首选宽度间隔项目_w_，首选高度_h_，水平尺寸的政策_hPolicy_和垂直尺寸的政策_vPolicy_。

的默认值提供一个间隙，能够舒展如果没有别的想要的空间。

```
QSpacerItem.__init__ (self, QSpacerItem)
```

```
QSpacerItem.changeSize (self, int w, int h, QSizePolicy.Policy hPolicy = QSizePolicy.Minimum, QSizePolicy.Policy vPolicy = QSizePolicy.Minimum)
```

更改此间隔的项目有首选宽度_w_，首选高度_h_，水平尺寸的政策_hPolicy_和垂直尺寸的政策_vPolicy_。

的默认值提供一个间隙，能够舒展如果没有别的想要的空间。

请注意，如果changeSize （）之后的间隔物项已被添加到一个布局被调用时，它是必要的布局无效，以使隔离物项的新大小生效。

**See also** [QSpacerItem.invalidate](qlayoutitem.html#invalidate)（ ） 。

```
Qt.Orientations QSpacerItem.expandingDirections (self)
```

[](index.htm)

[从重新实现](index.htm)[QLayoutItem.expandingDirections](qlayoutitem.html#expandingDirections)（ ） 。

```
QRect QSpacerItem.geometry (self)
```

[](qrect.html)

[从重新实现](qrect.html)[QLayoutItem.geometry](qlayoutitem.html#geometry)（ ） 。

**See also** [setGeometry](qspaceritem.html#setGeometry)（ ） 。

```
bool QSpacerItem.isEmpty (self)
```

从重新实现[QLayoutItem.isEmpty](qlayoutitem.html#isEmpty)（ ） 。

返回True。

```
QSize QSpacerItem.maximumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.maximumSize](qlayoutitem.html#maximumSize)（ ） 。

```
QSize QSpacerItem.minimumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.minimumSize](qlayoutitem.html#minimumSize)（ ） 。

```
QSpacerItem.setGeometry (self, QRect)
```

从重新实现[QLayoutItem.setGeometry](qlayoutitem.html#setGeometry)（ ） 。

**See also** [geometry](qspaceritem.html#geometry)（ ） 。

```
QSize QSpacerItem.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.sizeHint](qlayoutitem.html#sizeHint)（ ） 。

```
QSpacerItem QSpacerItem.spacerItem (self)
```

[](qspaceritem.html)

[从重新实现](qspaceritem.html)[QLayoutItem.spacerItem](qlayoutitem.html#spacerItem)（ ） 。

返回一个指向该对象。