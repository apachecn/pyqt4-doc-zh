# QDBusReply Class Reference

## [[QtDBus](index.htm) module]

该QDBusReply类存储为一个方法调用远程对象的答复。[More...](#details)

### Methods

*   `__init__ (self, QDBusMessage reply)`
*   `__init__ (self, QDBusPendingCall call)`
*   `__init__ (self, QDBusError error)`
*   `__init__ (self, QDBusReply other)`
*   `QDBusError error (self)`
*   `bool isValid (self)`
*   `object value (self, object type = None)`

* * *

## Detailed Description

该QDBusReply类存储为一个方法调用远程对象的答复。

一个QDBusReply对象的一个子集[QDBusMessage](qdbusmessage.html)对象，表示一个方法调用的答复。它仅包含第一个输出参数或错误代码，并使用[QDBusInterface](qdbusinterface.html)派生类，允许错误代码返回为函数的返回参数。

它可以以下面的方式被使用：

```
 QDBusReply<[QString](qstring.html)> reply = interface->call("RemoteMethod");
 if (reply.isValid())
     // use the returned value
     useValue(reply.value());
 else
     // call failed. Show an error condition.
     showError(reply.error());

```

如果远程方法调用不能失败，你可以跳过错误检查：

```
 [QString](qstring.html) reply = interface->call("RemoteMethod");

```

然而，如果它确实在这些条件下发生故障，返回的值[QDBusReply.value](qdbusreply.html#value)（）是一个缺省构造值。它可能是从一个有效的返回值没有什么区别。

QDBusReply对象用于为没有输出参数或返回值（即，他们有一个“空”返回类型）的远程调用。使用[isValid](qdbusreply.html#isValid)（ ）函数来测试是否回复成功。

* * *

## Method Documentation

```
QDBusReply.__init__ (self, QDBusMessage reply)
```

自动构建[QDBusReply](qdbusreply.html)从回复消息对象_reply_，提取它的第一个返回值，如果它是成功的回复。

```
QDBusReply.__init__ (self, QDBusPendingCall call)
```

自动构建[QDBusReply](qdbusreply.html)从挂起的异步调用对象_pcall_。如果呼叫尚未完成，[QDBusReply](qdbusreply.html)将调用QDBusPendingCall.waitForFinished （），它是一个阻塞操作。

如果返回类型的补丁，[QDBusReply](qdbusreply.html)将提取的答复的第一个返回参数。

```
QDBusReply.__init__ (self, QDBusError error)
```

构造一个[QDBusReply](qdbusreply.html)从挂起的回复消息对象，_reply_。

```
QDBusReply.__init__ (self, QDBusReply other)
```

从构造由下式给出了D-Bus的错误代码的错误答复_error_。

```
QDBusError QDBusReply.error (self)
```

[](qdbuserror.html)

[返回从远程函数调用返回的错误代码。如果远程调用没有返回一个错误（例如，如果它成功了） ，那么](qdbuserror.html)[QDBusError](qdbuserror.html)返回的对象将不会是一个有效的错误代码（[QDBusError.isValid](qdbuserror.html#isValid)（ ）将返回False ） 。

**See also** [isValid](qdbusreply.html#isValid)（ ） 。

```
bool QDBusReply.isValid (self)
```

返回True如果没有发生错误，否则返回False 。

**See also** [error](qdbusreply.html#error)（ ） 。

```
object QDBusReply.value (self, object type = None)
```

返回远程函数调用的返回值。如果远程调用返回一个错误，这个函数的返回值是不确定的，可能是从一个有效的返回值无法区分。

此功能无法使用，如果远程调用返回`void`。