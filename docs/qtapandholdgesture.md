# QTapAndHoldGesture Class Reference

## [[QtGui](index.htm) module]

该QTapAndHoldGesture类描述了一个水龙头和保持（又名LongTap ）手势用户所做的。[More...](#details)

继承[QGesture](qgesture.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QPointF position (self)`
*   `setPosition (self, QPointF pos)`

### Static Methods

*   `setTimeout (int msecs)`
*   `int timeout ()`

* * *

## Detailed Description

该QTapAndHoldGesture类描述了一个水龙头和保持（又名LongTap ）手势用户所做的。

手势使用手势在你的应用程序在处理Qt和信息的概述，请参阅[Gestures Programming](index.htm)文档。

* * *

## Method Documentation

```
QTapAndHoldGesture.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
QPointF QTapAndHoldGesture.position (self)
```

[

```
QTapAndHoldGesture.setPosition (self, QPointF pos)
```

```
QTapAndHoldGesture.setTimeout (int msecs)
```

设置超时时间，以毫秒为单位的手势触发之前。

](qpointf.html)

[识别器会检测触摸下来，而如果_msecs_后来接触仍然向下，就会触发](qpointf.html)[QTapAndHoldGesture](qtapandholdgesture.html)。默认值是700毫秒。

**See also** [timeout](qtapandholdgesture.html#timeout)（ ） 。

```
int QTapAndHoldGesture.timeout ()
```

获取超时时间，以毫秒为单位的手势触发之前。

识别器会检测触摸下来，如果超时（ ）后触摸仍然向下，就会触发[QTapAndHoldGesture](qtapandholdgesture.html)。默认值是700毫秒。

**See also** [setTimeout](qtapandholdgesture.html#setTimeout)（ ） 。