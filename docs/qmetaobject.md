# QMetaObject Class Reference

## [[QtCore](index.htm) module]

该QMetaObject类包含有关Qt对象的元信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QMetaObject)`
*   `QMetaClassInfo classInfo (self, int index)`
*   `int classInfoCount (self)`
*   `int classInfoOffset (self)`
*   `str className (self)`
*   `QMetaMethod constructor (self, int index)`
*   `int constructorCount (self)`
*   `QMetaEnum enumerator (self, int index)`
*   `int enumeratorCount (self)`
*   `int enumeratorOffset (self)`
*   `int indexOfClassInfo (self, str name)`
*   `int indexOfConstructor (self, str constructor)`
*   `int indexOfEnumerator (self, str name)`
*   `int indexOfMethod (self, str method)`
*   `int indexOfProperty (self, str name)`
*   `int indexOfSignal (self, str signal)`
*   `int indexOfSlot (self, str slot)`
*   `QMetaMethod method (self, int index)`
*   `int methodCount (self)`
*   `int methodOffset (self)`
*   `QObject newInstance (self, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `QMetaProperty property (self, int index)`
*   `int propertyCount (self)`
*   `int propertyOffset (self)`
*   `QMetaObject superClass (self)`
*   `QMetaProperty userProperty (self)`

### Static Methods

*   `bool checkConnectArgs (str signal, str method)`
*   `connectSlotsByName (QObject o)`
*   `object invokeMethod (QObject obj, str member, Qt.ConnectionType type, QGenericReturnArgument ret, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `object invokeMethod (QObject obj, str member, QGenericReturnArgument ret, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `object invokeMethod (QObject obj, str member, Qt.ConnectionType type, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `object invokeMethod (QObject obj, str member, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `QByteArray normalizedSignature (str method)`
*   `QByteArray normalizedType (str type)`

* * *

## Detailed Description

该QMetaObject类包含有关Qt对象的元信息。

Qt的[Meta-Object System](index.htm#meta-object-system)在Qt是负责信号和槽的对象间通信机制，运行时类型信息，而Qt的属性系统。单QMetaObject实例为每个创建[QObject](qobject.html)子类，用于在应用程序中，并且该实例存储所有的元信息的[QObject](qobject.html)子类。该对象可作为[QObject.metaObject](qobject.html#metaObject)（ ） 。

此类不正常所需的应用程序，但如果你写的元应用，如脚本引擎或GUI构建器是有用的。

你是最有可能找到有用的功能是这些：

*   [className](qmetaobject.html#className)() returns the name of a class.
*   [superClass](qmetaobject.html#superClass)() returns the superclass's meta-object.
*   [method](qmetaobject.html#method)() and [methodCount](qmetaobject.html#methodCount)() provide information about a class's meta-methods (signals, slots and other [invokable](qobject.html#Q_INVOKABLE) member functions).
*   [enumerator](qmetaobject.html#enumerator)() and [enumeratorCount](qmetaobject.html#enumeratorCount)() and provide information about a class's enumerators.
*   [propertyCount](qmetaobject.html#propertyCount)() and [property](qmetaobject.html#property)() provide information about a class's properties.
*   [constructor](qmetaobject.html#constructor)() and [constructorCount](qmetaobject.html#constructorCount)() provide information about a class's meta-constructors.

该指数函数[indexOfConstructor](qmetaobject.html#indexOfConstructor)（ ）[indexOfMethod](qmetaobject.html#indexOfMethod)（ ）[indexOfEnumerator](qmetaobject.html#indexOfEnumerator)（）和[indexOfProperty](qmetaobject.html#indexOfProperty)（ ）构造函数，成员函数，枚举或属性索引的元对象的映射名称。举例来说， Qt使用[indexOfMethod](qmetaobject.html#indexOfMethod)（ ）内部，当你连接一个信号到一个槽。

类也可以有一个列表_name_ - _value_对其他的类信息，存储在[QMetaClassInfo](qmetaclassinfo.html)对象。对的数目是由返回[classInfoCount](qmetaobject.html#classInfoCount)（） ，单一对被返回[classInfo](qmetaobject.html#classInfo)（ ） ，您可以搜索与配对[indexOfClassInfo](qmetaobject.html#indexOfClassInfo)（ ） 。

* * *

## Method Documentation

```
QMetaObject.__init__ (self)
```

```
QMetaObject.__init__ (self, QMetaObject)
```

```
bool QMetaObject.checkConnectArgs (str signal, str method)
```

返回True如果_signal_和_method_参数是兼容的，否则返回False 。

Both _signal_和_method_预期将被归一化。

**See also** [normalizedSignature](qmetaobject.html#normalizedSignature)（ ） 。

```
QMetaClassInfo QMetaObject.classInfo (self, int index)
```

[

用给定的返回的元数据的类别信息的项目_index_。

例如：

](qmetaclassinfo.html)

```
 class MyClass : publicQObject
 {
     Q_OBJECT
     Q_CLASSINFO("author", "Sabrina Schweinsteiger")
     Q_CLASSINFO("url", "http://doc.moosesoft.co.uk/1.0/")

 public:
     ...
 };

```

**See also** [classInfoCount](qmetaobject.html#classInfoCount)（ ）[classInfoOffset](qmetaobject.html#classInfoOffset)（）和[indexOfClassInfo](qmetaobject.html#indexOfClassInfo)（ ） 。

```
int QMetaObject.classInfoCount (self)
```

返回类信息的项目在这个类别的数量。

**See also** [classInfo](qmetaobject.html#classInfo)（ ）[classInfoOffset](qmetaobject.html#classInfoOffset)（）和[indexOfClassInfo](qmetaobject.html#indexOfClassInfo)（ ） 。

```
int QMetaObject.classInfoOffset (self)
```

返回类此信息类抵消，也就是说这个类的第一类信息项的索引位置。

如果类没有父类与类的信息，偏移量为0 ，否则偏移量是在类的所有超类的类信息项的总和。

**See also** [classInfo](qmetaobject.html#classInfo)（ ）[classInfoCount](qmetaobject.html#classInfoCount)（）和[indexOfClassInfo](qmetaobject.html#indexOfClassInfo)（ ） 。

```
str QMetaObject.className (self)
```

返回类的名称。

**See also** [superClass](qmetaobject.html#superClass)（ ） 。

```
QMetaObject.connectSlotsByName (QObject o)
```

递归搜索对于给定的所有子对象_object_，并连接从它们的匹配信号的时隙_object_下面的格式如下：

```
 void on_<object name>_<signal name>(<signal parameters>);

```

让我们假定我们的对象类型的子对象[QPushButton](qpushbutton.html)与[object name](qobject.html#objectName-prop) `button1`。赶上按钮的插槽`clicked()`信号将是：

```
 void on_button1_clicked();

```

**See also** [QObject.setObjectName](qobject.html#objectName-prop)（ ） 。

```
QMetaMethod QMetaObject.constructor (self, int index)
```

[

返回的元数据用于构造具有给定_index_。

此功能被引入Qt的4.5 。

](qmetamethod.html)

[**See also**](qmetamethod.html) [constructorCount](qmetaobject.html#constructorCount)（）和[newInstance](qmetaobject.html#newInstance)（ ） 。

```
int QMetaObject.constructorCount (self)
```

返回构造函数在这个类的数量。

此功能被引入Qt的4.5 。

**See also** [constructor](qmetaobject.html#constructor)（）和[indexOfConstructor](qmetaobject.html#indexOfConstructor)（ ） 。

```
QMetaEnum QMetaObject.enumerator (self, int index)
```

[

返回的元数据枚举给定的_index_。

](qmetaenum.html)

[**See also**](qmetaenum.html) [enumeratorCount](qmetaobject.html#enumeratorCount)（ ）[enumeratorOffset](qmetaobject.html#enumeratorOffset)（）和[indexOfEnumerator](qmetaobject.html#indexOfEnumerator)（ ） 。

```
int QMetaObject.enumeratorCount (self)
```

返回普查员在这个类的数量。

**See also** [enumerator](qmetaobject.html#enumerator)（ ）[enumeratorOffset](qmetaobject.html#enumeratorOffset)（）和[indexOfEnumerator](qmetaobject.html#indexOfEnumerator)（ ） 。

```
int QMetaObject.enumeratorOffset (self)
```

返回枚举这个类的偏移，即这个类的第一个枚举的索引位置。

如果类没有父类与枚举，偏移量为0 ，否则偏移在类的超类的所有统计员的总和。

**See also** [enumerator](qmetaobject.html#enumerator)（ ）[enumeratorCount](qmetaobject.html#enumeratorCount)（）和[indexOfEnumerator](qmetaobject.html#indexOfEnumerator)（ ） 。

```
int QMetaObject.indexOfClassInfo (self, str name)
```

查找类信息项_name_并返回其索引，否则返回-1 。

**See also** [classInfo](qmetaobject.html#classInfo)（ ）[classInfoCount](qmetaobject.html#classInfoCount)（）和[classInfoOffset](qmetaobject.html#classInfoOffset)（ ） 。

```
int QMetaObject.indexOfConstructor (self, str constructor)
```

Finds _constructor_并返回其索引，否则返回-1 。

注意，这个_constructor_必须以标准化形式，如通过返回[normalizedSignature](qmetaobject.html#normalizedSignature)（ ） 。

此功能被引入Qt的4.5 。

**See also** [constructor](qmetaobject.html#constructor)（ ）[constructorCount](qmetaobject.html#constructorCount)（）和[normalizedSignature](qmetaobject.html#normalizedSignature)（ ） 。

```
int QMetaObject.indexOfEnumerator (self, str name)
```

查找枚举_name_并返回其索引，否则返回-1 。

**See also** [enumerator](qmetaobject.html#enumerator)（ ）[enumeratorCount](qmetaobject.html#enumeratorCount)（）和[enumeratorOffset](qmetaobject.html#enumeratorOffset)（ ） 。

```
int QMetaObject.indexOfMethod (self, str method)
```

Finds _method_并返回其索引，否则返回-1 。

注意，这个_method_必须以标准化形式，如通过返回[normalizedSignature](qmetaobject.html#normalizedSignature)（ ） 。

**See also** [method](qmetaobject.html#method)（ ）[methodCount](qmetaobject.html#methodCount)（ ）[methodOffset](qmetaobject.html#methodOffset)（）和[normalizedSignature](qmetaobject.html#normalizedSignature)（ ） 。

```
int QMetaObject.indexOfProperty (self, str name)
```

认定财产_name_并返回其索引，否则返回-1 。

**See also** [property](qmetaobject.html#property)（ ）[propertyCount](qmetaobject.html#propertyCount)（）和[propertyOffset](qmetaobject.html#propertyOffset)（ ） 。

```
int QMetaObject.indexOfSignal (self, str signal)
```

Finds _signal_并返回其索引，否则返回-1 。

这是相同的[indexOfMethod](qmetaobject.html#indexOfMethod)（） ，不同之处在于它会返回-1，如果存在的方法，但不是一个信号。

注意，这个_signal_必须以标准化形式，如通过返回[normalizedSignature](qmetaobject.html#normalizedSignature)（ ） 。

**See also** [indexOfMethod](qmetaobject.html#indexOfMethod)（ ）[normalizedSignature](qmetaobject.html#normalizedSignature)（ ）[method](qmetaobject.html#method)（ ）[methodCount](qmetaobject.html#methodCount)（）和[methodOffset](qmetaobject.html#methodOffset)（ ） 。

```
int QMetaObject.indexOfSlot (self, str slot)
```

Finds _slot_并返回其索引，否则返回-1 。

这是相同的[indexOfMethod](qmetaobject.html#indexOfMethod)（） ，不同之处在于它会返回-1，如果存在的方法，但不是一个时隙。

**See also** [indexOfMethod](qmetaobject.html#indexOfMethod)（ ）[method](qmetaobject.html#method)（ ）[methodCount](qmetaobject.html#methodCount)（）和[methodOffset](qmetaobject.html#methodOffset)（ ） 。

```
object QMetaObject.invokeMethod (QObject obj, str member, Qt.ConnectionType type, QGenericReturnArgument ret, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

调用_member_在对象上（一个信号或一个时隙名）_obj_。返回True如果该成员可被调用。返回False，如果没有这样的成员或参数不匹配。

该调用可以是同步或异步的，这取决于_type_：

*   If _type_ is [Qt.DirectConnection](qt.html#ConnectionType-enum), the member will be invoked immediately.
*   If _type_ is [Qt.QueuedConnection](qt.html#ConnectionType-enum), a [QEvent](qevent.html) will be sent and the member is invoked as soon as the application enters the main event loop.
*   If _type_ is [Qt.BlockingQueuedConnection](qt.html#ConnectionType-enum), the method will be invoked in the same way as for [Qt.QueuedConnection](qt.html#ConnectionType-enum), except that the current thread will block until the event is delivered. Using this connection type to communicate between objects in the same thread will lead to deadlocks.
*   If _type_ is [Qt.AutoConnection](qt.html#ConnectionType-enum), the member is invoked synchronously if _obj_ lives in the same thread as the caller; otherwise it will invoke the member asynchronously.

的返回值_member_函数调用被放置在_ret_。如果调用是异步的，则返回值无法评估。你可以通过多达十个参数（_val0_，_val1_，_val2_，_val3_，_val4_，_val5_，_val6_，_val7_，_val8_和_val9_）到_member_功能。

[QGenericArgument](qgenericargument.html)和[QGenericReturnArgument](qgenericreturnargument.html)是内部的辅助类。由于信号和槽可以动态调用，则必须使用附上参数[Q_ARG](qmetaobject.html#Q_ARG)（）和[Q_RETURN_ARG](qmetaobject.html#Q_RETURN_ARG)（ ）宏。[Q_ARG](qmetaobject.html#Q_ARG)（ ）接受一个类型名称和类型的const引用;[Q_RETURN_ARG](qmetaobject.html#Q_RETURN_ARG)（ ）接受一个类型名称和一个非const引用。

您只需要在信号或插槽的名称传递给这个函数，而不是整个签名。例如，异步调用[animateClick()](qabstractbutton.html#animateClick)插槽上[QPushButton](qpushbutton.html)，使用下面的代码：

```
 [QMetaObject](qmetaobject.html).invokeMethod(pushButton, "animateClick",
                           [Qt](qt.html).QueuedConnection);

```

对于异步方法调用时，参数必须是已知Qt的元对象系统类型，因为Qt的需要复制到它们存储在幕后事件的参数。如果您尝试使用一个排队的连接，并收到错误消息

```
 [QMetaObject](qmetaobject.html).invokeMethod: Unable to handle unregistered datatype 'MyType'

```

通话[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（）注册的数据类型调用的invokeMethod （）之前。

要同步调用`compute(QString, int, double)`插槽上的一些任意对象`obj`检索它的返回值：

```
 [QString](qstring.html) retVal;
 [QMetaObject](qmetaobject.html).invokeMethod(obj, "compute", [Qt](qt.html).DirectConnection,
                           Q_RETURN_ARG([QString](qstring.html), retVal),
                           Q_ARG([QString](qstring.html), "sqrt"),
                           Q_ARG(int, 42),
                           Q_ARG(double, 9.7));

```

如果“计算”老虎不采取只有一个[QString](qstring.html)一int和一间双人按照指定的顺序，则调用将失败。

**See also** [Q_ARG](qmetaobject.html#Q_ARG)（ ）[Q_RETURN_ARG](qmetaobject.html#Q_RETURN_ARG)（ ）[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（）和[QMetaMethod.invoke](qmetamethod.html#invoke)（ ） 。

```
object QMetaObject.invokeMethod (QObject obj, str member, QGenericReturnArgument ret, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

这个函数的重载[invokeMethod](qmetaobject.html#invokeMethod)（ ） 。

此重载始终使用连接类型调用成员[Qt.AutoConnection](qt.html#ConnectionType-enum)。

```
object QMetaObject.invokeMethod (QObject obj, str member, Qt.ConnectionType type, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

这个函数的重载[invokeMethod](qmetaobject.html#invokeMethod)（ ） 。

如果该成员的返回值是没有兴趣此重载都可以使用。

```
object QMetaObject.invokeMethod (QObject obj, str member, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

这个函数的重载[invokeMethod](qmetaobject.html#invokeMethod)（ ） 。

使用的连接类型此重载调用成员[Qt.AutoConnection](qt.html#ConnectionType-enum)并忽略返回值。

```
QMetaMethod QMetaObject.method (self, int index)
```

[

返回的元数据的方法，用给定的_index_。

](qmetamethod.html)

[**See also**](qmetamethod.html) [methodCount](qmetaobject.html#methodCount)（ ）[methodOffset](qmetaobject.html#methodOffset)（）和[indexOfMethod](qmetaobject.html#indexOfMethod)（ ） 。

```
int QMetaObject.methodCount (self)
```

返回在这个类中已知的元对象系统的方法数，包括每一个基类提供的属性的数量。这些措施包括信号和槽以及与声明的成员函数[Q_INVOKABLE](qobject.html#Q_INVOKABLE)宏。

使用如下所示的代码来获得[QStringList](qstringlist.html)包含特定于给定类中的方法：

```
 const [QMetaObject](qmetaobject.html)* metaObject = obj->metaObject();
 [QStringList](qstringlist.html) methods;
 for(int i = metaObject->methodOffset(); i < metaObject->methodCount(); ++i)
     methods << [QString](qstring.html).fromLatin1(metaObject->method(i).signature());

```

**See also** [method](qmetaobject.html#method)（ ）[methodOffset](qmetaobject.html#methodOffset)（）和[indexOfMethod](qmetaobject.html#indexOfMethod)（ ） 。

```
int QMetaObject.methodOffset (self)
```

返回方法这个类的偏移，即这个类的一个成员函数的索引位置。

偏移量是在类的超类的所有方法（之和这始终是积极的，因为[QObject](qobject.html)有deleteLater （）槽和销毁（ ）信号） 。

**See also** [method](qmetaobject.html#method)（ ）[methodCount](qmetaobject.html#methodCount)（）和[indexOfMethod](qmetaobject.html#indexOfMethod)（ ） 。

```
QObject QMetaObject.newInstance (self, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

[

构造此类的一个新实例。你可以通过多达十个参数（_val0_，_val1_，_val2_，_val3_，_val4_，_val5_，_val6_，_val7_，_val8_和_val9_）给构造函数。返回新对象，或者0，如果没有合适的构造函数是可用的。

](qobject.html)

[请注意，只有建构与该声明](qobject.html)[Q_INVOKABLE](qobject.html#Q_INVOKABLE)改性剂是通过元对象系统提供。

此功能被引入Qt的4.5 。

**See also** [Q_ARG](qmetaobject.html#Q_ARG)（）和[constructor](qmetaobject.html#constructor)（ ） 。

```
QByteArray QMetaObject.normalizedSignature (str method)
```

[

归一给定的签名_method_。

Qt使用归一化签名来决定两个给定信号和槽是否兼容。正常化减少空白到最低限度，移动'常量'到前面在适当情况下，删除'常量'的值类型和替换值的常量引用。

](qbytearray.html)

[**See also**](qbytearray.html) [checkConnectArgs](qmetaobject.html#checkConnectArgs)（）和[normalizedType](qmetaobject.html#normalizedType)（ ） 。

```
QByteArray QMetaObject.normalizedType (str type)
```

[

归一_type_。

](qbytearray.html)

[See](qbytearray.html) [QMetaObject.normalizedSignature](qmetaobject.html#normalizedSignature)（ ）上的Qt如何标准化的描述。

例如：

```
 [QByteArray](qbytearray.html) normType = [QMetaObject](qmetaobject.html).normalizedType(" int    const  *");
 // normType is now "const int*"

```

这个函数中引入了Qt 4.2中。

**See also** [normalizedSignature](qmetaobject.html#normalizedSignature)（ ） 。

```
QMetaProperty QMetaObject.property (self, int index)
```

[](qmetaproperty.html)

[用给定的返回的元数据的属性_index_。如果没有这样的属性存在，空](qmetaproperty.html)[QMetaProperty](qmetaproperty.html)返回。

**See also** [propertyCount](qmetaobject.html#propertyCount)（ ）[propertyOffset](qmetaobject.html#propertyOffset)（）和[indexOfProperty](qmetaobject.html#indexOfProperty)（ ） 。

```
int QMetaObject.propertyCount (self)
```

返回这个类的属性的数量，包括每一个基类提供的属性的数量。

使用如下所示的代码来获得[QStringList](qstringlist.html)包含特定于某个给定的类的属性：

```
 const [QMetaObject](qmetaobject.html)* metaObject = obj->metaObject();
 [QStringList](qstringlist.html) properties;
 for(int i = metaObject->propertyOffset(); i < metaObject->propertyCount(); ++i)
     properties << [QString](qstring.html).fromLatin1(metaObject->property(i).name());

```

**See also** [property](qmetaobject.html#property)（ ）[propertyOffset](qmetaobject.html#propertyOffset)（）和[indexOfProperty](qmetaobject.html#indexOfProperty)（ ） 。

```
int QMetaObject.propertyOffset (self)
```

返回属性为这个类的偏移，即这个类的第一个属性的索引位置。

偏移量是在类的超类的所有属性的总和（这始终是积极的，因为[QObject](qobject.html)具有（）的名称属性） 。

**See also** [property](qmetaobject.html#property)（ ）[propertyCount](qmetaobject.html#propertyCount)（）和[indexOfProperty](qmetaobject.html#indexOfProperty)（ ） 。

```
QMetaObject QMetaObject.superClass (self)
```

[

返回超类，或0的元对象，如果没有这样的对象。

](qmetaobject.html)

[**See also**](qmetaobject.html) [className](qmetaobject.html#className)（ ） 。

```
QMetaProperty QMetaObject.userProperty (self)
```

[

返回具有该属性的`USER`标志设置为True 。

这个函数中引入了Qt 4.2中。

](qmetaproperty.html)

[**See also**](qmetaproperty.html) [QMetaProperty.isUser](qmetaproperty.html#isUser)（ ） 。