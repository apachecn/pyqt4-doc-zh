# QSslConfiguration Class Reference

## [[QtNetwork](index.htm) module]

该QSslConfiguration类包含一个SSL连接的配置和状态[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSslConfiguration other)`
*   `list-of-QSslCertificate caCertificates (self)`
*   `list-of-QSslCipher ciphers (self)`
*   `bool isNull (self)`
*   `QSslCertificate localCertificate (self)`
*   `QSslCertificate peerCertificate (self)`
*   `list-of-QSslCertificate peerCertificateChain (self)`
*   `int peerVerifyDepth (self)`
*   `QSslSocket.PeerVerifyMode peerVerifyMode (self)`
*   `QSslKey privateKey (self)`
*   `QSsl.SslProtocol protocol (self)`
*   `QSslCipher sessionCipher (self)`
*   `setCaCertificates (self, list-of-QSslCertificate certificates)`
*   `setCiphers (self, list-of-QSslCipher ciphers)`
*   `setLocalCertificate (self, QSslCertificate certificate)`
*   `setPeerVerifyDepth (self, int depth)`
*   `setPeerVerifyMode (self, QSslSocket.PeerVerifyMode mode)`
*   `setPrivateKey (self, QSslKey key)`
*   `setProtocol (self, QSsl.SslProtocol protocol)`
*   `setSslOption (self, QSsl.SslOption option, bool on)`
*   `bool testSslOption (self, QSsl.SslOption option)`

### Static Methods

*   `QSslConfiguration defaultConfiguration ()`
*   `setDefaultConfiguration (QSslConfiguration configuration)`

### Special Methods

*   `bool __eq__ (self, QSslConfiguration other)`
*   `bool __ne__ (self, QSslConfiguration other)`

* * *

## Detailed Description

该QSslConfiguration类包含一个SSL连接的配置和状态

QSslConfiguration是使用Qt的网络类，转发一个开放的SSL连接信息，并允许应用程序来控制连接的某些功能。

这QSslConfiguration目前支持的设置是：

*   The SSL/TLS protocol to be used
*   The certificate to be presented to the peer during connection and its associated private key
*   The ciphers allowed to be used for encrypting the connection
*   The list of Certificate Authorities certificates that are used to validate the peer's certificate

这些设置在连接握手过程仅适用。设置它们的连接已经建立后，没有任何效果。

该状态QSslConfiguration支持是：

*   The certificate the peer presented during handshake, along with the chain leading to a CA certificate
*   The cipher used to encrypt this session

一旦SSL连接启动的状态下才能够获得，但不一定之前，它的完成。某些设置可能，而不需要重新启动它的SSL连接的过程中改变（例如，密码可以被时间改变了） 。

在QSslConfiguration对象的状态不能改变。

QSslConfiguration可以被用于[QSslSocket](qsslsocket.html)和网络访问的API 。

注意，改变在QSslConfiguration设置是不足以改变在相关的SSL连接的设置。你必须调用修改QSslConfiguration对象setSslConfiguration来实现这个目标。下面的例子演示了如何将协议更改为使用TLSv1在[QSslSocket](qsslsocket.html)对象：

```
 QSslConfiguration config = sslSocket.sslConfiguration();
 config.setProtocol([QSsl](qssl.html).TlsV1);
 sslSocket.setSslConfiguration(config);

