# QNetworkInterface Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkInterface类提供​​主机的IP地址和网络接口的列表。[More...](#details)

### Types

*   `enum InterfaceFlag { IsUp, IsRunning, CanBroadcast, IsLoopBack, IsPointToPoint, CanMulticast }`
*   `class **[InterfaceFlags](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QNetworkInterface other)`
*   `list-of-QNetworkAddressEntry addressEntries (self)`
*   `InterfaceFlags flags (self)`
*   `QString hardwareAddress (self)`
*   `QString humanReadableName (self)`
*   `int index (self)`
*   `bool isValid (self)`
*   `QString name (self)`

### Static Methods

*   `list-of-QHostAddress allAddresses ()`
*   `list-of-QNetworkInterface allInterfaces ()`
*   `QNetworkInterface interfaceFromIndex (int index)`
*   `QNetworkInterface interfaceFromName (QString name)`

* * *

## Detailed Description

该QNetworkInterface类提供​​主机的IP地址和网络接口的列表。

QNetworkInterface表示连接到该程序正在运行主机一个网络接口。每个网络接口可以包含零个或多个IP地址，其中每一个与一个掩码和/或广播地址是任选关联。可以得到这样的三重奏列表[addressEntries](qnetworkinterface.html#addressEntries)（ ） 。或者，当网络掩码或广播地址是没有必要的，使用[allAddresses](qnetworkinterface.html#allAddresses)（ ）方便的功能，仅仅获得了IP地址。

QNetworkInterface还报告与接口的硬件地址[hardwareAddress](qnetworkinterface.html#hardwareAddress)（ ） 。

并非所有操作系统都支持报告的所有功能。只有IPv4地址，保证在所有平台上被列入这个类别。特别是， IPv6地址的清单只支持Windows XP和更新的版本， Linux的， MacOS X和BSD系统。

* * *

## Type Documentation

```
QNetworkInterface.InterfaceFlag
```

指定与此网络接口关联的标志。可能的值有：

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkInterface.IsUp` | `0x1` | 网络接口是活动的 |
| `QNetworkInterface.IsRunning` | `0x2` | 网络接口具有分配资源 |
| `QNetworkInterface.CanBroadcast` | `0x4` | 网络接口工作在广播模式 |
| `QNetworkInterface.IsLoopBack` | `0x8` | 网络接口是Loopback接口：也就是说，它是一个虚拟接口，其目的是主机本身 |
| `QNetworkInterface.IsPointToPoint` | `0x10` | 网络接口是一个点至点接口：就是有一个，可以通过它直接到达单其他地址。 |
| `QNetworkInterface.CanMulticast` | `0x20` | 网络接口支持多播 |

请注意，一个网络接口不能同时基于广播和点至点。

该InterfaceFlags类型是一个typedef为[QFlags](index.htm)\u003cInterfaceFlag\u003e 。它存储InterfaceFlag值的或组合。

* * *

## Method Documentation

```
QNetworkInterface.__init__ (self)
```

构造一个空的网络接口对象。

```
QNetworkInterface.__init__ (self, QNetworkInterface other)
```

创建的副本[QNetworkInterface](qnetworkinterface.html)包含的对象_other_。

```
list-of-QNetworkAddressEntry QNetworkInterface.addressEntries (self)
```

返回的IP地址列表，该接口具有与它们相关的子网掩码和广播地址。

如果网络掩码或广播地址的信息是没有必要的，你可以调用[allAddresses](qnetworkinterface.html#allAddresses)（ ）函数来获得公正的IP地址。

```
list-of-QHostAddress QNetworkInterface.allAddresses ()
```

这种便利函数返回的主机上找到的所有IP地址。这等同于调用[addressEntries](qnetworkinterface.html#addressEntries)（ ）对所有返回的对象[allInterfaces](qnetworkinterface.html#allInterfaces)（）获得的列表[QHostAddress](qhostaddress.html)对象然后调用QHostAddress.ip （ ）在每个这些。

```
list-of-QNetworkInterface QNetworkInterface.allInterfaces ()
```

将返回所有在主机上找到的网络接口的列表。

```
InterfaceFlags QNetworkInterface.flags (self)
```

[

返回与此网络接口关联的标志。

```
QString QNetworkInterface.hardwareAddress (self)
```

返回低级别的硬件地址为这个接口。在以太网接口，这将是一个MAC地址的字符串表示形式，由冒号分隔。

其他接口类型可以有其他类型的硬件地址。实现不应该依赖于这个函数返回一个有效的MAC地址。

```
QString QNetworkInterface.humanReadableName (self)
```

](index.htm)

[返回在Windows上，如“本地连接” ，如果该名称可确定此网络接口的可读名称。如果不能，则该函数返回相同](index.htm)[name](qnetworkinterface.html#name)（ ） 。人类可读的名称是一个名称，用户可以在Windows控制面板中修改，所以它可以在程序执行期间改变。

在Unix中，这个功能目前总是返回相同[name](qnetworkinterface.html#name)（ ） ，因为Unix系统都配置不存储为人类可读的名称。

此功能被引入Qt的4.5 。

```
int QNetworkInterface.index (self)
```

返回接口系统索引，如果知道的话。这是分配由操作系统来识别这个接口，它通常不发生变化的整数。它在IPv6地址匹配的范围ID字段。

如果索引不知道，这个函数返回0 。

此功能被引入Qt的4.5 。

```
QNetworkInterface QNetworkInterface.interfaceFromIndex (int index)
```

[](qnetworkinterface.html)

[返回](qnetworkinterface.html)[QNetworkInterface](qnetworkinterface.html)为对象的内部ID是接口_index_。网络接口具有所谓的“接口索引”，以从其他接口区分开来在系统上的唯一标识符。通常，这个值是逐步分配和被移除的接口，然后再加入每一次得到不同的值。

该指数还发现，在IPv6地址“范围ID字段。

```
QNetworkInterface QNetworkInterface.interfaceFromName (QString name)
```

[](qnetworkinterface.html)

[返回](qnetworkinterface.html)[QNetworkInterface](qnetworkinterface.html)对象命名接口_name_。如果没有这样的接口存在，该函数返回一个无效的[QNetworkInterface](qnetworkinterface.html)对象。

**See also** [name](qnetworkinterface.html#name)（）和[isValid](qnetworkinterface.html#isValid)（ ） 。

```
bool QNetworkInterface.isValid (self)
```

返回True如果[QNetworkInterface](qnetworkinterface.html)对象包含一个网络接口的有效信息。

```
QString QNetworkInterface.name (self)
```

返回此网络接口的名称。在Unix系统中，这是一个包含接口的类型和任选的序列号，如“ eth0的”，“ LO ”或“ pcn0 ”的字符串。在Windows上，它是不能被用户改变的内部ID 。