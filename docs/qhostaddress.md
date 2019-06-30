# QHostAddress Class Reference

## [[QtNetwork](index.htm) module]

该QHostAddress类提供一个IP地址。[More...](#details)

### Types

*   `enum SpecialAddress { Null, Broadcast, LocalHost, LocalHostIPv6, AnyIPv6, Any }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, SpecialAddress address)`
*   `__init__ (self, int ip4Addr)`
*   `__init__ (self, QString address)`
*   `__init__ (self, 16-tuple-of-int ip6Addr)`
*   `__init__ (self, QHostAddress copy)`
*   `clear (self)`
*   `bool isInSubnet (self, QHostAddress subnet, int netmask)`
*   `bool isInSubnet (self, tuple-of-QHostAddress-int subnet)`
*   `bool isNull (self)`
*   `QAbstractSocket.NetworkLayerProtocol protocol (self)`
*   `QString scopeId (self)`
*   `setAddress (self, int ip4Addr)`
*   `bool setAddress (self, QString address)`
*   `setAddress (self, 16-tuple-of-int ip6Addr)`
*   `setScopeId (self, QString id)`
*   `int toIPv4Address (self)`
*   `16-tuple-of-int toIPv6Address (self)`
*   `QString toString (self)`

### Static Methods

*   `tuple-of-QHostAddress-int parseSubnet (QString subnet)`

### Special Methods

*   `bool __eq__ (self, QHostAddress address)`
*   `bool __eq__ (self, SpecialAddress address)`
*   `int __hash__ (self)`
*   `bool __ne__ (self, QHostAddress address)`
*   `bool __ne__ (self, SpecialAddress address)`

* * *

## Detailed Description

该QHostAddress类提供一个IP地址。

此类包含IPv4或IPv6地址在一个平台和协议无关的方式。

QHostAddress通常与所使用的[QTcpSocket](qtcpsocket.html)，[QTcpServer](qtcpserver.html)和[QUdpSocket](qudpsocket.html)连接到主机或设立一个服务器。

主机地址设置与[setAddress](qhostaddress.html#setAddress)（） ，并检索与[toIPv4Address](qhostaddress.html#toIPv4Address)（ ）[toIPv6Address](qhostaddress.html#toIPv6Address)（） ，或[toString](qhostaddress.html#toString)（ ） 。您可以检查与类型[protocol](qhostaddress.html#protocol)（ ） 。

**Note:**请注意， QHostAddress没有做DNS查找。[QHostInfo](qhostinfo.html)是需要这一点。

该类还支持常见的预定义的地址：[Null](qhostaddress.html#SpecialAddress-enum)，[LocalHost](qhostaddress.html#SpecialAddress-enum)，[LocalHostIPv6](qhostaddress.html#SpecialAddress-enum)，[Broadcast](qhostaddress.html#SpecialAddress-enum)和[Any](qhostaddress.html#SpecialAddress-enum)。

* * *

## Type Documentation

```
QHostAddress.SpecialAddress
```

| Constant | Value | Description |
| --- | --- | --- |
| `QHostAddress.Null` | `0` | 空地址的对象。相当于[QHostAddress](qhostaddress.html#QHostAddress)（ ） 。 |
| `QHostAddress.LocalHost` | `2` | 在本地主机的IPv4地址。相当于[QHostAddress](qhostaddress.html)（ “127.0.0.1” ） 。 |
| `QHostAddress.LocalHostIPv6` | `3` | IPv6的本地主机地址。相当于[QHostAddress](qhostaddress.html)（ “.1” ） 。 |
| `QHostAddress.Broadcast` | `1` | IPv4的广播地址。相当于[QHostAddress](qhostaddress.html)（ “255.255.255.255” ） 。 |
| `QHostAddress.Any` | `4` | IPv4的任何地址。相当于[QHostAddress](qhostaddress.html)（ “0.0.0.0” ） 。 |
| `QHostAddress.AnyIPv6` | `5` | IPv6的任何地址。相当于[QHostAddress](qhostaddress.html)（ “[.](index.html)“ ） 。 |

* * *

## Method Documentation

```
QHostAddress.__init__ (self)
```

构造一个主机地址对象的IP地址为0.0.0.0 。

**See also** [clear](qhostaddress.html#clear)（ ） 。

```
QHostAddress.__init__ (self, SpecialAddress address)
```

构造一个主机地址对象的IPv4地址_ip4Addr_。

```
QHostAddress.__init__ (self, int ip4Addr)
```

构造一个主机地址对象的IPv6地址_ip6Addr_。

_ip6Addr_必须是网络字节顺序（大端）一个16字节的数组。

```
QHostAddress.__init__ (self, QString address)
```

构造一个主机地址对象的IPv6地址_ip6Addr_。

```
QHostAddress.__init__ (self, 16-tuple-of-int ip6Addr)
```

构造使用由天然结构中指定的地址的IPv4或IPv6地址_sockaddr_。

**See also** [setAddress](qhostaddress.html#setAddress)（ ） 。

```
QHostAddress.__init__ (self, QHostAddress copy)
```

构建了基于字符串的IPv4或IPv6地址_address_（例如， “127.0.0.1” ） 。

**See also** [setAddress](qhostaddress.html#setAddress)（ ） 。

```
QHostAddress.clear (self)
```

设置主机地址为0.0.0.0 。

```
bool QHostAddress.isInSubnet (self, QHostAddress subnet, int netmask)
```

返回True如果这个IP是由网络前缀描述的子网_subnet_和网络掩码_netmask_。

一个IP被认为是属于一个子网，如果它包含的最低和该子网中的最高地址。在IP版本4的情况下，最低的地址是网络地址，而最高地址是广播地址。

该_subnet_参数并不一定是实际的网络地址（子网中的最低地址） 。它可以是属于该子网的任何有效的IP地址。特别是，如果它等于通过这个对象持有的IP地址，这个函数将始终返回True （所提供的网络掩码是一个有效的值） 。

此功能被引入Qt的4.5 。

**See also** [parseSubnet](qhostaddress.html#parseSubnet)（ ） 。

```
bool QHostAddress.isInSubnet (self, tuple-of-QHostAddress-int subnet)
```

这是一个重载函数。

返回True如果这个IP是由描述的子网_subnet_。该[QHostAddress](qhostaddress.html)成员_subnet_包含网络前缀和整数（二）成员包含子网掩码（前缀长度） 。

此功能被引入Qt的4.5 。

```
bool QHostAddress.isNull (self)
```

返回True如果主机地址为空（ INADDR_ANY或IN6ADDR_ANY ） 。默认的构造函数创建一个空的地址，该地址是无效的任何主机或接口。

```
tuple-of-QHostAddress-int QHostAddress.parseSubnet (QString subnet)
```

解析包含在IP和子网信息_subnet_并返回网络前缀的网络前缀长度。

IP地址和网络掩码必须以斜杠（ / ）分隔。

此功能支持形式参数：

*   123.123.123.123/n where n is any value between 0 and 32
*   123.123.123.123/255.255.255.255
*   &lt;ipv6-address&gt;/n where n is any value between 0 and 128

对于IP版本4 ，这个函数接受以及缺少结尾的部分（即，小于4个字节，如“ 192.168.1 ” ），其次或不点。如果子网掩码也在这种情况下丢失，它被设置为实际传递的字节数（在上面的例子中，这将是24 ，为3个八比特组） 。

此功能被引入Qt的4.5 。

**See also** [isInSubnet](qhostaddress.html#isInSubnet)（ ） 。

```
QAbstractSocket.NetworkLayerProtocol QHostAddress.protocol (self)
```

[

返回主机地址中的网络层协议。

```
QString QHostAddress.scopeId (self)
```

](qabstractsocket.html#NetworkLayerProtocol-enum)

[返回一个IPv6地址的范围ID 。对于IPv4地址，或者地址不包含范围ID ，一个空](qabstractsocket.html#NetworkLayerProtocol-enum)[QString](qstring.html)返回。

IPv6的范围ID指定的范围_reachability_对于非全局IPv6地址，限制在其中的地址可使用的区域。所有的IPv6地址与这样的可达范围有关。范围ID被用来消除那些不能保证是全局唯一的地址。

的IPv6指定了以下四个层次的可达性：

*   Node-local: Addresses that are only used for communicating with services on the same interface (e.g., the loopback interface ".1").
*   Link-local: Addresses that are local to the network interface (_link_). There is always one link-local address for each IPv6 interface on your host. Link-local addresses ("fe80...") are generated from the MAC address of the local network adaptor, and are not guaranteed to be unique.
*   Site-local: Addresses that are local to the site / private network (e.g., the company intranet). Site-local addresses ("fec0...") are usually distributed by the site router, and are not guaranteed to be unique outside of the local site.
*   Global: For globally routable addresses, such as public servers on the Internet.

当使用链路本地和站点本地地址的IPv6连接，则必须指定范围ID 。一个链路本地地址的范围ID通常是相同的接口名称（例如，“ eth0的” ， “ EN1 ” ）或数字（例如， “ 1 ” ， “2” ） 。

这个函数是Qt 4.1中引入。

**See also** [setScopeId](qhostaddress.html#setScopeId)（ ） 。

```
QHostAddress.setAddress (self, int ip4Addr)
```

通过设置指定的IPv4地址_ip4Addr_。

```
bool QHostAddress.setAddress (self, QString address)
```

这是一个重载函数。

通过设置指定的IPv6地址_ip6Addr_。

_ip6Addr_必须是网络字节顺序（高位字节在前） 16字节的数组。

```
QHostAddress.setAddress (self, 16-tuple-of-int ip6Addr)
```

这是一个重载函数。

通过设置指定的IPv6地址_ip6Addr_。

```
QHostAddress.setScopeId (self, QString id)
```

设置地址的IPv6范围ID来_id_。如果地址协议是不支持IPv6 ，这个函数不执行任何操作。

这个函数是Qt 4.1中引入。

**See also** [scopeId](qhostaddress.html#scopeId)（ ） 。

```
int QHostAddress.toIPv4Address (self)
```

返回的IPv4地址为一个数字。

例如，如果地址是127.0.0.1 ，则返回值是2130706433 （即0x7f000001 ） 。

此值才有效，如果该协议（ ）是[IPv4Protocol](qabstractsocket.html#NetworkLayerProtocol-enum)。

**See also** [toString](qhostaddress.html#toString)（ ） 。

```
16-tuple-of-int QHostAddress.toIPv6Address (self)
```

返回IPv6地址作为Q_IPV6ADDR结构。该结构由16位无符号的字符。

```
 Q_IPV6ADDR addr = hostAddr.toIPv6Address();
 // addr contains 16 unsigned characters

 for (int i = 0; i < 16; ++i) {
     // process addr[i]
 }

```

此值才有效，如果[protocol](qhostaddress.html#protocol)（）是[IPv6Protocol](qabstractsocket.html#NetworkLayerProtocol-enum)。

**See also** [toString](qhostaddress.html#toString)（ ） 。

```
QString QHostAddress.toString (self)
```

返回该地址为一个字符串。

例如，如果该地址是IPv4地址127.0.0.1 ，则返回的字符串为“ 127.0.0.1” 。对于IPv6的字符串格式将遵循RFC5952建议。

**See also** [toIPv4Address](qhostaddress.html#toIPv4Address)（ ） 。

```
bool QHostAddress.__eq__ (self, QHostAddress address)
```

```
bool QHostAddress.__eq__ (self, SpecialAddress address)
```

```
int QHostAddress.__hash__ (self)
```

```
bool QHostAddress.__ne__ (self, QHostAddress address)
```

```
bool QHostAddress.__ne__ (self, SpecialAddress address)
```