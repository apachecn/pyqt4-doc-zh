# QNetworkSession Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkSession类提供对系统的接入点控制，使会话管理的情况下，当多个客户端访问同一个接入点。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum SessionError { UnknownSessionError, SessionAbortedError, RoamingError, OperationNotSupportedError, InvalidConfigurationError }`
*   `enum State { Invalid, NotAvailable, Connecting, Connected, ..., Roaming }`

### Methods

*   `__init__ (self, QNetworkConfiguration connConfig, QObject parent = None)`
*   `accept (self)`
*   `int activeTime (self)`
*   `int bytesReceived (self)`
*   `int bytesWritten (self)`
*   `close (self)`
*   `QNetworkConfiguration configuration (self)`
*   `connectNotify (self, SIGNAL() signal)`
*   `disconnectNotify (self, SIGNAL() signal)`
*   `SessionError error (self)`
*   `QString errorString (self)`
*   `ignore (self)`
*   `QNetworkInterface interface (self)`
*   `bool isOpen (self)`
*   `migrate (self)`
*   `open (self)`
*   `reject (self)`
*   `QVariant sessionProperty (self, QString key)`
*   `setSessionProperty (self, QString key, QVariant value)`
*   `State state (self)`
*   `stop (self)`
*   `bool waitForOpened (self, int msecs = 30000)`

### Qt Signals

*   `void closed ()`
*   `void error (QNetworkSession::SessionError)`
*   `void newConfigurationActivated ()`
*   `void opened ()`
*   `void preferredConfigurationChanged (const QNetworkConfiguration&,bool)`
*   `void stateChanged (QNetworkSession::State)`

* * *

## Detailed Description

该QNetworkSession类提供对系统的接入点控制，使会话管理的情况下，当多个客户端访问同一个接入点。

