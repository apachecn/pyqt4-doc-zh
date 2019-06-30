# QTextTableCell Class Reference

## [[QtGui](index.htm) module]

该QTextTableCell类表示一个单元格中的属性[QTextTable](qtexttable.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextTableCell o)`
*   `int column (self)`
*   `int columnSpan (self)`
*   `QTextCursor firstCursorPosition (self)`
*   `QTextCharFormat format (self)`
*   `bool isValid (self)`
*   `QTextCursor lastCursorPosition (self)`
*   `int row (self)`
*   `int rowSpan (self)`
*   `setFormat (self, QTextCharFormat format)`
*   `int tableCellFormatIndex (self)`

### Special Methods

*   `bool __eq__ (self, QTextTableCell other)`
*   `bool __ne__ (self, QTextTableCell other)`

* * *

## Detailed Description

该QTextTableCell类表示一个单元格中的属性[QTextTable](qtexttable.html)。

表细胞是文档结构件属于一个表。该表定货细胞转化为特定的行和列，单元格也可以跨多个列和行。

当一个表被插入到文档与细胞通常被创建[QTextCursor.insertTable](qtextcursor.html#insertTable)（ ） ，但他们也创造了，当一个表被重新调整被破坏。

细胞中含有大约在表中的位置信息，你可以得到[row](qtexttablecell.html#row)（）和[column](qtexttablecell.html#column)（）编号的细胞，其[rowSpan](qtexttablecell.html#rowSpan)（）和[columnSpan](qtexttablecell.html#columnSpan)（ ） 。

该[format](qtexttablecell.html#format)一个细胞的（ ）描述了其内容的默认字符格式。该[firstCursorPosition](qtexttablecell.html#firstCursorPosition)（）和[lastCursorPosition](qtexttablecell.html#lastCursorPosition)（）函数用于获取文档中的单元格的范围。

* * *

## Method Documentation

```
QTextTableCell.__init__ (self)
```

构造一个无效的表格单元格。

**See also** [isValid](qtexttablecell.html#isValid)（ ） 。

```
QTextTableCell.__init__ (self, QTextTableCell o)
```

拷贝构造函数。创建一个新的[QTextTableCell](qtexttablecell.html)基于所述对象_other_细胞。

```
int QTextTableCell.column (self)
```

返回包含该小区中的表中的列的数目。

**See also** [row](qtexttablecell.html#row)（ ） 。

```
int QTextTableCell.columnSpan (self)
```

返回该列单元格跨越的数目。默认值是1 。

**See also** [rowSpan](qtexttablecell.html#rowSpan)（ ） 。

```
QTextCursor QTextTableCell.firstCursorPosition (self)
```

[

返回此单元格中的第一个有效的光标位置。

](qtextcursor.html)

[**See also**](qtextcursor.html) [lastCursorPosition](qtexttablecell.html#lastCursorPosition)（ ） 。

```
QTextCharFormat QTextTableCell.format (self)
```

[

返回单元格的字符格式。

](qtextcharformat.html)

[**See also**](qtextcharformat.html) [setFormat](qtexttablecell.html#setFormat)（ ） 。

```
bool QTextTableCell.isValid (self)
```

返回True如果这是一个有效的表格单元格，否则返回False 。

```
QTextCursor QTextTableCell.lastCursorPosition (self)
```

[

返回此单元格中的最后一个有效的光标位置。

](qtextcursor.html)

[**See also**](qtextcursor.html) [firstCursorPosition](qtexttablecell.html#firstCursorPosition)（ ） 。

```
int QTextTableCell.row (self)
```

返回该行的表中的号码，包含此小区。

**See also** [column](qtexttablecell.html#column)（ ） 。

```
int QTextTableCell.rowSpan (self)
```

返回该行的单元格跨越的数目。默认值是1 。

**See also** [columnSpan](qtexttablecell.html#columnSpan)（ ） 。

```
QTextTableCell.setFormat (self, QTextCharFormat format)
```

设置单元格的字符格式_format_。例如，这可以被用来改变整个单元的背景色：

[QTextTableCell](qtexttablecell.html)细胞=表 - \u003e cellAt （2 ，3）;[QTextCharFormat](qtextcharformat.html)格式=细胞。[format](qtexttablecell.html#format)（）; format.setBackground （[Qt.blue](qt.html#GlobalColor-enum)） ; cell.setFormat （格式） ;

需要注意的是单元格的行或列跨度无法通过这个功能改变。你必须使用QTextTable.mergeCells和QTextTable.splitCell代替。

这个函数中引入了Qt 4.2中。

**See also** [format](qtexttablecell.html#format)（ ） 。

```
int QTextTableCell.tableCellFormatIndex (self)
```

返回文档的内部格式列表中的TableCell的格式的索引。

此功能被引入Qt的4.5 。

**See also** [QTextDocument.allFormats](qtextdocument.html#allFormats)（ ） 。

```
bool QTextTableCell.__eq__ (self, QTextTableCell other)
```

```
bool QTextTableCell.__ne__ (self, QTextTableCell other)
```