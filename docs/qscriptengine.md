# QScriptEngine Class Reference

## [[QtScript](index.htm) module]

该代码QScriptEngine类提供​​用于评估的Qt Script代码的环境。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum QObjectWrapOption { ExcludeChildObjects, ExcludeSuperClassMethods, ExcludeSuperClassProperties, AutoCreateDynamicProperties, ..., ExcludeSlots }`
*   `class **[QObjectWrapOptions](index.htm)**`
*   `enum ValueOwnership { QtOwnership, ScriptOwnership, AutoOwnership }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QObject parent)`
*   `abortEvaluation (self, QScriptValue result = QScriptValue())`
*   `QScriptEngineAgent agent (self)`
*   `QStringList availableExtensions (self)`
*   `bool canEvaluate (self, QString program)`
*   `clearExceptions (self)`
*   `collectGarbage (self)`
*   `QScriptContext currentContext (self)`
*   `QScriptValue defaultPrototype (self, int metaTypeId)`
*   `QScriptValue evaluate (self, QString program, QString fileName = QString(), int lineNumber = 1)`
*   `QScriptValue globalObject (self)`
*   `bool hasUncaughtException (self)`
*   `QStringList importedExtensions (self)`
*   `QScriptValue importExtension (self, QString extension)`
*   `installTranslatorFunctions (self, QScriptValue object = QScriptValue())`
*   `bool isEvaluating (self)`
*   `QScriptValue newArray (self, int length = 0)`
*   `QScriptValue newDate (self, float value)`
*   `QScriptValue newDate (self, QDateTime value)`
*   `QScriptValue newFunction (self, callable signature, int length = 0)`
*   `QScriptValue newFunction (self, callable signature, QScriptValue prototype, int length = 0)`
*   `QScriptValue newObject (self)`
*   `QScriptValue newObject (self, QScriptClass scriptClass, QScriptValue data = QScriptValue())`
*   `QScriptValue newQMetaObject (self, QMetaObject metaObject, QScriptValue ctor = QScriptValue())`
*   `QScriptValue newQObject (self, QObject object, ValueOwnership ownership = QScriptEngine.QtOwnership, QObjectWrapOptions options = 0)`
*   `QScriptValue newQObject (self, QScriptValue scriptObject, QObject qtObject, ValueOwnership ownership = QScriptEngine.QtOwnership, QObjectWrapOptions options = 0)`
*   `QScriptValue newRegExp (self, QRegExp regexp)`
*   `QScriptValue newRegExp (self, QString pattern, QString flags)`
*   `QScriptValue newVariant (self, QVariant value)`
*   `QScriptValue newVariant (self, QScriptValue object, QVariant value)`
*   `QScriptValue nullValue (self)`
*   `popContext (self)`
*   `int processEventsInterval (self)`
*   `QScriptContext pushContext (self)`
*   `reportAdditionalMemoryCost (self, int size)`
*   `setAgent (self, QScriptEngineAgent agent)`
*   `setDefaultPrototype (self, int metaTypeId, QScriptValue prototype)`
*   `setGlobalObject (self, QScriptValue object)`
*   `setProcessEventsInterval (self, int interval)`
*   `QScriptValue toObject (self, QScriptValue value)`
*   `QScriptString toStringHandle (self, QString str)`
*   `QScriptValue uncaughtException (self)`
*   `QStringList uncaughtExceptionBacktrace (self)`
*   `int uncaughtExceptionLineNumber (self)`
*   `QScriptValue undefinedValue (self)`

### Static Methods

*   `QScriptSyntaxCheckResult checkSyntax (QString program)`

### Qt Signals

*   `void signalHandlerException (const QScriptValue&)`

* * *

## Detailed Description

该代码QScriptEngine类提供​​用于评估的Qt Script代码的环境。

请参阅[QtScript](index.htm)文档，了解关于Qt的脚本语言，以及如何开始使用脚本你的C + +应用程序的信息。

### Evaluating Scripts

使用[evaluate](qscriptengine.html#evaluate)（ ）来评估的脚本代码，这是C + +的等效内置的脚本功能`eval()`。

```
 QScriptEngine myEngine;
 [QScriptValue](qscriptvalue.html) three = myEngine.evaluate("1 + 2");

```

[evaluate](qscriptengine.html#evaluate)（ ）返回一个[QScriptValue](qscriptvalue.html)保存了评价的结果。该[QScriptValue](qscriptvalue.html)类提供函数计算结果转换为不同的C + +类型（如[QScriptValue.toString](qscriptvalue.html#toString)（）和[QScriptValue.toNumber](qscriptvalue.html#toNumber)（））。

下面的代码片段显示了一个脚本函数可以被定义，然后从C + +调用的使用[QScriptValue.call](qscriptvalue.html#call)（）：

```
 [QScriptValue](qscriptvalue.html) fun = myEngine.evaluate("(function(a, b) { return a + b; })");
 QScriptValueList args;
 args << 1 << 2;
 [QScriptValue](qscriptvalue.html) threeAgain = fun.call([QScriptValue](qscriptvalue.html)(), args);

```

如可以从上面的代码段中可以看出，一个脚本被提供给发动机以字符串的形式。加载脚本的一种常见方法是通过读取一个文件的内容，并把它传递给[evaluate](qscriptengine.html#evaluate)（）：

```
 [QString](qstring.html) fileName = "helloworld.qs";
 [QFile](qfile.html) scriptFile(fileName);
 if (!scriptFile.open([QIODevice](qiodevice.html).ReadOnly))
     // handle error
 [QTextStream](qtextstream.html) stream(&scriptFile);
 [QString](qstring.html) contents = stream.readAll();
 scriptFile.close();
 myEngine.evaluate(contents, fileName);

```

在这里，我们传递的文件名作为第二个参数[evaluate](qscriptengine.html#evaluate)（ ） 。这并不影响评价以任何方式，第二个参数是用来识别脚本调试通用字符串（例如，文件名我们现在将任何显示[uncaughtExceptionBacktrace](qscriptengine.html#uncaughtExceptionBacktrace)（ ）涉及脚本） 。

### Engine Configuration

该[globalObject](qscriptengine.html#globalObject)（ ）函数返回**Global Object**与脚本引擎相关联。全局对象的属性是从任何脚本代码访问（也就是说，它们是全局变量） 。通常情况下，评估“用户”脚本之前，你会希望通过添加一个或多个属性的全局对象来配置脚本引擎：

```
 myEngine.globalObject().setProperty("myNumber", 123);
 ...
 [QScriptValue](qscriptvalue.html) myNumberPlusOne = myEngine.evaluate("myNumber + 1");

