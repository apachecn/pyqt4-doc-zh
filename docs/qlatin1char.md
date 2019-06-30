# QLatin1Char Class Reference

## [[QtCore](index.htm) module]

该QLatin1Char类提供一个8位ASCII/Latin-1字符。[More...](#details)

### Methods

*   `__init__ (self, str c)`
*   `__init__ (self, QLatin1Char)`
*   `str toLatin1 (self)`
*   `int unicode (self)`

### Special Methods

*   `str __repr__ (self)`

* * *

## Detailed Description

这个类可以醃制。

该QLatin1Char类提供一个8位ASCII/Latin-1字符。

这个类是唯一有用的，以避免在编解码器的C字符串的业务[QChar](qchar.html)（ CH）构造函数。您可以通过编写避免它[QChar](qchar.html)（CH ，0）。

* * *

## Method Documentation

```
QLatin1Char.__init__ (self, str c)
```

构造的Latin-1字符_c_。当输入字符的编码被称为是Latin-1的这种构造应该被使用。

```
QLatin1Char.__init__ (self, QLatin1Char)
```

```
str QLatin1Char.toLatin1 (self)
```

拉丁- 1字符转换为字符的8位ASCII表示。

```
int QLatin1Char.unicode (self)
```

拉丁- 1字符转换为字符的16位编码的Unicode表示。

```
str QLatin1Char.__repr__ (self)
```