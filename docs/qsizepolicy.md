# QSizePolicy Class Reference

## [[QtGui](index.htm) module]

该QSizePolicy类是描述水平和垂直大小调整政策的布局属性。[More...](#details)

### Types

*   `enum ControlType { DefaultType, ButtonBox, CheckBox, ComboBox, ..., ToolButton }`
*   `class **[ControlTypes](index.htm)**`
*   `enum Policy { Fixed, Minimum, Maximum, Preferred, ..., Ignored }`
*   `enum PolicyFlag { GrowFlag, ExpandFlag, ShrinkFlag, IgnoreFlag }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, Policy horizontal, Policy vertical)`
*   `__init__ (self, Policy horizontal, Policy vertical, ControlType type)`
*   `__init__ (self, QVariant variant)`
*   `__init__ (self, QSizePolicy)`
*   `ControlType controlType (self)`
*   `Qt.Orientations expandingDirections (self)`
*   `bool hasHeightForWidth (self)`
*   `bool hasWidthForHeight (self)`
*   `Policy horizontalPolicy (self)`
*   `int horizontalStretch (self)`
*   `setControlType (self, ControlType type)`
*   `setHeightForWidth (self, bool b)`
*   `setHorizontalPolicy (self, Policy d)`
*   `setHorizontalStretch (self, int stretchFactor)`
*   `setVerticalPolicy (self, Policy d)`
*   `setVerticalStretch (self, int stretchFactor)`
*   `setWidthForHeight (self, bool b)`
*   `transpose (self)`
*   `Policy verticalPolicy (self)`
*   `int verticalStretch (self)`

### Special Methods

*   `bool __eq__ (self, QSizePolicy s)`
*   `bool __ne__ (self, QSizePolicy s)`

* * *

## Detailed Description

该QSizePolicy类是描述水平和垂直大小调整政策的布局属性。

窗口小部件的大小策略是愿意以各种方式来被调整大小的表达式，并且会影响该部件是由处理[layout engine](index.htm)。每个插件返回一个QSizePolicy描述它宁愿当被布置在水平和垂直大小调整政策。你可以通过改变改变这个特定的小部件[QWidget.sizePolicy](qwidget.html#sizePolicy-prop)属性。

QSizePolicy包含两个独立的[QSizePolicy.Policy](qsizepolicy.html#Policy-enum)值和两个拉伸因子; 1描述的窗口小部件的水平尺寸的政策，以及其他描述其垂直尺寸的策略。它还包含一个标志，以指示其优选尺寸的高度和宽度是否是相关的。

水平和垂直的政策可以在构造函数中设置，并使用改变了[setHorizontalPolicy](qsizepolicy.html#setHorizontalPolicy)（）和[setVerticalPolicy](qsizepolicy.html#setVerticalPolicy)（）函数。拉伸因子可使用设置[setHorizontalStretch](qsizepolicy.html#setHorizontalStretch)（）和[setVerticalStretch](qsizepolicy.html#setVerticalStretch)（）函数。的标志，表示该部件的[sizeHint()](qwidget.html#sizeHint-prop)是宽度依赖性（如菜单栏或一个字包装标籤）可以使用被设置了[setHeightForWidth](qsizepolicy.html#setHeightForWidth)（）函数。

电流的大小政策和伸展因子使用被检索的[horizontalPolicy](qsizepolicy.html#horizontalPolicy)（ ）[verticalPolicy](qsizepolicy.html#verticalPolicy)（ ）[horizontalStretch](qsizepolicy.html#horizontalStretch)（）和[verticalStretch](qsizepolicy.html#verticalStretch)（）函数。或者，使用[transpose](qsizepolicy.html#transpose)（）函数来交换的水平和垂直的政策和延伸。该[hasHeightForWidth](qsizepolicy.html#hasHeightForWidth)（ ）函数返回的标志的指示尺寸暗示的依赖关系的现状。

使用[expandingDirections](qsizepolicy.html#expandingDirections)（ ）函数来确定相关的部件是否可以使更多的空间使用比其[sizeHint()](qwidget.html#sizeHint-prop)功能指示，以及找出哪些方向可以扩展。

最后， QSizePolicy类提供比较该尺寸的政策，在给定策略操作符，以及一个[QVariant](qvariant.html)运营商存储此QSizePolicy作为[QVariant](qvariant.html)对象。

* * *

## Type Documentation

```
QSizePolicy.ControlType
```

这个枚举变量指定不同类型的窗口小部件的布局互动方面：

| Constant | Value | Description |
| --- | --- | --- |
| `QSizePolicy.DefaultType` | `0x00000001` | 默认类型，未指定时。 |
| `QSizePolicy.ButtonBox` | `0x00000002` | A [QDialogButtonBox](qdialogbuttonbox.html)实例。 |
| `QSizePolicy.CheckBox` | `0x00000004` | A [QCheckBox](qcheckbox.html)实例。 |
| `QSizePolicy.ComboBox` | `0x00000008` | A [QComboBox](qcombobox.html)实例。 |
| `QSizePolicy.Frame` | `0x00000010` | A [QFrame](qframe.html)实例。 |
| `QSizePolicy.GroupBox` | `0x00000020` | A [QGroupBox](qgroupbox.html)实例。 |
| `QSizePolicy.Label` | `0x00000040` | A [QLabel](qlabel.html)实例。 |
| `QSizePolicy.Line` | `0x00000080` | A [QFrame](qframe.html)例如用[QFrame.HLine](qframe.html#Shape-enum) or [QFrame.VLine](qframe.html#Shape-enum)。 |
| `QSizePolicy.LineEdit` | `0x00000100` | A [QLineEdit](qlineedit.html)实例。 |
| `QSizePolicy.PushButton` | `0x00000200` | A [QPushButton](qpushbutton.html)实例。 |
| `QSizePolicy.RadioButton` | `0x00000400` | A [QRadioButton](qradiobutton.html)实例。 |
| `QSizePolicy.Slider` | `0x00000800` | A [QAbstractSlider](qabstractslider.html)实例。 |
| `QSizePolicy.SpinBox` | `0x00001000` | A [QAbstractSpinBox](qabstractspinbox.html)实例。 |
| `QSizePolicy.TabWidget` | `0x00002000` | A [QTabWidget](qtabwidget.html)实例。 |
| `QSizePolicy.ToolButton` | `0x00004000` | A [QToolButton](qtoolbutton.html)实例。 |

这个枚举被引入或修改的Qt 4.3 。

该ControlTypes类型是一个typedef为[QFlags](index.htm)\u003cControlType\u003e 。它存储的ControlType值的或组合。

**See also** [setControlType](qsizepolicy.html#setControlType)（）和[controlType](qsizepolicy.html#controlType)（ ） 。

```
QSizePolicy.Policy
```

这个枚举变量描述了各种每一维度大小类型构建时使用[QSizePolicy](qsizepolicy.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QSizePolicy.Fixed` | `0` | 该[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ）是唯一可以接受的选择，所以小部件不能增大或缩小（一个按钮，例如垂直方向） 。 |
| `QSizePolicy.Minimum` | `GrowFlag` | 在sizeHint （ ）是最小的，并且足够了。窗口小部件可以扩充，但它是更大（的按钮，例如水平方向）没有任何优势。它不能小于由sizeHint （）中提供的尺寸。 |
| `QSizePolicy.Maximum` | `ShrinkFlag` | 在sizeHint （）是一个最大值。窗口小部件可以被任何缩水金额不损害如果其他部件所需要的空间（如分隔线） 。它不能小于由sizeHint （）中提供的尺寸。 |
| `QSizePolicy.Preferred` | `GrowFlag &#124; ShrinkFlag` | 在sizeHint （ ）是最好的，但小部件可以被缩小，仍然是有用的。窗口小部件可以扩充，但它比sizeHint大没有优势（ ） （默认[QWidget](qwidget.html)政策）。 |
| `QSizePolicy.Expanding` | `GrowFlag &#124; ShrinkFlag &#124; ExpandFlag` | 在sizeHint （）是一个明智的大小，但小部件可以被缩小，仍然是有用的。窗口小部件可以利用额外的空间，所以它应该得到尽可能多的空间可能（例如一个水平滑块的水平方向） 。 |
| `QSizePolicy.MinimumExpanding` | `GrowFlag &#124; ExpandFlag` | 在sizeHint （ ）是最小的，并且足够了。窗口小部件可以利用额外的空间，所以它应该得到尽可能多的空间可能（例如一个水平滑块的水平方向） 。 |
| `QSizePolicy.Ignored` | `ShrinkFlag &#124; GrowFlag &#124; IgnoreFlag` | 在sizeHint （ ）被忽略。该部件将得到尽可能多的空间可能。 |

**See also** [PolicyFlag](qsizepolicy.html#PolicyFlag-enum)，[setHorizontalPolicy](qsizepolicy.html#setHorizontalPolicy)（）和[setVerticalPolicy](qsizepolicy.html#setVerticalPolicy)（ ） 。

```
QSizePolicy.PolicyFlag
```

这些标志被组合在一起以形成各种[Policy](qsizepolicy.html#Policy-enum)价值观：

| Constant | Value | Description |
| --- | --- | --- |
| `QSizePolicy.GrowFlag` | `1` | 如有必要，该部件可以超过它的大小提示。 |
| `QSizePolicy.ExpandFlag` | `2` | 该部件应该得到尽可能多的空间可能。 |
| `QSizePolicy.ShrinkFlag` | `4` | 窗口小部件可以收缩低于其尺寸暗示如果必要的。 |
| `QSizePolicy.IgnoreFlag` | `8` | 该物件的尺寸暗示被忽略。该部件将得到尽可能多的空间可能。 |

**See also** [Policy](qsizepolicy.html#Policy-enum)。

* * *

## Method Documentation

```
QSizePolicy.__init__ (self)
```

构造一个[QSizePolicy](qsizepolicy.html)与对象[Fixed](qsizepolicy.html#Policy-enum)作为它的水平和垂直的政策。

该策略可以使用改变了[setHorizontalPolicy](qsizepolicy.html#setHorizontalPolicy)（）和[setVerticalPolicy](qsizepolicy.html#setVerticalPolicy)（）函数。使用[setHeightForWidth](qsizepolicy.html#setHeightForWidth)（）函数，如果小部件的优选的高度是依赖于部件的宽度（例如，一个[QLabel](qlabel.html)用换行） 。

**See also** [setHorizontalStretch](qsizepolicy.html#setHorizontalStretch)（）和[setVerticalStretch](qsizepolicy.html#setVerticalStretch)（ ） 。

```
QSizePolicy.__init__ (self, Policy horizontal, Policy vertical)
```

构造一个[QSizePolicy](qsizepolicy.html)与给定对象_horizontal_和_vertical_政策和[DefaultType](qsizepolicy.html#ControlType-enum)作为控件类型。

使用[setHeightForWidth](qsizepolicy.html#setHeightForWidth)（）如果小部件的优选的高度是依赖于部件的宽度（例如，一个[QLabel](qlabel.html)用换行） 。

**See also** [setHorizontalStretch](qsizepolicy.html#setHorizontalStretch)（）和[setVerticalStretch](qsizepolicy.html#setVerticalStretch)（ ） 。

```
QSizePolicy.__init__ (self, Policy horizontal, Policy vertical, ControlType type)
```

构造一个[QSizePolicy](qsizepolicy.html)与给定对象_horizontal_和_vertical_政策，并指定控件_type_。

使用[setHeightForWidth](qsizepolicy.html#setHeightForWidth)（）如果小部件的优选的高度是依赖于部件的宽度（例如，一个[QLabel](qlabel.html)用换行） 。

此功能被引入Qt的4.3 。

**See also** [setHorizontalStretch](qsizepolicy.html#setHorizontalStretch)（ ）[setVerticalStretch](qsizepolicy.html#setVerticalStretch)（）和[controlType](qsizepolicy.html#controlType)（ ） 。

```
QSizePolicy.__init__ (self, QVariant variant)
```

```
QSizePolicy.__init__ (self, QSizePolicy)
```

```
ControlType QSizePolicy.controlType (self)
```

[

返回与它这种规模的政策适用于小部件关联的控件类型。

此功能被引入Qt的4.3 。

](qsizepolicy.html#ControlType-enum)

[**See also**](qsizepolicy.html#ControlType-enum) [setControlType](qsizepolicy.html#setControlType)（ ） 。

```
Qt.Orientations QSizePolicy.expandingDirections (self)
```

[](index.htm)

[返回一个widget是否可以使更多的空间使用比](index.htm)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ）函数表示。

的值[Qt.Horizontal](qt.html#Orientation-enum) or [Qt.Vertical](qt.html#Orientation-enum)也就是说，小部件可以水平或垂直生长（即水平或垂直的政策是[Expanding](qsizepolicy.html#Policy-enum) or [MinimumExpanding](qsizepolicy.html#Policy-enum)），而[Qt.Horizontal](qt.html#Orientation-enum)|[Qt.Vertical](qt.html#Orientation-enum)也就是说，它可以在两维生长。

**See also** [horizontalPolicy](qsizepolicy.html#horizontalPolicy)（）和[verticalPolicy](qsizepolicy.html#verticalPolicy)（ ） 。

```
bool QSizePolicy.hasHeightForWidth (self)
```

返回True如果控件的首选高度依赖于它的宽度，否则返回False 。

**See also** [setHeightForWidth](qsizepolicy.html#setHeightForWidth)（ ） 。

```
bool QSizePolicy.hasWidthForHeight (self)
```

返回True如果Widget的宽度取决于它的高度，否则返回False 。

此功能被引入Qt的4.8 。

**See also** [setWidthForHeight](qsizepolicy.html#setWidthForHeight)（ ） 。

```
Policy QSizePolicy.horizontalPolicy (self)
```

[

返回大小政策的水平分量。

](qsizepolicy.html#Policy-enum)

[**See also**](qsizepolicy.html#Policy-enum) [setHorizontalPolicy](qsizepolicy.html#setHorizontalPolicy)（ ）[verticalPolicy](qsizepolicy.html#verticalPolicy)（）和[horizontalStretch](qsizepolicy.html#horizontalStretch)（ ） 。

```
int QSizePolicy.horizontalStretch (self)
```

返回大小政策的水平拉伸因子。

**See also** [setHorizontalStretch](qsizepolicy.html#setHorizontalStretch)（ ）[verticalStretch](qsizepolicy.html#verticalStretch)（）和[horizontalPolicy](qsizepolicy.html#horizontalPolicy)（ ） 。

```
QSizePolicy.setControlType (self, ControlType type)
```

设置与它这种规模的政策适用于小部件关联的控件类型_type_。

控制类型指定这个大小政策适用widget的类型。它是利用一些风格，特别是[QMacStyle](index.htm)，插入部件之间适当的间距。例如， Mac OS X的水族准则指定按钮应该由12个像素进行分离，而垂直堆叠的单选按钮只需要6个像素。

此功能被引入Qt的4.3 。

**See also** [controlType](qsizepolicy.html#controlType)（）和[QStyle.layoutSpacing](qstyle.html#layoutSpacing)（ ） 。

```
QSizePolicy.setHeightForWidth (self, bool b)
```

设置一个标志，确定部件的首选高度是否取决于它的宽度，以_dependent_。

**See also** [hasHeightForWidth](qsizepolicy.html#hasHeightForWidth)（）和[setWidthForHeight](qsizepolicy.html#setWidthForHeight)（ ） 。

```
QSizePolicy.setHorizontalPolicy (self, Policy d)
```

设置的水平分量，以给定的_policy_。

**See also** [horizontalPolicy](qsizepolicy.html#horizontalPolicy)（ ）[setVerticalPolicy](qsizepolicy.html#setVerticalPolicy)（）和[setHorizontalStretch](qsizepolicy.html#setHorizontalStretch)（ ） 。

```
QSizePolicy.setHorizontalStretch (self, int stretchFactor)
```

将大小设置政策的水平伸长率与给定_stretchFactor_。

**See also** [horizontalStretch](qsizepolicy.html#horizontalStretch)（ ）[setVerticalStretch](qsizepolicy.html#setVerticalStretch)（）和[setHorizontalPolicy](qsizepolicy.html#setHorizontalPolicy)（ ） 。

```
QSizePolicy.setVerticalPolicy (self, Policy d)
```

设置垂直分量为给定的_policy_。

**See also** [verticalPolicy](qsizepolicy.html#verticalPolicy)（ ）[setHorizontalPolicy](qsizepolicy.html#setHorizontalPolicy)（）和[setVerticalStretch](qsizepolicy.html#setVerticalStretch)（ ） 。

```
QSizePolicy.setVerticalStretch (self, int stretchFactor)
```

设置大小政策的垂直拉伸因子来定_stretchFactor_。

**See also** [verticalStretch](qsizepolicy.html#verticalStretch)（ ）[setHorizontalStretch](qsizepolicy.html#setHorizontalStretch)（）和[setVerticalPolicy](qsizepolicy.html#setVerticalPolicy)（ ） 。

```
QSizePolicy.setWidthForHeight (self, bool b)
```

设置一个标志，确定widget的宽度是否依赖于它的高度，以_dependent_。

这是仅支持[QGraphicsLayout](qgraphicslayout.html)的子类。它不可能有两个高度为宽度和宽度作高度限制在同一时间的布局。

此功能被引入Qt的4.8 。

**See also** [hasWidthForHeight](qsizepolicy.html#hasWidthForHeight)（）和[setHeightForWidth](qsizepolicy.html#setHeightForWidth)（ ） 。

```
QSizePolicy.transpose (self)
```

交换的水平和垂直的政策和延伸。

```
Policy QSizePolicy.verticalPolicy (self)
```

[

返回大小政策的垂直分量。

](qsizepolicy.html#Policy-enum)

[**See also**](qsizepolicy.html#Policy-enum) [setVerticalPolicy](qsizepolicy.html#setVerticalPolicy)（ ）[horizontalPolicy](qsizepolicy.html#horizontalPolicy)（）和[verticalStretch](qsizepolicy.html#verticalStretch)（ ） 。

```
int QSizePolicy.verticalStretch (self)
```

返回大小政策的垂直拉伸因子。

**See also** [setVerticalStretch](qsizepolicy.html#setVerticalStretch)（ ）[horizontalStretch](qsizepolicy.html#horizontalStretch)（）和[verticalPolicy](qsizepolicy.html#verticalPolicy)（ ） 。

```
bool QSizePolicy.__eq__ (self, QSizePolicy s)
```

```
bool QSizePolicy.__ne__ (self, QSizePolicy s)
```