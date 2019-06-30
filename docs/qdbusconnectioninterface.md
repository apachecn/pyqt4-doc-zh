# QDBusConnectionInterface Class Reference

## [[QtDBus](index.htm) module]

该QDBusConnectionInterface类提供​​访问D - Bus总线守护进程服务。[More...](#details)

继承[QDBusAbstractInterface](qdbusabstractinterface.html)。

### Types

*   `enum RegisterServiceReply { ServiceNotRegistered, ServiceRegistered, ServiceQueued }`
*   `enum ServiceQueueOptions { DontQueueService, QueueService, ReplaceExistingService }`
*   `enum ServiceReplacementOptions { DontAllowReplacement, AllowReplacement }`

### Methods

*   `connectNotify (self, SIGNAL())`
*   `disconnectNotify (self, SIGNAL())`
*   `QDBusReply isServiceRegistered (self, QString serviceName)`
*   `QDBusReply registeredServiceNames (self)`
*   `QDBusReply registerService (self, QString serviceName, ServiceQueueOptions qoption = QDBusConnectionInterface.DontQueueService, ServiceReplacementOptions roption = QDBusConnectionInterface.DontAllowReplacement)`
*   `QDBusReply serviceOwner (self, QString name)`
*   `QDBusReply servicePid (self, QString serviceName)`
*   `QDBusReply serviceUid (self, QString serviceName)`
*   `QDBusReply startService (self, QString name)`
*   `QDBusReply unregisterService (self, QString serviceName)`

### Qt Signals

*   `void callWithCallbackFailed (const QDBusError&,const QDBusMessage&)`
*   `void serviceOwnerChanged (const QString&,const QString&,const QString&)`
*   `void serviceRegistered (const QString&)`
*   `void serviceUnregistered (const QString&)`

* * *

## Detailed Description

该QDBusConnectionInterface类提供​​访问D - Bus总线守护进程服务。

在D - Bus总线服务器守护进程提供1个专用接口`org.freedesktop.DBus`允许客户端访问总线的某些属性，如连接的客户端的列表。该QDBusConnectionInterface类提供了访问该界面。

这个类最常见的用途是用在总线上注册和注销服务名称[registerService](qdbusconnectioninterface.html#registerService)（）和[unregisterService](qdbusconnectioninterface.html#unregisterService)采用（ ）函数，查询有关现有名称[isServiceRegistered](qdbusconnectioninterface.html#isServiceRegistered)（ ）[registeredServiceNames](qdbusconnectioninterface.html#registeredServiceNames-prop)（）和[serviceOwner](qdbusconnectioninterface.html#serviceOwner)（ ）函数，并接收客户端已通过注册或取消注册的通知[serviceRegistered](qdbusconnectioninterface.html#serviceRegistered)（ ）[serviceUnregistered](qdbusconnectioninterface.html#serviceUnregistered)（）和[serviceOwnerChanged](qdbusconnectioninterface.html#serviceOwnerChanged)（ ）信号。

* * *

## Type Documentation

```
QDBusConnectionInterface.RegisterServiceReply
```

从可能的返回值[registerService](qdbusconnectioninterface.html#registerService)（）：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusConnectionInterface.ServiceNotRegistered` | `0` | 该呼叫失败和服务名称未注册。 |
| `QDBusConnectionInterface.ServiceRegistered` | `1` | 呼叫者现在是服务名称的拥有者。 |
| `QDBusConnectionInterface.ServiceQueued` | `2` | 调用者指定的[QueueService](qdbusconnectioninterface.html#ServiceQueueOptions-enum)标志和服务已经注册，所以我们在队列中。 |

该[serviceRegistered](qdbusconnectioninterface.html#serviceRegistered)当由该应用程序获得的服务（）信号将被发射。

```
QDBusConnectionInterface.ServiceQueueOptions
```

标志确定一个服务注册应该如何表现，如果服务名已被注册。

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusConnectionInterface.DontQueueService` | `0` | 如果一个应用程序请求一个已经拥有一个名字，没有排队会被执行。该registeredService （ ）调用只会失败。这是默认的。 |
| `QDBusConnectionInterface.QueueService` | `1` | 尝试注册​​请求的服务，但不要试图取代它，如果另一个应用程序已经有它注册。相反，只要把这个应用程序在队列中，直到它被放弃。该[serviceRegistered](qdbusconnectioninterface.html#serviceRegistered)当发生这种情况（在）信号将被发射。 |
| `QDBusConnectionInterface.ReplaceExistingService` | `2` | 如果另一个应用程序已经有注册的服务名，试图取代它。 |

**See also** [ServiceReplacementOptions](qdbusconnectioninterface.html#ServiceReplacementOptions-enum)。

```
QDBusConnectionInterface.ServiceReplacementOptions
```

标志确定，如果D- Bus服务器应该允许其他应用程序来替换一个名字，这个应用程序已经注册了[ReplaceExistingService](qdbusconnectioninterface.html#ServiceQueueOptions-enum)选项。

可能的值有：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusConnectionInterface.DontAllowReplacement` | `0` | 不要让其他应用程序来取代我们。该服务必须明确取消注册[unregisterService](qdbusconnectioninterface.html#unregisterService)（ ）用于其他应用程序，以获取它。这是默认的。 |
| `QDBusConnectionInterface.AllowReplacement` | `1` | 允许其他应用程序给我们的替换[ReplaceExistingService](qdbusconnectioninterface.html#ServiceQueueOptions-enum)选项[registerService](qdbusconnectioninterface.html#registerService)（ ）不进行干预。如果发生这种情况，则[serviceUnregistered](qdbusconnectioninterface.html#serviceUnregistered)（）信号将被发射。 |

**See also** [ServiceQueueOptions](qdbusconnectioninterface.html#ServiceQueueOptions-enum)。

* * *

## Method Documentation

```
QDBusConnectionInterface.connectNotify (self, SIGNAL())
```

```
QDBusConnectionInterface.disconnectNotify (self, SIGNAL())
```

```
QDBusReply QDBusConnectionInterface.isServiceRegistered (self, QString serviceName)
```

返回True如果服务名称_serviceName_拥有目前登记。

```
QDBusReply QDBusConnectionInterface.registeredServiceNames (self)
```

```
QDBusReply QDBusConnectionInterface.registerService (self, QString serviceName, ServiceQueueOptions qoption = QDBusConnectionInterface.DontQueueService, ServiceReplacementOptions roption = QDBusConnectionInterface.DontAllowReplacement)
```

申请注册的服务名_serviceName_在总线上。该_qoption_标志指定的D-Bus的服务器应该怎么做，如果_serviceName_已经注册。该_roption_标志指定服务器应该允许其他应用程序来取代我们的注册名称。

如果服务注册成功，[serviceRegistered](qdbusconnectioninterface.html#serviceRegistered)（）信号将被发射。如果被放置在队列中，该信号将在我们获得的名称被发射。如果_roption_ is [AllowReplacement](qdbusconnectioninterface.html#ServiceReplacementOptions-enum)时，[serviceUnregistered](qdbusconnectioninterface.html#serviceUnregistered)（ ）信号会在另一个应用程序取代了这一个发射。

**See also** [unregisterService](qdbusconnectioninterface.html#unregisterService)（ ） 。

```
QDBusReply QDBusConnectionInterface.serviceOwner (self, QString name)
```

返回名称的主要所有者的唯一连接名称_name_。如果请求的名字没有一个老板，返回`org.freedesktop.DBus.Error.NameHasNoOwner`错误。

```
QDBusReply QDBusConnectionInterface.servicePid (self, QString serviceName)
```

返回的Unix进程ID（PID ）为目前持有的巴士服务的过程_serviceName_。

```
QDBusReply QDBusConnectionInterface.serviceUid (self, QString serviceName)
```

返回的Unix用户ID（ UID）为目前持有的巴士服务的过程_serviceName_。

```
QDBusReply QDBusConnectionInterface.startService (self, QString name)
```

要求该总线开始由给定名称的服务_name_。

```
QDBusReply QDBusConnectionInterface.unregisterService (self, QString serviceName)
```

发布于巴士服务名索赔_serviceName_，这已与以前登记[registerService](qdbusconnectioninterface.html#registerService)（ ） 。如果这个应用程序有名称的所有权，它会被释放用于其他应用要求。如果只有名字排队，它放弃其在队列中的位置。

* * *

## Qt Signal Documentation

```
void callWithCallbackFailed (const QDBusError&,const QDBusMessage&)
```

这是该信号的默认超载。

当存在时是一个错误，这个信号被发射的[QDBusConnection.callWithCallback](qdbusconnection.html#callWithCallback)（ ） 。_error_指定错误。_call_是无法传递的消息。

**See also** [QDBusConnection.callWithCallback](qdbusconnection.html#callWithCallback)（ ） 。

```
void serviceOwnerChanged (const QString&,const QString&,const QString&)
```

这是该信号的默认超载。

这个信号是由D - Bus服务器发出每当服务所有权的变化发生在公交车，其中包括幻影的名字和disparition 。

这个信号表示该应用程序_oldOwner_的总线名称丧失所有权_name_应用_newOwner_。如果_oldOwner_是一个空字符串，它表示的名称_name_刚刚被创建，如果_newOwner_是空的，名称_name_目前尚无所有者和不再可用。

**Note:**连接到该信号将使应用程序监听并接收总线上的每一个服务的所有权变更。取决于有多少服务正在运行，这使应用程序被激活，以获得更多的信号比它需要。要避免此问题，请使用[QDBusServiceWatcher](qdbusservicewatcher.html)类，它可以侦听特定的变化。

```
void serviceRegistered (const QString&)
```

这是该信号的默认超载。

这个信号是由D-Bus的服务器当巴士服务名称（唯一的连接名称或知名服务名称）由下式给出发射_serviceName_由该应用程序获得的。

收购之后会发生这个应用程序使用请求的名称[registerService](qdbusconnectioninterface.html#registerService)（ ） 。

```
void serviceUnregistered (const QString&)
```

这是该信号的默认超载。

这个信号是由D - Bus服务器时发出此应用程序失去由下式给出的巴士服务名称的所有权_serviceName_。