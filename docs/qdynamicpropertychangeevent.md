# QDynamicPropertyChangeEvent Class Reference

## [[QtCore](index.htm) module]

该QDynamicPropertyChangeEvent类包含事件参数的动态属性更改事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QByteArray name)`
*   `__init__ (self, QDynamicPropertyChangeEvent)`
*   `QByteArray propertyName (self)`

* * *

## Detailed Description

该QDynamicPropertyChangeEvent类包含事件参数的动态属性更改事件。

动态属性更改事件被发送到的对象的属性时动态添加，更改或删除使用[QObject.setProperty](qobject.html#setProperty)（ ） 。

* * *

## Method Documentation

```
QDynamicPropertyChangeEvent.__init__ (self, QByteArray name)
```

构造一个动态属性更改事件对象的属性名称设置为_name_。

```
QDynamicPropertyChangeEvent.__init__ (self, QDynamicPropertyChangeEvent)
```

```
QByteArray QDynamicPropertyChangeEvent.propertyName (self)
```

[

返回添加，更改或删除的动态属性的名称。

](qbytearray.html)

[**See also**](qbytearray.html) [QObject.setProperty](qobject.html#setProperty)（）和[QObject.dynamicPropertyNames](qobject.html#dynamicPropertyNames)（ ） 。