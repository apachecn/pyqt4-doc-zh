# QPyDesignerCustomWidgetPlugin Class Reference

## [[QtDesigner](index.htm) module]

继承[QObject](qobject.html)和[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)。

### Methods

*   `__init__ (self, QObject parent = None)`

* * *

## Detailed Description

该QPyDesignerCustomWidgetPlugin类是提供给解决的事实，这是不可能的Python类从多个Qt类派生。

为了编写一个插件，它包含一个自定义窗口小部件，应实现从QPyDesignerCustomWidgetPlugin派生的Python类，而不是一个源自[QObject](qobject.html)和[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)。

* * *

## Method Documentation

```
QPyDesignerCustomWidgetPlugin.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。