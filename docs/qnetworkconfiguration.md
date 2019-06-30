# QNetworkConfiguration Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkConfiguration类提供的一个或多个接入点的配置的抽象。[More...](#details)

### Types

*   `enum BearerType { BearerUnknown, BearerEthernet, BearerWLAN, Bearer2G, ..., BearerWiMAX }`
*   `enum Purpose { UnknownPurpose, PublicPurpose, PrivatePurpose, ServiceSpecificPurpose }`
*   `enum StateFlag { Undefined, Defined, Discovered, Active }`
*   `class **[StateFlags](index.htm)**`
*   `enum Type { InternetAccessPoint, ServiceNetwork, UserChoice, Invalid }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QNetworkConfiguration other)`
*   `QString bearerName (self)`
*   `BearerType bearerType (self)`
*   `QString bearerTypeName (self)`
*   `list-of-QNetworkConfiguration children (self)`
*   `QString identifier (self)`
*   `bool isRoamingAvailable (self)`
*   `bool isValid (self)`
*   `QString name (self)`
*   `Purpose purpose (self)`
*   `StateFlags state (self)`
*   `Type type (self)`

### Special Methods

*   `bool __eq__ (self, QNetworkConfiguration cp)`
*   `bool __ne__ (self, QNetworkConfiguration cp)`

* * *

## Detailed Description

该QNetworkConfiguration类提供的一个或多个接入点的配置的抽象。

QNetworkConfiguration封装单个接入点或服务网络。在大多数情况下，一个单一的接入点的配置可以被映射到一个网络接口。然而，一个单一的网络接口可能并不总是映射到唯一的一个接入点的配置。对于同一网络中设备的多种配置可使得多个接入点。一例装置，可以表现出这样的结构可能是一个智能手机，它允许用户管理多个WLAN配置，而设备本身仅具有一个WLAN网络设备。

该QNetworkConfiguration还支持服务网络的概念。这个概念允许多个接入点的配置的组合成一个实体。这样的一组被称为服务网络，可以在案件是有益由此网络会话到特定目的地网络是必需的（如公司网络） 。当使用一服务网络的用户通常不关心其中的连接选项1被选择（例如，企业WLAN或VPN通过GPRS ） ，只要他能够达到公司的目标服务器。根据当前位置和时间的一些接入点组成的服务网络甚至可能不是可用的。此外自动接入点漫游可以启用，使该器件能够动态更改网络接口的配置，同时保持应用程序连接到目标网络。它允许适应不断变化的环境，并可以使优化与问候成本，速度或其他网络参数。

