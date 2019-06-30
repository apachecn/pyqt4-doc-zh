# QHelpEngine Class Reference

## [[QtHelp](index.htm) module]

该QHelpEngine类提供​​的帮助引擎的内容和指标。[More...](#details)

继承[QHelpEngineCore](qhelpenginecore.html)。

### Methods

*   `__init__ (self, QString collectionFile, QObject parent = None)`
*   `QHelpContentModel contentModel (self)`
*   `QHelpContentWidget contentWidget (self)`
*   `QHelpIndexModel indexModel (self)`
*   `QHelpIndexWidget indexWidget (self)`
*   `QHelpSearchEngine searchEngine (self)`

* * *

## Detailed Description

该QHelpEngine类提供​​的帮助引擎的内容和指标。

* * *

## Method Documentation

```
QHelpEngine.__init__ (self, QString collectionFile, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的帮助引擎与给定_parent_。帮助引擎使用存储在信息_collectionFile_提供帮助。如果集合文件不存在，它将被创建。

```
QHelpContentModel QHelpEngine.contentModel (self)
```

[

返回的内容模型。

](qhelpcontentmodel.html)

```
QHelpContentWidget QHelpEngine.contentWidget (self)
```

[

返回的内容控件。

](qhelpcontentwidget.html)

```
QHelpIndexModel QHelpEngine.indexModel (self)
```

[

返回指数模型。

](qhelpindexmodel.html)

```
QHelpIndexWidget QHelpEngine.indexWidget (self)
```

[

返回索引部件。

](qhelpindexwidget.html)

```
QHelpSearchEngine QHelpEngine.searchEngine (self)
```

[

返回的默认搜索引擎。

](qhelpsearchengine.html)