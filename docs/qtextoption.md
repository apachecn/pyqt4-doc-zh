# QTextOption Class Reference

## [[QtGui](index.htm) module]

该QTextOption类提供一般的富文本属性的说明。[More...](#details)

### Types

*   `enum Flag { IncludeTrailingSpaces, ShowTabsAndSpaces, ShowLineAndParagraphSeparators, AddSpaceForLineAndParagraphSeparators, SuppressColors }`
*   `class **[Flags](index.htm)**`
*   `class **[Tab](index.htm)**`
*   `enum TabType { LeftTab, RightTab, CenterTab, DelimiterTab }`
*   `enum WrapMode { NoWrap, WordWrap, ManualWrap, WrapAnywhere, WrapAtWordBoundaryOrAnywhere }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, Qt.Alignment alignment)`
*   `__init__ (self, QTextOption o)`
*   `Qt.Alignment alignment (self)`
*   `Flags flags (self)`
*   `setAlignment (self, Qt.Alignment aalignment)`
*   `setFlags (self, Flags aflags)`
*   `setTabArray (self, list-of-float tabStops)`
*   `setTabs (self, list-of-QTextOption.Tab tabStops)`
*   `setTabStop (self, float atabStop)`
*   `setTextDirection (self, Qt.LayoutDirection aDirection)`
*   `setUseDesignMetrics (self, bool b)`
*   `setWrapMode (self, WrapMode wrap)`
*   `list-of-float tabArray (self)`
*   `list-of-QTextOption.Tab tabs (self)`
*   `float tabStop (self)`
*   `Qt.LayoutDirection textDirection (self)`
*   `bool useDesignMetrics (self)`
*   `WrapMode wrapMode (self)`

* * *

## Detailed Description

该QTextOption类提供一般的富文本属性的说明。

QTextOption用于封装在一个对象共同的富文本属性。它包含有关文本对齐，布局方向，自动换行，并用文字渲染和布局相关的其他标准属性的信息。

* * *

## Type Documentation

```
QTextOption.Flag
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextOption.IncludeTrailingSpaces` | `0x80000000` | 当这个选项被设置，[QTextLine.naturalTextWidth](qtextline.html#naturalTextWidth)（）和naturalTextRect （）返回一个值，该值包括尾随在文本空间的宽度，否则该宽度被排除在外。 |
| `QTextOption.ShowTabsAndSpaces` | `0x1` | 可视化与小圆点空格和制表符与小箭头。 |
| `QTextOption.ShowLineAndParagraphSeparators` | `0x2` | 可视化线和段落分隔符用适当的符号字符。 |
| `QTextOption.AddSpaceForLineAndParagraphSeparators` | `0x4` | 在确定换行的位置考虑到空间增加了绘制分隔符。 |
| `QTextOption.SuppressColors` | `0x8` | 抑制在字符格式的所有颜色变化（除了主选择） 。 |

该标志类型是一个typedef为[QFlags](index.htm)\u003cFlag\u003e 。它存储标志值的一个或组合。

```
QTextOption.TabType
```

这个枚举持有不同类型的制表

| Constant | Value | Description |
| --- | --- | --- |
| `QTextOption.LeftTab` | `0` | 左标籤 |
| `QTextOption.RightTab` | `1` | 右舌 |
| `QTextOption.CenterTab` | `2` | 居中的选项卡 |
| `QTextOption.DelimiterTab` | `3` | 一个标籤停止在某一个分隔符字符 |

这个枚举被引入或修改的Qt 4.4 。

```
QTextOption.WrapMode
```

这个枚举说明如何文本被包裹在一个文件中。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextOption.NoWrap` | `0` | 文字不换行的。 |
| `QTextOption.WordWrap` | `1` | 文本被包裹在字边界。 |
| `QTextOption.ManualWrap` | `2` | 同QTextOption.NoWrap |
| `QTextOption.WrapAnywhere` | `3` | 文本可以在一行上的任意点被包裹，即使它出现在字的中间。 |
| `QTextOption.WrapAtWordBoundaryOrAnywhere` | `4` | 如果可能的话，包装发生在一个字边界，否则将发生在线路上的适当的点，即使是在一个字的中间。 |

* * *

## Method Documentation

```
QTextOption.__init__ (self)
```

构建与文本的默认属性的文本选项。文本对齐属性设置为[Qt.AlignLeft](qt.html#AlignmentFlag-enum)。自动换行属性设置为[QTextOption.WordWrap](qtextoption.html#WrapMode-enum)。在使用设计度量的标志设置为False 。

```
QTextOption.__init__ (self, Qt.Alignment alignment)
```

构造一个文本选项与给定_alignment_文本。自动换行属性设置为[QTextOption.WordWrap](qtextoption.html#WrapMode-enum)。在使用设计度量的标志设置为False 。

```
QTextOption.__init__ (self, QTextOption o)
```

构建的一个副本_other_文本选项。

```
Qt.Alignment QTextOption.alignment (self)
```

[

返回由选项中定义的文本对齐方式。

](index.htm)

[**See also**](index.htm) [setAlignment](qtextoption.html#setAlignment)（ ） 。

```
Flags QTextOption.flags (self)
```

[

返回与该选项相关的标志。

](index.htm)

[**See also**](index.htm) [setFlags](qtextoption.html#setFlags)（ ） 。

```
QTextOption.setAlignment (self, Qt.Alignment aalignment)
```

设置选项的文本对齐到指定的_alignment_。

**See also** [alignment](qtextoption.html#alignment)（ ） 。

```
QTextOption.setFlags (self, Flags aflags)
```

设置的选项给定关联的标志_flags_。

**See also** [flags](qtextoption.html#flags)（ ） 。

```
QTextOption.setTabArray (self, list-of-float tabStops)
```

设置文本布局选项卡的位置，以那些由指定的_tabStops_。

**See also** [tabArray](qtextoption.html#tabArray)（ ）[setTabStop](qtextoption.html#setTabStop)（）和[setTabs](qtextoption.html#setTabs)（ ） 。

```
QTextOption.setTabs (self, list-of-QTextOption.Tab tabStops)
```

设置选项卡属性_tabStops_。

**See also** [tabStop](qtextoption.html#tabStop)（）和[tabs](qtextoption.html#tabs)（ ） 。

```
QTextOption.setTabStop (self, float atabStop)
```

设置选项卡之间的默认距离设备单位停止由指定的值_tabStop_。

**See also** [tabStop](qtextoption.html#tabStop)（ ）[setTabArray](qtextoption.html#setTabArray)（ ）[setTabs](qtextoption.html#setTabs)（）和[tabs](qtextoption.html#tabs)（ ） 。

```
QTextOption.setTextDirection (self, Qt.LayoutDirection aDirection)
```

设置通过选项来指定所定义的文本布局方向_direction_。

**See also** [textDirection](qtextoption.html#textDirection)（ ） 。

```
QTextOption.setUseDesignMetrics (self, bool b)
```

If _enable_为真，那么布局将使用的设计指标，否则它会使用绘图设备的指标（这是默认行为） 。

**See also** [useDesignMetrics](qtextoption.html#useDesignMetrics)（ ） 。

```
QTextOption.setWrapMode (self, WrapMode wrap)
```

设置选项的文本换行模式为给定的_mode_。

**See also** [wrapMode](qtextoption.html#wrapMode)（ ） 。

```
list-of-float QTextOption.tabArray (self)
```

返回文本布局定义选项卡位置的列表。

**See also** [setTabArray](qtextoption.html#setTabArray)（）和[tabStop](qtextoption.html#tabStop)（ ） 。

```
list-of-QTextOption.Tab QTextOption.tabs (self)
```

返回文本布局定义选项卡位置的列表。

此功能被引入Qt的4.4 。

**See also** [tabStop](qtextoption.html#tabStop)（ ）[setTabs](qtextoption.html#setTabs)（）和[setTabStop](qtextoption.html#setTabStop)（ ） 。

```
float QTextOption.tabStop (self)
```

返回制表位之间的设备单位的距离。功能方便了上面的方法

**See also** [setTabStop](qtextoption.html#setTabStop)（ ）[tabArray](qtextoption.html#tabArray)（ ）[setTabs](qtextoption.html#setTabs)（）和[tabs](qtextoption.html#tabs)（ ） 。

```
Qt.LayoutDirection QTextOption.textDirection (self)
```

[

返回由选项中定义的文本布局的方向。

](qt.html#LayoutDirection-enum)

[**See also**](qt.html#LayoutDirection-enum) [setTextDirection](qtextoption.html#setTextDirection)（ ） 。

```
bool QTextOption.useDesignMetrics (self)
```

返回True如果使用布局设计，而不是设备的指标，否则返回False 。

**See also** [setUseDesignMetrics](qtextoption.html#setUseDesignMetrics)（ ） 。

```
WrapMode QTextOption.wrapMode (self)
```

[

返回由选项中定义的文本换行模式。

](qtextoption.html#WrapMode-enum)

[**See also**](qtextoption.html#WrapMode-enum) [setWrapMode](qtextoption.html#setWrapMode)（ ） 。