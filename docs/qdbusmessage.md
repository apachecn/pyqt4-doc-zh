# QDBusMessage Class Reference

## [[QtDBus](index.htm) module]

该QDBusMessage类表示发送或接收通过D - Bus总线一个消息。[More...](#details)

### Types

*   `enum MessageType { InvalidMessage, MethodCallMessage, ReplyMessage, ErrorMessage, SignalMessage }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDBusMessage other)`
*   `list-of-QVariant arguments (self)`
*   `bool autoStartService (self)`
*   `QDBusMessage createErrorReply (self, QString name, QString msg)`
*   `QDBusMessage createErrorReply (self, QDBusError error)`
*   `QDBusMessage createErrorReply (self, QDBusError.ErrorType type, QString msg)`
*   `QDBusMessage createReply (self, list-of-QVariant arguments = QList&lt;QVariant&gt;())`
*   `QDBusMessage createReply (self, QVariant argument)`
*   `QString errorMessage (self)`
*   `QString errorName (self)`
*   `QString interface (self)`
*   `bool isDelayedReply (self)`
*   `bool isReplyRequired (self)`
*   `QString member (self)`
*   `QString path (self)`
*   `QString service (self)`
*   `setArguments (self, list-of-QVariant arguments)`
*   `setAutoStartService (self, bool enable)`
*   `setDelayedReply (self, bool enable)`
*   `QString signature (self)`
*   `MessageType type (self)`

### Static Methods

*   `QDBusMessage createError (QString name, QString msg)`
*   `QDBusMessage createError (QDBusError error)`
*   `QDBusMessage createError (QDBusError.ErrorType type, QString msg)`
*   `QDBusMessage createMethodCall (QString service, QString path, QString interface, QString method)`
*   `QDBusMessage createSignal (QString path, QString interface, QString name)`

### Special Methods

*   `QDBusMessage __lshift__ (self, QVariant arg)`

* * *

## Detailed Description

该QDBusMessage类表示发送或接收通过D - Bus总线一个消息。

这个对象可以表示任何四个不同类型的消息的（[MessageType](qdbusmessage.html#MessageType-enum)） ，可以发生在总线上：

*   Method calls
*   Method return values
*   Signal emissions
*   Error codes

这种类型的对象与静态创建[createError](qdbusmessage.html#createError)（ ）[createMethodCall](qdbusmessage.html#createMethodCall)（）和[createSignal](qdbusmessage.html#createSignal)（）函数。使用[QDBusConnection.send](qdbusconnection.html#send)（ ）函数来发送消息。

* * *

## Type Documentation

```
QDBusMessage.MessageType
```

可能的消息类型：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusMessage.MethodCallMessage` | `1` | 较传出或传入方法调用的消息 |
| `QDBusMessage.SignalMessage` | `4` | 较传出或传入信号发射的消息 |
| `QDBusMessage.ReplyMessage` | `2` | 表示方法调用的返回值的消息 |
| `QDBusMessage.ErrorMessage` | `3` | 表示响应于一个方法调用的错误状态的信息 |
| `QDBusMessage.InvalidMessage` | `0` | 无效的消息：这是从来没有从D-Bus的收到的邮件设置 |

* * *

## Method Documentation

```
QDBusMessage.__init__ (self)
```

构造一个空的，无效的[QDBusMessage](qdbusmessage.html)对象。

**See also** [createError](qdbusmessage.html#createError)（ ）[createMethodCall](qdbusmessage.html#createMethodCall)（）和[createSignal](qdbusmessage.html#createSignal)（ ） 。

```
QDBusMessage.__init__ (self, QDBusMessage other)
```

通过构造特定对象的一个副本_other_。

注意：[QDBusMessage](qdbusmessage.html)对象是共享的。对副本所做的修改会影响到原来的为好。看[setDelayedReply](qdbusmessage.html#setDelayedReply)（ ）获取更多信息。

```
list-of-QVariant QDBusMessage.arguments (self)
```

返回与将要发送或从D-总线收到的参数列表。

**See also** [setArguments](qdbusmessage.html#setArguments)（ ） 。

```
bool QDBusMessage.autoStartService (self)
```

返回自动开始标志，以载[setAutoStartService](qdbusmessage.html#setAutoStartService)（ ） 。默认情况下，此标志为True ，这意味着[QtDBus](index.htm)会自动启动服务，如果它尚未运行。

此功能被引入Qt的4.7 。

**See also** [setAutoStartService](qdbusmessage.html#setAutoStartService)（ ） 。

```
QDBusMessage QDBusMessage.createError (QString name, QString msg)
```

[

构造一个新的乌思消息表示错误，用给定的_name_和_msg_。

](qdbusmessage.html)

```
QDBusMessage QDBusMessage.createError (QDBusError error)
```

[

构造一个新的乌思消息表示给定_error_。

](qdbusmessage.html)

```
QDBusMessage QDBusMessage.createError (QDBusError.ErrorType type, QString msg)
```

[

构造一个新的乌思消息错误类型_type_使用消息_msg_。返回乌思消息。

](qdbusmessage.html)

```
QDBusMessage QDBusMessage.createErrorReply (self, QString name, QString msg)
```

[

构造一个新的乌思消息表示错误应答消息，与给定_name_和_msg_。

](qdbusmessage.html)

```
QDBusMessage QDBusMessage.createErrorReply (self, QDBusError error)
```

[

构造一个新的乌思消息表示错误应答消息，从给定的_error_对象。

](qdbusmessage.html)

```
QDBusMessage QDBusMessage.createErrorReply (self, QDBusError.ErrorType type, QString msg)
```

[

构建了错误类型的新乌思回复消息_type_使用消息_msg_。返回乌思消息。

](qdbusmessage.html)

```
QDBusMessage QDBusMessage.createMethodCall (QString service, QString path, QString interface, QString method)
```

[

构造一个新的乌思消息表示一个方法调用。一个方法调用总是会通知其目的地地址（_service_，_path_，_interface_和_method_） 。

该乌思总线允许调用一个给定的远程对象上的方法，而无需指定目的接口，如果方法名是唯一的。然而，如果对远程对象的两个接口导出相同的方法名称，则结果是不确定的（两个中的一个可被称为或错误可以被返回）。

当一个对等情况下（即未在公共汽车上）使用乌思时，_service_参数是可选的。

](qdbusmessage.html)

[该QDBusObject和](qdbusmessage.html)[QDBusInterface](qdbusinterface.html)类提供了一个更简单的抽象同步方法调用。

这个函数返回一个[QDBusMessage](qdbusmessage.html)可以与发送对象[QDBusConnection.call](qdbusconnection.html#call)（ ） 。

```
QDBusMessage QDBusMessage.createReply (self, list-of-QVariant arguments = QList<QVariant>())
```

[

构造一个新的消息乌思代表的答复，与给定_arguments_。

](qdbusmessage.html)

```
QDBusMessage QDBusMessage.createReply (self, QVariant argument)
```

[

构造一个新的消息乌思代表的答复，与给定_argument_。

](qdbusmessage.html)

```
QDBusMessage QDBusMessage.createSignal (QString path, QString interface, QString name)
```

[

构造一个新的消息乌思用给定的_path_，_interface_和_name_，表示信号发射。

一个乌思信号从一个应用程序发出和接收到正在侦听从该接口信号的所有应用程序。

](qdbusmessage.html)

[该](qdbusmessage.html)[QDBusMessage](qdbusmessage.html)返回的对象可以使用被发送的[QDBusConnection.send](qdbusconnection.html#send)（）函数。

```
QString QDBusMessage.errorMessage (self)
```

返回与接收到的错误相关联的人类可读的消息。

此功能被引入Qt的4.3 。

```
QString QDBusMessage.errorName (self)
```

返回接收到的错误的名称。

```
QString QDBusMessage.interface (self)
```

返回被调用（在一个方法调用的情况下）的方法，或从接收到的信号的接口。

```
bool QDBusMessage.isDelayedReply (self)
```

返回延迟应答标志位，如设置[setDelayedReply](qdbusmessage.html#setDelayedReply)（ ） 。默认情况下，此标志为False ，这意味着[QtDBus](index.htm)有需要时会产生自动回复。

```
bool QDBusMessage.isReplyRequired (self)
```

返回标志，指示该消息应该会看到一个回复或没有。这是唯一有意义的[method call messages](qdbusmessage.html#MessageType-enum)：其他任何类型的消息不能有答复，该函数将始终返回False他们。

```
QString QDBusMessage.member (self)
```

返回所发射的信号的名称，或者被调用的方法的名称。

```
QString QDBusMessage.path (self)
```

```
QString QDBusMessage.service (self)
```

返回该服务的名称或远程方法调用的总线地址。

```
QDBusMessage.setArguments (self, list-of-QVariant arguments)
```

设置将要发送的D-Bus的参数_arguments_。这些将是参数的方法调用或信号中的参数。

**See also** [arguments](qdbusmessage.html#arguments)（ ） 。

```
QDBusMessage.setAutoStartService (self, bool enable)
```

设定自动开始标志，以_enable_。此标志仅是有道理的，方法调用的消息，它讲述了D-Bus的服务器要么自动开始负责服务名称，或不自动启动该服务。

默认情况下，此标志为True ，即服务是自动启动。这意味着：

当这个方法调用被发送到服务已在运行，方法调用被发送给它。如果服务没有运行的是，在D-Bus的守护程序要求自动启动分配给该服务名称服务。这是通过被放置在已知为D- Bus服务器的目录中。服务文件处理。这些文件然后每个都包含一个服务名称和路径时，该服务名称要求应执行的程序。

此功能被引入Qt的4.7 。

**See also** [autoStartService](qdbusmessage.html#autoStartService)（ ） 。

```
QDBusMessage.setDelayedReply (self, bool enable)
```

设置消息是否会被回答后（如果_enable_是真实的），或者是否应该通过产生一个自动回复[QtDBus](index.htm)（如果_enable_是假的） 。

在D-Bus的，所有方法调用必须产生给调用者的答复，除非调用者明确表示，否则（见[isReplyRequired](qdbusmessage.html#isReplyRequired)（））。[QtDBus](index.htm)自动生成这样的答复为被调用的任何插槽，但它也允许插槽，以表明他们是否会采取发送应答在以后的责任，之后该功能已完成处理。

**See also** [isDelayedReply](qdbusmessage.html#isDelayedReply)（）和[Delayed Replies](index.htm#delayed-replies)。

```
QString QDBusMessage.signature (self)
```

返回收到或方法调用的输出参数的信号的签名。

```
MessageType QDBusMessage.type (self)
```

[

返回的消息类型。

](qdbusmessage.html#MessageType-enum)

```
QDBusMessage QDBusMessage.__lshift__ (self, QVariant arg)
```

[](qdbusmessage.html)