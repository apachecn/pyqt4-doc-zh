# QScriptContextInfo Class Reference

## [[QtScript](index.htm) module]

该QScriptContextInfo类提供有关的其他信息[QScriptContext](qscriptcontext.html)。[More...](#details)

### Types

*   `enum FunctionType { ScriptFunction, QtFunction, QtPropertyFunction, NativeFunction }`

### Methods

*   `__init__ (self, QScriptContext context)`
*   `__init__ (self, QScriptContextInfo other)`
*   `__init__ (self)`
*   `int columnNumber (self)`
*   `QString fileName (self)`
*   `int functionEndLineNumber (self)`
*   `int functionMetaIndex (self)`
*   `QString functionName (self)`
*   `QStringList functionParameterNames (self)`
*   `int functionStartLineNumber (self)`
*   `FunctionType functionType (self)`
*   `bool isNull (self)`
*   `int lineNumber (self)`
*   `int scriptId (self)`

### Special Methods

*   `bool __eq__ (self, QScriptContextInfo other)`
*   `bool __ne__ (self, QScriptContextInfo other)`

* * *

## Detailed Description

该QScriptContextInfo类提供有关的其他信息[QScriptContext](qscriptcontext.html)。

QScriptContextInfo通常用于调试目的。它可以提供有关被执行时，如所调用的函数的类型，和当前语句的原始源代码中的位置的代码信息。

如果被调用的函数执行的Qt Script代码，您可以用函数获取脚本位置[fileName](qscriptcontextinfo.html#fileName)（）和[lineNumber](qscriptcontextinfo.html#lineNumber)（ ） 。

您可以得到一个Qt脚本函数定义的起始行号和结束行号[functionStartLineNumber](qscriptcontextinfo.html#functionStartLineNumber)（）和[functionEndLineNumber](qscriptcontextinfo.html#functionEndLineNumber)（） ，分别为。

对于Qt的脚本功能和Qt方法（如槽） ，你可以调用[functionParameterNames](qscriptcontextinfo.html#functionParameterNames)（ ）来获取函数的形式参数的名称。

对于Qt的方法和Qt属性访问器，你可以得到相关的索引[QMetaMethod](qmetamethod.html) or [QMetaProperty](qmetaproperty.html)通过调用[functionMetaIndex](qscriptcontextinfo.html#functionMetaIndex)（ ） 。

* * *

## Type Documentation

```
QScriptContextInfo.FunctionType
```

此枚举指定的函数被调用的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptContextInfo.ScriptFunction` | `0` | 该函数是一个Qt脚本功能，也就是说，它是一个通过调用定义[QScriptEngine.evaluate](qscriptengine.html#evaluate)（ ） 。 |
| `QScriptContextInfo.QtFunction` | `1` | 该函数是一个Qt函数（一个信号，槽或方法） 。 |
| `QScriptContextInfo.QtPropertyFunction` | `2` | 该函数是一个Qt属性的getter或setter 。 |
| `QScriptContextInfo.NativeFunction` | `3` | 该函数是一个内置Qt的脚本功能，或者它是通过调用定义[QScriptEngine.newFunction](qscriptengine.html#newFunction)（ ） 。 |

* * *

## Method Documentation

```
QScriptContextInfo.__init__ (self, QScriptContext context)
```

构造一个新的[QScriptContextInfo](qscriptcontextinfo.html)从给定的_context_。

有关的信息从所提取的_context_在构造的时候，也就是说，如果你继续在脚本执行_context_，上下文的新状态将不会反映在以前创建的[QScriptContextInfo](qscriptcontextinfo.html)。

```
QScriptContextInfo.__init__ (self, QScriptContextInfo other)
```

构造一个新的[QScriptContextInfo](qscriptcontextinfo.html)从_other_信息。

```
QScriptContextInfo.__init__ (self)
```

构造一个空[QScriptContextInfo](qscriptcontextinfo.html)。

**See also** [isNull](qscriptcontextinfo.html#isNull)（ ） 。

```
int QScriptContextInfo.columnNumber (self)
```

```
QString QScriptContextInfo.fileName (self)
```

返回在被执行的代码定义，如果可用的文件名，否则返回一个空字符串。

对于Qt的脚本代码，该函数返回被传递给filename参数[QScriptEngine.evaluate](qscriptengine.html#evaluate)（ ） 。

**See also** [lineNumber](qscriptcontextinfo.html#lineNumber)（）和[functionName](qscriptcontextinfo.html#functionName)（ ） 。

```
int QScriptContextInfo.functionEndLineNumber (self)
```

返回在被调用函数的定义结束行号，或-1，如果行号不可用。

结尾行号是唯一可用的，如果[functionType](qscriptcontextinfo.html#functionType)（）是[ScriptFunction](qscriptcontextinfo.html#FunctionType-enum)。

**See also** [functionStartLineNumber](qscriptcontextinfo.html#functionStartLineNumber)（ ） 。

```
int QScriptContextInfo.functionMetaIndex (self)
```

返回调用的函数或元索引， -1，如果荟萃索引不可用。

元指数仅当[functionType](qscriptcontextinfo.html#functionType)（）是[QtFunction](qscriptcontextinfo.html#FunctionType-enum) or [QtPropertyFunction](qscriptcontextinfo.html#FunctionType-enum)。为[QtFunction](qscriptcontextinfo.html#FunctionType-enum)，元索引可以被传递到[QMetaObject.method](qmetaobject.html#method)（）以获得对应的方法定义;为[QtPropertyFunction](qscriptcontextinfo.html#FunctionType-enum)，元索引可以被传递到[QMetaObject.property](qmetaobject.html#property)（ ）来获取相应的属性定义。

**See also** [QScriptContext.thisObject](qscriptcontext.html#thisObject)（ ） 。

```
QString QScriptContextInfo.functionName (self)
```

返回调用的函数的名称，或一个空字符串，如果该名称不可用。

对于类型的脚本功能[QtPropertyFunction](qscriptcontextinfo.html#FunctionType-enum)，这个函数总是返回属性的名称，你可以使用[QScriptContext.argumentCount](qscriptcontext.html#argumentCount)（ ）来区分之间的读取和写入。

**See also** [fileName](qscriptcontextinfo.html#fileName)（）和[functionType](qscriptcontextinfo.html#functionType)（ ） 。

```
QStringList QScriptContextInfo.functionParameterNames (self)
```

返回被调用函数的形参，或空的名字[QStringList](qstringlist.html)如果参数名称不可用。

**See also** [QScriptContext.argument](qscriptcontext.html#argument)（ ） 。

```
int QScriptContextInfo.functionStartLineNumber (self)
```

返回在所调用的函数的定义开始，或-1，如果行数是不可用的行数。

起始行号仅当[functionType](qscriptcontextinfo.html#functionType)（）是[ScriptFunction](qscriptcontextinfo.html#FunctionType-enum)。

**See also** [functionEndLineNumber](qscriptcontextinfo.html#functionEndLineNumber)（）和[fileName](qscriptcontextinfo.html#fileName)（ ） 。

```
FunctionType QScriptContextInfo.functionType (self)
```

[

返回调用的函数的类型。

](qscriptcontextinfo.html#FunctionType-enum)

[**See also**](qscriptcontextinfo.html#FunctionType-enum) [functionName](qscriptcontextinfo.html#functionName)（）和[QScriptContext.callee](qscriptcontext.html#callee)（ ） 。

```
bool QScriptContextInfo.isNull (self)
```

返回True如果[QScriptContextInfo](qscriptcontextinfo.html)是空的，即不包含任何信息。

```
int QScriptContextInfo.lineNumber (self)
```

返回对应于正在执行的语句的行号，或-1，如果行号不可用。

如果正在执行的Qt Script代码的行数才可用。

**See also** [columnNumber](index.htm#columnNumber)（）和[fileName](qscriptcontextinfo.html#fileName)（ ） 。

```
int QScriptContextInfo.scriptId (self)
```

返回在被执行的代码脚本的ID被定义，或者-1，如果ID是不可用（即正在执行的原生功能） 。

**See also** [QScriptEngineAgent.scriptLoad](qscriptengineagent.html#scriptLoad)（ ） 。

```
bool QScriptContextInfo.__eq__ (self, QScriptContextInfo other)
```

```
bool QScriptContextInfo.__ne__ (self, QScriptContextInfo other)
```