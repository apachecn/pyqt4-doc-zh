# QScriptValue Class Reference

## [[QtScript](index.htm) module]

该QScriptValue类作为一个容器Qt的脚本数据类型。[More...](#details)

### Types

*   `enum PropertyFlag { ReadOnly, Undeletable, SkipInEnumeration, PropertyGetter, ..., UserRange }`
*   `class **[PropertyFlags](index.htm)**`
*   `enum ResolveFlag { ResolveLocal, ResolvePrototype, ResolveScope, ResolveFull }`
*   `class **[ResolveFlags](index.htm)**`
*   `enum SpecialValue { NullValue, UndefinedValue }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QScriptValue other)`
*   `__init__ (self, SpecialValue value)`
*   `__init__ (self, QScriptEngine engine, SpecialValue val)`
*   `__init__ (self, bool value)`
*   `__init__ (self, QScriptEngine engine, bool val)`
*   `__init__ (self, int value)`
*   `__init__ (self, QScriptEngine engine, int val)`
*   `__init__ (self, float value)`
*   `__init__ (self, QScriptEngine engine, float val)`
*   `__init__ (self, QString value)`
*   `__init__ (self, QScriptEngine engine, QString val)`
*   `QScriptValue call (self, QScriptValue thisObject = QScriptValue(), list-of-QScriptValue args = QScriptValueList())`
*   `QScriptValue call (self, QScriptValue thisObject, QScriptValue arguments)`
*   `QScriptValue construct (self, list-of-QScriptValue args = QScriptValueList())`
*   `QScriptValue construct (self, QScriptValue arguments)`
*   `QScriptValue data (self)`
*   `QScriptEngine engine (self)`
*   `bool equals (self, QScriptValue other)`
*   `bool instanceOf (self, QScriptValue ctor)`
*   `bool isArray (self)`
*   `bool isBool (self)`
*   `bool isBoolean (self)`
*   `bool isDate (self)`
*   `bool isError (self)`
*   `bool isFunction (self)`
*   `bool isNull (self)`
*   `bool isNumber (self)`
*   `bool isObject (self)`
*   `bool isQMetaObject (self)`
*   `bool isQObject (self)`
*   `bool isRegExp (self)`
*   `bool isString (self)`
*   `bool isUndefined (self)`
*   `bool isValid (self)`
*   `bool isVariant (self)`
*   `bool lessThan (self, QScriptValue other)`
*   `QScriptValue property (self, QString name, ResolveFlags mode = QScriptValue.ResolvePrototype)`
*   `QScriptValue property (self, QScriptString name, ResolveFlags mode = QScriptValue.ResolvePrototype)`
*   `QScriptValue property (self, int arrayIndex, ResolveFlags mode = QScriptValue.ResolvePrototype)`
*   `PropertyFlags propertyFlags (self, QString name, ResolveFlags mode = QScriptValue.ResolvePrototype)`
*   `PropertyFlags propertyFlags (self, QScriptString name, ResolveFlags mode = QScriptValue.ResolvePrototype)`
*   `QScriptValue prototype (self)`
*   `QScriptClass scriptClass (self)`
*   `setData (self, QScriptValue data)`
*   `setProperty (self, QString name, QScriptValue value, PropertyFlags flags = QScriptValue.KeepExistingFlags)`
*   `setProperty (self, QScriptString name, QScriptValue value, PropertyFlags flags = QScriptValue.KeepExistingFlags)`
*   `setProperty (self, int arrayIndex, QScriptValue value, PropertyFlags flags = QScriptValue.KeepExistingFlags)`
*   `setPrototype (self, QScriptValue prototype)`
*   `setScriptClass (self, QScriptClass scriptClass)`
*   `bool strictlyEquals (self, QScriptValue other)`
*   `bool toBool (self)`
*   `bool toBoolean (self)`
*   `QDateTime toDateTime (self)`
*   `int toInt32 (self)`
*   `float toInteger (self)`
*   `float toNumber (self)`
*   `QScriptValue toObject (self)`
*   `QMetaObject toQMetaObject (self)`
*   `QObject toQObject (self)`
*   `QRegExp toRegExp (self)`
*   `QString toString (self)`
*   `int toUInt16 (self)`
*   `int toUInt32 (self)`
*   `QVariant toVariant (self)`

* * *

## Detailed Description

该QScriptValue类作为一个容器Qt的脚本数据类型。

QScriptValue支持在中定义的类型 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)标准：基元类型，它是未定义，为null ，布尔，数字和字符串;和对象类型。此外， Qt的脚本有内置的支持[QVariant](qvariant.html)，[QObject](qobject.html)和[QMetaObject](qmetaobject.html)。