```

添加自定义属性的脚本环境是提供脚本API是特定于应用程序的标准方法之一。通常这些自定义属性是由创建的对象[newQObject](qscriptengine.html#newQObject)（）或[newObject](qscriptengine.html#newObject)通过创建（ ）函数或构造函数[newFunction](qscriptengine.html#newFunction)（ ） 。

### Script Exceptions

[evaluate](qscriptengine.html#evaluate)（ ）可以抛出一个脚本异常（例如，由于语法错误） ，在这种情况下，返回值是被抛出的值（通常是`Error`对象） 。您可以检查是否评估通过调用出现异常[hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ） 。在这种情况下，你可以调用的错误对象的toString （）来获取错误消息。目前未捕获的异常，也可通过[uncaughtException](qscriptengine.html#uncaughtException)（ ） 。调用[clearExceptions](qscriptengine.html#clearExceptions)（ ）将导致任何未捕获的异常被清除。

```
 [QScriptValue](qscriptvalue.html) result = myEngine.evaluate(...);
 if (myEngine.hasUncaughtException()) {
     int line = myEngine.uncaughtExceptionLineNumber();
     qDebug() << "uncaught exception at line" << line << ":" << result.toString();
 }

```

该[checkSyntax](qscriptengine.html#checkSyntax)（）函数可以被用来确定是否代码可以被有效地传递给[evaluate](qscriptengine.html#evaluate)（ ） 。

### Script Object Creation

使用[newObject](qscriptengine.html#newObject)（）来创建一个标准的Qt Script对象，这是C + +的等效脚本语句`new Object()`。您可以使用对象特定功能​​的[QScriptValue](qscriptvalue.html)操纵脚本对象（例如[QScriptValue.setProperty](qscriptvalue.html#setProperty)（））。同样地，使用[newArray](qscriptengine.html#newArray)（）来创建一个Qt脚本数组对象。使用[newDate](qscriptengine.html#newDate)（ ）来创建一个`Date`对象，并[newRegExp](qscriptengine.html#newRegExp)（ ）来创建一个`RegExp`对象。

### QObject Integration

使用[newQObject](qscriptengine.html#newQObject)（ ）来包装[QObject](qobject.html)（或子类）的指针。[newQObject](qscriptengine.html#newQObject)（ ）返回一个代理脚本对象，属性，孩子，的信号和槽[QObject](qobject.html)可作为代理对象的属性。不需要任何绑定代码，因为它是使用Qt元对象系统动态地进行。

```
 [QPushButton](qpushbutton.html) button;
 [QScriptValue](qscriptvalue.html) scriptButton = myEngine.newQObject(&button);
 myEngine.globalObject().setProperty("button", scriptButton);

 myEngine.evaluate("button.checkable = true");

 qDebug() << scriptButton.property("checkable").toBoolean();
 scriptButton.property("show").call(); // call the show() slot

```

使用[qScriptConnect](qscriptengine.html#qScriptConnect)（ ）到一个C + +的信号连接到一个脚本函数，这是Qt脚本相当于[QObject.connect](qobject.html#connect)（ ） 。当一个脚本函数以响应一个C + +的信号调用时，它可能会导致脚本异常，你可以连接到[signalHandlerException](qscriptengine.html#signalHandlerException)（）信号捕捉这样的异常。

使用[newQMetaObject](qscriptengine.html#newQMetaObject)（ ）来包装[QMetaObject](qmetaobject.html)，这给你的一个“脚本表示”[QObject](qobject.html)基类。[newQMetaObject](qscriptengine.html#newQMetaObject)（ ）返回一个代理脚本对象，可作为代理对象的属性的类的枚举值。您还可以指定将用于构造类的对象（例如，当构造函数是从一个脚本调用）的函数。对于具有“标准”的Qt类的构造函数， Qt的脚本可以提供一个默认的构造函数的脚本为你见[scriptValueFromQMetaObject](qscriptengine.html#scriptValueFromQMetaObject)（ ） 。

如需了解更多信息[QObject](qobject.html)整合，见[Making Applications Scriptable](index.htm)

### Support for Custom C++ Types

使用[newVariant](qscriptengine.html#newVariant)（ ）来包装[QVariant](qvariant.html)。这可以被用来存储自定义的值（非[QObject](qobject.html)已登记的Qt的间位型系统）的C + +类型。为了使这种类型的脚本化的，通常一个原型（代表）对象的C + +类通过调用相关联[setDefaultPrototype](qscriptengine.html#setDefaultPrototype)（）;原型对象定义了C + +类型的脚本API 。不同的是[QObject](qobject.html)集成，没有自动绑定可能在这里，即你必须使用创建脚本API自己，例如[QScriptable](index.htm)类。

使用[fromScriptValue](qscriptengine.html#fromScriptValue)（ ）投从[QScriptValue](qscriptvalue.html)另一种类型，并[toScriptValue](qscriptengine.html#toScriptValue)（ ）来创建一个[QScriptValue](qscriptvalue.html)从另一个值。您可以指定C + +类型的转换是要与执行[qScriptRegisterMetaType](qscriptengine.html#qScriptRegisterMetaType)（）和[qScriptRegisterSequenceMetaType](qscriptengine.html#qScriptRegisterSequenceMetaType)（ ） 。默认情况下， Qt的脚本将使用[QVariant](qvariant.html)存储自定义类型的值。

### Importing Extensions

使用[importExtension](qscriptengine.html#importExtension)（ ）来导入基于插件的扩展进入发动机。通话[availableExtensions](qscriptengine.html#availableExtensions)（）来获取一个列表命名所有可用的扩展，[importedExtensions](qscriptengine.html#importedExtensions)（）来获取一个列表的命名只有那些已导入扩展。

Call [pushContext](qscriptengine.html#pushContext)（）打开了一个新的变量范围，[popContext](qscriptengine.html#popContext)（ ）来关闭当前作用域。如果你正在实施，评估含临时变量定义（如脚本代码的扩展，这是非常有用`var foo = 123;`）是安全的丢弃时，评估已经完成。

### Native Functions

使用[newFunction](qscriptengine.html#newFunction)（ ）包装机（C + + ）的功能，包括构造为自己的自定义类型，使得这些可以从脚本代码被调用。这些功能必须有签名[QScriptEngine.FunctionSignature](qscriptengine.html#FunctionSignature-typedef)。然后，您可以通过该函数作为参数传递给[newFunction](qscriptengine.html#newFunction)（ ） 。这里是一个函数返回它的前两个参数的和的一个例子：

```
 [QScriptValue](qscriptvalue.html) myAdd([QScriptContext](qscriptcontext.html) *context, QScriptEngine *engine)
 {
    [QScriptValue](qscriptvalue.html) a = context->argument(0);
    [QScriptValue](qscriptvalue.html) b = context->argument(1);
    return a.toNumber() + b.toNumber();
 }

