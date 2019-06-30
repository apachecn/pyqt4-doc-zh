# QDeclarativeError Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeError类封装了QML错误。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDeclarativeError)`
*   `int column (self)`
*   `QString description (self)`
*   `bool isValid (self)`
*   `int line (self)`
*   `setColumn (self, int)`
*   `setDescription (self, QString)`
*   `setLine (self, int)`
*   `setUrl (self, QUrl)`
*   `QString toString (self)`
*   `QUrl url (self)`

* * *

## Detailed Description

该QDeclarativeError类封装了QML错误。

QDeclarativeError包含错误的文本描述，以及位置信息（文件，行，列）。该[toString](qdeclarativeerror.html#toString)（ ）方法创建一个包含所有这些信息，例如单行，人类可读的字符串：

```
 file:///home/user/test.qml:7:8: Invalid property assignment: double expected

```

您可以使用[qDebug](index.htm#qDebug)（）或[qWarning](index.htm#qWarning)（）来输出错误到控制台。此方法将尝试打开由错误指示的文件，并包含额外的上下文信息。

```
 file:///home/user/test.qml:7:8: Invalid property assignment: double expected
         y: "hello"
            ^

```

* * *

## Method Documentation

```
QDeclarativeError.__init__ (self)
```

创建一个空的错误对象。

```
QDeclarativeError.__init__ (self, QDeclarativeError)
```

创建副本_other_。

```
int QDeclarativeError.column (self)
```

返回错误的列号。

**See also** [setColumn](qdeclarativeerror.html#setColumn)（ ） 。

```
QString QDeclarativeError.description (self)
```

返回的错误描述。

**See also** [setDescription](qdeclarativeerror.html#setDescription)（ ） 。

```
bool QDeclarativeError.isValid (self)
```

返回True如果这个错误是有效的，否则为False 。

```
int QDeclarativeError.line (self)
```

返回错误的行号。

**See also** [setLine](qdeclarativeerror.html#setLine)（ ） 。

```
QDeclarativeError.setColumn (self, int)
```

设置错误_column_数。

**See also** [column](qdeclarativeerror.html#column)（ ） 。

```
QDeclarativeError.setDescription (self, QString)
```

设置错误_description_。

**See also** [description](qdeclarativeerror.html#description)（ ） 。

```
QDeclarativeError.setLine (self, int)
```

设置错误_line_数。

**See also** [line](qdeclarativeerror.html#line)（ ） 。

```
QDeclarativeError.setUrl (self, QUrl)
```

设置_url_对于导致该错误的文件。

**See also** [url](qdeclarativeerror.html#url)（ ） 。

```
QString QDeclarativeError.toString (self)
```

返回错误为人类可读的字符串。

```
QUrl QDeclarativeError.url (self)
```

[

返回的URL，导致此错误的文件。

](qurl.html)

[**See also**](qurl.html) [setUrl](qdeclarativeerror.html#setUrl)（ ） 。