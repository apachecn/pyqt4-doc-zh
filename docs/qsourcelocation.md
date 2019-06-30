# QSourceLocation Class Reference

## [[QtXmlPatterns](index.htm) module]

通过URI ，行和列在资源的QSourceLocation类标识的位置。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSourceLocation other)`
*   `__init__ (self, QUrl u, int line = -1, int column = -1)`
*   `int column (self)`
*   `bool isNull (self)`
*   `int line (self)`
*   `setColumn (self, int newColumn)`
*   `setLine (self, int newLine)`
*   `setUri (self, QUrl newUri)`
*   `QUrl uri (self)`

### Special Methods

*   `bool __eq__ (self, QSourceLocation other)`
*   `int __hash__ (self)`
*   `bool __ne__ (self, QSourceLocation other)`

* * *

## Detailed Description

通过URI ，行和列在资源的QSourceLocation类标识的位置。

QSourceLocation是具有三个属性的简单基础的价值类，[uri](qsourcelocation.html#uri)（ ）[line](qsourcelocation.html#line)（）和[column](qsourcelocation.html#column)（ ） ，那加在一起，确定某一个点在一个资源，例如文件或内存中的文件。

[line](qsourcelocation.html#line)（）和[column](qsourcelocation.html#column)（ ）是指字符数（不是字节数） ，他们都从1开始，而不是0 。

* * *

## Method Documentation

```
QSourceLocation.__init__ (self)
```

构建[QSourceLocation](qsourcelocation.html)不识别任何东西。

对于默认构造QSourceLocation （ ） ，[isNull](qsourcelocation.html#isNull)（）返回`true`。

```
QSourceLocation.__init__ (self, QSourceLocation other)
```

构造一个[QSourceLocation](qsourcelocation.html)即副本_other_。

```
QSourceLocation.__init__ (self, QUrl u, int line = -1, int column = -1)
```

构造一个[QSourceLocation](qsourcelocation.html)与URI_u_，行_l_和列_c_。

```
int QSourceLocation.column (self)
```

返回当前列号。列号指的是字符，而不是字节数。第一列是列1 ，而不是0 。默认值是-1 ，表明该列数是未知的。

**See also** [setColumn](qsourcelocation.html#setColumn)（ ） 。

```
bool QSourceLocation.isNull (self)
```

Returns `true`如果这[QSourceLocation](qsourcelocation.html)不识别任何东西。

对于构造一个默认的[QSourceLocation](qsourcelocation.html)，这个函数返回`true`。这同样适用于任何其它[QSourceLocation](qsourcelocation.html)谁[uri](qsourcelocation.html#uri)（）是无效的。

```
int QSourceLocation.line (self)
```

返回当前的行号。第一行号是1 ，而不是0 。默认值是-1，表示行数是未知的。

**See also** [setLine](qsourcelocation.html#setLine)（ ） 。

```
QSourceLocation.setColumn (self, int newColumn)
```

设置列数_newColumn_。 0是无效的列号。第一列号为1。

**See also** [column](qsourcelocation.html#column)（ ） 。

```
QSourceLocation.setLine (self, int newLine)
```

设置行号_newLine_。 0是无效的行号。第一行号为1。

**See also** [line](qsourcelocation.html#line)（ ） 。

```
QSourceLocation.setUri (self, QUrl newUri)
```

设置URI来_newUri_。

**See also** [uri](qsourcelocation.html#uri)（ ） 。

```
QUrl QSourceLocation.uri (self)
```

[](qurl.html)

[返回的资源，这](qurl.html)[QSourceLocation](qsourcelocation.html)指。例如，资源可以在本地文件系统中的文件，如果URI方案是`file`。

**See also** [setUri](qsourcelocation.html#setUri)（ ） 。

```
bool QSourceLocation.__eq__ (self, QSourceLocation other)
```

```
int QSourceLocation.__hash__ (self)
```

```
bool QSourceLocation.__ne__ (self, QSourceLocation other)
```