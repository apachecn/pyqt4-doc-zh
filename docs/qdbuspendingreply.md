# QDBusPendingReply Class Reference

## [[QtDBus](index.htm) module]

该QDBusPendingReply类包含的答复异步方法调用[More...](#details)

继承[QDBusPendingCall](qdbuspendingcall.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDBusPendingReply other)`
*   `__init__ (self, QDBusPendingCall call)`
*   `__init__ (self, QDBusMessage reply)`
*   `QVariant argumentAt (self, int index)`
*   `QDBusError error (self)`
*   `bool isError (self)`
*   `bool isFinished (self)`
*   `bool isValid (self)`
*   `QDBusMessage reply (self)`
*   `object value (self, object type = None)`
*   `waitForFinished (self)`

* * *

## Detailed Description

该QDBusPendingReply类包含的答复异步方法调用

该QDBusPendingReply是一个模板类，多达8个模板参数。这些参数是将被用于提取的答复的数据的内容的类型。

这个类是类似的功能，[QDBusReply](qdbusreply.html)，但有两个重要的区别：

*   [QDBusReply](qdbusreply.html) accepts exactly one return type, whereas QDBusPendingReply can have from 1 to 8 types
*   [QDBusReply](qdbusreply.html) only works on already completed replies, whereas QDBusPendingReply allows one to wait for replies from pending calls

用在哪里[QDBusReply](qdbusreply.html)你可以这样写：

```
 [QDBusReply](qdbusreply.html)<[QString](qstring.html)> reply = interface->call("RemoteMethod");
 if (reply.isValid())
     // use the returned value
     useValue(reply.value());
 else
     // call failed. Show an error condition.
     showError(reply.error());

```

与QDBusPendingReply ，等效代码（包括您的答复阻塞等待）将是：

```
     QDBusPendingReply<[QString](qstring.html)> reply = interface->asyncCall("RemoteMethod");
     reply.waitForFinished();
     if (reply.isError())
         // call failed. Show an error condition.
         showError(reply.error());
     else
         // use the returned value
         useValue(reply.value());

```

对于方法调用具有多个输出参数，用[QDBusReply](qdbusreply.html)，你可以这样写：

```
 [QString](qstring.html) reply = interface->call("RemoteMethod");

```

而与QDBusPendingReply ，所有的输出参数应该是模板参数：

```
     QDBusPendingReply<bool, [QString](qstring.html)> reply = interface->asyncCall("RemoteMethod");
     reply.waitForFinished();
     if (!reply.isError()) {
         if (reply.argumentAt<0>())
             showSuccess(reply.argumentAt<1>());
         else
             showFailure(reply.argumentAt<1>());
     }

```

QDBusPendingReply对象可以关联[QDBusPendingCallWatcher](qdbuspendingcallwatcher.html)对象，它发出的信号，当回复到达。

* * *

## Method Documentation

```
QDBusPendingReply.__init__ (self)
```

创建一个空的[QDBusPendingReply](qdbuspendingreply.html)对象。而不设定[QDBusPendingCall](qdbuspendingcall.html)反对此回复，[QDBusPendingReply](qdbuspendingreply.html)什么都做不了。所有的函数都返回自己的失败值。

```
QDBusPendingReply.__init__ (self, QDBusPendingReply other)
```

创建的副本_other_ [QDBusPendingReply](qdbuspendingreply.html)对象。一样[QDBusPendingCall](qdbuspendingcall.html)和[QDBusPendingCallWatcher](qdbuspendingcallwatcher.html)，这[QDBusPendingReply](qdbuspendingreply.html)对象将共享同一个悬而未决的呼叫参考。所有副本共享相同的返回值。

```
QDBusPendingReply.__init__ (self, QDBusPendingCall call)
```

创建[QDBusPendingReply](qdbuspendingreply.html)对象，将采取它的内容从_call_挂起的异步调用。这[QDBusPendingReply](qdbuspendingreply.html)对象将共享相同的未决调用作为参考_call_。

```
QDBusPendingReply.__init__ (self, QDBusMessage reply)
```

创建[QDBusPendingReply](qdbuspendingreply.html)对象，将采取它的内容从消息_message_。在这种情况下，该对象将是已经在其成品状态和回复的内容将是可访问的。

**See also** [isFinished](qdbuspendingreply.html#isFinished)（ ） 。

```
QVariant QDBusPendingReply.argumentAt (self, int index)
```

返回参数的位置_index_在回复的内容。如果答复不具有的许多元素，这个函数的返回值是不确定的（可能会导致一个断言失败） ，所以要确认处理完毕，并答复是否有效是很重要的。

```
QDBusError QDBusPendingReply.error (self)
```

[](qdbuserror.html)

[检索应答消息的错误内容，如果它已完成处理。如果回复邮件尚未完成处理，或者如果它包含一个正常的回复讯息（非错误） ，这个函数返回一个无效的](qdbuserror.html)[QDBusError](qdbuserror.html)。

```
bool QDBusPendingReply.isError (self)
```

返回True如果应答包含一个错误信息，如果其包含一个正常的方法答复。

如果挂起调用还没有完成处理，该函数也返回True 。

```
bool QDBusPendingReply.isFinished (self)
```

返回True，如果待处理的呼叫完成处理和回复已经收到。如果这个函数返回True，则[isError](qdbuspendingreply.html#isError)（ ）[error](qdbuspendingreply.html#error)（）和[reply](qdbuspendingreply.html#reply)（ ）方法应该返回有效信息。

注意，这个函数只有改变状态，如果你调用[waitForFinished](qdbuspendingreply.html#waitForFinished)（ ），或者如果外部D-Bus的事件发生，这在一般如果返回到事件循环执行只发生。

**See also** [QDBusPendingCallWatcher.isFinished](qdbuspendingcallwatcher.html#isFinished)（ ） 。

```
bool QDBusPendingReply.isValid (self)
```

返回True如果应答包含一个正常的应答消息，如果其包含别的。

如果挂起调用还没有完成处理，这个函数返回False 。

```
QDBusMessage QDBusPendingReply.reply (self)
```

[](qdbusmessage.html)

[检索收到的异步调用的回复消息被发送，如果它已经完成处理。如果挂起调用还没有完成，这个函数返回一个](qdbusmessage.html)[QDBusMessage](qdbusmessage.html)类型[QDBusMessage.InvalidMessage](qdbusmessage.html#MessageType-enum)。

之后，它已经完成处理，消息类型要么是一个错误消息或一个正常的方法回复消息。

```
object QDBusPendingReply.value (self, object type = None)
```

返回此答复的第一个参数，强制转换为类型`T1`（这个类的第一个模板参数） 。这等效于调用argumentAt \u003c0\u003e （） 。

这个功能是为了方便，配套[QDBusReply.value](qdbusreply.html#value)（）函数。

需要注意的是，如果回答没有到达，这个函数会导致调用线程阻塞，直到答复处理。

```
QDBusPendingReply.waitForFinished (self)
```

挂起调用线程，直到收到回复和处理的执行。在此之后函数返回，[isFinished](qdbuspendingreply.html#isFinished)（ ）应该返回True，表示该回复的内容是准备进行处理。

**See also** [QDBusPendingCallWatcher.waitForFinished](qdbuspendingcallwatcher.html#waitForFinished)（ ） 。