# QScriptClassPropertyIterator Class Reference

## [[QtScript](index.htm) module]

该QScriptClassPropertyIterator类提供一个迭代器接口，用于定制的Qt Script对象。[More...](#details)

### Methods

*   `__init__ (self, QScriptValue object)`
*   `QScriptValue.PropertyFlags flags (self)`
*   `bool hasNext (self)`
*   `bool hasPrevious (self)`
*   `int id (self)`
*   `QScriptString name (self)`
*   `next (self)`
*   `QScriptValue object (self)`
*   `previous (self)`
*   `toBack (self)`
*   `toFront (self)`

* * *

## Detailed Description

该QScriptClassPropertyIterator类提供一个迭代器接口，用于定制的Qt Script对象。

这个类是只有相关的，如果你有子类[QScriptClass](qscriptclass.html)并希望提供您的自定义属性（例如枚举，当你的类的对象使用[QScriptValueIterator](qscriptvalueiterator.html)，或者与换在声明脚本） 。

该[object](qscriptclasspropertyiterator.html#object)（ ）函数返回的Qt脚本对象的迭代器遍历。

[toFront](qscriptclasspropertyiterator.html#toFront)（ ）[hasNext](qscriptclasspropertyiterator.html#hasNext)（）和[next](qscriptclasspropertyiterator.html#next)（ ）提供向前迭代。

[toBack](qscriptclasspropertyiterator.html#toBack)（ ）[hasPrevious](qscriptclasspropertyiterator.html#hasPrevious)（）和[previous](qscriptclasspropertyiterator.html#previous)（ ）提供向后迭代。

[name](qscriptclasspropertyiterator.html#name)（ ）[id](qscriptclasspropertyiterator.html#id)（）和[flags](qscriptclasspropertyiterator.html#flags)（ ）有关已跃过使用最后一个属性返回信息[next](qscriptclasspropertyiterator.html#next)（）或[previous](qscriptclasspropertyiterator.html#previous)（ ） 。

* * *

## Method Documentation

```
QScriptClassPropertyIterator.__init__ (self, QScriptValue object)
```

构造一个迭代器遍历_object_。

子类应确保迭代器被设置为物业序列的前面（第一属性之前） 。

```
QScriptValue.PropertyFlags QScriptClassPropertyIterator.flags (self)
```

[](index.htm)

[返回用跃过最后一个属性的标志](index.htm)[next](qscriptclasspropertyiterator.html#next)（）或[previous](qscriptclasspropertyiterator.html#previous)（ ） 。

默认实现调用propertyFlags （）函数[object](qscriptclasspropertyiterator.html#object)（ ）与参数[name](qscriptclasspropertyiterator.html#name)（ ） 。

```
bool QScriptClassPropertyIterator.hasNext (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果至少有一个项目未来的迭代器（即迭代器_not_在属性序列）的后面，否则返回False 。

**See also** [next](qscriptclasspropertyiterator.html#next)（）和[hasPrevious](qscriptclasspropertyiterator.html#hasPrevious)（ ） 。

```
bool QScriptClassPropertyIterator.hasPrevious (self)
```

这种方法是抽象的，应在任何子类中重新实现。

如果在后面的迭代器至少有一个项目，则返回True （即迭代器_not_在属性序列）的前面，否则返回False 。

**See also** [previous](qscriptclasspropertyiterator.html#previous)（）和[hasNext](qscriptclasspropertyiterator.html#hasNext)（ ） 。

```
int QScriptClassPropertyIterator.id (self)
```

返回用跃过最后一个属性的id[next](qscriptclasspropertyiterator.html#next)（）或[previous](qscriptclasspropertyiterator.html#previous)（ ） 。

默认实现返回0 。

**See also** [name](qscriptclasspropertyiterator.html#name)（ ） 。

```
QScriptString QScriptClassPropertyIterator.name (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qscriptstring.html)

[返回用跃过最后一个属性的名称](qscriptstring.html)[next](qscriptclasspropertyiterator.html#next)（）或[previous](qscriptclasspropertyiterator.html#previous)（ ） 。

**See also** [id](qscriptclasspropertyiterator.html#id)（ ） 。

```
QScriptClassPropertyIterator.next (self)
```

这种方法是抽象的，应在任何子类中重新实现。

一个位置前进的迭代器。

在位于容器的后面的迭代器调用这个函数会导致不确定的结果。

**See also** [hasNext](qscriptclasspropertyiterator.html#hasNext)（ ）[previous](qscriptclasspropertyiterator.html#previous)（）和[name](qscriptclasspropertyiterator.html#name)（ ） 。

```
QScriptValue QScriptClassPropertyIterator.object (self)
```

[

返回的Qt Script对象这个迭代器遍历。

```
QScriptClassPropertyIterator.previous (self)
```

这种方法是抽象的，应在任何子类中重新实现。

一个位置移动迭代回来。

在位于容器的前一个迭代器调用这个函数会导致不确定的结果。

](qscriptvalue.html)

[**See also**](qscriptvalue.html) [hasPrevious](qscriptclasspropertyiterator.html#hasPrevious)（ ）[next](qscriptclasspropertyiterator.html#next)（）和[name](qscriptclasspropertyiterator.html#name)（ ） 。

```
QScriptClassPropertyIterator.toBack (self)
```

这种方法是抽象的，应在任何子类中重新实现。

移动迭代器的背面[QScriptValue](qscriptvalue.html)（后最后一个属性） 。

**See also** [toFront](qscriptclasspropertyiterator.html#toFront)（）和[previous](qscriptclasspropertyiterator.html#previous)（ ） 。

```
QScriptClassPropertyIterator.toFront (self)
```

这种方法是抽象的，应在任何子类中重新实现。

移动迭代器的前面[QScriptValue](qscriptvalue.html)（第一属性之前） 。

**See also** [toBack](qscriptclasspropertyiterator.html#toBack)（）和[next](qscriptclasspropertyiterator.html#next)（ ） 。