# QDeclarativeContext Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeContext类定义中的QML引擎的内容。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QDeclarativeEngine engine, QObject parent = None)`
*   `__init__ (self, QDeclarativeContext context, QObject parent = None)`
*   `QUrl baseUrl (self)`
*   `QObject contextObject (self)`
*   `QVariant contextProperty (self, QString)`
*   `QDeclarativeEngine engine (self)`
*   `bool isValid (self)`
*   `QDeclarativeContext parentContext (self)`
*   `QUrl resolvedUrl (self, QUrl)`
*   `setBaseUrl (self, QUrl)`
*   `setContextObject (self, QObject)`
*   `setContextProperty (self, QString, QObject)`
*   `setContextProperty (self, QString, QVariant)`

* * *

## Detailed Description

该QDeclarativeContext类定义中的QML引擎的内容。

上下文允许数据被暴露在由QML引擎实例化的QML组件。

每个QDeclarativeContext包含的一组属性，其独特的[QObject](qobject.html)性质，即允许数据被明确地通过名称绑定到上下文。上下文属性都通过调用定义和更新[QDeclarativeContext.setContextProperty](qdeclarativecontext.html#setContextProperty)（ ） 。下面的例子显示了Qt的模型被绑定到一个上下文，然后从一个QML文件的访问。

```
 [QDeclarativeEngine](qdeclarativeengine.html) engine;
 [QStringListModel](qstringlistmodel.html) modelData;
 QDeclarativeContext *context = new QDeclarativeContext(engine.rootContext());
 context->setContextProperty("myModel", &modelData);

 [QDeclarativeComponent](qdeclarativecomponent.html) component(&engine);
 component.setData("import QtQuick 1.0\nListView { model: myModel }", [QUrl](qurl.html)());
 [QObject](qobject.html) *window = component.create(context);

```

注意它是创作者将其删除构建任何QDeclarativeContext责任。如果`context`在本例中的对象不再需要时`window`组件实例被破坏，`context`必须显式地销毁。确保这一点的最简单的方法是设置`window`作为父`context`。

为了简化绑定和维护更大的数据集，一个上下文对象可以在QDeclarativeContext进行设置。是上下文对象的所有属性可通过名称的背景下，彷彿他们都分别通过调用添加[QDeclarativeContext.setContextProperty](qdeclarativecontext.html#setContextProperty)（ ） 。通过属性的通知信号被检测到更改属性的值。设置一个上下文对象是速度更快，比手动添加和维修器材上下文属性值更容易。

下面的例子中有相同的效果与前面的一个，但是它使用了一个上下文对象。

```
 class MyDataSet : ... {
     ...
     Q_PROPERTY([QAbstractItemModel](qabstractitemmodel.html) *myModel READ model NOTIFY modelChanged)
     ...
 };

 MyDataSet myDataSet;
 [QDeclarativeEngine](qdeclarativeengine.html) engine;
 QDeclarativeContext *context = new QDeclarativeContext(engine.rootContext());
 context->setContextObject(&myDataSet);

 [QDeclarativeComponent](qdeclarativecomponent.html) component(&engine);
 component.setData("import QtQuick 1.0\nListView { model: myModel }", [QUrl](qurl.html)());
 component.create(context);

```

通过明确添加的所有属性[QDeclarativeContext.setContextProperty](qdeclarativecontext.html#setContextProperty)（ ）优先于上下文对象的属性。

#### The Context Hierarchy

上下文可以形成一个分层结构。这个层次结构的根是QML引擎的[root context](qdeclarativeengine.html#rootContext)。儿童上下文继承父母的上下文属性，如果一个孩子的上下文设置已经存在于它的父上下文属性，新的上下文属性将复盖母公司。

下面的示例定义两个上下文 - `context1`和`context2`。第二个方面复盖从先用一个新值继承了“b”的内容属性。

```
 [QDeclarativeEngine](qdeclarativeengine.html) engine;
 QDeclarativeContext *context1 = new QDeclarativeContext(engine.rootContext());
 QDeclarativeContext *context2 = new QDeclarativeContext(context1);

 context1->setContextProperty("a", 12);
 context1->setContextProperty("b", 12);

 context2->setContextProperty("b", 15);

```

而在实例化一个上下文QML对象不严格的情况下拥有的，绑定。如果上下文被销毁，优秀的QML对象的属性绑定将停止评估。

**Warning:**设置上下文对象或之后有物体在这种情况下被创建增加新的内容属性是一个昂贵的操作（实际上是强迫所有绑定重新评估） 。因此，只要有可能，你应该使用它来创建任何对象之前完成上下文的“设置” 。

* * *

## Method Documentation

```
QDeclarativeContext.__init__ (self, QDeclarativeEngine engine, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的[QDeclarativeContext](qdeclarativecontext.html)作为一个子_engine_的根上下文，以及[QObject](qobject.html) _parent_。

```
QDeclarativeContext.__init__ (self, QDeclarativeContext context, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的[QDeclarativeContext](qdeclarativecontext.html)用给定的_parentContext_和[QObject](qobject.html) _parent_。

```
QUrl QDeclarativeContext.baseUrl (self)
```

[

返回组件的基本URL ，或含有成分，如果没有被设置。

](qurl.html)

[**See also**](qurl.html) [setBaseUrl](qdeclarativecontext.html#setBaseUrl)（ ） 。

```
QObject QDeclarativeContext.contextObject (self)
```

[

返回上下文对象，或0 ，如果没有上下文对象。

](qobject.html)

[**See also**](qobject.html) [setContextObject](qdeclarativecontext.html#setContextObject)（ ） 。

```
QVariant QDeclarativeContext.contextProperty (self, QString)
```

返回的值_name_属性这方面的[QVariant](qvariant.html)。

**See also** [setContextProperty](qdeclarativecontext.html#setContextProperty)（ ） 。

```
QDeclarativeEngine QDeclarativeContext.engine (self)
```

[](qdeclarativeengine.html)

[返回上下文的](qdeclarativeengine.html)[QDeclarativeEngine](qdeclarativeengine.html)，或者0，如果上下文没有[QDeclarativeEngine](qdeclarativeengine.html)或[QDeclarativeEngine](qdeclarativeengine.html)被摧毁。

```
bool QDeclarativeContext.isValid (self)
```

返回上下文是否有效。

是有效的，上下文必须有一个发动机，它的[contextObject](qdeclarativecontext.html#contextObject)（） ，如果有的话，必须没有被删除。

```
QDeclarativeContext QDeclarativeContext.parentContext (self)
```

[](qdeclarativecontext.html)

[返回上下文的父](qdeclarativecontext.html)[QDeclarativeContext](qdeclarativecontext.html)，或者0，如果这方面没有父或父已被破坏。

```
QUrl QDeclarativeContext.resolvedUrl (self, QUrl)
```

[

解析URL_src_相对于包含组件的URL 。

](qurl.html)

[**See also**](qurl.html) [QDeclarativeEngine.baseUrl](qdeclarativeengine.html#baseUrl)（）和[setBaseUrl](qdeclarativecontext.html#setBaseUrl)（ ） 。

```
QDeclarativeContext.setBaseUrl (self, QUrl)
```

显式设置的URL[resolvedUrl](qdeclarativecontext.html#resolvedUrl)（ ）将使用相对引用_baseUrl_。

调用此函数将复盖默认使用的含有成分的url 。

**See also** [baseUrl](qdeclarativecontext.html#baseUrl)（）和[resolvedUrl](qdeclarativecontext.html#resolvedUrl)（ ） 。

```
QDeclarativeContext.setContextObject (self, QObject)
```

设置上下文_object_。

**See also** [contextObject](qdeclarativecontext.html#contextObject)（ ） 。

```
QDeclarativeContext.setContextProperty (self, QString, QObject)
```

设置_value_的_name_财产这方面。

[QDeclarativeContext](qdeclarativecontext.html)不**not**取得其所有权_value_。

**See also** [contextProperty](qdeclarativecontext.html#contextProperty)（ ） 。

```
QDeclarativeContext.setContextProperty (self, QString, QVariant)
```

设置的_value_的_name_财产这方面。