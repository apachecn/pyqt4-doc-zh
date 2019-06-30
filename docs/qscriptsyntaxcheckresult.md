# QScriptSyntaxCheckResult Class Reference

## [[QtScript](index.htm) module]

该QScriptSyntaxCheckResult类提供了一个脚本语法检查的结果。[More...](#details)

### Types

*   `enum State { Error, Intermediate, Valid }`

### Methods

*   `__init__ (self, QScriptSyntaxCheckResult other)`
*   `int errorColumnNumber (self)`
*   `int errorLineNumber (self)`
*   `QString errorMessage (self)`
*   `State state (self)`

* * *

## Detailed Description

该QScriptSyntaxCheckResult类提供了一个脚本语法检查的结果。

QScriptSyntaxCheckResult被退回[QScriptEngine.checkSyntax](qscriptengine.html#checkSyntax)（ ）提供有关语法信息（ ）脚本的正确性。

* * *

## Type Documentation

```
QScriptSyntaxCheckResult.State
```

此枚举指定一个语法检查的状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptSyntaxCheckResult.Error` | `0` | 该程序包含一个语法错误。 |
| `QScriptSyntaxCheckResult.Intermediate` | `1` | 该方案是不完整的。 |
| `QScriptSyntaxCheckResult.Valid` | `2` | 该程序是一个语法正确的Qt Script程序。 |

* * *

## Method Documentation

```
QScriptSyntaxCheckResult.__init__ (self, QScriptSyntaxCheckResult other)
```

构造一个新的[QScriptSyntaxCheckResult](qscriptsyntaxcheckresult.html)从_other_结果。

```
int QScriptSyntaxCheckResult.errorColumnNumber (self)
```

返回此错误的列号[QScriptSyntaxCheckResult](qscriptsyntaxcheckresult.html)，或-1，如果没有任何错误。

**See also** [state](qscriptsyntaxcheckresult.html#state)（）和[errorLineNumber](qscriptsyntaxcheckresult.html#errorLineNumber)（ ） 。

```
int QScriptSyntaxCheckResult.errorLineNumber (self)
```

返回此错误的行号[QScriptSyntaxCheckResult](qscriptsyntaxcheckresult.html)，或-1，如果没有任何错误。

**See also** [state](qscriptsyntaxcheckresult.html#state)（）和[errorMessage](qscriptsyntaxcheckresult.html#errorMessage)（ ） 。

```
QString QScriptSyntaxCheckResult.errorMessage (self)
```

返回此错误消息[QScriptSyntaxCheckResult](qscriptsyntaxcheckresult.html)，或一个空字符串，如果没有错误。

**See also** [state](qscriptsyntaxcheckresult.html#state)（）和[errorLineNumber](qscriptsyntaxcheckresult.html#errorLineNumber)（ ） 。

```
State QScriptSyntaxCheckResult.state (self)
```

[](qscriptsyntaxcheckresult.html#State-enum)

[返回此状态](qscriptsyntaxcheckresult.html#State-enum)[QScriptSyntaxCheckResult](qscriptsyntaxcheckresult.html)。