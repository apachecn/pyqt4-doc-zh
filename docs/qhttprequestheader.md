# QHttpRequestHeader Class Reference

## [[QtNetwork](index.htm) module]

该QHttpRequestHeader类包含HTTP请求头信息。[More...](#details)

继承[QHttpHeader](qhttpheader.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString method, QString path, int major = 1, int minor = 1)`
*   `__init__ (self, QHttpRequestHeader header)`
*   `__init__ (self, QString str)`
*   `int majorVersion (self)`
*   `QString method (self)`
*   `int minorVersion (self)`
*   `bool parseLine (self, QString line, int number)`
*   `QString path (self)`
*   `setRequest (self, QString method, QString path, int major = 1, int minor = 1)`
*   `QString toString (self)`

* * *

## Detailed Description

该QHttpRequestHeader类包含HTTP请求头信息。

该类用于在[QHttp](qhttp.html)类如果客户端从服务器请求的东西报告标题信息。

HTTP请求有它描述了请求的操作的方法。最常见的请求“GET”和“POST” 。除了请求方法的报头还包括一个请求-URI来指定要使用的方法的位置。

的方法，请求URI和协议版本可以使用构造函数或更高版本使用设置[setRequest](qhttprequestheader.html#setRequest)（ ） 。该值可使用以下方式获得[method](qhttprequestheader.html#method)（ ）[path](qhttprequestheader.html#pathx)（ ）[majorVersion](qhttprequestheader.html#majorVersion)（）和[minorVersion](qhttprequestheader.html#minorVersion)（ ） 。

注意，该请求-URI必须在预期由HTTP服务器的格式。也就是说，所有保留字符必须在％ HH （其中HH是两个十六进制数字）进行编码。看[QUrl.toPercentEncoding](qurl.html#toPercentEncoding)（ ）获取更多信息。

重要的继承功能：[setValue](qhttpheader.html#setValue)（）和[value](qhttpheader.html#value)（ ） 。

* * *

## Method Documentation

```
QHttpRequestHeader.__init__ (self)
```

构造一个空的HTTP请求头。

```
QHttpRequestHeader.__init__ (self, QString method, QString path, int major = 1, int minor = 1)
```

构造一个HTTP请求头的方法_method_时，请求-URI_path_和协议版本_majorVer_和_minorVer_。该_path_参数必须被正确编码的HTTP请求。

```
QHttpRequestHeader.__init__ (self, QHttpRequestHeader header)
```

构造的副本_header_。

```
QHttpRequestHeader.__init__ (self, QString str)
```

从字符串构造一个HTTP请求头_str_。该_str_应该由一个或多个“ \ r \ n ”分隔行，第一行应该是请求行（格式：方法，空间，请求的URI ，空间的HTTP版本） ，其馀各行应具备的格式键，冒号，空格，值。

```
int QHttpRequestHeader.majorVersion (self)
```

从重新实现[QHttpHeader.majorVersion](qhttpheader.html#majorVersion)（ ） 。

返回主协议版本的HTTP请求头。

**See also** [minorVersion](qhttprequestheader.html#minorVersion)（ ）[method](qhttprequestheader.html#method)（ ）[path](qhttprequestheader.html#pathx)（）和[setRequest](qhttprequestheader.html#setRequest)（ ） 。

```
QString QHttpRequestHeader.method (self)
```

返回HTTP请求头的方法。

**See also** [path](qhttprequestheader.html#pathx)（ ）[majorVersion](qhttprequestheader.html#majorVersion)（ ）[minorVersion](qhttprequestheader.html#minorVersion)（）和[setRequest](qhttprequestheader.html#setRequest)（ ） 。

```
int QHttpRequestHeader.minorVersion (self)
```

从重新实现[QHttpHeader.minorVersion](qhttpheader.html#minorVersion)（ ） 。

返回未成年协议版本的HTTP请求头。

**See also** [majorVersion](qhttprequestheader.html#majorVersion)（ ）[method](qhttprequestheader.html#method)（ ）[path](qhttprequestheader.html#pathx)（）和[setRequest](qhttprequestheader.html#setRequest)（ ） 。

```
bool QHttpRequestHeader.parseLine (self, QString line, int number)
```

```
QString QHttpRequestHeader.path (self)
```

```
QHttpRequestHeader.setRequest (self, QString method, QString path, int major = 1, int minor = 1)
```

该函数设置请求方法来_method_中，请求URI来_path_和协议版本_majorVer_和_minorVer_。该_path_参数必须被正确编码的HTTP请求。

**See also** [method](qhttprequestheader.html#method)（ ）[path](qhttprequestheader.html#pathx)（ ）[majorVersion](qhttprequestheader.html#majorVersion)（）和[minorVersion](qhttprequestheader.html#minorVersion)（ ） 。

```
QString QHttpRequestHeader.toString (self)
```

从重新实现[QHttpHeader.toString](qhttpheader.html#toString)（ ） 。