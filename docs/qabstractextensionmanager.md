# QAbstractExtensionManager Class Reference

## [[QtDesigner](index.htm) module]

该QAbstractExtensionManager类提供了在Qt Designer中的扩展管理器的界面。[More...](#details)

通过继承[QExtensionManager](qextensionmanager.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QAbstractExtensionManager)`
*   `QObject extension (self, QObject object, QString iid)`
*   `registerExtensions (self, QAbstractExtensionFactory factory, QString iid)`
*   `unregisterExtensions (self, QAbstractExtensionFactory factory, QString iid)`

* * *

## Detailed Description

该QAbstractExtensionManager类提供了在Qt Designer中的扩展管理器的界面。

QAbstractExtensionManager不打算直接实例化;使用[QExtensionManager](qextensionmanager.html)代替。

In _Qt Designer_，扩展不创建，直到你需要它们。出于这个原因，实现自定义扩展时，您还必须创建一个[QExtensionFactory](qextensionfactory.html)，即一个类，它能够让你的扩展的一个实例，并使用它注册_Qt Designer_的[extension manager](qextensionmanager.html)。

当一个扩展是必需的，_Qt Designer_的[extension manager](qextensionmanager.html)将通过其所有已注册的工厂运行要求[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）对每一直到第一个能够创建请求的扩展选定对象，被发现。这家工厂将使这个扩展的实例。

* * *

## Method Documentation

```
QAbstractExtensionManager.__init__ (self)
```

```
QAbstractExtensionManager.__init__ (self, QAbstractExtensionManager)
```

```
QObject QAbstractExtensionManager.extension (self, QObject object, QString iid)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回的延伸，由指定的_iid_，对于给定的_object_。

```
QAbstractExtensionManager.registerExtensions (self, QAbstractExtensionFactory factory, QString iid)
```

这种方法是抽象的，应在任何子类中重新实现。

注册给定的扩展名_factory_由指定的扩展名_iid_。

```
QAbstractExtensionManager.unregisterExtensions (self, QAbstractExtensionFactory factory, QString iid)
```

这种方法是抽象的，应在任何子类中重新实现。

注销定_factory_由指定的扩展名_iid_。

](qobject.html)