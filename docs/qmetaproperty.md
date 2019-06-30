# QMetaProperty Class Reference

## [[QtCore](index.htm) module]

该QMetaProperty类提供的属性的元数据。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QMetaProperty)`
*   `QMetaEnum enumerator (self)`
*   `bool hasNotifySignal (self)`
*   `bool hasStdCppSet (self)`
*   `bool isConstant (self)`
*   `bool isDesignable (self, QObject object = None)`
*   `bool isEditable (self, QObject object = None)`
*   `bool isEnumType (self)`
*   `bool isFinal (self)`
*   `bool isFlagType (self)`
*   `bool isReadable (self)`
*   `bool isResettable (self)`
*   `bool isScriptable (self, QObject object = None)`
*   `bool isStored (self, QObject object = None)`
*   `bool isUser (self, QObject object = None)`
*   `bool isValid (self)`
*   `bool isWritable (self)`
*   `str name (self)`
*   `QMetaMethod notifySignal (self)`
*   `int notifySignalIndex (self)`
*   `int propertyIndex (self)`
*   `QVariant read (self, QObject obj)`
*   `bool reset (self, QObject obj)`
*   `Type type (self)`
*   `str typeName (self)`
*   `int userType (self)`
*   `bool write (self, QObject obj, QVariant value)`

* * *

## Detailed Description

该QMetaProperty类提供的属性的元数据。

属性的元数据是从一个对象的元对象获得的。看[QMetaObject.property](qmetaobject.html#property)（）和[QMetaObject.propertyCount](qmetaobject.html#propertyCount)（ ）了解详情。

### Property Meta-Data

一个属性有[name](qmetaproperty.html#name)（）和一个[type](qmetaproperty.html#type)（） ，以及用于指定其行为的各种属性：[isReadable](qmetaproperty.html#isReadable)（ ）[isWritable](qmetaproperty.html#isWritable)（ ）[isDesignable](qmetaproperty.html#isDesignable)（ ）[isScriptable](qmetaproperty.html#isScriptable)（）和[isStored](qmetaproperty.html#isStored)（ ） 。

如果该属性是一个枚举，[isEnumType](qmetaproperty.html#isEnumType)（ ）返回True，如果属性是一个枚举，这也是一个标志（即它的值可以使用OR运算符进行组合） ，[isEnumType](qmetaproperty.html#isEnumType)（）和[isFlagType](qmetaproperty.html#isFlagType)（）都返回True。枚举这些类型可以从[enumerator](qmetaproperty.html#enumerator)（ ） 。

该属性的值设置和检索[read](qmetaproperty.html#read)（ ）[write](qmetaproperty.html#write)（）和[reset](qmetaproperty.html#reset)（） ，它们也可以通过改变[QObject](qobject.html)的设置和获取功能。看[QObject.setProperty](qobject.html#setProperty)（）和[QObject.property](qobject.html#property)（ ）了解详情。

### Copying and Assignment

QMetaProperty对象可以通过值被复制。然而，每个副本将引用相同的基础属性的元数据。

* * *

## Method Documentation

```
QMetaProperty.__init__ (self)
```

```
QMetaProperty.__init__ (self, QMetaProperty)
```

```
QMetaEnum QMetaProperty.enumerator (self)
```

[

返回枚举，如果这个属性的类型是一个枚举类型，否则返回的值是不确定的。

](qmetaenum.html)

[**See also**](qmetaenum.html) [isEnumType](qmetaproperty.html#isEnumType)（）和[isFlagType](qmetaproperty.html#isFlagType)（ ） 。

```
bool QMetaProperty.hasNotifySignal (self)
```

返回True如果此属性有相应的变化通知信号，否则返回False 。

**See also** [notifySignal](qmetaproperty.html#notifySignal)（ ） 。

```
bool QMetaProperty.hasStdCppSet (self)
```

```
bool QMetaProperty.isConstant (self)
```

返回True如果该属性是不变的，否则返回False 。

属性是恒定的，如果`Q_PROPERTY()`的`CONSTANT`属性被设置。

此功能被引入Qt的4.6 。

```
bool QMetaProperty.isDesignable (self, QObject object = None)
```

返回True如果此属性是可设计为给定的_object_否则返回False 。

如果没有_object_给出时，函数返回False ，如果`Q_PROPERTY()`的`DESIGNABLE`属性为False ，否则返回True （如果属性为True或者是一个函数或表达式） 。

**See also** [isScriptable](qmetaproperty.html#isScriptable)（）和[isStored](qmetaproperty.html#isStored)（ ） 。

```
bool QMetaProperty.isEditable (self, QObject object = None)
```

```
bool QMetaProperty.isEnumType (self)
```

返回True ，如果属性的类型是一个枚举值，否则返回False 。

**See also** [enumerator](qmetaproperty.html#enumerator)（）和[isFlagType](qmetaproperty.html#isFlagType)（ ） 。

```
bool QMetaProperty.isFinal (self)
```

返回True如果该属性是最终的，否则返回False 。

属性是最终的，如果`Q_PROPERTY()`的`FINAL`属性被设置。

此功能被引入Qt的4.6 。

```
bool QMetaProperty.isFlagType (self)
```

返回True ，如果属性的类型是作为一个标志枚举值，否则返回False 。

标志可以使用OR运算符进行组合。一个标志类型是隐式也是一个枚举类型。

**See also** [isEnumType](qmetaproperty.html#isEnumType)（ ）[enumerator](qmetaproperty.html#enumerator)（）和[QMetaEnum.isFlag](qmetaenum.html#isFlag)（ ） 。

```
bool QMetaProperty.isReadable (self)
```

返回True如果此属性是可读的，否则返回False 。

**See also** [isWritable](qmetaproperty.html#isWritable)（ ）[read](qmetaproperty.html#read)（）和[isValid](qmetaproperty.html#isValid)（ ） 。

```
bool QMetaProperty.isResettable (self)
```

返回True如果此属性可以重置为默认值，否则返回False 。

**See also** [reset](qmetaproperty.html#reset)（ ） 。

```
bool QMetaProperty.isScriptable (self, QObject object = None)
```

返回True，如果属性是可编写脚本对于给定的_object_否则返回False 。

如果没有_object_给出时，函数返回False ，如果`Q_PROPERTY()`的`SCRIPTABLE`属性为False ，否则返回True （如果属性为True或者是一个函数或表达式） 。

**See also** [isDesignable](qmetaproperty.html#isDesignable)（）和[isStored](qmetaproperty.html#isStored)（ ） 。

```
bool QMetaProperty.isStored (self, QObject object = None)
```

返回True如果该属性用于存储_object_否则返回False 。

如果没有_object_给出时，函数返回False ，如果`Q_PROPERTY()`的`STORED`属性为False ，否则返回True （如果属性为True或者是一个函数或表达式） 。

**See also** [isDesignable](qmetaproperty.html#isDesignable)（）和[isScriptable](qmetaproperty.html#isScriptable)（ ） 。

```
bool QMetaProperty.isUser (self, QObject object = None)
```

如果这个属性被指定为返回True`USER`属性，即，使得用户能够编辑所述一个_object_或者说是某种其他方式显着。否则返回False 。例如，本`text`属性是`USER`一个可编辑的属性[QLineEdit](qlineedit.html)。

If _object_为null，则函数返回False ，如果`Q_PROPERTY()`的`USER`属性为False 。否则，它返回True 。

**See also** [QMetaObject.userProperty](qmetaobject.html#userProperty)（ ）[isDesignable](qmetaproperty.html#isDesignable)（）和[isScriptable](qmetaproperty.html#isScriptable)（ ） 。

```
bool QMetaProperty.isValid (self)
```

返回True如果此属性是有效的（可读），否则返回False 。

**See also** [isReadable](qmetaproperty.html#isReadable)（ ） 。

```
bool QMetaProperty.isWritable (self)
```

返回True如果此属性为可写，否则返回False 。

**See also** [isReadable](qmetaproperty.html#isReadable)（）和[write](qmetaproperty.html#write)（ ） 。

```
str QMetaProperty.name (self)
```

返回此属性的名称。

**See also** [type](qmetaproperty.html#type)（）和[typeName](qmetaproperty.html#typeName)（ ） 。

```
QMetaMethod QMetaProperty.notifySignal (self)
```

[](qmetamethod.html)

[返回](qmetamethod.html)[QMetaMethod](qmetamethod.html)属性更改通知信号的实例，如果已指定，否则返回一个无效的[QMetaMethod](qmetamethod.html)。

此功能被引入Qt的4.5 。

**See also** [hasNotifySignal](qmetaproperty.html#hasNotifySignal)（ ） 。

```
int QMetaProperty.notifySignalIndex (self)
```

返回如果指定了属性更改通知信号的索引，否则返回-1 。

此功能被引入Qt的4.6 。

**See also** [hasNotifySignal](qmetaproperty.html#hasNotifySignal)（ ） 。

```
int QMetaProperty.propertyIndex (self)
```

返回此属性的索引。

此功能被引入Qt的4.6 。

```
QVariant QMetaProperty.read (self, QObject obj)
```

从给定的读取属性的值_object_。返回值，如果它能够读取它，否则返回一个无效的变体。

**See also** [write](qmetaproperty.html#write)（ ）[reset](qmetaproperty.html#reset)（）和[isReadable](qmetaproperty.html#isReadable)（ ） 。

```
bool QMetaProperty.reset (self, QObject obj)
```

将属性重置为给定的_object_用reset方法。返回True如果工作过的复位，否则返回False 。

复位方法是可选的，只有少数的属性支持他们。

**See also** [read](qmetaproperty.html#read)（）和[write](qmetaproperty.html#write)（ ） 。

```
Type QMetaProperty.type (self)
```

[](index.htm#Type-enum)

[返回此属性的类型。返回值是的值之一](index.htm#Type-enum)[QVariant.Type](qvariant.html#Type-enum)枚举。

**See also** [userType](qmetaproperty.html#userType)（ ）[typeName](qmetaproperty.html#typeName)（）和[name](qmetaproperty.html#name)（ ） 。

```
str QMetaProperty.typeName (self)
```

返回此属性的类型的名称。

**See also** [type](qmetaproperty.html#type)（）和[name](qmetaproperty.html#name)（ ） 。

```
int QMetaProperty.userType (self)
```

返回此属性的用户类型。返回值是已注册的价值观之一[QMetaType](qmetatype.html)，或者0，如果类型未注册。

这个函数中引入了Qt 4.2中。

**See also** [type](qmetaproperty.html#type)（ ）[QMetaType](qmetatype.html)和[typeName](qmetaproperty.html#typeName)（ ） 。

```
bool QMetaProperty.write (self, QObject obj, QVariant value)
```

Writes _value_作为该属性的值设置为给定_object_。返回True ，如果写入成功，否则返回False 。

**See also** [read](qmetaproperty.html#read)（ ）[reset](qmetaproperty.html#reset)（）和[isWritable](qmetaproperty.html#isWritable)（ ） 。