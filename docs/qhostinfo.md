# QHostInfo Class Reference

## [[QtNetwork](index.htm) module]

该QHostInfo类提供静态函数为主机名查找。[More...](#details)

### Types

*   `enum HostInfoError { NoError, HostNotFound, UnknownError }`

### Methods

*   `__init__ (self, int id = -1)`
*   `__init__ (self, QHostInfo d)`
*   `list-of-QHostAddress addresses (self)`
*   `HostInfoError error (self)`
*   `QString errorString (self)`
*   `QString hostName (self)`
*   `int lookupId (self)`
*   `setAddresses (self, list-of-QHostAddress addresses)`
*   `setError (self, HostInfoError error)`
*   `setErrorString (self, QString errorString)`
*   `setHostName (self, QString name)`
*   `setLookupId (self, int id)`

### Static Methods

*   `abortHostLookup (int lookupId)`
*   `QHostInfo fromName (QString name)`
*   `QString localDomainName ()`
*   `QString localHostName ()`
*   `int lookupHost (QString name, QObject receiver, SLOT(QHostInfo)SLOT() member)`
*   `int lookupHost (QString name, callable receiver)`

* * *

## Detailed Description

该QHostInfo类提供静态函数为主机名查找。

QHostInfo使用提供的操作系统找到一个主机名，或与IP地址对应的主机名相关的IP地址（ ES ）的查找机制。这个类提供了两个静态的便利功能：一个以异步方式工作，并发出信号，一旦主机被发现，而另一个块，并返回一个QHostInfo对象。

要查找主机的IP地址异步调用[lookupHost](qhostinfo.html#lookupHost)（ ） ，这需要主机名或IP地址，接收对象和槽签名作为参数并返回一个ID 。你可以通过调用中止查询[abortHostLookup](qhostinfo.html#abortHostLookup)（ ）与查找的ID 。

例如：

```
 // To find the IP address of qt.nokia.com
 QHostInfo.lookupHost("qt.nokia.com",
                       this, SLOT(printResults(QHostInfo)));

 // To find the host name for 4.2.2.1
 QHostInfo.lookupHost("4.2.2.1",
                       this, SLOT(printResults(QHostInfo)));

```

该槽被调用时，结果准备就绪。结果被存储在一个QHostInfo对象。通话[addresses](qhostinfo.html#addresses)（ ）来获得主机的IP地址列表，并[hostName](qhostinfo.html#hostName)（）来获取被查找的主机名。

如果查找失败，[error](qhostinfo.html#error)（）返回发生错误的类型。[errorString](qhostinfo.html#errorString)（ ）给出了查找错误的人类可读的描述。

如果你想有一个阻塞的查找，使用[QHostInfo.fromName](qhostinfo.html#fromName)（ ）函数：

```
 QHostInfo info = QHostInfo.fromName("qt.nokia.com");

```

QHostInfo支持国际化域名（IDN ）通过IDNA和Punycode的标准。

检索本地主机的名称，使用静态[QHostInfo.localHostName](qhostinfo.html#localHostName)（）函数。

**Note:**由于Qt的4.6.1 QHostInfo使用多线程进行DNS查询，而不是一个专用的DNS线程。这提高了性能，而且还当使用改变信号的排放顺序[lookupHost](qhostinfo.html#lookupHost)（ ）相比， Qt之前版本。**Note:**由于Qt的4.6.3 QHostInfo使用以提高性能，一个小的内部60秒DNS缓存。

* * *

## Type Documentation

```
QHostInfo.HostInfoError
```

这个枚举描述试图解析主机名时可能出现的各种错误。

| Constant | Value | Description |
| --- | --- | --- |
| `QHostInfo.NoError` | `0` | 该查找是成功的。 |
| `QHostInfo.HostNotFound` | `1` | 未找到主机没有IP地址。 |
| `QHostInfo.UnknownError` | `2` | 发生未知错误。 |

**See also** [error](qhostinfo.html#error)（）和[setError](qhostinfo.html#setError)（ ） 。

* * *

## Method Documentation

```
QHostInfo.__init__ (self, int id = -1)
```

构造一个空的主机信息对象查找的ID_id_。

**See also** [lookupId](qhostinfo.html#lookupId)（ ） 。

```
QHostInfo.__init__ (self, QHostInfo d)
```

构造的副本_other_。

```
QHostInfo.abortHostLookup (int lookupId)
```

中止主机查找的ID_id_，所返回的[lookupHost](qhostinfo.html#lookupHost)（ ） 。

**See also** [lookupHost](qhostinfo.html#lookupHost)（）和[lookupId](qhostinfo.html#lookupId)（ ） 。

```
list-of-QHostAddress QHostInfo.addresses (self)
```

返回与关联的IP地址列表[hostName](qhostinfo.html#hostName)（ ） 。这个列表可能是空的。

例如：

```
 [QHostInfo](qhostinfo.html) info;
 ...
 if (!info.addresses().isEmpty()) {
     [QHostAddress](qhostaddress.html) address = info.addresses().first();
     // use the first IP address
 }

```

**See also** [setAddresses](qhostinfo.html#setAddresses)（ ）[hostName](qhostinfo.html#hostName)（）和[error](qhostinfo.html#error)（ ） 。

```
HostInfoError QHostInfo.error (self)
```

[](qhostinfo.html#HostInfoError-enum)

[返回，如果主机名查找失败时发生错误的类型，否则返回](qhostinfo.html#HostInfoError-enum)[NoError](qhostinfo.html#HostInfoError-enum)。

**See also** [setError](qhostinfo.html#setError)（）和[errorString](qhostinfo.html#errorString)（ ） 。

```
QString QHostInfo.errorString (self)
```

如果查找失败，则此函数返回错误的人类可读的描述;否则返回“未知错误” 。

**See also** [setErrorString](qhostinfo.html#setErrorString)（）和[error](qhostinfo.html#error)（ ） 。

```
QHostInfo QHostInfo.fromName (QString name)
```

[](qhostinfo.html)

[对于给定的主机查找IP地址（ ES ）_name_。查找这意味着在程序执行过程中的功能块被挂起，直到查找的结果是准备好了。返回在该查询的结果](qhostinfo.html)[QHostInfo](qhostinfo.html)对象。

如果你传递一个文字IP地址_name_而不是一个主机名，[QHostInfo](qhostinfo.html)将搜索的域名为IP （即，[QHostInfo](qhostinfo.html)将执行_reverse_查找） 。如果成功，则返回[QHostInfo](qhostinfo.html)将包含解析域名和IP地址的主机名。

**See also** [lookupHost](qhostinfo.html#lookupHost)（ ） 。

```
QString QHostInfo.hostName (self)
```

返回主机的IP地址进行查找时的名称。

**See also** [setHostName](qhostinfo.html#setHostName)（）和[localHostName](qhostinfo.html#localHostName)（ ） 。

```
QString QHostInfo.localDomainName ()
```

返回本机的DNS域。

注： DNS域是不相关的，在Windows网络中存在的域名。

**See also** [hostName](qhostinfo.html#hostName)（ ） 。

```
QString QHostInfo.localHostName ()
```

返回本机的主机名。

**See also** [hostName](qhostinfo.html#hostName)（ ） 。

```
int QHostInfo.lookupHost (QString name, QObject receiver, SLOT(QHostInfo)SLOT() member)
```

查找与主机名相关的IP地址（ ES ）_name_，并返回查找的ID。当查找的结果是准备好了，槽或信号_member_在_receiver_被称为一个[QHostInfo](qhostinfo.html)的说法。该[QHostInfo](qhostinfo.html)对象可以被检查，以得到该查找的结果。

该查找是一个函数调用，例如执行：

```
 [QHostInfo](qhostinfo.html).lookupHost("www.kde.org",
                       this, SLOT(lookedUp([QHostInfo](qhostinfo.html))));

```

槽的实施打印有关的查询返回的地址的基本信息，或报告，如果它失败的错误：

```
 void MyWidget.lookedUp(const [QHostInfo](qhostinfo.html) &host)
 {
     if (host.error() != [QHostInfo](qhostinfo.html).NoError) {
         qDebug() << "Lookup failed:" << host.errorString();
         return;
     }

     foreach (const [QHostAddress](qhostaddress.html) &address, host.addresses())
         qDebug() << "Found address:" << address.toString();
 }

```

如果你传递一个文字IP地址_name_而不是一个主机名，[QHostInfo](qhostinfo.html)将搜索的域名为IP （即，[QHostInfo](qhostinfo.html)将执行_reverse_查找） 。上的成功，将所得[QHostInfo](qhostinfo.html)将包含解析域名和IP地址的主机名。例如：

```
 [QHostInfo](qhostinfo.html).lookupHost("4.2.2.1",
                       this, SLOT(lookedUp([QHostInfo](qhostinfo.html))));

```

**Note:**有没有保证，如果你开始的多个请求与lookupHost （ ）的信号将被发出的顺序。

**See also** [abortHostLookup](qhostinfo.html#abortHostLookup)（ ）[addresses](qhostinfo.html#addresses)（ ）[error](qhostinfo.html#error)（）和[fromName](qhostinfo.html#fromName)（ ） 。

```
int QHostInfo.lookupHost (QString name, callable receiver)
```

```
int QHostInfo.lookupId (self)
```

返回此查询的ID 。

**See also** [setLookupId](qhostinfo.html#setLookupId)（ ）[abortHostLookup](qhostinfo.html#abortHostLookup)（）和[hostName](qhostinfo.html#hostName)（ ） 。

```
QHostInfo.setAddresses (self, list-of-QHostAddress addresses)
```

设置在该地址列表[QHostInfo](qhostinfo.html)至_addresses_。

**See also** [addresses](qhostinfo.html#addresses)（ ） 。

```
QHostInfo.setError (self, HostInfoError error)
```

设置这种错误类型[QHostInfo](qhostinfo.html)至_error_。

**See also** [error](qhostinfo.html#error)（）和[errorString](qhostinfo.html#errorString)（ ） 。

```
QHostInfo.setErrorString (self, QString errorString)
```

设置错误的发生，以人类可读的描述_str_如果查找失败。

**See also** [errorString](qhostinfo.html#errorString)（）和[setError](qhostinfo.html#setError)（ ） 。

```
QHostInfo.setHostName (self, QString name)
```

设置该主机名[QHostInfo](qhostinfo.html)至_hostName_。

**See also** [hostName](qhostinfo.html#hostName)（ ） 。

```
QHostInfo.setLookupId (self, int id)
```

设置此查询的ID_id_。

**See also** [lookupId](qhostinfo.html#lookupId)（）和[lookupHost](qhostinfo.html#lookupHost)（ ） 。