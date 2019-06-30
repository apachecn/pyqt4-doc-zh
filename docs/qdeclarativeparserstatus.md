# QDeclarativeParserStatus Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeParserStatus类提供的QML解析器的状态更新。[More...](#details)

通过继承[QDeclarativeItem](qdeclarativeitem.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDeclarativeParserStatus)`
*   `classBegin (self)`
*   `componentComplete (self)`

* * *

## Detailed Description

该QDeclarativeParserStatus类提供的QML解析器的状态更新。

QDeclarativeParserStatus提供了一种机制，用于通过一个实例化的类[QDeclarativeEngine](qdeclarativeengine.html)要在他们的创作关键点收到通知。

这个类通常用于优化的目的，因为它可以让你推迟昂贵的操作后，所有的属性都被设置在对象上，直到。例如， QML的[Text](index.htm)元素使用的解析器状态推迟文字排版，直到所有的属性都被设置（我们不希望布局时，`text`被分配，然后重新布局时`font`分配和重新布局时再`width`被分配，等等） 。

要使用QDeclarativeParserStatus ，你必须同时继承一个[QObject](qobject.html)派生类和QDeclarativeParserStatus ，并使用[Q_INTERFACES](qobject.html#Q_INTERFACES)（）宏。

```
 class MyObject : public [QObject](qobject.html), public QDeclarativeParserStatus
 {
     Q_OBJECT
     Q_INTERFACES(QDeclarativeParserStatus)

 public:
     MyObject([QObject](qobject.html) *parent = 0);
     ...
     void classBegin();
     void componentComplete();
 }

```

* * *

## Method Documentation

```
QDeclarativeParserStatus.__init__ (self)
```

```
QDeclarativeParserStatus.__init__ (self, QDeclarativeParserStatus)
```

```
QDeclarativeParserStatus.classBegin (self)
```

这种方法是抽象的，应在任何子类中重新实现。

类创建后调用，但任何属性已设定之前。

```
QDeclarativeParserStatus.componentComplete (self)
```

这种方法是抽象的，应在任何子类中重新实现。

导致此实例已建设完成的根组件后调用。在这一点上所有的静态值和绑定值已被分配给类。