```

[QSslSocket](qsslsocket.html)，[QNetworkAccessManager](qnetworkaccessmanager.html)，[QSslSocket.sslConfiguration](qsslsocket.html#sslConfiguration)（ ）[QSslSocket.setSslConfiguration](qsslsocket.html#setSslConfiguration)（ ）

* * *

## Method Documentation

```
QSslConfiguration.__init__ (self)
```

构造一个空的SSL配置。此配置不包含有效的设置和状态将是空的。[isNull](qsslconfiguration.html#isNull)（ ）将返回True这个构造函数被调用后。

一旦任何setter方法​​被调用时，[isNull](qsslconfiguration.html#isNull)（ ）将返回False 。

```
QSslConfiguration.__init__ (self, QSslConfiguration other)
```

副本的配置和状态_other_。如果_other_为null，则该对象将是空过。

```
list-of-QSslCertificate QSslConfiguration.caCertificates (self)
```

返回此连接的CA证书数据库。握手阶段中的CA证书数据库所使用的插座，以验证对方的证书。它可以与握手之前被修改[setCaCertificates](qsslconfiguration.html#setCaCertificates)（） ，或用[QSslSocket](qsslsocket.html)的[addCaCertificate()](qsslsocket.html#addCaCertificate)和[addCaCertificates()](qsslsocket.html#addCaCertificates)。

**See also** [setCaCertificates](qsslconfiguration.html#setCaCertificates)（ ） 。

```
list-of-QSslCipher QSslConfiguration.ciphers (self)
```

返回此连接的当前密码的加密套件。在握手阶段该列表用于选择一个会话密码。密码返回的列表是按递减优先级进行排序。 （例如，在列表中的第一密码是最优选的密码） 。会话密码将是第一个在也支持对等的列表。

默认情况下，握手阶段可以选择任何由该系统的SSL库支持的加密算法，这可能会有所不同从系统到系统。通过此系统的SSL库支持的密码列表是由返回[QSslSocket.supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。你可以通过调用限制用于选择会话密码为这个套接字密码列表[setCiphers](qsslconfiguration.html#setCiphers)（ ）与所支持的加密算法的子集。你可以通过调用恢复使用整套[setCiphers](qsslconfiguration.html#setCiphers)（ ）与返回列表[QSslSocket.supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

**See also** [setCiphers](qsslconfiguration.html#setCiphers)（）和[QSslSocket.supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslConfiguration QSslConfiguration.defaultConfiguration ()
```

[

返回新的SSL连接使用的默认SSL配置。

默认的SSL配置包括：

*   no local certificate and no private key
*   protocol SecureProtocols (meaning either TLS 1.0 or SSL 3 will be used)
*   the system's default CA certificate list
*   the cipher list equal to the list of the SSL libraries' supported SSL ciphers

](qsslconfiguration.html)

