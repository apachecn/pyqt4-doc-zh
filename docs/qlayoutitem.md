# QLayoutItem Class Reference

## [[QtGui](index.htm) module]

该QLayoutItem类提供了一个抽象的概念，一个[QLayout](qlayout.html)操纵。[More...](#details)

通过继承[QLayout](qlayout.html)，[QSpacerItem](qspaceritem.html)和[QWidgetItem](qwidgetitem.html)。

### Methods

*   `__init__ (self, Qt.Alignment alignment = 0)`
*   `__init__ (self, QLayoutItem)`
*   `Qt.Alignment alignment (self)`
*   `QSizePolicy.ControlTypes controlTypes (self)`
*   `Qt.Orientations expandingDirections (self)`
*   `QRect geometry (self)`
*   `bool hasHeightForWidth (self)`
*   `int heightForWidth (self, int)`
*   `invalidate (self)`
*   `bool isEmpty (self)`
*   `QLayout layout (self)`
*   `QSize maximumSize (self)`
*   `int minimumHeightForWidth (self, int)`
*   `QSize minimumSize (self)`
*   `setAlignment (self, Qt.Alignment a)`
*   `setGeometry (self, QRect)`
*   `QSize sizeHint (self)`
*   `QSpacerItem spacerItem (self)`
*   `QWidget widget (self)`

* * *

## Detailed Description

该QLayoutItem类提供了一个抽象的概念，一个[QLayout](qlayout.html)操纵。

这是使用自定义布局。

提供纯虚函数返回有关布局的信息，包括，[sizeHint](qlayoutitem.html#sizeHint)（ ）[minimumSize](qlayoutitem.html#minimumSize)（ ）[maximumSize](qlayoutitem.html#maximumSize)（ ）和扩展（ ） 。

布局的几何形状可以设置和检索[setGeometry](qlayoutitem.html#setGeometry)（）和[geometry](qlayoutitem.html#geometry)（） ，其与对准[setAlignment](qlayoutitem.html#setAlignment)（）和[alignment](qlayoutitem.html#alignment)（ ） 。

[isEmpty](qlayoutitem.html#isEmpty)（ ）返回版面项目是否为空。如果具体项目是一个[QWidget](qwidget.html)，它可以使用来检索[widget](qlayoutitem.html#widget)（ ） 。同样，对于[layout](qlayoutitem.html#layout)（）和[spacerItem](qlayoutitem.html#spacerItem)（ ） 。

一些布局有宽度和高度的相互依存关系。这些可以使用表示[hasHeightForWidth](qlayoutitem.html#hasHeightForWidth)（ ）[heightForWidth](qlayoutitem.html#heightForWidth)（）和[minimumHeightForWidth](qlayoutitem.html#minimumHeightForWidth)（ ） 。如需详细说明见_Qt Quarterly_文章[Trading Height for Width](http://qt.nokia.com/doc/qq/qq04-height-for-width.html)。

* * *

## Method Documentation

```
QLayoutItem.__init__ (self, Qt.Alignment alignment = 0)
```

构造与布局项目_alignment_。不是所有的子类支持对齐。

```
QLayoutItem.__init__ (self, QLayoutItem)
```

```
Qt.Alignment QLayoutItem.alignment (self)
```

[

返回此项目的对齐方式。

](index.htm)

[**See also**](index.htm) [setAlignment](qlayoutitem.html#setAlignment)（ ） 。

```
QSizePolicy.ControlTypes QLayoutItem.controlTypes (self)
```

[](index.htm)

[返回该控件的类型（ s）为布局项目。对于](index.htm)[QWidgetItem](qwidgetitem.html)，控件类型来自于小部件的大小政策，对[QLayoutItem](qlayoutitem.html)，控制类型，从布局中的内容导出。

**See also** [QSizePolicy.controlType](qsizepolicy.html#controlType)（ ） 。

```
Qt.Orientations QLayoutItem.expandingDirections (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](index.htm)

[返回此布局的项目是否可以使更多的空间比使用](index.htm)[sizeHint](qlayoutitem.html#sizeHint)（ ） 。的值[Qt.Vertical](qt.html#Orientation-enum) or [Qt.Horizontal](qt.html#Orientation-enum)意味着它要在只有一维增长，而[Qt.Vertical](qt.html#Orientation-enum)|[Qt.Horizontal](qt.html#Orientation-enum)也就是说，它要在这两个方面的增长。

```
QRect QLayoutItem.geometry (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回复盖此布局项目的矩形。

](qrect.html)

[**See also**](qrect.html) [setGeometry](qlayoutitem.html#setGeometry)（ ） 。

```
bool QLayoutItem.hasHeightForWidth (self)
```

返回True如果此布局的首选高度依赖于它的宽度，否则返回False 。默认实现返回False 。

在支持高度宽度布局管理器重新实现这个函数。

**See also** [heightForWidth](qlayoutitem.html#heightForWidth)（）和[QWidget.heightForWidth](qwidget.html#heightForWidth)（ ） 。

```
int QLayoutItem.heightForWidth (self, int)
```

返回此布局项目的首选高度，给出的宽度_w_。

默认实现返回-1 ，表明首选高度独立于项目的宽度。使用功能[hasHeightForWidth](qlayoutitem.html#hasHeightForWidth)（）通常比调用此函数和试验-1快得多。

在支持高度宽度布局管理器重新实现这个函数。一个典型的实现将看起来像这样：

```
 int MyLayout.heightForWidth(int w) const
 {
     if (cache_dirty || cached_width != w) {
         // not all C++ compilers support "mutable"
         MyLayout *that = (MyLayout*)this;
         int h = calculateHeightForWidth(w);
         that->cached_hfw = h;
         return h;
     }
     return cached_hfw;
 }

```

缓存强烈建议，没有它的布局将需要指数时间。

**See also** [hasHeightForWidth](qlayoutitem.html#hasHeightForWidth)（ ） 。

```
QLayoutItem.invalidate (self)
```

无效在此布局项目的任何缓存信息。

```
bool QLayoutItem.isEmpty (self)
```

这种方法是抽象的，应在任何子类中重新实现。

实现在子类中返回此项目是否为空，即是否包含任何部件。

```
QLayout QLayoutItem.layout (self)
```

[](qlayout.html)

[如果这个项目是一个](qlayout.html)[QLayout](qlayout.html)，它返回一个[QLayout](qlayout.html)否则返回0。此功能提供了类型安全的铸造。

```
QSize QLayoutItem.maximumSize (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

实现在子类中返回这个项目的最大尺寸。

```
int QLayoutItem.minimumHeightForWidth (self, int)
```

返回这个窗口部件需要为给定的宽度最小高度_w_。默认实现只返回heightForWidth （_w_） 。

](qsize.html)

```
QSize QLayoutItem.minimumSize (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

实现在子类中返回该项目的最小尺寸。

```
QLayoutItem.setAlignment (self, Qt.Alignment a)
```

设置此项目的对齐方式_alignment_。

](qsize.html)

[**Note:**项目定位只支持](qsize.html)[QLayoutItem](qlayoutitem.html)子类在那里将有一个视觉效果。以外[QSpacerItem](qspaceritem.html)，它提供了布局，继承所有公共Qt类空白[QLayoutItem](qlayoutitem.html)支持项目对齐。

**See also** [alignment](qlayoutitem.html#alignment)（ ） 。

```
QLayoutItem.setGeometry (self, QRect)
```

这种方法是抽象的，应在任何子类中重新实现。

实现在子类中设置该项目的几何图形_r_。

**See also** [geometry](qlayoutitem.html#geometry)（ ） 。

```
QSize QLayoutItem.sizeHint (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

实现在子类中返回此项目的首选尺寸。

](qsize.html)

```
QSpacerItem QLayoutItem.spacerItem (self)
```

[](qspaceritem.html)

[如果这个项目是一个](qspaceritem.html)[QSpacerItem](qspaceritem.html)，它返回一个[QSpacerItem](qspaceritem.html)否则返回0。此功能提供了类型安全的铸造。

```
QWidget QLayoutItem.widget (self)
```

[](qwidget.html)

[如果这个项目是一个](qwidget.html)[QWidget](qwidget.html)，它返回一个[QWidget](qwidget.html)否则返回0。此功能提供了类型安全的铸造。