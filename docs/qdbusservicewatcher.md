# QDBusServiceWatcher Class Reference

## [[QtDBus](index.htm) module]

该QDBusServiceWatcher类允许用户观看的巴士服务的变化。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `class **[WatchMode](index.htm)**`
*   `enum WatchModeFlag { WatchForRegistration, WatchForUnregistration, WatchForOwnerChange }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QString service, QDBusConnection connection, WatchMode watchMode = QDBusServiceWatcher.WatchForOwnerChange, QObject parent = None)`
*   `addWatchedService (self, QString newService)`
*   `QDBusConnection connection (self)`
*   `bool removeWatchedService (self, QString service)`
*   `setConnection (self, QDBusConnection connection)`
*   `setWatchedServices (self, QStringList services)`
*   `setWatchMode (self, WatchMode mode)`
*   `QStringList watchedServices (self)`
*   `WatchMode watchMode (self)`

### Qt Signals

*   `void serviceOwnerChanged (const QString&,const QString&,const QString&)`
*   `void serviceRegistered (const QString&)`
*   `void serviceUnregistered (const QString&)`

* * *

## Detailed Description

该QDBusServiceWatcher类允许用户观看的巴士服务的变化。

一个QDBusServiceWatcher对象可以用来通知用户有关服务名的总线上的所有权变更申请。它有三个手表模式：

*   Watching for service registration only.
*   Watching for service unregistration only.
*   Watching for any kind of service ownership change (the default mode).

除了被创建或删除，服务可能会改变所有人没有注销/寄存器操作发生的事情。所以，[serviceRegistered](qdbusservicewatcher.html#serviceRegistered)（）和[serviceUnregistered](qdbusservicewatcher.html#serviceUnregistered)如果发生这种情况（）信号可能不被发射。

这个类是比使用更高效的[QDBusConnectionInterface.serviceOwnerChanged](qdbusconnectioninterface.html#serviceOwnerChanged)（ ）信号，因为它允许一个只接收为其类是感兴趣的信号

* * *

## Type Documentation

```
QDBusServiceWatcher.WatchModeFlag
```

[QDBusServiceWatcher](qdbusservicewatcher.html)支持三种不同的观看模式，这是由该标志配置：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusServiceWatcher.WatchForRegistration` | `0x01` | 手表仅售服务注册，而忽略与其他服务的所有权变更的任何信号。 |
| `QDBusServiceWatcher.WatchForUnregistration` | `0x02` | 手表仅售服务注销，而忽略相关的其他服务所有权变更的任何信号。 |
| `QDBusServiceWatcher.WatchForOwnerChange` | `0x03` | 观看任何类型的服务所有权的变化。 |

该WatchMode类型是一个typedef为[QFlags](index.htm)\u003cWatchModeFlag\u003e 。它存储WatchModeFlag值的或组合。

* * *

## Method Documentation

```
QDBusServiceWatcher.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QDBusServiceWatcher](qdbusservicewatcher.html)对象。需要注意的是，直到你设置一个连接[setConnection](qdbusservicewatcher.html#setConnection)（ ） ，这个对象将不会发出任何信号。

该_parent_参数被传递到[QObject](qobject.html)设置该对象的父。

```
QDBusServiceWatcher.__init__ (self, QString service, QDBusConnection connection, WatchMode watchMode = QDBusServiceWatcher.WatchForOwnerChange, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QDBusServiceWatcher](qdbusservicewatcher.html)对象，并将其附加到_connection_连接。另外，此功能将立即启动窥伺_watchMode_更改服务_service_。

该_parent_参数被传递到[QObject](qobject.html)设置该对象的父。

```
QDBusServiceWatcher.addWatchedService (self, QString newService)
```

添加_newService_到服务，通过该对象被监视的列表。这个函数是比更有效[setWatchedServices](qdbusservicewatcher.html#watchedServices-prop)（ ），并应尽可能使用添加服务。

```
QDBusConnection QDBusServiceWatcher.connection (self)
```

[](qdbusconnection.html)

[返回](qdbusconnection.html)[QDBusConnection](qdbusconnection.html)这个对象附加到。

**See also** [setConnection](qdbusservicewatcher.html#setConnection)（ ） 。

```
bool QDBusServiceWatcher.removeWatchedService (self, QString service)
```

移除_service_从正在观看由该对象的服务的列表。需要注意的是D-Bus的通知是异步的，所以有可能还是待交付有关信号_service_。每当D-Bus的消息处理这些信号仍然会排放。

如果被拆除的任何服务该函数返回True。

```
QDBusServiceWatcher.setConnection (self, QDBusConnection connection)
```

设置D-Bus的连接，这个对象附加到会_connection_。看着所有服务将被转移到这方面。

需要注意的是[QDBusConnection](qdbusconnection.html)对象引用计数：[QDBusServiceWatcher](qdbusservicewatcher.html)将保持一个参考此连接，而它的存在。连接不关闭，直到引用计数下降到零，所以这将确保任何通知而收到这[QDBusServiceWatcher](qdbusservicewatcher.html)对象存在。

**See also** [connection](qdbusservicewatcher.html#connection)（ ） 。

```
QDBusServiceWatcher.setWatchedServices (self, QStringList services)
```

```
QDBusServiceWatcher.setWatchMode (self, WatchMode mode)
```

```
QStringList QDBusServiceWatcher.watchedServices (self)
```

```
WatchMode QDBusServiceWatcher.watchMode (self)
```

[

* * *

## Qt Signal Documentation

```
void serviceOwnerChanged (const QString&,const QString&,const QString&)
```

这是该信号的默认超载。

每当这个对象检测到有关于该服务的所有权改变这个信号被发射_serviceName_服务。该_oldOwner_参数包含旧的所有者名称和_newOwner_是新的主人。两_oldOwner_和_newOwner_是唯一的连接名。

注意，此信号也被发射时的_serviceName_服务注册或未注册。如果它被注册，_oldOwner_将包含一个空字符串，而如果是未注册的，_newOwner_将包含一个空字符串。

如果你只需要找出如果该服务被注册或只登记，不被通知的所有权变更，请考虑使用这些操作的具体模式。如果您使用更具体的模式这个类是更有效的。

](index.htm)

[**See also**](index.htm) [serviceRegistered](qdbusservicewatcher.html#serviceRegistered)（）和[serviceUnregistered](qdbusservicewatcher.html#serviceUnregistered)（ ） 。

```
void serviceRegistered (const QString&)
```

这是该信号的默认超载。

每当这个对象检测这个信号被发射，该服务_serviceName_在公共汽车上变得可用。

**See also** [serviceUnregistered](qdbusservicewatcher.html#serviceUnregistered)（）和[serviceOwnerChanged](qdbusservicewatcher.html#serviceOwnerChanged)（ ） 。

```
void serviceUnregistered (const QString&)
```

这是该信号的默认超载。

每当这个对象检测这个信号被发射，该服务_serviceName_从总线被取消注册，并不再可用。

**See also** [serviceRegistered](qdbusservicewatcher.html#serviceRegistered)（）和[serviceOwnerChanged](qdbusservicewatcher.html#serviceOwnerChanged)（ ） 。