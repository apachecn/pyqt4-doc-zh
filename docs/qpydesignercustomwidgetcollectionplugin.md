# QPyDesignerCustomWidgetCollectionPlugin Class Reference

## [[QtDesigner](index.htm) module]

继承[QObject](qobject.html)和[QDesignerCustomWidgetCollectionInterface](qdesignercustomwidgetcollectioninterface.html)。

### Methods

*   `__init__ (self, QObject parent = None)`

* * *

## Detailed Description

该QPyDesignerCustomWidgetCollectionPlugin类是提供给解决的事实，这是不可能的Python类从多个Qt类派生。

为了编写一个插件，包含了几个自定义部件，应实现从QPyDesignerCustomWidgetCollectionPlugin派生的Python类，而不是一个源自[QObject](qobject.html)和[QDesignerCustomWidgetCollectionInterface](qdesignercustomwidgetcollectioninterface.html)。

* * *

## Method Documentation

```
QPyDesignerCustomWidgetCollectionPlugin.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。