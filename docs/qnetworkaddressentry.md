# QNetworkAddressEntry Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkAddressEntry类存储一个IP地址，通过网络接口支持，连同其相关联的网络掩码和广播地址。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QNetworkAddressEntry other)`
*   `QHostAddress broadcast (self)`
*   `QHostAddress ip (self)`
*   `QHostAddress netmask (self)`
*   `int prefixLength (self)`
*   `setBroadcast (self, QHostAddress newBroadcast)`
*   `setIp (self, QHostAddress newIp)`
*   `setNetmask (self, QHostAddress newNetmask)`
*   `setPrefixLength (self, int length)`

### Special Methods

*   `bool __eq__ (self, QNetworkAddressEntry other)`
*   `bool __ne__ (self, QNetworkAddressEntry other)`

* * *

## Detailed Description

该QNetworkAddressEntry类存储一个IP地址，通过网络接口支持，连同其相关联的网络掩码和广播地址。

每个网络接口可以包含零个或多个IP地址，从而可以用一个掩码和/或广播地址（根据从操作系统支持）相关联。

这个类表示一个这样的团体。

* * *

## Method Documentation

```
QNetworkAddressEntry.__init__ (self)
```

构造一个空[QNetworkAddressEntry](qnetworkaddressentry.html)对象。

```
QNetworkAddressEntry.__init__ (self, QNetworkAddressEntry other)
```

构造一个[QNetworkAddressEntry](qnetworkaddressentry.html)对象，该对象是该对象的一个拷贝_other_。

```
QHostAddress QNetworkAddressEntry.broadcast (self)
```

[

返回与该IPv4地址和网络掩码相关联的广播地址。它通常可以从这些2通过设置于其中的网络掩码包含0的IP地址为1的比特导出。 （换句话说，通过按位或运算与网络掩码的逆的IP地址）

这个成员总是空的IPv6地址，因为广播的概念已经被摒弃，该系统支持多播的。特别是，该组对应于本地网络中的所有节点的主机可以通过“所有节点”特殊的多播组（地址FF02.1 ）即可到达。

](qhostaddress.html)

[**See also**](qhostaddress.html) [setBroadcast](qnetworkaddressentry.html#setBroadcast)（ ） 。

```
QHostAddress QNetworkAddressEntry.ip (self)
```

[

这个函数返回一个IPv4或IPv6地址发现，被发现在一个网络接口。

](qhostaddress.html)

[**See also**](qhostaddress.html) [setIp](qnetworkaddressentry.html#setIp)（ ） 。

```
QHostAddress QNetworkAddressEntry.netmask (self)
```

[

返回与IP地址关联的子网掩码。网络掩码是体现在一个IP地址，如255.255.0.0的形式。

](qhostaddress.html)

[对于IPv6地址，前缀长度被转换为一个地址设置为1的位的数目等于前缀长度。为64位（最常见的值）的前缀长度，网络掩码将被表示为一个](qhostaddress.html)[QHostAddress](qhostaddress.html)保持的地址FFFF： FFFF： FFFF： FFFF。

**See also** [setNetmask](qnetworkaddressentry.html#setNetmask)（）和[prefixLength](qnetworkaddressentry.html#prefixLength)（ ） 。

```
int QNetworkAddressEntry.prefixLength (self)
```

返回此IP地址的前缀长度。前缀长度的子网掩码设置为1的比特数匹配（见[netmask](qnetworkaddressentry.html#netmask)（））。对于IPv4地址，该值介于0和32 。为IPv6地址，它包含在0和128 ，是表示地址的最佳形式。

该函数返回-1，如果前缀长度无法确定（即，[netmask](qnetworkaddressentry.html#netmask)（ ）返回一个空QHostAddress （ ） ） 。

此功能被引入Qt的4.5 。

**See also** [setPrefixLength](qnetworkaddressentry.html#setPrefixLength)（）和[netmask](qnetworkaddressentry.html#netmask)（ ） 。

```
QNetworkAddressEntry.setBroadcast (self, QHostAddress newBroadcast)
```

设置的这个广播IP地址[QNetworkAddressEntry](qnetworkaddressentry.html)反对_newBroadcast_。

**See also** [broadcast](qnetworkaddressentry.html#broadcast)（ ） 。

```
QNetworkAddressEntry.setIp (self, QHostAddress newIp)
```

设置IP地址[QNetworkAddressEntry](qnetworkaddressentry.html)对象包含_newIp_。

**See also** [ip](qnetworkaddressentry.html#ip)（ ） 。

```
QNetworkAddressEntry.setNetmask (self, QHostAddress newNetmask)
```

设置网络掩码，这[QNetworkAddressEntry](qnetworkaddressentry.html)对象包含_newNetmask_。设置子网掩码还设置了前缀长度以匹配新的网络掩码。

**See also** [netmask](qnetworkaddressentry.html#netmask)（）和[setPrefixLength](qnetworkaddressentry.html#setPrefixLength)（ ） 。

```
QNetworkAddressEntry.setPrefixLength (self, int length)
```

设置这个IP地址的前缀长度_length_。价值_length_必须是有效的这种类型的IP地址： 0至32之间为IPv4地址，介于0和128为IPv6地址。设置为任何无效的值等于设置为-1 ，这意味着“无前缀长度” 。

设置前缀长度还设置了网络掩码（见[netmask](qnetworkaddressentry.html#netmask)（））。

此功能被引入Qt的4.5 。

**See also** [prefixLength](qnetworkaddressentry.html#prefixLength)（）和[setNetmask](qnetworkaddressentry.html#setNetmask)（ ） 。

```
bool QNetworkAddressEntry.__eq__ (self, QNetworkAddressEntry other)
```

```
bool QNetworkAddressEntry.__ne__ (self, QNetworkAddressEntry other)
```