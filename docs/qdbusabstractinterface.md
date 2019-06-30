# QDBusAbstractInterface Class Reference

## [[QtDBus](index.htm) module]

该QDBusAbstractInterface类是在所有的D-Bus接口的基类[QtDBus](index.htm)对远程接口绑定，允许访问[More...](#details)

继承[QObject](qobject.html)。

通过继承[QDBusConnectionInterface](qdbusconnectioninterface.html)和[QDBusInterface](qdbusinterface.html)。

### Methods

*   `__init__ (self, QString service, QString path, str interface, QDBusConnection connection, QObject parent)`
*   `QDBusPendingCall asyncCall (self, QString method, QVariant arg1 = QVariant(), QVariant arg2 = QVariant(), QVariant arg3 = QVariant(), QVariant arg4 = QVariant(), QVariant arg5 = QVariant(), QVariant arg6 = QVariant(), QVariant arg7 = QVariant(), QVariant arg8 = QVariant())`
*   `QDBusPendingCall asyncCallWithArgumentList (self, QString method, list-of-QVariant args)`
*   `QDBusMessage call (self, QString method, QVariant arg1 = QVariant(), QVariant arg2 = QVariant(), QVariant arg3 = QVariant(), QVariant arg4 = QVariant(), QVariant arg5 = QVariant(), QVariant arg6 = QVariant(), QVariant arg7 = QVariant(), QVariant arg8 = QVariant())`
*   `QDBusMessage call (self, QDBus.CallMode mode, QString method, QVariant arg1 = QVariant(), QVariant arg2 = QVariant(), QVariant arg3 = QVariant(), QVariant arg4 = QVariant(), QVariant arg5 = QVariant(), QVariant arg6 = QVariant(), QVariant arg7 = QVariant(), QVariant arg8 = QVariant())`
*   `QDBusMessage callWithArgumentList (self, QDBus.CallMode mode, QString method, list-of-QVariant args)`
*   `bool callWithCallback (self, QString method, list-of-QVariant args, QObject receiver, SLOT() returnMethod, SLOT() errorMethod)`
*   `object callWithCallback (self, QString method, list-of-QVariant args, callable returnMethod, callable errorMethod)`
*   `bool callWithCallback (self, QString method, list-of-QVariant args, QObject receiver, SLOT() slot)`
*   `object callWithCallback (self, QString method, list-of-QVariant args, callable slot)`
*   `QDBusConnection connection (self)`
*   `connectNotify (self, SIGNAL() signal)`
*   `disconnectNotify (self, SIGNAL() signal)`
*   `QString interface (self)`
*   `bool isValid (self)`
*   `QDBusError lastError (self)`
*   `QString path (self)`
*   `QString service (self)`
*   `setTimeout (self, int timeout)`
*   `int timeout (self)`

* * *

## Detailed Description

该QDBusAbstractInterface类是在所有的D-Bus接口的基类[QtDBus](index.htm)对远程接口绑定，允许访问

生成的代码类也从QDBusAbstractInterface派生，这里所描述的所有方法也适用于生成代码的类。除了这里描述的那些生成代码的类提供对远程方法的成员函数，它允许对正确的参数编译时检查和返回值，以及物业类型匹配和信号参数匹配。

* * *

## Method Documentation

```
QDBusAbstractInterface.__init__ (self, QString service, QString path, str interface, QDBusConnection connection, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
QDBusPendingCall QDBusAbstractInterface.asyncCall (self, QString method, QVariant arg1 = QVariant(), QVariant arg2 = QVariant(), QVariant arg3 = QVariant(), QVariant arg4 = QVariant(), QVariant arg5 = QVariant(), QVariant arg6 = QVariant(), QVariant arg7 = QVariant(), QVariant arg8 = QVariant())
```

[

调用该方法_method_在该接口上，并传递参数给此函数的方法。

](qdbuspendingcall.html)

[的参数，以`call`被传递到通过D-Bus的远程函数作为输入参数。返回](qdbuspendingcall.html)[QDBusPendingCall](qdbuspendingcall.html)对象可以用来了解的回复信息。

此功能可与多达8个参数，在参数传递中使用_arg1_，_arg2_，_arg3_，_arg4_，_arg5_，_arg6_，_arg7_和_arg8_。如果您需要超过8个参数，或者如果你有一个可变数目的参数传递，使用[asyncCallWithArgumentList](qdbusabstractinterface.html#asyncCallWithArgumentList)（ ） 。

它可用于以下方式：

```
 [QString](qstring.html) value = retrieveValue();
 [QDBusPendingCall](qdbuspendingcall.html) pcall = interface->asyncCall(QLatin1String("Process"), value);

 [QDBusPendingCallWatcher](qdbuspendingcallwatcher.html) *watcher = new [QDBusPendingCallWatcher](qdbuspendingcallwatcher.html)(pcall, this);

 [QObject](qobject.html).connect(watcher, SIGNAL(finished([QDBusPendingCallWatcher](qdbuspendingcallwatcher.html)*)),
                  this, SLOT(callFinishedSlot([QDBusPendingCallWatcher](qdbuspendingcallwatcher.html)*)));

```

这个例子说明了函数调用与0 ， 1​​和2的参数，并说明在每个传递不同的参数类型（第一通电话`"ProcessWorkUnicode"`将包含一个Unicode字符串，第二次调用`"ProcessWork"`将包含一个字符串和一个字节数组） 。

此功能被引入Qt的4.5 。

```
QDBusPendingCall QDBusAbstractInterface.asyncCallWithArgumentList (self, QString method, list-of-QVariant args)
```

[](qdbuspendingcall.html)

[由地方指定调用远程方法_method_在该接口上，使用_args_作为参数。这个函数返回一个](qdbuspendingcall.html)[QDBusPendingCall](qdbuspendingcall.html)对象，该对象可以被用来跟踪答复的状态，一旦它已经到达访问其内容。

通常情况下，你应该使用拨打电话[asyncCall](qdbusabstractinterface.html#asyncCall)（ ） 。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

此功能被引入Qt的4.5 。

```
QDBusMessage QDBusAbstractInterface.call (self, QString method, QVariant arg1 = QVariant(), QVariant arg2 = QVariant(), QVariant arg3 = QVariant(), QVariant arg4 = QVariant(), QVariant arg5 = QVariant(), QVariant arg6 = QVariant(), QVariant arg7 = QVariant(), QVariant arg8 = QVariant())
```

[

调用该方法_method_在该接口上，并传递参数给此函数的方法。

](qdbusmessage.html)

[的参数，以`call`被传递到通过D-Bus的远程函数作为输入参数。输出参数中返回的](qdbusmessage.html)[QDBusMessage](qdbusmessage.html)回复。如果回答是错误的答复，[lastError](qdbusabstractinterface.html#lastError)（）也将被设置到该错误消息的内容。

此功能可与多达8个参数，在参数传递中使用_arg1_，_arg2_，_arg3_，_arg4_，_arg5_，_arg6_，_arg7_和_arg8_。如果您需要超过8个参数，或者如果你有一个可变数目的参数传递，使用[callWithArgumentList](qdbusabstractinterface.html#callWithArgumentList)（ ） 。

它可用于以下方式：

```
 [QString](qstring.html) value = retrieveValue();
 [QDBusMessage](qdbusmessage.html) reply;

 [QDBusReply](qdbusreply.html)<int> api = interface->call(QLatin1String("GetAPIVersion"));
 if (api >= 14)
   reply = interface->call(QLatin1String("ProcessWorkUnicode"), value);
 else
   reply = interface->call(QLatin1String("ProcessWork"), QLatin1String("UTF-8"), value.toUtf8());

```

这个例子说明了函数调用与0 ， 1​​和2的参数，并说明在每个传递不同的参数类型（第一通电话`"ProcessWorkUnicode"`将包含一个Unicode字符串，第二次调用`"ProcessWork"`将包含一个字符串和一个字节数组） 。

```
QDBusMessage QDBusAbstractInterface.call (self, QDBus.CallMode mode, QString method, QVariant arg1 = QVariant(), QVariant arg2 = QVariant(), QVariant arg3 = QVariant(), QVariant arg4 = QVariant(), QVariant arg5 = QVariant(), QVariant arg6 = QVariant(), QVariant arg7 = QVariant(), QVariant arg8 = QVariant())
```

[

这是一个重载函数。

调用该方法_method_在该接口上，并传递参数给此函数的方法。如果_mode_ is `NoWaitForReply`，那么这个功能将发出呼叫后立即返回，而不等待来自远程方法的答复。否则，_mode_表示该功能是否应该启动了Qt事件循环在等待答复的到来。

](qdbusmessage.html)

[此功能可与多达8个参数，在参数传递中使用_arg1_，_arg2_，_arg3_，_arg4_，_arg5_，_arg6_，_arg7_和_arg8_。如果您需要超过8个参数，或者如果你有一个可变数目的参数传递，使用](qdbusmessage.html)[callWithArgumentList](qdbusabstractinterface.html#callWithArgumentList)（ ） 。

如果此功能重新进入Qt的事件循环，以等待答复，这将排除用户输入。在等待期间，它可能会带来信号和其他方法调用您的应用程序。因此，它必须准备处理重入每当一个呼叫被置于与[call](qdbusabstractinterface.html#call)（ ） 。

```
QDBusMessage QDBusAbstractInterface.callWithArgumentList (self, QDBus.CallMode mode, QString method, list-of-QVariant args)
```

[](qdbusmessage.html)

[由地方指定调用远程方法_method_在该接口上，使用_args_作为参数。这个函数返回接收的答复消息，它可以是一个正常的](qdbusmessage.html)[QDBusMessage.ReplyMessage](qdbusmessage.html#MessageType-enum)（表示成功）或[QDBusMessage.ErrorMessage](qdbusmessage.html#MessageType-enum)（如果调用失败） 。该_mode_参数指定如何调用应放置。

如果调用成功，[lastError](qdbusabstractinterface.html#lastError)（ ）将被清零，否则，它会包含这个调用产生的误差。

通常情况下，你应该使用拨打电话[call](qdbusabstractinterface.html#call)（ ） 。

**Warning:**如果你使用`UseEventLoop`，您的代码必须准备好应对任何重入：其他方法调用和信号，可能这个函数返回前交付，以及其他排队Qt的信号和事件。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

```
bool QDBusAbstractInterface.callWithCallback (self, QString method, list-of-QVariant args, QObject receiver, SLOT() returnMethod, SLOT() errorMethod)
```

由地方指定调用远程方法_method_在该接口上，使用_args_作为参数。排队的呼叫后，立即这个函数返回。从遥控功能的答复被传递到_returnMethod_对象_receiver_。如果发生错误，则_errorMethod_对象_receiver_被称为代替。

如果排队成功，该函数返回True。这并不表示该执行调用成功。如果失败，则_errorMethod_被调用。如果排队失败，这个函数返回False ，没有插槽将被调用。

该_returnMethod_必须有作为它的参数的函数调用返回的类型。任选地，它可具有[QDBusMessage](qdbusmessage.html)参数作为它的最后一个或唯一的参数。该_errorMethod_必须有一个[QDBusError](qdbuserror.html)作为其唯一的参数。

此功能被引入Qt的4.3 。

**See also** [QDBusError](qdbuserror.html)和[QDBusMessage](qdbusmessage.html)。

```
object QDBusAbstractInterface.callWithCallback (self, QString method, list-of-QVariant args, callable returnMethod, callable errorMethod)
```

这是一个重载函数。

此功能已被弃用。请使用重载版本。

由地方指定调用远程方法_method_在该接口上，使用_args_作为参数。排队的呼叫后，立即这个函数返回。从远程功能或所发出任何错误的回复被传递到_slot_插槽上的对象_receiver_。

如果排队成功该函数返回True ：它并不表示调用成功。如果它失败了，该槽被调用并显示一条错误消息。[lastError](qdbusabstractinterface.html#lastError)（ ）将不会在这些情况下设定。

**See also** [QDBusError](qdbuserror.html)和[QDBusMessage](qdbusmessage.html)。

```
bool QDBusAbstractInterface.callWithCallback (self, QString method, list-of-QVariant args, QObject receiver, SLOT() slot)
```

```
object QDBusAbstractInterface.callWithCallback (self, QString method, list-of-QVariant args, callable slot)
```

```
QDBusConnection QDBusAbstractInterface.connection (self)
```

[

返回此接口assocated与连接。

```
QDBusAbstractInterface.connectNotify (self, SIGNAL() signal)
```

```
QDBusAbstractInterface.disconnectNotify (self, SIGNAL() signal)
```

```
QString QDBusAbstractInterface.interface (self)
```

返回此接口的名称。

```
bool QDBusAbstractInterface.isValid (self)
```

返回True如果这是一个有效的参考远程对象。如果创建这个接口的（例如，如果远程应用程序不存在）期间发生了错误，则返回False 。

](qdbusconnection.html)

[注意：当与远程对象时，它并不总是可能的，以确定它创建时存在一个](qdbusconnection.html)[QDBusInterface](qdbusinterface.html)。

```
QDBusError QDBusAbstractInterface.lastError (self)
```

[

返回错误产生的最后一个操作，或无效的错误，如果上次操作没有产生一个错误。

```
QString QDBusAbstractInterface.path (self)
```

```
QString QDBusAbstractInterface.service (self)
```

返回该接口相关联的服务的名称。

```
QDBusAbstractInterface.setTimeout (self, int timeout)
```

设置以毫秒为单位的超时以后所有乌思调用_timeout_。 -1表示默认乌思超时时间（通常为25秒） 。

此功能被引入Qt的4.8 。

](qdbuserror.html)

[**See also**](qdbuserror.html) [timeout](qdbusabstractinterface.html#timeout)（ ） 。

```
int QDBusAbstractInterface.timeout (self)
```

返回以毫秒为单位的超时时间的当前值。 -1表示默认乌思超时时间（通常为25秒） 。

此功能被引入Qt的4.8 。

**See also** [setTimeout](qdbusabstractinterface.html#setTimeout)（ ） 。