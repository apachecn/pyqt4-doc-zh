# QXmlNamespaceSupport Class Reference

## [[QtXml](index.htm) module]

该QXmlNamespaceSupport类是一个辅助类XML的读者这要包括命名空间支持。[More...](#details)

### Methods

*   `__init__ (self)`
*   `popContext (self)`
*   `QString prefix (self, QString)`
*   `QStringList prefixes (self)`
*   `QStringList prefixes (self, QString)`
*   `processName (self, QString, bool, QString, QString)`
*   `pushContext (self)`
*   `reset (self)`
*   `setPrefix (self, QString, QString)`
*   `splitName (self, QString, QString, QString)`
*   `QString uri (self, QString)`

* * *

## Detailed Description

该QXmlNamespaceSupport类是一个辅助类XML的读者这要包括命名空间支持。

您可以设置前缀为当前命名空间[setPrefix](qxmlnamespacesupport.html#setPrefix)（ ） ，并获取当前前缀（或那些在给定的URI ）的列表[prefixes](qxmlnamespacesupport.html#prefixes)（ ） 。命名空间URI可从[uri](qxmlnamespacesupport.html#uri)（ ） 。使用[pushContext](qxmlnamespacesupport.html#pushContext)（ ）来启动一个新的命名空间上下文，[popContext](qxmlnamespacesupport.html#popContext)（）以返回到先前的名称空间上下文。使用[splitName](qxmlnamespacesupport.html#splitName)（）或[processName](qxmlnamespacesupport.html#processName)（ ）的名字时分为前缀和本地名称。

* * *

## Method Documentation

```
QXmlNamespaceSupport.__init__ (self)
```

构造一个[QXmlNamespaceSupport](qxmlnamespacesupport.html)。

```
QXmlNamespaceSupport.popContext (self)
```

恢复到以前的名称空间上下文。

通常情况下，你应该弹出的上下文在每个XML元素的结束。弹出的上下文后，所有的命名空间前缀映射以前在部队得到恢复。

**See also** [pushContext](qxmlnamespacesupport.html#pushContext)（ ） 。

```
QString QXmlNamespaceSupport.prefix (self, QString)
```

返回映射到命名空间URI的前缀之一_uri_。

如果一个以上的前缀当前映射到同一个URI ，这个功能使得一个任意的选择，如果你想要所有的前缀，使用[prefixes](qxmlnamespacesupport.html#prefixes)（ ）来代替。

注：要检查是否有默认前缀，使用[uri](qxmlnamespacesupport.html#uri)（ ）函数以“ ”的说法。

**See also** [setPrefix](qxmlnamespacesupport.html#setPrefix)（ ） 。

```
QStringList QXmlNamespaceSupport.prefixes (self)
```

返回当前声明的前缀列表。

如果有一个默认的前缀，这个功能并不在列表中返回它;检查使用缺省前缀[uri](qxmlnamespacesupport.html#uri)（ ）以“ ”的说法。

```
QStringList QXmlNamespaceSupport.prefixes (self, QString)
```

这是一个重载函数。

返回所有前缀的当前命名空间URI声明的列表_uri_。

在“ XML ： ”前缀是包括在内。如果你只想要一个映射到命名空间URI的前缀，你不关心哪一个你得到的，使用[prefix](qxmlnamespacesupport.html#prefix)（ ）函数来代替。

注：空（默认）前缀是从来没有列入这个名单，检查是否有默认命名空间，调用的存在[uri](qxmlnamespacesupport.html#uri)（ ）以“ ”作为参数。

```
QXmlNamespaceSupport.processName (self, QString, bool, QString, QString)
```

在目前情况下通过删除前缀和寻找它目前宣布的前缀中处理一个原始的XML 1.0的名称。

_qname_要被处理的原始XML 1.0的名称。_isAttribute_是真的，如果名字是一个属性名称。

这个函数存储到命名空间URI_nsuri_（这将被设置为空字符串，如果原始名称有一个未声明的前缀） ，并存储在本地名称（不带前缀）_localname_（这将被设置为空字符串，如果没有命名空间是在使用中） 。

请注意，属性名是不同于元素名称处理：一个没有前缀的元素名称获取默认命名空间（如果有的话） ，而一个没有前缀的属性名称不。

```
QXmlNamespaceSupport.pushContext (self)
```

启动一个新的名称空间上下文。

通常情况下，你应该推动一个新的上下文在每个XML元素的开始：新的上下文自动继承其父上下文的声明，并且它也跟踪哪些声明是在这一背景下进行。

**See also** [popContext](qxmlnamespacesupport.html#popContext)（ ） 。

```
QXmlNamespaceSupport.reset (self)
```

重置此命名空间支持对象准备重用。

```
QXmlNamespaceSupport.setPrefix (self, QString, QString)
```

这个函数声明的前缀_pre_在当前名称空间上下文是命名空间URI_uri_。前缀仍然有效，直到此背景下被弹出，除非它被遮蔽在子上下文。

需要注意的是在这个库中的不对称性。[prefix](qxmlnamespacesupport.html#prefix)（ ）不返回默认的“ ”前缀，即使你已经宣布之一，检查是否有默认前缀，则必须使用明确查一查[uri](qxmlnamespacesupport.html#uri)（ ） 。这种不对称的存在，使其更容易查找前缀的属性名，其中是不允许的默认前缀。

**See also** [prefix](qxmlnamespacesupport.html#prefix)（ ） 。

```
QXmlNamespaceSupport.splitName (self, QString, QString, QString)
```

拆分名_qname_在'：'并返回前缀_prefix_并在当地名称_localname_。

**See also** [processName](qxmlnamespacesupport.html#processName)（ ） 。

```
QString QXmlNamespaceSupport.uri (self, QString)
```

查找前缀_prefix_在目前情况下，并返回当前映射的命名空间URI 。使用空字符串（ “”）的默认命名空间。