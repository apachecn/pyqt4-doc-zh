# QXmlQuery Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlQuery类执行的XQuery查询XML数据，或仿照看起来像XML的非XML数据。[More...](#details)

### Types

*   `enum QueryLanguage { XQuery10, XSLT20 }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlQuery other)`
*   `__init__ (self, QXmlNamePool np)`
*   `__init__ (self, QueryLanguage queryLanguage, QXmlNamePool pool = QXmlNamePool())`
*   `bindVariable (self, QXmlName name, QXmlItem value)`
*   `bindVariable (self, QXmlName name, QIODevice)`
*   `bindVariable (self, QXmlName name, QXmlQuery query)`
*   `bindVariable (self, QString localName, QXmlItem value)`
*   `bindVariable (self, QString localName, QIODevice)`
*   `bindVariable (self, QString localName, QXmlQuery query)`
*   `evaluateTo (self, QXmlResultItems result)`
*   `bool evaluateTo (self, QAbstractXmlReceiver callback)`
*   `bool evaluateTo (self, QStringList target)`
*   `bool evaluateTo (self, QIODevice target)`
*   `bool evaluateTo (self, QString output)`
*   `QString evaluateToString (self)`
*   `QStringList evaluateToStringList (self)`
*   `QXmlName initialTemplateName (self)`
*   `bool isValid (self)`
*   `QAbstractMessageHandler messageHandler (self)`
*   `QXmlNamePool namePool (self)`
*   `QNetworkAccessManager networkAccessManager (self)`
*   `QueryLanguage queryLanguage (self)`
*   `setFocus (self, QXmlItem item)`
*   `bool setFocus (self, QUrl documentURI)`
*   `bool setFocus (self, QIODevice document)`
*   `bool setFocus (self, QString focus)`
*   `setInitialTemplateName (self, QXmlName name)`
*   `setInitialTemplateName (self, QString name)`
*   `setMessageHandler (self, QAbstractMessageHandler messageHandler)`
*   `setNetworkAccessManager (self, QNetworkAccessManager newManager)`
*   `setQuery (self, QString sourceCode, QUrl documentUri = QUrl())`
*   `setQuery (self, QIODevice sourceCode, QUrl documentUri = QUrl())`
*   `setQuery (self, QUrl queryURI, QUrl baseUri = QUrl())`
*   `setUriResolver (self, QAbstractUriResolver resolver)`
*   `QAbstractUriResolver uriResolver (self)`

* * *

## Detailed Description

该QXmlQuery类执行的XQuery查询XML数据，或仿照看起来像XML的非XML数据。

