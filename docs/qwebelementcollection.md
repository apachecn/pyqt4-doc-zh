# QWebElementCollection Class Reference

## [[QtWebKit](index.htm) module]

该QWebElementCollection类表示网络元素的集合。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QWebElement contextElement, QString query)`
*   `__init__ (self, QWebElementCollection)`
*   `append (self, QWebElementCollection collection)`
*   `QWebElement at (self, int i)`
*   `int count (self)`
*   `QWebElement first (self)`
*   `QWebElement last (self)`
*   `list-of-QWebElement toList (self)`

### Special Methods

*   `QWebElementCollection __add__ (self, QWebElementCollection other)`
*   `QWebElement __getitem__ (self, int i)`
*   `QWebElementCollection __iadd__ (self, QWebElementCollection other)`
*   `__len__ (self)`

* * *

## Detailed Description

该QWebElementCollection类表示网络元素的集合。

在一个文档元素可以使用被选择[QWebElement.findAll](qwebelement.html#findAll)（） ，或使用[QWebElement](qwebelement.html)构造函数。该集合是通过选择符合指定CSS选择器表达式，文档中的所有元素组成的。

选择的元素的数目是通过提供[count](qwebelementcollection.html#count)（）属性。单个元素可以通过使用索引来检索[at](qwebelementcollection.html#at)（ ） 。

它也可以遍历使用Qt的foreach宏集合中的所有元素：

```
 QWebElementCollection collection = document.findAll("p");
 foreach ([QWebElement](qwebelement.html) paraElement, collection) {
     ...
 }

```

* * *

## Method Documentation

```
QWebElementCollection.__init__ (self)
```

构造一个空的集合。

```
QWebElementCollection.__init__ (self, QWebElement contextElement, QString query)
```

从构造的子元素的列表元素的集合_contextElement_匹配指定CSS选择器_query_。

```
QWebElementCollection.__init__ (self, QWebElementCollection)
```

构造的副本_other_。

```
QWebElementCollection.append (self, QWebElementCollection collection)
```

通过附加的所有项目扩展集合_other_。

结果集合可能包含重复的元素。

**See also** [operator+=](qwebelementcollection.html#operator-2b-eq)（ ） 。

```
QWebElement QWebElementCollection.at (self, int i)
```

[

返回元素的索引位置_i_在该集合中。

```
int QWebElementCollection.count (self)
```

返回集合中的元素数目。

](qwebelement.html)

```
QWebElement QWebElementCollection.first (self)
```

[

返回集合中的第一个元素。

](qwebelement.html)

[**See also**](qwebelement.html) [last](qwebelementcollection.html#last)（ ）[operator[]](qwebelementcollection.html#operator-5b-5d)（ ）[at](qwebelementcollection.html#at)（）和[count](qwebelementcollection.html#count)（ ） 。

```
QWebElement QWebElementCollection.last (self)
```

[

返回集合中的最后一个元素。

](qwebelement.html)

[**See also**](qwebelement.html) [first](qwebelementcollection.html#first)（ ）[operator[]](qwebelementcollection.html#operator-5b-5d)（ ）[at](qwebelementcollection.html#at)（）和[count](qwebelementcollection.html#count)（ ） 。

```
list-of-QWebElement QWebElementCollection.toList (self)
```

返回[QList](index.htm)对象包含在这个集合中的元素。

```
QWebElementCollection QWebElementCollection.__add__ (self, QWebElementCollection other)
```

[](qwebelementcollection.html)

```
QWebElement QWebElementCollection.__getitem__ (self, int i)
```

[](qwebelement.html)

```
QWebElementCollection QWebElementCollection.__iadd__ (self, QWebElementCollection other)
```

[

```
 QWebElementCollection.__len__ (self)
```

](qwebelementcollection.html)