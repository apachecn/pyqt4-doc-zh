# QMimeSource Class Reference

## [[QtGui](index.htm) module]

该QMimeSource类是提供一定的MIME类型格式化的数据对象的抽象。[More...](#details)

通过继承[QDropEvent](qdropevent.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QMimeSource)`
*   `QByteArray encodedData (self, str)`
*   `str format (self, int i = 0)`
*   `bool provides (self, str)`

* * *

## Detailed Description

该QMimeSource类是提供一定的MIME类型格式化的数据对象的抽象。

首选的方法来拖放是使用[QDrag](qdrag.html)在与结合[QMimeData](qmimedata.html)。看[Drag and Drop](index.htm)了解详情。

* * *

## Method Documentation

```
QMimeSource.__init__ (self)
```

```
QMimeSource.__init__ (self, QMimeSource)
```

```
QByteArray QMimeSource.encodedData (self, str)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回指定的MIME这个对象的编码数据_format_。

```
str QMimeSource.format (self, int i = 0)
```

这种方法是抽象的，应在任何子类中重新实现。

返回（_i_ - 支持1）次的MIME格式，或0 。

```
bool QMimeSource.provides (self, str)
```

返回True如果对象可以提供的数据格式_mimeType_否则返回False 。

](qbytearray.html)

[如果从继承](qbytearray.html)[QMimeSource](qmimesource.html)，出于一致性考虑，最好是实施更抽象canDecode （）函数，如QTextDrag.canDecode （ ）和QImageDrag.canDecode （ ） 。