# QScriptValueIterator Class Reference

## [[QtScript](index.htm) module]

该QScriptValueIterator类提供了一个Java风格的迭代器[QScriptValue](qscriptvalue.html)。[More...](#details)

### Methods

*   `__init__ (self, QScriptValue value)`
*   `QScriptValue.PropertyFlags flags (self)`
*   `bool hasNext (self)`
*   `bool hasPrevious (self)`
*   `QString name (self)`
*   `next (self)`
*   `previous (self)`
*   `remove (self)`
*   `QScriptString scriptName (self)`
*   `setValue (self, QScriptValue value)`
*   `toBack (self)`
*   `toFront (self)`
*   `QScriptValue value (self)`

* * *

## Detailed Description

该QScriptValueIterator类提供了一个Java风格的迭代器[QScriptValue](qscriptvalue.html)。

该QScriptValueIterator构造函数接受一个[QScriptValue](qscriptvalue.html)作为参数。施工完毕后，迭代器位于属性序列的开始。以下是如何遍历的所有属性[QScriptValue](qscriptvalue.html)：

```
 [QScriptValue](qscriptvalue.html) object;
 ...
 QScriptValueIterator it(object);
 while (it.hasNext()) {
     it.next();
     qDebug() << it.name() << ": " << it.value().toString();
 }

```

该[next](qscriptvalueiterator.html#next)（ ）前进的迭代器。该[name](qscriptvalueiterator.html#name)（ ）[value](qscriptvalueiterator.html#value)（）和[flags](qscriptvalueiterator.html#flags)（ ）函数返回被跳过的最后一个项目的名称，值和标志。

如果你想为你遍历删除的属性[QScriptValue](qscriptvalue.html)，使用[remove](qscriptvalueiterator.html#remove)（ ） 。如果要修改某个属性的值，请使用[setValue](qscriptvalueiterator.html#setValue)（ ） 。

需要注意的是QScriptValueIterator只能通过迭代[QScriptValue](qscriptvalue.html)自身的特性，即它不遵循原型链。你可以使用一个循环像这样遵循原型链：

```
 [QScriptValue](qscriptvalue.html) obj = ...; // the object to iterate over
 while (obj.isObject()) {
     QScriptValueIterator it(obj);
     while (it.hasNext()) {
         it.next();
         qDebug() << it.name();
     }
     obj = obj.prototype();
 }

```

需要注意的是QScriptValueIterator不会自动跳过具有的属性[QScriptValue.SkipInEnumeration](qscriptvalue.html#PropertyFlag-enum)标志设置，该标志只影响迭代的脚本代码。如果你愿意，你可以跳过此类物业的代码如下所示：

```
 while (it.hasNext()) {
     it.next();
     if (it.flags() & [QScriptValue](qscriptvalue.html).SkipInEnumeration)
         continue;
     qDebug() << "found enumerated property:" << it.name();
 }

```

* * *

## Method Documentation

```
QScriptValueIterator.__init__ (self, QScriptValue value)
```

构造一个迭代器遍历_object_。迭代器被设置为在属性的序列的前部（第一属性之前）。

```
QScriptValue.PropertyFlags QScriptValueIterator.flags (self)
```

[](index.htm)

[返回用跃过最后一个属性的标志](index.htm)[next](qscriptvalueiterator.html#next)（）或[previous](qscriptvalueiterator.html#previous)（ ） 。

**See also** [value](qscriptvalueiterator.html#value)（ ） 。

```
bool QScriptValueIterator.hasNext (self)
```

返回True如果至少有一个项目未来的迭代器（即迭代器_not_在属性序列）的后面，否则返回False 。

**See also** [next](qscriptvalueiterator.html#next)（）和[hasPrevious](qscriptvalueiterator.html#hasPrevious)（ ） 。

```
bool QScriptValueIterator.hasPrevious (self)
```

如果在后面的迭代器至少有一个项目，则返回True （即迭代器_not_在属性序列）的前面，否则返回False 。

**See also** [previous](qscriptvalueiterator.html#previous)（）和[hasNext](qscriptvalueiterator.html#hasNext)（ ） 。

```
QString QScriptValueIterator.name (self)
```

返回用跃过最后一个属性的名称[next](qscriptvalueiterator.html#next)（）或[previous](qscriptvalueiterator.html#previous)（ ） 。

**See also** [value](qscriptvalueiterator.html#value)（）和[flags](qscriptvalueiterator.html#flags)（ ） 。

```
QScriptValueIterator.next (self)
```

一个位置前进的迭代器。

在位于容器的后面的迭代器调用这个函数会导致不确定的结果。

**See also** [hasNext](qscriptvalueiterator.html#hasNext)（ ）[previous](qscriptvalueiterator.html#previous)（）和[name](qscriptvalueiterator.html#name)（ ） 。

```
QScriptValueIterator.previous (self)
```

一个位置移动迭代回来。

在位于容器的前一个迭代器调用这个函数会导致不确定的结果。

**See also** [hasPrevious](qscriptvalueiterator.html#hasPrevious)（ ）[next](qscriptvalueiterator.html#next)（）和[name](qscriptvalueiterator.html#name)（ ） 。

```
QScriptValueIterator.remove (self)
```

删除所有已使用跃过最后一个属性[next](qscriptvalueiterator.html#next)（）或[previous](qscriptvalueiterator.html#previous)（ ） 。

**See also** [setValue](qscriptvalueiterator.html#setValue)（ ） 。

```
QScriptString QScriptValueIterator.scriptName (self)
```

[](qscriptstring.html)

[返回用跃过最后一个属性的名称](qscriptstring.html)[next](qscriptvalueiterator.html#next)（）或[previous](qscriptvalueiterator.html#previous)（ ） 。

此功能被引入Qt的4.4 。

```
QScriptValueIterator.setValue (self, QScriptValue value)
```

设置_value_这是用跳过去的财产[next](qscriptvalueiterator.html#next)（）或[previous](qscriptvalueiterator.html#previous)（ ） 。

**See also** [value](qscriptvalueiterator.html#value)（）和[name](qscriptvalueiterator.html#name)（ ） 。

```
QScriptValueIterator.toBack (self)
```

移动迭代器的背面[QScriptValue](qscriptvalue.html)（后最后一个属性） 。

**See also** [toFront](qscriptvalueiterator.html#toFront)（）和[previous](qscriptvalueiterator.html#previous)（ ） 。

```
QScriptValueIterator.toFront (self)
```

移动迭代器的前面[QScriptValue](qscriptvalue.html)（第一属性之前） 。

**See also** [toBack](qscriptvalueiterator.html#toBack)（）和[next](qscriptvalueiterator.html#next)（ ） 。

```
QScriptValue QScriptValueIterator.value (self)
```

[](qscriptvalue.html)

[返回用跃过最后一个属性的值](qscriptvalue.html)[next](qscriptvalueiterator.html#next)（）或[previous](qscriptvalueiterator.html#previous)（ ） 。

**See also** [setValue](qscriptvalueiterator.html#setValue)（）和[name](qscriptvalueiterator.html#name)（ ） 。