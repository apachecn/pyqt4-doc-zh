# QDeclarativeComponent Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeComponent类封装了QML组件定义。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum Status { Null, Ready, Loading, Error }`

### Methods

*   `__init__ (self, QDeclarativeEngine, QObject parent = None)`
*   `__init__ (self, QDeclarativeEngine, QString fileName, QObject parent = None)`
*   `__init__ (self, QDeclarativeEngine, QUrl url, QObject parent = None)`
*   `QObject beginCreate (self, QDeclarativeContext)`
*   `completeCreate (self)`
*   `QObject create (self, QDeclarativeContext context = None)`
*   `QDeclarativeContext creationContext (self)`
*   `list-of-QDeclarativeError errors (self)`
*   `bool isError (self)`
*   `bool isLoading (self)`
*   `bool isNull (self)`
*   `bool isReady (self)`
*   `loadUrl (self, QUrl url)`
*   `float progress (self)`
*   `setData (self, QByteArray, QUrl baseUrl)`
*   `Status status (self)`
*   `QUrl url (self)`

### Qt Signals

*   `void progressChanged (qreal)`
*   `void statusChanged (QDeclarativeComponent::Status)`

* * *

## Detailed Description

该QDeclarativeComponent类封装了QML组件定义。

组件是可重用的，封装QML元素具有定义良好的接口。他们往往在定义[Component Files](index.htm)。

一个QDeclarativeComponent实例可以从QML文件中创建。例如，如果有一个`main.qml`文件是这样的：

```
 import QtQuick 1.0

 [Item](index.htm) {
     width: 200
     height: 200
 }

```

