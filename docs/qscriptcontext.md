# QScriptContext Class Reference

## [[QtScript](index.htm) module]

该QScriptContext类表示一个Qt脚本函数调用。[More...](#details)

### Types

*   `enum Error { UnknownError, ReferenceError, SyntaxError, TypeError, RangeError, URIError }`
*   `enum ExecutionState { NormalState, ExceptionState }`

### Methods

*   `QScriptValue activationObject (self)`
*   `QScriptValue argument (self, int index)`
*   `int argumentCount (self)`
*   `QScriptValue argumentsObject (self)`
*   `QStringList backtrace (self)`
*   `QScriptValue callee (self)`
*   `QScriptEngine engine (self)`
*   `bool isCalledAsConstructor (self)`
*   `QScriptContext parentContext (self)`
*   `setActivationObject (self, QScriptValue activation)`
*   `setThisObject (self, QScriptValue thisObject)`
*   `ExecutionState state (self)`
*   `QScriptValue thisObject (self)`
*   `QScriptValue throwError (self, Error error, QString text)`
*   `QScriptValue throwError (self, QString text)`
*   `QScriptValue throwValue (self, QScriptValue value)`
*   `QString toString (self)`

* * *

## Detailed Description

该QScriptContext类表示一个Qt脚本函数调用。

一个QScriptContext提供了访问` this'对象和参数传递给脚本的功能。您通常希望当你写一个本机（ C + +）函数来访问这些信息（见[QScriptEngine.newFunction](qscriptengine.html#newFunction)（ ） ）将被调用的脚本代码。例如，当脚本代码

```
 foo(20.5, "hello", new Object())

```

被评估，一个QScriptContext将被创建，并在上下文将携带的参数作为QScriptValues ​​，在这种特殊情况下，参数将其中[QScriptValue](qscriptvalue.html)含有数20.5 ，第二[QScriptValue](qscriptvalue.html)包含字符串`"hello"`以及第三[QScriptValue](qscriptvalue.html)包含一个Qt Script对象。

使用[argumentCount](qscriptcontext.html#argumentCount)（）来获取参数传递给函数的数量，[argument](qscriptcontext.html#argument)（）来获取参数在一定的指数。该[argumentsObject](qscriptcontext.html#argumentsObject)（ ）函数返回一个包含所有参数的Qt的脚本数组对象，你可以使用[QScriptValueIterator](qscriptvalueiterator.html)遍历其元素，或者传递数组作为参数使用另一个脚本函数[QScriptValue.call](qscriptvalue.html#call)（ ） 。

使用[thisObject](qscriptcontext.html#thisObject)（ ）来获得与函数调用相关的` this'对象，并[setThisObject](qscriptcontext.html#setThisObject)（ ）来设置` this'对象。如果要实现一个本地的“实例方法” ，通常取[thisObject](qscriptcontext.html#thisObject)（ ）和访问它的一个或多个属性：

```
 [QScriptValue](qscriptvalue.html) Person_prototype_fullName(QScriptContext *context, [QScriptEngine](qscriptengine.html) *engine)
 {
     [QScriptValue](qscriptvalue.html) self = context->thisObject();
     [QString](qstring.html) result;
     result += self.property("firstName").toString();
     result += QLatin1String(" ");
     result += self.property("lastName").toString();
     return result;
 }

```

使用[isCalledAsConstructor](qscriptcontext.html#isCalledAsConstructor)（）来确定函数被调用的构造函数（如`"new foo()"`（作为构造函数），或者只是`"foo()"`） 。当一个函数被调用的构造函数中，[thisObject](qscriptcontext.html#thisObject)（）中包含的功能，预计以初始化新构造的对象。

使用[throwValue](qscriptcontext.html#throwValue)（）或[throwError](qscriptcontext.html#throwError)（ ）抛出一个异常。

使用[callee](qscriptcontext.html#callee)（ ），得到[QScriptValue](qscriptvalue.html)表示被调用的函数。例如，这可以被用于递归地调用该函数。

使用[parentContext](qscriptcontext.html#parentContext)（ ）来获得一个指向前面这种情况下在激活堆栈上下文。 （构建某种形式的回溯时，如）这是用于调试目的大多是有用的。

该[activationObject](qscriptcontext.html#activationObject)（ ）函数返回用于保存与该函数调用关联的本地变量的对象。你可以通过调用替换激活对象[setActivationObject](qscriptcontext.html#setActivationObject)（ ） 。这些函数的典型用法是，当你想脚本代码在父上下文的语境来评价，例如：实现一个include（）函数：

```
 [QScriptValue](qscriptvalue.html) myInclude(QScriptContext *ctx, [QScriptEngine](qscriptengine.html) *eng)
 {
     [QString](qstring.html) fileName = ctx->argument(0).toString();
     [QString](qstring.html) contents = readTheFile(fileName);
     ctx->setActivationObject(ctx->parentContext()->activationObject());
     ctx->setThisObject(ctx->parentContext()->thisObject());
     return eng->evaluate(contents, fileName);
 }

```

使用[backtrace](qscriptcontext.html#backtrace)（ ）来获得与这方面有关的人类可读的回溯。这对于实现本机的功能调试时非常有用。该[toString](qscriptcontext.html#toString)（ ）函数提供了上下文的字符串表示形式。 （[QScriptContextInfo](qscriptcontextinfo.html)提供有关QScriptContext更详细的调试相关的信息。 ）

使用[engine](qscriptcontext.html#engine)（）来获得一个指向[QScriptEngine](qscriptengine.html)这方面驻留英寸

* * *

## Type Documentation

```
QScriptContext.Error
```

此枚举指定类型的错误。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptContext.ReferenceError` | `1` | 参考错误。 |
| `QScriptContext.SyntaxError` | `2` | 语法错误。 |
| `QScriptContext.TypeError` | `3` | A型错误。 |
| `QScriptContext.RangeError` | `4` | 值域错误。 |
| `QScriptContext.URIError` | `5` | 一个URI错误。 |
| `QScriptContext.UnknownError` | `0` | 未知错误。 |

```
QScriptContext.ExecutionState
```

这个枚举指定上下文的frameution状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptContext.NormalState` | `0` | 上下文是在正常状态下。 |
| `QScriptContext.ExceptionState` | `1` | 上下文是在一个特殊的状态。 |

* * *

## Method Documentation

```
QScriptValue QScriptContext.activationObject (self)
```

[](qscriptvalue.html)

[返回此激活对象](qscriptvalue.html)[QScriptContext](qscriptcontext.html)。激活对象提供与此内容相关联的局部变量。

**Note:**激活对象可能无法使用，如果没有活动[QScriptEngineAgent](qscriptengineagent.html)的，因为它可能会被优化。

**See also** [setActivationObject](qscriptcontext.html#setActivationObject)（ ）[argument](qscriptcontext.html#argument)（）和[argumentsObject](qscriptcontext.html#argumentsObject)（ ） 。

```
QScriptValue QScriptContext.argument (self, int index)
```

[

返回的函数参数在给定的_index_。

](qscriptvalue.html)

[If _index_\u003e =](qscriptvalue.html)[argumentCount](qscriptcontext.html#argumentCount)（）的一个[QScriptValue](qscriptvalue.html)基本类型的未定义返回。

**See also** [argumentCount](qscriptcontext.html#argumentCount)（ ） 。

```
int QScriptContext.argumentCount (self)
```

返回的参数传递给函数在此调用的次数。

请注意，参数计数可以从参数的正式编号（不同的`length`物业[callee](qscriptcontext.html#callee)（））。

**See also** [argument](qscriptcontext.html#argument)（ ） 。

```
QScriptValue QScriptContext.argumentsObject (self)
```

[](qscriptvalue.html)

[返回此参数对象](qscriptvalue.html)[QScriptContext](qscriptcontext.html)。

该参数对象的属性`callee`（等于[callee](qscriptcontext.html#callee)（））和`length`（等于[argumentCount](qscriptcontext.html#argumentCount)（）），和属性`0`，`1`，...，[argumentCount](qscriptcontext.html#argumentCount)（ ） - 1 ，提供访问参数值。起初，物业`P`（ 0 \u003c=`P`\u003c[argumentCount](qscriptcontext.html#argumentCount)（ ） ）具有相同的值作为参数（`P`） 。在案件时`P`小于的函数形式参数的数量，`P`与激活对象的相应属性分享它的值（[activationObject](qscriptcontext.html#activationObject)（））。这意味着，更改此属性将更改激活对象的相应属性，反之亦然。

**See also** [argument](qscriptcontext.html#argument)（）和[activationObject](qscriptcontext.html#activationObject)（ ） 。

```
QStringList QScriptContext.backtrace (self)
```

返回此人类可读的回溯[QScriptContext](qscriptcontext.html)。

每一行的形式为`&lt;function-name&gt;(&lt;arguments&gt;)@&lt;file-name&gt;:&lt;line-number&gt;`。

要访问各个部分的调试相关的信息（例如，构造自己的回溯表示） ，使用[QScriptContextInfo](qscriptcontextinfo.html)。

**See also** [QScriptEngine.uncaughtExceptionBacktrace](qscriptengine.html#uncaughtExceptionBacktrace)（ ）[QScriptContextInfo](qscriptcontextinfo.html)和[toString](qscriptcontext.html#toString)（ ） 。

```
QScriptValue QScriptContext.callee (self)
```

[](qscriptvalue.html)

[返回被调用。被调用的是函数对象，这](qscriptvalue.html)[QScriptContext](qscriptcontext.html)代表的调用。

```
QScriptEngine QScriptContext.engine (self)
```

[](qscriptengine.html)

[返回](qscriptengine.html)[QScriptEngine](qscriptengine.html)这[QScriptContext](qscriptcontext.html)属于。

```
bool QScriptContext.isCalledAsConstructor (self)
```

返回True如果函数被调用的构造函数（如`"new foo()"`），否则返回False 。

当一个函数被调用的构造函数中，[thisObject](qscriptcontext.html#thisObject)（）包含要初始化的新构造的对象。

**Note:**此功能只保证工作对应于原生函数的上下文。

```
QScriptContext QScriptContext.parentContext (self)
```

[](qscriptcontext.html)

[返回此父上下文](qscriptcontext.html)[QScriptContext](qscriptcontext.html)。

```
QScriptContext.setActivationObject (self, QScriptValue activation)
```

设置这个激活对象[QScriptContext](qscriptcontext.html)为给定的_activation_。

If _activation_不是一个对象，这个函数不执行任何操作。

**Note:**为对应的JavaScript函数的上下文，这是只保证工作，如果有一个[QScriptEngineAgent](qscriptengineagent.html)活性在发动机上，而功能进行评价。

**See also** [activationObject](qscriptcontext.html#activationObject)（ ） 。

```
QScriptContext.setThisObject (self, QScriptValue thisObject)
```

设置了` this'对象与此相关[QScriptContext](qscriptcontext.html)要_thisObject_。

If _thisObject_不是一个对象，这个函数不执行任何操作。

**See also** [thisObject](qscriptcontext.html#thisObject)（ ） 。

```
ExecutionState QScriptContext.state (self)
```

[](qscriptcontext.html#ExecutionState-enum)

[返回此的frameution状态](qscriptcontext.html#ExecutionState-enum)[QScriptContext](qscriptcontext.html)。

```
QScriptValue QScriptContext.thisObject (self)
```

[](qscriptvalue.html)

[返回与此相关联的` this'对象](qscriptvalue.html)[QScriptContext](qscriptcontext.html)。

**See also** [setThisObject](qscriptcontext.html#setThisObject)（ ） 。

```
QScriptValue QScriptContext.throwError (self, Error error, QString text)
```

[

抛出一个_error_用给定的_text_。返回创建的错误对象。

该_text_将被存储在`message`错误对象的属性。

](qscriptvalue.html)

[Error对象将被初始化为包含有关发生错误的位置信息;具体而言，它将拥有属性`lineNumber`，`fileName`和`stack`。这些属性中描述](qscriptvalue.html)[QtScript Extensions to ECMAScript](index.htm#qtscript-extensions-to-ecmascript)。

**See also** [throwValue](qscriptcontext.html#throwValue)（）和[state](qscriptcontext.html#state)（ ） 。

```
QScriptValue QScriptContext.throwError (self, QString text)
```

[

这是一个重载函数。

与给定抛出一个错误_text_。返回创建的错误对象。

](qscriptvalue.html)

[**See also**](qscriptvalue.html) [throwValue](qscriptcontext.html#throwValue)（）和[state](qscriptcontext.html#state)（ ） 。

```
QScriptValue QScriptContext.throwValue (self, QScriptValue value)
```

[

用给定的抛出一个异常_value_。返回抛出（相同的参数）的值。

](qscriptvalue.html)

[**See also**](qscriptvalue.html) [throwError](qscriptcontext.html#throwError)（）和[state](qscriptcontext.html#state)（ ） 。

```
QString QScriptContext.toString (self)
```

返回此上下文的字符串表示形式。这对于调试非常有用。

此功能被引入Qt的4.4 。

**See also** [backtrace](qscriptcontext.html#backtrace)（ ） 。