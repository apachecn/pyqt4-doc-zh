# QNetworkConfigurationManager Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkConfigurationManager类管理系统所提供的网络配置。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `class **[Capabilities](index.htm)**`
*   `enum Capability { CanStartAndStopInterfaces, DirectConnectionRouting, SystemSessionSupport, ApplicationLevelRoaming, ..., NetworkSessionRequired }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `list-of-QNetworkConfiguration allConfigurations (self, QNetworkConfiguration.StateFlags flags = 0)`
*   `Capabilities capabilities (self)`
*   `QNetworkConfiguration configurationFromIdentifier (self, QString identifier)`
*   `QNetworkConfiguration defaultConfiguration (self)`
*   `bool isOnline (self)`
*   `updateConfigurations (self)`

### Qt Signals

*   `void configurationAdded (const QNetworkConfiguration&)`
*   `void configurationChanged (const QNetworkConfiguration&)`
*   `void configurationRemoved (const QNetworkConfiguration&)`
*   `void onlineStateChanged (bool)`
*   `void updateCompleted ()`

* * *

## Detailed Description

该QNetworkConfigurationManager类管理系统所提供的网络配置。

QNetworkConfigurationManager提供对系统已知的网络配置，并允许应用程序在运行时，检测系统的能力（与问候网络会话）。

A [QNetworkConfiguration](qnetworkconfiguration.html)抽象一组描述如何在网络接口必须被配置为连接到一个特定的目标网络的配置选项。 QNetworkConfigurationManager维护和更新QNetworkConfigurations的全局列表。应用程序可以通过访问和过滤此列表[allConfigurations](qnetworkconfigurationmanager.html#allConfigurations)（ ） 。如果一个新的配置添加或现有被删除或更改[configurationAdded](qnetworkconfigurationmanager.html#configurationAdded)（ ）[configurationRemoved](qnetworkconfigurationmanager.html#configurationRemoved)（）和[configurationChanged](qnetworkconfigurationmanager.html#configurationChanged)（）信号被分别发射。

该[defaultConfiguration](qnetworkconfigurationmanager.html#defaultConfiguration)（ ）可以打算立即创建一个新的网络会话无需关心特定配置时使用。它返回一个[QNetworkConfiguration.Discovered](qnetworkconfiguration.html#StateFlag-enum)配置。如果没有任何发现的人则返回一个无效的配置。

一些配置更新可能需要一些时间来执行更新。例如，WLAN扫描就是这样一个例子。除非该平台进行内部更新，可能需要通过手动触发配置更新[QNetworkConfigurationManager.updateConfigurations](qnetworkconfigurationmanager.html#updateConfigurations)（ ） 。更新过程的完成是由发光的起诉[updateCompleted](qnetworkconfigurationmanager.html#updateCompleted)（）信号。更新过程，确保每一个现有的[QNetworkConfiguration](qnetworkconfiguration.html)实例更新。有没有必要通过索要重新配置清单[allConfigurations](qnetworkconfigurationmanager.html#allConfigurations)（ ） 。

* * *

## Type Documentation

```
QNetworkConfigurationManager.Capability
```

指定承载API的系统的能力。可能的值有：

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkConfigurationManager.CanStartAndStopInterfaces` | `0x00000001` | 网络会议和其相关的接入点可以启动和停止。如果该标志没有被设置[QNetworkSession](qnetworksession.html)只能监视而不会影响接入点的状态。在某些平台上，此功能可能需要提升的用户权限。此选项特定平台和可能不总是可用的。 |
| `QNetworkConfigurationManager.DirectConnectionRouting` | `0x00000002` | 网络会话和它们的插座可以绑定到一个特定的网络接口。穿过套接字的任何数据包进入到指定的网络接口，从而忽视了标准的路由表项。这可能是有用的，当两个接口可以达到重叠的IP范围或应用程序具有的问候针对网络的特殊需求。此选项特定平台和可能不总是可用的。 |
| `QNetworkConfigurationManager.SystemSessionSupport` | `0x00000004` | 如果这个标志被设置在底层平台确保了网络接口没有关闭，直到最后一个网络会话已[closed()](qnetworksession.html#close)。这可以跨多个进程。如果平台支持会话缺少这个API只能确保为同一进程内的网络会话的上述行为。在一般的移动平台（如Symbian/S60 ）有这样的支持，而大多数桌面平台缺乏这种能力。 |
| `QNetworkConfigurationManager.ApplicationLevelRoaming` | `0x00000008` | 该系统使应用程序在系统中的漫游行为控制。应用程序可以启动漫游的情况下（当前的链路是不适合的），并进行协商，如果系统已经确定更合适的接入点。 |
| `QNetworkConfigurationManager.ForcedRoaming` | `0x00000010` | 该系统断开现有的接入点，并通过一个更适合的重新连接。该应用程序没有在这个过程中的任何控制，并有重新活跃的插座。 |
| `QNetworkConfigurationManager.DataStatistics` | `0x00000020` | 如果该标志被设置[QNetworkSession](qnetworksession.html)可以提供关于发送和接收的数据的统计信息。 |
| `QNetworkConfigurationManager.NetworkSessionRequired` | `0x00000040` | 如果这个标志被设置在平台要求网络运营才能执行网络会话被创建。 |

功能类型是一个typedef为[QFlags](index.htm)\u003cCapability\u003e 。它存储能力值的一个或组合。

* * *

## Method Documentation

```
QNetworkConfigurationManager.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QNetworkConfigurationManager](qnetworkconfigurationmanager.html)用给定的_parent_。

请注意，以确保立即可用的当前配置的有效名单，更新被施工造成一些延迟期间完成。

```
list-of-QNetworkConfiguration QNetworkConfigurationManager.allConfigurations (self, QNetworkConfiguration.StateFlags flags = 0)
```

返回的配置，这符合给出的列表_filter_。

默认情况下，该函数返回所有（已定义和未定义）配置。

一种无线网络与一个特定的SSID可能只能访问在一定区域内，尽管该系统具有用于其有效的配置的事实。因此，过滤器旗标可用于列表限制为仅发现并可能连接的配置。

If _filter_设置为零则该函数返回所有可能的配置。

注意，这个函数返回的状态的所有配置，因为他们知道在这个函数调用的时间。举例来说如果类型的WLAN的结构进行定义的系统可能必须以确定它是否是实际可用的执行WLAN扫描。为了获得最准确的状态[updateConfigurations](qnetworkconfigurationmanager.html#updateConfigurations)（ ）应该用于更新每个配置的状态。请注意，这样的更新可能需要一些时间。它的完成是由信号[updateCompleted](qnetworkconfigurationmanager.html#updateCompleted)（ ） 。在没有配置更新的这个函数返回的最佳估计在调用的时候。因此，如果无线网络配置是感兴趣的，则建议[updateConfigurations](qnetworkconfigurationmanager.html#updateConfigurations)（ ）被调用一次后[QNetworkConfigurationManager](qnetworkconfigurationmanager.html)实例化（WLAN扫描太费时在构造函数中执行） 。在此之后，数据被保持自动向上最新的系统信息报告的任何变化。

```
Capabilities QNetworkConfigurationManager.capabilities (self)
```

[

返回由当前平台所支持的功能。

](index.htm)

```
QNetworkConfiguration QNetworkConfigurationManager.configurationFromIdentifier (self, QString identifier)
```

[](qnetworkconfiguration.html)

[返回](qnetworkconfiguration.html)[QNetworkConfiguration](qnetworkconfiguration.html)为_identifier_否则返回一个无效的[QNetworkConfiguration](qnetworkconfiguration.html)。

**See also** [QNetworkConfiguration.identifier](qnetworkconfiguration.html#identifier)（ ） 。

```
QNetworkConfiguration QNetworkConfigurationManager.defaultConfiguration (self)
```

[

返回要使用的默认配置。这个函数总是返回一个发现的配置，否则配置无效。

](qnetworkconfiguration.html)

[在某些情况下，可能需要调用](qnetworkconfiguration.html)[updateConfigurations](qnetworkconfigurationmanager.html#updateConfigurations)（） ，并等待[updateCompleted](qnetworkconfigurationmanager.html#updateCompleted)调用此函数之前（ ）信号。

**See also** [allConfigurations](qnetworkconfigurationmanager.html#allConfigurations)（ ） 。

```
bool QNetworkConfigurationManager.isOnline (self)
```

返回True如果系统被认为是连接到通过活动的网络接口其它设备，否则返回False 。

这相当于下面的代码片段：

```
 [QNetworkConfigurationManager](qnetworkconfigurationmanager.html) mgr;
 [QList](index.htm)<[QNetworkConfiguration](qnetworkconfiguration.html)> activeConfigs = mgr.allConfigurations([QNetworkConfiguration](qnetworkconfiguration.html).Active)
 if (activeConfigs.count() > 0)
     Q_ASSERT(mgr.isOnline())
 else
     Q_ASSERT(!mgr.isOnline())

```

**See also** [onlineStateChanged](qnetworkconfigurationmanager.html#onlineStateChanged)（ ） 。

```
QNetworkConfigurationManager.updateConfigurations (self)
```

启动所有配置的更新。这可以被用于启动可能需要获得正确的状态配置的WLAN扫描或其它费时的更新。

这个调用是异步的。此更新完成后，[updateCompleted](qnetworkconfigurationmanager.html#updateCompleted)（）信号被发射。如果新的配置被发现或被删除或更改旧的更新过程中可能会触发一个或多个排放[configurationAdded](qnetworkconfigurationmanager.html#configurationAdded)（ ）[configurationRemoved](qnetworkconfigurationmanager.html#configurationRemoved)（）和[configurationChanged](qnetworkconfigurationmanager.html#configurationChanged)（ ）信号。

如果配置状态的变化，因为这更新所有现有的结果[QNetworkConfiguration](qnetworkconfiguration.html)实例自动更新。

**See also** [allConfigurations](qnetworkconfigurationmanager.html#allConfigurations)（ ） 。

* * *

## Qt Signal Documentation

```
void configurationAdded (const QNetworkConfiguration&)
```

这是该信号的默认超载。

每当一个新的网络配置被添加到系统中，这信号被发射。被指定的新配置_config_。

```
void configurationChanged (const QNetworkConfiguration&)
```

这是该信号的默认超载。

这个信号被发射时的[state](qnetworkconfiguration.html#state)的_config_变化。

```
void configurationRemoved (const QNetworkConfiguration&)
```

这是该信号的默认超载。

当配置即将被从系统中移除这个信号被发射。拆下的结构，通过指定_config_，是无效的，但保留名称和标识。

此功能被引入Qt的4.8 。

```
void onlineStateChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时，该设备改变从联机到脱机模式或反之亦然。_isOnline_代表该设备的新的状态。

该州被认为是只要在线[allConfigurations](qnetworkconfigurationmanager.html#allConfigurations)（[QNetworkConfiguration.Active](qnetworkconfiguration.html#StateFlag-enum)）返回与至少一个条目的列表。

```
void updateCompleted ()
```

这是该信号的默认超载。

当配置更新已经完成这个信号被发射。这样的更新可以通过启动[updateConfigurations](qnetworkconfigurationmanager.html#updateConfigurations)（ ） 。