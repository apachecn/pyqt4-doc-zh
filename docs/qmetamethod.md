# QMetaMethod Class Reference

## [[QtCore](index.htm) module]

该QMetaMethod类提供的成员函数的元数据。[More...](#details)

### Types

*   `enum Access { Private, Protected, Public }`
*   `enum MethodType { Method, Signal, Slot, Constructor }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QMetaMethod)`
*   `Access access (self)`
*   `object invoke (self, QObject object, Qt.ConnectionType connectionType, QGenericReturnArgument returnValue, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `object invoke (self, QObject object, QGenericReturnArgument returnValue, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `object invoke (self, QObject object, Qt.ConnectionType connectionType, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `object invoke (self, QObject object, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))`
*   `int methodIndex (self)`
*   `MethodType methodType (self)`
*   `list-of-QByteArray parameterNames (self)`
*   `list-of-QByteArray parameterTypes (self)`
*   `str signature (self)`
*   `str tag (self)`
*   `str typeName (self)`

* * *

## Detailed Description

该QMetaMethod类提供的成员函数的元数据。

一个QMetaMethod有[methodType](qmetamethod.html#methodType)（）的一个[signature](qmetamethod.html#signature)（ ）的列表[parameterTypes](qmetamethod.html#parameterTypes)（）和[parameterNames](qmetamethod.html#parameterNames)（ ） ，返回[typeName](qmetamethod.html#typeName)（）的一个[tag](qmetamethod.html#tag)（） ，和一个[access](qmetamethod.html#access)（ ）说明。您可以使用[invoke](qmetamethod.html#invoke)（ ）来调用方法上的任意[QObject](qobject.html)。

的方法，将只登记了元对象系统，如果它是一个槽，一个信号，或者与所声明的[Q_INVOKABLE](qobject.html#Q_INVOKABLE)宏。构造也可以与注册[Q_INVOKABLE](qobject.html#Q_INVOKABLE)。

* * *

## Type Documentation

```
QMetaMethod.Access
```

这个枚举变量描述的方法的访问级别，下面在C + +中使用的约定。

| Constant | Value |
| --- | --- |
| `QMetaMethod.Private` | `0` |
| `QMetaMethod.Protected` | `1` |
| `QMetaMethod.Public` | `2` |

```
QMetaMethod.MethodType
```

| Constant | Value | Description |
| --- | --- | --- |
| `QMetaMethod.Method` | `0` | 该函数是一个普通的成员函数。 |
| `QMetaMethod.Signal` | `1` | 该函数是一个信号。 |
| `QMetaMethod.Slot` | `2` | 该函数是一个槽。 |
| `QMetaMethod.Constructor` | `3` | 该函数是一个构造函数。 |

* * *

## Method Documentation

```
QMetaMethod.__init__ (self)
```

```
QMetaMethod.__init__ (self, QMetaMethod)
```

```
Access QMetaMethod.access (self)
```

[

返回此方法（私有，保护，或公共）的访问规范。

信号始终受到保护，这意味着你只能从类或子类发出它们。

](qmetamethod.html#Access-enum)

[**See also**](qmetamethod.html#Access-enum) [methodType](qmetamethod.html#methodType)（ ） 。

```
object QMetaMethod.invoke (self, QObject object, Qt.ConnectionType connectionType, QGenericReturnArgument returnValue, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

调用此方法的对象上_object_。返回True如果该成员可被调用。返回False，如果没有这样的成员或参数不匹配。

该调用可以是同步或异步的，这取决于_connectionType_：

*   If _connectionType_ is [Qt.DirectConnection](qt.html#ConnectionType-enum), the member will be invoked immediately.
*   If _connectionType_ is [Qt.QueuedConnection](qt.html#ConnectionType-enum), a [QEvent](qevent.html) will be posted and the member is invoked as soon as the application enters the main event loop.
*   If _connectionType_ is [Qt.AutoConnection](qt.html#ConnectionType-enum), the member is invoked synchronously if _object_ lives in the same thread as the caller; otherwise it will invoke the member asynchronously.

这个方法调用的返回值放在_returnValue_。如果调用是异步的，则返回值无法评估。你可以通过多达十个参数（_val0_，_val1_，_val2_，_val3_，_val4_，_val5_，_val6_，_val7_，_val8_和_val9_）这个方法调用。

[QGenericArgument](qgenericargument.html)和[QGenericReturnArgument](qgenericreturnargument.html)是内部的辅助类。由于信号和槽可以动态调用，则必须使用附上参数[Q_ARG](qmetaobject.html#Q_ARG)（）和[Q_RETURN_ARG](qmetaobject.html#Q_RETURN_ARG)（ ）宏。[Q_ARG](qmetaobject.html#Q_ARG)（ ）接受一个类型名称和类型的const引用;[Q_RETURN_ARG](qmetaobject.html#Q_RETURN_ARG)（ ）接受一个类型名称和一个非const引用。

异步调用的[animateClick()](qabstractbutton.html#animateClick)插槽上[QPushButton](qpushbutton.html)：

```
 int methodIndex = pushButton->metaObject()->indexOfMethod("animateClick()");
 [QMetaMethod](qmetamethod.html) method = metaObject->method(methodIndex);
 method.invoke(pushButton, [Qt](qt.html).QueuedConnection);

```

对于异步方法调用时，参数必须是已知Qt的元对象系统类型，因为Qt的需要复制到它们存储在幕后事件的参数。如果您尝试使用一个排队的连接，并收到错误消息

```
 [QMetaMethod](qmetamethod.html).invoke: Unable to handle unregistered datatype 'MyType'

```

通话[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（）注册的数据类型调用QMetaMethod.invoke （）之前。

要同步调用`compute(QString, int, double)`插槽上的一些任意对象`obj`检索它的返回值：

```
 [QString](qstring.html) retVal;
 [QByteArray](qbytearray.html) normalizedSignature = [QMetaObject](qmetaobject.html).normalizedSignature("compute(QString, int, double)");
 int methodIndex = obj->metaObject()->indexOfMethod(normalizedSignature);
 [QMetaMethod](qmetamethod.html) method = metaObject->method(methodIndex);
 method.invoke(obj,
               [Qt](qt.html).DirectConnection,
               Q_RETURN_ARG([QString](qstring.html), retVal),
               Q_ARG([QString](qstring.html), "sqrt"),
               Q_ARG(int, 42),
               Q_ARG(double, 9.7));

```

[QMetaObject.normalizedSignature](qmetaobject.html#normalizedSignature)（）被用在这里，以确保签名的格式是什么调用（）期望。例如多馀的空格被删除。

如果“计算”老虎不采取只有一个[QString](qstring.html)一int和一间双人按照指定的顺序，则调用将失败。

**Warning:**这种方法不会测试的参数的有效性：_object_必须是类的实例[QMetaObject](qmetaobject.html)而本[QMetaMethod](qmetamethod.html)已建成使用。该参数必须具有相同的类型的那些预期通过该方法，否则，该行为是未定义的。

**See also** [Q_ARG](qmetaobject.html#Q_ARG)（ ）[Q_RETURN_ARG](qmetaobject.html#Q_RETURN_ARG)（ ）[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（）和[QMetaObject.invokeMethod](qmetaobject.html#invokeMethod)（ ） 。

```
object QMetaMethod.invoke (self, QObject object, QGenericReturnArgument returnValue, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

这个函数的重载[invoke](qmetamethod.html#invoke)（ ） 。

此重载始终使用连接类型调用该方法[Qt.AutoConnection](qt.html#ConnectionType-enum)。

```
object QMetaMethod.invoke (self, QObject object, Qt.ConnectionType connectionType, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

这个函数的重载[invoke](qmetamethod.html#invoke)（ ） 。

如果该成员的返回值是没有兴趣此重载都可以使用。

```
object QMetaMethod.invoke (self, QObject object, QGenericArgument value0 = QGenericArgument(0,0), QGenericArgument value1 = QGenericArgument(0,0), QGenericArgument value2 = QGenericArgument(0,0), QGenericArgument value3 = QGenericArgument(0,0), QGenericArgument value4 = QGenericArgument(0,0), QGenericArgument value5 = QGenericArgument(0,0), QGenericArgument value6 = QGenericArgument(0,0), QGenericArgument value7 = QGenericArgument(0,0), QGenericArgument value8 = QGenericArgument(0,0), QGenericArgument value9 = QGenericArgument(0,0))
```

这个函数的重载[invoke](qmetamethod.html#invoke)（ ） 。

使用的连接类型此重载调用该方法[Qt.AutoConnection](qt.html#ConnectionType-enum)并忽略返回值。

```
int QMetaMethod.methodIndex (self)
```

返回此方法的指数。

此功能被引入Qt的4.6 。

```
MethodType QMetaMethod.methodType (self)
```

[

返回此方法（信号，槽，或方法）的类型。

](qmetamethod.html#MethodType-enum)

[**See also**](qmetamethod.html#MethodType-enum) [access](qmetamethod.html#access)（ ） 。

```
list-of-QByteArray QMetaMethod.parameterNames (self)
```

返回参数名称的列表。

**See also** [parameterTypes](qmetamethod.html#parameterTypes)（）和[signature](qmetamethod.html#signature)（ ） 。

```
list-of-QByteArray QMetaMethod.parameterTypes (self)
```

返回参数类型的列表。

**See also** [parameterNames](qmetamethod.html#parameterNames)（）和[signature](qmetamethod.html#signature)（ ） 。

```
str QMetaMethod.signature (self)
```

返回此方法的签名（例如，`setValue(double)`） 。

**See also** [parameterTypes](qmetamethod.html#parameterTypes)（）和[parameterNames](qmetamethod.html#parameterNames)（ ） 。

```
str QMetaMethod.tag (self)
```

返回与此方法关联的标记。

标籤是由公认的特殊宏`moc`这使人们有可能添加有关方法的额外信息。

标籤信息可以在函数声明如下方式添加：

```
 #define THISISTESTTAG // tag text
 ...
 private slots:
     THISISTESTTAG void testFunc();

```

并且信息可以通过使用如下方式访问：

```
 MainWindow win;
 win.show();

 int functionIndex = win.metaObject()->indexOfSlot("testFunc()");
 [QMetaMethod](qmetamethod.html) mm = metaObject()->method(functionIndex);
 qDebug() << mm.tag(); // prints THISISTESTTAG

```

就目前而言，`moc`不支持任何特殊的标记。

```
str QMetaMethod.typeName (self)
```

返回此方法的返回类型，或空字符串，如果返回类型是_void_。