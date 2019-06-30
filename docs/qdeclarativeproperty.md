# QDeclarativeProperty Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeProperty类文摘从QML创建的对象访问属性。[More...](#details)

### Types

*   `enum PropertyTypeCategory { InvalidCategory, List, Object, Normal }`
*   `enum Type { Invalid, Property, SignalProperty }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QObject)`
*   `__init__ (self, QObject, QDeclarativeContext)`
*   `__init__ (self, QObject, QDeclarativeEngine)`
*   `__init__ (self, QObject, QString)`
*   `__init__ (self, QObject, QString, QDeclarativeContext)`
*   `__init__ (self, QObject, QString, QDeclarativeEngine)`
*   `__init__ (self, QDeclarativeProperty)`
*   `bool connectNotifySignal (self, QObject dest, SLOT()SLOT() slot)`
*   `bool connectNotifySignal (self, callable dest)`
*   `bool connectNotifySignal (self, QObject dest, int method)`
*   `bool hasNotifySignal (self)`
*   `int index (self)`
*   `bool isDesignable (self)`
*   `bool isProperty (self)`
*   `bool isResettable (self)`
*   `bool isSignalProperty (self)`
*   `bool isValid (self)`
*   `bool isWritable (self)`
*   `QMetaMethod method (self)`
*   `QString name (self)`
*   `bool needsNotifySignal (self)`
*   `QObject object (self)`
*   `QMetaProperty property (self)`
*   `int propertyType (self)`
*   `PropertyTypeCategory propertyTypeCategory (self)`
*   `str propertyTypeName (self)`
*   `QVariant read (self)`
*   `bool reset (self)`
*   `Type type (self)`
*   `bool write (self, QVariant)`

### Static Methods

*   `QVariant read (QObject, QString)`
*   `QVariant read (QObject, QString, QDeclarativeContext)`
*   `QVariant read (QObject, QString, QDeclarativeEngine)`
*   `bool write (QObject, QString, QVariant)`
*   `bool write (QObject, QString, QVariant, QDeclarativeContext)`
*   `bool write (QObject, QString, QVariant, QDeclarativeEngine)`

### Special Methods

*   `bool __eq__ (self, QDeclarativeProperty)`
*   `int __hash__ (self)`
*   `bool __ne__ (self, QDeclarativeProperty)`

* * *

## Detailed Description

该QDeclarativeProperty类文摘从QML创建的对象访问属性。

由于QML使用Qt的元类型系统中所有现有的[QMetaObject](qmetaobject.html)类可以用来反思，并与QML创建的对象进行交互。然而，一些通过QML提供的新功能 - 如类型安全和附加属性 - 是最容易通过简化他们的一些自然的复杂性QDeclarativeProperty类中使用。

