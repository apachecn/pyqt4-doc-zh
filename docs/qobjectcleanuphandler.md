# QObjectCleanupHandler Class Reference

## [[QtCore](index.htm) module]

该QObjectCleanupHandler类手表多的一生[QObjects](index.htm#qobjects)。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self)`
*   `QObject add (self, QObject object)`
*   `clear (self)`
*   `bool isEmpty (self)`
*   `remove (self, QObject object)`

* * *

## Detailed Description

该QObjectCleanupHandler类手表多的一生[QObjects](index.htm#qobjects)。

每当你需要知道QObjectCleanupHandler是非常有用的当数[QObject](qobject.html)是由别人所拥有s有被删除。这是很重要的，例如，在已分配的共享库的应用程序引用内存时。

跟踪一些[QObject](qobject.html)秒，创造QObjectCleanupHandler ，并[add](qobjectcleanuphandler.html#add)（ ）你感兴趣的如果你不再有兴趣追踪一个特定的对象，使用对象[remove](qobjectcleanuphandler.html#remove)（）从清理处理程序将其删除。如果正在跟踪的清理处理程序的对象被别人删除了它会自动从清理处理程序中删除。您可以删除在清理处理程序中的所有对象与[clear](qobjectcleanuphandler.html#clear)（ ） ，或者通过破坏清理处理程序。[isEmpty](qobjectcleanuphandler.html#isEmpty)如果QObjectCleanupHandler没有对象追踪（）返回True 。

* * *

## Method Documentation

```
QObjectCleanupHandler.__init__ (self)
```

构造一个空[QObjectCleanupHandler](qobjectcleanuphandler.html)。

```
QObject QObjectCleanupHandler.add (self, QObject object)
```

[

添加_object_该清理处理，并返回指向对象的指针。

](qobject.html)

[**See also**](qobject.html) [remove](qobjectcleanuphandler.html#remove)（ ） 。

```
QObjectCleanupHandler.clear (self)
```

删除此清理处理程序中的所有对象。清理处理程序变空。

**See also** [isEmpty](qobjectcleanuphandler.html#isEmpty)（ ） 。

```
bool QObjectCleanupHandler.isEmpty (self)
```

返回True如果此清理处理程序是空的，或者如果在此清理处理程序中的所有对象都被摧毁，否则返回False 。

**See also** [add](qobjectcleanuphandler.html#add)（ ）[remove](qobjectcleanuphandler.html#remove)（）和[clear](qobjectcleanuphandler.html#clear)（ ） 。

```
QObjectCleanupHandler.remove (self, QObject object)
```

移除_object_从这个清理处理程序。该对象不会被销毁。

**See also** [add](qobjectcleanuphandler.html#add)（ ） 。