# QDeclarativeListReference Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeListReference类允许的操作[QDeclarativeListProperty](index.htm)属性。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QObject, str property, QDeclarativeEngine engine = None)`
*   `__init__ (self, QDeclarativeListReference)`
*   `bool append (self, QObject)`
*   `QObject at (self, int)`
*   `bool canAppend (self)`
*   `bool canAt (self)`
*   `bool canClear (self)`
*   `bool canCount (self)`
*   `bool clear (self)`
*   `int count (self)`
*   `bool isValid (self)`
*   `QMetaObject listElementType (self)`
*   `QObject object (self)`

* * *

## Detailed Description

该QDeclarativeListReference类允许的操作[QDeclarativeListProperty](index.htm)属性。

QDeclarativeListReference允许C + +程序来读取，并在一个简单的和类型安全的方式赋值到一个QML列表属性。一个QDeclarativeListReference可以通过传递一个对象和属性名或通过创建一个[QDeclarativeProperty](qdeclarativeproperty.html)实例。这两个是equivalant ：

```
 QDeclarativeListReference ref1(object, "children");

 [QDeclarativeProperty](qdeclarativeproperty.html) ref2(object, "children");
 QDeclarativeListReference ref2 = qvariant_cast<QDeclarativeListReference>(ref2.read());

```

不是所有的QML列表属性支持所有操作。一组方法，[canAppend](qdeclarativelistreference.html#canAppend)（ ）[canAt](qdeclarativelistreference.html#canAt)（ ）[canClear](qdeclarativelistreference.html#canClear)（）和[canCount](qdeclarativelistreference.html#canCount)（）允许程序查询的操作是否被支撑在一个给定的属性。

QML列表属性是类型安全的。只[QObject](qobject.html)就这么从正确的基类派生可以分配到列表中。该[listElementType](qdeclarativelistreference.html#listElementType)（ ）方法可用于查询[QMetaObject](qmetaobject.html)的[QObject](qobject.html)输入的支持。尝试了不正确类型的对象添加到一个列表属性将失败。

像正常的列表，通过访问索引列表元素时，它是调用者的责任，以确保它不会使用要求进行超出范围的元素[count](qdeclarativelistreference.html#count)前（ ）方法调用[at](qdeclarativelistreference.html#at)（ ） 。

* * *

## Method Documentation

```
QDeclarativeListReference.__init__ (self)
```

构造一个无效的实例。

```
QDeclarativeListReference.__init__ (self, QObject, str property, QDeclarativeEngine engine = None)
```

构造一个[QDeclarativeListReference](qdeclarativelistreference.html)为_object_的_property_。如果_property_是不是一个列表属性，无效[QDeclarativeListReference](qdeclarativelistreference.html)被创建。如果_object_参考构造被破坏后，它会自动失效。也就是说，它是安全的保持[QDeclarativeListReference](qdeclarativelistreference.html)即使实例_object_被删除。

路过_engine_需要访问一些创建QML列表属性。如果有疑问，和发动机可用，它传递。

```
QDeclarativeListReference.__init__ (self, QDeclarativeListReference)
```

```
bool QDeclarativeListReference.append (self, QObject)
```

追加可_object_到列表中。返回True如果操作成功，否则为False 。

**See also** [canAppend](qdeclarativelistreference.html#canAppend)（ ） 。

```
QObject QDeclarativeListReference.at (self, int)
```

[

返回的列表元素_index_，或者0，如果操作失败。

](qobject.html)

[**See also**](qobject.html) [canAt](qdeclarativelistreference.html#canAt)（ ） 。

```
bool QDeclarativeListReference.canAppend (self)
```

返回True如果列表属性可以附加到，否则为False。返回False，如果引用是无效的。

**See also** [append](qdeclarativelistreference.html#append)（ ） 。

```
bool QDeclarativeListReference.canAt (self)
```

返回True如果列表属性可以通过索引查询，否则为False 。返回False，如果引用是无效的。

**See also** [at](qdeclarativelistreference.html#at)（ ） 。

```
bool QDeclarativeListReference.canClear (self)
```

返回True如果列表属性可以被清除，否则为False。返回False，如果引用是无效的。

**See also** [clear](qdeclarativelistreference.html#clear)（ ） 。

```
bool QDeclarativeListReference.canCount (self)
```

返回True如果列表属性可以查询其元素计数，否则为False 。返回False，如果引用是无效的。

**See also** [count](qdeclarativelistreference.html#count)（ ） 。

```
bool QDeclarativeListReference.clear (self)
```

清除列表。返回True如果操作成功，否则为False 。

**See also** [canClear](qdeclarativelistreference.html#canClear)（ ） 。

```
int QDeclarativeListReference.count (self)
```

返回对象列表中的号码，或者0，如果操作失败。

```
bool QDeclarativeListReference.isValid (self)
```

返回True如果该实例是指一个有效的列表属性，否则为False 。

```
QMetaObject QDeclarativeListReference.listElementType (self)
```

[](qmetaobject.html)

[返回](qmetaobject.html)[QMetaObject](qmetaobject.html)为存储在列表属性的元素。返回0，如果引用是无效的。

该[QMetaObject](qmetaobject.html)可以使用的时间提前，以确定一个给定实例是否可以被添加到列表。

```
QObject QDeclarativeListReference.object (self)
```

[

返回列表属性的对象。返回0，如果引用是无效的。

](qobject.html)