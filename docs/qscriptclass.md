# QScriptClass Class Reference

## [[QtScript](index.htm) module]

该QScriptClass类提供用于定义（一类）的Qt Script对象的自定义行为的接口。[More...](#details)

### Types

*   `enum Extension { Callable, HasInstance }`
*   `enum QueryFlag { HandlesReadAccess, HandlesWriteAccess }`
*   `class **[QueryFlags](index.htm)**`

### Methods

*   `__init__ (self, QScriptEngine engine)`
*   `QScriptEngine engine (self)`
*   `QVariant extension (self, Extension extension, QVariant argument = QVariant())`
*   `QString name (self)`
*   `QScriptClassPropertyIterator newIterator (self, QScriptValue object)`
*   `QScriptValue property (self, QScriptValue object, QScriptString name, int id)`
*   `QScriptValue.PropertyFlags propertyFlags (self, QScriptValue object, QScriptString name, int id)`
*   `QScriptValue prototype (self)`
*   `(QueryFlags, int id) queryProperty (self, QScriptValue object, QScriptString name, QueryFlags flags)`
*   `setProperty (self, QScriptValue object, QScriptString name, int id, QScriptValue value)`
*   `bool supportsExtension (self, Extension extension)`

* * *

## Detailed Description

该QScriptClass类提供用于定义（一类）的Qt Script对象的自定义行为的接口。

该QScriptClass类定义用于处理交互的各个方面与类相关的Qt的脚本对象的接口。这些对象通过调用创建[QScriptEngine.newObject](qscriptengine.html#newObject)（ ） ，传递一个指针QScriptClass作为参数。

通过子类QScriptClass ，您可以精确地定义了如何访问使用你的类的对象的属性进行处理。这使得属性的完全动态处理，例如：它比功能更强大[QScriptEngine.newQObject](qscriptengine.html#newQObject)（ ） 。例如，您可以使用QScriptClass实现数组类型的对象（即处理的对象`length`属性和属性的名称是有效的数组索引，以特殊的方式） ，或者为了实现一个“活” （运行时定义的）的代理到底层对象。

如果你只需要处理访问一组已知在创建一个对象的时间属性（即“半静态” ） ，你可能会考虑使用[QScriptValue.setProperty](qscriptvalue.html#setProperty)（ ）来定义的getter / setter函数的相关性，而不是继承QScriptClass 。

重新实现[queryProperty](qscriptclass.html#queryProperty)（）来指定哪些属性在自定义的方式通过你的脚本类处理（即应**delegated**到QScriptClass ） ，以及哪些属性应该就像正常的Qt Script对象的属性进行处理。

重新实现[property](qscriptclass.html#property)（）和[setProperty](qscriptclass.html#setProperty)（ ）来执行实际的访问（读或写）到您的类处理性能。此外，您可以重新实现[propertyFlags](qscriptclass.html#propertyFlags)（）来指定自定义标记为您的物业。

重新实现[newIterator](qscriptclass.html#newIterator)（ ）提供一个迭代器为自定义类的对象。这仅仅是必要的，如果你的类的对象可以有你想要当一个对象被一起用来报告自定义属性[QScriptValueIterator](qscriptvalueiterator.html)类，或者当一个对象被用在换在枚举声明中的脚本。

当实现对象的自定义类，通常使用[QScriptValue.setData](qscriptvalue.html#setData)（ ）来存储特定于实例的数据作为对象初始化的一部分，该数据将无法从脚本直接访问，但您可以访问它，例如在您的重新实现[property](qscriptclass.html#property)（）和[setProperty](qscriptclass.html#setProperty)（ ） （通过调用[QScriptValue.data](qscriptvalue.html#data)（））来执行自定义处理。

重新实现[prototype](qscriptclass.html#prototype)（）为您的脚本类提供自定义的原型对象。

重新实现[supportsExtension](qscriptclass.html#supportsExtension)（）和[extension](qscriptclass.html#extension)（ ）如果你的自定义脚本类支持一个由扩展枚举指定的扩展名或更多。

* * *

## Type Documentation

```
QScriptClass.Extension
```

这个枚举指定可能的扩展到[QScriptClass](qscriptclass.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptClass.Callable` | `0` | 这个类的实例可以被称为功能。 |
| `QScriptClass.HasInstance` | `1` | 此类的实例实现[ [ HasInstance ] 。 |

**See also** [extension](qscriptclass.html#extension)（ ） 。

```
QScriptClass.QueryFlag
```

这个枚举变量描述了用于查询标志[QScriptClass](qscriptclass.html)关于如何获得一个属性的处理方式。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptClass.HandlesReadAccess` | `0x01` | 该[QScriptClass](qscriptclass.html)手柄读取访问这个属性。 |
| `QScriptClass.HandlesWriteAccess` | `0x02` | 该[QScriptClass](qscriptclass.html)处理写访问这个属性。 |

该QueryFlags类型是一个typedef为[QFlags](index.htm)\u003cQueryFlag\u003e 。它存储QueryFlag值的或组合。

**See also** [queryProperty](qscriptclass.html#queryProperty)（ ） 。

* * *

## Method Documentation

```
QScriptClass.__init__ (self, QScriptEngine engine)
```

构造一个[QScriptClass](qscriptclass.html)对象在给定的被使用_engine_。

发动机不走的所有权[QScriptClass](qscriptclass.html)对象。

```
QScriptEngine QScriptClass.engine (self)
```

[](qscriptengine.html)

[返回发动机，这](qscriptengine.html)[QScriptClass](qscriptclass.html)相关联。

```
QVariant QScriptClass.extension (self, Extension extension, QVariant argument = QVariant())
```

这个虚函数可以在重新实现[QScriptClass](qscriptclass.html)子类以提供扩展的支持。可选的_argument_可以作为输入提供给_extension_;结果必须在一个形式被返回[QVariant](qvariant.html)。您可以致电[supportsExtension](qscriptclass.html#supportsExtension)（ ）来检查一个扩展是支持的[QScriptClass](qscriptclass.html)。默认情况下，没有扩展名的支持，这个函数返回一个无效[QVariant](qvariant.html)。

如果实现的可赎回扩展， Qt的脚本会调用这个函数时，你的类的一个实例作为函数调用（例如，从一个脚本或使用[QScriptValue.call](qscriptvalue.html#call)（））。该_argument_将包含一个指针，指向[QScriptContext](qscriptcontext.html)表示函数调用，你应该返回一个[QVariant](qvariant.html)保存函数调用的结果。在下面的示例中的参数传递给脚本函数的总和相加并返回：

```
 if (extension == Callable) {
     [QScriptContext](qscriptcontext.html) *context = qvariant_cast<[QScriptContext](qscriptcontext.html)*>(argument);
     [QScriptEngine](qscriptengine.html) *engine = context->engine();
     double sum = 0;
     for (int i = 0; i < context->argumentCount(); ++i)
         sum += context->argument(i).toNumber();
     return sum;
 }

```

如果实现[HasInstance](qscriptclass.html#Extension-enum)扩展， Qt的脚本会调用这个函数作为评估的一部分，`instanceof`操作者，如在ECMA-262第11.8.6说明。该_argument_是一个包含两个项目一个QScriptValueList ：第一项是对象[HasInstance](qscriptclass.html#Extension-enum)被应用到（你的类的一个实例） ，第二项可以是任何值。扩展（ ）应该返回True ，如果该值代表行为的对象，否则返回False。

**See also** [supportsExtension](qscriptclass.html#supportsExtension)（ ） 。

```
QString QScriptClass.name (self)
```

返回脚本类的名称。

Qt的脚本使用此名称来生成对象的情况下，你不提供一个toString函数的默认字符串表示形式。

默认实现返回一个空字符串。

```
QScriptClassPropertyIterator QScriptClass.newIterator (self, QScriptValue object)
```

[

返回一个迭代器遍历给定的自定义属性_object_。

默认实现返回0 ，这意味着没有任何自定义属性来遍历。

](qscriptclasspropertyiterator.html)

[重新实现这个功能，如果你的脚本类的对象可以有一个或多个自定义属性（例如那些报导被处理](qscriptclasspropertyiterator.html)[queryProperty](qscriptclass.html#queryProperty)（ ） ），您要当一个对象的属性列举（例如，通过一个for in语句在脚本中）出现。

Qt的脚本需要新的迭代器对象的所有权。

**See also** [QScriptValueIterator](qscriptvalueiterator.html)。

```
QScriptValue QScriptClass.property (self, QScriptValue object, QScriptString name, int id)
```

[

用给定的返回属性的值_name_的给定_object_。

](qscriptvalue.html)

[该_id_如果你分配一个值给它的参数是唯一有用的](qscriptvalue.html)[queryProperty](qscriptclass.html#queryProperty)（ ） 。

默认实现不执行任何操作，并返回一个无效的[QScriptValue](qscriptvalue.html)。

**See also** [setProperty](qscriptclass.html#setProperty)（）和[propertyFlags](qscriptclass.html#propertyFlags)（ ） 。

```
QScriptValue.PropertyFlags QScriptClass.propertyFlags (self, QScriptValue object, QScriptString name, int id)
```

[

返回属性的标志与给定_name_的给定_object_。

](index.htm)

[该_id_如果你分配一个值给它的参数是唯一有用的](index.htm)[queryProperty](qscriptclass.html#queryProperty)（ ） 。

默认实现返回0 。

**See also** [property](qscriptclass.html#property)（ ） 。

```
QScriptValue QScriptClass.prototype (self)
```

[](qscriptvalue.html)

[返回要使用的对象作为这个类的新实例的原型（与创建](qscriptvalue.html)[QScriptEngine.newObject](qscriptengine.html#newObject)（））。

默认实现返回一个无效的[QScriptValue](qscriptvalue.html)的，这意味着标准的对象的原型将被使用。重新实现此功能提供您自己的自定义原型。

通常你初始化你的原型对象在类的构造函数，那么它在这个函数中返回。

请参阅“利用基于原型的继承”一节[QtScript](index.htm)文档以获取有关如何原型使用的详细信息。

```
(QueryFlags, int id) QScriptClass.queryProperty (self, QScriptValue object, QScriptString name, QueryFlags flags)
```

查询如何用给定的访问属性这个脚本类_name_的给定_object_应该如何处理。给定_flags_指定感兴趣的方面。这个函数应该返回的一个子集_flags_来表示，其中属性访问方面应该由脚本类被进一步处理。

例如，如果_flags_包含[HandlesReadAccess](qscriptclass.html#QueryFlag-enum)，你想你的类来处理该物业的读数（通过[property](qscriptclass.html#property)（ ）函数） ，返回的标志应包括：[HandlesReadAccess](qscriptclass.html#QueryFlag-enum)。如果返回的标志不包含[HandlesReadAccess](qscriptclass.html#QueryFlag-enum)，该物业将作为一个正常的脚本对象属性来处理。

您可以选择使用_id_参数存储将随后被传递给函数，如值[property](qscriptclass.html#property)（）和[setProperty](qscriptclass.html#setProperty)（ ） 。

此函数的默认实现返回0 。

注意：如果给定的属性是不是已经对对象的一个属性，此功能时，才调用。例如，假设你做广告，你要处理的读访问属性`foo`，但不能写入权限，如果`foo`然后被分配一个值，它会成为一个正常的脚本对象的属性，随后你将不再就到读访问查询`foo`。

**See also** [property](qscriptclass.html#property)（ ） 。

```
QScriptClass.setProperty (self, QScriptValue object, QScriptString name, int id, QScriptValue value)
```

设置该属性与给定_name_的给定_object_为给定的_value_。

该_id_如果你分配一个值给它的参数是唯一有用的[queryProperty](qscriptclass.html#queryProperty)（ ） 。

默认实现不执行任何操作。

无效的_value_表示请求移除该属性。

**See also** [property](qscriptclass.html#property)（ ） 。

```
bool QScriptClass.supportsExtension (self, Extension extension)
```

返回True如果[QScriptClass](qscriptclass.html)支持给定_extension_否则，则返回False。默认情况下，没有扩展名的支持。

重新实现这个功能，可显示哪些扩展您的自定义类的支持。

**See also** [extension](qscriptclass.html#extension)（ ） 。