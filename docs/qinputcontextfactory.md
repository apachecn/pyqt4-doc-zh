# QInputContextFactory Class Reference

## [[QtGui](index.htm) module]

该QInputContextFactory类创建[QInputContext](qinputcontext.html)对象。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QInputContextFactory)`

### Static Methods

*   `QInputContext create (QString key, QObject parent)`
*   `QString description (QString key)`
*   `QString displayName (QString key)`
*   `QStringList keys ()`
*   `QStringList languages (QString key)`

* * *

## Detailed Description

该QInputContextFactory类创建[QInputContext](qinputcontext.html)对象。

输入上下文工厂创建一个[QInputContext](qinputcontext.html)对象对于一个给定密钥[QInputContextFactory.create](qinputcontextfactory.html#create)（ ） 。

输入上下文是内置的或动态的输入上下文的插件加载（见[QInputContextPlugin](index.htm)） 。

[keys](qinputcontextfactory.html#keys)（ ）返回的有效键的列表。键是使用的名称，例如，以识别并指定输入方法输入方法切换机构。该名称必须一致[QInputContext.identifierName](qinputcontext.html#identifierName)（ ） ，并可能只包含ASCII字符。

一键可用于通过检索相关的输入上下文的支持的语言[languages](qinputcontextfactory.html#languages)（ ） 。您可以使用检索输入上下文的描述[description](qinputcontextfactory.html#description)（ ），最后你可以得到的一个用户友好的国际化名称[QInputContext](qinputcontext.html)使用由键指定的对象[displayName](qinputcontextfactory.html#displayName)（ ） 。

版权所有（C ）2003-2004 immodule Qt的项目。保留所有权利。

该文件是写在自己的许可以促进诺基亚公司和/或其附属公司（ - IES ） 。你可以使用这个文件在你的Qt许可。下面的描述是从原来的文件头复制。联系immodule-qt@freedesktop.org如果是这种许可的条件不明确给你。

* * *

## Method Documentation

```
QInputContextFactory.__init__ (self)
```

```
QInputContextFactory.__init__ (self, QInputContextFactory)
```

```
QInputContext QInputContextFactory.create (QString key, QObject parent)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qinputcontext.html)

[创建并返回一个](qinputcontext.html)[QInputContext](qinputcontext.html)对象通过指定的输入上下文_key_用给定的_parent_。键是区分大小写的。

**See also** [keys](qinputcontextfactory.html#keys)（ ） 。

```
QString QInputContextFactory.description (QString key)
```

返回的一个国际化的简要说明[QInputContext](qinputcontext.html)由指定的对象_key_。你可以，例如，使用在用户界面这样的描述。

**See also** [keys](qinputcontextfactory.html#keys)（）和[displayName](qinputcontextfactory.html#displayName)（ ） 。

```
QString QInputContextFactory.displayName (QString key)
```

返回的一个用户友好的国际化名称[QInputContext](qinputcontext.html)由指定的对象_key_。你可以，例如，在一个菜单使用此名称。

**See also** [keys](qinputcontextfactory.html#keys)（）和[QInputContext.identifierName](qinputcontext.html#identifierName)（ ） 。

```
QStringList QInputContextFactory.keys ()
```

返回键这个工厂可以创建输入上下文的列表。

键是使用的名称，例如，以识别并指定输入方法输入方法切换机构。该名称必须一致[QInputContext.identifierName](qinputcontext.html#identifierName)（ ） ，并可能只包含ASCII字符。

**See also** [create](qinputcontextfactory.html#create)（ ）[displayName](qinputcontextfactory.html#displayName)（）和[QInputContext.identifierName](qinputcontext.html#identifierName)（ ） 。

```
QStringList QInputContextFactory.languages (QString key)
```

返回由所支持的语言[QInputContext](qinputcontext.html)由指定的对象_key_。

语言表达为语言代码（例如“ zh_CN的” ， “ ZH_TW ” ， “了zh_HK ” ， “ JA ” ， “KO” ， ... ） 。支持多国语言输入上下文可以返回所有支持的语言为[QStringList](qstringlist.html)。该名称必须一致[QInputContext.language](qinputcontext.html#language)（ ） 。

此信息可被用来优化的用户界面。

**See also** [keys](qinputcontextfactory.html#keys)（ ）[QInputContext.language](qinputcontext.html#language)（）和[QLocale](qlocale.html)。