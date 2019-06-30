# QAuthenticator Class Reference

## [[QtNetwork](index.htm) module]

该QAuthenticator类提供了一个验证对象。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QAuthenticator other)`
*   `bool isNull (self)`
*   `QVariant option (self, QString opt)`
*   `dict-of-QString-QVariant options (self)`
*   `QString password (self)`
*   `QString realm (self)`
*   `setOption (self, QString opt, QVariant value)`
*   `setPassword (self, QString password)`
*   `setUser (self, QString user)`
*   `QString user (self)`

### Special Methods

*   `bool __eq__ (self, QAuthenticator other)`
*   `bool __ne__ (self, QAuthenticator other)`

* * *

## Detailed Description

该QAuthenticator类提供了一个验证对象。

该QAuthenticator类通常是在使用[authenticationRequired()](qnetworkaccessmanager.html#authenticationRequired)和[proxyAuthenticationRequired()](qnetworkaccessmanager.html#proxyAuthenticationRequired)信号[QNetworkAccessManager](qnetworkaccessmanager.html)和[QAbstractSocket](qabstractsocket.html)。这个类提供了一种访问需要身份验证的服务时所需的认证信息传递回插座。

QAuthenticator支持以下身份验证方法：

*   Basic
*   NTLM version 2
*   Digest-MD5

### Options

除了身份验证所需的用户名和密码，一个QAuthenticator对象也可以包含额外的选项。该[options](qauthenticator.html#options)（ ）函数可用于查询服务器发送传入的选项，而[setOption](qauthenticator.html#setOption)（）函数可以被用来指定设备发送的选择，要由验证器计算处理。接受和提供的选项取决于身份验证类型（见（）方法） 。

下表列出了已知传入的选项，以及接受离任选项。进入选项列表并不详尽，因为服务器可以在任何时候有更多的信息。即将离任的选项列表是详尽的，但是，没有未知的选项将被视为或发送回服务器。

#### Basic

| Option | Direction | Description |
| --- | --- | --- |
| `realm` | Incoming | Contains the realm of the authentication, the same as [realm](qauthenticator.html#realm)() |

基本验证机制支持没有传出选项。

#### NTLM version 2

NTLM身份验证机制目前不支持传入或传出的选项。

#### Digest-MD5

| Option | Direction | Description |
| --- | --- | --- |
| `realm` | Incoming | Contains the realm of the authentication, the same as [realm](qauthenticator.html#realm)() |

在DIGEST- MD5认证机制支持没有传出选项。

* * *

## Method Documentation

```
QAuthenticator.__init__ (self)
```

构造一个空认证对象

```
QAuthenticator.__init__ (self, QAuthenticator other)
```

构造的副本_other_。

```
bool QAuthenticator.isNull (self)
```

返回True如果认证为null 。

```
QVariant QAuthenticator.option (self, QString opt)
```

返回相关选项的值_opt_如果它是由服务器设置。看[QAuthenticator#Options](qauthenticator.html#options)对于传入选项的更多信息。如果选项_opt_没有找到，无效[QVariant](qvariant.html)将被退回。

此功能被引入Qt的4.7 。

**See also** [setOption](qauthenticator.html#setOption)（ ）[options](qauthenticator.html#options)（）和[QAuthenticator#Options](qauthenticator.html#options)。

```
dict-of-QString-QVariant QAuthenticator.options (self)
```

返回此设置所有传入的选项[QAuthenticator](qauthenticator.html)通过解析服务器应答对象。看[QAuthenticator#Options](qauthenticator.html#options)对于传入选项的更多信息。

此功能被引入Qt的4.7 。

**See also** [option](qauthenticator.html#option)（）和[QAuthenticator#Options](qauthenticator.html#options)。

```
QString QAuthenticator.password (self)
```

返回用于身份验证的密码。

**See also** [setPassword](qauthenticator.html#setPassword)（ ） 。

```
QString QAuthenticator.realm (self)
```

返回需要验证的领域。

```
QAuthenticator.setOption (self, QString opt, QVariant value)
```

设置传出选项_opt_以价值_value_。看[QAuthenticator#Options](qauthenticator.html#options)对于传出选项的更多信息。

此功能被引入Qt的4.7 。

**See also** [options](qauthenticator.html#options)（ ）[option](qauthenticator.html#option)（）和[QAuthenticator#Options](qauthenticator.html#options)。

```
QAuthenticator.setPassword (self, QString password)
```

设置_password_用于身份验证。

**See also** [password](qauthenticator.html#password)（ ） 。

```
QAuthenticator.setUser (self, QString user)
```

设置_user_用于身份验证。

**See also** [user](qauthenticator.html#user)（ ） 。

```
QString QAuthenticator.user (self)
```

返回用于身份验证的用户。

**See also** [setUser](qauthenticator.html#setUser)（ ） 。

```
bool QAuthenticator.__eq__ (self, QAuthenticator other)
```

```
bool QAuthenticator.__ne__ (self, QAuthenticator other)
```