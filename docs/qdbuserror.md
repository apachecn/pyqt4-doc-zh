# QDBusError Class Reference

## [[QtDBus](index.htm) module]

该QDBusError类代表从D - Bus总线或从总线发现远程应用程序收到一个错误。[More...](#details)

### Types

*   `enum ErrorType { NoError, Other, Failed, NoMemory, ..., InvalidMember }`

### Methods

*   `__init__ (self, QDBusError other)`
*   `bool isValid (self)`
*   `QString message (self)`
*   `QString name (self)`
*   `ErrorType type (self)`

### Static Methods

*   `QString errorString (ErrorType error)`

* * *

## Detailed Description

该QDBusError类代表从D - Bus总线或从总线发现远程应用程序收到一个错误。

当使用D - Bus总线服务或远程应用程序通过D-Bus处理，一些错误情况可能会发生。这个错误条件是通过返回错误值或由QDBusError有时信号。

C + +和Java的例外是D-Bus的错误，一个有效的比喻：不是有一个返回值，远程应用程序和总线正常返回可能决定抛出一个错误条件。然而，本[QtDBus](index.htm)实现不使用C + +异常抛出机制，所以你会收到QDBusErrors在返回的答复（见[QDBusReply.error](qdbusreply.html#error)（））。

QDBusError对象用于检查错误名称和距离公共汽车站和远程应用程序收到的消息。你不应该自己创建这些对象的信号错误条件从D-Bus的调用时：相反，使用[QDBusMessage.createError](qdbusmessage.html#createError)（）和[QDBusConnection.send](qdbusconnection.html#send)（ ） 。

* * *

## Type Documentation

```
QDBusError.ErrorType
```

为了便于核查的D-Bus的执行和总线守护程序本身产生的最常见的D-Bus错误，[QDBusError](qdbuserror.html)可以比作一组预先定义的值：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusError.NoError` | `0` | [QDBusError](qdbuserror.html)是无效的（即，调用成功） |
| `QDBusError.Other` | `1` | [QDBusError](qdbuserror.html)包含错误，它是众所周知的之一 |
| `QDBusError.Failed` | `2` | 调用失败（`org.freedesktop.DBus.Error.Failed`） |
| `QDBusError.NoMemory` | `3` | 出存储器（`org.freedesktop.DBus.Error.NoMemory`） |
| `QDBusError.ServiceUnknown` | `4` | 被调用的服务是未知的（`org.freedesktop.DBus.Error.ServiceUnknown`） |
| `QDBusError.NoReply` | `5` | 被调用的方法没有在指定的超时时间内答复（`org.freedesktop.DBus.Error.NoReply`） |
| `QDBusError.BadAddress` | `6` | 给出的地址是无效的（`org.freedesktop.DBus.Error.BadAddress`） |
| `QDBusError.NotSupported` | `7` | 不支持通话/操作（`org.freedesktop.DBus.Error.NotSupported`） |
| `QDBusError.LimitsExceeded` | `8` | 分配给此进程/呼叫/连接的限制超出了预先定义的值（`org.freedesktop.DBus.Error.LimitsExceeded`） |
| `QDBusError.AccessDenied` | `9` | 呼叫/操作试图访问一个资源它不允许（`org.freedesktop.DBus.Error.AccessDenied`） |
| `QDBusError.NoServer` | `10` | _Documentation doesn't say what this is for_（`org.freedesktop.DBus.Error.NoServer`） |
| `QDBusError.Timeout` | `11` | _Documentation doesn't say what this is for or how it's used_（`org.freedesktop.DBus.Error.Timeout`） |
| `QDBusError.NoNetwork` | `12` | _Documentation doesn't say what this is for_（`org.freedesktop.DBus.Error.NoNetwork`） |
| `QDBusError.AddressInUse` | `13` | QDBusServer试图绑定到一个地址已被使用（`org.freedesktop.DBus.Error.AddressInUse`） |
| `QDBusError.Disconnected` | `14` | 呼叫/进程/消息被发送后，[QDBusConnection](qdbusconnection.html)断开（`org.freedesktop.DBus.Error.Disconnected`） |
| `QDBusError.InvalidArgs` | `15` | 传递给这个调用/操作的参数是无效的（`org.freedesktop.DBus.Error.InvalidArgs`） |
| `QDBusError.UnknownMethod` | `16` | 在这个对象/接口与给定的参数（未找到调用的方法`org.freedesktop.DBus.Error.UnknownMethod`） |
| `QDBusError.TimedOut` | `17` | _Documentation doesn't say..._（`org.freedesktop.DBus.Error.TimedOut`） |
| `QDBusError.InvalidSignature` | `18` | 类型签名是无效的或兼容（`org.freedesktop.DBus.Error.InvalidSignature`） |
| `QDBusError.UnknownInterface` | `19` | 该接口是不为人所知的 |
| `QDBusError.InternalError` | `20` | 发生内部错误（`com.trolltech.QtDBus.Error.InternalError`） |
| `QDBusError.InvalidObjectPath` | `23` | 提供的对象路径无效。 |
| `QDBusError.InvalidService` | `22` | 所请求的服务无效。 |
| `QDBusError.InvalidMember` | `25` | 该部件是无效的。 |
| `QDBusError.InvalidInterface` | `24` | 该接口是无效的。 |
| `QDBusError.UnknownObject` | `21` | 远程对象找不到。 |

* * *

## Method Documentation

```
QDBusError.__init__ (self, QDBusError other)
```

```
QString QDBusError.errorString (ErrorType error)
```

返回与错误情况相关联的错误名称_error_。

此功能被引入Qt的4.3 。

```
bool QDBusError.isValid (self)
```

返回True如果这是一个有效的错误条件（例如，如果有一个错误） ，否则为False 。

```
QString QDBusError.message (self)
```

返回被叫与此错误相关的消息。错误信息是实现定义的，通常包含人类可读的错误代码，虽然这并不意味着它是适合您的最终用户。

```
QString QDBusError.name (self)
```

返回这个错误的名字。错误名称类似的D-Bus接口的名称，如`org.freedesktop.DBus.InvalidArgs`。

**See also** [type](qdbuserror.html#type)（ ） 。

```
ErrorType QDBusError.type (self)
```

[](qdbuserror.html#ErrorType-enum)

[返回此错误的](qdbuserror.html#ErrorType-enum)[ErrorType](qdbuserror.html#ErrorType-enum)。

**See also** [ErrorType](qdbuserror.html#ErrorType-enum)。