```

为了揭露这个功能的脚本代码，可以将其设置为全局对象的一个属性：

```
 [QScriptValue](qscriptvalue.html) fun = myEngine.newFunction(myAdd);
 myEngine.globalObject().setProperty("myAdd", fun);

```

一旦做到这一点，脚本代码可以调用你的函数在完全相同的方式作为一个“正常”的脚本函数：

```
 [QScriptValue](qscriptvalue.html) result = myEngine.evaluate("myAdd(myNumber, 1)");

```

### Long-running Scripts

如果您需要评估从主（图形用户界面）线程可能长时间运行脚本，你应该首先调用[setProcessEventsInterval](qscriptengine.html#setProcessEventsInterval)（ ） ，以确保该GUI保持响应。你可以通过调用中止当前运行脚本[abortEvaluation](qscriptengine.html#abortEvaluation)（ ） 。您可以决定是否发动机是通过调用当前正在运行的脚本[isEvaluating](qscriptengine.html#isEvaluating)（ ） 。

### Garbage Collection

Qt的脚本对象可以被垃圾收集时，他们不再被引用。有没有保证，以时自动垃圾回收将会发生。

该[collectGarbage](qscriptengine.html#collectGarbage)（ ）函数可以被调用来显式地请求垃圾收集。

该[reportAdditionalMemoryCost](qscriptengine.html#reportAdditionalMemoryCost)（ ）函数可以被调用，以表明一个Qt Script对象佔并非由脚本环境管理内存。报告的额外成本使得它更可能是垃圾收集器将被触发。这可能是有用的，例如，当许多习俗，当地人的Qt Script对象被分配。

### Core Debugging/Tracing Facilities

由于Qt的4.4 ，您可以通过有关脚本执行（如脚本函数调用和语句的执行）活动通知[QScriptEngineAgent](qscriptengineagent.html)接口，见[setAgent](qscriptengine.html#setAgent)（）函数。这可以被用来实现调试和代码QScriptEngine的分析。

* * *

## Type Documentation

```
QScriptEngine.QObjectWrapOption
```

这些标志包装时指定一个选项[QObject](qobject.html)终场前[newQObject](qscriptengine.html#newQObject)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptEngine.ExcludeChildObjects` | `0x0001` | 该脚本对象不会暴露子对象的属性。 |
| `QScriptEngine.ExcludeSuperClassMethods` | `0x0002` | 该脚本对象不会暴露在超类继承的信号和槽。 |
| `QScriptEngine.ExcludeSuperClassProperties` | `0x0004` | 该脚本对象不会暴露在超类继承的属性。 |
| `QScriptEngine.ExcludeSuperClassContents` | `0x0006` | 简写形式ExcludeSuperClassMethods &#124; ExcludeSuperClassProperties |
| `QScriptEngine.ExcludeDeleteLater` | `0x0010` | 该脚本对象将不会暴露[QObject.deleteLater](qobject.html#deleteLater)（）槽。 |
| `QScriptEngine.ExcludeSlots` | `0x0020` | 该脚本对象将不会暴露[QObject](qobject.html)的插槽。 |
| `QScriptEngine.AutoCreateDynamicProperties` | `0x0100` | 不已经在存在属性[QObject](qobject.html)将创建作为该对象的动态属性，而不是作为脚本对象的属性。 |
| `QScriptEngine.PreferExistingWrapperObject` | `0x0200` | 如果与请求的配置一个包装对象已存在，则返回该对象。 |
| `QScriptEngine.SkipMethodsInEnumeration` | `0x0008` | 枚举对象的属性时，不包括方法（信号和槽） 。 |

该QObjectWrapOptions类型是一个typedef为[QFlags](index.htm)\u003cQObjectWrapOption\u003e 。它存储QObjectWrapOption值的或组合。

```
QScriptEngine.ValueOwnership
```

包装一个C + +的值，例如，当此枚举指定所有权通过使用[newQObject](qscriptengine.html#newQObject)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptEngine.QtOwnership` | `0` | 标准的Qt所有权规则适用，即相关联的对象将永远不会被明确地被脚本引擎删除。这是默认的。 （[QObject](qobject.html)所有权的解释[Object Trees & Ownership](index.htm)。 ） |
| `QScriptEngine.ScriptOwnership` | `1` | 该值是由脚本环境拥有。相关的数据都将被删除时，相应的（比如，在垃圾收集器发现，有没有更多的活动引用到的值） 。 |
| `QScriptEngine.AutoOwnership` | `2` | 如果关联的对象有父， Qt的所有权规则（ QtOwnership ），否则，该对象是由脚本环境（ ScriptOwnership ）全资拥有。 |

* * *

## Method Documentation

```
QScriptEngine.__init__ (self)
```

构造一个[QScriptEngine](qscriptengine.html)对象。

该[globalObject](qscriptengine.html#globalObject)（ ）初始化为具有属性中所描述 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)，第15.1节。

```
QScriptEngine.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QScriptEngine](qscriptengine.html)与给定对象_parent_。

该[globalObject](qscriptengine.html#globalObject)（ ）初始化为具有属性中所描述 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)，第15.1节。

```
QScriptEngine.abortEvaluation (self, QScriptValue result = QScriptValue())
```

中止任何脚本评估目前正在进行这款发动机。给定_result_被传递回作为评价的结果（即，它是从调用返回到[evaluate](qscriptengine.html#evaluate)（ ）被中止） 。

如果发动机没有评估一个脚本（即[isEvaluating](qscriptengine.html#isEvaluating)（ ）返回False ） ，这个函数不执行任何操作。

调用此函数，如果您需要中止正在运行的脚本出于某种原因，如当你发现这个脚本已经运行了几秒钟没有完成。

此功能被引入Qt的4.4 。

**See also** [evaluate](qscriptengine.html#evaluate)（ ）[isEvaluating](qscriptengine.html#isEvaluating)（）和[setProcessEventsInterval](qscriptengine.html#setProcessEventsInterval)（ ） 。

```
QScriptEngineAgent QScriptEngine.agent (self)
```

[

返回在此引擎上，或0当前已安装，如果没有安装代理的代理。

此功能被引入Qt的4.4 。

](qscriptengineagent.html)

[**See also**](qscriptengineagent.html) [setAgent](qscriptengine.html#setAgent)（ ） 。

```
QStringList QScriptEngine.availableExtensions (self)
```

返回一个列表的命名可以导入现有的扩展使用[importExtension](qscriptengine.html#importExtension)（）函数。该列表包括已导入扩展。

此功能被引入Qt的4.4 。

**See also** [importExtension](qscriptengine.html#importExtension)（）和[importedExtensions](qscriptengine.html#importedExtensions)（ ） 。

```
bool QScriptEngine.canEvaluate (self, QString program)
```

```
QScriptSyntaxCheckResult QScriptEngine.checkSyntax (QString program)
```

[](qscriptsyntaxcheckresult.html)

[检查给定的语法_program_。返回](qscriptsyntaxcheckresult.html)[QScriptSyntaxCheckResult](qscriptsyntaxcheckresult.html)对象，该对象包含检查的结果。

此功能被引入Qt的4.5 。

```
QScriptEngine.clearExceptions (self)
```

清除在这款发动机的任何未捕获的异常。

此功能被引入Qt的4.4 。

**See also** [hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ） 。

```
QScriptEngine.collectGarbage (self)
```

运行垃圾回收器。

垃圾收集器将尝试通过定位和处理不再可达脚本环境中的对象回收内存。

通常你不需要调用此函数;垃圾收集器会自动被调用时，[QScriptEngine](qscriptengine.html)决定是明智的，这样做（即已经建立了一定数量的新对象时） 。但是，您可以明确地请求垃圾收集，应尽快进行调用这个函数。

**See also** [reportAdditionalMemoryCost](qscriptengine.html#reportAdditionalMemoryCost)（ ） 。

```
QScriptContext QScriptEngine.currentContext (self)
```

[

返回当前上下文。

](qscriptcontext.html)

[当前上下文通常访问来检索本地函数的参数和' this'对象，为了方便，它可作为第一个参数](qscriptcontext.html)[QScriptEngine.FunctionSignature](qscriptengine.html#FunctionSignature-typedef)。

```
QScriptValue QScriptEngine.defaultPrototype (self, int metaTypeId)
```

[](qscriptvalue.html)

[返回与给定关联的默认原型_metaTypeId_，或无效](qscriptvalue.html)[QScriptValue](qscriptvalue.html)如果没有预设的样机已定。

**See also** [setDefaultPrototype](qscriptengine.html#setDefaultPrototype)（ ） 。

```
QScriptValue QScriptEngine.evaluate (self, QString program, QString fileName = QString(), int lineNumber = 1)
```

[

Evaluates _program_，使用_lineNumber_作为基准线数，并返回该评价的结果。

脚本代码会在当前上下文中进行评估。

](qscriptvalue.html)

[的评价_program_可能会导致发动机异常，在这种情况下，返回值将是被抛出（通常是一个例外`Error`对象） 。您可以致电](qscriptvalue.html)[hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ） ，以确定是否发生在最后一次通话异常，评估（ ） 。

_lineNumber_用于指定一个开始行号为_program_;报告，涉及到本次评测的发动机（如行号信息[uncaughtExceptionLineNumber](qscriptengine.html#uncaughtExceptionLineNumber)（ ） ）将基于这个论点。例如，如果_program_由两行代码，并在第二行的语句会导致一个脚本异常，[uncaughtExceptionLineNumber](qscriptengine.html#uncaughtExceptionLineNumber)（ ）将返回给定的_lineNumber_加1 。当没有指定起始行号，行号为1型。

_fileName_用于错误报告。例如，在错误的对象的文件名可以访问通过“文件名”属性，如果它提供了这个功能。

**See also** [canEvaluate](index.htm#canEvaluate)（ ）[hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ）[isEvaluating](qscriptengine.html#isEvaluating)（）和[abortEvaluation](qscriptengine.html#abortEvaluation)（ ） 。

```
QScriptValue QScriptEngine.globalObject (self)
```

[

返回此引擎的全局对象。

](qscriptvalue.html)

[默认情况下，全局对象包含了内置对象是一部分](qscriptvalue.html) [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)，如数学，日期和字符串。此外，您可以设置全局对象的属性，以使所有脚本代码你自己的扩展。在脚本代码的非局部变量将被创建为全局对象的属性，以及在全局代码中的局部变量。

**See also** [setGlobalObject](qscriptengine.html#setGlobalObject)（ ） 。

```
bool QScriptEngine.hasUncaughtException (self)
```

返回True如果最后一个脚本评价，导致未捕获的异常，否则返回False 。

唯一的例外状态被清除时，[evaluate](qscriptengine.html#evaluate)（）被调用。

**See also** [uncaughtException](qscriptengine.html#uncaughtException)（）和[uncaughtExceptionLineNumber](qscriptengine.html#uncaughtExceptionLineNumber)（ ） 。

```
QStringList QScriptEngine.importedExtensions (self)
```

返回一个列表的命名已导入的扩展使用[importExtension](qscriptengine.html#importExtension)（）函数。

此功能被引入Qt的4.4 。

**See also** [availableExtensions](qscriptengine.html#availableExtensions)（ ） 。

```
QScriptValue QScriptEngine.importExtension (self, QString extension)
```

[](qscriptvalue.html)

[进口给定的_extension_这个](qscriptvalue.html)[QScriptEngine](qscriptengine.html)。回报[undefinedValue](qscriptengine.html#undefinedValue)（ ）如果分机已成功导入。您可以致电[hasUncaughtException](qscriptengine.html#hasUncaughtException)（）来检查是否发生错误，在这种情况下，返回值是被抛出的异常（通常是一个值`Error`对象） 。

[QScriptEngine](qscriptengine.html)确保一个特定的扩展仅导入一次，随后调用importExtension （ ）使用相同的扩展名会做什么，回报[undefinedValue](qscriptengine.html#undefinedValue)（ ） 。

**See also** [availableExtensions](qscriptengine.html#availableExtensions)（ ）[QScriptExtensionPlugin](index.htm)和[Creating QtScript Extensions](index.htm)。

```
QScriptEngine.installTranslatorFunctions (self, QScriptValue object = QScriptValue())
```

安装在给定的翻译功能_object_或全局对象上，如果没有指定对象。

Qt的剧本翻译的功能和C + +翻译功能之间的关系如下表所述：

| Script Function | Corresponding C++ Function |
| --- | --- |
| qsTr() | [QObject.tr](qobject.html#tr)() |
| [QT_TR_NOOP](index.htm#QT_TR_NOOP)() | [QT_TR_NOOP](index.htm#QT_TR_NOOP)() |
| qsTranslate() | [QCoreApplication.translate](qcoreapplication.html#translate)() |
| [QT_TRANSLATE_NOOP](index.htm#QT_TRANSLATE_NOOP)() | [QT_TRANSLATE_NOOP](index.htm#QT_TRANSLATE_NOOP)() |
| qsTrId() (since 4.7) | [qtTrId](index.htm#qtTrId)() |
| [QT_TRID_NOOP](index.htm#QT_TRID_NOOP)() (since 4.7) | [QT_TRID_NOOP](index.htm#QT_TRID_NOOP)() |

此功能被引入Qt的4.5 。

**See also** [Internationalization with Qt](index.htm)。

```
bool QScriptEngine.isEvaluating (self)
```

返回True如果该发动机目前正在评估一个脚本，否则返回False 。

此功能被引入Qt的4.4 。

**See also** [evaluate](qscriptengine.html#evaluate)（）和[abortEvaluation](qscriptengine.html#abortEvaluation)（ ） 。

```
QScriptValue QScriptEngine.newArray (self, int length = 0)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)与给定的类数组对象_length_。

**See also** [newObject](qscriptengine.html#newObject)（ ） 。

```
QScriptValue QScriptEngine.newDate (self, float value)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)之类的日期与给定对象_value_（毫秒自1970年1月1日的数字， UTC ） 。

```
QScriptValue QScriptEngine.newDate (self, QDateTime value)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)从给定的类Date对象_value_。

**See also** [QScriptValue.toDateTime](qscriptvalue.html#toDateTime)（ ） 。

```
QScriptValue QScriptEngine.newFunction (self, callable signature, int length = 0)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QScriptValue](qscriptvalue.html)一个封装了原生（ C + +）的功能。_fun_必须是一个C + +函数签名[QScriptEngine.FunctionSignature](qscriptengine.html#FunctionSignature-typedef)。_length_是参数的数量_fun_预计，这将成为`length`的创建属性[QScriptValue](qscriptvalue.html)。

需要注意的是_length_只给出了函数需要的参数个数的指示，一个函数的实际调用可以包括任意数量的参数。您可以检查[argumentCount()](qscriptcontext.html#argumentCount)的[QScriptContext](qscriptcontext.html)与调用相关联，以确定传递的参数的实际数目。

A `prototype`属性是生成的函数对象自动创建的，以提供该功能将被用作构造函数的可能性。

通过结合newFunction （ ）和属性标志[QScriptValue.PropertyGetter](qscriptvalue.html#PropertyFlag-enum)和[QScriptValue.PropertySetter](qscriptvalue.html#PropertyFlag-enum)，您可以创建像在脚本代码的正常性能的脚本对象的属性，但实际上通过函数（类似于物业的工作访问[Qt's Property System](index.htm#qt-s-property-system)） 。例如：

```
 static [QScriptValue](qscriptvalue.html) getSetFoo([QScriptContext](qscriptcontext.html) *context, [QScriptEngine](qscriptengine.html) *engine)
 {
     [QScriptValue](qscriptvalue.html) callee = context->callee();
     if (context->argumentCount() == 1) // writing?
         callee.setProperty("value", context->argument(0));
     return callee.property("value");
 }

 ....

 [QScriptValue](qscriptvalue.html) object = engine.newObject();
 object.setProperty("foo", engine.newFunction(getSetFoo),
     [QScriptValue](qscriptvalue.html).PropertyGetter | [QScriptValue](qscriptvalue.html).PropertySetter);

```

当属性`foo`脚本对象的脚本代码随后访问，`getSetFoo()`将被调用来处理访问。在这种特殊情况下，我们选择了存储的“真实”的价值`foo`作为访问函数本身的属性，你可以自由的做任何你喜欢这个功能。

在上面的例子中，一个单一的原生函数用来处理读取和写入属性;参数计数来确定，如果我们正在处理一个读或写。您还可以使用两个单独的函数，只需指定相关标志（[QScriptValue.PropertyGetter](qscriptvalue.html#PropertyFlag-enum) or [QScriptValue.PropertySetter](qscriptvalue.html#PropertyFlag-enum)）设置属性时，例如：

```
 [QScriptValue](qscriptvalue.html) object = engine.newObject();
 object.setProperty("foo", engine.newFunction(getFoo), [QScriptValue](qscriptvalue.html).PropertyGetter);
 object.setProperty("foo", engine.newFunction(setFoo), [QScriptValue](qscriptvalue.html).PropertySetter);

```

**See also** [QScriptValue.call](qscriptvalue.html#call)（ ） 。

```
QScriptValue QScriptEngine.newFunction (self, callable signature, QScriptValue prototype, int length = 0)
```

[

从创建一个构造函数_fun_用给定的_length_。该`prototype`所得到的函数的属性被设定为给定的_prototype_。该`constructor`物业_prototype_被设定为所产生的功能。

](qscriptvalue.html)

[当一个函数被调用的构造函数（例如`new Foo()`） ，与函数调用相关的` this'对象是新对象，该函数将初始化;这个默认构造对象的原型将是功能的公共`prototype`属性。如果你总是想要的功能表现为一个构造函数（如`Foo()`还应该创建一个新的对象） ，或者如果你需要创建自己的对象，而不是使用默认的` this'对象，你应该确保你的对象的原型是否设置正确，或者通过手动设置它，或者，当包装一个自定义类型，由经注册的](qscriptvalue.html)[defaultPrototype](qscriptengine.html#defaultPrototype)该类型的（） 。例如：

```
 [QScriptValue](qscriptvalue.html) Foo([QScriptContext](qscriptcontext.html) *context, [QScriptEngine](qscriptengine.html) *engine)
 {
     if (context->calledAsConstructor()) {
         // initialize the new object
         context->thisObject().setProperty("bar", ...);
         // ...
         // return a non-object value to indicate that the
         // thisObject() should be the result of the "new Foo()" expression
         return engine->undefinedValue();
     } else {
         // not called as "new Foo()", just "Foo()"
         // create our own object and return that one
         [QScriptValue](qscriptvalue.html) object = engine->newObject();
         object.setPrototype(context->callee().property("prototype"));
         object.setProperty("baz", ...);
         return object;
     }
 }

 ...

 [QScriptValue](qscriptvalue.html) fooProto = engine->newObject();
 fooProto.setProperty("whatever", ...);
 engine->globalObject().setProperty("Foo", engine->newFunction(Foo, fooProto));

```

包装一个自定义类型，并为它提供一个构造函数，你通常会做这样的事情：

```
 class Bar { ... };

 Q_DECLARE_METATYPE(Bar)

 [QScriptValue](qscriptvalue.html) constructBar([QScriptContext](qscriptcontext.html) *context, [QScriptEngine](qscriptengine.html) *engine)
 {
     Bar bar;
     // initialize from arguments in context, if desired
     ...
     return engine->toScriptValue(bar);
 }

 class BarPrototype : public [QObject](qobject.html), public [QScriptable](index.htm)
 {
 // provide the scriptable interface of this type using slots and properties
 ...
 };

 ...

 // create and register the Bar prototype and constructor in the engine
 BarPrototype *barPrototypeObject = new BarPrototype(...);
 [QScriptValue](qscriptvalue.html) barProto = engine->newQObject(barPrototypeObject);
 engine->setDefaultPrototype(qMetaTypeId<Bar>, barProto);
 [QScriptValue](qscriptvalue.html) barCtor = engine->newFunction(constructBar, barProto);
 engine->globalObject().setProperty("Bar", barCtor);

```

```
QScriptValue QScriptEngine.newObject (self)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)Object类的对象。

所创建的对象的原型将是对象的原型对象。

**See also** [newArray](qscriptengine.html#newArray)（）和[QScriptValue.setProperty](qscriptvalue.html#setProperty)（ ） 。

```
QScriptValue QScriptEngine.newObject (self, QScriptClass scriptClass, QScriptValue data = QScriptValue())
```

[

这是一个重载函数。

](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)给定的类的对象，_scriptClass_。

所创建的对象的原型将是对象的原型对象。

_data_如果指定，则设定为新的对象的内部数据（使用[QScriptValue.setData](qscriptvalue.html#setData)（））。

此功能被引入Qt的4.4 。

**See also** [QScriptValue.scriptClass](qscriptvalue.html#scriptClass)（）和[reportAdditionalMemoryCost](qscriptengine.html#reportAdditionalMemoryCost)（ ） 。

```
QScriptValue QScriptEngine.newQMetaObject (self, QMetaObject metaObject, QScriptValue ctor = QScriptValue())
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)对象，它代表一个[QObject](qobject.html)类，使用给定的_metaObject_和构造函数_ctor_。

的枚举_metaObject_（与Q_ENUMS申报）可作为创建的属性[QScriptValue](qscriptvalue.html)。当类被称为一个函数，_ctor_将被调用来创建类的新实例。

例如：

```
 [QScriptValue](qscriptvalue.html) mySpecialQObjectConstructor([QScriptContext](qscriptcontext.html) *context,
                                          [QScriptEngine](qscriptengine.html) *engine)
 {
     [QObject](qobject.html) *parent = context->argument(0).toQObject();
     [QObject](qobject.html) *object = new [QObject](qobject.html)(parent);
     return engine->newQObject(object, [QScriptEngine](qscriptengine.html).ScriptOwnership);
 }

 ...

 [QScriptValue](qscriptvalue.html) ctor = engine.newFunction(mySpecialQObjectConstructor);
 [QScriptValue](qscriptvalue.html) metaObject = engine.newQMetaObject(&[QObject](qobject.html).staticMetaObject, ctor);
 engine.globalObject().setProperty("QObject", metaObject);

 [QScriptValue](qscriptvalue.html) result = engine.evaluate("new QObject()");

```

**See also** [newQObject](qscriptengine.html#newQObject)（）和[scriptValueFromQMetaObject](qscriptengine.html#scriptValueFromQMetaObject)（ ） 。

```
QScriptValue QScriptEngine.newQObject (self, QObject object, ValueOwnership ownership = QScriptEngine.QtOwnership, QObjectWrapOptions options = 0)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)对象，它封装了给定的[QObject](qobject.html) _object_，使用给定的_ownership_。给定_options_控制与所得到的脚本对象的交互的各个方面。

信号和槽，属性和儿童_object_可作为所创建的属性[QScriptValue](qscriptvalue.html)。欲了解更多信息，请参阅[QtScript](index.htm)文档。

If _object_是一个空指针，这个函数返回[nullValue](qscriptengine.html#nullValue)（ ） 。

如果默认样机已经注册了_object_的类（或它的超类，递归） ，新的脚本对象的原型将被设置为默认的原型。

如果给定的_object_外面被删除[QtScript](index.htm)的控制，任何试图访问已删除[QObject](qobject.html)的成员通过[QtScript](index.htm)包装对象（通过脚本代码或C + + ）将导致脚本异常。

**See also** [QScriptValue.toQObject](qscriptvalue.html#toQObject)（）和[reportAdditionalMemoryCost](qscriptengine.html#reportAdditionalMemoryCost)（ ） 。

```
QScriptValue QScriptEngine.newQObject (self, QScriptValue scriptObject, QObject qtObject, ValueOwnership ownership = QScriptEngine.QtOwnership, QObjectWrapOptions options = 0)
```

[

这是一个重载函数。

初始化给定的_scriptObject_保持在给定_qtObject_，并返回该_scriptObject_。

](qscriptvalue.html)

[此功能使您能够“促进”一个普通的Qt Script对象（由创建](qscriptvalue.html)[newObject](qscriptengine.html#newObject)（）函数），以一[QObject](qobject.html)代理，或取代[QObject](qobject.html)包含先前所创建的对象内[newQObject](qscriptengine.html#newQObject)（）函数。

的原型（ ）_scriptObject_将保持不变。

If _scriptObject_不是一个对象，这个函数的行为类似于正常[newQObject](qscriptengine.html#newQObject)（ ） ，也就是说，它会创建一个新的脚本对象并返回它。

当你想提供一个脚本构造的这个功能是非常有用的[QObject](qobject.html)基类。如果你的构造函数中调用一个`new`表达式（[QScriptContext.isCalledAsConstructor](qscriptcontext.html#isCalledAsConstructor)（ ）返回True ） ，你可以通过[QScriptContext.thisObject](qscriptcontext.html#thisObject)（ ） （默认构造脚本对象）这个函数来初始化新的对象。

此功能被引入Qt的4.4 。

**See also** [reportAdditionalMemoryCost](qscriptengine.html#reportAdditionalMemoryCost)（ ） 。

```
QScriptValue QScriptEngine.newRegExp (self, QRegExp regexp)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)一流的RegExp与给定的对象_regexp_。

**See also** [QScriptValue.toRegExp](qscriptvalue.html#toRegExp)（ ） 。

```
QScriptValue QScriptEngine.newRegExp (self, QString pattern, QString flags)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)一流的RegExp与给定的对象_pattern_和_flags_。

法律标志是“G” （全局） ， 'I' （忽略大小写） ，和“M”（多行） 。

```
QScriptValue QScriptEngine.newVariant (self, QVariant value)
```

[](qscriptvalue.html)

[创建](qscriptvalue.html)[QtScript](index.htm)物体保持给定的变体_value_。

如果默认样机已经注册的元类型的id_value_，那么创建的对象的原型将是原型，否则，原型将是对象的原型对象。

**See also** [setDefaultPrototype](qscriptengine.html#setDefaultPrototype)（ ）[QScriptValue.toVariant](qscriptvalue.html#toVariant)（）和[reportAdditionalMemoryCost](qscriptengine.html#reportAdditionalMemoryCost)（ ） 。

```
QScriptValue QScriptEngine.newVariant (self, QScriptValue object, QVariant value)
```

[

这是一个重载函数。

初始化给定的Qt脚本_object_以保持给定的变体_value_，并返回该_object_。

](qscriptvalue.html)

[此功能使您能够“促进”一个普通的Qt Script对象（由创建](qscriptvalue.html)[newObject](qscriptengine.html#newObject)（）函数），以一个变体，或替换包含在对象内的变体通过先前建立的[newVariant](qscriptengine.html#newVariant)（）函数。

的原型（ ）_object_将保持不变。

If _object_不是一个对象，这个函数的行为类似于正常[newVariant](qscriptengine.html#newVariant)（ ） ，也就是说，它会创建一个新的脚本对象并返回它。

当你想提供一个脚本构造一个C + +类型，此功能非常有用。如果你的构造函数中调用一个`new`表达式（[QScriptContext.isCalledAsConstructor](qscriptcontext.html#isCalledAsConstructor)（ ）返回True ） ，你可以通过[QScriptContext.thisObject](qscriptcontext.html#thisObject)（ ） （默认构造脚本对象）这个函数来初始化新的对象。

此功能被引入Qt的4.4 。

**See also** [reportAdditionalMemoryCost](qscriptengine.html#reportAdditionalMemoryCost)（ ） 。

```
QScriptValue QScriptEngine.nullValue (self)
```

[](qscriptvalue.html)

[返回](qscriptvalue.html)[QScriptValue](qscriptvalue.html)的原始类型空。

**See also** [undefinedValue](qscriptengine.html#undefinedValue)（ ） 。

```
QScriptEngine.popContext (self)
```

跳出当前执行上下文，并恢复前一个。该功能必须在配合使用[pushContext](qscriptengine.html#pushContext)（ ） 。

**See also** [pushContext](qscriptengine.html#pushContext)（ ） 。

```
int QScriptEngine.processEventsInterval (self)
```

返回呼叫之间的时间间隔以毫秒为单位[QCoreApplication.processEvents](qcoreapplication.html#processEvents)（ ）解释器运行时。

**See also** [setProcessEventsInterval](qscriptengine.html#setProcessEventsInterval)（ ） 。

```
QScriptContext QScriptEngine.pushContext (self)
```

[](qscriptcontext.html)

[进入一个新的执行上下文，并返回相关的](qscriptcontext.html)[QScriptContext](qscriptcontext.html)对象。

一旦你与上下文做的，你应该叫[popContext](qscriptengine.html#popContext)（ ）来恢复旧的上下文。

默认情况下，新的上下文的` this'对象是全局对象。上下文的[callee](qscriptcontext.html#callee)（ ）将是无效的。

当您要评估的脚本代码，就好像它是一个函数体，此功能非常有用。您可以使用上下文的[activationObject](qscriptcontext.html#activationObject)（ ）来初始化局部变量将提供给脚本。例如：

```
 [QScriptEngine](qscriptengine.html) engine;
 [QScriptContext](qscriptcontext.html) *context = engine.pushContext();
 context->activationObject().setProperty("myArg", 123);
 engine.evaluate("var tmp = myArg + 42");
 ...
 engine.popContext();

```

在上面的例子中，新的变量“TMP ”，在脚本中定义的将是本地上下文;换句话说，脚本不会对地球环境有任何影响。

万一栈溢出，则返回0

**See also** [popContext](qscriptengine.html#popContext)（ ） 。

```
QScriptEngine.reportAdditionalMemoryCost (self, int size)
```

报告的给予额外的内存消耗_size_，以字节为单位，对垃圾收集器。

这个函数可以调用，以表明一个Qt Script对象都有一个与之关联的内存不是由Qt的脚本本身的管理。报告的额外成本使得它更可能是垃圾收集器将被触发。

请注意，如果额外的记忆体与脚本环境之外的对象共享，成本不应该被报导，因为收集了Qt Script对象将不会导致内存被释放反正。

Negative _size_值将被忽略，即这个功能不能用于报告，额外的内存已经被释放。

This function was introduced in Qt 4.7.

**See also** [collectGarbage](qscriptengine.html#collectGarbage)（ ） 。

```
QScriptEngine.setAgent (self, QScriptEngineAgent agent)
```

安装给定的_agent_在此引擎上。该代理将收到有关脚本执行的各种活动。当你想找出到底是什么引擎这样做是有用的，例如：何时[evaluate](qscriptengine.html#evaluate)（）被调用。代理接口是一样的调试器和分析器工具的基础。

该引擎维护的所有权_agent_。

如有调用此函数将取代现有的代理。

此功能被引入Qt的4.4 。

**See also** [agent](qscriptengine.html#agent)（ ） 。

```
QScriptEngine.setDefaultPrototype (self, int metaTypeId, QScriptValue prototype)
```

设置确定了在给定的C + +类的默认原型_metaTypeId_至_prototype_。

默认的原型为类型的值的脚本接口_metaTypeId_当该类型的值从脚本代码访问。每当脚本引擎（隐式或显式地）创建一个[QScriptValue](qscriptvalue.html)从类型的值_metaTypeId_，默认的原型将被设置为[QScriptValue](qscriptvalue.html)的原型。

该_prototype_对象本身可以使用的两个主要技术之一来建造;最简单的是子类化[QScriptable](index.htm)，它使您能够通过定义类型的脚本API[QObject](qobject.html)属性和插槽。另一种可能性是通过调用来创建一个脚本对象[newObject](qscriptengine.html#newObject)（ ） ，并填充包裹所需的属性（如原生函数的对象[newFunction](qscriptengine.html#newFunction)（））。

**See also** [defaultPrototype](qscriptengine.html#defaultPrototype)（ ）[qScriptRegisterMetaType](qscriptengine.html#qScriptRegisterMetaType)（ ）[QScriptable](index.htm)和[Default Prototypes Example](index.htm)。

```
QScriptEngine.setGlobalObject (self, QScriptValue object)
```

设置要在给定的这台发动机的全局对象_object_。如果_object_是不是一个有效的脚本对象，这个函数不执行任何操作。

当设置一个自定义的全局对象，你可能要使用[QScriptValueIterator](qscriptvalueiterator.html)复制的标准全局对象的属性，或者，你可以设置你的自定义对象的内部原型是原始全局对象。

此功能被引入Qt的4.5 。

**See also** [globalObject](qscriptengine.html#globalObject)（ ） 。

```
QScriptEngine.setProcessEventsInterval (self, int interval)
```

设置呼叫QCoreApplication.processEvents之间的时间间隔_interval_毫秒。

当解释器运行时，所有事件处理是在默认情况下阻止。这意味着，例如，该GUI将不被更新和定时器将不被触发。以允许解释器在执行期间的事件处理1可指定的处理的时间间隔是一个正的值，表示毫秒的每个时间间隔的秒数[QCoreApplication.processEvents](qcoreapplication.html#processEvents)（）被调用。

默认值是-1，这解释器执行过程中禁用事件处理。

您可以使用[QCoreApplication.postEvent](qcoreapplication.html#postEvent)（）发表，在接下来的时间间隔进行自定义处理事件。例如，你可以保持的脚本和呼叫的总运行时间轨迹[abortEvaluation](qscriptengine.html#abortEvaluation)当你发现这个脚本已经运行了很长一段时间没有完成（ ） 。

**See also** [processEventsInterval](qscriptengine.html#processEventsInterval)（ ） 。

```
QScriptValue QScriptEngine.toObject (self, QScriptValue value)
```

[](qscriptvalue.html)

[转换给定的_value_一个对象，如果有这样的转换是可能的，否则返回一个无效的](qscriptvalue.html)[QScriptValue](qscriptvalue.html)。该转换是根据下面的表执行：

| Input Type | Result |
| --- | --- |
| Undefined | An invalid [QScriptValue](qscriptvalue.html). |
| Null | An invalid [QScriptValue](qscriptvalue.html). |
| Boolean | A new Boolean object whose internal value is set to the value of the boolean. |
| Number | A new Number object whose internal value is set to the value of the number. |
| String | A new String object whose internal value is set to the value of the string. |
| Object | The result is the object itself (no conversion). |

此功能被引入Qt的4.5 。

**See also** [newObject](qscriptengine.html#newObject)（ ） 。

```
QScriptString QScriptEngine.toStringHandle (self, QString str)
```

[

返回表示给定字符串的句柄，_str_。

](qscriptstring.html)

[](qscriptstring.html)[QScriptString](qscriptstring.html)可以用来快速查找属性和比较属性名的脚本对象。

此功能被引入Qt的4.4 。

**See also** [QScriptValue.property](qscriptvalue.html#property)（ ） 。

```
QScriptValue QScriptEngine.uncaughtException (self)
```

[](qscriptvalue.html)

[返回当前未捕获的异常，或无效](qscriptvalue.html)[QScriptValue](qscriptvalue.html)如果没有捕获的异常。

唯一的例外值通常是一个`Error`对象，在这种情况下，你可以调用toString（）的返回值来获得一个错误消息。

**See also** [hasUncaughtException](qscriptengine.html#hasUncaughtException)（）和[uncaughtExceptionLineNumber](qscriptengine.html#uncaughtExceptionLineNumber)（ ） 。

```
QStringList QScriptEngine.uncaughtExceptionBacktrace (self)
```

返回最后一个未捕获的异常的人类可读的回溯。

它的形式为`&lt;function-name&gt;()@&lt;file-name&gt;:&lt;line-number&gt;`。

**See also** [uncaughtException](qscriptengine.html#uncaughtException)（ ） 。

```
int QScriptEngine.uncaughtExceptionLineNumber (self)
```

返回最近发生的未捕获异常的代码行数。

行号从1开始的，除非一个不同的基地被指定为第二个参数[evaluate](qscriptengine.html#evaluate)（ ） 。

**See also** [hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ） 。

```
QScriptValue QScriptEngine.undefinedValue (self)
```

[](qscriptvalue.html)

[返回](qscriptvalue.html)[QScriptValue](qscriptvalue.html)基本类型未定义的。

**See also** [nullValue](qscriptengine.html#nullValue)（ ） 。

* * *

## Qt Signal Documentation

```
void signalHandlerException (const QScriptValue&)
```

这是该信号的默认超载。

当连接到一个信号的脚本功能使这个信号被发射的_exception_。

此功能被引入Qt的4.4 。

**See also** [qScriptConnect](qscriptengine.html#qScriptConnect)（ ） 。