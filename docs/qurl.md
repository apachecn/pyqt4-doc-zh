# QUrl Class Reference

## [[QtCore](index.htm) module]

该QUrl类提供了一个方便的接口，用于处理URL 。[More...](#details)

### Types

*   `enum FormattingOption { None, RemoveScheme, RemovePassword, RemoveUserInfo, ..., StripTrailingSlash }`
*   `class **[FormattingOptions](index.htm)**`
*   `enum ParsingMode { TolerantMode, StrictMode }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString url)`
*   `__init__ (self, QString url, ParsingMode mode)`
*   `__init__ (self, QUrl copy)`
*   `addEncodedQueryItem (self, QByteArray key, QByteArray value)`
*   `addQueryItem (self, QString key, QString value)`
*   `list-of-QByteArray allEncodedQueryItemValues (self, QByteArray key)`
*   `QStringList allQueryItemValues (self, QString key)`
*   `QString authority (self)`
*   `clear (self)`
*   `detach (self)`
*   `QByteArray encodedFragment (self)`
*   `QByteArray encodedHost (self)`
*   `QByteArray encodedPassword (self)`
*   `QByteArray encodedPath (self)`
*   `QByteArray encodedQuery (self)`
*   `list-of-tuple-of-QByteArray-QByteArray encodedQueryItems (self)`
*   `QByteArray encodedQueryItemValue (self, QByteArray key)`
*   `QByteArray encodedUserName (self)`
*   `QString errorString (self)`
*   `QString fragment (self)`
*   `bool hasEncodedQueryItem (self, QByteArray key)`
*   `bool hasFragment (self)`
*   `bool hasQuery (self)`
*   `bool hasQueryItem (self, QString key)`
*   `QString host (self)`
*   `bool isDetached (self)`
*   `bool isEmpty (self)`
*   `bool isLocalFile (self)`
*   `bool isParentOf (self, QUrl url)`
*   `bool isRelative (self)`
*   `bool isValid (self)`
*   `QString password (self)`
*   `QString path (self)`
*   `int port (self)`
*   `int port (self, int defaultPort)`
*   `list-of-tuple-of-QString-QString queryItems (self)`
*   `QString queryItemValue (self, QString key)`
*   `str queryPairDelimiter (self)`
*   `str queryValueDelimiter (self)`
*   `removeAllEncodedQueryItems (self, QByteArray key)`
*   `removeAllQueryItems (self, QString key)`
*   `removeEncodedQueryItem (self, QByteArray key)`
*   `removeQueryItem (self, QString key)`
*   `QUrl resolved (self, QUrl relative)`
*   `QString scheme (self)`
*   `setAuthority (self, QString authority)`
*   `setEncodedFragment (self, QByteArray fragment)`
*   `setEncodedHost (self, QByteArray host)`
*   `setEncodedPassword (self, QByteArray password)`
*   `setEncodedPath (self, QByteArray path)`
*   `setEncodedQuery (self, QByteArray query)`
*   `setEncodedQueryItems (self, list-of-tuple-of-QByteArray-QByteArray query)`
*   `setEncodedUrl (self, QByteArray url)`
*   `setEncodedUrl (self, QByteArray url, ParsingMode mode)`
*   `setEncodedUserName (self, QByteArray userName)`
*   `setFragment (self, QString fragment)`
*   `setHost (self, QString host)`
*   `setPassword (self, QString password)`
*   `setPath (self, QString path)`
*   `setPort (self, int port)`
*   `setQueryDelimiters (self, str valueDelimiter, str pairDelimiter)`
*   `setQueryItems (self, list-of-tuple-of-QString-QString query)`
*   `setScheme (self, QString scheme)`
*   `setUrl (self, QString url)`
*   `setUrl (self, QString url, ParsingMode mode)`
*   `setUserInfo (self, QString userInfo)`
*   `setUserName (self, QString userName)`
*   `swap (self, QUrl other)`
*   `QByteArray toEncoded (self, FormattingOptions options = QUrl.None)`
*   `QString toLocalFile (self)`
*   `QString topLevelDomain (self)`
*   `QString toString (self, FormattingOptions options = QUrl.None)`
*   `QString userInfo (self)`
*   `QString userName (self)`

### Static Methods

*   `QString fromAce (QByteArray)`
*   `QUrl fromEncoded (QByteArray url)`
*   `QUrl fromEncoded (QByteArray url, ParsingMode mode)`
*   `QUrl fromLocalFile (QString localfile)`
*   `QString fromPercentEncoding (QByteArray)`
*   `QString fromPunycode (QByteArray)`
*   `QUrl fromUserInput (QString userInput)`
*   `QStringList idnWhitelist ()`
*   `setIdnWhitelist (QStringList)`
*   `QByteArray toAce (QString)`
*   `QByteArray toPercentEncoding (QString input, QByteArray exclude = QByteArray(), QByteArray include = QByteArray())`
*   `QByteArray toPunycode (QString)`

### Special Methods

*   `bool __eq__ (self, QUrl url)`
*   `bool __ge__ (self, QUrl url)`
*   `int __hash__ (self)`
*   `bool __lt__ (self, QUrl url)`
*   `bool __ne__ (self, QUrl url)`
*   `str __repr__ (self)`

* * *

## Detailed Description

该QUrl类提供了一个方便的接口，用于处理URL 。

它可以解析和构造的URL在这两个编码和非编码形式。 QUrl还拥有国际化域名（IDN ）的支持。

使用QUrl最常用的方法是通过构造函数传递给它初始化一个[QString](qstring.html)。否则，[setUrl](qurl.html#setUrl)（）和[setEncodedUrl](qurl.html#setEncodedUrl)（）也可以使用。

URL可以有两种形式来表示：编码和非编码。未编码的表示法是适于显示给用户，而是编码表示通常你会发送到Web服务器什么。例如，未编码的URL “ http://bühler.example.com/List applicants.xml的”将被发送到服务器的“ http://xn--bhler-kva.example.com/List ％ 20of ％ 20applicants.xml “ ，这可以通过调用验证[toEncoded](qurl.html#toEncoded)（）函数。

一个URL ，也可以通过调用构造一块一块[setScheme](qurl.html#setScheme)（ ）[setUserName](qurl.html#setUserName)（ ）[setPassword](qurl.html#setPassword)（ ）[setHost](qurl.html#setHost)（ ）[setPort](qurl.html#setPort)（ ）[setPath](qurl.html#setPath)（ ）[setEncodedQuery](qurl.html#setEncodedQuery)（）和[setFragment](qurl.html#setFragment)（ ） 。一些方便的功能也可以：[setAuthority](qurl.html#setAuthority)（ ）设置用户名，密码，主机和端口。[setUserInfo](qurl.html#setUserInfo)（）设置用户名和密码一次。

Call [isValid](qurl.html#isValid)（ ）来检查URL是否有效。这可以在任何一点的URL的构建过程中来完成。

构造查询是通过使用特别方便[setQueryItems](qurl.html#setQueryItems)（ ）[addQueryItem](qurl.html#addQueryItem)（）和[removeQueryItem](qurl.html#removeQueryItem)（ ） 。使用[setQueryDelimiters](qurl.html#setQueryDelimiters)（ ）来定制用于生成查询字符串分隔符。

为了生成编码的URL字符串或查询字符串的方便，有两个静态函数调用[fromPercentEncoding](qurl.html#fromPercentEncoding)（）和[toPercentEncoding](qurl.html#toPercentEncoding)（ ）涉及％的编码和将QString解码。

调用[isRelative](qurl.html#isRelative)（ ）会告诉的URL是否是相对的。相对URL可以通过将它作为参数传递给解决[resolved](qurl.html#resolved)（ ） ，它返回一个绝对URL 。[isParentOf](qurl.html#isParentOf)（ ）是用于确定一个URL是否是另一个的父代。

[fromLocalFile](qurl.html#fromLocalFile)（ ）通过解析本地文件路径构造一个QUrl 。[toLocalFile](qurl.html#toLocalFile)（ ）转换成一个URL到本地文件路径。

URL的人类可读的表示是牵强[toString](qurl.html#toString)（ ） 。这种表示是适合显示的URL中未编码形式的用户。然而的编码形式，所返回的[toEncoded](qurl.html#toEncoded)（ ） ，是供内部使用，传递给Web服务器，邮件客户端等。

QUrl符合URI规范从[RFC 3986](http://www.rfc-editor.org/rfc/rfc3986.txt)（统一资源标识符：通用语法） ，并且包括从计划扩展[RFC 1738](http://www.rfc-editor.org/rfc/rfc1738.txt)（统一资源定位器） 。在QUrl情况下折叠规则符合[RFC 3491](http://www.rfc-editor.org/rfc/rfc3491.txt)（ NAMEPREP ：一个STRINGPREP简介国际化域名（ IDN ） ） 。

#### Character Conversions

遵循这些规则，以避免错误的字符转换时用的URL和字符串处理：

*   When creating an [QString](qstring.html) to contain a URL from a [QByteArray](qbytearray.html) or a char*, always use [QString.fromUtf8](qstring.html#fromUtf8)().
*   Favor the use of [QUrl.fromEncoded](qurl.html#fromEncoded)() and [QUrl.toEncoded](qurl.html#toEncoded)() instead of QUrl(string) and [QUrl.toString](qurl.html#toString)() when converting a QUrl to or from a string.

* * *

## Type Documentation

```
QUrl.FormattingOption
```

格式选项定义了如何当写出来的文字的URL格式。

| Constant | Value | Description |
| --- | --- | --- |
| `QUrl.None` | `0x0` | URL的格式不变。 |
| `QUrl.RemoveScheme` | `0x1` | 该计划从URL中移除。 |
| `QUrl.RemovePassword` | `0x2` | 任何密码在URL中移除。 |
| `QUrl.RemoveUserInfo` | `RemovePassword &#124; 0x4` | URL中的任何用户信息被删除。 |
| `QUrl.RemovePort` | `0x8` | 任何指定的端口是从URL中移除。 |
| `QUrl.RemoveAuthority` | `RemoveUserInfo &#124; RemovePort &#124; 0x10` |   |
| `QUrl.RemovePath` | `0x20` | 在URL的路径被删除，只留下了方案，主机地址和端口（如果有的话） 。 |
| `QUrl.RemoveQuery` | `0x40` | 网址（以下一个' ？ '字符）的查询部分被删除。 |
| `QUrl.RemoveFragment` | `0x80` |   |
| `QUrl.StripTrailingSlash` | `0x10000` | 如果存在的斜线被删除。 |

请注意，在折叠的规则的情况下[Nameprep](http://www.rfc-editor.org/rfc/rfc3491.txt)，这[QUrl](qurl.html)符合，需要总是被转换为小写的主机名，而不管使用的Qt.FormattingOptions的。

该FormattingOptions类型是一个typedef为[QFlags](index.htm)\u003cFormattingOption\u003e 。它存储FormattingOption值的或组合。

```
QUrl.ParsingMode
```

解析模式控制方式[QUrl](qurl.html)解析字符串。

| Constant | Value | Description |
| --- | --- | --- |
| `QUrl.TolerantMode` | `0` | [QUrl](qurl.html)将设法纠正URL中一些常见的错误。处理用户输入的URL时，这种模式十分有用。 |
| `QUrl.StrictMode` | `1` | 只有有效的URL被接受。此模式适用于一般的URL验证有用。 |

在TolerantMode ，解析器修正了以下无效输入：

*   Spaces and "%20": If an encoded URL contains a space, this will be replaced with "%20". If a decoded URL contains "%20", this will be replaced with a single space before the URL is parsed.
*   Single "%" characters: Any occurrences of a percent character "%" not followed by exactly two hexadecimal characters (e.g., "13% coverage.html") will be replaced by "%25".
*   Reserved and unreserved characters: An encoded URL should only contain a few characters as literals; all other characters should be percent-encoded. In TolerantMode, these characters will be automatically percent-encoded where they are not allowed: space / double-quote / "&lt;" / "&gt;" / "[" / "" / "]" / "^" / "`" / "{" / "|" / "}"

* * *

## Method Documentation

```
QUrl.__init__ (self)
```

构造一个空[QUrl](qurl.html)对象。

```
QUrl.__init__ (self, QString url)
```

通过解析构造一个URL_url_。_url_被假定为在人类可读表示，没有百分之编码。[QUrl](qurl.html)会自动％的编码，但在URL中允许的所有字符。默认的解析模式是[TolerantMode](qurl.html#ParsingMode-enum)。

例如：

```
 [QUrl](qurl.html) url("http://www.example.com/List of holidays.xml");
 // url.toEncoded() == "http://www.example.com/List%20of%20holidays.xml"

```

从一个编码的字符串，调用构造一个URL[fromEncoded](qurl.html#fromEncoded)（）：

```
 [QUrl](qurl.html) url = [QUrl](qurl.html).fromEncoded("http://qt.nokia.com/List%20of%20holidays.xml");

```

**See also** [setUrl](qurl.html#setUrl)（ ）[setEncodedUrl](qurl.html#setEncodedUrl)（ ）[fromEncoded](qurl.html#fromEncoded)（）和[TolerantMode](qurl.html#ParsingMode-enum)。

```
QUrl.__init__ (self, QString url, ParsingMode mode)
```

构造的副本_other_。

```
QUrl.__init__ (self, QUrl copy)
```

这是一个重载函数。

解析_url_使用分析器模式_parsingMode_。默认的解析模式是[TolerantMode](qurl.html#ParsingMode-enum)。

**See also** [setUrl](qurl.html#setUrl)（ ） 。

```
QUrl.addEncodedQueryItem (self, QByteArray key, QByteArray value)
```

插入对_key_=_value_到URL的查询字符串。

注：此功能不验证，要么_key_ or _value_被正确编码。它是调用者的责任，以确保查询的分隔符的编码正确，如果有的话。

此功能被引入Qt的4.4 。

**See also** [addQueryItem](qurl.html#addQueryItem)（）和[setQueryDelimiters](qurl.html#setQueryDelimiters)（ ） 。

```
QUrl.addQueryItem (self, QString key, QString value)
```

插入对_key_=_value_到URL的查询字符串。

之前它被添加到查询的键/值对被编码。两人在内部转换成单独的字符串。该_key_和_value_首先编码成UTF -8 ，然后由valueDelimiter （返回的字符分隔） 。每个键/值对是通过pairDelimiter （返回的字符分隔） 。

**Note:**此方法不编码空格（ ASCII码0X20 ）为加号（+ ）标志，就像HTML表单做。如果你需要这种编码方式，你必须自己编码值，并使用QUrl.addEncodedQueryItem 。

**See also** [addEncodedQueryItem](qurl.html#addEncodedQueryItem)（ ） 。

```
list-of-QByteArray QUrl.allEncodedQueryItemValues (self, QByteArray key)
```

返回的查询字符串值的一个列表，其关键是等于_key_从URL中。

注意：如果该编码_key_不匹配查询的编码版本，此功能将无法正常工作。也就是说，如果该URL的编码查询“的搜索= Qt的％ 20Rules ” ，调用这个函数_key_= “ ％ 73earch ”将返回一个空列表。

此功能被引入Qt的4.4 。

**See also** [allQueryItemValues](qurl.html#allQueryItemValues)（ ）[queryItemValue](qurl.html#queryItemValue)（）和[encodedQueryItemValue](qurl.html#encodedQueryItemValue)（ ） 。

```
QStringList QUrl.allQueryItemValues (self, QString key)
```

返回的查询字符串值的一个列表，其关键是等于_key_从URL中。

**Note:**此方法不解码的空间加号（+ ）符号空格（ ASCII码0X20 ） ，如HTML表单做。如果你需要这种解码，则必须使用QUrl.allEncodedQueryItemValues​​和自己解码数据。

**See also** [queryItemValue](qurl.html#queryItemValue)（ ） 。

```
QString QUrl.authority (self)
```

返回如果它被定义URL的权限，否则为空字符串返回。

**See also** [setAuthority](qurl.html#setAuthority)（ ） 。

```
QUrl.clear (self)
```

重置的内容[QUrl](qurl.html)。调用该函数后，[QUrl](qurl.html)等于一个已经构建了默认的空构造函数。

```
QUrl.detach (self)
```

```
QByteArray QUrl.encodedFragment (self)
```

[](qbytearray.html)

[返回如果它被定义URL的片段;否则返回空字符串。返回的值将拥有非ASCII和其他控制字符百分比编码，如](qbytearray.html)[toEncoded](qurl.html#toEncoded)（ ） 。

此功能被引入Qt的4.4 。

**See also** [setEncodedFragment](qurl.html#setEncodedFragment)（）和[toEncoded](qurl.html#toEncoded)（ ） 。

```
QByteArray QUrl.encodedHost (self)
```

[

返回URL的主机部分，如果它被定义，否则返回空字符串。

注： encodedHost （ ）不返回百分比编码的主机名。取而代之的是， ACE编码（ ASCII裸以Punycode编码）的形式将任何非ASCII主机名返回。

](qbytearray.html)

[此功能相当于调用](qbytearray.html)[QUrl.toAce](qurl.html#toAce)（ ）上的返回值[host](qurl.html#host)（ ） 。

此功能被引入Qt的4.4 。

**See also** [setEncodedHost](qurl.html#setEncodedHost)（ ） 。

```
QByteArray QUrl.encodedPassword (self)
```

[](qbytearray.html)

[返回如果它被定义URL的密码，否则一个空字符串返回。返回的值将拥有非ASCII和其他控制字符百分比编码，如](qbytearray.html)[toEncoded](qurl.html#toEncoded)（ ） 。

此功能被引入Qt的4.4 。

**See also** [setEncodedPassword](qurl.html#setEncodedPassword)（）和[toEncoded](qurl.html#toEncoded)（ ） 。

```
QByteArray QUrl.encodedPath (self)
```

[](qbytearray.html)

[返回如果它被定义URL的路径，否则返回空字符串。返回的值将拥有非ASCII和其他控制字符百分比编码，如](qbytearray.html)[toEncoded](qurl.html#toEncoded)（ ） 。

此功能被引入Qt的4.4 。

**See also** [setEncodedPath](qurl.html#setEncodedPath)（）和[toEncoded](qurl.html#toEncoded)（ ） 。

```
QByteArray QUrl.encodedQuery (self)
```

[

返回百分比编码形式的URL查询字符串。

](qbytearray.html)

[**See also**](qbytearray.html) [setEncodedQuery](qurl.html#setEncodedQuery)（ ） 。

```
list-of-tuple-of-QByteArray-QByteArray QUrl.encodedQueryItems (self)
```

返回URL的查询字符串，如编码键和值的映射。

此功能被引入Qt的4.4 。

**See also** [setEncodedQueryItems](qurl.html#setEncodedQueryItems)（ ）[setQueryItems](qurl.html#setQueryItems)（）和[setEncodedQuery](qurl.html#setEncodedQuery)（ ） 。

```
QByteArray QUrl.encodedQueryItemValue (self, QByteArray key)
```

[

返回第一个查询字符串值，其关键是等于_key_从URL中。

注意：如果该编码_key_不匹配查询的编码版本，此功能将无法正常工作。也就是说，如果该URL的编码查询“的搜索= Qt的％ 20Rules ” ，调用这个函数_key_= “ ％ 73earch ”将返回一个空字符串。

此功能被引入Qt的4.4 。

](qbytearray.html)

[**See also**](qbytearray.html) [queryItemValue](qurl.html#queryItemValue)（）和[allQueryItemValues](qurl.html#allQueryItemValues)（ ） 。

```
QByteArray QUrl.encodedUserName (self)
```

[](qbytearray.html)

[返回如果它被定义URL的用户名;否则返回空字符串。返回的值将拥有非ASCII和其他控制字符百分比编码，如](qbytearray.html)[toEncoded](qurl.html#toEncoded)（ ） 。

此功能被引入Qt的4.4 。

**See also** [setEncodedUserName](qurl.html#setEncodedUserName)（ ） 。

```
QString QUrl.errorString (self)
```

返回解释了为什么一个URL是在这样的情况下无效的文本字符串，否则返回一个空字符串。

这个函数中引入了Qt 4.2中。

```
QString QUrl.fragment (self)
```

返回URL的片段。

**See also** [setFragment](qurl.html#setFragment)（ ） 。

```
QString QUrl.fromAce (QByteArray)
```

返回Unicode形式给定的域名_domain_，它被编码为ASCII兼容性编码（ACE）。此函数的结果被认为是等同于_domain_。

如果该值在_domain_可以不进行编码，它会被转换为[QString](qstring.html)并返回。

该ASCII兼容性编码（ACE ）是由RFC 3490 ， RFC 3491和RFC 3492中定义。它是国际化域名的应用（ IDNA ）规范，它允许域名（如部分`"example.com"`）使用国际字符写入。

这个函数中引入了Qt 4.2中。

```
QUrl QUrl.fromEncoded (QByteArray url)
```

[](qurl.html)

[解析_input_并返回相应的](qurl.html)[QUrl](qurl.html)。_input_被假定为以编码形式，只包含ASCII字符。

URL是使用分析[TolerantMode](qurl.html#ParsingMode-enum)。

**See also** [toEncoded](qurl.html#toEncoded)（）和[setUrl](qurl.html#setUrl)（ ） 。

```
QUrl QUrl.fromEncoded (QByteArray url, ParsingMode mode)
```

[

这是一个重载函数。

解析使用URL_parsingMode_。

](qurl.html)

[**See also**](qurl.html) [toEncoded](qurl.html#toEncoded)（）和[setUrl](qurl.html#setUrl)（ ） 。

```
QUrl QUrl.fromLocalFile (QString localfile)
```

[](qurl.html)

[返回](qurl.html)[QUrl](qurl.html)代表性_localFile_，解释为一个本地文件。这个函数接受由斜线以及本地分隔这个平台分隔的路径。

这个函数还接受了一倍，领先的斜杠（或反斜杠）的路径来表示一个远程文件，如“ / /服务器名/路径/到/ file.txt的” 。请注意，只有某些平台上可以使用实际打开该文件[QFile.open](qfile.html#open)（ ） 。

**See also** [toLocalFile](qurl.html#toLocalFile)（ ）[isLocalFile](qurl.html#isLocalFile)（）和[QDir.toNativeSeparators](qdir.html#toNativeSeparators)（ ） 。

```
QString QUrl.fromPercentEncoding (QByteArray)
```

返回一个解码副本_input_。_input_首先从百分之编码解码，然后转换从UTF-8转换为Unicode 。

```
QString QUrl.fromPunycode (QByteArray)
```

```
QUrl QUrl.fromUserInput (QString userInput)
```

[](qurl.html)

[从提供的用户返回一个有效的URL_userInput_字符串如果一个人可以扣除。在这是不可能的，无效的情况下](qurl.html)[QUrl](qurl.html#QUrl)（ ）返回。

最能够浏览Web应用程序，允许用户输入在一个普通的字符串形式的URL。这个字符串可以手动输入到地址栏，从剪贴板获得，或通过命令行参数传递。

当该字符串是不是已经是一个有效的URL ，一个最好的猜测是执行，使各种网络相关的假设。

在该情况下，字符串对应于该系统上的一个有效的文件路径，文件:/ / URL构造，使用[QUrl.fromLocalFile](qurl.html#fromLocalFile)（ ） 。

如果不是这种情况，试图把串入一个http://或ftp:// URL协议。在该情况下，后者的字符串开头是'ftp ' 。结果，然后通过传递[QUrl](qurl.html)的宽容解析器，并在案件或成功，有效的[QUrl](qurl.html)返回，否则一[QUrl](qurl.html#QUrl)（ ） 。

#### Examples:

*   qt.nokia.com becomes http://qt.nokia.com
*   ftp.qt.nokia.com becomes ftp://ftp.qt.nokia.com
*   hostname becomes http://hostname
*   /home/user/test.html becomes file:///home/user/test.html

此功能被引入Qt的4.6 。

```
bool QUrl.hasEncodedQueryItem (self, QByteArray key)
```

返回True如果有一个查询字符串对，其关键是等于_key_从URL中。

注意：如果该编码_key_不匹配查询的编码版本，这个函数将返回False 。也就是说，如果该URL的编码查询“的搜索= Qt的％ 20Rules ” ，调用这个函数_key_= “ ％ 73earch ”将返回False 。

此功能被引入Qt的4.4 。

**See also** [hasQueryItem](qurl.html#hasQueryItem)（ ） 。

```
bool QUrl.hasFragment (self)
```

返回True如果该URL包含一个片段（例如，如果＃ ，看到就可以了） 。

这个函数中引入了Qt 4.2中。

**See also** [fragment](qurl.html#fragment)（）和[setFragment](qurl.html#setFragment)（ ） 。

```
bool QUrl.hasQuery (self)
```

返回True如果该URL包含查询（即，如果？被认为就可以了） 。

这个函数中引入了Qt 4.2中。

**See also** [hasQueryItem](qurl.html#hasQueryItem)（）和[encodedQuery](qurl.html#encodedQuery)（ ） 。

```
bool QUrl.hasQueryItem (self, QString key)
```

返回True如果有一个查询字符串对，其关键是等于_key_从URL中。

**See also** [hasEncodedQueryItem](qurl.html#hasEncodedQueryItem)（ ） 。

```
QString QUrl.host (self)
```

返回如果它被定义URL的主机;否则返回空字符串。

**See also** [setHost](qurl.html#setHost)（ ） 。

```
QStringList QUrl.idnWhitelist ()
```

返回被允许有非ASCII字符在他们的作文顶级域的当前白名单。

See [setIdnWhitelist](qurl.html#setIdnWhitelist)（ ）就本列表的理由。

这个函数中引入了Qt 4.2中。

**See also** [setIdnWhitelist](qurl.html#setIdnWhitelist)（ ） 。

```
bool QUrl.isDetached (self)
```

```
bool QUrl.isEmpty (self)
```

返回True如果URL中没有数据，否则返回False 。

```
bool QUrl.isLocalFile (self)
```

返回True如果这个URL是指向一个本地文件路径。 URL是本地文件路径，如果该计划是“文件” 。

注意，这个函数考虑的URL与主机名是本地文件路径，即使最终的文件路径不能打开[QFile.open](qfile.html#open)（ ） 。

此功能被引入Qt的4.8 。

**See also** [fromLocalFile](qurl.html#fromLocalFile)（）和[toLocalFile](qurl.html#toLocalFile)（ ） 。

```
bool QUrl.isParentOf (self, QUrl url)
```

返回True如果这个URL是父_childUrl_。_childUrl_这是URL的孩子，如果两个URL共享相同的方案和权威，这个URL的路径是路径的父_childUrl_。

```
bool QUrl.isRelative (self)
```

返回True如果该URL是相对的，否则返回False 。 URL是相对的，如果它的方案是不确定的，因此这个函数相当于调用[scheme](qurl.html#scheme)（ ） 。[isEmpty](qurl.html#isEmpty)（ ） 。

```
bool QUrl.isValid (self)
```

返回True如果该URL是有效的，否则返回False 。

该URL通过一致性测试运行。 URL的每一个部分都必须符合报告为有效的URL的URI标准的标准编码规则。

```
 bool checkUrl(const [QUrl](qurl.html) &url) {
     if (!url.isValid()) {
         qDebug([QString](qstring.html)("Invalid URL: %1").arg(url.toString()));
         return false;
     }

     return true;
 }

```

```
QString QUrl.password (self)
```

返回如果它被定义URL的密码，否则一个空字符串返回。

**See also** [setPassword](qurl.html#setPassword)（ ） 。

```
QString QUrl.path (self)
```

```
int QUrl.port (self)
```

返回URL的端口，或-1，如果该端口是不确定的。

**See also** [setPort](qurl.html#setPort)（ ） 。

```
int QUrl.port (self, int defaultPort)
```

这是一个重载函数。

返回URL的端口，或_defaultPort_如果端口是不确定的。

例如：

```
 [QFtp](qftp.html) ftp;
 ftp.connectToHost(url.host(), url.port(21));

```

这个函数是Qt 4.1中引入。

```
list-of-tuple-of-QString-QString QUrl.queryItems (self)
```

返回URL的查询字符串作为键和值的映射。

**Note:**此方法不解码的空间加号（+ ）符号空格（ ASCII码0X20 ） ，如HTML表单做。如果你需要这种解码，则必须使用QUrl.encodedQueryItems和自己解码数据。

**See also** [setQueryItems](qurl.html#setQueryItems)（）和[setEncodedQuery](qurl.html#setEncodedQuery)（ ） 。

```
QString QUrl.queryItemValue (self, QString key)
```

返回第一个查询字符串值，其关键是等于_key_从URL中。

**Note:**此方法不解码的空间加号（+ ）符号空格（ ASCII码0X20 ） ，如HTML表单做。如果你需要这种解码，则必须使用QUrl.encodedQueryItemValue和自己解码数据。

**See also** [allQueryItemValues](qurl.html#allQueryItemValues)（ ） 。

```
str QUrl.queryPairDelimiter (self)
```

返回用于在URL中的查询字符串键值对之间的分隔字符。

```
str QUrl.queryValueDelimiter (self)
```

返回用于在URL中的查询字符串键和值之间的分隔字符。

```
QUrl.removeAllEncodedQueryItems (self, QByteArray key)
```

删除所有的查询字符串对的关键是等于_key_从URL中。

注意：如果该编码_key_不匹配查询的编码版本，此功能将无法正常工作。也就是说，如果该URL的编码查询“的搜索= Qt的％ 20Rules ” ，调用这个函数_key_= “ ％ 73earch ”不会做任何事。

此功能被引入Qt的4.4 。

**See also** [removeQueryItem](qurl.html#removeQueryItem)（ ） 。

```
QUrl.removeAllQueryItems (self, QString key)
```

删除所有的查询字符串对的关键是等于_key_从URL中。

**See also** [removeQueryItem](qurl.html#removeQueryItem)（ ） 。

```
QUrl.removeEncodedQueryItem (self, QByteArray key)
```

删除第一个查询字符串对，其关键是等于_key_从URL中。

注意：如果该编码_key_不匹配查询的编码版本，此功能将无法正常工作。也就是说，如果该URL的编码查询“的搜索= Qt的％ 20Rules ” ，调用这个函数_key_= “ ％ 73earch ”不会做任何事。

此功能被引入Qt的4.4 。

**See also** [removeQueryItem](qurl.html#removeQueryItem)（）和[removeAllQueryItems](qurl.html#removeAllQueryItems)（ ） 。

```
QUrl.removeQueryItem (self, QString key)
```

删除第一个查询字符串对，其关键是等于_key_从URL中。

**See also** [removeAllQueryItems](qurl.html#removeAllQueryItems)（ ） 。

```
QUrl QUrl.resolved (self, QUrl relative)
```

[

返回此URL的合并的结果与_relative_。这个URL被用作基础来转换_relative_一个绝对URL 。

If _relative_是不是一个相对的URL ，这个函数将返回_relative_直接。否则，这两个URL的路径被合并，并返回该新URL的基URL的方案和权威，但合并后的路径，如下面的例子：

](qurl.html)

```
 QUrl baseUrl("http://qt.nokia.com/support");
 [QUrl](qurl.html) relativeUrl("../products/solutions");
 qDebug(baseUrl.resolved(relativeUrl).toString());
 // prints "http://qt.nokia.com/products/solutions"

```

呼叫解决（ ）与“..”返回[QUrl](qurl.html)其目录是比原来更高一层。同样，调用解析（ ）用“ .. / .. ”从路径中移除两个层次。如果_relative_是“/” ，路径变为“/”。

**See also** [isRelative](qurl.html#isRelative)（ ） 。

```
QString QUrl.scheme (self)
```

返回URL的方案。如果返回一个空字符串，这意味着该计划是不确定的，网址是那么相对的。

**See also** [setScheme](qurl.html#setScheme)（）和[isRelative](qurl.html#isRelative)（ ） 。

```
QUrl.setAuthority (self, QString authority)
```

设置URL的权限_authority_。

URL的权限是用户信息，主机名和端口的组合。所有这些元素都是可选的，因此一个空的权力是有效的。

用户信息和主机是通过一个“分开[@](index.html)“：” ，并在主机和端口通过一个分离“ 。如果用户信息是空的，则'[@](index.html)“必须省略，虽然流浪'：'是允许的，如果该端口为空。

下面的例子显示了一个有效的权威字符串：

![](../img/qurl-authority.png)

**See also** [authority](qurl.html#authority)（ ） 。

```
QUrl.setEncodedFragment (self, QByteArray fragment)
```

设定URL的片段的百分比编码_fragment_。该片段是URL的最后部分，通过一个“＃”后面字符的字符串来表示。它通常用于在HTTP进行指的是页面上的某条链路或点：

![](../img/qurl-fragment.png)

的片段，有时也被称为URL为“参考” 。

通过QByteArray中（的说法） （空[QByteArray](qbytearray.html)）将取消设置的片段。传递的参数[QByteArray](qbytearray.html)（ “”） （空但不为空[QByteArray](qbytearray.html)）将设置片段为空字符串（就像原始的URL了一个孤独的“＃” ） 。

此功能被引入Qt的4.4 。

**See also** [setFragment](qurl.html#setFragment)（）和[encodedFragment](qurl.html#encodedFragment)（ ） 。

```
QUrl.setEncodedHost (self, QByteArray host)
```

设定URL的主机与ACE -或百分比编码_host_。该_host_是在URL的权限的用户信息元素的一部分，如描述[setAuthority](qurl.html#setAuthority)（ ） 。

此功能被引入Qt的4.4 。

**See also** [setHost](qurl.html#setHost)（ ）[encodedHost](qurl.html#encodedHost)（ ）[setAuthority](qurl.html#setAuthority)（）和[fromAce](qurl.html#fromAce)（ ） 。

```
QUrl.setEncodedPassword (self, QByteArray password)
```

设定URL的密码，以百分比编码_password_。该_password_是在URL的权限的用户信息元素的一部分，如描述[setUserInfo](qurl.html#setUserInfo)（ ） 。

注：此功能不会验证_password_被正确编码。它是调用者的责任，以确保任何分隔符（如冒号或斜线）被正确编码。

此功能被引入Qt的4.4 。

**See also** [setPassword](qurl.html#setPassword)（ ）[encodedPassword](qurl.html#encodedPassword)（）和[setUserInfo](qurl.html#setUserInfo)（ ） 。

```
QUrl.setEncodedPath (self, QByteArray path)
```

设定URL的路径百分比编码_path_。该路径是自带的权威之后，但在查询字符串之前的URL的一部分。

![](../img/qurl-ftppath.png)

对于非分层方案，路径将是一切按照计划的声明，如下面的示例所示：

![](../img/qurl-mailtopath.png)

注：此功能不会验证_path_被正确编码。它是调用者的责任，以确保任何分隔符（如'？'和'＃' ）被正确编码。

此功能被引入Qt的4.4 。

**See also** [setPath](qurl.html#setPath)（ ）[encodedPath](qurl.html#encodedPath)（）和[setUserInfo](qurl.html#setUserInfo)（ ） 。

```
QUrl.setEncodedQuery (self, QByteArray query)
```

URL的查询字符串设置为_query_。该字符串被插入原样，并且打电话时不进行任何进一步的编码[toEncoded](qurl.html#toEncoded)（ ） 。

如果你需要传递一个不适合的键 - 值模式的查询字符串，此功能非常有用，或者使用不同的方案进行编码特殊字符，比什么建议由[QUrl](qurl.html)。

通过QByteArray中的（值）至_query_（空[QByteArray](qbytearray.html)）完全取消设置的查询。然而，路过的值[QByteArray](qbytearray.html)（ “”）将查询设置为空值，因为如果原始URL有一个孤独的“ ？ ” 。

**See also** [encodedQuery](qurl.html#encodedQuery)（）和[hasQuery](qurl.html#hasQuery)（ ） 。

```
QUrl.setEncodedQueryItems (self, list-of-tuple-of-QByteArray-QByteArray query)
```

URL的查询字符串设置为的编码版本_query_。的内容_query_被转换为字符串内部，每对由pairDelimiter （ ）返回的字符，键和值分隔由valueDelimiter （分隔） 。

注：此功能不确认键 - 值对的编码正确。它是调用者的责任，以确保查询的分隔符的编码正确，如果有的话。

此功能被引入Qt的4.4 。

**See also** [setQueryDelimiters](qurl.html#setQueryDelimiters)（ ）[encodedQueryItems](qurl.html#encodedQueryItems)（）和[setQueryItems](qurl.html#setQueryItems)（ ） 。

```
QUrl.setEncodedUrl (self, QByteArray url)
```

通过解析的内容构造一个URL_encodedUrl_。

_encodedUrl_被假定为一个URL字符串的百分比编码形式，只包含ASCII字符。

使用[isValid](qurl.html#isValid)（ ） ，以确定是否一个有效的URL构建。

**See also** [setUrl](qurl.html#setUrl)（ ） 。

```
QUrl.setEncodedUrl (self, QByteArray url, ParsingMode mode)
```

通过解析的内容构造一个URL_encodedUrl_使用给定的_parsingMode_。

```
QUrl.setEncodedUserName (self, QByteArray userName)
```

设定URL的用户名的百分比编码_userName_。该_userName_是在URL的权限的用户信息元素的一部分，如描述[setUserInfo](qurl.html#setUserInfo)（ ） 。

注：此功能不会验证_userName_被正确编码。它是调用者的责任，以确保任何分隔符（如冒号或斜线）被正确编码。

此功能被引入Qt的4.4 。

**See also** [setUserName](qurl.html#setUserName)（ ）[encodedUserName](qurl.html#encodedUserName)（）和[setUserInfo](qurl.html#setUserInfo)（ ） 。

```
QUrl.setFragment (self, QString fragment)
```

设置URL的片段_fragment_。该片段是URL的最后部分，通过一个“＃”后面字符的字符串来表示。它通常用于在HTTP进行指的是页面上的某条链路或点：

![](../img/qurl-fragment.png)

的片段，有时也被称为URL为“参考” 。

路过的QString （的说法） （空[QString](qstring.html)）将取消设置的片段。传递的参数[QString](qstring.html)（ “”） （空但不为空[QString](qstring.html)）将设置片段为空字符串（就像原始的URL了一个孤独的“＃” ） 。

**See also** [fragment](qurl.html#fragment)（）和[hasFragment](qurl.html#hasFragment)（ ） 。

```
QUrl.setHost (self, QString host)
```

设置URL的主机_host_。主机是权威的一部分。

**See also** [host](qurl.html#host)（）和[setAuthority](qurl.html#setAuthority)（ ） 。

```
QUrl.setIdnWhitelist (QStringList)
```

集顶级域名（TLD ）中被允许有非ASCII字符的域值的白名单_list_。

请注意，如果你调用这个函数，你需要做这样**`\em`**你开始可能访问任何线程之前[idnWhitelist](qurl.html#idnWhitelist)（ ） 。

Qt拥有自带包含已发布国际化域名（IDN ）和规则的支持，以保证没有欺骗同样可以看的字符（如拉丁小写字母之间发生的互联网顶级域的默认列表`'a'`和西里尔当量，这在大多数字体是视觉上相同） 。

这份清单会定期维护，如登记发布新规则。

这个功能是为那些谁需要操作的列表，以添加或删除顶级域名。这是不建议改变其用途以外的其他测试值，因为它可能会暴露用户的安全风险。

这个函数中引入了Qt 4.2中。

**See also** [idnWhitelist](qurl.html#idnWhitelist)（ ） 。

```
QUrl.setPassword (self, QString password)
```

设定URL的密码_password_。该_password_是在URL的权限的用户信息元素的一部分，如描述[setUserInfo](qurl.html#setUserInfo)（ ） 。

**See also** [password](qurl.html#password)（）和[setUserInfo](qurl.html#setUserInfo)（ ） 。

```
QUrl.setPath (self, QString path)
```

设置的URL的路径_path_。该路径是自带的权威之后，但在查询字符串之前的URL的一部分。

![](../img/qurl-ftppath.png)

对于非分层方案，路径将是一切按照计划的声明，如下面的示例所示：

![](../img/qurl-mailtopath.png)

**See also** [path](qurl.html#pathx)（ ） 。

```
QUrl.setPort (self, int port)
```

设置URL的端口_port_。该港口是URL的权威的一部分，如描述[setAuthority](qurl.html#setAuthority)（ ） 。

_port_必须在0到65535之间的包容性。端口设置为-1表示该端口是不确定的。

**See also** [port](qurl.html#port)（ ） 。

```
QUrl.setQueryDelimiters (self, str valueDelimiter, str pairDelimiter)
```

设置用于键和值之间的分隔字符，并在URL的查询字符串键值对之间。默认值为分隔符是“=” ，默认对分隔符是“＆” 。

![](../img/qurl-querystring.png)

_valueDelimiter_将用于从值分离键和_pairDelimiter_将用于单独的键 - 值对。在查询字符串中的键和值的编码表示这些分隔字符出现的所有百分比编码。

If _valueDelimiter_被设置为“ - ”和_pairDelimiter_是'/' ，上面的查询字符串将代替来表示是这样的：

```
 http://www.example.com/cgi-bin/drawgraph.cgi?type-pie/color-green

```

调用此函数不改变目前的查询字符串的分隔符。它只会影响[queryItems](qurl.html#queryItems)（ ）[setQueryItems](qurl.html#setQueryItems)（）和addQueryItems （） 。

```
QUrl.setQueryItems (self, list-of-tuple-of-QString-QString query)
```

URL的查询字符串设置为的编码版本_query_。的内容_query_被转换为字符串内部，每对由pairDelimiter （ ）返回的字符，键和值分隔由valueDelimiter （分隔） 。

**Note:**此方法不编码空格（ ASCII码0X20 ）为加号（+ ）标志，就像HTML表单做。如果你需要这种编码方式，你必须自己编码值，并使用QUrl.setEncodedQueryItems 。

**See also** [setQueryDelimiters](qurl.html#setQueryDelimiters)（ ）[queryItems](qurl.html#queryItems)（）和[setEncodedQueryItems](qurl.html#setEncodedQueryItems)（ ） 。

```
QUrl.setScheme (self, QString scheme)
```

设置URL的计划_scheme_。作为一个方案只能包含ASCII字符，没有转换或编码完成对输入。

该计划描述了URL的类型（或协议） 。 “：”它是由一个或多个ASCII字符，在开始的URL ，并且后跟一个表示。下面的例子显示了一个URL如该计划是“ ftp”的：

![](../img/qurl-authority2.png)

该方案还可以是空的，在这种情况下该URL被解释为相。

**See also** [scheme](qurl.html#scheme)（）和[isRelative](qurl.html#isRelative)（ ） 。

```
QUrl.setUrl (self, QString url)
```

通过解析的内容构造一个URL_url_。

_url_被假定为Unicode格式，不带％的编码。

调用[isValid](qurl.html#isValid)（ ）会告诉一个有效的URL是否被建造。

**See also** [setEncodedUrl](qurl.html#setEncodedUrl)（ ） 。

```
QUrl.setUrl (self, QString url, ParsingMode mode)
```

这是一个重载函数。

解析_url_使用该模式解析_parsingMode_。

**See also** [setEncodedUrl](qurl.html#setEncodedUrl)（ ） 。

```
QUrl.setUserInfo (self, QString userInfo)
```

设置URL的用户信息来_userInfo_。用户信息是URL的权威的可选部分，如第[setAuthority](qurl.html#setAuthority)().

用户信息包括用户名和任选的密码，由一个分离的“：” 。如果密码是空的，结肠必须被省略。下面的例子显示了一个有效的用户信息字符串：

![](../img/qurl-authority3.png)

**See also** [userInfo](qurl.html#userInfo)（ ）[setUserName](qurl.html#setUserName)（ ）[setPassword](qurl.html#setPassword)（）和[setAuthority](qurl.html#setAuthority)（ ） 。

```
QUrl.setUserName (self, QString userName)
```

设定URL的用户名_userName_。该_userName_是在URL的权限的用户信息元素的一部分，如描述[setUserInfo](qurl.html#setUserInfo)（ ） 。

**See also** [setEncodedUserName](qurl.html#setEncodedUserName)（ ）[userName](qurl.html#userName)（）和[setUserInfo](qurl.html#setUserInfo)（ ） 。

```
QUrl.swap (self, QUrl other)
```

交换链接_other_与此URL 。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QByteArray QUrl.toAce (QString)
```

[

返回给定域名的ASCII兼容编码_domain_。此函数的结果被认为是等同于_domain_。

将ASCII兼容编码（ACE ）是由RFC 3490 ， RFC 3491和RFC 3492中定义。它是国际化域名的应用（ IDNA ）规范，它允许域名（如部分`"example.com"`）使用国际字符写入。

这个函数返回一个空QByteArra如果_domain_是不是一个有效的主机名。请注意，特别是IPv6文本不是有效的域名。

这个函数中引入了Qt 4.2中。

](qbytearray.html)

```
QByteArray QUrl.toEncoded (self, FormattingOptions options = QUrl.None)
```

[](qbytearray.html)

[返回URL的编码表示，如果是有效的，否则空](qbytearray.html)[QByteArray](qbytearray.html)返回。该输出可以通过传递标志与定制_options_。

用户信息，路径和片段都转换为UTF- 8 ，而所有非ASCII字符，然后％的编码。主机名是使用Punycode的编码。

```
QString QUrl.toLocalFile (self)
```

返回URL格式化为一个本地文件路径的路径。返回的路径将使用正斜杠，即使它最初是从一个与反斜杠创建。

如果这个URL中包含一个非空主机名，它会被编码的返回值在中小企业网络（例如， “ / /服务器名/路径/到/ file.txt的” ）发现的形式。

如果这是一个相对URL ，在Qt 4.x的这个函数返回的路径，以保持向后兼容性。这将改变从5.0起。那么路径是唯一的网址如该计划是“文件”返回，并为所有其他URL的返回空字符串。

**See also** [fromLocalFile](qurl.html#fromLocalFile)（）和[isLocalFile](qurl.html#isLocalFile)（ ） 。

```
QByteArray QUrl.toPercentEncoding (QString input, QByteArray exclude = QByteArray(), QByteArray include = QByteArray())
```

[

返回的编码副本_input_。_input_首先被转化为UTF -8 ，和所有的ASCII字符是不是在毫无保留的组是百分之编码。为了防止字符被编码的百分之通过他们来_exclude_。要强制字符是百分比编码传递给他们_include_。

](qbytearray.html)

[未保留的定义是： ALPHA / DIGIT /“ - ”/“。 ” / “](qbytearray.html)[_](index.html)“/” 〜“

```
 [QByteArray](qbytearray.html) ba = [QUrl](qurl.html).toPercentEncoding("{a fishy string?}", "{}", "s");
 qDebug(ba.constData());
 // prints "{a fi%73hy %73tring%3F}"

```

```
QString QUrl.topLevelDomain (self)
```

返回URL的TLD （顶级域名） ， （如。 co.uk ， 。净额） 。请注意，返回值前面带一个“。”除非该网址没有包含有效的顶级域名，在这种情况下，函数返回一个空字符串。

此功能被引入Qt的4.8 。

```
QByteArray QUrl.toPunycode (QString)
```

[

```
QString QUrl.toString (self, FormattingOptions options = QUrl.None)
```

返回URL的人显示的字符串表示形式。该输出可以通过传递标志与定制_options_。

](qbytearray.html)

[**See also**](qbytearray.html) [FormattingOptions](qurl.html#FormattingOption-enum)和[toEncoded](qurl.html#toEncoded)（ ） 。

```
QString QUrl.userInfo (self)
```

返回URL的用户信息，或空字符串，如果用户信息是不确定的。

**See also** [setUserInfo](qurl.html#setUserInfo)（ ） 。

```
QString QUrl.userName (self)
```

返回如果它被定义URL的用户名;否则返回空字符串。

**See also** [setUserName](qurl.html#setUserName)（）和[encodedUserName](qurl.html#encodedUserName)（ ） 。

```
bool QUrl.__eq__ (self, QUrl url)
```

```
bool QUrl.__ge__ (self, QUrl url)
```

```
int QUrl.__hash__ (self)
```

```
bool QUrl.__lt__ (self, QUrl url)
```

```
bool QUrl.__ne__ (self, QUrl url)
```

```
str QUrl.__repr__ (self)
```