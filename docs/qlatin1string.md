# QLatin1String Class Reference

## [[QtCore](index.htm) module]

该QLatin1String类提供了简单包装的一个US-ASCII/Latin-1编码的字符串文字。[More...](#details)

### Methods

*   `__init__ (self, str s)`
*   `__init__ (self, QLatin1String)`
*   `str latin1 (self)`

### Special Methods

*   `bool __eq__ (self, QString s)`
*   `bool __eq__ (self, QLatin1String s2)`
*   `bool __eq__ (self, QStringRef s2)`
*   `bool __ge__ (self, QString s)`
*   `bool __ge__ (self, QLatin1String s2)`
*   `bool __gt__ (self, QString s)`
*   `bool __gt__ (self, QLatin1String s2)`
*   `bool __le__ (self, QString s)`
*   `bool __le__ (self, QLatin1String s2)`
*   `bool __lt__ (self, QString s)`
*   `bool __lt__ (self, QLatin1String s2)`
*   `bool __ne__ (self, QString s)`
*   `bool __ne__ (self, QLatin1String s2)`
*   `bool __ne__ (self, QStringRef s2)`
*   `str __repr__ (self)`

* * *

## Detailed Description

这个类可以醃制。

该QLatin1String类提供了简单包装的一个US-ASCII/Latin-1编码的字符串文字。

许多[QString](qstring.html)的成员函数重载接受`const char *`而不是[QString](qstring.html)。这包括拷贝构造函数，赋值操作符，比较操作符，以及其他各种功能，如[insert()](qstring.html#insert)，[replace()](qstring.html#replace)和[indexOf()](qstring.html#indexOf)。这些功能通常是优化，以避免建设[QString](qstring.html)为对象`const char *`数据。例如，假设`str`是[QString](qstring.html)，

```
 if (str == "auto" || str == "extern"
         || str == "static" || str == "register") {
     ...
 }

```

是不是快很多

```
 if (str == [QString](qstring.html)("auto") || str == [QString](qstring.html)("extern")
         || str == [QString](qstring.html)("static") || str == [QString](qstring.html)("register")) {
     ...
 }

```

因为它没有构造四个临时[QString](qstring.html)对象，使字符数据的深层副本。

定义应用程序`QT_NO_CAST_FROM_ASCII`（在所说明[QString](qstring.html)文档）不具有访问[QString](qstring.html)的`const char *`API。提供指定固定的Latin-1的字符串的有效方式， Qt提供了QLatin1String ，这是围绕一个只是一个非常薄的包装`const char *`。使用QLatin1String ，上面的例子代码变得

```
 if (str == QLatin1String("auto")
         || str == QLatin1String("extern")
         || str == QLatin1String("static")
         || str == QLatin1String("register") {
     ...
 }

```

这是一个有点长一些，但它提供了完全相同的利益作为代码的第一个版本，并且比使用转换Latin-1的字符串更快[QString.fromLatin1](qstring.html#fromLatin1)（ ） 。

多亏了[QString](qstring.html)（常量QLatin1String ＆ ）构造函数， QLatin1String可以到处使用[QString](qstring.html)预计。例如：

```
 [QLabel](qlabel.html) *label = new [QLabel](qlabel.html)(QLatin1String("MOD"), this);

```

* * *

## Method Documentation

```
QLatin1String.__init__ (self, str s)
```

构造一个[QLatin1String](qlatin1string.html)对象，它存储_str_。注意，如果_str_为0时，将创建一个空字符串，这种情况下是通过处理[QString](qstring.html)。

字符串数据是_not_复制。调用者必须能够保证_str_也不会被删除或修改，只要该[QLatin1String](qlatin1string.html)对象存在。

**See also** [latin1](qlatin1string.html#latin1)（ ） 。

```
QLatin1String.__init__ (self, QLatin1String)
```

```
str QLatin1String.latin1 (self)
```

返回存储在此对象中的Latin-1的字符串。

```
bool QLatin1String.__eq__ (self, QString s)
```

```
bool QLatin1String.__eq__ (self, QLatin1String s2)
```

```
bool QLatin1String.__eq__ (self, QStringRef s2)
```

```
bool QLatin1String.__ge__ (self, QString s)
```

```
bool QLatin1String.__ge__ (self, QLatin1String s2)
```

```
bool QLatin1String.__gt__ (self, QString s)
```

```
bool QLatin1String.__gt__ (self, QLatin1String s2)
```

```
bool QLatin1String.__le__ (self, QString s)
```

```
bool QLatin1String.__le__ (self, QLatin1String s2)
```

```
bool QLatin1String.__lt__ (self, QString s)
```

```
bool QLatin1String.__lt__ (self, QLatin1String s2)
```

```
bool QLatin1String.__ne__ (self, QString s)
```

```
bool QLatin1String.__ne__ (self, QLatin1String s2)
```

```
bool QLatin1String.__ne__ (self, QStringRef s2)
```

```
str QLatin1String.__repr__ (self)
```