类型的特殊配置[UserChoice](qnetworkconfiguration.html#Type-enum)提供一种由平台解析为实际的网络结构的佔位符的配置，当一个[session](qnetworksession.html) is [opened](qnetworksession.html#open)。不是所有平台都支持用户选择配置的概念。

### Configuration states

可以通过以下方式获得可用配置的清单[QNetworkConfigurationManager.allConfigurations](qnetworkconfigurationmanager.html#allConfigurations)（ ） 。配置中可以有多个状态。该[Defined](qnetworkconfiguration.html#StateFlag-enum)配置状态表示的结构被存储在设备上。但是，该构造还没有准备好被激活为如WLAN中可能无法使用在当前时间。

该[Discovered](qnetworkconfiguration.html#StateFlag-enum)状态隐含该配置是[Defined](qnetworkconfiguration.html#StateFlag-enum)与外界条件是这样的配置，可以立即使用，以打开一个新的网络会话。这样的条件以外，例如，可以是以太网电缆实际上是连接到设备，或与指定的SSID的无线网络是否在范围内。

该[Active](qnetworkconfiguration.html#StateFlag-enum)状态隐含该配置是[Discovered](qnetworkconfiguration.html#StateFlag-enum)。处于这种状态的配置是当前正在使用的应用程序。底层网络接口有一个有效的IP配置，并可以在设备和目标网络之间传输的IP数据包。

该[Undefined](qnetworkconfiguration.html#StateFlag-enum)状态表示系统有可能的目标网络的知识，但实际上并不能使用这些知识来连接到它。为这样的状态，例如，可以是已经发现，但用户还没有实际保存包括所需的密码这将允许设备连接到它的结构的加密的WLAN 。

根据配置的不同类型的一些州是一过性的。可以使用GPRS / UMTS连接可能几乎总是[Discovered](qnetworkconfiguration.html#StateFlag-enum)如果在GSM / UMTS网络是可用的。然而，如果将GSM / UMTS网络失去连接的相关联的配置有可能改变它的状态[Discovered](qnetworkconfiguration.html#StateFlag-enum)至[Defined](qnetworkconfiguration.html#StateFlag-enum)为好。类似的用例可能是由WLAN连接状态被触发。[QNetworkConfigurationManager.updateConfigurations](qnetworkconfigurationmanager.html#updateConfigurations)（）可用于手动触发状态的更新。请注意，某些平台并不需要这些更新，因为他们暗中更改一旦被发现的状态。如果配置的状态更改所有相关QNetworkConfiguration情况自动改变它们的状态。

* * *

## Type Documentation

```
QNetworkConfiguration.BearerType
```

指定用于由一个配置的承载类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkConfiguration.BearerUnknown` | `0` | 承载的类型未知或不确定的。该[bearerTypeName](qnetworkconfiguration.html#bearerTypeName)（ ）函数可以返回更多的信息。 |
| `QNetworkConfiguration.BearerEthernet` | `1` | 该配置是一个以太网接口。 |
| `QNetworkConfiguration.BearerWLAN` | `2` | 该设置是针对无线局域网的接口。 |
| `QNetworkConfiguration.Bearer2G` | `3` | 该设置是针对CSD ， GPRS， HSCSD ， EDGE或cdmaOne的接口。 |
| `QNetworkConfiguration.BearerCDMA2000` | `4` | 的配置是适用于CDMA接口。 |
| `QNetworkConfiguration.BearerWCDMA` | `5` | 配置为W-CDMA/UMTS接口。 |
| `QNetworkConfiguration.BearerHSPA` | `6` | 该配置是高速分组接入（HSPA ）接口。 |
| `QNetworkConfiguration.BearerBluetooth` | `7` | 配置为蓝牙接口。 |
| `QNetworkConfiguration.BearerWiMAX` | `8` | 配置是用于WiMAX接口。 |

```
QNetworkConfiguration.Purpose
```

指定配置的目的。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkConfiguration.UnknownPurpose` | `0` | 在配置上并没有指定任何目的。这是默认值。 |
| `QNetworkConfiguration.PublicPurpose` | `1` | 该配置可用于一般用途的互联网接入。 |
| `QNetworkConfiguration.PrivatePurpose` | `2` | 该配置适用于访问私有网络，如一个办公室内联网。 |
| `QNetworkConfiguration.ServiceSpecificPurpose` | `3` | 该配置可用于运营商特定服务（如接收彩信或内容流） 。 |

```
QNetworkConfiguration.StateFlag
```

指定配置状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkConfiguration.Undefined` | `0x0000001` | 这种状态是用于瞬时配置，如新发现的WLAN的量，用户实际上并没有创建配置爱好。 |
| `QNetworkConfiguration.Defined` | `0x0000002` | 定义的配置是众所周知的系统，但不是立即可用（例如，配置的WLAN是不在范围内或以太网电缆目前没有插入机） 。 |
| `QNetworkConfiguration.Discovered` | `0x0000006` | 发现的配置，可立即用于创建一个新的[QNetworkSession](qnetworksession.html)。已发现的结构的一个例子可以是一个无线局域网是在范围内。如果设备移出的范围内发现标志被丢弃。第二个例子是一个GPRS配置通常仍然发现，只要该设备具有网络复盖。具有此状态的配置也是在状态QNetworkConfiguration.Defined 。如果配置一个服务网络这个标志被设置，如果底层的接入点配置的至少一个具有发现的状态。 |
| `QNetworkConfiguration.Active` | `0x000000e` | 该配置是目前使用的一个开放的网络会议（见[QNetworkSession.isOpen](qnetworksession.html#isOpen)（））。然而，这并不意味着当前进程是创建公开会议的实体。它仅仅表明，如果一个新的[QNetworkSession](qnetworksession.html)是在此基础上对配置进行构建[QNetworkSession.state](qnetworksession.html#state)（ ）将返回[QNetworkSession.Connected](qnetworksession.html#State-enum)。这种状态意味着QNetworkConfiguration.Discovered状态。 |

该StateFlags类型是一个typedef为[QFlags](index.htm)\u003cStateFlag\u003e 。它存储StateFlag值的或组合。

```
QNetworkConfiguration.Type
```

这个枚举描述的配置类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkConfiguration.InternetAccessPoint` | `0` | 配置指定了细节的单一访问点。注意，类型InternetAccessPoint的配置可以是类型ServiceNetwork的其他QNetworkConfigurations的一部分。 |
| `QNetworkConfiguration.ServiceNetwork` | `1` | 该配置是基于一组类型InternetAccessPoint的QNetworkConfigurations的。所有小组成员可以达到同样的目标网络。这种类型的配置是漫游功能的网络会话的强制性要求。在某些平台这种形式的配置也可以被称为服务网络接入点（ SNAP ） 。 |
| `QNetworkConfiguration.UserChoice` | `2` | 配置是一个佔位符将由该平台的会话打开的时候被解析为实际的配置。根据不同的平台上的选择可能会生成一个弹出式对话框，询问他的首选用户。 |
| `QNetworkConfiguration.Invalid` | `3` | 配置是无效的。 |

* * *

## Method Documentation

```
QNetworkConfiguration.__init__ (self)
```

构造一个无效的配置对象。

**See also** [isValid](qnetworkconfiguration.html#isValid)（ ） 。

```
QNetworkConfiguration.__init__ (self, QNetworkConfiguration other)
```

创建的副本[QNetworkConfiguration](qnetworkconfiguration.html)包含的对象_other_。

```
QString QNetworkConfiguration.bearerName (self)
```

此功能已被弃用。

此功能已被弃用。这等同于调用[bearerTypeName](qnetworkconfiguration.html#bearerTypeName)（ ） ，但[bearerType](qnetworkconfiguration.html#bearerType)（ ）应优先使用。

```
BearerType QNetworkConfiguration.bearerType (self)
```

[

返回此网络配置承载的类型。

](qnetworkconfiguration.html#BearerType-enum)

[如果载体的类型](qnetworkconfiguration.html#BearerType-enum)[unknown](qnetworkconfiguration.html#BearerType-enum)该[bearerTypeName](qnetworkconfiguration.html#bearerTypeName)（）函数可以被用于检索承载一个纹理类型名称。

一个无效的网络配置总是返回[BearerUnknown](qnetworkconfiguration.html#BearerType-enum)值。

```
QString QNetworkConfiguration.bearerTypeName (self)
```

返回此网络配置为一个字符串承载的类型。

该字符串不被翻译，并因此不能被显示给用户。随后的表显示之间的固定映射[BearerType](qnetworkconfiguration.html#BearerType-enum)并为已知类型的承载类型名称。如果[BearerType](qnetworkconfiguration.html#BearerType-enum)未知这个函数可以返回更多的信息，如果它是可用的，否则一个空字符串将被返回。

| [BearerType](qnetworkconfiguration.html#BearerType-enum) | Value |
| --- | --- |
| [BearerUnknown](qnetworkconfiguration.html#BearerType-enum) |  | The session is based on an unknown or unspecified bearer type. The value of the string returned describes the bearer type. |
| [BearerEthernet](qnetworkconfiguration.html#BearerType-enum) | Ethernet |
| [BearerWLAN](qnetworkconfiguration.html#BearerType-enum) | WLAN |
| [Bearer2G](qnetworkconfiguration.html#BearerType-enum) | 2G |
| [BearerCDMA2000](qnetworkconfiguration.html#BearerType-enum) | CDMA2000 |
| [BearerWCDMA](qnetworkconfiguration.html#BearerType-enum) | WCDMA |
| [BearerHSPA](qnetworkconfiguration.html#BearerType-enum) | HSPA |
| [BearerBluetooth](qnetworkconfiguration.html#BearerType-enum) | Bluetooth |
| [BearerWiMAX](qnetworkconfiguration.html#BearerType-enum) | WiMAX |

这个函数返回一个空字符串，如果这是无效的配置，类型的网络配置[QNetworkConfiguration.ServiceNetwork](qnetworkconfiguration.html#Type-enum) or [QNetworkConfiguration.UserChoice](qnetworkconfiguration.html#Type-enum)。

**See also** [bearerType](qnetworkconfiguration.html#bearerType)（ ） 。

```
list-of-QNetworkConfiguration QNetworkConfiguration.children (self)
```

返回优先顺序该网络配置的所有子配置。在列表中的第一子结构具有最高优先级。

类型的唯一网络配置[ServiceNetwork](qnetworkconfiguration.html#Type-enum)可以有孩子。否则，这个函数返回一个空列表。

```
QString QNetworkConfiguration.identifier (self)
```

返回此网络配置的独特性和平台特定的标识符，否则为空字符串。

```
bool QNetworkConfiguration.isRoamingAvailable (self)
```

返回True如果此配置支持漫游，否则为False 。

```
bool QNetworkConfiguration.isValid (self)
```

返回True如果[QNetworkConfiguration](qnetworkconfiguration.html)目的是有效的。如果用户删除配置或配置了缺省构造的配置可能会变得无效。

的添加和删除的配置，可以通过监测[QNetworkConfigurationManager](qnetworkconfigurationmanager.html)。

**See also** [QNetworkConfigurationManager](qnetworkconfigurationmanager.html)。

```
QString QNetworkConfiguration.name (self)
```

返回该配置的用户可见的名称。

名称可以是底层的接入点的名称或服务的网络，这种结构代表名称。

```
Purpose QNetworkConfiguration.purpose (self)
```

[

返回该配置的目的。

其目的字段可以用于以编程方式确定配置的目的。这些信息通常是接入点或服务网络的元数据的一部分。

](qnetworkconfiguration.html#Purpose-enum)

```
StateFlags QNetworkConfiguration.state (self)
```

[

返回构造的当前状态。

](index.htm)

```
Type QNetworkConfiguration.type (self)
```

[

返回构造的类型。

配置中可以代表一个单独的接入点的配置或一组接入点的配置。这样的一组被称为服务网络。这是基于一个服务网络上的配置可以潜在地支持网络会话的漫游。

```
bool QNetworkConfiguration.__eq__ (self, QNetworkConfiguration cp)
```

```
bool QNetworkConfiguration.__ne__ (self, QNetworkConfiguration cp)
```

](qnetworkconfiguration.html#Type-enum)