# QGraphicsObject Class Reference

## [[QtGui](index.htm) module]

该QGraphicsObject类提供了一个基类，用于需要信号的所有图形项目，插槽和属性。[More...](#details)

继承[QObject](qobject.html)和[QGraphicsItem](qgraphicsitem.html)。

通过继承[QDeclarativeItem](qdeclarativeitem.html)，[QGraphicsSvgItem](qgraphicssvgitem.html)，[QGraphicsTextItem](qgraphicstextitem.html)和[QGraphicsWidget](qgraphicswidget.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None)`
*   `grabGesture (self, Qt.GestureType type, Qt.GestureFlags flags = Qt.GestureFlags(0))`
*   `ungrabGesture (self, Qt.GestureType type)`
*   `updateMicroFocus (self)`

### Qt Signals

*   `void enabledChanged ()`
*   `void opacityChanged ()`
*   `void parentChanged ()`
*   `void rotationChanged ()`
*   `void scaleChanged ()`
*   `void visibleChanged ()`
*   `void xChanged ()`
*   `void yChanged ()`
*   `void zChanged ()`

* * *

## Detailed Description

该QGraphicsObject类提供了一个基类，用于需要信号的所有图形项目，插槽和属性。

这个类扩展了[QGraphicsItem](qgraphicsitem.html)同[QObject](qobject.html)的信号/插槽和财产的机制。它映射了许多[QGraphicsItem](qgraphicsitem.html)的基本的setter和getter性能，并增加了通知信号很多。

### Parents and Children

每个图形对象可以与一个父项构成。这可确保当它的父项被破坏的物品将被销毁。虽然QGraphicsObject从两个继承[QObject](qobject.html)和[QGraphicsItem](qgraphicsitem.html)，你应该使用所提供的功能[QGraphicsItem](qgraphicsitem.html)，_not_ [QObject](qobject.html)，管理父和子项之间的关系。

项目之间的关系可以用探索的[parentItem](qgraphicsitem.html#parentItem)（）和[childItems](qgraphicsitem.html#childItems)（）函数。在项目中一个场景的层次结构中，[parentObject](qgraphicsitem.html#parentObject)（）和[parentWidget](qgraphicsitem.html#parentWidget)（ ）函数的等效[QWidget.parent](qobject.html#parent)（）和[QWidget.parentWidget](qwidget.html#parentWidget)对于（ ）函数[QWidget](qwidget.html)子类。

* * *

## Method Documentation

```
QGraphicsObject.__init__ (self, QGraphicsItem parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsObject](qgraphicsobject.html)同_parent_。

```
QGraphicsObject.grabGesture (self, Qt.GestureType type, Qt.GestureFlags flags = Qt.GestureFlags(0))
```

订阅图形对象给定的_gesture_具体_flags_。

**See also** [ungrabGesture](qgraphicsobject.html#ungrabGesture)（）和[QGestureEvent](qgestureevent.html)。

```
QGraphicsObject.ungrabGesture (self, Qt.GestureType type)
```

退订图形从给定的对象_gesture_。

**See also** [grabGesture](qgraphicsobject.html#grabGesture)（）和[QGestureEvent](qgestureevent.html)。

```
QGraphicsObject.updateMicroFocus (self)
```

这种方法也是一个Qt槽与C + +的签名`void updateMicroFocus()`。

更新项目的微焦点。这是插槽方便。

此功能被引入Qt的4.7 。

**See also** [QInputContext](qinputcontext.html)。

* * *

## Qt Signal Documentation

```
void enabledChanged ()
```

这是该信号的默认超载。

每当项目获得的启用或禁用此信号被发射。

**See also** [isEnabled](qgraphicsitem.html#isEnabled)（ ） 。

```
void opacityChanged ()
```

这是该信号的默认超载。

这个信号被发射时的项目变更不透明度

**See also** [QGraphicsItem.opacity](qgraphicsitem.html#opacity)（ ） 。

```
void parentChanged ()
```

这是该信号的默认超载。

这个信号被发射时的项目变更父

```
void rotationChanged ()
```

这是该信号的默认超载。

这个信号被发射时的项目变更的roation 。

```
void scaleChanged ()
```

这是该信号的默认超载。

这个信号被发射时的项目变更的规模。

```
void visibleChanged ()
```

这是该信号的默认超载。

这个信号被发射时的项目变更的可视性

**See also** [visible](qgraphicsobject.html#visible-prop)。

```
void xChanged ()
```

这是该信号的默认超载。

这个信号被发射时的项目变更的x坐标位置

**See also** [pos](qgraphicsitem.html#pos)（ ） 。

```
void yChanged ()
```

这是该信号的默认超载。

这个信号被发射时的项目变更的y位置。

**See also** [pos](qgraphicsitem.html#pos)（ ） 。

```
void zChanged ()
```

这是该信号的默认超载。

这个信号被发射时的项目变更z值。

**See also** [pos](qgraphicsitem.html#pos)（ ） 。