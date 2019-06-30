# QTextBlockUserData Class Reference

## [[QtGui](index.htm) module]

该QTextBlockUserData类用于自定义数据与文本块相关联。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextBlockUserData)`

* * *

## Detailed Description

该QTextBlockUserData类用于自定义数据与文本块相关联。

QTextBlockUserData提供了一个抽象的接口，用于特定应用的用户数据与文本块的关联容器类[QTextDocument](qtextdocument.html)。

通常，这个类的子类提供的功能，以允许数据被存储和检索，以及实例使用附加到文本块[QTextBlock.setUserData](qtextblock.html#setUserData)（ ） 。这使得它可以存储在可以安全地被应用程序检索的方式每个文本块的附加数据。

每个子类都必须提供析构函数的重新实现，以确保任何私人数据被自动清除，当用户数据对象被删除。

* * *

## Method Documentation

```
QTextBlockUserData.__init__ (self)
```

```
QTextBlockUserData.__init__ (self, QTextBlockUserData)
```