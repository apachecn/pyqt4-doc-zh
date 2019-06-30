# QScriptString Class Reference

## [[QtScript](index.htm) module]

该QScriptString类充当手柄来“实习”的字符串中[QScriptEngine](qscriptengine.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QScriptString other)`
*   `bool isValid (self)`
*   `(int, bool ok) toArrayIndex (self)`
*   `QString toString (self)`

### Special Methods

*   `bool __eq__ (self, QScriptString other)`
*   `int __hash__ (self)`
*   `bool __ne__ (self, QScriptString other)`

* * *

## Detailed Description

该QScriptString类充当手柄来“实习”的字符串中[QScriptEngine](qscriptengine.html)。

QScriptString可以用来实现更快的（重复）属性获取/设置和属性名称的比较，脚本对象。

为了得到一个字符串的QScriptString表示，将字符串传递给[QScriptEngine.toStringHandle](qscriptengine.html#toStringHandle)（ ） 。典型的使用模式是注册一个或多个预先定义的字符串设置你的脚本环境中时，随后使用相关QScriptString作为参数，例如[QScriptValue.property](qscriptvalue.html#property)（ ） 。

调用[toString](qscriptstring.html#toString)（ ）函数来获得一个QScriptString表示字符串。

调用[toArrayIndex](qscriptstring.html#toArrayIndex)（ ）函数将QScriptString转换为数组索引。使用时，这是有用的[QScriptClass](qscriptclass.html)实现类似数组的对象。

* * *

## Method Documentation

```
QScriptString.__init__ (self)
```

构造一个无效的[QScriptString](qscriptstring.html)。

```
QScriptString.__init__ (self, QScriptString other)
```

构造一个新的[QScriptString](qscriptstring.html)即副本_other_。

```
bool QScriptString.isValid (self)
```

返回True如果[QScriptString](qscriptstring.html)是有效的，否则返回False 。

```
(int, bool ok) QScriptString.toArrayIndex (self)
```

尝试将它转换[QScriptString](qscriptstring.html)到[QtScript](index.htm)数组的索引，并返回结果。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

此功能被引入Qt的4.6 。

```
QString QScriptString.toString (self)
```

返回字符串，此[QScriptString](qscriptstring.html)代表，或一个空字符串，如果这[QScriptString](qscriptstring.html)是无效的。

**See also** [isValid](qscriptstring.html#isValid)（ ） 。

```
bool QScriptString.__eq__ (self, QScriptString other)
```

```
int QScriptString.__hash__ (self)
```

```
bool QScriptString.__ne__ (self, QScriptString other)
```