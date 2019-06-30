# QAbstractExtensionFactory Class Reference

## [[QtDesigner](index.htm) module]

该QAbstractExtensionFactory类提供了在Qt Designer中的扩展工厂的接口。[More...](#details)

通过继承[QExtensionFactory](qextensionfactory.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QAbstractExtensionFactory)`
*   `QObject extension (self, QObject object, QString iid)`

* * *

## Detailed Description

该QAbstractExtensionFactory类提供了在Qt Designer中的扩展工厂的接口。

QAbstractExtensionFactory不打算直接实例化;使用[QExtensionFactory](qextensionfactory.html)代替。

In _Qt Designer_，扩展工厂用于查找并创建一个名为扩展，因为它们是必需的。出于这个原因，实现自定义扩展时，您还必须创建一个[QExtensionFactory](qextensionfactory.html)，即一个类，它能够让你的扩展的一个实例，并使用它注册_Qt Designer_的[extension manager](qextensionmanager.html)。

当一个扩展是必需的，_Qt Designer_的[extension manager](qextensionmanager.html)将通过其所有已注册的工厂运行要求[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）对每一直到第一个能够创建请求的扩展选定对象，被发现。这家工厂将使这个扩展的实例。

* * *

## Method Documentation

```
QAbstractExtensionFactory.__init__ (self)
```

```
QAbstractExtensionFactory.__init__ (self, QAbstractExtensionFactory)
```

```
QObject QAbstractExtensionFactory.extension (self, QObject object, QString iid)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回由指定的扩展名_iid_对于给定的_object_。

](qobject.html)