# QHttpResponseHeader Class Reference

## [[QtNetwork](index.htm) module]

该QHttpResponseHeader类包含HTTP响应头信息。[More...](#details)

继承[QHttpHeader](qhttpheader.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QHttpResponseHeader header)`
*   `__init__ (self, QString str)`
*   `__init__ (self, int code, QString text = QString(), int major = 1, int minor = 1)`
*   `int majorVersion (self)`
*   `int minorVersion (self)`
*   `bool parseLine (self, QString line, int number)`
*   `QString reasonPhrase (self)`
*   `setStatusLine (self, int code, QString text = QString(), int major = 1, int minor = 1)`
*   `int statusCode (self)`
*   `QString toString (self)`

* * *

## Detailed Description

该QHttpResponseHeader类包含HTTP响应头信息。

这个类是由[QHttp](qhttp.html)类报告的报头信息，客户端从服务器接收。

HTTP响应有一个状态代码，表明该响应的状态。此代码是一个3位数的整数结果代码（详见至RFC 1945） 。除了状态代码，您还可以指定描述的代码的原因（ “理词” ），一个人类可读的文本。这个类可以让你得到状态码和原因短语。

* * *

## Method Documentation

```
QHttpResponseHeader.__init__ (self)
```

构造一个空的HTTP响应头。

```
QHttpResponseHeader.__init__ (self, QHttpResponseHeader header)
```

构造的副本_header_。

```
QHttpResponseHeader.__init__ (self, QString str)
```

从字符串构造一个HTTP响应头_str_。该字符串被解析和信息设置。该_str_应该由一个或多个的“ \ r \ n ”分隔行，第一行应该是状态行（格式： HTTP版本，空间，状态代码，空间，原因短语） ;其馀各行应该有格式为key ，冒号，空格，值。

```
QHttpResponseHeader.__init__ (self, int code, QString text = QString(), int major = 1, int minor = 1)
```

构造一个[QHttpResponseHeader](qhttpresponseheader.html)，状态代码设置为_code_，原因短语_text_和协议版本_majorVer_和_minorVer_。

这个函数是Qt 4.1中引入。

**See also** [statusCode](qhttpresponseheader.html#statusCode)（ ）[reasonPhrase](qhttpresponseheader.html#reasonPhrase)（ ）[majorVersion](qhttpresponseheader.html#majorVersion)（）和[minorVersion](qhttpresponseheader.html#minorVersion)（ ） 。

```
int QHttpResponseHeader.majorVersion (self)
```

从重新实现[QHttpHeader.majorVersion](qhttpheader.html#majorVersion)（ ） 。

返回主协议版本的HTTP响应头。

**See also** [minorVersion](qhttpresponseheader.html#minorVersion)（ ）[statusCode](qhttpresponseheader.html#statusCode)（）和[reasonPhrase](qhttpresponseheader.html#reasonPhrase)（ ） 。

```
int QHttpResponseHeader.minorVersion (self)
```

从重新实现[QHttpHeader.minorVersion](qhttpheader.html#minorVersion)（ ） 。

返回未成年协议版本的HTTP响应头。

**See also** [majorVersion](qhttpresponseheader.html#majorVersion)（ ）[statusCode](qhttpresponseheader.html#statusCode)（）和[reasonPhrase](qhttpresponseheader.html#reasonPhrase)（ ） 。

```
bool QHttpResponseHeader.parseLine (self, QString line, int number)
```

```
QString QHttpResponseHeader.reasonPhrase (self)
```

返回原因短语HTTP响应头。

**See also** [statusCode](qhttpresponseheader.html#statusCode)（ ）[majorVersion](qhttpresponseheader.html#majorVersion)（）和[minorVersion](qhttpresponseheader.html#minorVersion)（ ） 。

```
QHttpResponseHeader.setStatusLine (self, int code, QString text = QString(), int major = 1, int minor = 1)
```

设置状态代码_code_，原因短语_text_和协议版本_majorVer_和_minorVer_。

这个函数是Qt 4.1中引入。

**See also** [statusCode](qhttpresponseheader.html#statusCode)（ ）[reasonPhrase](qhttpresponseheader.html#reasonPhrase)（ ）[majorVersion](qhttpresponseheader.html#majorVersion)（）和[minorVersion](qhttpresponseheader.html#minorVersion)（ ） 。

```
int QHttpResponseHeader.statusCode (self)
```

返回的HTTP响应头的状态代码。

**See also** [reasonPhrase](qhttpresponseheader.html#reasonPhrase)（ ）[majorVersion](qhttpresponseheader.html#majorVersion)（）和[minorVersion](qhttpresponseheader.html#minorVersion)（ ） 。

```
QString QHttpResponseHeader.toString (self)
```

从重新实现[QHttpHeader.toString](qhttpheader.html#toString)（ ） 。