# QDBusSignature Class Reference

## [[QtDBus](index.htm) module]

该QDBusSignature类使程序员可以识别由D-Bus的类型系统提供的签名类型。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString signature)`
*   `__init__ (self, QDBusSignature)`
*   `setSignature (self, QString signature)`
*   `QString signature (self)`

### Special Methods

*   `bool __eq__ (self, QDBusSignature rhs)`
*   `bool __ge__ (self, QDBusSignature rhs)`
*   `int __hash__ (self)`
*   `bool __lt__ (self, QDBusSignature rhs)`
*   `bool __ne__ (self, QDBusSignature rhs)`

* * *

## Detailed Description

该QDBusSignature类使程序员可以识别由D-Bus的类型系统提供的签名类型。

* * *

## Method Documentation

```
QDBusSignature.__init__ (self)
```

构造一个新的签名。

**See also** [setSignature](qdbussignature.html#setSignature)（ ） 。

```
QDBusSignature.__init__ (self, QString signature)
```

构造一个新的签名从给定的_signature_。

```
QDBusSignature.__init__ (self, QDBusSignature)
```

构造一个新的签名从给定的_signature_。

```
QDBusSignature.setSignature (self, QString signature)
```

分配给定的值_signature_这个签名。

**See also** [signature](qdbussignature.html#signature)（ ） 。

```
QString QDBusSignature.signature (self)
```

返回此签名。

**See also** [setSignature](qdbussignature.html#setSignature)（ ） 。

```
bool QDBusSignature.__eq__ (self, QDBusSignature rhs)
```

```
bool QDBusSignature.__ge__ (self, QDBusSignature rhs)
```

```
int QDBusSignature.__hash__ (self)
```

```
bool QDBusSignature.__lt__ (self, QDBusSignature rhs)
```

```
bool QDBusSignature.__ne__ (self, QDBusSignature rhs)
```