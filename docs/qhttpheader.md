# QHttpHeader Class Reference

## [[QtNetwork](index.htm) module]

该QHttpHeader类包含HTTP头信息。[More...](#details)

通过继承[QHttpRequestHeader](qhttprequestheader.html)和[QHttpResponseHeader](qhttpresponseheader.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QHttpHeader header)`
*   `__init__ (self, QString str)`
*   `addValue (self, QString key, QString value)`
*   `QStringList allValues (self, QString key)`
*   `int contentLength (self)`
*   `QString contentType (self)`
*   `bool hasContentLength (self)`
*   `bool hasContentType (self)`
*   `bool hasKey (self, QString key)`
*   `bool isValid (self)`
*   `QStringList keys (self)`
*   `int majorVersion (self)`
*   `int minorVersion (self)`
*   `bool parse (self, QString str)`
*   `bool parseLine (self, QString line, int number)`
*   `removeAllValues (self, QString key)`
*   `removeValue (self, QString key)`
*   `setContentLength (self, int len)`
*   `setContentType (self, QString type)`
*   `setValid (self, bool)`
*   `setValue (self, QString key, QString value)`
*   `setValues (self, list-of-tuple-of-QString-QString values)`
*   `QString toString (self)`
*   `QString value (self, QString key)`
*   `list-of-tuple-of-QString-QString values (self)`

* * *

## Detailed Description

该QHttpHeader类包含HTTP头信息。

在大多数情况下，你应该使用这个类的更专业的衍生物，[QHttpResponseHeader](qhttpresponseheader.html)和[QHttpRequestHeader](qhttprequestheader.html)，而不是直接使用QHttpHeader 。

QHttpHeader提供的HTTP标头字段。 HTTP头域由一个名称，后跟一个冒号，一个空格，和字段值。 （参见RFC 1945 ）。字段名不区分大小写。一个典型的标头栏位看起来像这样：

```
 content-type: text/html

```

在API的报头字段的名称被称为“键”和内容被称为“价值” 。您可以获取和设置一个报头字段的值，用其与关键[value](qhttpheader.html#value)（）和[setValue](qhttpheader.html#setValue)（ ），例如

```
 header.setValue("content-type", "text/html");
 [QString](qstring.html) contentType = header.value("content-type");

```

有些领域是如此普遍， getter和setter方法​​是为他们提供一个方便的替代品使用[value](qhttpheader.html#value)（）和[setValue](qhttpheader.html#setValue)（ ），例如[contentLength](qhttpheader.html#contentLength)（）和[contentType](qhttpheader.html#contentType)（ ）[setContentLength](qhttpheader.html#setContentLength)（）和[setContentType](qhttpheader.html#setContentType)（ ） 。

每头键都有一个_single_与它相关联的值。如果设置的值已经存在一个关键的前一个值将被丢弃。

* * *

## Method Documentation

```
QHttpHeader.__init__ (self)
```

构造一个空的HTTP标头。

```
QHttpHeader.__init__ (self, QHttpHeader header)
```

构造的副本_header_。

```
QHttpHeader.__init__ (self, QString str)
```

构造一个HTTP头的_str_。

这个构造函数解析字符串_str_为报头字段，并添加该信息。该_str_应该由一个或多个的“ \ r \ n ”分隔行;这些线路的格式应为关键，冒号，空格，值。

```
QHttpHeader.addValue (self, QString key, QString value)
```

添加一个新条目与_key_和_value_。

```
QStringList QHttpHeader.allValues (self, QString key)
```

返回与给定的所有条目_key_。如果没有条目有这_key_，则返回一个空字符串列表。

```
int QHttpHeader.contentLength (self)
```

返回特殊的HTTP标头字段的值`content-length`。

**See also** [setContentLength](qhttpheader.html#setContentLength)（）和[hasContentLength](qhttpheader.html#hasContentLength)（ ） 。

```
QString QHttpHeader.contentType (self)
```

返回特殊的HTTP标头字段的值`content-type`。

**See also** [setContentType](qhttpheader.html#setContentType)（）和[hasContentType](qhttpheader.html#hasContentType)（ ） 。

```
bool QHttpHeader.hasContentLength (self)
```

如果头具有特殊的HTTP标头字段中的条目，则返回True`content-length`否则返回False 。

**See also** [contentLength](qhttpheader.html#contentLength)（）和[setContentLength](qhttpheader.html#setContentLength)（ ） 。

```
bool QHttpHeader.hasContentType (self)
```

如果头具有特殊的HTTP标头字段中的条目，则返回True`content-type`否则返回False 。

**See also** [contentType](qhttpheader.html#contentType)（）和[setContentType](qhttpheader.html#setContentType)（ ） 。

```
bool QHttpHeader.hasKey (self, QString key)
```

如果HTTP头有一个给定的条目，则返回True_key_否则返回False 。

**See also** [value](qhttpheader.html#value)（ ）[setValue](qhttpheader.html#setValue)（）和[keys](qhttpheader.html#keys)（ ） 。

```
bool QHttpHeader.isValid (self)
```

返回True如果HTTP头是有效的，否则返回False 。

A [QHttpHeader](qhttpheader.html)是无效的，如果它是通过解析一个格式错误的字符串创建的。

```
QStringList QHttpHeader.keys (self)
```

返回在HTTP报头中的键的列表。

**See also** [hasKey](qhttpheader.html#hasKey)（ ） 。

```
int QHttpHeader.majorVersion (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回主协议版本的HTTP标头。

```
int QHttpHeader.minorVersion (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回未成年协议版本的HTTP标头。

```
bool QHttpHeader.parse (self, QString str)
```

```
bool QHttpHeader.parseLine (self, QString line, int number)
```

```
QHttpHeader.removeAllValues (self, QString key)
```

删除与该键中的所有条目_key_从HTTP标头。

```
QHttpHeader.removeValue (self, QString key)
```

删除与该键的条目_key_从HTTP标头。

**See also** [value](qhttpheader.html#value)（）和[setValue](qhttpheader.html#setValue)（ ） 。

```
QHttpHeader.setContentLength (self, int len)
```

设置特殊的HTTP标头字段的值`content-length`至_len_。

**See also** [contentLength](qhttpheader.html#contentLength)（）和[hasContentLength](qhttpheader.html#hasContentLength)（ ） 。

```
QHttpHeader.setContentType (self, QString type)
```

设置特殊的HTTP标头字段的值`content-type`至_type_。

**See also** [contentType](qhttpheader.html#contentType)（）和[hasContentType](qhttpheader.html#hasContentType)（ ） 。

```
QHttpHeader.setValid (self, bool)
```

```
QHttpHeader.setValue (self, QString key, QString value)
```

设置与该项目的值_key_至_value_。

如果没有条目_key_存在，一个新的项与给定_key_和_value_被创建。如果与一个条目_key_已经存在，则第一个值将被丢弃并用给定的替换_value_。

**See also** [value](qhttpheader.html#value)（ ）[hasKey](qhttpheader.html#hasKey)（）和[removeValue](qhttpheader.html#removeValue)（ ） 。

```
QHttpHeader.setValues (self, list-of-tuple-of-QString-QString values)
```

套头项是在键值对列表_values_。

**See also** [values](qhttpheader.html#values)（ ） 。

```
QString QHttpHeader.toString (self)
```

返回的HTTP标头的字符串表示形式。

该字符串是适合于采用一个构造函数使用[QString](qstring.html)。它是由线的格式：关键，冒号，空格，值， “ \ r \ N” 。

```
QString QHttpHeader.value (self, QString key)
```

返回与给定条目中的第一个值_key_。如果没有条目有这_key_，则返回一个空字符串。

**See also** [setValue](qhttpheader.html#setValue)（ ）[removeValue](qhttpheader.html#removeValue)（ ）[hasKey](qhttpheader.html#hasKey)（）和[keys](qhttpheader.html#keys)（ ） 。

```
list-of-tuple-of-QString-QString QHttpHeader.values (self)
```

返回头中的所有条目。

**See also** [setValues](qhttpheader.html#setValues)（ ） 。