下面的代码加载这个QML文件作为一个组件，使用创建该组件的一个实例[create](qdeclarativecomponent.html#create)（ ） ，然后查询[Item](index.htm)的[width](index.htm#width-prop)价值：

```
 [QDeclarativeEngine](qdeclarativeengine.html) *engine = new [QDeclarativeEngine](qdeclarativeengine.html);
 QDeclarativeComponent component(engine, [QUrl](qurl.html).fromLocalFile("main.qml"));

 [QObject](qobject.html) *myObject = component.create();
 [QDeclarativeItem](qdeclarativeitem.html) *item = qobject_cast<[QDeclarativeItem](qdeclarativeitem.html)*>(myObject);
 int width = item->width();  // width = 200

```

#### Network Components

如果传递给QDeclarativeComponent URL是一个网络资源，或者QML文档引用的网络资源，将QDeclarativeComponent具有获取网络数据之前，它能够创建对象。在这种情况下， QDeclarativeComponent将有[Loading](qdeclarativecomponent.html#Status-enum) [status](qdeclarativecomponent.html#status-prop)。应用程序将不得不等待，直到该组件是[Ready](qdeclarativecomponent.html#Status-enum)打电话之前[QDeclarativeComponent.create](qdeclarativecomponent.html#create)（ ） 。

下面的示例演示如何加载从网络资源中的QML文件。创建QDeclarativeComponent后，它测试组件是否被加载。如果是，它连接到[QDeclarativeComponent.statusChanged](qdeclarativecomponent.html#statusChanged)（ ）信号，否则调用`continueLoading()`方法直接。需要注意的是[QDeclarativeComponent.isLoading](qdeclarativecomponent.html#isLoading)（ ）可能是假的网络组件，如果该组件已被缓存，并立即准备就绪。

```
 MyApplication.MyApplication()
 {
     // ...
     component = new QDeclarativeComponent(engine, [QUrl](qurl.html)("http://www.example.com/main.qml"));
     if (component->isLoading())
         [QObject](qobject.html).connect(component, SIGNAL(statusChanged(QDeclarativeComponent.Status)),
                          this, SLOT(continueLoading()));
     else
         continueLoading();
 }

 void MyApplication.continueLoading()
 {
     if (component->isError()) {
         qWarning() << component->errors();
     } else {
         [QObject](qobject.html) *myObject = component->create();
     }
 }

```

* * *

## Type Documentation

```
QDeclarativeComponent.Status
```

指定的加载状态[QDeclarativeComponent](qdeclarativecomponent.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QDeclarativeComponent.Null` | `0` | This [QDeclarativeComponent](qdeclarativecomponent.html)没有数据。通话[loadUrl](qdeclarativecomponent.html#loadUrl)（）或[setData](qdeclarativecomponent.html#setData)（）添加QML内容。 |
| `QDeclarativeComponent.Ready` | `1` | This [QDeclarativeComponent](qdeclarativecomponent.html)准备就绪，[create](qdeclarativecomponent.html#create)（ ）可以被调用。 |
| `QDeclarativeComponent.Loading` | `2` | This [QDeclarativeComponent](qdeclarativecomponent.html)正在加载网络数据。 |
| `QDeclarativeComponent.Error` | `3` | 发生了错误。通话[errors](qdeclarativecomponent.html#errors)（ ）来获取{列表[QDeclarativeError](qdeclarativeerror.html){ } }错误。 |

* * *

## Method Documentation

```
QDeclarativeComponent.__init__ (self, QDeclarativeEngine, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QDeclarativeComponent](qdeclarativecomponent.html)没有数据，并给它指定_engine_和_parent_。与设定的数据[setData](qdeclarativecomponent.html#setData)（ ） 。

```
QDeclarativeComponent.__init__ (self, QDeclarativeEngine, QString fileName, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
QDeclarativeComponent.__init__ (self, QDeclarativeEngine, QUrl url, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QDeclarativeComponent](qdeclarativecomponent.html)从给定的_fileName_并给它指定_parent_和_engine_。

**See also** [loadUrl](qdeclarativecomponent.html#loadUrl)（ ） 。

```
QObject QDeclarativeComponent.beginCreate (self, QDeclarativeContext)
```

[](qobject.html)

[这种方法提供了更高级的控制组件实例的创建。一般情况下，程序员应该使用](qobject.html)[QDeclarativeComponent.create](qdeclarativecomponent.html#create)（）来创建一个组件。

此组件创建一个对象实例。返回0，如果创建失败。_context_指定一个要在其中创建对象实例的上下文。

When [QDeclarativeComponent](qdeclarativecomponent.html)构造一个实例，它发生在三个步骤：

1.  对象层次被创建，并且常数值分配。
2.  物业绑定进行评估的第一次。
3.  如果适用，[QDeclarativeParserStatus.componentComplete](qdeclarativeparserstatus.html#componentComplete)（）被调用的对象。

QDeclarativeComponent.beginCreate （ ）不同于[QDeclarativeComponent.create](qdeclarativecomponent.html#create)（） ，因为它仅执行步骤1 。[QDeclarativeComponent.completeCreate](qdeclarativecomponent.html#completeCreate)（ ）必须被调用来完成步骤2和3 。

使用附加属性时，将信息传达给一个实例化的组件，因为它可以让它们的初始值进行配置之前，物业绑定生效，这突破点有时是有用的。

```
QDeclarativeComponent.completeCreate (self)
```

这种方法提供了更高级的控制组件实例的创建。一般情况下，程序员应该使用[QDeclarativeComponent.create](qdeclarativecomponent.html#create)（）来创建一个组件。

完成组件创建开始[QDeclarativeComponent.beginCreate](qdeclarativecomponent.html#beginCreate)（ ） 。

```
QObject QDeclarativeComponent.create (self, QDeclarativeContext context = None)
```

[

此组件创建一个对象实例。返回0，如果创建失败。_context_指定一个要在其中创建对象实例的上下文。

](qobject.html)

[If _context_为0 （默认值） ，它会在引擎的创建实例](qobject.html)[root context](qdeclarativeengine.html#rootContext)。

```
QDeclarativeContext QDeclarativeComponent.creationContext (self)
```

[](qdeclarativecontext.html)

[返回](qdeclarativecontext.html)[QDeclarativeContext](qdeclarativecontext.html)该组件被创建。这是仅适用于直接从QML创建的组件。

```
list-of-QDeclarativeError QDeclarativeComponent.errors (self)
```

返回的最后一个编译期间发生的错误的列表或创建操作。如果返回空列表[isError](qdeclarativecomponent.html#isError)（ ）未设置。

```
bool QDeclarativeComponent.isError (self)
```

返回True如果[status](qdeclarativecomponent.html#status-prop)（）==[QDeclarativeComponent.Error](qdeclarativecomponent.html#Status-enum)。

```
bool QDeclarativeComponent.isLoading (self)
```

返回True如果[status](qdeclarativecomponent.html#status-prop)（）==[QDeclarativeComponent.Loading](qdeclarativecomponent.html#Status-enum)。

```
bool QDeclarativeComponent.isNull (self)
```

返回True如果[status](qdeclarativecomponent.html#status-prop)（）==[QDeclarativeComponent.Null](qdeclarativecomponent.html#Status-enum)。

```
bool QDeclarativeComponent.isReady (self)
```

返回True如果[status](qdeclarativecomponent.html#status-prop)（）==[QDeclarativeComponent.Ready](qdeclarativecomponent.html#Status-enum)。

```
QDeclarativeComponent.loadUrl (self, QUrl url)
```

加载[QDeclarativeComponent](qdeclarativecomponent.html)从所提供的_url_。

确保所提供的URL是充分和正确的，尤其是借[QUrl.fromLocalFile](qurl.html#fromLocalFile)（ ）装载从本地文件系统中的文件时。

```
float QDeclarativeComponent.progress (self)
```

```
QDeclarativeComponent.setData (self, QByteArray, QUrl baseUrl)
```

设置[QDeclarativeComponent](qdeclarativecomponent.html)使用给定的QML_data_。如果_url_被提供，它是用来设置该组件的名称和提供一个基本路径由该元件得到解决的项目。

```
Status QDeclarativeComponent.status (self)
```

[](qdeclarativecomponent.html#Status-enum)

```
QUrl QDeclarativeComponent.url (self)
```

[

* * *

## Qt Signal Documentation

```
void progressChanged (qreal)
```

这是该信号的默认超载。

每当发射组件的加载进度的变化。_progress_将介于0.0 （无负载）和1.0 （成品）目前的进展。

```
void statusChanged (QDeclarativeComponent::Status)
```

这是该信号的默认超载。

每当发射组件的状态变化。_status_将新的状态。

](qurl.html)