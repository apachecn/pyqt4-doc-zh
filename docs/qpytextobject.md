# QPyTextObject Class Reference

## [[QtGui](index.htm) module]

继承[QObject](qobject.html)和[QTextObjectInterface](qtextobjectinterface.html)。

### Methods

*   `__init__ (self, QObject parent = None)`

* * *

## Detailed Description

该QPyTextObject类是提供给解决的事实，这是不可能的Python类从多个Qt类派生。

为了创造新类型的文本对象，你可以添加到[QTextDocument](qtextdocument.html)你应该实现从QPyTextObject派生的Python类，而不是一个源自[QObject](qobject.html)和[QTextObjectInterface](qtextobjectinterface.html)。

* * *

## Method Documentation

```
QPyTextObject.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。