该QXmlQuery类编译和执行写入查询[XQuery language](http://www.w3.org/TR/xquery/)。 QXmlQuery通常是用来查询XML数据，但它也可以查询已仿照看起来像XML的非XML数据。

使用QXmlQuery查询XML数据，如下面的代码片段，很简单，因为它可以使用内置的[XML data model](qabstractxmlnodemodel.html)作为其代表来遍历数据基础查询引擎。在指定了内置的数据模型[XQuery 1.0 and XPath 2.0 Data Model](http://www.w3.org/TR/xpath-datamodel/)。

```
 QXmlQuery query;
 query.setQuery("doc('index.html')/html/body/p[1]");

 [QXmlSerializer](qxmlserializer.html) serializer(query, myOutputDevice);
 query.evaluateTo(&serializer);

```

该示例使用QXmlQuery来匹配XML文档的第一个段落，然后[output the result](qxmlserializer.html)到设备为XML。

使用QXmlQuery查询_non-XML_数据需要写入的子类[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)作为替换为内置的XML数据模型的使用。自定义数据模型将能够遍历非XML数据所要求的[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)接口。这个自定义数据模型的实例就变成使用的查询引擎遍历非XML数据的委讬。有关如何使用QXmlQuery查询非XML数据，请参阅文档的一个例子[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

### Running XQueries

要运行设置与QXmlQuery查询，调用的评价功能之一。

*   evaluateTo([QAbstractXmlReceiver](qabstractxmlreceiver.html) *) is called with a pointer to an XML [receiver](qabstractxmlreceiver.html), which receives the query results as a sequence of callbacks. The receiver callback class is like the callback class used for translating the output of a SAX parser. [QXmlSerializer](qxmlserializer.html), for example, is a receiver callback class for translating the sequence of callbacks for output as unformatted XML text.

*   evaluateTo([QXmlResultItems](qxmlresultitems.html) *) is called with a pointer to an iterator for an empty sequence of query [result items](qxmlresultitems.html). The Java-like iterator allows the query results to be accessed sequentially.

*   evaluateTo([QStringList](qstringlist.html) *) is like evaluateTo([QXmlResultItems](qxmlresultitems.html) *), but the query must evaluate to a sequence of strings.

### Running XPath Expressions

XPath语言是的一个子集[XQuery](index.htm)语言，所以运行XPath表达式是一样的运行[XQuery](index.htm)查询。通过使用XPath表达式来QXmlQuery[setQuery](qxmlquery.html#setQuery)（ ） 。

### Running XSLT stylesheets

运行一个XSLT样式表是喜欢跑步的[XQuery](index.htm)，不同之处在于，当你构建你的QXmlQuery ，你必须通过[QXmlQuery.XSLT20](qxmlquery.html#QueryLanguage-enum)告诉QXmlQuery解释不管它从得到[setQuery](qxmlquery.html#setQuery)（ ）作为XSLT样式表，而不是一个[XQuery](index.htm)。您还必须通过调用设置输入文件[setFocus](qxmlquery.html#setFocus)（ ） 。

```
     QXmlQuery query(QXmlQuery.XSLT20);
     query.setFocus([QUrl](qurl.html)("myInput.xml"));
     query.setQuery([QUrl](qurl.html)("myStylesheet.xsl"));
     query.evaluateTo(out);

```

**Note:**目前，[setFocus](qxmlquery.html#setFocus)（ ）必须被调用_before_ [setQuery](qxmlquery.html#setQuery)（ ）使用XSLT时。

另一种方式来运行一个XSLT样式表是使用`xmlpatterns`命令行实用程序。

```
 xmlpatterns myStylesheet.xsl myInput.xml

```

**Note:**对于目前的版本中， XSLT支持应考虑实验。见[XSLT conformance](index.htm#xslt-2-0)了解详情。

样式表参数使用绑定[bindVariable](qxmlquery.html#bindVariable)（ ） 。

### Binding A Query To A Starting Node

当一个查询被执行的XML数据，如代码段所述，`doc()`函数返回的内置数据模型，其中的查询评估将开始的节点。但是，当一个查询运行在包含非XML数据的一个自定义节点模型[bindVariable](qxmlquery.html#bindVariable)（ ）函数必须调用一个变量名绑定到自定义模型的起始节点。澳元变量引用被用在[XQuery](index.htm)文字来访问自定义模型的起始节点。这是没有必要声明外部查询中的变量名。参见示例说明文档中的[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

### Reentrancy and Thread-Safety

QXmlQuery是可重入的，但不是线程安全的。它是安全使用QxmlQuery拷贝构造函数来创建查询的副本，并执行相同的查询多次。在幕后， QXmlQuery将重用，如打开的文件和编译的查询的资源尽可能。但它是不是安全使用QXmlQuery的同一实例中的多个线程。

### Error Handling

可发生在查询计算错误。例子包括错误类型和文件加载错误。当发生错误时：

*   The error message is sent to the [messageHandler](qxmlquery.html#messageHandler)().
*   [QXmlResultItems.hasError](qxmlresultitems.html#hasError)() will return `true`, or [evaluateTo](qxmlquery.html#evaluateTo)() will return `false`;
*   The results of the evaluation are undefined.

### Resource Management

当查询运行时，它会解析文件，分配内部数据结构来保存它们，则可能在网络上加载其他资源。这时候可能会重复使用这些分配的资源，以避免重新加载并重新分析他们。

When [setQuery](qxmlquery.html#setQuery)（）被调用时，该查询的文本被编译成一个内部数据结构，并进行了优化。优化的形式随后可重复用于查询的多个评估。由于编译 - 优化的过程可以是昂贵的，它重复了同样的查询，应避免使用QXmlQuery的一个单独的实例为每个查询文本。

一旦文件被解析，它的内部表示保持在QXmlQuery实例，并在多个QXmlQuery实例共享。

实例[QCoreApplication](qcoreapplication.html)必须存在QXmlQuery才能使用。

### Event Handling

当QXmlQuery访问资源（例如，呼叫`fn:doc()`加载一个文件，或通过绑定变量访问设备） ，事件循环使用，这意味着事件将被处理。为了避免处理事件时， QXmlQuery访问的资源，在一个单独的线程中创建您的QXmlQuery实例。

* * *

## Type Documentation

```
QXmlQuery.QueryLanguage
```

指定是否要[QXmlQuery](qxmlquery.html)解释输入到[setQuery](qxmlquery.html#setQuery)（）作为[XQuery](index.htm)或作为XSLT样式表。

| Constant | Value | Description |
| --- | --- | --- |
| `QXmlQuery.XQuery10` | `1` | [XQuery](index.htm)1.0 。 |
| `QXmlQuery.XSLT20` | `2` | XSLT 2.0的选择，在W3C XML模式1.1的唯一性约束上找到了禁区XPath模式。除了限制的语法，表达式的类型检查阶段假定节点序列成为焦点。领域， W3C XML模式1.1的唯一性约束上找到了禁区XPath模式。除了限制的语法，表达式的类型检查阶段假定节点序列成为焦点。表示的XPath 2.0 。拥有公共API中没有作用，它的内部使用。由于有了XmlSchema11IdentityConstraintSelector和XmlSchema11IdentityConstraintField ，表达式的类型检查阶段假定节点序列成为焦点。 |

这个枚举被引入或修改的Qt 4.5 。

**See also** [setQuery](qxmlquery.html#setQuery)（ ） 。

* * *

## Method Documentation

```
QXmlQuery.__init__ (self)
```

构造不能使用，直到无效的，空的查询[setQuery](qxmlquery.html#setQuery)（）被调用。

**Note:**如果您打算使用这个这个构造函数必须不能使用[QXmlQuery](qxmlquery.html)处理XSL -T样式表。其他的构造，必须在这种情况下被使用。

```
QXmlQuery.__init__ (self, QXmlQuery other)
```

构造一个[QXmlQuery](qxmlquery.html)即副本_other_。新的实例将与现有的查询尽可能共享资源。

```
QXmlQuery.__init__ (self, QXmlNamePool np)
```

构建将使用一个查询_np_正如它的名字池。该查询不能被计算，直到[setQuery](qxmlquery.html#setQuery)（ ）被调用。

```
QXmlQuery.__init__ (self, QueryLanguage queryLanguage, QXmlNamePool pool = QXmlNamePool())
```

构建体将被用来执行XQuery查询或XSL -T样式表的查询，这取决于的值_queryLanguage_。它将使用_np_正如它的名字池。

**Note:**如果你的[QXmlQuery](qxmlquery.html)将处理XSL -T样式表，这个构造函数必须被使用。默认的构造函数只能创建实例[QXmlQuery](qxmlquery.html)运行的XQuery 。

**Note:**本新闻稿中的XSL -T的支持，被认为是实验性的。请参阅[XSLT conformance](index.htm#xslt-2-0)了解详情。

此功能被引入Qt的4.5 。

**See also** [queryLanguage](qxmlquery.html#queryLanguage)（ ） 。

```
QXmlQuery.bindVariable (self, QXmlName name, QXmlItem value)
```

绑定变量_name_到_value_使$_name_可以从查询中用于指代的_value_。

_name_必须不_null_。_name_。 ISNULL（ ）必须返回False 。如果_name_已绑定由以前的bindVariable （ ）调用，它以前的绑定将被改写。

If _value_为null ，这样_value_。 ISNULL（ ）返回True，_name_已经有约束力的，效果是消除了现有绑定_name_。

要绑定类型的值[QString](qstring.html) or [QUrl](qurl.html)，包装在一个值[QVariant](qvariant.html)这样，[QXmlItem](qxmlitem.html)的[QVariant](qvariant.html)构造函数被调用。

由查询处理的所有字符串必须是有效的[XQuery](index.htm)字符串，这意味着它们必须只包含XML 1.0字符。然而，这一要求没有被选中。如果查询处理一个无效的字符串，该行为是未定义的。

**See also** [QVariant.isValid](qvariant.html#isValid)（ ）[How QVariant maps to XQuery's Data Model](index.htm#qtxdm)和[QXmlItem.isNull](qxmlitem.html#isNull)（ ） 。

```
QXmlQuery.bindVariable (self, QXmlName name, QIODevice)
```

绑定变量_name_到_device_使$_name_可以从查询中用于指代的_device_。该[QIODevice](qiodevice.html) _device_暴露于查询作为类型的URI`xs:anyURI`，它可以被传递到`fn:doc()`函数来进行读取。例如，该功能可用于在存储器中通过XML文档来`fn:doc`。

```
     [QByteArray](qbytearray.html) myDocument;
     [QBuffer](qbuffer.html) buffer(&myDocument); // This is a QIODevice.
     buffer.open([QIODevice](qiodevice.html).ReadOnly);
     [QXmlQuery](qxmlquery.html) query;
     query.bindVariable("myDocument", &buffer);
     query.setQuery("doc($myDocument)");

```

调用者必须确保_device_已被打开，至少[QIODevice.ReadOnly](qiodevice.html#OpenModeFlag-enum)在此之前绑定。否则，行为是未定义的。

如果该查询将访问包含在一个XML文档[QString](qstring.html)，使用[QBuffer](qbuffer.html)如下面的代码片段所示。假设_myQString_包含`&lt;document&gt;content&lt;/document&gt;`

```
     [QBuffer](qbuffer.html) device;
     device.setData(myQString.toUtf8());
     device.open([QIODevice](qiodevice.html).ReadOnly);

     [QXmlQuery](qxmlquery.html) query;
     query.bindVariable("inputDocument", &device);
     query.setQuery("doc($inputDocument)/query[theDocument]");

```

_name_必须不_null_。_name_。 ISNULL（ ）必须返回False 。如果_name_已绑定，其以前的绑定将被改写。该URI，它_name_计算结果为是任意的，可能会改变。

如果该变量绑定的变化（例如，飞行如果同名一个以前的绑定是一个[QVariant](qvariant.html)，或者，如果没有先前的绑定） ，[isValid](qxmlquery.html#isValid)（ ）将返回`false`，并且需要查询文本的重新编译。重新编译查询，请致电[setQuery](qxmlquery.html#setQuery)（ ） 。出于这个原因，[bindVariable](qxmlquery.html#bindVariable)（ ）之前，应叫[setQuery](qxmlquery.html#setQuery)（） ，如果可能的话。

**Note:** _device_不能被删除，而这[QXmlQuery](qxmlquery.html)存在。

```
QXmlQuery.bindVariable (self, QXmlName name, QXmlQuery query)
```

结合查询的结果_query_，一个变量的名字_name_。

评价_query_当这个函数被调用时会被展开。

If _query_是无效的，行为是未定义的。_query_将被复制。

此功能被引入Qt的4.5 。

**See also** [isValid](qxmlquery.html#isValid)（ ） 。

```
QXmlQuery.bindVariable (self, QString localName, QXmlItem value)
```

这是一个重载函数。

这个函数构造一个[QXmlName](qxmlname.html)从_localName_使用查询的[namespace](qxmlnamepool.html)。然后，该函数的行为与重载函数。它等价于下面的代码片段。

```
     [QXmlNamePool](qxmlnamepool.html) namePool(query.namePool());
     query.bindVariable([QXmlName](qxmlname.html)(namePool, localName), value);

```

```
QXmlQuery.bindVariable (self, QString localName, QIODevice)
```

这是一个重载函数。

If _localName_是一个有效的[NCName](qxmlname.html#isNCName)，这个功能相当于下面的代码片段。

```
     [QXmlNamePool](qxmlnamepool.html) namePool(query.namePool());
     query.bindVariable([QXmlName](qxmlname.html)(namePool, localName), device);

```

A [QXmlName](qxmlname.html)从构造_localName_，并传递到带有相应的过载_device_。

**See also** [QXmlName.isNCName](qxmlname.html#isNCName)（ ） 。

```
QXmlQuery.bindVariable (self, QString localName, QXmlQuery query)
```

这是一个重载函数。

具有相同的行为和效果被重载的函数，但需要在变量名_localName_作为[QString](qstring.html)。_query_用作重载的函数。

此功能被引入Qt的4.5 。

```
QXmlQuery.evaluateTo (self, QXmlResultItems result)
```

起动评价，并使其在可_result_。如果_result_为null，则行为是未定义的。评估发生增量（懒惰的评价） ，作为主叫方使用[QXmlResultItems.next](qxmlresultitems.html#next)（）来获取下一个结果。

**See also** [QXmlResultItems.next](qxmlresultitems.html#next)（ ） 。

```
bool QXmlQuery.evaluateTo (self, QAbstractXmlReceiver callback)
```

评估该查询，并将其结果作为对一个序列的回调[receiver](qabstractxmlreceiver.html) _callback_。[QXmlQuery](qxmlquery.html)不采取所有权_callback_。

如果评估过程中发生错误，错误信息被发送到[messageHandler](qxmlquery.html#messageHandler)（）和`false`返回。

如果此查询[is invalid](qxmlquery.html#isValid)，`false`返回和行为是未定义的。如果_callback_为空，行为是未定义的。

**See also** [QAbstractXmlReceiver](qabstractxmlreceiver.html)和[isValid](qxmlquery.html#isValid)（ ） 。

```
bool QXmlQuery.evaluateTo (self, QStringList target)
```

尝试评估该查询，并将结果返回在_target_ [string list](qstringlist.html)。

如果查询[is valid](qxmlquery.html#isValid)和评估成功，则返回True 。否则，返回False，并且内容_target_是不确定的。

查询必须评估为序列`xs:string`值。如果查询不计算为一个字符串序列，这些值通常可以通过增加一个调用转换`string()`在本月底[XQuery](index.htm)。

If _target_为null，则行为是未定义的。

```
bool QXmlQuery.evaluateTo (self, QIODevice target)
```

评估查询，序列化输出为XML到_output_。

如果评估过程中发生错误，错误信息被发送到[messageHandler](qxmlquery.html#messageHandler)（ ）的内容_output_是不确定的，`false`返回，否则`true`返回。

If _output_ is `null`行为是不确定的。[QXmlQuery](qxmlquery.html)不采取所有权_output_。

在内部，类[QXmlFormatter](qxmlformatter.html)用于此。

此功能被引入Qt的4.5 。

```
bool QXmlQuery.evaluateTo (self, QString output)
```

评估查询或样式表，并将输出写入到_target_。

[QXmlSerializer](qxmlserializer.html)用于将输出写入到_target_。在将来的版本中，它预计这一功能将被更改为尊重在样式表中设置序列化选项。

如果评估过程中发生错误，错误信息被发送到[messageHandler](qxmlquery.html#messageHandler)（）和`false`返回。

If _target_ is `null`或者是不是至少在开[QIODevice.WriteOnly](qiodevice.html#OpenModeFlag-enum)模式，其行为是未定义的。[QXmlQuery](qxmlquery.html)不采取所有权_target_。

这是一个重载函数。

此功能被引入Qt的4.5 。

```
QString QXmlQuery.evaluateToString (self)
```

```
QStringList QXmlQuery.evaluateToStringList (self)
```

```
QXmlName QXmlQuery.initialTemplateName (self)
```

[](qxmlname.html)

[返回XSL -T样式表的模板，运行一个XSL -T样式表时，处理器将调用的名头。此功能仅在使用适用](qxmlname.html)[QXmlQuery](qxmlquery.html)处理XSL -T样式表。缺省情况下，初始模板设置。在这种情况下，一个默认的构造[QXmlName](qxmlname.html)返回。

此功能被引入Qt的4.5 。

**See also** [setInitialTemplateName](qxmlquery.html#setInitialTemplateName)（ ） 。

```
bool QXmlQuery.isValid (self)
```

返回True如果这个查询是有效的。无效的查询的例子是那些包含语法错误或者还没有[setQuery](qxmlquery.html#setQuery)（ ）召之即来呢。

```
QAbstractMessageHandler QXmlQuery.messageHandler (self)
```

[](qabstractmessagehandler.html)

[返回处理这个编译和运行时消息的消息处理程序](qabstractmessagehandler.html)[QXmlQuery](qxmlquery.html)。

**See also** [setMessageHandler](qxmlquery.html#setMessageHandler)（ ） 。

```
QXmlNamePool QXmlQuery.namePool (self)
```

[](qxmlnamepool.html)

[返回此名称池](qxmlnamepool.html)[QXmlQuery](qxmlquery.html)构建[names](qxmlname.html)。有没有setter的名字池，因为混合池的名称会导致错误，由于名称的混乱。

```
QNetworkAccessManager QXmlQuery.networkAccessManager (self)
```

[

返回该网络管理器，或0 ，如果它没有被设置。

此功能被引入Qt的4.5 。

](qnetworkaccessmanager.html)

[**See also**](qnetworkaccessmanager.html) [setNetworkAccessManager](qxmlquery.html#setNetworkAccessManager)（ ） 。

```
QueryLanguage QXmlQuery.queryLanguage (self)
```

[](qxmlquery.html#QueryLanguage-enum)

[返回一个值，指示这是什么](qxmlquery.html#QueryLanguage-enum)[QXmlQuery](qxmlquery.html)被用于。默认值是[QXmlQuery.XQuery10](qxmlquery.html#QueryLanguage-enum)，这意味着[QXmlQuery](qxmlquery.html)被用于执行[XQuery](index.htm)和XPath查询。[QXmlQuery.XSLT20](qxmlquery.html#QueryLanguage-enum)也可以退回，这表明[QXmlQuery](qxmlquery.html)是运行XSL -T电子表格。

此功能被引入Qt的4.5 。

```
QXmlQuery.setFocus (self, QXmlItem item)
```

将焦点设置_item_。重点是一组上下文项表达式和路径表达式从导航的项目。例如，在表达式_p/span_时，该元件_p_计算结果为是重点下面的表达式，_span_。

焦点可以使用上下文项表达式来访问，即，点（ “。”） 。

默认情况下，焦点未设置，是不确定的。因此，它会导致动态误差，`XPDY0002`如果聚焦是试图将被访问。之前的查询设置与重点必须设置[setQuery](qxmlquery.html#setQuery)（ ） 。

没有设置它为null的项定义的行为。

```
bool QXmlQuery.setFocus (self, QUrl documentURI)
```

这是一个重载函数。

将焦点是位于文档_documentURI_并返回True 。如果_documentURI_无法加载，则返回False。它是不确定在什么时候该文件可能被加载。当加载文档，消息处理程序和URI解析器在此设置[QXmlQuery](qxmlquery.html)被使用。

If _documentURI_为空或不是一个有效的URI ，这个函数的行为是未定义的。

此功能被引入Qt的4.5 。

```
bool QXmlQuery.setFocus (self, QIODevice document)
```

将焦点是_document_从读[QIODevice](qiodevice.html)并返回True 。如果_document_无法加载，则返回False。

[QXmlQuery](qxmlquery.html)不采取所有权_document_。用户可以保证一个文件是可从_document_设备与该文件是不是空的。该设备必须至少在只读模式打开。_document_必须保持在范围只要当前查询是活动的。

这是一个重载函数。

此功能被引入Qt的4.5 。

```
bool QXmlQuery.setFocus (self, QString focus)
```

这个函数的作用相同，调用[setFocus](qxmlquery.html#setFocus)（ ）过载与[QIODevice](qiodevice.html)其内容是_focus_编码为UTF- 8 。即，_focus_被视为它包含在XML文档。

返回作为过载相同的结果。

这是一个重载函数。

此功能被引入Qt的4.6 。

```
QXmlQuery.setInitialTemplateName (self, QXmlName name)
```

设置_name_初始模板。初始模板，而不是试图匹配模板的上下文节点（如果有的话）一个处理器调用第一个。如果初始模板没有设置，模板调用的标准顺序将被使用。

此功能仅在使用适用[QXmlQuery](qxmlquery.html)处理XSL -T样式表。该名称将成为编译的样式表的一部分。因此，这个函数必须在调用之前调用[setQuery](qxmlquery.html#setQuery)（ ） 。

如果样式表没有命名模板_name_，该处理器将使用模板调用的标准顺序。

此功能被引入Qt的4.5 。

**See also** [initialTemplateName](qxmlquery.html#initialTemplateName)（ ） 。

```
QXmlQuery.setInitialTemplateName (self, QString name)
```

这是一个重载函数。

设置初始模板的名称，以_localName_，它必须是一个有效的[local name](qxmlname.html#localName)。初始模板，而不是试图匹配模板的上下文节点（如果有的话）一个处理器调用第一个。如果初始模板没有设置，模板调用的标准顺序将被使用。

此功能仅在使用适用[QXmlQuery](qxmlquery.html)处理XSL -T样式表。该名称将成为编译的样式表的一部分。因此，这个函数必须在调用之前调用[setQuery](qxmlquery.html#setQuery)（ ） 。

If _localName_不是一个有效的[local name](qxmlname.html#localName)，效果是不确定的。如果样式表没有命名模板_localName_，该处理器将使用模板调用的标准顺序。

此功能被引入Qt的4.5 。

**See also** [initialTemplateName](qxmlquery.html#initialTemplateName)（ ） 。

```
QXmlQuery.setMessageHandler (self, QAbstractMessageHandler messageHandler)
```

更改[message handler](qabstractmessagehandler.html)这[QXmlQuery](qxmlquery.html)至_aMessageHandler_。该查询将所有的编译和运行时消息，此消息处理程序。[QXmlQuery](qxmlquery.html)不采取所有权_aMessageHandler_。

通常情况下，默认的消息处理就足够了。它写的编译和运行时消息，_stderr_。默认的消息处理程序，包括颜色代码，如果_stderr_可以使色彩。

请注意，更改消息处理程序查询已经编译后没有效果，即查询在运行时使用相同的消息处理程序，它使用在编译时。

When [QXmlQuery](qxmlquery.html)电话[QAbstractMessageHandler.message](qabstractmessagehandler.html#message)（ ） ，参数如下：

| message() argument | Semantics |
| --- | --- |
| [QtMsgType](index.htm#QtMsgType-enum) type | Only [QtWarningMsg](index.htm#QtMsgType-enum) and [QtFatalMsg](index.htm#QtMsgType-enum) are used. The former identifies a compile or runtime warning, while the latter identifies a dynamic or static error. |
| const [QString](qstring.html) & description | An XHTML document which is the actual message. It is translated into the current language. |
| const [QUrl](qurl.html) &identifier | Identifies the error with a URI, where the fragment is the error code, and the rest of the URI is the error namespace. |
| const [QSourceLocation](qsourcelocation.html) & sourceLocation | Identifies where the error occurred. |

**See also** [messageHandler](qxmlquery.html#messageHandler)（ ） 。

```
QXmlQuery.setNetworkAccessManager (self, QNetworkAccessManager newManager)
```

设置网络管理员_newManager_。[QXmlQuery](qxmlquery.html)不采取所有权_newManager_。

此功能被引入Qt的4.5 。

**See also** [networkAccessManager](qxmlquery.html#networkAccessManager)（ ） 。

```
QXmlQuery.setQuery (self, QString sourceCode, QUrl documentUri = QUrl())
```

此套[QXmlQuery](qxmlquery.html)到[XQuery](index.htm)从读_sourceCode_设备。该设备必须已经打开了至少[QIODevice.ReadOnly](qiodevice.html#OpenModeFlag-enum)。

_documentURI_表示从得到的查询_sourceCode_设备。它是静态上下文的基URI ，如在定义[XQuery language](http://www.w3.org/TR/xquery/)。它在内部使用，以解决出现在查询中相对URI ，以及消息的报告。_documentURI_可以为空。如果为空，则[application file path](qcoreapplication.html#applicationFilePath)被使用。如果不是空的，它可以是相对的或绝对的。如果是相对的，它解决了自身对[application file path](qcoreapplication.html#applicationFilePath)之前就被采用。如果_documentURI_既不是一个有效的URI ，也没有空，其结果是不确定的。

如果查询包含一个静态错误（如语法错误） ，则错误消息被发送到[messageHandler](qxmlquery.html#messageHandler)（）和[isValid](qxmlquery.html#isValid)（ ）将返回_false_。

变量必须setQuery前绑定（ ）被调用。

的编码[XQuery](index.htm)在_sourceCode_检测到内部使用的规则来设置和检测编码[XQuery](index.htm)文件，这些文件中的解释[XQuery language](http://www.w3.org/TR/xquery/)。

If _sourceCode_ is `null`或无法读取，或者如果_documentURI_是不是一个有效的URI ，行为是未定义的。

**See also** [isValid](qxmlquery.html#isValid)（ ） 。

```
QXmlQuery.setQuery (self, QIODevice sourceCode, QUrl documentUri = QUrl())
```

此套[QXmlQuery](qxmlquery.html)到[XQuery](index.htm)从读_queryURI_。使用[isValid](qxmlquery.html#isValid)（ ）调用此函数后。如果发生读取错误_queryURI_比如，查询不存在，无法读取，或者是无效的，[isValid](qxmlquery.html#isValid)（ ）将返回_false_。

所支持的URI方案是相同的[XQuery](index.htm)功能`fn:doc`，除了queryURI可以是一个变量绑定的对象。

_baseURI_是静态上下文的基URI ，如定义[XQuery language](http://www.w3.org/TR/xquery/)。它在内部使用，以解决出现在查询中相对URI ，以及消息的报告。如果_baseURI_是空的，_queryURI_被使用。否则，_baseURI_被使用，并且它解决了对[application file path](qcoreapplication.html#applicationFilePath)如果它是相对的。

If _queryURI_为空或无效，或者如果_baseURI_是无效的，这个函数的行为是未定义的。

```
QXmlQuery.setQuery (self, QUrl queryURI, QUrl baseUri = QUrl())
```

这是一个重载函数。

这个函数的行为和要求是一样的setQuery （[QIODevice](qiodevice.html)* ，常量[QUrl](qurl.html)＆），后[XQuery](index.htm)已经读取的IO设备插入一个字符串。因为_sourceCode_已经是一个Unicode字符串，检测它的编码是不必要的。

```
QXmlQuery.setUriResolver (self, QAbstractUriResolver resolver)
```

设置的URI解析器_resolver_。[QXmlQuery](qxmlquery.html)不采取所有权_resolver_。

**See also** [uriResolver](qxmlquery.html#uriResolver)（ ） 。

```
QAbstractUriResolver QXmlQuery.uriResolver (self)
```

[](qabstracturiresolver.html)

[返回查询的URI解析器。如果没有的URI解析器已定，](qabstracturiresolver.html)[QtXmlPatterns](index.htm)将使用的URI的查询，因为它们。

这个URI解析器提供了一个抽象层，或_polymorphic URIs_。解析器可以重写_logical_URI与物理的，或者它可以翻译过时的或无效的URI来有效的。

[QtXmlPatterns](index.htm)调用的URI解析器遇到所有的URI ，除了命名空间。具体而言，所有内建的函数来处理的URI （`fn:doc()`和`fn:doc-available()`） 。

在的情况下`fn:doc()`，绝对URI是基URI在静态情况下（这最有可能是查询的位置） 。而不是使用URI指定的用户的返回值[QAbstractUriResolver.resolve](qabstracturiresolver.html#resolve)（）将被使用。

When [QtXmlPatterns](index.htm)电话[QAbstractUriResolver.resolve](qabstracturiresolver.html#resolve)（ ）的绝对URI是由授权的URI[XQuery](index.htm)语言，相对URI是由用户指定的URI。

**See also** [setUriResolver](qxmlquery.html#setUriResolver)（ ） 。