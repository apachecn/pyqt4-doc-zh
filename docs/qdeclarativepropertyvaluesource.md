# QDeclarativePropertyValueSource Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativePropertyValueSource类是属性值的来源，如动画和绑定的接口。[More...](#details)

通过继承[QPyDeclarativePropertyValueSource](qpydeclarativepropertyvaluesource.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDeclarativePropertyValueSource)`
*   `setTarget (self, QDeclarativeProperty)`

* * *

## Detailed Description

该QDeclarativePropertyValueSource类是属性值的来源，如动画和绑定的接口。

See [Property Value Sources](index.htm#property-value-sources)有关编写自定义属性值来源的信息。

* * *

## Method Documentation

```
QDeclarativePropertyValueSource.__init__ (self)
```

构造一个[QDeclarativePropertyValueSource](qdeclarativepropertyvaluesource.html)。

```
QDeclarativePropertyValueSource.__init__ (self, QDeclarativePropertyValueSource)
```

```
QDeclarativePropertyValueSource.setTarget (self, QDeclarativeProperty)
```

这种方法是抽象的，应在任何子类中重新实现。

设定目标_property_对价值源泉。这个方法将被QML引擎赋值源时被调用。