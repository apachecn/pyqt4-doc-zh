# QDeclarativeNetworkAccessManagerFactory Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeNetworkAccessManagerFactory类创建[QNetworkAccessManager](qnetworkaccessmanager.html)实例一QML引擎。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDeclarativeNetworkAccessManagerFactory)`
*   `QNetworkAccessManager create (self, QObject parent)`

* * *

## Detailed Description

该QDeclarativeNetworkAccessManagerFactory类创建[QNetworkAccessManager](qnetworkaccessmanager.html)实例一QML引擎。

一个QML引擎使用[QNetworkAccessManager](qnetworkaccessmanager.html)所有网络接入。通过实施一个工厂，能够提供QML发动机与定制[QNetworkAccessManager](qnetworkaccessmanager.html)有专门的缓存，代理和cookie的支持情况。

实现工厂，子类QDeclarativeNetworkAccessManagerFactory和实现虚拟[create](qdeclarativenetworkaccessmanagerfactory.html#create)（）方法，然后将其用分配给相关的QML引擎[QDeclarativeEngine.setNetworkAccessManagerFactory](qdeclarativeengine.html#setNetworkAccessManagerFactory)（ ） 。

注意QML引擎可能创造[QNetworkAccessManager](qnetworkaccessmanager.html)从多个线程实例。正因为如此，本实施[create](qdeclarativenetworkaccessmanagerfactory.html#create)（ ）方法必须是[reentrant](index.htm)。此外，开发人员应该小心，如果该对象的信号从返回[create](qdeclarativenetworkaccessmanagerfactory.html#create)（ ）被连接到可能在不同的线程被创建的对象的槽：

*   The QML engine internally handles all requests, and cleans up any [QNetworkReply](qnetworkreply.html) objects it creates. Receiving the [QNetworkAccessManager.finished](qnetworkaccessmanager.html#finished)() signal in another thread may not provide the receiver with a valid reply object if it has already been deleted.
*   Authentication details provided to [QNetworkAccessManager.authenticationRequired](qnetworkaccessmanager.html#authenticationRequired)() must be provided immediately, so this signal cannot be connected as a [Qt.QueuedConnection](qt.html#ConnectionType-enum) (or as the default [Qt.AutoConnection](qt.html#ConnectionType-enum) from another thread).

有关信号和线程的详细信息，请参阅[Threads and QObjects](index.htm)和[Signals and Slots Across Threads](index.htm#signals-and-slots-across-threads)。

* * *

## Method Documentation

```
QDeclarativeNetworkAccessManagerFactory.__init__ (self)
```

```
QDeclarativeNetworkAccessManagerFactory.__init__ (self, QDeclarativeNetworkAccessManagerFactory)
```

```
QNetworkAccessManager QDeclarativeNetworkAccessManagerFactory.create (self, QObject parent)
```

[

这种方法是抽象的，应在任何子类中重新实现。

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qnetworkaccessmanager.html)

[创建并返回一个网络访问管理器与指定的_parent_。此方法必须返回一个新的](qnetworkaccessmanager.html)[QNetworkAccessManager](qnetworkaccessmanager.html)比如每次它被称为。

注意：这个方法可能被多个线程调用，因此确保该方法的实现是可重入的。