# QDeclarativeExpression Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeExpression类评估的JavaScript在QML上下文。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDeclarativeContext, QObject, QString, QObject parent = None)`
*   `clearError (self)`
*   `QDeclarativeContext context (self)`
*   `QDeclarativeEngine engine (self)`
*   `QDeclarativeError error (self)`
*   `(QVariant, bool valueIsUndefined) evaluate (self)`
*   `QString expression (self)`
*   `bool hasError (self)`
*   `int lineNumber (self)`
*   `bool notifyOnValueChanged (self)`
*   `QObject scopeObject (self)`
*   `setExpression (self, QString)`
*   `setNotifyOnValueChanged (self, bool)`
*   `setSourceLocation (self, QString fileName, int line)`
*   `QString sourceFile (self)`

### Qt Signals

*   `void valueChanged ()`

* * *

## Detailed Description

该QDeclarativeExpression类评估的JavaScript在QML上下文。

例如，给定一个文件`main.qml`像这样：

```
 import QtQuick 1.0

 [Item](index.htm) {
     width: 200; height: 200
 }

```

下面的代码在评估上述QML上下文JavaScript表达式：

```
 [QDeclarativeEngine](qdeclarativeengine.html) *engine = new [QDeclarativeEngine](qdeclarativeengine.html);
 [QDeclarativeComponent](qdeclarativecomponent.html) component(engine, [QUrl](qurl.html).fromLocalFile("main.qml"));

 [QObject](qobject.html) *myObject = component.create();
 QDeclarativeExpression *expr = new QDeclarativeExpression(engine->rootContext(), myObject, "width * 2");
 int result = expr->evaluate().toInt();  // result = 400

```

* * *

## Method Documentation

```
QDeclarativeExpression.__init__ (self)
```

创建一个无效的[QDeclarativeExpression](qdeclarativeexpression.html)。

作为表达不会有一个关联的[QDeclarativeContext](qdeclarativecontext.html)，这将是一个空表达式对象，它的值将永远是无效的[QVariant](qvariant.html)。

```
QDeclarativeExpression.__init__ (self, QDeclarativeContext, QObject, QString, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QDeclarativeExpression](qdeclarativeexpression.html)对象，该对象是一个子_parent_。

该_expression_JavaScript的将在被执行_ctxt_ [QDeclarativeContext](qdeclarativecontext.html)。如果指定，_scope_对象的属性也将在范围表达式的执行过程中。

```
QDeclarativeExpression.clearError (self)
```

清除任何表达错误。调用[hasError](qdeclarativeexpression.html#hasError)（ ）以下，这将返回False 。

**See also** [hasError](qdeclarativeexpression.html#hasError)（）和[error](qdeclarativeexpression.html#error)（ ） 。

```
QDeclarativeContext QDeclarativeExpression.context (self)
```

[](qdeclarativecontext.html)

[返回](qdeclarativecontext.html)[QDeclarativeContext](qdeclarativecontext.html)这种表达是与，或0相关的，如果没有关联关系或[QDeclarativeContext](qdeclarativecontext.html)已被摧毁。

```
QDeclarativeEngine QDeclarativeExpression.engine (self)
```

[](qdeclarativeengine.html)

[返回](qdeclarativeengine.html)[QDeclarativeEngine](qdeclarativeengine.html)这种表达是与，或0相关的，如果没有关联关系或[QDeclarativeEngine](qdeclarativeengine.html)已被摧毁。

```
QDeclarativeError QDeclarativeExpression.error (self)
```

[](qdeclarativeerror.html)

[返回从最后一次调用的任何错误](qdeclarativeerror.html)[evaluate](qdeclarativeexpression.html#evaluate)（ ） 。如果没有错误，将返回一个无效的[QDeclarativeError](qdeclarativeerror.html)实例。

**See also** [hasError](qdeclarativeexpression.html#hasError)（）和[clearError](qdeclarativeexpression.html#clearError)（ ） 。

```
(QVariant, bool valueIsUndefined) QDeclarativeExpression.evaluate (self)
```

Evaulates表达式，返回了评价的结果，或无效[QVariant](qvariant.html)如果表达式是无效的或有错误。

_valueIsUndefined_被设置为True，如果表达导致一个未定义的值。

**See also** [hasError](qdeclarativeexpression.html#hasError)（）和[error](qdeclarativeexpression.html#error)（ ） 。

```
QString QDeclarativeExpression.expression (self)
```

返回表达式的字符串。

**See also** [setExpression](qdeclarativeexpression.html#setExpression)（ ） 。

```
bool QDeclarativeExpression.hasError (self)
```

返回True如果到最后通话[evaluate](qdeclarativeexpression.html#evaluate)（ ）导致错误，否则为False 。

**See also** [error](qdeclarativeexpression.html#error)（）和[clearError](qdeclarativeexpression.html#clearError)（ ） 。

```
int QDeclarativeExpression.lineNumber (self)
```

返回此表达式的源文件中的行号。源位置必须通过调用预先设置[setSourceLocation](qdeclarativeexpression.html#setSourceLocation)（ ） 。

```
bool QDeclarativeExpression.notifyOnValueChanged (self)
```

返回True如果[valueChanged](qdeclarativeexpression.html#valueChanged)（ ）信号被发射时，表达式的评估值的变化。

**See also** [setNotifyOnValueChanged](qdeclarativeexpression.html#setNotifyOnValueChanged)（ ） 。

```
QObject QDeclarativeExpression.scopeObject (self)
```

[

返回表达式的范围对象，如果提供的话，否则为0 。

](qobject.html)

[除了由表达式的提供数据](qobject.html)[QDeclarativeContext](qdeclarativecontext.html)，范围对象的属性也在范围内表达的评价。

```
QDeclarativeExpression.setExpression (self, QString)
```

表达式设置为_expression_。

**See also** [expression](qdeclarativeexpression.html#expression)（ ） 。

```
QDeclarativeExpression.setNotifyOnValueChanged (self, bool)
```

设置是否[valueChanged](qdeclarativeexpression.html#valueChanged)（ ）信号被发射时，表达式的评估值的变化。

If _notifyOnChange_是真的，[QDeclarativeExpression](qdeclarativeexpression.html)将监测参与式的评估性能，并放出[QDeclarativeExpression.valueChanged](qdeclarativeexpression.html#valueChanged)（ ），如果他们已经改变。这使得应用程序，以确保与表达式的结果相关联的任何值保持在最新状态。

If _notifyOnChange_为假（默认），[QDeclarativeExpression](qdeclarativeexpression.html)不会montitor涉及的表达式的求值的属性，并[QDeclarativeExpression.valueChanged](qdeclarativeexpression.html#valueChanged)（）将永远不会被发射。这是更有效的，如果应用程序想表达的是“一次性”的评价。

**See also** [notifyOnValueChanged](qdeclarativeexpression.html#notifyOnValueChanged)（ ） 。

```
QDeclarativeExpression.setSourceLocation (self, QString fileName, int line)
```

设置这个表达式的位置_line_的_url_。此信息被用于由脚本引擎。

```
QString QDeclarativeExpression.sourceFile (self)
```

返回此表达式的源文件的URL 。源位置必须通过调用预先设置[setSourceLocation](qdeclarativeexpression.html#setSourceLocation)（ ） 。

* * *

## Qt Signal Documentation

```
void valueChanged ()
```

这是该信号的默认超载。

每次发射从最后一次被计算的表达式值的变化。表达式必须被评估至少一次（通过调用[QDeclarativeExpression.evaluate](qdeclarativeexpression.html#evaluate)（））这个信号之前将被发射。