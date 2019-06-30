# QDBusConnection Class Reference

## [[QtDBus](index.htm) module]

该QDBusConnection类代表到D - Bus总线守护进程的连接。[More...](#details)

### Types

*   `enum BusType { SessionBus, SystemBus, ActivationBus }`
*   `class **[ConnectionCapabilities](index.htm)**`
*   `enum ConnectionCapability { UnixFileDescriptorPassing }`
*   `enum RegisterOption { ExportAdaptors, ExportScriptableSlots, ExportScriptableSignals, ExportScriptableProperties, ..., ExportChildObjects }`
*   `class **[RegisterOptions](index.htm)**`
*   `enum UnregisterMode { UnregisterNode, UnregisterTree }`

### Methods

*   `__init__ (self, QString name)`
*   `__init__ (self, QDBusConnection other)`
*   `QDBusPendingCall asyncCall (self, QDBusMessage message, int timeout = -1)`
*   `QString baseService (self)`
*   `QDBusMessage call (self, QDBusMessage message, QDBus.CallMode mode = QDBus.Block, int timeout = -1)`
*   `bool callWithCallback (self, QDBusMessage message, QObject receiver, SLOT() returnMethod, SLOT() errorMethod, int timeout = -1)`
*   `object callWithCallback (self, QDBusMessage message, callable returnMethod, callable errorMethod, int timeout = -1)`
*   `bool callWithCallback (self, QDBusMessage message, QObject receiver, SLOT() slot, int timeout = -1)`
*   `object callWithCallback (self, QDBusMessage message, callable slot, int timeout = -1)`
*   `bool connect (self, QString service, QString path, QString interface, QString name, QObject receiver, SLOT() slot)`
*   `object connect (self, QString service, QString path, QString interface, QString name, callable slot)`
*   `bool connect (self, QString service, QString path, QString interface, QString name, QString signature, QObject receiver, SLOT() slot)`
*   `object connect (self, QString service, QString path, QString interface, QString name, QString signature, callable slot)`
*   `bool connect (self, QString service, QString path, QString interface, QString name, QStringList argumentMatch, QString signature, QObject receiver, SLOT() slot)`
*   `object connect (self, QString service, QString path, QString interface, QString name, QStringList argumentMatch, QString signature, callable slot)`
*   `ConnectionCapabilities connectionCapabilities (self)`
*   `bool disconnect (self, QString service, QString path, QString interface, QString name, QObject receiver, SLOT() slot)`
*   `object disconnect (self, QString service, QString path, QString interface, QString name, callable slot)`
*   `bool disconnect (self, QString service, QString path, QString interface, QString name, QString signature, QObject receiver, SLOT() slot)`
*   `object disconnect (self, QString service, QString path, QString interface, QString name, QString signature, callable slot)`
*   `bool disconnect (self, QString service, QString path, QString interface, QString name, QStringList argumentMatch, QString signature, QObject receiver, SLOT() slot)`
*   `object disconnect (self, QString service, QString path, QString interface, QString name, QStringList argumentMatch, QString signature, callable slot)`
*   `QDBusConnectionInterface interface (self)`
*   `bool isConnected (self)`
*   `QDBusError lastError (self)`
*   `QString name (self)`
*   `QObject objectRegisteredAt (self, QString path)`
*   `bool registerObject (self, QString path, QObject object, RegisterOptions options = QDBusConnection.ExportAdaptors)`
*   `bool registerService (self, QString serviceName)`
*   `bool send (self, QDBusMessage message)`
*   `unregisterObject (self, QString path, UnregisterMode mode = QDBusConnection.UnregisterNode)`
*   `bool unregisterService (self, QString serviceName)`

### Static Methods

*   `QDBusConnection connectToBus (BusType type, QString name)`
*   `QDBusConnection connectToBus (QString address, QString name)`
*   `QDBusConnection connectToPeer (QString address, QString name)`
*   `disconnectFromBus (QString name)`
*   `disconnectFromPeer (QString name)`
*   `QByteArray localMachineId ()`
*   `QDBusConnection sender ()`
*   `QDBusConnection sessionBus ()`
*   `QDBusConnection systemBus ()`

* * *

## Detailed Description

该QDBusConnection类代表到D - Bus总线守护进程的连接。

这个类是在一个D-Bus的会话初始点。使用它，你可以访问远程对象，接口，连接远程信号传送到对象的插槽;注册对象，等等。

使用创建的D-Bus连接的[connectToBus](qdbusconnection.html#connectToBus)（ ）函数，该函数打开一个到服务器守护程序的连接，并执行初始握手，与相关联的名称连接。进一步尝试使用相同的名称来连接将返回相同的连接。

的连接，然后扯下使用[disconnectFromBus](qdbusconnection.html#disconnectFromBus)（）函数。

一旦断开连接，调用[connectToBus](qdbusconnection.html#connectToBus)（ ）将不会重新建立连接，必须创建一个新的QDBusConnection实例。

为了方便的两个最常见的连接类型，[sessionBus](qdbusconnection.html#sessionBus)（）和[systemBus](qdbusconnection.html#systemBus)（ ）函数返回打开连接到会话服务器守护程序和系统服务器守护程序，分别。这些连接被打开第一次使用时和关闭时的[QCoreApplication](qcoreapplication.html)析构函数被执行。

D-Bus的还支持对等网络连接，而不需要一个总线服务器守护程序。使用这种设备，两个应用程序可以相互交谈并交换信息。这可以通过传递一个地址来实现[connectToBus](qdbusconnection.html#connectToBus)（ ）函数，它是由另一个D-Bus的应用程序中使用QDBusServer打开。

* * *

## Type Documentation

```
QDBusConnection.BusType
```

指定的总线连接的类型。有效的总线类型包括：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusConnection.SessionBus` | `0` | 会话总线，与正在运行的桌面会话相关联 |
| `QDBusConnection.SystemBus` | `1` | 系统总线，搭配全系统进程进行通信 |
| `QDBusConnection.ActivationBus` | `2` | 激活总线， “别名”为启动该服务总线 |

在会话总线，可以由共享同一桌面会话（因此得名）同一用户找到其他应用程序。在系统总线，但是，对于整个系统共享流程通常发现。

```
QDBusConnection.ConnectionCapability
```

这个枚举变量描述了一个D-Bus的连接可用的功能。

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusConnection.UnixFileDescriptorPassing` | `0x0001` | 能够通过Unix的文件描述符给其他进程（见[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)） |

这个枚举被引入或修改的Qt 4.8 。

该ConnectionCapabilities类型是一个typedef为[QFlags](index.htm)\u003cConnectionCapability\u003e 。它存储ConnectionCapability值的或组合。

**See also** [connectionCapabilities](qdbusconnection.html#connectionCapabilities)（ ） 。

```
QDBusConnection.RegisterOption
```

指定与连接对象注册的选项。可能的值有：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusConnection.ExportAdaptors` | `0x01` | 导出适配器在这个对象中找到的内容 |
| `QDBusConnection.ExportScriptableSlots` | `0x10` | 导出此对象的可编写脚本的插槽 |
| `QDBusConnection.ExportScriptableSignals` | `0x20` | 导出此对象的脚本化的信号 |
| `QDBusConnection.ExportScriptableProperties` | `0x40` | 导出此对象的脚本属性 |
| `QDBusConnection.ExportScriptableInvokables` | `0x80` | 导出此对象的可编写脚本invokables |
| `QDBusConnection.ExportScriptableContents` | `0xf0` | 简写形式ExportScriptableSlots &#124; ExportScriptableSignals &#124; ExportScriptableProperties |
| `QDBusConnection.ExportNonScriptableSlots` | `0x100` | 导出此对象的非脚本化的插槽 |
| `QDBusConnection.ExportNonScriptableSignals` | `0x200` | 导出此对象的非脚本化的信号 |
| `QDBusConnection.ExportNonScriptableProperties` | `0x400` | 导出此对象的非脚本化的属性 |
| `QDBusConnection.ExportNonScriptableInvokables` | `0x800` | 导出此对象的非脚本化的invokables |
| `QDBusConnection.ExportNonScriptableContents` | `0xf00` | 简写形式ExportNonScriptableSlots &#124; ExportNonScriptableSignals &#124; ExportNonScriptableProperties |
| `QDBusConnection.ExportAllSlots` | `ExportScriptableSlots &#124; ExportNonScriptableSlots` | 导出所有该对象的插槽 |
| `QDBusConnection.ExportAllSignals` | `ExportScriptableSignals &#124; ExportNonScriptableSignals` | 导出所有该对象的信号 |
| `QDBusConnection.ExportAllProperties` | `ExportScriptableProperties &#124; ExportNonScriptableProperties` | 导出所有的此对象的属性 |
| `QDBusConnection.ExportAllInvokables` | `ExportScriptableInvokables &#124; ExportNonScriptableInvokables` | 导出所有该对象的invokables |
| `QDBusConnection.ExportAllContents` | `ExportScriptableContents &#124; ExportNonScriptableContents` | 导出所有该对象的内容 |
| `QDBusConnection.ExportChildObjects` | `0x1000` | 导出此对象的子对象 |

该RegisterOptions类型是一个typedef为[QFlags](index.htm)\u003cRegisterOption\u003e 。它存储使用registerOption值的或组合。

**See also** [registerObject](qdbusconnection.html#registerObject)（ ）[QDBusAbstractAdaptor](qdbusabstractadaptor.html)和[Using adaptors](index.htm)。

```
QDBusConnection.UnregisterMode
```

该模式用于注销一个对象路径：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBusConnection.UnregisterNode` | `0` | 注销这个节点只有：不取消注册子对象 |
| `QDBusConnection.UnregisterTree` | `1` | 注销此节点及其所有子树 |

但是请注意，如果该对象被注册了[ExportChildObjects](qdbusconnection.html#RegisterOption-enum)选项， UnregisterNode将注销子对象了。

* * *

## Method Documentation

```
QDBusConnection.__init__ (self, QString name)
```

创建[QDBusConnection](qdbusconnection.html)附加到名称与连接对象_name_。

这不打开连接。你必须调用[connectToBus](qdbusconnection.html#connectToBus)（）将其打开。

```
QDBusConnection.__init__ (self, QDBusConnection other)
```

创建的副本_other_连接。

```
QDBusPendingCall QDBusConnection.asyncCall (self, QDBusMessage message, int timeout = -1)
```

[](qdbuspendingcall.html)

[发送_message_在紧接该连接并返回。此功能适用于方法只调用。它返回类型的对象](qdbuspendingcall.html)[QDBusPendingCall](qdbuspendingcall.html)它可以被用来跟踪应答的状态。

如果没有答复内收到_timeout_毫秒为单位，自动误差将交付指示呼叫期满。默认_timeout_是-1，这将被替换为一个实现定义的值，是适合进程间通信（通常25秒） 。此超时也是在等待QDBusPendingCall.waitForFinished （ ）的上限。

请参阅[QDBusInterface.asyncCall](qdbusabstractinterface.html#asyncCall)（ ）函数用于发出呼叫的一个更友好的方式。

此功能被引入Qt的4.5 。

```
QString QDBusConnection.baseService (self)
```

返回此连接的唯一连接的名称，如果这[QDBusConnection](qdbusconnection.html)对象连接，或空[QString](qstring.html)否则。

唯一的连接名称是一个字符串形式“ ： x.xxx ” （其中x是十进制数字） ，是由D-Bus的服务器守护程序在连接时分配。它唯一标识此客户端的总线。

这个函数返回一个空的[QString](qstring.html)为对等连接。

```
QDBusMessage QDBusConnection.call (self, QDBusMessage message, QDBus.CallMode mode = QDBus.Block, int timeout = -1)
```

[](qdbusmessage.html)

[发送_message_在这方面，板块，等待答复，顶多_timeout_毫秒。此功能适用于方法只调用。它返回的应答消息作为它的返回值，这将是两种类型的](qdbusmessage.html)[QDBusMessage.ReplyMessage](qdbusmessage.html#MessageType-enum) or [QDBusMessage.ErrorMessage](qdbusmessage.html#MessageType-enum)。

如果没有答复内收到_timeout_毫秒为单位，自动误差将交付指示呼叫期满。默认_timeout_是-1，这将被替换为一个实现定义的值，是适合进程间通信（通常25秒） 。

请参阅[QDBusInterface.call](qdbusabstractinterface.html#call)（ ）函数用于发出呼叫的一个更友好的方式。

**Warning:** If _mode_ is [QDBus.BlockWithGui](qdbus.html#CallMode-enum)，此功能将重新进入，以等待答复Qt的事件循环。在等待期间，它可能会带来信号和其他方法调用您的应用程序。因此，它必须准备处理重入每当一个呼叫被置于与（）的调用。

```
bool QDBusConnection.callWithCallback (self, QDBusMessage message, QObject receiver, SLOT() returnMethod, SLOT() errorMethod, int timeout = -1)
```

发送_message_在紧接该连接并返回。当应答被接收时，该方法_returnMethod_被称为在_receiver_对象。如果发生错误，则该方法_errorMethod_将被调用来代替。

如果没有答复内收到_timeout_毫秒为单位，自动误差将交付指示呼叫期满。默认_timeout_是-1，这将被替换为一个实现定义的值，是适合进程间通信（通常25秒） 。

此功能适用于方法只调用。这是保证的时隙将被调用一次的答复，只要在参数类型匹配，并且不会发生错误。

返回True如果消息被发送，或假，如果无法发送邮件。

```
object QDBusConnection.callWithCallback (self, QDBusMessage message, callable returnMethod, callable errorMethod, int timeout = -1)
```

此功能已被弃用。

这是一个重载函数。

发送_message_在紧接该连接并返回。当应答被接收时，该方法_returnMethod_被称为在_receiver_对象。

此功能适用于方法只调用。这是保证的时隙将被调用一次的答复，只要在参数类型匹配，并且不会发生错误。

这个函数是危险的，因为它不能报告错误，包括超时期满。

返回True如果消息被发送，或假，如果无法发送邮件。

```
bool QDBusConnection.callWithCallback (self, QDBusMessage message, QObject receiver, SLOT() slot, int timeout = -1)
```

```
object QDBusConnection.callWithCallback (self, QDBusMessage message, callable slot, int timeout = -1)
```

```
bool QDBusConnection.connect (self, QString service, QString path, QString interface, QString name, QObject receiver, SLOT() slot)
```

连接由指定的信号_service_，_path_，_interface_和_name_参数到槽_slot_在对象_receiver_。该参数_service_和_path_可以为空，表示到的（任何信号的连接_interface_，_name_）对，从任何远程应用程序。

返回True如果连接成功。

**Warning:**该信号将只被传递到时隙，如果参数匹配。该验证可以做到在接收到信号，只有当，而不是在连接时间。

```
object QDBusConnection.connect (self, QString service, QString path, QString interface, QString name, callable slot)
```

这是一个重载函数。

该信号连接到槽_slot_在对象_receiver_。不同于以往的[connect](qdbusconnection.html#connect)（）过载时，此功能允许一个使用指定参数签名要连接的_signature_变量。该函数将验证这个签名可以传送到指定的插槽由_slot_并返回，否则返回False 。

返回True如果连接成功。

**Note:**此功能验证信号的签名相匹配的插槽的参数，但它不会验证与远程服务给定的签名存在的实际信号。

```
bool QDBusConnection.connect (self, QString service, QString path, QString interface, QString name, QString signature, QObject receiver, SLOT() slot)
```

这是一个重载函数。

该信号连接到槽_slot_在对象_receiver_。不同于以往的[connect](qdbusconnection.html#connect)（）过载时，此功能允许一个使用指定参数签名要连接的_signature_变量。该函数将验证这个签名可以传送到指定的插槽由_slot_并返回，否则返回False 。

该_argumentMatch_参数列出了要匹配的字符串参数，按顺序。需要注意的是，要匹配一个空字符串，你需要传递一个[QString](qstring.html)那是空的，但不为空（即，[QString](qstring.html)（“” ））。空[QString](qstring.html)跳过该位置匹配。

返回True如果连接成功。

**Note:**此功能验证信号的签名相匹配的插槽的参数，但它不会验证与远程服务给定的签名存在的实际信号。

此功能被引入Qt的4.6 。

```
object QDBusConnection.connect (self, QString service, QString path, QString interface, QString name, QString signature, callable slot)
```

```
bool QDBusConnection.connect (self, QString service, QString path, QString interface, QString name, QStringList argumentMatch, QString signature, QObject receiver, SLOT() slot)
```

```
object QDBusConnection.connect (self, QString service, QString path, QString interface, QString name, QStringList argumentMatch, QString signature, callable slot)
```

```
ConnectionCapabilities QDBusConnection.connectionCapabilities (self)
```

[](index.htm)

[返回此连接的能力，谈判与总线的服务器或对等。如果这](index.htm)[QDBusConnection](qdbusconnection.html)没有连接，这个函数没有返回的能力。

此功能被引入Qt的4.8 。

```
QDBusConnection QDBusConnection.connectToBus (BusType type, QString name)
```

[](qdbusconnection.html)

[打开型的连接_type_对已知的总线和联营公司与它的连接名称中的一个_name_。返回](qdbusconnection.html)[QDBusConnection](qdbusconnection.html)与该连接相关联的对象。

```
QDBusConnection QDBusConnection.connectToBus (QString address, QString name)
```

[](qdbusconnection.html)

[打开上的地址到私有总线的连接_address_和与它相关联的连接名称_name_。返回](qdbusconnection.html)[QDBusConnection](qdbusconnection.html)与该连接相关联的对象。

```
QDBusConnection QDBusConnection.connectToPeer (QString address, QString name)
```

[](qdbusconnection.html)

[打开上地址的对等连接_address_和与它相关联的连接名称_name_。返回](qdbusconnection.html)[QDBusConnection](qdbusconnection.html)与该连接相关联的对象。

此功能被引入Qt的4.8 。

```
bool QDBusConnection.disconnect (self, QString service, QString path, QString interface, QString name, QObject receiver, SLOT() slot)
```

断开由指定的信号_service_，_path_，_interface_和_name_从槽参数_slot_在对象_receiver_。作为传递给该参数必须相同[connect](qdbusconnection.html#connect)（）函数。

返回True如果断开成功。

```
object QDBusConnection.disconnect (self, QString service, QString path, QString interface, QString name, callable slot)
```

这是一个重载函数。

断开由指定的信号_service_，_path_，_interface_，_name_和_signature_从槽参数_slot_在对象_receiver_。作为传递给该参数必须相同[connect](qdbusconnection.html#connect)（）函数。

返回True如果断开成功。

```
bool QDBusConnection.disconnect (self, QString service, QString path, QString interface, QString name, QString signature, QObject receiver, SLOT() slot)
```

这是一个重载函数。

断开由指定的信号_service_，_path_，_interface_，_name_，_argumentMatch_和_signature_从槽参数_slot_在对象_receiver_。作为传递给该参数必须相同[connect](qdbusconnection.html#connect)（）函数。

返回True如果断开成功。

此功能被引入Qt的4.6 。

```
object QDBusConnection.disconnect (self, QString service, QString path, QString interface, QString name, QString signature, callable slot)
```

```
bool QDBusConnection.disconnect (self, QString service, QString path, QString interface, QString name, QStringList argumentMatch, QString signature, QObject receiver, SLOT() slot)
```

```
object QDBusConnection.disconnect (self, QString service, QString path, QString interface, QString name, QStringList argumentMatch, QString signature, callable slot)
```

```
QDBusConnection.disconnectFromBus (QString name)
```

关闭的名字总线连接_name_。

需要注意的是，如果仍有[QDBusConnection](qdbusconnection.html)使用相同的连接相关联的对象，该连接不会被关闭，直到所有引用都将被丢弃。但是，可以使用创建没有进一步的引用[QDBusConnection](qdbusconnection.html)构造函数。

```
QDBusConnection.disconnectFromPeer (QString name)
```

关闭的名义对等连接_name_。

需要注意的是，如果仍有[QDBusConnection](qdbusconnection.html)使用相同的连接相关联的对象，该连接不会被关闭，直到所有引用都将被丢弃。但是，可以使用创建没有进一步的引用[QDBusConnection](qdbusconnection.html)构造函数。

此功能被引入Qt的4.8 。

```
QDBusConnectionInterface QDBusConnection.interface (self)
```

[](qdbusconnectioninterface.html)

[返回](qdbusconnectioninterface.html)[QDBusConnectionInterface](qdbusconnectioninterface.html)对象，表示该连接的D-Bus的服务器接口。

```
bool QDBusConnection.isConnected (self)
```

返回True如果[QDBusConnection](qdbusconnection.html)对象连接。

```
QDBusError QDBusConnection.lastError (self)
```

[

返回所发生的这方面的最后一个错误。

](qdbuserror.html)

[该功能提供了低级别的代码。如果你使用](qdbuserror.html)[QDBusInterface.call](qdbusabstractinterface.html#call)（ ） ，错误代码是报告它的返回值。

**See also** [QDBusInterface](qdbusinterface.html)和[QDBusMessage](qdbusmessage.html)。

```
QByteArray QDBusConnection.localMachineId ()
```

[

返回已知的D -Bus系统在本地机器的ID 。运行的D-总线的每个节点或主机具有一个唯一的标识符，该标识符可用于从其它主机相区别，如果它们共享资源，如文件系统。

注意，在本地机器ID不保证是整个系统的靴子持久的，所以该标识符不应该被存储在持久性存储器（例如文件系统） 。它是保证只有在此引导会话的生命周期保持不变。

此功能被引入Qt的4.8 。

```
QString QDBusConnection.name (self)
```

](qbytearray.html)

[返回连接名称为这个连接，给出name参数来](qbytearray.html)[connectToBus](qdbusconnection.html#connectToBus)（ ） 。

连接名称可以用来唯一标识实际的底层连接到总线。从一个单一的连接制作的复制品总是隐含共享底层的连接，从而将具有相同的连接名称。

相反，两种连接方式具有不同的连接名称将永远既可以连接到不同的总线，或有不同的唯一的名称（如返回的[baseService](qdbusconnection.html#baseService)（ ） ）的总线上。

此功能被引入Qt的4.5 。

**See also** [connectToBus](qdbusconnection.html#connectToBus)（）和[disconnectFromBus](qdbusconnection.html#disconnectFromBus)（ ） 。

```
QObject QDBusConnection.objectRegisteredAt (self, QString path)
```

[](qobject.html)

[返回注册到该对象](qobject.html)[registerObject](qdbusconnection.html#registerObject)（ ）由给定的对象路径_path_。

```
bool QDBusConnection.registerObject (self, QString path, QObject object, RegisterOptions options = QDBusConnection.ExportAdaptors)
```

登记对象_object_在路径_path_如果注册成功则返回True。该_options_参数指定了对象_object_将通过D-Bus的暴露。

此功能不会取代现有的对象：如果有已经在路径注册的对象_path_，这个函数将返回False 。使用[unregisterObject](qdbusconnection.html#unregisterObject)（ ）先注销它。

你不能注册的对象为已注册的对象的子对象[QDBusConnection.ExportChildObjects](qdbusconnection.html#RegisterOption-enum)。

```
bool QDBusConnection.registerService (self, QString serviceName)
```

尝试注册_serviceName_在D-Bus的服务器上，如果注册成功则返回True 。如果该名称已被其他应用程序的注册将失败。

**See also** [unregisterService](qdbusconnection.html#unregisterService)（）和[QDBusConnectionInterface.registerService](qdbusconnectioninterface.html#registerService)（ ） 。

```
bool QDBusConnection.send (self, QDBusMessage message)
```

发送_message_在这方面，没有等待答复。本品适用于错误，信号和返回值，以及调用的返回值是没有必要的。

返回True如果消息被排队成功，否则返回False。

```
QDBusConnection QDBusConnection.sender ()
```

[](qdbusconnection.html)

[返回发送的信号的连接，如果在调用通过激活一个时隙](qdbusconnection.html)[QDBus](qdbus.html)，否则返回0 。

**Note:**请避免此功能。这个函数不是线程安全的，所以如果有任何其他线程提供一个D-Bus的调用，此函数可能返回错误的连接。在新的代码，请用[QDBusContext.connection](index.htm#connection)（ ） （请参阅类关于如何使用它的描述） 。

**Warning:**此功能不[reentrant](index.htm#reentrant)。

```
QDBusConnection QDBusConnection.sessionBus ()
```

[](qdbusconnection.html)

[返回](qdbusconnection.html)[QDBusConnection](qdbusconnection.html)对象打开与会话总线。这个函数返回的对象引用是有效的，直到应用程序终止，在这一点上的连接将被关闭和删除对象。

```
QDBusConnection QDBusConnection.systemBus ()
```

[](qdbusconnection.html)

[返回](qdbusconnection.html)[QDBusConnection](qdbusconnection.html)打开对象与系统总线。这个函数返回的对象引用是有效的，直到[QCoreApplication](qcoreapplication.html)的析构函数被执行，当连接将被关闭和对象，删除。

```
QDBusConnection.unregisterObject (self, QString path, UnregisterMode mode = QDBusConnection.UnregisterNode)
```

注销注册到一个对象[registerObject](qdbusconnection.html#registerObject)（ ）由给定的对象路径_path_并且，如果_mode_ is [QDBusConnection.UnregisterTree](qdbusconnection.html#UnregisterMode-enum)，它的所有子对象了。

请注意，您不能注销了未与登记对象[registerObject](qdbusconnection.html#registerObject)（ ） 。

```
bool QDBusConnection.unregisterService (self, QString serviceName)
```

注销服务_serviceName_先前与注册[registerService](qdbusconnection.html#registerService)（ ），如果成功则返回True。

**See also** [registerService](qdbusconnection.html#registerService)（）和[QDBusConnectionInterface.unregisterService](qdbusconnectioninterface.html#unregisterService)（ ） 。