对于基于对象类型（包括Date和RegExp ） ，使用NEWT （ ）函数[QScriptEngine](qscriptengine.html)（例如[QScriptEngine.newObject](qscriptengine.html#newObject)（） ）来创建所需类型的QScriptValue 。对于原始类型，使用QScriptValue构造函数重载之一。

命名为T （ ）的方法（例如[isBool](qscriptvalue.html#isBool)（ ）[isUndefined](qscriptvalue.html#isUndefined)（） ）可以被用来测试一个值是否是特定类型的。命名为TOT （ ）方法（例如[toBool](qscriptvalue.html#toBool)（ ）[toString](qscriptvalue.html#toString)()) can be used to convert a QScriptValue to another type. You can also use the generic [qscriptvalue_cast](qscriptvalue.html#qscriptvalue_cast)() function.

Object values have zero or more properties which are themselves QScriptValues. Use [setProperty](qscriptvalue.html#setProperty)() to set a property of an object, and call [property](qscriptvalue.html#property)() to retrieve the value of a property.

```
 [QScriptEngine](qscriptengine.html) myEngine;
 QScriptValue myObject = myEngine.newObject();
 QScriptValue myOtherObject = myEngine.newObject();
 myObject.setProperty("myChild", myOtherObject);
 myObject.setProperty("name", "John Doe");

```

Each property can have a set of attributes; these are specified as the third (optional) argument to [setProperty](qscriptvalue.html#setProperty)(). The attributes of a property can be queried by calling the [propertyFlags](qscriptvalue.html#propertyFlags)() function. The following code snippet creates a property that cannot be modified by script code:

```
 QScriptValue val(&myEngine, 123);
 myObject.setProperty("myReadOnlyProperty", val, QScriptValue.ReadOnly);

```

如果你想遍历一个脚本对象的属性，使用[QScriptValueIterator](qscriptvalueiterator.html)类。

对象的值有一个内部`prototype`属性，该属性可以被访问[prototype](qscriptvalue.html#prototype)（）和[setPrototype](qscriptvalue.html#setPrototype)（ ） 。属性添加到原型由具有该原型中的所有对象共享，这被称为基于原型的继承。在实践中，这意味着（默认）的[property](qscriptvalue.html#property)（ ）函数将自动尝试查找看在财产[prototype](qscriptvalue.html#prototype)（ ）（和的原型[prototype](qscriptvalue.html#prototype)（） ，等等） ，如果对象本身不具有所需的特性。请注意，不是由执行这个原型基于查找[setProperty](qscriptvalue.html#setProperty)（）;[setProperty](qscriptvalue.html#setProperty)（ ）总是会在脚本对象本身创造的财产。欲了解更多信息，请参阅[QtScript](index.htm)文档。

函数对象（对象的[isFunction](qscriptvalue.html#isFunction)（ ）返回True ）可以通过调用来调用[call](qscriptvalue.html#call)（ ） 。构造函数可以用来构造新的对象通过调用[construct](qscriptvalue.html#construct)（ ） 。

使用[equals](qscriptvalue.html#equals)（ ）[strictlyEquals](qscriptvalue.html#strictlyEquals)（）和[lessThan](qscriptvalue.html#lessThan)（ ）到QScriptValue比较到另一个。

对象的值可以有与它们相关联的自定义数据，见[setData](qscriptvalue.html#setData)（）和[data](qscriptvalue.html#data)（）函数。默认情况下，这个数据是不可访问的脚本，它可以用来存储你想要用脚本对象相关联的任何数据。通常，这是通过使用自定义类对象（见[QScriptClass](qscriptclass.html)）来存储一个C + +类，它包含了“原生”对象数据。

请注意，一个QScriptValue的量[isObject](qscriptvalue.html#isObject)（ ）是真实的，只有带有一个参考的实际对象;复制QScriptValue将只复制对象的引用，而不是对象本身。如果你想克隆一个对象（即一个对象的属性复制到另一个对象） ，你可以用一个帮助做`for-in`声明脚本代码，或[QScriptValueIterator](qscriptvalueiterator.html)在C + + 。

* * *

## Type Documentation

```
QScriptValue.PropertyFlag
```

这个枚举描述属性的特性。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptValue.ReadOnly` | `0x00000001` | 该属性是只读的。通过Qt的脚本代码试图写入该属性将被忽略。 |
| `QScriptValue.Undeletable` | `0x00000002` | 试图通过Qt的脚本代码`delete`该属性将被忽略。 |
| `QScriptValue.SkipInEnumeration` | `0x00000004` | 该物业不能由一个枚举`for-in`枚举。 |
| `QScriptValue.PropertyGetter` | `0x00000008` | 该物业由一个将被调用来获得属性值函数定义。 |
| `QScriptValue.PropertySetter` | `0x00000010` | 该物业由一个将被调用来设置属性值函数定义。 |

这个标志被用于表示一个现有的属性是一个[QObject](qobject.html)成员（属性或方法） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptValue.KeepExistingFlags` | `0x00000800` | 这个值被用来表示[setProperty](qscriptvalue.html#setProperty)（ ）该物业的标志应保持不变。如果属性不存在，则默认标志（ 0 ）将被使用。 |

标志在此范围内不使用Qt的脚本，并且可以用于定制的目的。

该PropertyFlags类型是一个typedef为[QFlags](index.htm)\u003cPropertyFlag\u003e 。它存储PropertyFlag值的或组合。

```
QScriptValue.ResolveFlag
```

此枚举指定如何查找某个对象的属性。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptValue.ResolveLocal` | `0x00` | 只检查对象自己的属性。 |
| `QScriptValue.ResolvePrototype` | `0x01` | 检查对象本身的属性，然后再搜索原型链。这是默认的。 |

检查对象本身的属性，然后再搜索作用域链。

检查对象本身的属性，然后再搜索原型链，最后搜索的作用域链。

该ResolveFlags类型是一个typedef为[QFlags](index.htm)\u003cResolveFlag\u003e 。它存储ResolveFlag值的或组合。

```
QScriptValue.SpecialValue
```

此枚举用于指定一个单值类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptValue.UndefinedValue` | `1` | 一个未定义的值。 |
| `QScriptValue.NullValue` | `0` | null值。 |

* * *

## Method Documentation

```
QScriptValue.__init__ (self)
```

构造一个无效的[QScriptValue](qscriptvalue.html)。

```
QScriptValue.__init__ (self, QScriptValue other)
```

构造一个新的[QScriptValue](qscriptvalue.html)即副本_other_。

注意，如果_other_本发明的目的（即，[isObject](qscriptvalue.html#isObject)（ ）将返回True ） ，那么只有一个参照相关对象被复制到新的脚本值（即，对象本身不会被复制） 。

```
QScriptValue.__init__ (self, SpecialValue value)
```

```
QScriptValue.__init__ (self, QScriptEngine engine, SpecialValue val)
```

```
QScriptValue.__init__ (self, bool value)
```

```
QScriptValue.__init__ (self, QScriptEngine engine, bool val)
```

```
QScriptValue.__init__ (self, int value)
```

```
QScriptValue.__init__ (self, QScriptEngine engine, int val)
```

```
QScriptValue.__init__ (self, float value)
```

```
QScriptValue.__init__ (self, QScriptEngine engine, float val)
```

构造一个新的[QScriptValue](qscriptvalue.html)用特别的_value_。

此功能被引入Qt的4.5 。

```
QScriptValue.__init__ (self, QString value)
```

构造一个新的[QScriptValue](qscriptvalue.html)用布尔_value_。

此功能被引入Qt的4.5 。

```
QScriptValue.__init__ (self, QScriptEngine engine, QString val)
```

构造一个新的[QScriptValue](qscriptvalue.html)以数字_value_。

此功能被引入Qt的4.5 。

```
QScriptValue QScriptValue.call (self, QScriptValue thisObject = QScriptValue(), list-of-QScriptValue args = QScriptValueList())
```

[](qscriptvalue.html)

[调用此](qscriptvalue.html)[QScriptValue](qscriptvalue.html)作为一个功能，用_thisObject_在函数调用中的' this'对象，并通过_args_作为参数传递给函数。返回从函数返回的值。

如果这[QScriptValue](qscriptvalue.html)是不是一个函数，调用（ ）不执行任何操作，并返回一个无效的[QScriptValue](qscriptvalue.html)。

注意，如果_thisObject_是不是一个对象，全局对象（见[QScriptEngine.globalObject](qscriptengine.html#globalObject)（） ）将被用作`这个'对象。

调用调用（ ）可能会导致异常发生在脚本引擎，在这种情况下， （）调用返回抛出的值（通常是`Error`对象） 。您可以致电[QScriptEngine.hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ） ，以确定是否发生了异常。

```
 [QScriptEngine](qscriptengine.html) engine;
 engine.evaluate("function fullName() { return this.firstName + ' ' + this.lastName; }");
 engine.evaluate("somePerson = { firstName: 'John', lastName: 'Doe' }");

 [QScriptValue](qscriptvalue.html) global = engine.globalObject();
 [QScriptValue](qscriptvalue.html) fullName = global.property("fullName");
 [QScriptValue](qscriptvalue.html) who = global.property("somePerson");
 qDebug() << fullName.call(who).toString(); // "John Doe"

 engine.evaluate("function cube(x) { return x * x * x; }");
 [QScriptValue](qscriptvalue.html) cube = global.property("cube");
 QScriptValueList args;
 args << 3;
 qDebug() << cube.call([QScriptValue](qscriptvalue.html)(), args).toNumber(); // 27

```

**See also** [construct](qscriptvalue.html#construct)（ ） 。

```
QScriptValue QScriptValue.call (self, QScriptValue thisObject, QScriptValue arguments)
```

[](qscriptvalue.html)

[调用此](qscriptvalue.html)[QScriptValue](qscriptvalue.html)作为一个功能，用_thisObject_在函数调用中的' this'对象，并通过_arguments_作为参数传递给函数。返回从函数返回的值。

如果这[QScriptValue](qscriptvalue.html)不是一个函数，[call](qscriptvalue.html#call)（ ）不执行任何操作，并返回一个无效的[QScriptValue](qscriptvalue.html)。

_arguments_可以是一个参数对象，数组， null或undefined ;任何其他类型将导致一个TypeError异常被抛出。

注意，如果_thisObject_是不是一个对象，全局对象（见[QScriptEngine.globalObject](qscriptengine.html#globalObject)（） ）将被用作`这个'对象。

这个功能的一个常见用法是原生函数调用转发到另一个函数：

```
 [QScriptValue](qscriptvalue.html) myNativeFunction([QScriptContext](qscriptcontext.html) *ctx, [QScriptEngine](qscriptengine.html) *)
 {
     [QScriptValue](qscriptvalue.html) otherFunction = ...;
     return otherFunction.call(ctx->thisObject(), ctx->argumentsObject());
 }

```

**See also** [construct](qscriptvalue.html#construct)（）和[QScriptContext.argumentsObject](qscriptcontext.html#argumentsObject)（ ） 。

```
QScriptValue QScriptValue.construct (self, list-of-QScriptValue args = QScriptValueList())
```

[](qscriptvalue.html)

[创建一个新的`Object`并调用这个](qscriptvalue.html)[QScriptValue](qscriptvalue.html)作为一个构造函数，使用创建的对象作为` this'对象和传球_args_作为参数。如果从构造函数调用的返回值是一个对象，则该对象被返回，否则默认的构造的对象返回。

如果这[QScriptValue](qscriptvalue.html)是不是一个函数，构造（ ）不执行任何操作，并返回一个无效的[QScriptValue](qscriptvalue.html)。

调用构造（ ）可能会导致异常发生在脚本引擎，在这种情况下，构建（）返回一个被抛出（通常是一个值`Error`对象） 。您可以致电[QScriptEngine.hasUncaughtException](qscriptengine.html#hasUncaughtException)（ ） ，以确定是否发生了异常。

**See also** [call](qscriptvalue.html#call)（）和[QScriptEngine.newObject](qscriptengine.html#newObject)（ ） 。

```
QScriptValue QScriptValue.construct (self, QScriptValue arguments)
```

[](qscriptvalue.html)

[创建一个新的`Object`并调用这个](qscriptvalue.html)[QScriptValue](qscriptvalue.html)作为一个构造函数，使用创建的对象作为` this'对象和传球_arguments_作为参数。如果从构造函数调用的返回值是一个对象，则该对象被返回，否则默认的构造的对象返回。

如果这[QScriptValue](qscriptvalue.html)不是一个函数，[construct](qscriptvalue.html#construct)（ ）不执行任何操作，并返回一个无效的[QScriptValue](qscriptvalue.html)。

_arguments_可以是一个参数对象，数组， null或undefined 。任何其他类型将导致一个TypeError异常被抛出。

**See also** [call](qscriptvalue.html#call)（ ）[QScriptEngine.newObject](qscriptengine.html#newObject)（）和[QScriptContext.argumentsObject](qscriptcontext.html#argumentsObject)（ ） 。

```
QScriptValue QScriptValue.data (self)
```

[](qscriptvalue.html)

[返回此内部数据](qscriptvalue.html)[QScriptValue](qscriptvalue.html)对象。[QtScript](index.htm)使用这个属性来存储日期，字符串，数字和布尔对象的原始值。对于其他类型的对象，自定义数据可以使用存储[setData](qscriptvalue.html#setData)（ ） 。

此功能被引入Qt的4.4 。

**See also** [setData](qscriptvalue.html#setData)（ ） 。

```
QScriptEngine QScriptValue.engine (self)
```

[](qscriptengine.html)

[返回](qscriptengine.html)[QScriptEngine](qscriptengine.html)创建此[QScriptValue](qscriptvalue.html)，或者0 ，如果这[QScriptValue](qscriptvalue.html)无效或值不与特定的发动机相关联。

```
bool QScriptValue.equals (self, QScriptValue other)
```

返回True如果[QScriptValue](qscriptvalue.html)等于_other_，否则返回False 。比较如下所述的行为 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)11.9.3节， “抽象相等比较算法” 。

这个函数可以返回真实的，即使这种类型[QScriptValue](qscriptvalue.html)是的类型不同_other_值，即比较不严格。例如， 9号比较字符串“ 9”返回True ;一个未定义的值进行比较，以空值返回True ;一个比较`Number`对象，其原始值是6到`String`对象，其原始值“6”返回True ;和数字1比较的布尔值`true`返回True。如果你想执行一个比较没有这样的隐式数值转换，使用[strictlyEquals](qscriptvalue.html#strictlyEquals)（ ） 。

注意，如果这个[QScriptValue](qscriptvalue.html)或_other_值是对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的valueOf（）的函数（也可能[toString](qscriptvalue.html#toString)（ ） ） ，试图将对象转换为原始值（可能导致一个未捕获的脚本异常） 。

**See also** [strictlyEquals](qscriptvalue.html#strictlyEquals)（）和[lessThan](qscriptvalue.html#lessThan)（ ） 。

```
bool QScriptValue.instanceOf (self, QScriptValue ctor)
```

返回True如果[QScriptValue](qscriptvalue.html)是的一个实例_other_否则返回False 。

This [QScriptValue](qscriptvalue.html)被认为是一个实例_other_如果_other_是一个函数和的值`prototype`物业_other_是在原型的这条产业链[QScriptValue](qscriptvalue.html)。

```
bool QScriptValue.isArray (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是Array类的一个对象，否则返回False 。

**See also** [QScriptEngine.newArray](qscriptengine.html#newArray)（ ） 。

```
bool QScriptValue.isBool (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是原始的Boolean类型，否则返回False 。

此功能被引入Qt的4.5 。

**See also** [toBool](qscriptvalue.html#toBool)（ ） 。

```
bool QScriptValue.isBoolean (self)
```

```
bool QScriptValue.isDate (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是Date类的一个对象，否则返回False 。

**See also** [QScriptEngine.newDate](qscriptengine.html#newDate)（ ） 。

```
bool QScriptValue.isError (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是Error类的一个对象，否则返回False 。

**See also** [QScriptContext.throwError](qscriptcontext.html#throwError)（ ） 。

```
bool QScriptValue.isFunction (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是一个函数，否则返回False 。

**See also** [call](qscriptvalue.html#call)（ ） 。

```
bool QScriptValue.isNull (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是原始类型的Null ;否则返回False。

**See also** [QScriptEngine.nullValue](qscriptengine.html#nullValue)（ ） 。

```
bool QScriptValue.isNumber (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是的基本类型数，否则返回False 。

**See also** [toNumber](qscriptvalue.html#toNumber)（ ） 。

```
bool QScriptValue.isObject (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是Object类型，否则返回False 。

需要注意的是函数值，变量值和[QObject](qobject.html)值是对象，所以对于这样的值该函数返回True 。

**See also** [toObject](index.htm#toObject)（）和[QScriptEngine.newObject](qscriptengine.html#newObject)（ ） 。

```
bool QScriptValue.isQMetaObject (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是[QMetaObject](qmetaobject.html)否则返回False 。

**See also** [toQMetaObject](qscriptvalue.html#toQMetaObject)（）和[QScriptEngine.newQMetaObject](qscriptengine.html#newQMetaObject)（ ） 。

```
bool QScriptValue.isQObject (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是[QObject](qobject.html)否则返回False 。

注意：这个函数返回True ，即使[QObject](qobject.html)这[QScriptValue](qscriptvalue.html)包裹已被删除。

**See also** [toQObject](qscriptvalue.html#toQObject)（）和[QScriptEngine.newQObject](qscriptengine.html#newQObject)（ ） 。

```
bool QScriptValue.isRegExp (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是设置了RegExp类的一个对象，否则返回False 。

**See also** [QScriptEngine.newRegExp](qscriptengine.html#newRegExp)（ ） 。

```
bool QScriptValue.isString (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是原始类型为String ，否则返回False 。

**See also** [toString](qscriptvalue.html#toString)（ ） 。

```
bool QScriptValue.isUndefined (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是未定义的原始类型，否则返回False 。

**See also** [QScriptEngine.undefinedValue](qscriptengine.html#undefinedValue)（ ） 。

```
bool QScriptValue.isValid (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是有效的，否则返回False 。

```
bool QScriptValue.isVariant (self)
```

返回True如果[QScriptValue](qscriptvalue.html)是一个变量的值，否则返回False 。

**See also** [toVariant](qscriptvalue.html#toVariant)（）和[QScriptEngine.newVariant](qscriptengine.html#newVariant)（ ） 。

```
bool QScriptValue.lessThan (self, QScriptValue other)
```

返回True如果[QScriptValue](qscriptvalue.html)小于_other_，否则返回False 。比较如下所述的行为 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)11.8.5节， “抽象关系比较算法” 。

注意，如果这个[QScriptValue](qscriptvalue.html)或_other_值是对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的valueOf（）的函数（也可能[toString](qscriptvalue.html#toString)（ ） ） ，试图将对象转换为原始值（可能导致一个未捕获的脚本异常） 。

**See also** [equals](qscriptvalue.html#equals)（ ） 。

```
QScriptValue QScriptValue.property (self, QString name, ResolveFlags mode = QScriptValue.ResolvePrototype)
```

[](qscriptvalue.html)

[返回此值](qscriptvalue.html)[QScriptValue](qscriptvalue.html)的属性与给定的_name_，使用给定的_mode_为解决该房产。

如果没有这样的属性存在，无效[QScriptValue](qscriptvalue.html)返回。

如果属性是使用一个getter函数实现的（即有[PropertyGetter](qscriptvalue.html#PropertyFlag-enum)标志设置） ，要求财产（ ）对脚本引擎的副作用，因为getter函数将被调用（可能导致一个未捕获的脚本异常） 。如果发生异常，财产（ ）返回被抛出（通常是一个值`Error`对象） 。

**See also** [setProperty](qscriptvalue.html#setProperty)（ ）[propertyFlags](qscriptvalue.html#propertyFlags)（）和[QScriptValueIterator](qscriptvalueiterator.html)。

```
QScriptValue QScriptValue.property (self, QScriptString name, ResolveFlags mode = QScriptValue.ResolvePrototype)
```

[](qscriptvalue.html)

[返回此值](qscriptvalue.html)[QScriptValue](qscriptvalue.html)的属性与给定的_name_，使用给定的_mode_为解决该房产。

这种超负荷[property](qscriptvalue.html#property)当你需要查找同一个属性重复，因为查询的速度就会加快，当名字被表示为一个字符串实习（）是非常有用的。

此功能被引入Qt的4.4 。

**See also** [QScriptEngine.toStringHandle](qscriptengine.html#toStringHandle)（）和[setProperty](qscriptvalue.html#setProperty)（ ） 。

```
QScriptValue QScriptValue.property (self, int arrayIndex, ResolveFlags mode = QScriptValue.ResolvePrototype)
```

[

这是一个重载函数。

返回属性在给定_arrayIndex_，使用给定的_mode_为解决该房产。

此功能与数组对象时提供了方便和性能。

](qscriptvalue.html)

[如果这](qscriptvalue.html)[QScriptValue](qscriptvalue.html)是不是一个Array对象，这个函数的行为就像[property](qscriptvalue.html#property)（ ）被调用的字符串表示形式_arrayIndex_。

```
PropertyFlags QScriptValue.propertyFlags (self, QString name, ResolveFlags mode = QScriptValue.ResolvePrototype)
```

[

返回属性的标志与给定_name_，使用给定的_mode_为解决该房产。

](index.htm)

[**See also**](index.htm) [property](qscriptvalue.html#property)（ ） 。

```
PropertyFlags QScriptValue.propertyFlags (self, QScriptString name, ResolveFlags mode = QScriptValue.ResolvePrototype)
```

[

返回属性的标志与给定_name_，使用给定的_mode_为解决该房产。

此功能被引入Qt的4.4 。

](index.htm)

[**See also**](index.htm) [property](qscriptvalue.html#property)（ ） 。

```
QScriptValue QScriptValue.prototype (self)
```

[](qscriptvalue.html)

[如果这](qscriptvalue.html)[QScriptValue](qscriptvalue.html)是一个对象，返回内部原型（`__proto__`此对象的属性） ，否则返回一个无效的[QScriptValue](qscriptvalue.html)。

**See also** [setPrototype](qscriptvalue.html#setPrototype)（）和[isObject](qscriptvalue.html#isObject)（ ） 。

```
QScriptClass QScriptValue.scriptClass (self)
```

[

返回自定义类的脚本，此脚本对象的一个实例，或者0，如果对象是一个自定义类的没有。

此功能被引入Qt的4.4 。

](qscriptclass.html)

[**See also**](qscriptclass.html) [setScriptClass](qscriptvalue.html#setScriptClass)（ ） 。

```
QScriptValue.setData (self, QScriptValue data)
```

设置内部_data_这[QScriptValue](qscriptvalue.html)对象。您可以使用此功能来设置，将不会直接访问脚本对象的具体数据，但可以检索在C + +中使用[data](qscriptvalue.html#data)（）函数。

此功能被引入Qt的4.4 。

**See also** [data](qscriptvalue.html#data)（）和[QScriptEngine.reportAdditionalMemoryCost](qscriptengine.html#reportAdditionalMemoryCost)（ ） 。

```
QScriptValue.setProperty (self, QString name, QScriptValue value, PropertyFlags flags = QScriptValue.KeepExistingFlags)
```

设置这个值[QScriptValue](qscriptvalue.html)的属性与给定的_name_为给定的_value_。

如果这[QScriptValue](qscriptvalue.html)不是一个对象，这个函数不执行任何操作。

如果这[QScriptValue](qscriptvalue.html)不已经有名称的属性_name_，一个新的属性被创建;给定的_flags_然后指定这个属性可以通过脚本代码来访问。

If _value_是无效的，该属性被删除。

如果属性是使用setter函数实现的（即有[PropertySetter](qscriptvalue.html#PropertyFlag-enum)标志设置） ，调用的setProperty （ ）对脚本引擎的副作用，因为setter函数将被调用给定的_value_作为参数（可能导致一个未捕获的脚本异常） 。

请注意，您不能为指定自定义的getter或setter函数内置属性，如`length`Array对象或元属性的属性[QObject](qobject.html)对象。

**See also** [property](qscriptvalue.html#property)（ ） 。

```
QScriptValue.setProperty (self, QScriptString name, QScriptValue value, PropertyFlags flags = QScriptValue.KeepExistingFlags)
```

设置这个值[QScriptValue](qscriptvalue.html)的属性与给定的_name_为给定的_value_。给定_flags_指定此属性可以通过脚本代码来访问。

这种超负荷[setProperty](qscriptvalue.html#setProperty)当你需要多次设置相同的属性，因为可以执行的操作时，速度更快的名字被表示为一个字符串实习（）是非常有用的。

此功能被引入Qt的4.4 。

**See also** [QScriptEngine.toStringHandle](qscriptengine.html#toStringHandle)（ ） 。

```
QScriptValue.setProperty (self, int arrayIndex, QScriptValue value, PropertyFlags flags = QScriptValue.KeepExistingFlags)
```

这是一个重载函数。

设置该属性在给定_arrayIndex_为给定的_value_。

此功能与数组对象时提供了方便和性能。

如果这[QScriptValue](qscriptvalue.html)是不是一个Array对象，这个函数的行为就像[setProperty](qscriptvalue.html#setProperty)（ ）被调用的字符串表示形式_arrayIndex_。

```
QScriptValue.setPrototype (self, QScriptValue prototype)
```

如果这[QScriptValue](qscriptvalue.html)是一个对象，设置内部原型（`__proto__`这个对象是物业）_prototype_否则什么都不做。

内部原型不应该与公共财产名称为“原型”混淆;公众原型通常只设置在充当构造函数。

**See also** [prototype](qscriptvalue.html#prototype)（）和[isObject](qscriptvalue.html#isObject)（ ） 。

```
QScriptValue.setScriptClass (self, QScriptClass scriptClass)
```

设置此脚本对象的自定义脚本类_scriptClass_。这可以用来“推动”（例如通过在脚本中“新”运算符创建一个简单的脚本对象，或者通过[QScriptEngine.newObject](qscriptengine.html#newObject)（中） C + +）到自定义类型的对象。

If _scriptClass_为0时，该对象将被降级为普通的脚本对象。

此功能被引入Qt的4.4 。

**See also** [scriptClass](qscriptvalue.html#scriptClass)（）和[setData](qscriptvalue.html#setData)（ ） 。

```
bool QScriptValue.strictlyEquals (self, QScriptValue other)
```

返回True如果[QScriptValue](qscriptvalue.html)等于_other_使用严格的比较（无转换） ，否则返回False 。比较如下所述的行为 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)11.9.6节， “严格相等比较算法” 。

如果这种类型[QScriptValue](qscriptvalue.html)是的类型不同_other_值，此函数返回False 。如果类型相同，则结果取决于类型，如下面的表中：

| Type | Result |
| --- | --- |
| Undefined | true |
| Null | true |
| Boolean | true if both values are true, false otherwise |
| Number | false if either value is NaN (Not-a-Number); true if values are equal, false otherwise |
| String | true if both values are exactly the same sequence of characters, false otherwise |
| Object | true if both values refer to the same object, false otherwise |

**See also** [equals](qscriptvalue.html#equals)（ ） 。

```
bool QScriptValue.toBool (self)
```

返回此布尔值[QScriptValue](qscriptvalue.html)使用中所描述的转换规则 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)第9.2节， “ ToBoolean ” 。

注意，如果这个[QScriptValue](qscriptvalue.html)是一个对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的valueOf（）的函数（也可能[toString](qscriptvalue.html#toString)（ ） ） ，试图将对象转换为原始值（可能导致一个未捕获的脚本异常） 。

此功能被引入Qt的4.5 。

**See also** [isBool](qscriptvalue.html#isBool)（ ） 。

```
bool QScriptValue.toBoolean (self)
```

```
QDateTime QScriptValue.toDateTime (self)
```

[](qdatetime.html)

[返回](qdatetime.html)[QDateTime](qdatetime.html)这个值的表示，在本地时间。如果这[QScriptValue](qscriptvalue.html)是不是一个日期，或者日期的值是NaN （非数字号码） ，无效[QDateTime](qdatetime.html)返回。

**See also** [isDate](qscriptvalue.html#isDate)（ ） 。

```
int QScriptValue.toInt32 (self)
```

返回此签名的32位整数值[QScriptValue](qscriptvalue.html)使用中所描述的转换规则 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)第9.5节“ ToInt32 ” 。

注意，如果这个[QScriptValue](qscriptvalue.html)是一个对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的valueOf（）的函数（也可能[toString](qscriptvalue.html#toString)（ ） ） ，试图将对象转换为原始值（可能导致一个未捕获的脚本异常） 。

**See also** [toNumber](qscriptvalue.html#toNumber)（）和[toUInt32](qscriptvalue.html#toUInt32)（ ） 。

```
float QScriptValue.toInteger (self)
```

返回此整数值[QScriptValue](qscriptvalue.html)使用中所描述的转换规则 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)9.4节， “ ToInteger ” 。

注意，如果这个[QScriptValue](qscriptvalue.html)是一个对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的valueOf（）的函数（也可能[toString](qscriptvalue.html#toString)（ ） ） ，试图将对象转换为原始值（可能导致一个未捕获的脚本异常） 。

**See also** [toNumber](qscriptvalue.html#toNumber)（ ） 。

```
float QScriptValue.toNumber (self)
```

返回此数值[QScriptValue](qscriptvalue.html)，如在定义 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)第9.3节， “ ToNumber ” 。

注意，如果这个[QScriptValue](qscriptvalue.html)是一个对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的valueOf（）的函数（也可能[toString](qscriptvalue.html#toString)（ ） ） ，试图将对象转换为原始值（可能导致一个未捕获的脚本异常） 。

**See also** [isNumber](qscriptvalue.html#isNumber)（ ）[toInteger](qscriptvalue.html#toInteger)（ ）[toInt32](qscriptvalue.html#toInt32)（ ）[toUInt32](qscriptvalue.html#toUInt32)（）和[toUInt16](qscriptvalue.html#toUInt16)（ ） 。

```
QScriptValue QScriptValue.toObject (self)
```

[](qscriptvalue.html)

```
QMetaObject QScriptValue.toQMetaObject (self)
```

[](qmetaobject.html)

[如果这](qmetaobject.html)[QScriptValue](qscriptvalue.html)是[QMetaObject](qmetaobject.html)，返回[QMetaObject](qmetaobject.html)指针的[QScriptValue](qscriptvalue.html)代表，否则返回0 。

**See also** [isQMetaObject](qscriptvalue.html#isQMetaObject)（ ） 。

```
QObject QScriptValue.toQObject (self)
```

[](qobject.html)

[如果这](qobject.html)[QScriptValue](qscriptvalue.html)是[QObject](qobject.html)，返回[QObject](qobject.html)指针的[QScriptValue](qscriptvalue.html)代表，否则返回0 。

如果[QObject](qobject.html)这[QScriptValue](qscriptvalue.html)包裹已被删除，这个函数返回0 （即它有可能为toQObject （ ）为0 ，即使返回[isQObject](qscriptvalue.html#isQObject)（ ）返回True ） 。

**See also** [isQObject](qscriptvalue.html#isQObject)（ ） 。

```
QRegExp QScriptValue.toRegExp (self)
```

[](qregexp.html)

[返回](qregexp.html)[QRegExp](qregexp.html)这个值表示。如果这[QScriptValue](qscriptvalue.html)是不是正则表达式，空[QRegExp](qregexp.html)返回。

**See also** [isRegExp](qscriptvalue.html#isRegExp)（ ） 。

```
QString QScriptValue.toString (self)
```

返回此字符串值[QScriptValue](qscriptvalue.html)，如在定义 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)第9.8节“的ToString ” 。

注意，如果这个[QScriptValue](qscriptvalue.html)是一个对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的toString （ ）函数（以及可能的valueOf （ ） ） ，试图将对象转换为原始值（可能导致一个未捕获脚本异常） 。

**See also** [isString](qscriptvalue.html#isString)（ ） 。

```
int QScriptValue.toUInt16 (self)
```

返回此的无符号16位整型值[QScriptValue](qscriptvalue.html)使用中所描述的转换规则 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)9.7节， “ ToUint16 ” 。

注意，如果这个[QScriptValue](qscriptvalue.html)是一个对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的valueOf（）的函数（也可能[toString](qscriptvalue.html#toString)（ ） ） ，试图将对象转换为原始值（可能导致一个未捕获的脚本异常） 。

**See also** [toNumber](qscriptvalue.html#toNumber)（ ） 。

```
int QScriptValue.toUInt32 (self)
```

返回此的无符号32位整型值[QScriptValue](qscriptvalue.html)使用中所描述的转换规则 [ECMA-262](http://www.ecma-international.org/publications/standards/Ecma-262.htm)第9.6节“ ToUint32 ” 。

注意，如果这个[QScriptValue](qscriptvalue.html)是一个对象，调用这个函数对脚本引擎的副作用，因为引擎会调用对象的valueOf（）的函数（也可能[toString](qscriptvalue.html#toString)（ ） ） ，试图将对象转换为原始值（可能导致一个未捕获的脚本异常） 。

**See also** [toNumber](qscriptvalue.html#toNumber)（）和[toInt32](qscriptvalue.html#toInt32)（ ） 。

```
QVariant QScriptValue.toVariant (self)
```

返回[QVariant](qvariant.html)这个值[QScriptValue](qscriptvalue.html)，如果它可以被转换成一个[QVariant](qvariant.html)否则返回一个无效的[QVariant](qvariant.html)。该转换是根据下面的表执行：

| Input Type | Result |
| --- | --- |
| Undefined | An invalid [QVariant](qvariant.html). |
| Null | An invalid [QVariant](qvariant.html). |
| Boolean | A [QVariant](qvariant.html) containing the value of the boolean. |
| Number | A [QVariant](qvariant.html) containing the value of the number. |
| String | A [QVariant](qvariant.html) containing the value of the string. |
| [QVariant](qvariant.html) Object | The result is the [QVariant](qvariant.html) value of the object (no conversion). |
| [QObject](qobject.html) Object | A [QVariant](qvariant.html) containing a pointer to the [QObject](qobject.html). |
| Date Object | A [QVariant](qvariant.html) containing the date value ([toDateTime](qscriptvalue.html#toDateTime)()). |
| RegExp Object | A [QVariant](qvariant.html) containing the regular expression value ([toRegExp](qscriptvalue.html#toRegExp)()). |
| Array Object | The array is converted to a [QVariantList](qvariant.html#QVariantList-typedef). Each element is converted to a [QVariant](qvariant.html), recursively; cyclic references are not followed. |
| Object | The object is converted to a [QVariantMap](qvariant.html#QVariantMap-typedef). Each property is converted to a [QVariant](qvariant.html), recursively; cyclic references are not followed. |

**See also** [isVariant](qscriptvalue.html#isVariant)（ ） 。