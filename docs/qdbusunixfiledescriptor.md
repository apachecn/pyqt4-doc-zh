# QDBusUnixFileDescriptor Class Reference

## [[QtDBus](index.htm) module]

该QDBusUnixFileDescriptor类各执一份的Unix文件描述符。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, int fileDescriptor)`
*   `__init__ (self, QDBusUnixFileDescriptor other)`
*   `int fileDescriptor (self)`
*   `bool isValid (self)`
*   `setFileDescriptor (self, int fileDescriptor)`

### Static Methods

*   `bool isSupported ()`

* * *

## Detailed Description

该QDBusUnixFileDescriptor类各执一份的Unix文件描述符。

该QDBusUnixFileDescriptor类用于容纳一个Unix的文件描述符与使用[QtDBus](index.htm)模块。这使得应用程序可以自动发送和接收的Unix文件描述符在D-Bus的连接，映射到D -总线类型的“h” 。

也可以使用如在信号和通过用QDBusConnection.registerObject注册得到出口到D-总线时隙参数类型QDBusUnixFileDescriptors的对象。

QDBusUnixFileDescriptor不走文件描述符的所有权。相反，它将使用Unix系统调用`dup(2)`使文件描述符的副本。此文件描述符属于QDBusUnixFileDescriptor对象，不应该被存储或由用户关闭。相反，你应该让自己的副本，如果你需要的。

#### Availability

Unix的文件描述符的逝世是不是适用于所有的D-Bus连接。此功能目前与D-Bus的图书馆和总线守护程序版本1.4及以上的Unix系统。[QtDBus](index.htm)自动启用该功能，如果这样的版本被发现在编译时和运行时。

要验证您的连接不支持通过文件描述符，检查[QDBusConnection.UnixFileDescriptorPassing](qdbusconnection.html#ConnectionCapability-enum)功能设置与[QDBusConnection.connectionCapabilities](qdbusconnection.html#connectionCapabilities)（ ） 。如果标志不活跃，那么你将无法做出有QDBusUnixFileDescriptor作为参数，甚至在一个变体中嵌入这种类型的调用方法。您也不会收到包含该类型的呼叫。

另请注意，远程应用程序可能无法让Unix文件描述符传递的支持。如果你犯了一个D-Bus的到无法接受这样一种类型的远程应用程序，您将收到一条错误的答复。如果您尝试发送一个含有D-Bus的文件描述符的信号，或从一个方法调用返回之一，该消息将被丢弃。

即使功能不可用， QDBusUnixFileDescriptor将继续运行，所以代码不需要有编译时检查此功能的可用性。

在非Unix系统， QDBusUnixFileDescriptor将始终报告无效状态，[QDBusUnixFileDescriptor.isSupported](qdbusunixfiledescriptor.html#isSupported)（ ）将返回False 。

* * *

## Method Documentation

```
QDBusUnixFileDescriptor.__init__ (self)
```

构造一个[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)没有包装的文件描述符。这等效于一个无效的文件描述符（如-1）构成的对象。

**See also** [fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（）和[isValid](qdbusunixfiledescriptor.html#isValid)（ ） 。

```
QDBusUnixFileDescriptor.__init__ (self, int fileDescriptor)
```

构造一个[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)通过复制的对象_fileDescriptor_参数。原始文件的描述符是不被用户触摸并必须关闭。

请注意，返回的值由[fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（）将来自不同_fileDescriptor_参数传递。

如果_fileDescriptor_参数是无效的，[isValid](qdbusunixfiledescriptor.html#isValid)（ ）将返回False，[fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（ ）将返回-1 。

**See also** [setFileDescriptor](qdbusunixfiledescriptor.html#setFileDescriptor)（）和[fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（ ） 。

```
QDBusUnixFileDescriptor.__init__ (self, QDBusUnixFileDescriptor other)
```

构造一个[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)通过复制对象_other_。

```
int QDBusUnixFileDescriptor.fileDescriptor (self)
```

返回包含此Unix的文件描述符[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)对象。无效的文件描述符由值-1表示。

请注意，这个函数返回的文件描述符是由拥有[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)对象，并且必须不被保存过去的这个对象的生存期。它是确定使用它，而这个对象是有效的，但如果一个人想存放更长的使用，文件描述符应使用Unix的克隆`dup(2)`，`dup2(2)` or `dup3(2)`功能。

**See also** [setFileDescriptor](qdbusunixfiledescriptor.html#setFileDescriptor)（）和[isValid](qdbusunixfiledescriptor.html#isValid)（ ） 。

```
bool QDBusUnixFileDescriptor.isSupported ()
```

如果在Unix文件描述符都在这个平台上支持，则返回True 。换句话说，该函数返回True，如果这是一个Unix平台上。

需要注意的是[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)继续运行，即使这个函数返回False 。唯一的区别在于[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)对象将始终处于[isValid](qdbusunixfiledescriptor.html#isValid)（ ） == False状态和[fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（ ）将总是返回-1 。本课程将不消耗任何作业系统资源。

```
bool QDBusUnixFileDescriptor.isValid (self)
```

返回True如果Unix的文件描述符是有效的。一个有效的Unix文件描述符不是-1 。

**See also** [fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（ ） 。

```
QDBusUnixFileDescriptor.setFileDescriptor (self, int fileDescriptor)
```

设置文件描述符，这[QDBusUnixFileDescriptor](qdbusunixfiledescriptor.html)对象保存到副本_fileDescriptor_。原始文件的描述符是不被用户触摸并必须关闭。

请注意，返回的值由[fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（）将来自不同_fileDescriptor_参数传递。

如果_fileDescriptor_参数是无效的，[isValid](qdbusunixfiledescriptor.html#isValid)（ ）将返回False，[fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（ ）将返回-1 。

**See also** [isValid](qdbusunixfiledescriptor.html#isValid)（）和[fileDescriptor](qdbusunixfiledescriptor.html#fileDescriptor)（ ） 。