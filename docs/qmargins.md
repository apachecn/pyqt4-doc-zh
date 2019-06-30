# QMargins Class Reference

## [[QtCore](index.htm) module]

该QMargins类定义的四个边距的矩形。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, int aleft, int atop, int aright, int abottom)`
*   `__init__ (self, QMargins)`
*   `int bottom (self)`
*   `bool isNull (self)`
*   `int left (self)`
*   `int right (self)`
*   `setBottom (self, int abottom)`
*   `setLeft (self, int aleft)`
*   `setRight (self, int aright)`
*   `setTop (self, int atop)`
*   `int top (self)`

### Special Methods

*   `bool __eq__ (self, QMargins m2)`
*   `bool __ne__ (self, QMargins m2)`

* * *

## Detailed Description

该QMargins类定义的四个边距的矩形。

QMargin定义了一组四个边距，左，上，右，下，描述围绕矩形边框的大小。

该[isNull](qmargins.html#isNull)只有当所有的边距设置为零（ ）函数返回True。

相比QMargin对象可以被串流播放以及。

* * *

## Method Documentation

```
QMargins.__init__ (self)
```

构造一个对象边距设置为0的所有利润。

**See also** [isNull](qmargins.html#isNull)（ ） 。

```
QMargins.__init__ (self, int aleft, int atop, int aright, int abottom)
```

构建边距与给定的_left_，_top_，_right_，_bottom_

**See also** [setLeft](qmargins.html#setLeft)（ ）[setRight](qmargins.html#setRight)（ ）[setTop](qmargins.html#setTop)（）和[setBottom](qmargins.html#setBottom)（ ） 。

```
QMargins.__init__ (self, QMargins)
```

```
int QMargins.bottom (self)
```

返回下边距。

**See also** [setBottom](qmargins.html#setBottom)（ ） 。

```
bool QMargins.isNull (self)
```

返回True如果所有的利润都为0 ，否则返回False 。

```
int QMargins.left (self)
```

返回留有馀量。

**See also** [setLeft](qmargins.html#setLeft)（ ） 。

```
int QMargins.right (self)
```

返回右页边距。

**See also** [setRight](qmargins.html#setRight)（ ） 。

```
QMargins.setBottom (self, int abottom)
```

设置下边距来_bottom_。

**See also** [bottom](qmargins.html#bottom)（ ） 。

```
QMargins.setLeft (self, int aleft)
```

设置左边距为_left_。

**See also** [left](qmargins.html#left)（ ） 。

```
QMargins.setRight (self, int aright)
```

设置右边距为_right_。

**See also** [right](qmargins.html#right)（ ） 。

```
QMargins.setTop (self, int atop)
```

设置上边距，以_Top_。

**See also** [top](qmargins.html#top)（ ） 。

```
int QMargins.top (self)
```

返回顶部边距。

**See also** [setTop](qmargins.html#setTop)（ ） 。

```
bool QMargins.__eq__ (self, QMargins m2)
```

```
bool QMargins.__ne__ (self, QMargins m2)
```