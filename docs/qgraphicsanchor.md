# QGraphicsAnchor Class Reference

## [[QtGui](index.htm) module]

该QGraphicsAnchor类表示两个项目之间的锚[QGraphicsAnchorLayout](qgraphicsanchorlayout.html)。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `setSizePolicy (self, QSizePolicy.Policy policy)`
*   `setSpacing (self, float spacing)`
*   `QSizePolicy.Policy sizePolicy (self)`
*   `float spacing (self)`
*   `unsetSpacing (self)`

* * *

## Detailed Description

该QGraphicsAnchor类表示两个项目之间的锚[QGraphicsAnchorLayout](qgraphicsanchorlayout.html)。

图形锚提供了一个API ，使您能够查询和操纵锚具有的属性。当锚定器被添加到布局与[QGraphicsAnchorLayout.addAnchor](qgraphicsanchorlayout.html#addAnchor)（ ） ，返回一个QGraphicsAnchor实例，其中的属性被初始化为它们的默认值。该属性可以被进一步改变，并且它们将被下一次的布局被激活拾取。

* * *

## Method Documentation

```
QGraphicsAnchor.setSizePolicy (self, QSizePolicy.Policy policy)
```

```
QGraphicsAnchor.setSpacing (self, float spacing)
```

```
QSizePolicy.Policy QGraphicsAnchor.sizePolicy (self)
```

[

```
float QGraphicsAnchor.spacing (self)
```

```
QGraphicsAnchor.unsetSpacing (self)
```

](qsizepolicy.html#Policy-enum)