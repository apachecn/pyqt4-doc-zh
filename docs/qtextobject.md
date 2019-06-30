# QTextObject Class Reference

## [[QtGui](index.htm) module]

该QTextObject类是为不同类型对象的基类，它可以为一组零件[QTextDocument](qtextdocument.html)在一起。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QTextBlockGroup](qtextblockgroup.html)和[QTextFrame](qtextframe.html)。

### Methods

*   `__init__ (self, QTextDocument doc)`
*   `QTextDocument document (self)`
*   `QTextFormat format (self)`
*   `int formatIndex (self)`
*   `int objectIndex (self)`
*   `setFormat (self, QTextFormat format)`

* * *

## Detailed Description

该QTextObject类是为不同类型对象的基类，它可以为一组零件[QTextDocument](qtextdocument.html)在一起。

通用分组文本对象列表（[QTextList](qtextlist.html)） ，框架（[QTextFrame](qtextframe.html)）和表（[QTextTable](qtexttable.html)） 。文本对象都有一个关联的[format](qtextobject.html#format)（）和[document](qtextobject.html#document)（ ） 。

基本上有两种类型的文本对象：那些被用来与块（块格式），以及那些被用于字符（字符格式） 。第一种是来源于[QTextBlockGroup](qtextblockgroup.html)以及从所述第二类[QTextFrame](qtextframe.html)。

你很少需要直接使用这个类。在创建自定义的文本对象，你还需要重写[QTextDocument.createObject](qtextdocument.html#createObject)（），它作为一个工厂方法来创建文本对象。

* * *

## Method Documentation

```
QTextObject.__init__ (self, QTextDocument doc)
```

创建一个新的[QTextObject](qtextobject.html)对于给定的_document_。

**Warning:**这个函数不应该被直接调用，而只能从[QTextDocument.createObject](qtextdocument.html#createObject)（ ） 。

```
QTextDocument QTextObject.document (self)
```

[

返回此对象所属的文件。

](qtextdocument.html)

[**See also**](qtextdocument.html) [format](qtextobject.html#format)（ ） 。

```
QTextFormat QTextObject.format (self)
```

[

返回文本对象的格式。

](qtextformat.html)

[**See also**](qtextformat.html) [setFormat](qtextobject.html#setFormat)（）和[document](qtextobject.html#document)（ ） 。

```
int QTextObject.formatIndex (self)
```

返回文档的内部格式列表中的对象的格式的索引。

**See also** [QTextDocument.allFormats](qtextdocument.html#allFormats)（ ） 。

```
int QTextObject.objectIndex (self)
```

返回此对象的对象索引。这可以被一起使用[QTextFormat.setObjectIndex](qtextformat.html#setObjectIndex)（ ） 。

```
QTextObject.setFormat (self, QTextFormat format)
```

设置文本对象的_format_。

**See also** [format](qtextobject.html#format)（ ） 。