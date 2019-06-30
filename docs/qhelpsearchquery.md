# QHelpSearchQuery Class Reference

## [[QtHelp](index.htm) module]

该QHelpSearchQuery类包含字段名称和相关的搜索词[More...](#details)

### Types

*   `enum FieldName { DEFAULT, FUZZY, WITHOUT, PHRASE, ALL, ATLEAST }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, FieldName field, QStringList wordList)`
*   `__init__ (self, QHelpSearchQuery)`

* * *

## Detailed Description

该QHelpSearchQuery类包含字段名称和相关的搜索词

该QHelpSearchQuery类包含字段名称和相关的搜索词。视场搜索词可能会被分成不同的条款被搜索引擎不同的解析。

* * *

## Type Documentation

```
QHelpSearchQuery.FieldName
```

该枚举类型指定由搜索引擎处理的字段名。

| Constant | Value | Description |
| --- | --- | --- |
| `QHelpSearchQuery.DEFAULT` | `0` | 由搜索小工具提供的默认领域，有几个方面应该分开并存储在单词列表除了包含在引号中的搜索字词。 |
| `QHelpSearchQuery.FUZZY` | `1` | 一个字段只能与clucene使用规定。条款应分别在单独的单词，并传递给搜索引擎。 |
| `QHelpSearchQuery.WITHOUT` | `2` | 一个字段只能与clucene使用规定。条款应分别在单独的单词，并传递给搜索引擎。 |
| `QHelpSearchQuery.PHRASE` | `3` | 一个字段只能与clucene使用规定。条款不应被分成单独的单词。 |
| `QHelpSearchQuery.ALL` | `4` | 一个字段只能与clucene使用规定。术语应该被分成单独的词，并传递到搜索引擎 |
| `QHelpSearchQuery.ATLEAST` | `5` | 一个字段只能与clucene使用规定。术语应该被分成单独的词，并传递到搜索引擎 |

* * *

## Method Documentation

```
QHelpSearchQuery.__init__ (self)
```

构造一个新的空[QHelpSearchQuery](qhelpsearchquery.html)。

```
QHelpSearchQuery.__init__ (self, FieldName field, QStringList wordList)
```

构造一个新的[QHelpSearchQuery](qhelpsearchquery.html)并用给定的初始化它_field_和_wordList_。

```
QHelpSearchQuery.__init__ (self, QHelpSearchQuery)
```