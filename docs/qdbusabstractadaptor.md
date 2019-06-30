# QDBusAbstractAdaptor Class Reference

## [[QtDBus](index.htm) module]

该QDBusAbstractAdaptor类是D -总线适配器类的基类。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent)`
*   `bool autoRelaySignals (self)`
*   `setAutoRelaySignals (self, bool enable)`

* * *

## Detailed Description

该QDBusAbstractAdaptor类是D -总线适配器类的基类。

该QDBusAbstractAdaptor类是起点打算使用的D-Bus提供接口给外部世界的所有对象。这是通过将来自于QDBusAbstractAdaptor到正常的一个的一个或多个类来实现[QObject](qobject.html)然后注册了[QObject](qobject.html)与QDBusConnection.registerObject 。 QDBusAbstractAdaptor对象旨在是重量轻的包装，大多只是中继呼叫到真实对象（它的父） ，且信号从它。

每个QDBusAbstractAdaptor派生类应该定义的D-Bus接口它使用的是Q_CLASSINFO宏在类定义实现。请注意，只有一个接口可以以这种方式被暴露。

QDBusAbstractAdaptor使用标准[QObject](qobject.html)的信号，槽和属性的机制来确定什么信号，方法和属性导出到总线。通过QDBusAbstractAdaptor派生类发出的任何信号会自动通过任何物体上注册的D-Bus连接中继。

从QDBusAbstractAdaptor派生类必须使用在堆上创建的_new_算子，并且不能被用户删除（它们将被自动删除，当它们连接到该对象也被删除） 。

* * *

## Method Documentation

```
QDBusAbstractAdaptor.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QDBusAbstractAdaptor](qdbusabstractadaptor.html)同_obj_作为父对象。

```
bool QDBusAbstractAdaptor.autoRelaySignals (self)
```

返回True如果自动信号从实物中继（见对象（ ） ）被启用， otherwiser返回False 。

**See also** [setAutoRelaySignals](qdbusabstractadaptor.html#setAutoRelaySignals)（ ） 。

```
QDBusAbstractAdaptor.setAutoRelaySignals (self, bool enable)
```

自动切换信号从实物中继（见对象（ ） ） 。

自动信号中继由具有两个类完全相同的方法signatue父的信号的信号 - 信号连接。

If _enable_设置为True ，连接信号，如果设置为False ，断开所有信号。

**See also** [autoRelaySignals](qdbusabstractadaptor.html#autoRelaySignals)（ ） 。