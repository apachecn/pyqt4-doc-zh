# QStyleFactory Class Reference

## [[QtGui](index.htm) module]

该QStyleFactory类创建[QStyle](qstyle.html)对象。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleFactory)`

### Static Methods

*   `QStyle create (QString)`
*   `QStringList keys ()`

* * *

## Detailed Description

该QStyleFactory类创建[QStyle](qstyle.html)对象。

该[QStyle](qstyle.html)类是封装了图形用户界面的外观和感觉的抽象基类。 QStyleFactory创建一个[QStyle](qstyle.html)使用对象[create](qstylefactory.html#create)（）函数和密钥识别的样式。该样式是内置的或动态的样式插件加载（见[QStylePlugin](index.htm)） 。

有效密钥可使用检索到的[keys](qstylefactory.html#keys)（）函数。通常情况下，他们包括“窗口” ， “主题” ， “ CDE ” ， “ PLASTIQUE ”和“ cleanlooks ” 。根据不同的平台上， “ windowsxp系统” ， “WindowsVista兼容”和“麦金塔”可能是可用的。请注意，键是区分大小写的。

* * *

## Method Documentation

```
QStyleFactory.__init__ (self)
```

```
QStyleFactory.__init__ (self, QStyleFactory)
```

```
QStyle QStyleFactory.create (QString)
```

[](qstyle.html)

[创建并返回一个](qstyle.html)[QStyle](qstyle.html)匹配给定对象_key_，或返回0 ，如果没有匹配的风格被发现。

两个内置样式和款式风格的插件中查询匹配的风格。

**Note:**使用的密钥不区分大小写。

**See also** [keys](qstylefactory.html#keys)（ ） 。

```
QStringList QStyleFactory.keys ()
```

返回有效的密钥列表，即键这个工厂可以创建样式。

**See also** [create](qstylefactory.html#create)（ ） 。