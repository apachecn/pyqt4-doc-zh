# QWebElement Class Reference

## [[QtWebKit](index.htm) module]

该QWebElement类提供了一个便捷的DOM元素[QWebFrame](qwebframe.html)。[More...](#details)

### Types

*   `enum StyleResolveStrategy { InlineStyle, CascadedStyle, ComputedStyle }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QWebElement)`
*   `addClass (self, QString name)`
*   `appendInside (self, QString markup)`
*   `appendInside (self, QWebElement element)`
*   `appendOutside (self, QString markup)`
*   `appendOutside (self, QWebElement element)`
*   `QString attribute (self, QString name, QString defaultValue = QString())`
*   `QStringList attributeNames (self, QString namespaceUri = QString())`
*   `QString attributeNS (self, QString namespaceUri, QString name, QString defaultValue = QString())`
*   `QStringList classes (self)`
*   `QWebElement clone (self)`
*   `QWebElement document (self)`
*   `encloseContentsWith (self, QWebElement element)`
*   `encloseContentsWith (self, QString markup)`
*   `encloseWith (self, QString markup)`
*   `encloseWith (self, QWebElement element)`
*   `QVariant evaluateJavaScript (self, QString scriptSource)`
*   `QWebElementCollection findAll (self, QString selectorQuery)`
*   `QWebElement findFirst (self, QString selectorQuery)`
*   `QWebElement firstChild (self)`
*   `QRect geometry (self)`
*   `bool hasAttribute (self, QString name)`
*   `bool hasAttributeNS (self, QString namespaceUri, QString name)`
*   `bool hasAttributes (self)`
*   `bool hasClass (self, QString name)`
*   `bool hasFocus (self)`
*   `bool isNull (self)`
*   `QWebElement lastChild (self)`
*   `QString localName (self)`
*   `QString namespaceUri (self)`
*   `QWebElement nextSibling (self)`
*   `QWebElement parent (self)`
*   `QString prefix (self)`
*   `prependInside (self, QString markup)`
*   `prependInside (self, QWebElement element)`
*   `prependOutside (self, QString markup)`
*   `prependOutside (self, QWebElement element)`
*   `QWebElement previousSibling (self)`
*   `removeAllChildren (self)`
*   `removeAttribute (self, QString name)`
*   `removeAttributeNS (self, QString namespaceUri, QString name)`
*   `removeClass (self, QString name)`
*   `removeFromDocument (self)`
*   `render (self, QPainter painter)`
*   `render (self, QPainter painter, QRect clip)`
*   `replace (self, QString markup)`
*   `replace (self, QWebElement element)`
*   `setAttribute (self, QString name, QString value)`
*   `setAttributeNS (self, QString namespaceUri, QString name, QString value)`
*   `setFocus (self)`
*   `setInnerXml (self, QString markup)`
*   `setOuterXml (self, QString markup)`
*   `setPlainText (self, QString text)`
*   `setStyleProperty (self, QString name, QString value)`
*   `QString styleProperty (self, QString name, StyleResolveStrategy strategy)`
*   `QString tagName (self)`
*   `QWebElement takeFromDocument (self)`
*   `toggleClass (self, QString name)`
*   `QString toInnerXml (self)`
*   `QString toOuterXml (self)`
*   `QString toPlainText (self)`
*   `QWebFrame webFrame (self)`

### Special Methods

*   `bool __eq__ (self, QWebElement o)`
*   `bool __ne__ (self, QWebElement o)`

* * *

## Detailed Description

该QWebElement类提供了一个便捷的DOM元素[QWebFrame](qwebframe.html)。

一个QWebElement对象可以方便地访问文档模型，通过DOM元素的树形结构来表示。树的根被称为文档元素，并且可以使用访问[QWebFrame.documentElement](qwebframe.html#documentElement)（ ） 。

特定元素可以使用访问[findAll](qwebelement.html#findAll)（）和[findFirst](qwebelement.html#findFirst)（ ） 。这些元素是使用CSS选择确定。下面的代码片断演示了使用[findAll](qwebelement.html#findAll)（ ） 。

```
     QWebElement document = frame->documentElement();
     /* Assume the document has the following structure:

        <p class=intro>
          <span>Intro</span>
          <span>Snippets</span>
        </p>
        <p>
          <span>Content</span>
          <span>Here</span>
        </p>
     */

     [QWebElementCollection](qwebelementcollection.html) allSpans = document.findAll("span");
     [QWebElementCollection](qwebelementcollection.html) introSpans = document.findAll("p.intro span");

```

第一个列表包含所有`span`在文档中的元素。第二个列表包含`span`这是子元素`p`，与分类`intro`。

Using [findFirst](qwebelement.html#findFirst)（ ）比调用更有效率[findAll](qwebelement.html#findAll)（） ，并仅提取列表中的第一个元素返回。

另外，您可以使用手动遍历文档[firstChild](qwebelement.html#firstChild)（）和[nextSibling](qwebelement.html#nextSibling)（）：

```
     frame->setHtml("<html><body><p>First Paragraph</p><p>Second Paragraph</p></body></html>");
     QWebElement doc = frame->documentElement();
     QWebElement body = doc.firstChild();
     QWebElement firstParagraph = body.firstChild();
     QWebElement secondParagraph = firstParagraph.nextSibling();

```

单个元素可以使用的方法，例如进行检查或更换[attribute](qwebelement.html#attributex)（）或[setAttribute](qwebelement.html#setAttribute)（ ） 。举个例子来说，捕捉用户的输入中供以后使用（自动完成）的文本字段，浏览器可以做这样的事情：

```
     QWebElement firstTextInput = document.findFirst("input[type=text]");
     [QString](qstring.html) storedText = firstTextInput.attribute("value");

```

当在同一个页面稍后再访，浏览器可以在文本字段自动修改输入元素的值属性填写：

```
     QWebElement firstTextInput = document.findFirst("input[type=text]");
     textInput.setAttribute("value", storedText);

```

另一个用例是模拟一个click事件的元素上。下面的代码片断演示了如何调用一个提交按钮的JavaScript DOM方法点击（ ） ：

```
     QWebElement document = frame->documentElement();
     /* Assume that the document has the following structure:

         <form name="myform" action="submit_form.asp" method="get">
             <input type="text" name="myfield">
             <input type="submit" value="Submit">
         </form>

      */

     QWebElement button = document.findFirst("input[type=submit]");
     button.evaluateJavaScript("this.click()");

```

QWebElement的基本内容是公开共享的。创建QWebElement的副本不会创建内容的副本。相反，这两个实例指向同一个元素。

子元素中的内容可以被转换为纯文本[toPlainText](qwebelement.html#toPlainText)（）;使用到XHTML[toInnerXml](qwebelement.html#toInnerXml)（ ） 。要包含元素的标记输出，使用[toOuterXml](qwebelement.html#toOuterXml)（ ） 。

它是可能使用替换子元素的含量[setPlainText](qwebelement.html#setPlainText)（）和[setInnerXml](qwebelement.html#setInnerXml)（ ） 。要更换元件本身及其内容，请使用[setOuterXml](qwebelement.html#setOuterXml)（ ） 。

### Examples

该[DOM Traversal Example](index.htm)显示遍历文件在运行的例子的方法之一。

该[Simple Selector Example](index.htm)可用于尝试这个类的搜索功能，并提供示例代码，你可以开始工作。

* * *

## Type Documentation

```
QWebElement.StyleResolveStrategy
```

这个枚举说明如何[QWebElement](qwebelement.html)的styleProperty解决给定的属性名。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebElement.InlineStyle` | `0` | 返回属性值，因为它是在元素中定义，不尊重样式继承和其它CSS规则。 |
| `QWebElement.CascadedStyle` | `1` | 该属性的值是使用在文档的样式表中定义的继承和重要性规则确定。 |
| `QWebElement.ComputedStyle` | `2` | 该属性的值是从环境中解决了样式属性的绝对值。 |

* * *

## Method Documentation

```
QWebElement.__init__ (self)
```

构造一个空的网络元素。

```
QWebElement.__init__ (self, QWebElement)
```

构造的副本_other_。

```
QWebElement.addClass (self, QString name)
```

用给定的添加指定的类_name_到的元素。

```
QWebElement.appendInside (self, QString markup)
```

附加解析的结果_markup_作为元素的最后一个子。

空元素上调用这个函数什么都不做。

**See also** [prependInside](qwebelement.html#prependInside)（ ）[prependOutside](qwebelement.html#prependOutside)（）和[appendOutside](qwebelement.html#appendOutside)（ ） 。

```
QWebElement.appendInside (self, QWebElement element)
```

添加给定的_element_作为元素的最后一个子。

If _element_是另一个元素的子元素，它是重新父此元素。如果_element_在此元素的子元素，那么其在儿童中的列表中的位置被改变。

空元素上调用这个函数什么都不做。

**See also** [prependInside](qwebelement.html#prependInside)（ ）[prependOutside](qwebelement.html#prependOutside)（）和[appendOutside](qwebelement.html#appendOutside)（ ） 。

```
QWebElement.appendOutside (self, QString markup)
```

插入解析的结果_markup_这个元素之后。

空元素上调用这个函数什么都不做。

**See also** [appendInside](qwebelement.html#appendInside)（ ）[prependInside](qwebelement.html#prependInside)（）和[prependOutside](qwebelement.html#prependOutside)（ ） 。

```
QWebElement.appendOutside (self, QWebElement element)
```

插入给定_element_这个元素之后。

If _element_是另一个元素的子元素，它是重新父到这个元素的父元素。

空元素上调用这个函数什么都不做。

**See also** [appendInside](qwebelement.html#appendInside)（ ）[prependInside](qwebelement.html#prependInside)（）和[prependOutside](qwebelement.html#prependOutside)（ ） 。

```
QString QWebElement.attribute (self, QString name, QString defaultValue = QString())
```

```
QStringList QWebElement.attributeNames (self, QString namespaceUri = QString())
```

返回的属性列表对于给定的命名空间_namespaceUri_。

**See also** [attribute](qwebelement.html#attributex)（）和[setAttribute](qwebelement.html#setAttribute)（ ） 。

```
QString QWebElement.attributeNS (self, QString namespaceUri, QString name, QString defaultValue = QString())
```

返回属性与给定_name_在_namespaceUri_。如果属性不存在，_defaultValue_返回。

**See also** [setAttributeNS](qwebelement.html#setAttributeNS)（ ）[setAttribute](qwebelement.html#setAttribute)（）和[attribute](qwebelement.html#attributex)（ ） 。

```
QStringList QWebElement.classes (self)
```

返回的类此元素的列表。

```
QWebElement QWebElement.clone (self)
```

[

返回此元素的一个克隆。

该克隆可在任何点在文件中插入。

](qwebelement.html)

[**See also**](qwebelement.html) [appendInside](qwebelement.html#appendInside)（ ）[prependInside](qwebelement.html#prependInside)（ ）[prependOutside](qwebelement.html#prependOutside)（）和[appendOutside](qwebelement.html#appendOutside)（ ） 。

```
QWebElement QWebElement.document (self)
```

[

返回此元素属于文档。

```
QWebElement.encloseContentsWith (self, QWebElement element)
```

封闭此元素的内容与_element_。这个元素变成内最深的后代的孩子_element_。

＃＃＃插图

](qwebelement.html)

[**See also**](qwebelement.html) [encloseWith](qwebelement.html#encloseWith)（ ） 。

```
QWebElement.encloseContentsWith (self, QString markup)
```

封闭此元素的内容与解析的结果_markup_。这个元素变成内最深的后代的孩子_markup_。

**See also** [encloseWith](qwebelement.html#encloseWith)（ ） 。

```
QWebElement.encloseWith (self, QString markup)
```

包围该元素与解析的结果_markup_。这个元素变成内最深的后代的孩子_markup_。

**See also** [replace](qwebelement.html#replace)（ ） 。

```
QWebElement.encloseWith (self, QWebElement element)
```

包围该元素与_element_。这个元素变成内最深的后代的孩子_element_。

**See also** [replace](qwebelement.html#replace)（ ） 。

```
QVariant QWebElement.evaluateJavaScript (self, QString scriptSource)
```

Executes _scriptSource_以这个项目为`this`对象。

```
QWebElementCollection QWebElement.findAll (self, QString selectorQuery)
```

[

返回子元素匹配给定的CSS选择一个新的列表_selectorQuery_。如果没有匹配的元素，则返回一个空列表。

](qwebelementcollection.html)

[](qwebelementcollection.html)[Standard CSS2 selector](http://www.w3.org/TR/REC-CSS2/selector.html#q1)语法用于查询。

**Note:**这种搜索是递归执行。

**See also** [findFirst](qwebelement.html#findFirst)（ ） 。

```
QWebElement QWebElement.findFirst (self, QString selectorQuery)
```

[

返回匹配给定的CSS选择器的第一个子元素_selectorQuery_。

](qwebelement.html)

[](qwebelement.html)[Standard CSS2 selector](http://www.w3.org/TR/REC-CSS2/selector.html#q1)语法用于查询。

**Note:**这种搜索是递归执行。

**See also** [findAll](qwebelement.html#findAll)（ ） 。

```
QWebElement QWebElement.firstChild (self)
```

[

返回元素的第一个孩子。

](qwebelement.html)

[**See also**](qwebelement.html) [lastChild](qwebelement.html#lastChild)（ ）[previousSibling](qwebelement.html#previousSibling)（）和[nextSibling](qwebelement.html#nextSibling)（ ） 。

```
QRect QWebElement.geometry (self)
```

[

返回此元素的几何形状，相对于其包含框架。

](qrect.html)

[**See also**](qrect.html) [tagName](qwebelement.html#tagName)（ ） 。

```
bool QWebElement.hasAttribute (self, QString name)
```

如果此元素具有与给定的属性，则返回True_name_否则返回False 。

**See also** [attribute](qwebelement.html#attributex)（）和[setAttribute](qwebelement.html#setAttribute)（ ） 。

```
bool QWebElement.hasAttributeNS (self, QString namespaceUri, QString name)
```

如果此元素具有与给定的属性，则返回True_name_在_namespaceUri_否则返回False 。

**See also** [attributeNS](qwebelement.html#attributeNS)（）和[setAttributeNS](qwebelement.html#setAttributeNS)（ ） 。

```
bool QWebElement.hasAttributes (self)
```

返回True如果该元素具有定义的任何属性，否则返回False ;

**See also** [attribute](qwebelement.html#attributex)（）和[setAttribute](qwebelement.html#setAttribute)（ ） 。

```
bool QWebElement.hasClass (self, QString name)
```

如果此元素有一个类用给定的，则返回True_name_否则返回False 。

```
bool QWebElement.hasFocus (self)
```

返回True如果该元素具有键盘输入焦点，否则返回False

**See also** [setFocus](qwebelement.html#setFocus)（ ） 。

```
bool QWebElement.isNull (self)
```

返回True如果该元素是一个空元素，否则返回False 。

```
QWebElement QWebElement.lastChild (self)
```

[

返回元素的最后一个子。

](qwebelement.html)

[**See also**](qwebelement.html) [firstChild](qwebelement.html#firstChild)（ ）[previousSibling](qwebelement.html#previousSibling)（）和[nextSibling](qwebelement.html#nextSibling)（ ） 。

```
QString QWebElement.localName (self)
```

返回元素的本地名称。如果元素没有使用名称空间，则返回一个空字符串。

```
QString QWebElement.namespaceUri (self)
```

返回此元素的命名空间URI 。如果元素没有命名空间URI ，则返回一个空字符串。

```
QWebElement QWebElement.nextSibling (self)
```

[

返回元素的下一个兄弟。

](qwebelement.html)

[**See also**](qwebelement.html) [firstChild](qwebelement.html#firstChild)（ ）[previousSibling](qwebelement.html#previousSibling)（）和[lastChild](qwebelement.html#lastChild)（ ） 。

```
QWebElement QWebElement.parent (self)
```

[

返回此elemen的父元素。如果该元素是根文档元素，则返回一个空元素。

```
QString QWebElement.prefix (self)
```

返回元素的命名空间前缀。如果元素没有命名空间前缀，则返回空字符串。

```
QWebElement.prependInside (self, QString markup)
```

预先规划解析结果_markup_作为元素的第一个孩子。

空元素上调用这个函数什么都不做。

](qwebelement.html)

[**See also**](qwebelement.html) [appendInside](qwebelement.html#appendInside)（ ）[prependOutside](qwebelement.html#prependOutside)（）和[appendOutside](qwebelement.html#appendOutside)（ ） 。

```
QWebElement.prependInside (self, QWebElement element)
```

预先考虑_element_作为元素的第一个孩子。

If _element_是另一个元素的子元素，它是重新父此元素。如果_element_在此元素的子元素，那么其在儿童中的列表中的位置被改变。

空元素上调用这个函数什么都不做。

**See also** [appendInside](qwebelement.html#appendInside)（ ）[prependOutside](qwebelement.html#prependOutside)（）和[appendOutside](qwebelement.html#appendOutside)（ ） 。

```
QWebElement.prependOutside (self, QString markup)
```

插入解析的结果_markup_在此之前的元素。

空元素上调用这个函数什么都不做。

**See also** [appendInside](qwebelement.html#appendInside)（ ）[prependInside](qwebelement.html#prependInside)（）和[appendOutside](qwebelement.html#appendOutside)（ ） 。

```
QWebElement.prependOutside (self, QWebElement element)
```

插入给定_element_在此之前的元素。

If _element_是另一个元素的子元素，它是重新父到这个元素的父元素。

空元素上调用这个函数什么都不做。

**See also** [appendInside](qwebelement.html#appendInside)（ ）[prependInside](qwebelement.html#prependInside)（）和[appendOutside](qwebelement.html#appendOutside)（ ） 。

```
QWebElement QWebElement.previousSibling (self)
```

[

返回元素的前一个同级。

](qwebelement.html)

[**See also**](qwebelement.html) [firstChild](qwebelement.html#firstChild)（ ）[nextSibling](qwebelement.html#nextSibling)（）和[lastChild](qwebelement.html#lastChild)（ ） 。

```
QWebElement.removeAllChildren (self)
```

从此元素移除所有子项。

**See also** [removeFromDocument](qwebelement.html#removeFromDocument)（）和[takeFromDocument](qwebelement.html#takeFromDocument)（ ） 。

```
QWebElement.removeAttribute (self, QString name)
```

删除该属性与给定_name_从这个项目。

**See also** [attribute](qwebelement.html#attributex)（ ）[setAttribute](qwebelement.html#setAttribute)（）和[hasAttribute](qwebelement.html#hasAttribute)（ ） 。

```
QWebElement.removeAttributeNS (self, QString namespaceUri, QString name)
```

删除该属性与给定_name_在_namespaceUri_，从这个项目。

**See also** [attributeNS](qwebelement.html#attributeNS)（ ）[setAttributeNS](qwebelement.html#setAttributeNS)（）和[hasAttributeNS](qwebelement.html#hasAttributeNS)（ ） 。

```
QWebElement.removeClass (self, QString name)
```

用给定的移除指定的类_name_从元素。

```
QWebElement.removeFromDocument (self)
```

删除这个元素从文档中，并使其空元素。

**See also** [removeAllChildren](qwebelement.html#removeAllChildren)（）和[takeFromDocument](qwebelement.html#takeFromDocument)（ ） 。

```
QWebElement.render (self, QPainter painter)
```

渲染元素融入_painter_。

```
QWebElement.render (self, QPainter painter, QRect clip)
```

渲染元素融入_painter_削波_clip_。

```
QWebElement.replace (self, QString markup)
```

替换该元素与解析的结果_markup_。

这种方法不会取代\u003cHTML\u003e ， \u003cHEAD\u003e或\u003cBODY\u003e元素。

**See also** [encloseWith](qwebelement.html#encloseWith)（ ） 。

```
QWebElement.replace (self, QWebElement element)
```

替换该元素与_element_。

这种方法不会取代\u003cHTML\u003e ， \u003cHEAD\u003e或\u003cBODY\u003e元素。

**See also** [encloseWith](qwebelement.html#encloseWith)（ ） 。

```
QWebElement.setAttribute (self, QString name, QString value)
```

添加一个属性与给定_name_和_value_。如果具有相同名称的属性存在，它的值被替换_value_。

**See also** [attribute](qwebelement.html#attributex)（ ）[attributeNS](qwebelement.html#attributeNS)（）和[setAttributeNS](qwebelement.html#setAttributeNS)（ ） 。

```
QWebElement.setAttributeNS (self, QString namespaceUri, QString name, QString value)
```

添加一个属性与给定_name_在_namespaceUri_同_value_。如果具有相同名称的属性存在，它的值被替换_value_。

**See also** [attributeNS](qwebelement.html#attributeNS)（ ）[attribute](qwebelement.html#attributex)（）和[setAttribute](qwebelement.html#setAttribute)（ ） 。

```
QWebElement.setFocus (self)
```

使键盘输入焦点设定到此元素

**See also** [hasFocus](qwebelement.html#hasFocus)（ ） 。

```
QWebElement.setInnerXml (self, QString markup)
```

替换这个元素的内容与_markup_。字符串可能包含HTML或XML标籤，其被解析并插入之前格式化成文档。

**Note:**这是目前的（ X）HTML元素只有实施。

**See also** [toInnerXml](qwebelement.html#toInnerXml)（ ）[toOuterXml](qwebelement.html#toOuterXml)（）和[setOuterXml](qwebelement.html#setOuterXml)（ ） 。

```
QWebElement.setOuterXml (self, QString markup)
```

替换此元素的内容，以及它自己的标记与_markup_。字符串可能包含HTML或XML标籤，其被解析并插入之前格式化成文档。

**Note:**这是目前仅实施了（ X）HTML元素。

**See also** [toOuterXml](qwebelement.html#toOuterXml)（ ）[toInnerXml](qwebelement.html#toInnerXml)（）和[setInnerXml](qwebelement.html#setInnerXml)（ ） 。

```
QWebElement.setPlainText (self, QString text)
```

替换该元素与现有的内容_text_。

这等效于设置在HTML innerText属性。

**See also** [toPlainText](qwebelement.html#toPlainText)（ ） 。

```
QWebElement.setStyleProperty (self, QString name, QString value)
```

设置内嵌样式的值与给定_name_至_value_。

设置一个值，并不一定意味着它将成为应用价值，由于该样式属性的值可能已设置较早具有较高优先级的外部或内嵌式声明的事实。

为了确保该值将被应用，你可能要追加！“重要”的价值。

**See also** [styleProperty](qwebelement.html#styleProperty)（ ） 。

```
QString QWebElement.styleProperty (self, QString name, StyleResolveStrategy strategy)
```

返回样式的值与给定_name_使用指定的_strategy_。如果与风格_name_不存在，则返回一个空字符串。

在CSS中，该级联部分取决于它的CSS规则的优先级，因而应用。一般情况下，最后定义的规则优先。因此，内联样式规则优先于嵌入块样式规则，作为回报优先于外部的样式规则。

如果“ ！重要的”声明被设置于其中的一个，申报接收优先级最高，除非其他声明也使用了“ ！重要”的宣言。然后，最后“ ！重要”的声明发生predecence 。

**See also** [setStyleProperty](qwebelement.html#setStyleProperty)（ ） 。

```
QString QWebElement.tagName (self)
```

返回此元素的标籤名称。

**See also** [geometry](qwebelement.html#geometry)（ ） 。

```
QWebElement QWebElement.takeFromDocument (self)
```

[

删除这个元素从文档并返回一个引用。

该元件仍然有效去除后，可插入到文档的其他部分。

](qwebelement.html)

[**See also**](qwebelement.html) [removeAllChildren](qwebelement.html#removeAllChildren)（）和[removeFromDocument](qwebelement.html#removeFromDocument)（ ） 。

```
QWebElement.toggleClass (self, QString name)
```

用给定的添加指定的类_name_如果它不存在。如果该类已存在，它将被删除。

```
QString QWebElement.toInnerXml (self)
```

返回元素的开始和结束标籤之间的XML内容。

**Note:**这是目前的（ X）HTML元素只有实施。

**Note:**返回的标记的格式将服从包含该元素的文档的命名空间。这意味着返回值会服从的XML格式规则，如自闭标籤，只有当文件是文本/ xhtml + xml “ 。

**See also** [setInnerXml](qwebelement.html#setInnerXml)（ ）[setOuterXml](qwebelement.html#setOuterXml)（）和[toOuterXml](qwebelement.html#toOuterXml)（ ） 。

```
QString QWebElement.toOuterXml (self)
```

返回该元素转换为XML ，包括开始和结束标记，以及它的属性。

**Note:**这是目前的（ X）HTML元素只有实施。

**Note:**返回的标记的格式将服从包含该元素的文档的命名空间。这意味着返回值会服从的XML格式规则，如自闭标籤，只有当文件是文本/ xhtml + xml “ 。

**See also** [setOuterXml](qwebelement.html#setOuterXml)（ ）[setInnerXml](qwebelement.html#setInnerXml)（）和[toInnerXml](qwebelement.html#toInnerXml)（ ） 。

```
QString QWebElement.toPlainText (self)
```

返回开始和这个元素的结束标籤之间的文本。

这相当于读取HTML innerText属性。

**See also** [setPlainText](qwebelement.html#setPlainText)（ ） 。

```
QWebFrame QWebElement.webFrame (self)
```

[

返回web框架而这个元素是的一部分。如果元素是一个空元素，则返回null 。

```
bool QWebElement.__eq__ (self, QWebElement o)
```

```
bool QWebElement.__ne__ (self, QWebElement o)
```

](qwebframe.html)