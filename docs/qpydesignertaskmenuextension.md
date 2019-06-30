# QPyDesignerTaskMenuExtension Class Reference

## [[QtDesigner](index.htm) module]

继承[QObject](qobject.html)和[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)。

### Methods

*   `__init__ (self, QObject parent)`

* * *

## Detailed Description

该QPyDesignerTaskMenuExtension类是提供给解决的事实，这是不可能的Python类从多个Qt类派生。

为了自定义条目添加到Qt Designer中的任务菜单中，你应该实现从QPyDesignerTaskMenuExtension派生的Python类，而不是一个源自[QObject](qobject.html)和[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)。

* * *

## Method Documentation

```
QPyDesignerTaskMenuExtension.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。