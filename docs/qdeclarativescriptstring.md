# QDeclarativeScriptString Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeScriptString类封装了一个脚本，它的上下文。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDeclarativeScriptString)`
*   `QDeclarativeContext context (self)`
*   `QObject scopeObject (self)`
*   `QString script (self)`
*   `setContext (self, QDeclarativeContext)`
*   `setScopeObject (self, QObject)`
*   `setScript (self, QString)`

* * *

## Detailed Description

该QDeclarativeScriptString类封装了一个脚本，它的上下文。

QDeclarativeScriptString被用来创建[QObject](qobject.html)接受从QML脚本“转让”的属性。

通常，下面的QML会导致约束正在建立的`script`财产;即`script`将被分配从运行而获得的值`myObj.value = Math.max(myValue, 100)`

```
 MyType {
     script: myObj.value = Math.max(myValue, 100)
 }

```

相反，如果该属性有一个类型QDeclarativeScriptString ，脚本本身的 - _myObj.value = Math.max(myValue, 100)_ - 将被传递给`script`属性和类可以选择如何处理它。通常情况下，该类将使用一段时间以后评估脚本[QDeclarativeExpression](qdeclarativeexpression.html)。

```
 [QDeclarativeExpression](qdeclarativeexpression.html) expr(scriptString.context(), scriptString.script(), scriptStr.scopeObject());
 expr.value();

```

* * *

## Method Documentation

```
QDeclarativeScriptString.__init__ (self)
```

构造一个空实例。

```
QDeclarativeScriptString.__init__ (self, QDeclarativeScriptString)
```

Copies _other_。

```
QDeclarativeContext QDeclarativeScriptString.context (self)
```

[

返回上下文的脚本。

](qdeclarativecontext.html)

[**See also**](qdeclarativecontext.html) [setContext](qdeclarativescriptstring.html#setContext)（ ） 。

```
QObject QDeclarativeScriptString.scopeObject (self)
```

[

返回的范围对象的脚本。

](qobject.html)

[**See also**](qobject.html) [setScopeObject](qdeclarativescriptstring.html#setScopeObject)（ ） 。

```
QString QDeclarativeScriptString.script (self)
```

返回脚本文本。

**See also** [setScript](qdeclarativescriptstring.html#setScript)（ ） 。

```
QDeclarativeScriptString.setContext (self, QDeclarativeContext)
```

设置_context_为脚本。

**See also** [context](qdeclarativescriptstring.html#context)（ ） 。

```
QDeclarativeScriptString.setScopeObject (self, QObject)
```

设定范围_object_为脚本。

**See also** [scopeObject](qdeclarativescriptstring.html#scopeObject)（ ） 。

```
QDeclarativeScriptString.setScript (self, QString)
```

设置_script_文本。

**See also** [script](qdeclarativescriptstring.html#script)（ ） 。