一个QNetworkSession使得在系统的网络接口控制。会话的配置参数是通过确定[QNetworkConfiguration](qnetworkconfiguration.html)对象，其中就必然。根据会话的类型（单一的接入点或网络服务）的会话可以被链接到一个或多个网络接口。借[opening](qnetworksession.html#open)和[closing](qnetworksession.html#close)网络课程的开发者可以启动和停止系统的网络接口。如果该结构代表多个接入点（见[QNetworkConfiguration.ServiceNetwork](qnetworkconfiguration.html#Type-enum)）更先进的功能，例如漫游可能得到支持。

QNetworkSession支持会话管理同一进程内的，并根据平台的功能可支持外的过程的会话。如果同一个网络配置使用多个打开的会话，一旦最后一个会话已经关闭了底层网络接口仅终止。

### Roaming

应用程序可以连接到[preferredConfigurationChanged](qnetworksession.html#preferredConfigurationChanged)（）信号，以便接收通知时，更合适的接入点成为可用的。响应于该信号的应用程序必须或者发起漫游经由[migrate](qnetworksession.html#migrate)（）或[ignore](qnetworksession.html#ignore)（ ）新的接入点。一旦会话已漫游[newConfigurationActivated](qnetworksession.html#newConfigurationActivated)（）信号被发射。该应用程序现在可以测试载体和必须要么[accept](qnetworksession.html#accept)（）或[reject](qnetworksession.html#reject)（ ）它。会议将返回到先前的接入点，如果漫游遭到拒绝。随后的状态图描述了所需要的状态转换。

![](../img/roaming-states.png)

有些平台可能区分强制漫游和应用层漫游（ ALR ） 。 ALR意味着应用控制（通过[migrate](qnetworksession.html#migrate)（ ）[ignore](qnetworksession.html#ignore)（ ）[accept](qnetworksession.html#accept)（）和[reject](qnetworksession.html#reject)（））是否在网络会话可以从一个接入点漫游到下一个。如果应用程序保持状态的套接字连接，并要控制从一个接口到下一个过渡这样的控制是有用的。强制漫游意味着系统会自动漫游到下一个网络没有谘询该应用程序。这样做的好处是应用程序可以利用漫游功能，而实际上是意识到这一点。预期的应用程序检测到相关插座被打破，并自动通过新的网络链路重新连接。

如果平台支持漫游的两种模式，一个应用程序通过连接到显示其偏好[preferredConfigurationChanged](qnetworksession.html#preferredConfigurationChanged)（）信号。连接到这个信号意味着该应用程序要接管漫游行为的控制，因此意味着应用程序级的漫游。如果客户端无法连接到[preferredConfigurationChanged](qnetworksession.html#preferredConfigurationChanged)（ ） ，强制漫游使用。如果不支持强制漫游网络会话将默认不漫游。

有些应用程序可能要抑制任何形式的漫游完全的。可能的用例可能是高优先级下载或远程服务无法处理漫游功能的客户端。客户可以通过连接到抑制漫游[preferredConfigurationChanged](qnetworksession.html#preferredConfigurationChanged)（ ）信号，并回答与每个信号发射[ignore](qnetworksession.html#ignore)（ ） 。

* * *

## Type Documentation

```
QNetworkSession.SessionError
```

这个枚举说明可能发生的会话错误。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkSession.UnknownSessionError` | `0` | 发生不明的错误。 |
| `QNetworkSession.SessionAbortedError` | `1` | 这次会议是由用户中止或系统。 |
| `QNetworkSession.RoamingError` | `2` | 会话不能漫游到一个新的配置。 |
| `QNetworkSession.OperationNotSupportedError` | `3` | 不支持当前配置的操作。 |
| `QNetworkSession.InvalidConfigurationError` | `4` | 目前无法对当前配置进行操作。 |

```
QNetworkSession.State
```

这个枚举变量描述了会话的连接状态。如果会话是基于一个单一的访问点配置会话的状态是一样的相关网络接口的状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkSession.Invalid` | `0` | 这次会议是由于无效的配置无效。这可能会发生因已移除接入点或者是无效的，开始与配置。 |
| `QNetworkSession.NotAvailable` | `1` | 这次会议是基于一个定义，但尚未发现[QNetworkConfiguration](qnetworkconfiguration.html)（见[QNetworkConfiguration.StateFlag](qnetworkconfiguration.html#StateFlag-enum)） 。 |
| `QNetworkSession.Connecting` | `2` | 网络会话正在建立。 |
| `QNetworkSession.Connected` | `3` | 网络会话连接。如果当前进程想使用这个会话它通过调用注册其兴趣[open](qnetworksession.html#open)（ ） 。网络会话被认为是准备好套接字操作，如果它[isOpen](qnetworksession.html#isOpen)（）和连接。 |
| `QNetworkSession.Closing` | `4` | 网络会话处于被关闭的过程。 |
| `QNetworkSession.Disconnected` | `5` | 网络会话没有连接。相关[QNetworkConfiguration](qnetworkconfiguration.html)有状态[QNetworkConfiguration.Discovered](qnetworkconfiguration.html#StateFlag-enum)。 |
| `QNetworkSession.Roaming` | `6` | 所述网络会话是从一个接入点漫游到另一个接入点。 |

* * *

## Method Documentation

```
QNetworkSession.__init__ (self, QNetworkConfiguration connConfig, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个会话的基础上_connectionConfig_用给定的_parent_。

**See also** [QNetworkConfiguration](qnetworkconfiguration.html)。

```
QNetworkSession.accept (self)
```

这种方法也是一个Qt槽与C + +的签名`void accept()`。

指示会话永久接受新的接入点。一旦该功能被称为会话可能不会返回到旧的接入点。

旧的接入点可以在这一过程中被关闭，如果有针对它没有其它的网络会话。因此，仍然使用旧的接入点的任何打开的socket可能变得不稳定，并完成迁移之前，应该关闭。

```
int QNetworkSession.activeTime (self)
```

返回该会话一直活跃的秒数。

```
int QNetworkSession.bytesReceived (self)
```

返回字节接收到的数据量，否则为0 。

该字段值包括其两端使用相同的网络接口的所有开放式网络会话使用。

如果会话是基于服务的网络配置在所有活动成员配置发送的字节数返回。

此功能可能并不总是在所有平台上，并返回0的支持。可以通过检测到该平台的能力[QNetworkConfigurationManager.DataStatistics](qnetworkconfigurationmanager.html#Capability-enum)。

**Note:**在某些平台上，此功能可能运行主事件循环。

```
int QNetworkSession.bytesWritten (self)
```

返回以字节为单位发送的数据量，否则为0 。

该字段值包括其两端使用相同的网络接口的所有开放式网络会话使用。

如果会话是基于服务的网络配置在所有活动成员配置发送的字节数返回。

此功能可能并不总是在所有平台上，并返回0的支持。可以通过检测到该平台的能力[QNetworkConfigurationManager.DataStatistics](qnetworkconfigurationmanager.html#Capability-enum)。

**Note:**在某些平台上，此功能可能运行主事件循环。

```
QNetworkSession.close (self)
```

这种方法也是一个Qt槽与C + +的签名`void close()`。

减少对相关的网络配置的会话计数器。如果会话计数器归零活动的网络接口被关闭。这也意味着[state](qnetworksession.html#state)（）将只从改变[Connected](qnetworksession.html#State-enum)至[Disconnected](qnetworksession.html#State-enum)如果当前会话是最后打开的会话。

如果平台不支持外的会话过程中调用此函数不停止的接口。在这种情况下[stop](qnetworksession.html#stop)（ ）已被用来强制关闭。该平台的能力可通过被检测[QNetworkConfigurationManager.capabilities](qnetworkconfigurationmanager.html#capabilities)（ ） 。

注意，这个调用是异步的。根据此调用的结果的结果可以通过连接到被询问[stateChanged](qnetworksession.html#stateChanged)（ ）[opened](qnetworksession.html#opened)（）或[error](qnetworksession.html#error)（ ）信号。

**See also** [open](qnetworksession.html#open)（ ）[stop](qnetworksession.html#stop)（）和[isOpen](qnetworksession.html#isOpen)（ ） 。

```
QNetworkConfiguration QNetworkSession.configuration (self)
```

[](qnetworkconfiguration.html)

[返回](qnetworkconfiguration.html)[QNetworkConfiguration](qnetworkconfiguration.html)该网络会话对象基础上的。

**See also** [QNetworkConfiguration](qnetworkconfiguration.html)。

```
QNetworkSession.connectNotify (self, SIGNAL() signal)
```

```
QNetworkSession.disconnectNotify (self, SIGNAL() signal)
```

```
SessionError QNetworkSession.error (self)
```

[

返回上次发生错误的类型。

](qnetworksession.html#SessionError-enum)

[**See also**](qnetworksession.html#SessionError-enum) [state](qnetworksession.html#state)（）和[errorString](qnetworksession.html#errorString)（ ） 。

```
QString QNetworkSession.errorString (self)
```

返回上次发生设备错误的人类可读的描述。

**See also** [error](qnetworksession.html#error)（ ） 。

```
QNetworkSession.ignore (self)
```

这种方法也是一个Qt槽与C + +的签名`void ignore()`。

该函数表示该应用程序不希望漫游会话。

**See also** [migrate](qnetworksession.html#migrate)（ ） 。

```
QNetworkInterface QNetworkSession.interface (self)
```

[

返回用于此会话的网络接口。

](qnetworkinterface.html)

[这个函数只返回一个有效的](qnetworkinterface.html)[QNetworkInterface](qnetworkinterface.html)在本次会议是[Connected](qnetworksession.html#State-enum)。

返回的接口可能会改变一个漫游过程的结果。

注：此功能在Symbian的模拟器，由于连接是模拟Windows上的工作方式。

**See also** [state](qnetworksession.html#state)（ ） 。

```
bool QNetworkSession.isOpen (self)
```

返回True如果这个环节是开放的。如果所有打开的会话数是大于零的底层网络接口将保持连接/向上。

会话可以通过被控制[open](qnetworksession.html#open)（）和[close](qnetworksession.html#close)（ ） 。

```
QNetworkSession.migrate (self)
```

这种方法也是一个Qt槽与C + +的签名`void migrate()`。

指示会话漫游到新的接入点。旧的接入点保持有效，直到应用程序调用[accept](qnetworksession.html#accept)（ ） 。

该[newConfigurationActivated](qnetworksession.html#newConfigurationActivated)（）信号被发射一次漫游已经完成。

**See also** [accept](qnetworksession.html#accept)（ ） 。

```
QNetworkSession.open (self)
```

这种方法也是一个Qt槽与C + +的签名`void open()`。

创建一个公开会议这增加了底层网络接口上的会话计数。直到会话引用计数器达到零，系统将不会终止网络接口。因此，一个公开会议允许应用程序注册其使用的接口。

由于调用open的结果（ ）接口将被启动，如果它没有连接/上呢。有些平台可能不提供了进程外会话的支持。在这种平台上的会话计数器会忽略另一个进程持有的任何会议。该平台的能力可通过被检测[QNetworkConfigurationManager.capabilities](qnetworkconfigurationmanager.html#capabilities)（ ） 。

注意，这个调用是异步的。根据此调用的结果的结果可以通过连接到被询问[stateChanged](qnetworksession.html#stateChanged)（ ）[opened](qnetworksession.html#opened)（）或[error](qnetworksession.html#error)（ ）信号。

这不是一个要求，以便监测底层网络接口打开会话。

**See also** [close](qnetworksession.html#close)（ ）[stop](qnetworksession.html#stop)（）和[isOpen](qnetworksession.html#isOpen)（ ） 。

```
QNetworkSession.reject (self)
```

这种方法也是一个Qt槽与C + +的签名`void reject()`。

新的接入点是不适合的应用。通过调用这个函数会返回先前的接入点/配置。这个动作可能会使已经通过不想要的接入点建立的任何插座。

**See also** [accept](qnetworksession.html#accept)（ ） 。

```
QVariant QNetworkSession.sessionProperty (self, QString key)
```

返回属性的值_key_。

一个网络会话可以有附加这可能说明会话更详细的属性。这个函数可用于获得这些属性。

下面的属性键，保证在所有平台上指定：

| Key | Description |
| --- | --- |
| ActiveConfiguration | If the session [isOpen](qnetworksession.html#isOpen)() this property returns the identifier of the [QNetworkConfiguration](qnetworkconfiguration.html) that is used by this session; otherwise an empty string.该键的主要目的是确定哪些互联网接入点使用，如果会话是基于[ServiceNetwork](qnetworkconfiguration.html#Type-enum)。下面的代码片段凸显差异：

```
 [QNetworkConfigurationManager](qnetworkconfigurationmanager.html) mgr;
 [QNetworkConfiguration](qnetworkconfiguration.html) ap = mgr.defaultConfiguration();
 [QNetworkSession](qnetworksession.html) *session = new [QNetworkSession](qnetworksession.html)(ap);
 ... //code activates session

 [QString](qstring.html) ident = session-&gt;sessionProperty("ActiveConfiguration").toString();
 if ( ap.type() == [QNetworkConfiguration](qnetworkconfiguration.html).ServiceNetwork ) {
     Q_ASSERT( ap.identifier() != ident );
     Q_ASSERT( ap.children().contains( mgr.configurationFromIdentifier(ident) ) );
 } else if ( ap.type() == [QNetworkConfiguration](qnetworkconfiguration.html).InternetAccessPoint ) {
     Q_ASSERT( ap.identifier() == ident );
 }

```

 |
| UserChoiceConfiguration | If the session [isOpen](qnetworksession.html#isOpen)() and is bound to a [QNetworkConfiguration](qnetworkconfiguration.html) of type UserChoice, this property returns the identifier of the [QNetworkConfiguration](qnetworkconfiguration.html) that the configuration resolved to when [open](qnetworksession.html#open)() was called; otherwise an empty string.这个密钥的目的是为了确定实际[QNetworkConfiguration](qnetworkconfiguration.html)该会话使用。这关键是要从不同_ActiveConfiguration_在这关键的可能会返回一个标识符为任何一个[service network](qnetworkconfiguration.html#Type-enum)或[Internet access points](qnetworkconfiguration.html#Type-enum)配置，而_ActiveConfiguration_总是返回标识符[Internet access points](qnetworkconfiguration.html#Type-enum)配置。 |
| ConnectInBackground | Setting this property to _true_ before calling [open](qnetworksession.html#open)() implies that the connection attempt is made but if no connection can be established, the user is not connsulted and asked to select a suitable connection. This property is not set by default and support for it depends on the platform. |
| AutoCloseSessionTimeout | If the session requires polling to keep its state up to date, this property holds the timeout in milliseconds before the session will automatically close. If the value of this property is -1 the session will not automatically close. This property is set to -1 by default.此属性的目的是尽量减少在使用轮询来更新会话的状态平台的资源使用。应用程序可以将此属性的值设置为所需的超时之前关闭会话。响应于该[closed](qnetworksession.html#closed)（ ）信号的网络会话应删除，以确保所有投票已停止。一旦它再次需要该会话就可以被重建。此属性对会话不需要轮询没有影响。 |

**See also** [setSessionProperty](qnetworksession.html#setSessionProperty)（ ） 。

```
QNetworkSession.setSessionProperty (self, QString key, QVariant value)
```

设置属性_value_本届会议。该物业使用标识_key_。移除已设置的属性可以通过传递一个无效的实现[QVariant](qvariant.html)。

注意，这个_UserChoiceConfiguration_和_ActiveConfiguration_属性是只读的，不能用这种方法来改变。

**See also** [sessionProperty](qnetworksession.html#sessionProperty)（ ） 。

```
State QNetworkSession.state (self)
```

[

返回会话的状态。

如果会话是基于一个单一的访问点配置会话的状态是一样的相关网络接口的状态。因此，一个网络会话对象可以用来监视网络接口。

](qnetworksession.html#State-enum)

[A](qnetworksession.html#State-enum) [QNetworkConfiguration.ServiceNetwork](qnetworkconfiguration.html#Type-enum)根据会议总结了所有儿童的状态，因此返回[Connected](qnetworksession.html#State-enum)如果状态的服务网络的至少一个[children()](qnetworkconfiguration.html#children)配置处于活动状态。

请注意，它不是必需的，以便获得网络接口的状态举行公开会议。一个连接，但闭门会议可以用来监视网络接口，而一个开放和连接的会话对象可能会阻止网络接口被关闭。

**See also** [error](qnetworksession.html#error)（）和[stateChanged](qnetworksession.html#stateChanged)（ ） 。

```
QNetworkSession.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。

对失效的网络接口的所有打开的会话，因此停止了底层网络接口。此函数始终改变会话的[state](qnetworksession.html#state)（ ）标志，以[Disconnected](qnetworksession.html#State-enum)。

在Symbian平台，一个' NetworkControl的能力是必需的全接口级站（不带能力，仅在当前会话已停止） 。

**See also** [open](qnetworksession.html#open)（）和[close](qnetworksession.html#close)（ ） 。

```
bool QNetworkSession.waitForOpened (self, int msecs = 30000)
```

等待，直到会话已开盘，最高_msecs_毫秒。如果会话已经打开，则该函数返回True，否则返回False 。当它返回False的情况下，你可以调用[error](qnetworksession.html#error)（）来确定错误的原因。

下面的例子最多等待一秒要打开的会话：

```
 session->open();
 if (session->waitForOpened(1000))
     qDebug("Open!");

```

If _msecs_为-1 ，此功能将不会超时。

**See also** [open](qnetworksession.html#open)（）和[error](qnetworksession.html#error)（ ） 。

* * *

## Qt Signal Documentation

```
void closed ()
```

这是该信号的默认超载。

当网络会话已被关闭，这个信号被发射。

```
void error (QNetworkSession::SessionError)
```

这是该信号的默认超载。

这个信号被发射时发生错误之后。该_error_参数描述发生的错误。

**See also** [error](qnetworksession.html#error)（）和[errorString](qnetworksession.html#errorString)（ ） 。

```
void newConfigurationActivated ()
```

这是该信号的默认超载。

这个信号被发射一次会话已漫游到新的接入点。应用程序可能会重新开放插座和测试新的网络链接适用性。随后，它必须要么[accept](qnetworksession.html#accept)（）或[reject](qnetworksession.html#reject)（ ）新的接入点。

**See also** [accept](qnetworksession.html#accept)（）和[reject](qnetworksession.html#reject)（ ） 。

```
void opened ()
```

这是该信号的默认超载。

网络会话已被打开时，这个信号被发射。

底层网络接口不会被只要会话保持打开关闭。请注意，此功能是依赖于[system wide session support](qnetworkconfigurationmanager.html#Capability-enum)。

```
void preferredConfigurationChanged (const QNetworkConfiguration&,bool)
```

这是该信号的默认超载。

这个信号被发射时的会话更改首选配置/接入点。只有那些基于服务的网络配置会话可能会发出这样的信号。_config_可用于确定接入点的具体细节，如代理设置，并_isSeamless_指示漫游是否将打破会话的IP地址。

其结果是，以该信号中的应用程序必须通过调用启动漫游过程[migrate](qnetworksession.html#migrate)（ ）或选择[ignore](qnetworksession.html#ignore)（ ）新的接入点。

如果在漫游过程是非无缝的IP地址将改变表示一个插座变得无效。然而无缝移动可以确保本地IP地址不会改变。这是通过使用这势必会在实际链路地址的虚拟IP地址来实现。在漫游过程中，虚拟地址被附加到新的链路地址。

有些平台可能支持强制漫游和应用层漫游（ ALR ）的概念。强制漫游意味着该平台可以简单地漫游到一个新的配置没有谘询应用。它是由应用程序来检测链路层的损失和重建它的插座。相比之下ALR提供的机会，以防止系统的漫游。如果这个会话是基于一个支持漫游的应用程序可以选择是否要通过连接到这个信号进行谘询（ ALR用例）的配置。只要这个信号连接保持该会话仍然注册为漫游的利益相关者，否则漫游将通过该平台实施。

**See also** [migrate](qnetworksession.html#migrate)（ ）[ignore](qnetworksession.html#ignore)（）和[QNetworkConfiguration.isRoamingAvailable](qnetworkconfiguration.html#isRoamingAvailable)（ ） 。

```
void stateChanged (QNetworkSession::State)
```

这是该信号的默认超载。

这个信号被发射时的网络会话的状态改变。该_state_参数是新的状态。

**See also** [state](qnetworksession.html#state)（ ） 。