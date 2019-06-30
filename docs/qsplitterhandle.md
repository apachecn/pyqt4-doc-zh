# QSplitterHandle Class Reference

## [[QtGui](index.htm) module]

该QSplitterHandle类提供​​处理分离器的功能。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, Qt.Orientation o, QSplitter parent)`
*   `int closestLegalPosition (self, int p)`
*   `bool event (self, QEvent)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `moveSplitter (self, int p)`
*   `bool opaqueResize (self)`
*   `Qt.Orientation orientation (self)`
*   `paintEvent (self, QPaintEvent)`
*   `resizeEvent (self, QResizeEvent)`
*   `setOrientation (self, Qt.Orientation o)`
*   `QSize sizeHint (self)`
*   `QSplitter splitter (self)`

* * *

## Detailed Description

该QSplitterHandle类提供​​处理分离器的功能。

QSplitterHandle通常人们所认为的，当他们想到一个分离器。它是用于调整大小的窗口小部件的把手。

用一个典型的开发[QSplitter](qsplitter.html)永远不用担心QSplitterHandle 。提供它是为了谁想要分配器手柄，提供额外的功能，如弹出式菜单的开发。

典型的方法之一将创造分配器手柄是子类化[QSplitter](qsplitter.html)然后重新实现[QSplitter.createHandle](qsplitter.html#createHandle)（ ）实例化自定义的分配器手柄。例如，最小[QSplitter](qsplitter.html)子类可能看起来像这样：

```
 class Splitter : public [QSplitter](qsplitter.html)
 {
 public:
     Splitter([Qt](qt.html).Orientation orientation, [QWidget](qwidget.html) *parent = 0);

 protected:
     QSplitterHandle *createHandle();
 };

```

该[createHandle()](qsplitter.html#createHandle)实现简单地构造了一个自定义的分配器手柄，称为`Splitter`在这个例子中：

```
 QSplitterHandle *Splitter.createHandle()
 {
     return new SplitterHandle(orientation(), this);
 }

```

对一个给定的句柄信息可以使用类似的功能来获得[orientation](qsplitterhandle.html#orientation)（）和[opaqueResize](qsplitterhandle.html#opaqueResize)（） ，并从它的父分离器检索。像这些细节可以用来给定制处理不同的外观取决于分离器的方向。

该自定义手柄子类的复杂性取决于它需要执行的任务。一个简单的子类可能只提供一个[paintEvent](qsplitterhandle.html#paintEvent)（）实现：

```
 void SplitterHandle.paintEvent([QPaintEvent](qpaintevent.html) *event)
 {
     [QPainter](qpainter.html) painter(this);
     if (orientation() == [Qt](qt.html).Horizontal) {
         gradient.setStart(rect().left(), rect().height()/2);
         gradient.setFinalStop(rect().right(), rect().height()/2);
     } else {
         gradient.setStart(rect().width()/2, rect().top());
         gradient.setFinalStop(rect().width()/2, rect().bottom());
     }
     painter.fillRect(event->rect(), [QBrush](qbrush.html)(gradient));
 }

```

在该示例中，预定义的梯度设置不同，这取决于手柄的方向。 QSplitterHandle提供了一个合理的尺寸暗示的手柄，所以子类并不需要提供一个重新实现[sizeHint](qsplitterhandle.html#sizeHint)（ ），除非手柄有特殊尺寸要求。

* * *

## Method Documentation

```
QSplitterHandle.__init__ (self, Qt.Orientation o, QSplitter parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QSplitter](qsplitter.html)用给定的处理_orientation_和[QSplitter](qsplitter.html) _parent_。

```
int QSplitterHandle.closestLegalPosition (self, int p)
```

返回最接近的合法地位_pos_的分路器手柄。该位置从分离器的左边或顶边测量，即使是从右到左的语言。

**See also** [QSplitter.closestLegalPosition](qsplitter.html#closestLegalPosition)（）和[moveSplitter](qsplitterhandle.html#moveSplitter)（ ） 。

```
bool QSplitterHandle.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QSplitterHandle.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QSplitterHandle.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QSplitterHandle.mouseReleaseEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QSplitterHandle.moveSplitter (self, int p)
```

告诉分路器来移动该句柄来定位_pos_，它是从微件的左边缘或上边缘之间的距离。

需要注意的是_pos_也从左侧（或顶部）测量从右到左的语言。这个函数将映射_pos_调用前的适当位置[QSplitter.moveSplitter](qsplitter.html#moveSplitter)（ ） 。

**See also** [QSplitter.moveSplitter](qsplitter.html#moveSplitter)（）和[closestLegalPosition](qsplitterhandle.html#closestLegalPosition)（ ） 。

```
bool QSplitterHandle.opaqueResize (self)
```

返回True如果部件是动态调整大小（不透明） ，否则返回False 。这个值是由控制[QSplitter](qsplitter.html)。

**See also** [QSplitter.opaqueResize](qsplitter.html#opaqueResize-prop)（ ） 。

```
Qt.Orientation QSplitterHandle.orientation (self)
```

[](qt.html#Orientation-enum)

[返回手柄的方向。这通常是由传播](qt.html#Orientation-enum)[QSplitter](qsplitter.html)。

**See also** [setOrientation](qsplitterhandle.html#setOrientation)（）和[QSplitter.orientation](qsplitter.html#orientation-prop)（ ） 。

```
QSplitterHandle.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QSplitterHandle.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QSplitterHandle.setOrientation (self, Qt.Orientation o)
```

设置分离器手柄的方向向_orientation_。这通常是由传播[QSplitter](qsplitter.html)。

**See also** [orientation](qsplitterhandle.html#orientation)（）和[QSplitter.setOrientation](qsplitter.html#orientation-prop)（ ） 。

```
QSize QSplitterHandle.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QSplitter QSplitterHandle.splitter (self)
```

[

返回与此分路器句柄相关联的分离器。

](qsplitter.html)

[**See also**](qsplitter.html) [QSplitter.handle](qsplitter.html#handle)（ ） 。