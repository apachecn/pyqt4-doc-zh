# QPyDesignerMemberSheetExtension Class Reference

## [[QtDesigner](index.htm) module]

继承[QObject](qobject.html)和[QDesignerMemberSheetExtension](qdesignermembersheetextension.html)。

### Methods

*   `__init__ (self, QObject parent)`

* * *

## Detailed Description

该QPyDesignerMemberSheetExtension类是提供给解决的事实，这是不可能的Python类从多个Qt类派生。

为了组态连接时，操纵Widget的成员函数，你应该实现从QPyDesignerMemberSheetExtension派生的Python类，而不是一个源自[QObject](qobject.html)和[QDesignerMemberSheetExtension](qdesignermembersheetextension.html)。

* * *

## Method Documentation

```
QPyDesignerMemberSheetExtension.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。