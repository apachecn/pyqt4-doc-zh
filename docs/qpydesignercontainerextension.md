# QPyDesignerContainerExtension Class Reference

## [[QtDesigner](index.htm) module]

继承[QObject](qobject.html)和[QDesignerContainerExtension](qdesignercontainerextension.html)。

### Methods

*   `__init__ (self, QObject parent)`

* * *

## Detailed Description

该QPyDesignerContainerExtension类是提供给解决的事实，这是不可能的Python类从多个Qt类派生。

为网页添加到Qt Designer中的工作空间自定义多页的容器，应实现从QPyDesignerContainerExtension派生的Python类，而不是一个源自[QObject](qobject.html)和[QDesignerContainerExtension](qdesignercontainerextension.html)。

* * *

## Method Documentation

```
QPyDesignerContainerExtension.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。