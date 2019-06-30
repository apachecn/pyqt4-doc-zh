# QProcessEnvironment Class Reference

## [[QtCore](index.htm) module]

该QProcessEnvironment类认为可以传递给一个程序的环境变量。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QProcessEnvironment other)`
*   `clear (self)`
*   `bool contains (self, QString name)`
*   `insert (self, QString name, QString value)`
*   `insert (self, QProcessEnvironment e)`
*   `bool isEmpty (self)`
*   `QStringList keys (self)`
*   `remove (self, QString name)`
*   `QStringList toStringList (self)`
*   `QString value (self, QString name, QString defaultValue = QString())`

### Static Methods

*   `QProcessEnvironment systemEnvironment ()`

### Special Methods

*   `bool __eq__ (self, QProcessEnvironment other)`
*   `bool __ne__ (self, QProcessEnvironment other)`

* * *

## Detailed Description

该QProcessEnvironment类认为可以传递给一个程序的环境变量。

一个进程的环境是由一组被称为环境变量key = value对的。该QProcessEnvironment类包装的概念，并可以方便地操纵这些变量。它的意思也可以一起使用[QProcess](qprocess.html)，设置为子进程的环境。它不能被用于改变当前进程的环境。

可以用以下方式获得的调用进程的环境[QProcessEnvironment.systemEnvironment](qprocessenvironment.html#systemEnvironment)（ ） 。

在Unix系统中，变量名称是区分大小写的。出于这个原因，这个类不会接触到变量的名称。还要注意的Unix环境允许两个变量名和内容，包含任意的二进制数据（除NUL字符），但是这是不支持QProcessEnvironment 。这个类只支持名称和可编码是由当前区域设置（见QTextCodec.codecForLocale ）值。

在Windows中，变量名是大小写不敏感的。因此， QProcessEnvironment总是大写的名字，做不区分大小写的比较。

在Windows CE上，环境的概念并不存在。这个类将保持与其他平台之间的兼容性设置的值，但设置的值将不会对正在创建的过程没有影响。

* * *

## Method Documentation

```
QProcessEnvironment.__init__ (self)
```

创建一个新的[QProcessEnvironment](qprocessenvironment.html)对象。此构造函数创建一个空的环境。如果在设置[QProcess](qprocess.html)，这将导致当前的环境变量被删除。

```
QProcessEnvironment.__init__ (self, QProcessEnvironment other)
```

创建[QProcessEnvironment](qprocessenvironment.html)对象，它是一个拷贝_other_。

```
QProcessEnvironment.clear (self)
```

移除所有这一切key = value对[QProcessEnvironment](qprocessenvironment.html)对象，使之为空。

**See also** [isEmpty](qprocessenvironment.html#isEmpty)（）和[systemEnvironment](qprocessenvironment.html#systemEnvironment)（ ） 。

```
bool QProcessEnvironment.contains (self, QString name)
```

返回True如果name环境变量_name_在这个被发现[QProcessEnvironment](qprocessenvironment.html)对象。

在Windows中，变量名是大小写不敏感的，所以关键是转换为大写搜索之前。在其他系统上，名称是区分大小写的，因此没有改造中的应用。

**See also** [insert](qprocessenvironment.html#insert)（）和[value](qprocessenvironment.html#value)（ ） 。

```
QProcessEnvironment.insert (self, QString name, QString value)
```

插入名称的环境变量_name_和内容_value_这个[QProcessEnvironment](qprocessenvironment.html)对象。如果该变量已经存在，它被替换为新值。

在Windows中，变量名是大小写不敏感的，所以插入之前这个函数总是变大写变量名。在其他系统上，名称是区分大小写的，所以没有变换应用。

在大多数系统中，没有内容插入一个变量将有应用，如果该变量没有被设置在所有相同的效果。然而，为了保证不存在任何不兼容，要删除一个变量，请使用[remove](qprocessenvironment.html#remove)（）函数。

**See also** [contains](qprocessenvironment.html#contains)（ ）[remove](qprocessenvironment.html#remove)（）和[value](qprocessenvironment.html#value)（ ） 。

```
QProcessEnvironment.insert (self, QProcessEnvironment e)
```

这是一个重载函数。

插入的内容_e_在这[QProcessEnvironment](qprocessenvironment.html)对象。在这个对象的变量，也存在于_e_将被复盖。

此功能被引入Qt的4.8 。

```
bool QProcessEnvironment.isEmpty (self)
```

返回True如果[QProcessEnvironment](qprocessenvironment.html)对象是空的：那就是有没有设置key = value对。

**See also** [clear](qprocessenvironment.html#clear)（ ）[systemEnvironment](qprocessenvironment.html#systemEnvironment)（）和[insert](qprocessenvironment.html#insert)（ ） 。

```
QStringList QProcessEnvironment.keys (self)
```

返回包含在这一切的变数名称的列表[QProcessEnvironment](qprocessenvironment.html)对象。

此功能被引入Qt的4.8 。

```
QProcessEnvironment.remove (self, QString name)
```

删除所确定的环境变量_name_由此[QProcessEnvironment](qprocessenvironment.html)对象。如果该变量不存在之前，没有任何反应。

在Windows中，变量名是大小写不敏感的，所以关键是转换为大写搜索之前。在其他系统上，名称是区分大小写的，因此没有改造中的应用。

**See also** [contains](qprocessenvironment.html#contains)（ ）[insert](qprocessenvironment.html#insert)（）和[value](qprocessenvironment.html#value)（ ） 。

```
QProcessEnvironment QProcessEnvironment.systemEnvironment ()
```

[

该systemEnvironment函数返回调用进程的环境。

](qprocessenvironment.html)

[它返回一个](qprocessenvironment.html)[QProcessEnvironment](qprocessenvironment.html)。这个函数不缓存系统环境。因此，有可能获得环境的更新版本，如果低级别的C库函数如`setenv`OT`putenv`已被调用。

但是请注意，重复调用此函数将重新[QProcessEnvironment](qprocessenvironment.html)对象，这是一个非平凡的操作。

此功能被引入Qt的4.6 。

**See also** [QProcess.systemEnvironment](qprocess.html#systemEnvironment)（ ） 。

```
QStringList QProcessEnvironment.toStringList (self)
```

这个转换[QProcessEnvironment](qprocessenvironment.html)对象转换成字符串，一个用于设置每个环境变量的列表。环境变量的名称和它的值是由一个平等的字符（' = '）隔开。

该[QStringList](qstringlist.html)此函数返回的内容是适合与QProcess.setEnvironment功能的使用。然而，它是推荐使用QProcess.setProcessEnvironment代替，因为这将避免不必要的数据的复制。

**See also** [systemEnvironment](qprocessenvironment.html#systemEnvironment)（ ）[QProcess.systemEnvironment](qprocess.html#systemEnvironment)（ ）[QProcess.environment](qprocess.html#environment)（）和[QProcess.setEnvironment](qprocess.html#setEnvironment)（ ） 。

```
QString QProcessEnvironment.value (self, QString name, QString defaultValue = QString())
```

这个搜索[QProcessEnvironment](qprocessenvironment.html)对象，用于确定一个变量_name_并返回它的值。如果在该对象中找到的变量，则_defaultValue_返回来代替。

在Windows中，变量名是大小写不敏感的，所以关键是转换为大写搜索之前。在其他系统上，名称是区分大小写的，因此没有改造中的应用。

**See also** [contains](qprocessenvironment.html#contains)（ ）[insert](qprocessenvironment.html#insert)（）和[remove](qprocessenvironment.html#remove)（ ） 。

```
bool QProcessEnvironment.__eq__ (self, QProcessEnvironment other)
```

```
bool QProcessEnvironment.__ne__ (self, QProcessEnvironment other)
```