[**See also**](qsslconfiguration.html) [QSslSocket.supportedCiphers](qsslsocket.html#supportedCiphers)（）和[setDefaultConfiguration](qsslconfiguration.html#setDefaultConfiguration)（ ） 。

```
bool QSslConfiguration.isNull (self)
```

返回True如果这是一个空[QSslConfiguration](qsslconfiguration.html)对象。

A [QSslConfiguration](qsslconfiguration.html)对象为null ，如果它已被缺省构造并没有setter方法被调用。

**See also** [setProtocol](qsslconfiguration.html#setProtocol)（ ）[setLocalCertificate](qsslconfiguration.html#setLocalCertificate)（ ）[setPrivateKey](qsslconfiguration.html#setPrivateKey)（ ）[setCiphers](qsslconfiguration.html#setCiphers)（）和[setCaCertificates](qsslconfiguration.html#setCaCertificates)（ ） 。

```
QSslCertificate QSslConfiguration.localCertificate (self)
```

[

返回在SSL握手过程中要呈现给同行的证书。

](qsslcertificate.html)

[**See also**](qsslcertificate.html) [setLocalCertificate](qsslconfiguration.html#setLocalCertificate)（ ） 。

```
QSslCertificate QSslConfiguration.peerCertificate (self)
```

[

返回同行的数字证书（即您已连接到主机的直接证明） ，或空凭证，如果对等未分配证书。

对等证书握手阶段中的自动检查，所以这个功能通常用来获取用于显示或连接诊断目的的证书。它包含有关对等的信息，包括它的主机名，证书颁发者，和同行的公钥。

](qsslcertificate.html)

[因为对等证书握手阶段中的设置，它是安全的，从连接到一个插槽存取等证书](qsslcertificate.html)[QSslSocket.sslErrors](qsslsocket.html#sslErrors)（ ）信号，[QNetworkReply.sslErrors](qnetworkreply.html#sslErrors)（）信号，或[QSslSocket.encrypted](qsslsocket.html#encrypted)（）信号。

如果证书无效，则返回，它可能意味着SSL握手失败，或者它可能意味着您已连接到主机没有证书，或者它可能意味着没有连接。

如果你想检查对端的完整的证书链，利用[peerCertificateChain](qsslconfiguration.html#peerCertificateChain)（）来得到一次全部。

**See also** [peerCertificateChain](qsslconfiguration.html#peerCertificateChain)（ ）[QSslSocket.sslErrors](qsslsocket.html#sslErrors)（ ）[QSslSocket.ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（ ）[QNetworkReply.sslErrors](qnetworkreply.html#sslErrors)（）和[QNetworkReply.ignoreSslErrors](qnetworkreply.html#ignoreSslErrors)（ ） 。

```
list-of-QSslCertificate QSslConfiguration.peerCertificateChain (self)
```

返回数字证书，开始与对端的直接证书，并与CA的证书结束的对等的链条。

同行证书握手阶段中的自动检查。此功能通常用于获取证书显示，或用于执行连接诊断。证书包含有关对等和证书发行机构，包括主机名，发行人名称和发行者公开密钥的信息。

因为对等证书握手阶段中的设置，它是安全的，从连接到一个插槽存取等证书[QSslSocket.sslErrors](qsslsocket.html#sslErrors)（ ）信号，[QNetworkReply.sslErrors](qnetworkreply.html#sslErrors)（）信号，或[QSslSocket.encrypted](qsslsocket.html#encrypted)（）信号。

如果返回空列表，它可能意味着SSL握手失败，或者它可能意味着您已连接到主机没有证书，或者它可能意味着没有连接。

如果你想只得到了同行的直接证明，使用[peerCertificate](qsslconfiguration.html#peerCertificate)（ ） 。

**See also** [peerCertificate](qsslconfiguration.html#peerCertificate)（ ）[QSslSocket.sslErrors](qsslsocket.html#sslErrors)（ ）[QSslSocket.ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（ ）[QNetworkReply.sslErrors](qnetworkreply.html#sslErrors)（）和[QNetworkReply.ignoreSslErrors](qnetworkreply.html#ignoreSslErrors)（ ） 。

```
int QSslConfiguration.peerVerifyDepth (self)
```

返回的证书在同行中的证书链，如果没有最大深度已设置在SSL握手阶段，或0 （默认值）要检查的最大数目，这表明整个证书链应该进行检查。

该证书在发出订单，开始与对端自己的证书，那么它的颁发者的证书，等检查。

**See also** [setPeerVerifyDepth](qsslconfiguration.html#setPeerVerifyDepth)（）和[peerVerifyMode](qsslconfiguration.html#peerVerifyMode)（ ） 。

```
QSslSocket.PeerVerifyMode QSslConfiguration.peerVerifyMode (self)
```

[](qsslsocket.html#PeerVerifyMode-enum)

[返回验证模式。这种模式决定是否](qsslsocket.html#PeerVerifyMode-enum)[QSslSocket](qsslsocket.html)应要求对等方的证书（即客户端从服务器请求一个证书，或请求从客户端证书的服务器） ，以及是否应当要求该证书是有效的。

默认模式是AutoVerifyPeer ，它告诉[QSslSocket](qsslsocket.html)使用VerifyPeer为客户， QueryPeer的服务器。

**See also** [setPeerVerifyMode](qsslconfiguration.html#setPeerVerifyMode)（ ） 。

```
QSslKey QSslConfiguration.privateKey (self)
```

[](qsslkey.html)

[返回](qsslkey.html)[SSL key](qsslkey.html)分配给该连接或null键，如果没有已分配呢。

**See also** [setPrivateKey](qsslconfiguration.html#setPrivateKey)（）和[localCertificate](qsslconfiguration.html#localCertificate)（ ） 。

```
QSsl.SslProtocol QSslConfiguration.protocol (self)
```

[

返回的协议设置为这个SSL配置。

](qssl.html#SslProtocol-enum)

[**See also**](qssl.html#SslProtocol-enum) [setProtocol](qsslconfiguration.html#setProtocol)（ ） 。

```
QSslCipher QSslConfiguration.sessionCipher (self)
```

[](qsslcipher.html)

[返回套接字的密码](qsslcipher.html)[cipher](qsslcipher.html)或空密码，如果是不加密的连接。套接字的密码在会议期间握手阶段设置。密码是用于加密和解密通过套接字发送的数据。

在SSL基础设施还提供了一些函数来设置密码从中握手阶段将最终选择会话密码的有序列表。这种有序列表必须到位握手阶段开始之前。

**See also** [ciphers](qsslconfiguration.html#ciphers)（ ）[setCiphers](qsslconfiguration.html#setCiphers)（）和[QSslSocket.supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslConfiguration.setCaCertificates (self, list-of-QSslCertificate certificates)
```

设置此套接字的CA证书数据库是_certificates_。证书数据库之前必须设置为SSL握手。握手阶段中的CA证书数据库所使用的插座，以验证对方的证书。

**See also** [caCertificates](qsslconfiguration.html#caCertificates)（ ） 。

```
QSslConfiguration.setCiphers (self, list-of-QSslCipher ciphers)
```

加密的加密套件为这个套接字设置为_ciphers_，其中必须包含在由supportedCiphers返回列表中的密码的一个子集（ ） 。

限制密码套件必须在握手阶段，那里的会话密码被选为前完成。

**See also** [ciphers](qsslconfiguration.html#ciphers)（）和[QSslSocket.supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslConfiguration.setDefaultConfiguration (QSslConfiguration configuration)
```

设置要使用的新SSL连接是默认的SSL配置_configuration_。现有的连接不受此调用。

**See also** [QSslSocket.supportedCiphers](qsslsocket.html#supportedCiphers)（）和[defaultConfiguration](qsslconfiguration.html#defaultConfiguration)（ ） 。

```
QSslConfiguration.setLocalCertificate (self, QSslCertificate certificate)
```

设置SSL握手过程呈现给对端是证书_certificate_。

设置证书一旦连接已建立没有任何效果。

证书是在SSL的过程中使用的识别手段。本地证书是由远端验证本地用户的身份对认证机构的名单。在大多数情况下，例如在HTTP网页浏览，只能识别服务器到客户端，所以客户端没有发送证书。

**See also** [localCertificate](qsslconfiguration.html#localCertificate)（ ） 。

```
QSslConfiguration.setPeerVerifyDepth (self, int depth)
```

设置证书在同行中的证书链在SSL握手阶段进行检查的最大数量，以_depth_。设置为0的深度表示没有最大深度被设定，表明整个证书链应进行检查。

该证书在发出订单，开始与对端自己的证书，那么它的颁发者的证书，等检查。

**See also** [peerVerifyDepth](qsslconfiguration.html#peerVerifyDepth)（）和[setPeerVerifyMode](qsslconfiguration.html#setPeerVerifyMode)（ ） 。

```
QSslConfiguration.setPeerVerifyMode (self, QSslSocket.PeerVerifyMode mode)
```

设置验证模式_mode_。这种模式决定是否[QSslSocket](qsslsocket.html)应要求对等方的证书（即客户端从服务器请求一个证书，或请求从客户端证书的服务器） ，以及是否应当要求该证书是有效的。

默认模式是AutoVerifyPeer ，它告诉[QSslSocket](qsslsocket.html)使用VerifyPeer为客户， QueryPeer的服务器。

**See also** [peerVerifyMode](qsslconfiguration.html#peerVerifyMode)（ ） 。

```
QSslConfiguration.setPrivateKey (self, QSslKey key)
```

设置连接的私人[key](qsslkey.html)至_key_。私钥和当地[certificate](qsslcertificate.html)所使用的客户端和服务器必须证明自己身份的SSL同行。

密钥和本地证书是必需的，如果你正在创建一个SSL服务器套接字。如果要创建一个SSL客户端套接字，密钥和本地证书是如果你的客户端必须确定自己的SSL服务器所需。

**See also** [privateKey](qsslconfiguration.html#privateKey)（）和[setLocalCertificate](qsslconfiguration.html#setLocalCertificate)（ ） 。

```
QSslConfiguration.setProtocol (self, QSsl.SslProtocol protocol)
```

设置协议设置此配置是_protocol_。

设置协议一旦连接已经建立没有任何效果。

**See also** [protocol](qsslconfiguration.html#protocol)（ ） 。

```
QSslConfiguration.setSslOption (self, QSsl.SslOption option, bool on)
```

启用或禁用SSL的兼容性选项。

**See also**testSSlOption （ ） 。

```
bool QSslConfiguration.testSslOption (self, QSsl.SslOption option)
```

如果启用了指定的SSL兼容性选项，则返回True 。

此功能被引入Qt的4.8 。

**See also**testSSlOption （ ） 。

```
bool QSslConfiguration.__eq__ (self, QSslConfiguration other)
```

```
bool QSslConfiguration.__ne__ (self, QSslConfiguration other)
```