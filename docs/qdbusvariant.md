# QDBusVariant Class Reference

## [[QtDBus](index.htm) module]

该QDBusVariant类使程序员可以识别由D-Bus的类型系统提供的变量类型。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QVariant variant)`
*   `__init__ (self, QDBusVariant)`
*   `setVariant (self, QVariant variant)`
*   `QVariant variant (self)`

### Special Methods

*   `bool __eq__ (self, QDBusVariant v2)`
*   `bool __ne__ (self, QDBusVariant v2)`

* * *

## Detailed Description

该QDBusVariant类使程序员可以识别由D-Bus的类型系统提供的变量类型。

一个D-Bus的函数，它接受一个整数，一个D-Bus的变体和一个字符串作为参数，可以调用下面的参数列表（见[QDBusMessage.setArguments](qdbusmessage.html#setArguments)（）） ：

```
     [QList](index.htm)<[QVariant](qvariant.html)> arguments;
     arguments << [QVariant](qvariant.html)(42) << [QVariant](qvariant.html).fromValue(QDBusVariant(43)) << [QVariant](qvariant.html)("hello");
     myDBusMessage.setArguments(arguments);

```

当一个D-Bus的函数返回一个D-Bus的变种，它可以检索如下：

```
     // call a D-Bus function that returns a D-Bus variant
     [QVariant](qvariant.html) v = callMyDBusFunction();
     // retrieve the D-Bus variant
     QDBusVariant dbusVariant = qvariant_cast<QDBusVariant>(v);
     // retrieve the actual value stored in the D-Bus variant
     [QVariant](qvariant.html) result = dbusVariant.variant();

```

该[QVariant](qvariant.html)内QDBusVariant需要在一个D-Bus的变种正常的D-Bus的值和值来区分。

* * *

## Method Documentation

```
QDBusVariant.__init__ (self)
```

构造一个新的D-Bus的变体。

```
QDBusVariant.__init__ (self, QVariant variant)
```

构造一个新的D-Bus的变种从给定的Qt_variant_。

**See also** [setVariant](qdbusvariant.html#setVariant)（ ） 。

```
QDBusVariant.__init__ (self, QDBusVariant)
```

```
QDBusVariant.setVariant (self, QVariant variant)
```

分配给Qt的价值_variant_这种D-Bus的变体。

**See also** [variant](qdbusvariant.html#variant)（ ） 。

```
QVariant QDBusVariant.variant (self)
```

返回此D-Bus的变体作为[QVariant](qvariant.html)对象。

**See also** [setVariant](qdbusvariant.html#setVariant)（ ） 。

```
bool QDBusVariant.__eq__ (self, QDBusVariant v2)
```

```
bool QDBusVariant.__ne__ (self, QDBusVariant v2)
```