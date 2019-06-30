# QWhatsThisClickedEvent Class Reference

## [[QtGui](index.htm) module]

该QWhatsThisClickedEvent类提供了可以用来处理超链接中的一个事件“这是什么？ ”文本。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QString href)`
*   `__init__ (self, QWhatsThisClickedEvent)`
*   `QString href (self)`

* * *

## Detailed Description

该QWhatsThisClickedEvent类提供了可以用来处理超链接中的一个事件“这是什么？ ”文本。

* * *

## Method Documentation

```
QWhatsThisClickedEvent.__init__ (self, QString href)
```

构造一个包含由指定的URL事件_href_当一个链接被点击了“这是什么？ ”消息。

**See also** [href](qwhatsthisclickedevent.html#href)（ ） 。

```
QWhatsThisClickedEvent.__init__ (self, QWhatsThisClickedEvent)
```

```
QString QWhatsThisClickedEvent.href (self)
```

返回是在用户单击该URL “这是什么？ ”文本。