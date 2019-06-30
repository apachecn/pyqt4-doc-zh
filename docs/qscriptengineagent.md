# QScriptEngineAgent Class Reference

## [[QtScript](index.htm) module]

该QScriptEngineAgent类提供了一个接口来报告有关事件[QScriptEngine](qscriptengine.html)执行。[More...](#details)

### Types

*   `enum Extension { DebuggerInvocationRequest }`

### Methods

*   `__init__ (self, QScriptEngine engine)`
*   `contextPop (self)`
*   `contextPush (self)`
*   `QScriptEngine engine (self)`
*   `exceptionCatch (self, int scriptId, QScriptValue exception)`
*   `exceptionThrow (self, int scriptId, QScriptValue exception, bool hasHandler)`
*   `QVariant extension (self, Extension extension, QVariant argument = QVariant())`
*   `functionEntry (self, int scriptId)`
*   `functionExit (self, int scriptId, QScriptValue returnValue)`
*   `positionChange (self, int scriptId, int lineNumber, int columnNumber)`
*   `scriptLoad (self, int id, QString program, QString fileName, int baseLineNumber)`
*   `scriptUnload (self, int id)`
*   `bool supportsExtension (self, Extension extension)`

* * *

## Detailed Description

该QScriptEngineAgent类提供了一个接口来报告有关事件[QScriptEngine](qscriptengine.html)执行。

该QScriptEngineAgent类是用来监视和/或控制的一个执行工具的基础[QScriptEngine](qscriptengine.html)如调试器和分析器。

为了处理脚本加载和卸载事件，重新实现[scriptLoad](qscriptengineagent.html#scriptLoad)（）和[scriptUnload](qscriptengineagent.html#scriptUnload)（）函数。[scriptLoad](qscriptengineagent.html#scriptLoad)（）被输入到后称为[QScriptEngine.evaluate](qscriptengine.html#evaluate)（ ）已经被解析，执行给定的脚本权利之前。该引擎可为每个脚本一个ID ，它可作为一个参数来[scriptLoad](qscriptengineagent.html#scriptLoad)（）;随后，其它事件处理程序可以使用该ID来识别特定的脚本。一个常见的用法[scriptLoad](qscriptengineagent.html#scriptLoad)（ ）是保留的脚本文本，文件名和底线号（原输入[QScriptEngine.evaluate](qscriptengine.html#evaluate)（）），以使其他的事件处理程序可以例如一个行号映射到文本的相应的行。

[scriptUnload](qscriptengineagent.html#scriptUnload)（ ）被调用时，[QScriptEngine](qscriptengine.html)已经不再使用的脚本;的QScriptEngineAgent可能在这一点上安全地丢弃任何与脚本（如脚本文本）相关联的资源。注意，后[scriptUnload](qscriptengineagent.html#scriptUnload)（ ）被调用时，[QScriptEngine](qscriptengine.html)可重复使用相关的脚本ID为新脚本（即作为参数传递给后续调用[scriptLoad](qscriptengineagent.html#scriptLoad)（））。

评价下面的脚本将导致[scriptUnload](qscriptengineagent.html#scriptUnload)（ ）被调用的评估完成后立即：

```
 var a = Math.random() + 2;

```

评价下面的脚本将\ B { }不导致调用[scriptUnload](qscriptengineagent.html#scriptUnload)（ ）当评估完成：

```
 function cube(a) {
     return a * a * a;
 }

 var a = cube(3);

```

该脚本不被卸载，因为它定义了一个函数（`cube`）保留在脚本环境评估已完成。如果后续的脚本中删除该`cube`功能（例如，通过将其设置为`null`） ，[scriptUnload](qscriptengineagent.html#scriptUnload)（ ）当函数被垃圾收集会被调用。一般而言，一个脚本不卸载，直到发动机已确定没有其内容被引用。

处理脚本函数调用和返回，重新实现[functionEntry](qscriptengineagent.html#functionEntry)（）和[functionExit](qscriptengineagent.html#functionExit)（）函数。[functionEntry](qscriptengineagent.html#functionEntry)（ ）当一个脚本函数将要执行的调用;[functionExit](qscriptengineagent.html#functionExit)（）被调用时，一个脚本函数即将返回，无论是正常还是由于异常。

为了处理单个脚本语句，重新实现[positionChange](qscriptengineagent.html#positionChange)（ ） 。[positionChange](qscriptengineagent.html#positionChange)（）被调用每次引擎将要执行的脚本的一个新的语句，因此提供的脚本监控的最好水平。

为了处理异常，重新实现[exceptionThrow](qscriptengineagent.html#exceptionThrow)（）和[exceptionCatch](qscriptengineagent.html#exceptionCatch)（ ） 。[exceptionThrow](qscriptengineagent.html#exceptionThrow)（）被调用时，一个脚本异常被抛出，它已被处理之前。[exceptionCatch](qscriptengineagent.html#exceptionCatch)（ ）被调用时，一个异常处理程序存在，并执行将在处理程序代码将被收回。

* * *

## Type Documentation

```
QScriptEngineAgent.Extension
```

这个枚举指定可能的扩展到[QScriptEngineAgent](qscriptengineagent.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptEngineAgent.DebuggerInvocationRequest` | `0` | 代理手柄`debugger`脚本语句。 |

**See also** [extension](qscriptengineagent.html#extension)（ ） 。

* * *

## Method Documentation

```
QScriptEngineAgent.__init__ (self, QScriptEngine engine)
```

该_engine_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QScriptEngineAgent](qscriptengineagent.html)对象为给定的_engine_。

该发动机采用了代理的所有权。

Call [QScriptEngine.setAgent](qscriptengine.html#setAgent)（ ）使本剂中的活性剂。

```
QScriptEngineAgent.contextPop (self)
```

在当前脚本上下文将要弹出这个函数被调用。

默认实现不执行任何操作。

**See also** [contextPush](qscriptengineagent.html#contextPush)（）和[functionExit](qscriptengineagent.html#functionExit)（ ） 。

```
QScriptEngineAgent.contextPush (self)
```

这个函数被调用时，一个新的脚本上下文一直推。

默认实现不执行任何操作。

**See also** [contextPop](qscriptengineagent.html#contextPop)（）和[functionEntry](qscriptengineagent.html#functionEntry)（ ） 。

```
QScriptEngine QScriptEngineAgent.engine (self)
```

[](qscriptengine.html)

[返回](qscriptengine.html)[QScriptEngine](qscriptengine.html)此代理相关联。

```
QScriptEngineAgent.exceptionCatch (self, int scriptId, QScriptValue exception)
```

这个函数被调用的时候给出_exception_即将被捕获，在所确定的脚本_scriptId_。

如果你想处理此事件重新实现这个函数。

默认实现不执行任何操作。

**See also** [exceptionThrow](qscriptengineagent.html#exceptionThrow)（ ） 。

```
QScriptEngineAgent.exceptionThrow (self, int scriptId, QScriptValue exception, bool hasHandler)
```

这个函数被调用的时候给出_exception_发生在发动机，在所确定的脚本_scriptId_。如果异常是由本地的Qt脚本函数抛出，_scriptId_是-1。

If _hasHandler_诚然，有一个`catch` or `finally`块将处理该异常。如果_hasHandler_是假的，没有异常处理程序。

如果你想处理此事件重新实现这个函数。例如，一个调试器可以当一个未捕获的异常发生时通知用户（即_hasHandler_是假的） 。

默认实现不执行任何操作。

**See also** [exceptionCatch](qscriptengineagent.html#exceptionCatch)（ ） 。

```
QVariant QScriptEngineAgent.extension (self, Extension extension, QVariant argument = QVariant())
```

这个虚函数可以在重新实现[QScriptEngineAgent](qscriptengineagent.html)子类以提供扩展的支持。可选的_argument_可以作为输入提供给_extension_;结果必须在一个形式被返回[QVariant](qvariant.html)。您可以致电[supportsExtension](qscriptengineagent.html#supportsExtension)（ ）来检查一个扩展是支持的[QScriptEngineAgent](qscriptengineagent.html)。默认情况下，没有扩展名的支持，这个函数返回一个无效[QVariant](qvariant.html)。

如果实现[DebuggerInvocationRequest](qscriptengineagent.html#Extension-enum)扩展， Qt的脚本会调用这个函数时，`debugger`语句在脚本中遇到的问题。该_argument_是[QVariantList](qvariant.html#QVariantList-typedef)包含三个项目：第一个项目是scriptId （长） ，第二项是行数（一个int ） ，第三项是列数（一个整数） 。

**See also** [supportsExtension](qscriptengineagent.html#supportsExtension)（ ） 。

```
QScriptEngineAgent.functionEntry (self, int scriptId)
```

这个函数被调用时，一个脚本函数被调用的引擎。如果脚本的功能是不是原生的Qt脚本功能，它驻留在确定脚本_scriptId_否则，_scriptId_是-1。

这个函数被调用执行脚本函数的开始之前。你可以得到[QScriptContext](qscriptcontext.html)与函数调用相关[QScriptEngine.currentContext](qscriptengine.html#currentContext)（ ） 。可传递给函数的参数。

重新实现这个函数来处理此事件。例如，一个调试器的实现可以重新实现这个函数（和[functionExit](qscriptengineagent.html#functionExit)（））来跟踪调用堆栈和提供步骤，以上的功能。

默认实现不执行任何操作。

**See also** [functionExit](qscriptengineagent.html#functionExit)（ ）[positionChange](qscriptengineagent.html#positionChange)（）和[QScriptEngine.currentContext](qscriptengine.html#currentContext)（ ） 。

```
QScriptEngineAgent.functionExit (self, int scriptId, QScriptValue returnValue)
```

当目前执行的脚本函数即将返回该函数被调用。如果脚本的功能是不是原生的Qt脚本功能，它驻留在确定脚本_scriptId_否则，_scriptId_是-1。该_returnValue_是脚本函数将返回值。

只是脚本函数返回之前调用此函数。您仍然可以访问[QScriptContext](qscriptcontext.html)与脚本函数调用相关联[QScriptEngine.currentContext](qscriptengine.html#currentContext)（ ） 。

如果发动机的[hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ）函数返回True ，脚本函数退出，由于异常，否则，脚本函数正常返回。

重新实现这个函数来处理此事件，通常你会那么还需要重新实现[functionEntry](qscriptengineagent.html#functionEntry)（ ） 。

默认实现不执行任何操作。

**See also** [functionEntry](qscriptengineagent.html#functionEntry)（）和[QScriptEngine.hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ） 。

```
QScriptEngineAgent.positionChange (self, int scriptId, int lineNumber, int columnNumber)
```

这个函数被调用当发动机即将在确定脚本执行一个新的语句_scriptId_。该语句开始由指定的行和列_lineNumber_是不是原生的Qt脚本函数生成此事件。

重新实现这个函数来处理此事件。例如，一个调试器的实现可以重新实现这个功能，提供线，由线步进，和一个分析器实现可以用它来计算被执行每个语句的次数。

默认实现不执行任何操作。

**Note:** _columnNumber_未定义

**See also** [scriptLoad](qscriptengineagent.html#scriptLoad)（）和[functionEntry](qscriptengineagent.html#functionEntry)（ ） 。

```
QScriptEngineAgent.scriptLoad (self, int id, QString program, QString fileName, int baseLineNumber)
```

这个函数被调用时，引擎解析的脚本，并与给定关联的它_id_。该ID可以用来识别在随后的事件通知这个特定的脚本。

_program_，_fileName_和_baseLineNumber_是原始参数的[QScriptEngine.evaluate](qscriptengine.html#evaluate)（ ）调用触发此事件。

这个函数被调用之前的脚本即将进行评估。

您可以重新实现此功能来记录关于脚本的信息，例如，通过保留脚本文本，你可以得到的文本行对应于一个后续调用一个行号[positionChange](qscriptengineagent.html#positionChange)（ ） 。

默认实现不执行任何操作。

**See also** [scriptUnload](qscriptengineagent.html#scriptUnload)（ ） 。

```
QScriptEngineAgent.scriptUnload (self, int id)
```

这个函数被调用时，引擎已经丢弃确定给定的脚本_id_。

您可以重新实现这个函数来清除任何已与脚本相关的资源。

默认实现不执行任何操作。

**See also** [scriptLoad](qscriptengineagent.html#scriptLoad)（ ） 。

```
bool QScriptEngineAgent.supportsExtension (self, Extension extension)
```

返回True如果[QScriptEngineAgent](qscriptengineagent.html)支持给定_extension_否则，则返回False。默认情况下，没有扩展名的支持。

**See also** [extension](qscriptengineagent.html#extension)（ ） 。