不像[QMetaProperty](qmetaproperty.html)它代表一个类类型的属性， QDeclarativeProperty封装在一个特定的对象实例的属性。要读取一个属性值，程序员创建一个QDeclarativeProperty实例，并调用[read](qdeclarativeproperty.html#read)（）方法。同样写一个属性值[write](qdeclarativeproperty.html#write)（）方法被使用。

例如，对于下面的QML代码：

```
 // MyItem.qml
 import QtQuick 1.0

 [Text](index.htm) { text: "A bit of text" }

```

该[Text](index.htm)对象的属性可以用QDeclarativeProperty进行访问，如下所示：

```
 #include <QDeclarativeProperty>
 #include <QGraphicsObject>

 ...

 [QDeclarativeView](qdeclarativeview.html) view([QUrl](qurl.html).fromLocalFile("MyItem.qml"));
 QDeclarativeProperty property(view.rootObject(), "font.pixelSize");
 qWarning() << "Current pixel size:" << property.read().toInt();
 property.write(24);
 qWarning() << "Pixel size should now be 24:" << property.read().toInt();

```

* * *

## Type Documentation

```
QDeclarativeProperty.PropertyTypeCategory
```

此枚举指定一个类别的QML属性。

| Constant | Value | Description |
| --- | --- | --- |
| `QDeclarativeProperty.InvalidCategory` | `0` | 该属性是无效的，或者是一个信号特性。 |
| `QDeclarativeProperty.List` | `1` | 该属性是一个[QDeclarativeListProperty](index.htm)列表属性 |
| `QDeclarativeProperty.Object` | `2` | 该属性是一个[QObject](qobject.html)派生类型的指针 |
| `QDeclarativeProperty.Normal` | `3` | 该属性是一个正常的值属性。 |

```
QDeclarativeProperty.Type
```

此枚举指定类型QML属性。

| Constant | Value | Description |
| --- | --- | --- |
| `QDeclarativeProperty.Invalid` | `0` | 该属性无效。 |
| `QDeclarativeProperty.Property` | `1` | 该属性是一个普通的Qt属性。 |
| `QDeclarativeProperty.SignalProperty` | `2` | 该属性是一个信号特性。 |

* * *

## Method Documentation

```
QDeclarativeProperty.__init__ (self)
```

创建一个无效的[QDeclarativeProperty](qdeclarativeproperty.html)。

```
QDeclarativeProperty.__init__ (self, QObject)
```

创建[QDeclarativeProperty](qdeclarativeproperty.html)为默认属性_obj_。如果没有默认属性，无效[QDeclarativeProperty](qdeclarativeproperty.html)将被创建。

```
QDeclarativeProperty.__init__ (self, QObject, QDeclarativeContext)
```

创建[QDeclarativeProperty](qdeclarativeproperty.html)为默认属性_obj_使用[context](qdeclarativecontext.html) _ctxt_。如果没有默认属性，无效[QDeclarativeProperty](qdeclarativeproperty.html)将被创建。

```
QDeclarativeProperty.__init__ (self, QObject, QDeclarativeEngine)
```

创建[QDeclarativeProperty](qdeclarativeproperty.html)为默认属性_obj_使用环境的实例，是由提供的QML组件_engine_。如果没有默认属性，无效[QDeclarativeProperty](qdeclarativeproperty.html)将被创建。

```
QDeclarativeProperty.__init__ (self, QObject, QString)
```

创建[QDeclarativeProperty](qdeclarativeproperty.html)该物业_name_的_obj_。

```
QDeclarativeProperty.__init__ (self, QObject, QString, QDeclarativeContext)
```

创建[QDeclarativeProperty](qdeclarativeproperty.html)该物业_name_的_obj_使用[context](qdeclarativecontext.html) _ctxt_。

创建[QDeclarativeProperty](qdeclarativeproperty.html)没有上下文会使一些特性 - 像附加属性 - 无法访问。

```
QDeclarativeProperty.__init__ (self, QObject, QString, QDeclarativeEngine)
```

创建[QDeclarativeProperty](qdeclarativeproperty.html)该物业_name_的_obj_使用环境的实例，是由提供的QML组件_engine_。

```
QDeclarativeProperty.__init__ (self, QDeclarativeProperty)
```

创建副本_other_。

```
bool QDeclarativeProperty.connectNotifySignal (self, QObject dest, SLOT()SLOT() slot)
```

该属性的改变通知信号连接到指定的_slot_的_dest_对象并返回True 。返回False，如果该元属性并不代表定期Qt的属性，或者如果它没有改变通知信号，或者如果_dest_对象不具有指定的_slot_。

```
bool QDeclarativeProperty.connectNotifySignal (self, callable dest)
```

该属性的改变通知信号连接到指定的_method_的_dest_对象并返回True 。返回False，如果该元属性并不代表定期Qt的属性，或者如果它没有改变通知信号，或者如果_dest_对象不具有指定的_method_。

```
bool QDeclarativeProperty.connectNotifySignal (self, QObject dest, int method)
```

```
bool QDeclarativeProperty.hasNotifySignal (self)
```

如果属性有改变通知信号，否则为False ，则返回True 。

```
int QDeclarativeProperty.index (self)
```

返回属性的Qt的元对象的索引。

```
bool QDeclarativeProperty.isDesignable (self)
```

返回True，如果属性是可设计的，否则为False 。

```
bool QDeclarativeProperty.isProperty (self)
```

返回True如果[QDeclarativeProperty](qdeclarativeproperty.html)代表一个普通的Qt属性。

```
bool QDeclarativeProperty.isResettable (self)
```

返回True，如果属性是可复位，否则为False 。

```
bool QDeclarativeProperty.isSignalProperty (self)
```

返回True如果[QDeclarativeProperty](qdeclarativeproperty.html)代表一个QML信号特性。

```
bool QDeclarativeProperty.isValid (self)
```

返回True如果[QDeclarativeProperty](qdeclarativeproperty.html)指的是一个有效的属性，否则为False 。

```
bool QDeclarativeProperty.isWritable (self)
```

返回True，如果属性是可写的，否则为False 。

```
QMetaMethod QDeclarativeProperty.method (self)
```

[](qmetamethod.html)

[返回](qmetamethod.html)[QMetaMethod](qmetamethod.html)这个属性，如果它是一个[SignalProperty](qdeclarativeproperty.html#Type-enum)，否则返回一个无效的[QMetaMethod](qmetamethod.html)。

```
QString QDeclarativeProperty.name (self)
```

返回此QML属性的名称。

```
bool QDeclarativeProperty.needsNotifySignal (self)
```

如果该属性需要改变通知信号绑定保持upto日期，否则返回False ，则返回True 。

某些属性，如附加属性或那些值永远不会改变，不需要改变通知。

```
QObject QDeclarativeProperty.object (self)
```

[](qobject.html)

[返回](qobject.html)[QDeclarativeProperty](qdeclarativeproperty.html)的[QObject](qobject.html)。

```
QMetaProperty QDeclarativeProperty.property (self)
```

[](qmetaproperty.html)

[返回](qmetaproperty.html)[Qt property](qmetaproperty.html)与此QML属性相关联。

```
int QDeclarativeProperty.propertyType (self)
```

返回[QVariant](qvariant.html)类型的财产，或[QVariant.Invalid](qvariant.html#Type-enum)如果该属性没有[QVariant](qvariant.html)类型。

```
PropertyTypeCategory QDeclarativeProperty.propertyTypeCategory (self)
```

[

返回属性类别。

```
str QDeclarativeProperty.propertyTypeName (self)
```

返回属性的类型名称，或者0，如果属性没有类型名称。

```
QVariant QDeclarativeProperty.read (self)
```

返回的属性值。

```
QVariant QDeclarativeProperty.read (QObject, QString)
```

返回_name_物业价值_object_。此方法等效于：

](qdeclarativeproperty.html#PropertyTypeCategory-enum)

```
 QDeclarativeProperty p(object, name);
 p.read();

```

```
QVariant QDeclarativeProperty.read (QObject, QString, QDeclarativeContext)
```

返回_name_物业价值_object_使用[context](qdeclarativecontext.html) _ctxt_。此方法等效于：

```
 [QDeclarativeProperty](qdeclarativeproperty.html) p(object, name, context);
 p.read();

```

```
QVariant QDeclarativeProperty.read (QObject, QString, QDeclarativeEngine)
```

返回_name_物业价值_object_使用环境的实例，是由提供的QML组件_engine_。 。此方法等效于：

```
 [QDeclarativeProperty](qdeclarativeproperty.html) p(object, name, engine);
 p.read();

```

```
bool QDeclarativeProperty.reset (self)
```

重置属性，如果属性是可复位返回True 。如果该属性是无法确认，没有任何反应并返回False 。

```
Type QDeclarativeProperty.type (self)
```

[

返回属性的类型。

```
bool QDeclarativeProperty.write (self, QVariant)
```

属性值设置为_value_并返回True 。返回False，如果该属性不能被设置，因为_value_是错误的类型，例如。

```
bool QDeclarativeProperty.write (QObject, QString, QVariant)
```

Writes _value_到_name_物业_object_。此方法等效于：

](qdeclarativeproperty.html#Type-enum)

```
 QDeclarativeProperty p(object, name);
 p.write(value);

```

```
bool QDeclarativeProperty.write (QObject, QString, QVariant, QDeclarativeContext)
```

Writes _value_到_name_物业_object_使用[context](qdeclarativecontext.html) _ctxt_。此方法等效于：

```
 [QDeclarativeProperty](qdeclarativeproperty.html) p(object, name, ctxt);
 p.write(value);

```

```
bool QDeclarativeProperty.write (QObject, QString, QVariant, QDeclarativeEngine)
```

Writes _value_到_name_物业_object_使用环境的实例，是由提供的QML组件_engine_。此方法等效于：

```
 [QDeclarativeProperty](qdeclarativeproperty.html) p(object, name, engine);
 p.write(value);

```

```
bool QDeclarativeProperty.__eq__ (self, QDeclarativeProperty)
```

```
int QDeclarativeProperty.__hash__ (self)
```

```
bool QDeclarativeProperty.__ne__ (self, QDeclarativeProperty)
```