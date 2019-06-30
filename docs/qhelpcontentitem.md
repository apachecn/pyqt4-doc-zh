# QHelpContentItem Class Reference

## [[QtHelp](index.htm) module]

该QHelpContentItem类提供的项目与使用[QHelpContentModel](qhelpcontentmodel.html)。[More...](#details)

### Methods

*   `QHelpContentItem child (self, int row)`
*   `int childCount (self)`
*   `int childPosition (self, QHelpContentItem child)`
*   `QHelpContentItem parent (self)`
*   `int row (self)`
*   `QString title (self)`
*   `QUrl url (self)`

* * *

## Detailed Description

该QHelpContentItem类提供的项目与使用[QHelpContentModel](qhelpcontentmodel.html)。

* * *

## Method Documentation

```
QHelpContentItem QHelpContentItem.child (self, int row)
```

[

返回的内容项的子在该给予_row_。

](qhelpcontentitem.html)

[**See also**](qhelpcontentitem.html) [parent](qhelpcontentitem.html#parent)（ ） 。

```
int QHelpContentItem.childCount (self)
```

返回子项的数量。

```
int QHelpContentItem.childPosition (self, QHelpContentItem child)
```

返回给定位置_child_。

```
QHelpContentItem QHelpContentItem.parent (self)
```

[

返回父内容项目。

```
int QHelpContentItem.row (self)
```

从它的父母视图返回此项目的行。

```
QString QHelpContentItem.title (self)
```

返回内容项目的标题。

](qhelpcontentitem.html)

```
QUrl QHelpContentItem.url (self)
```

[

返回此内容项的URL 。

](qurl.html)