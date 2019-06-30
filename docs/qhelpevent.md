# QHelpEvent Class Reference

## [[QtGui](index.htm) module]

该QHelpEvent类提供用于请求有关的一个小部件的特定点有用的信息的事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QEvent.Type type, QPoint pos, QPoint globalPos)`
*   `__init__ (self, QHelpEvent)`
*   `QPoint globalPos (self)`
*   `int globalX (self)`
*   `int globalY (self)`
*   `QPoint pos (self)`
*   `int x (self)`
*   `int y (self)`

* * *

## Detailed Description

该QHelpEvent类提供用于请求有关的一个小部件的特定点有用的信息的事件。

此事件可以在应用程序中截获到提供工具提示和“这是什么？ ”帮助为自定义控件。该[type](qevent.html#type)（ ）可以是[QEvent.ToolTip](qevent.html#Type-enum) or [QEvent.WhatsThis](qevent.html#Type-enum)。

* * *

## Method Documentation

```
QHelpEvent.__init__ (self, QEvent.Type type, QPoint pos, QPoint globalPos)
```

构造一个帮助事件与给定_type_对应于由指定窗口小部件的相对位置_pos_并通过指定的全球地位_globalPos_。

_type_必须是[QEvent.ToolTip](qevent.html#Type-enum) or [QEvent.WhatsThis](qevent.html#Type-enum)。

**See also** [pos](qhelpevent.html#pos)（）和[globalPos](qhelpevent.html#globalPos)（ ） 。

```
QHelpEvent.__init__ (self, QHelpEvent)
```

```
QPoint QHelpEvent.globalPos (self)
```

[

返回时，在全局坐标生成事件的鼠标光标位置。

](qpoint.html)

[**See also**](qpoint.html) [pos](qhelpevent.html#pos)（ ）[globalX](qhelpevent.html#globalX)（）和[globalY](qhelpevent.html#globalY)（ ） 。

```
int QHelpEvent.globalX (self)
```

同[globalPos](qhelpevent.html#globalPos)（ ） 。[x](qhelpevent.html#x)（ ） 。

**See also** [x](qhelpevent.html#x)（ ）[globalY](qhelpevent.html#globalY)（）和[globalPos](qhelpevent.html#globalPos)（ ） 。

```
int QHelpEvent.globalY (self)
```

同[globalPos](qhelpevent.html#globalPos)（ ） 。[y](qhelpevent.html#y)（ ） 。

**See also** [y](qhelpevent.html#y)（ ）[globalX](qhelpevent.html#globalX)（）和[globalPos](qhelpevent.html#globalPos)（ ） 。

```
QPoint QHelpEvent.pos (self)
```

[

返回生成事件，当鼠标光标的位置，相对于到该事件被调度的部件。

](qpoint.html)

[**See also**](qpoint.html) [globalPos](qhelpevent.html#globalPos)（ ）[x](qhelpevent.html#x)（）和[y](qhelpevent.html#y)（ ） 。

```
int QHelpEvent.x (self)
```

同[pos](qhelpevent.html#pos)（ ） ×（ ） 。

**See also** [y](qhelpevent.html#y)（ ）[pos](qhelpevent.html#pos)（）和[globalPos](qhelpevent.html#globalPos)（ ） 。

```
int QHelpEvent.y (self)
```

同[pos](qhelpevent.html#pos)（ ） Y（ ） 。

**See also** [x](qhelpevent.html#x)（ ）[pos](qhelpevent.html#pos)（）和[globalPos](qhelpevent.html#globalPos)（ ） 。