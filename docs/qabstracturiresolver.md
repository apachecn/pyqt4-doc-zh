# QAbstractUriResolver Class Reference

## [[QtXmlPatterns](index.htm) module]

该QAbstractUriResolver类是解决统一资源标识符一个回调接口。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QUrl resolve (self, QUrl relative, QUrl baseURI)`

* * *

## Detailed Description

该QAbstractUriResolver类是解决统一资源标识符一个回调接口。

统一资源标识符（URI）是一个字符串，用于唯一标识一个资源。 URI是通用的全局标识符。这是非常有用的变换，它位于身体的东西（一个URL ）的URI标识逻辑的东西变成一个URI ，或一个URI简单地映射到不同的URI 。[QAbstractUriResolver.resolve](qabstracturiresolver.html#resolve)（ ）提供了这个功能。

例如，一个可以写一个QAbstractUriResolver子类重写库ISBN号URI作为书名的URL ，例如，_urn:isbn:0-345-33973-8_将被重写为_file:///books/returnOfTheKing.doc_。或QAbstractUriResolver子类可以为一个Web浏览器，让浏览器通过映射进来让他们空的URI请求保护用户的私人文件写入。

* * *

## Method Documentation

```
QAbstractUriResolver.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QAbstractUriResolver](qabstracturiresolver.html)用指定的_parent_。

```
QUrl QAbstractUriResolver.resolve (self, QUrl relative, QUrl baseURI)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回_relative_使用URI的解析_baseURI_。

调用者保证两台_relative_和_baseURI_是有效的，并且_baseURI_是绝对的。_relative_可以是相对的，绝对的，还是空的。

](qurl.html)

[返回](qurl.html)[QUrl](qurl.html)可以构造一个默认的[QUrl](qurl.html)。如果它不构成一个缺省[QUrl](qurl.html)，这将是绝对有效的。如果构造一个默认的[QUrl](qurl.html)返回，这意味着_relative_URI不被接受有待解决。

如果重新实现的决心（ ）函数决定它无关，有关解决_relative_URI ，它应该简单地返回_relative_URI解决了对_baseURI_，即：

```
 return baseURI.resolved(relative);

```

**See also** [QUrl.isRelative](qurl.html#isRelative)（）和[QUrl.isValid](qurl.html#isValid)（ ） 。