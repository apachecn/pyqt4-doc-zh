# QTextTableCellFormat Class Reference

## [[QtGui](index.htm) module]

该QTextTableCellFormat类提供格式设置信息表中的单元格[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextCharFormat](qtextcharformat.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextTableCellFormat)`
*   `float bottomPadding (self)`
*   `bool isValid (self)`
*   `float leftPadding (self)`
*   `float rightPadding (self)`
*   `setBottomPadding (self, float padding)`
*   `setLeftPadding (self, float padding)`
*   `setPadding (self, float padding)`
*   `setRightPadding (self, float padding)`
*   `setTopPadding (self, float padding)`
*   `float topPadding (self)`

* * *

## Detailed Description

该QTextTableCellFormat类提供格式设置信息表中的单元格[QTextDocument](qtextdocument.html)。

在文档中的表格单元格的表格单元格的格式指定表格单元格的可视属性。

表格单元格的填充属性由控制[setLeftPadding](qtexttablecellformat.html#setLeftPadding)（ ）[setRightPadding](qtexttablecellformat.html#setRightPadding)（ ）[setTopPadding](qtexttablecellformat.html#setTopPadding)（）和[setBottomPadding](qtexttablecellformat.html#setBottomPadding)（ ） 。所有垫可以设置一次使用[setPadding](qtexttablecellformat.html#setPadding)（ ） 。

* * *

## Method Documentation

```
QTextTableCellFormat.__init__ (self)
```

构造一个新的表格单元格的格式对象。

此功能被引入Qt的4.4 。

```
QTextTableCellFormat.__init__ (self, QTextTableCellFormat)
```

```
float QTextTableCellFormat.bottomPadding (self)
```

获取表格单元格的底部填充。

此功能被引入Qt的4.4 。

**See also** [setBottomPadding](qtexttablecellformat.html#setBottomPadding)（ ）[leftPadding](qtexttablecellformat.html#leftPadding)（ ）[rightPadding](qtexttablecellformat.html#rightPadding)（）和[topPadding](qtexttablecellformat.html#topPadding)（ ） 。

```
bool QTextTableCellFormat.isValid (self)
```

返回True如果表格单元格的格式是有效的，否则返回False 。

此功能被引入Qt的4.4 。

```
float QTextTableCellFormat.leftPadding (self)
```

获取表格单元格的左填充。

此功能被引入Qt的4.4 。

**See also** [setLeftPadding](qtexttablecellformat.html#setLeftPadding)（ ）[rightPadding](qtexttablecellformat.html#rightPadding)（ ）[topPadding](qtexttablecellformat.html#topPadding)（）和[bottomPadding](qtexttablecellformat.html#bottomPadding)（ ） 。

```
float QTextTableCellFormat.rightPadding (self)
```

获取表格单元格的右边填充。

此功能被引入Qt的4.4 。

**See also** [setRightPadding](qtexttablecellformat.html#setRightPadding)（ ）[leftPadding](qtexttablecellformat.html#leftPadding)（ ）[topPadding](qtexttablecellformat.html#topPadding)（）和[bottomPadding](qtexttablecellformat.html#bottomPadding)（ ） 。

```
QTextTableCellFormat.setBottomPadding (self, float padding)
```

设置底部_padding_表单元格。

此功能被引入Qt的4.4 。

**See also** [bottomPadding](qtexttablecellformat.html#bottomPadding)（ ）[setLeftPadding](qtexttablecellformat.html#setLeftPadding)（ ）[setRightPadding](qtexttablecellformat.html#setRightPadding)（）和[setTopPadding](qtexttablecellformat.html#setTopPadding)（ ） 。

```
QTextTableCellFormat.setLeftPadding (self, float padding)
```

设置左_padding_表单元格。

此功能被引入Qt的4.4 。

**See also** [leftPadding](qtexttablecellformat.html#leftPadding)（ ）[setRightPadding](qtexttablecellformat.html#setRightPadding)（ ）[setTopPadding](qtexttablecellformat.html#setTopPadding)（）和[setBottomPadding](qtexttablecellformat.html#setBottomPadding)（ ） 。

```
QTextTableCellFormat.setPadding (self, float padding)
```

设置左，右，上，下_padding_表单元格。

此功能被引入Qt的4.4 。

**See also** [setLeftPadding](qtexttablecellformat.html#setLeftPadding)（ ）[setRightPadding](qtexttablecellformat.html#setRightPadding)（ ）[setTopPadding](qtexttablecellformat.html#setTopPadding)（）和[setBottomPadding](qtexttablecellformat.html#setBottomPadding)（ ） 。

```
QTextTableCellFormat.setRightPadding (self, float padding)
```

设置右边_padding_表单元格。

此功能被引入Qt的4.4 。

**See also** [rightPadding](qtexttablecellformat.html#rightPadding)（ ）[setLeftPadding](qtexttablecellformat.html#setLeftPadding)（ ）[setTopPadding](qtexttablecellformat.html#setTopPadding)（）和[setBottomPadding](qtexttablecellformat.html#setBottomPadding)（ ） 。

```
QTextTableCellFormat.setTopPadding (self, float padding)
```

设置顶部_padding_表单元格。

此功能被引入Qt的4.4 。

**See also** [topPadding](qtexttablecellformat.html#topPadding)（ ）[setLeftPadding](qtexttablecellformat.html#setLeftPadding)（ ）[setRightPadding](qtexttablecellformat.html#setRightPadding)（）和[setBottomPadding](qtexttablecellformat.html#setBottomPadding)（ ） 。

```
float QTextTableCellFormat.topPadding (self)
```

获取表格单元格的顶部填充。

此功能被引入Qt的4.4 。

**See also** [setTopPadding](qtexttablecellformat.html#setTopPadding)（ ）[leftPadding](qtexttablecellformat.html#leftPadding)（ ）[rightPadding](qtexttablecellformat.html#rightPadding)（）和[bottomPadding](qtexttablecellformat.html#bottomPadding)（ ） 。