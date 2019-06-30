# QXmlResultItems Class Reference

## [[QtXmlPatterns](index.htm) module]

通过评估的结果QXmlResultItems类的迭代[XQuery](index.htm)在[QXmlQuery](qxmlquery.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `QXmlItem current (self)`
*   `bool hasError (self)`
*   `QXmlItem next (self)`

* * *

## Detailed Description

通过评估的结果QXmlResultItems类的迭代[XQuery](index.htm)在[QXmlQuery](qxmlquery.html)。

QXmlResultItems提出了一个相关查询的评估作为一个序列[QXmlItems](qxmlitem.html)。该序列走过一边喊[next](qxmlresultitems.html#next)（ ） ，查询懒评估其实际产生的序列。

```
 [QXmlQuery](qxmlquery.html) query;
 query.setQuery("<e/>, 1, 'two'");
 QXmlResultItems result;

 if (query.isValid()) {
     query.evaluateTo(&result);
     [QXmlItem](qxmlitem.html) item(result.next());
     while (!item.isNull()) {
         // use item
         item = result.next();
     }
     if (result.hasError())
         /* Runtime error! */;
 }

```

让的效果[next](qxmlresultitems.html#next)（ ）由懒惰的评价产生的序列是可以发生在任何调用一个查询错误[next](qxmlresultitems.html#next)（ ） 。如果发生错误，都[next](qxmlresultitems.html#next)（）和[current](qxmlresultitems.html#current)（ ）将返回空值[QXmlItem](qxmlitem.html)和[hasError](qxmlresultitems.html#hasError)（ ）将返回True 。

QXmlResultItems可以被认为是一个“迭代”遍历查询结果的顺序一次，在向前的方向。每次调用[next](qxmlresultitems.html#next)（ ）前进迭代到下一个[QXmlItem](qxmlitem.html)的序列中，并返回它，并[current](qxmlresultitems.html#current)（ ）总是返回[QXmlItem](qxmlitem.html)那[next](qxmlresultitems.html#next)（ ）返回的最后一次被调用。

**Note:**当使用的QXmlResultItems超载[QXmlQuery.evaluateTo](qxmlquery.html#evaluateTo)（ ）执行查询，最好是创建这个类的一个新实例为每个新的结果集，而不是重新使用旧的实例。

* * *

## Method Documentation

```
QXmlResultItems.__init__ (self)
```

构造的一个实例[QXmlResultItems](qxmlresultitems.html)。

```
QXmlItem QXmlResultItems.current (self)
```

[](qxmlitem.html)

[返回当前项目。目前的产品被生产和返回的最后一个项目](qxmlitem.html)[next](qxmlresultitems.html#next)（ ） 。

返回一个空[QXmlItem](qxmlitem.html)如果不存在相关联的[QXmlQuery](qxmlquery.html)。

```
bool QXmlResultItems.hasError (self)
```

如果查询的评估过程中出现错误，则返回True 。

返回False，如果查询评估已经完成。

```
QXmlItem QXmlResultItems.next (self)
```

[](qxmlitem.html)

[返回由相关的查询懒评估产生的序列中的下一个结果。当返回](qxmlitem.html)[QXmlItem](qxmlitem.html)为null，则评价正常终止，不产生另一种结果，或者发生了错误。通话[hasError](qxmlresultitems.html#hasError)（）来判断是否为null项目被正常终止或错误导致的。

返回一个空[QXmlItem](qxmlitem.html)如果不存在相关联的[QXmlQuery](qxmlquery.html)。