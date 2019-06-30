# QWidgetItem Class Reference

## [[QtGui](index.htm) module]

该QWidgetItem类为表示一个小部件的布局项目。[More...](#details)

继承[QLayoutItem](qlayoutitem.html)。

### Methods

*   `__init__ (self, QWidget w)`
*   `Qt.Orientations expandingDirections (self)`
*   `QRect geometry (self)`
*   `bool hasHeightForWidth (self)`
*   `int heightForWidth (self, int)`
*   `bool isEmpty (self)`
*   `QSize maximumSize (self)`
*   `QSize minimumSize (self)`
*   `setGeometry (self, QRect)`
*   `QSize sizeHint (self)`
*   `QWidget widget (self)`

* * *

## Detailed Description

该QWidgetItem类为表示一个小部件的布局项目。

通常情况下，你不需要直接使用这个类。 Qt的内建布局管理器提供了以下功能布局中操纵部件：

| Class | Functions |
| --- | --- |
| [QBoxLayout](qboxlayout.html) | [addWidget()](qboxlayout.html#addWidget), [insertWidget()](qboxlayout.html#insertWidget), [setStretchFactor()](qboxlayout.html#setStretchFactor) |
| [QGridLayout](qgridlayout.html) | [addWidget()](qgridlayout.html#addWidget) |
| [QStackedLayout](qstackedlayout.html) | [addWidget()](qstackedlayout.html#addWidget), [insertWidget()](qstackedlayout.html#insertWidget), [currentWidget()](qstackedlayout.html#currentWidget), [setCurrentWidget()](qstackedlayout.html#setCurrentWidget), [widget()](qstackedlayout.html#widget) |

* * *

## Method Documentation

```
QWidgetItem.__init__ (self, QWidget w)
```

创建一个包含给定的项目_widget_。

```
Qt.Orientations QWidgetItem.expandingDirections (self)
```

[](index.htm)

[从重新实现](index.htm)[QLayoutItem.expandingDirections](qlayoutitem.html#expandingDirections)（ ） 。

```
QRect QWidgetItem.geometry (self)
```

[](qrect.html)

[从重新实现](qrect.html)[QLayoutItem.geometry](qlayoutitem.html#geometry)（ ） 。

**See also** [setGeometry](qwidgetitem.html#setGeometry)（ ） 。

```
bool QWidgetItem.hasHeightForWidth (self)
```

从重新实现[QLayoutItem.hasHeightForWidth](qlayoutitem.html#hasHeightForWidth)（ ） 。

```
int QWidgetItem.heightForWidth (self, int)
```

从重新实现[QLayoutItem.heightForWidth](qlayoutitem.html#heightForWidth)（ ） 。

```
bool QWidgetItem.isEmpty (self)
```

从重新实现[QLayoutItem.isEmpty](qlayoutitem.html#isEmpty)（ ） 。

返回True如果该控件是隐藏的，否则返回False 。

**See also** [QWidget.isHidden](qwidget.html#isHidden)（ ） 。

```
QSize QWidgetItem.maximumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.maximumSize](qlayoutitem.html#maximumSize)（ ） 。

```
QSize QWidgetItem.minimumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.minimumSize](qlayoutitem.html#minimumSize)（ ） 。

```
QWidgetItem.setGeometry (self, QRect)
```

从重新实现[QLayoutItem.setGeometry](qlayoutitem.html#setGeometry)（ ） 。

**See also** [geometry](qwidgetitem.html#geometry)（ ） 。

```
QSize QWidgetItem.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.sizeHint](qlayoutitem.html#sizeHint)（ ） 。

```
QWidget QWidgetItem.widget (self)
```

[](qwidget.html)

[从重新实现](qwidget.html)[QLayoutItem.widget](qlayoutitem.html#widget)（ ） 。

返回此项目管理的小工具。