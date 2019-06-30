# QFormLayout Class Reference

## [[QtGui](index.htm) module]

该QFormLayout类管理输入部件及其关联的标籤形式。[More...](#details)

继承[QLayout](qlayout.html)。

### Types

*   `enum FieldGrowthPolicy { FieldsStayAtSizeHint, ExpandingFieldsGrow, AllNonFixedFieldsGrow }`
*   `enum ItemRole { LabelRole, FieldRole, SpanningRole }`
*   `enum RowWrapPolicy { DontWrapRows, WrapLongRows, WrapAllRows }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `addItem (self, QLayoutItem item)`
*   `addRow (self, QWidget label, QWidget field)`
*   `addRow (self, QWidget label, QLayout field)`
*   `addRow (self, QString labelText, QWidget field)`
*   `addRow (self, QString labelText, QLayout field)`
*   `addRow (self, QWidget widget)`
*   `addRow (self, QLayout layout)`
*   `int count (self)`
*   `Qt.Orientations expandingDirections (self)`
*   `FieldGrowthPolicy fieldGrowthPolicy (self)`
*   `Qt.Alignment formAlignment (self)`
*   `(int rowPtr, ItemRole rolePtr) getItemPosition (self, int index)`
*   `(int rowPtr, ItemRole rolePtr) getLayoutPosition (self, QLayout layout)`
*   `(int rowPtr, ItemRole rolePtr) getWidgetPosition (self, QWidget widget)`
*   `bool hasHeightForWidth (self)`
*   `int heightForWidth (self, int width)`
*   `int horizontalSpacing (self)`
*   `insertRow (self, int row, QWidget label, QWidget field)`
*   `insertRow (self, int row, QWidget label, QLayout field)`
*   `insertRow (self, int row, QString labelText, QWidget field)`
*   `insertRow (self, int row, QString labelText, QLayout field)`
*   `insertRow (self, int row, QWidget widget)`
*   `insertRow (self, int row, QLayout layout)`
*   `invalidate (self)`
*   `QLayoutItem itemAt (self, int row, ItemRole role)`
*   `QLayoutItem itemAt (self, int index)`
*   `Qt.Alignment labelAlignment (self)`
*   `QWidget labelForField (self, QWidget field)`
*   `QWidget labelForField (self, QLayout field)`
*   `QSize minimumSize (self)`
*   `int rowCount (self)`
*   `RowWrapPolicy rowWrapPolicy (self)`
*   `setFieldGrowthPolicy (self, FieldGrowthPolicy policy)`
*   `setFormAlignment (self, Qt.Alignment alignment)`
*   `setGeometry (self, QRect rect)`
*   `setHorizontalSpacing (self, int spacing)`
*   `setItem (self, int row, ItemRole role, QLayoutItem item)`
*   `setLabelAlignment (self, Qt.Alignment alignment)`
*   `setLayout (self, int row, ItemRole role, QLayout layout)`
*   `setRowWrapPolicy (self, RowWrapPolicy policy)`
*   `setSpacing (self, int)`
*   `setVerticalSpacing (self, int spacing)`
*   `setWidget (self, int row, ItemRole role, QWidget widget)`
*   `QSize sizeHint (self)`
*   `int spacing (self)`
*   `QLayoutItem takeAt (self, int index)`
*   `int verticalSpacing (self)`

* * *

## Detailed Description

该QFormLayout类管理输入部件及其关联的标籤形式。

QFormLayout是勾画出它在一个两列的表格孩子一个方便的布局类。左栏包括标籤，右列包含“场”的小部件（行编辑器，旋转框等） 。

传统上，这样的两栏式布局形式采用实现[QGridLayout](qgridlayout.html)。 QFormLayout是更高级别的替代方案，提供了以下优点：

*   **Adherence to the different platform's look and feel guidelines.**

    例如，本 [Mac OS X Aqua](http://developer.apple.com/documentation/UserExperience/Conceptual/AppleHIGuidelines/XHIGIntro/chapter_1_section_1.html)和KDE指引指定的标籤应该是右对齐的，而Windows和GNOME应用程序通常使用左对齐。

*   **Support for wrapping long rows.**

    对于具有小显示器的设备， QFormLayout可以设置为[wrap long rows](qformlayout.html#RowWrapPolicy-enum)或什至[wrap all rows](qformlayout.html#RowWrapPolicy-enum)。

*   **Convenient API for creating label--field pairs.**

    该[addRow](qformlayout.html#addRow)（ ）重载采用一个[QString](qstring.html)和[QWidget](qwidget.html)*创建一个[QLabel](qlabel.html)在幕后，并自动设置其为好友。然后，我们可以编写这样的代码：

    ```
     QFormLayout *formLayout = new QFormLayout;
     formLayout-&gt;addRow(tr("&Name:"), nameLineEdit);
     formLayout-&gt;addRow(tr("&Email:"), emailLineEdit);
     formLayout-&gt;addRow(tr("&Age:"), ageSpinBox);
     setLayout(formLayout);

    ```

    使用下面的代码，写的比较这[QGridLayout](qgridlayout.html)：

    ```
     nameLabel = new [QLabel](qlabel.html)(tr("&Name:"));
     nameLabel-&gt;setBuddy(nameLineEdit);

     emailLabel = new [QLabel](qlabel.html)(tr("&Name:"));
     emailLabel-&gt;setBuddy(emailLineEdit);

     ageLabel = new [QLabel](qlabel.html)(tr("&Name:"));
     ageLabel-&gt;setBuddy(ageSpinBox);

     [QGridLayout](qgridlayout.html) *gridLayout = new [QGridLayout](qgridlayout.html);
     gridLayout-&gt;addWidget(nameLabel, 0, 0);
     gridLayout-&gt;addWidget(nameLineEdit, 0, 1);
     gridLayout-&gt;addWidget(emailLabel, 1, 0);
     gridLayout-&gt;addWidget(emailLineEdit, 1, 1);
     gridLayout-&gt;addWidget(ageLabel, 2, 0);
     gridLayout-&gt;addWidget(ageSpinBox, 2, 1);
     setLayout(gridLayout);

    ```

下表显示了默认的外观在不同的风格。

| [QCommonStyle](qcommonstyle.html) derived styles (except [QPlastiqueStyle](index.htm)) | [QMacStyle](index.htm) | [QPlastiqueStyle](index.htm) | Qt Extended styles |
| --- | --- | --- | --- |
| ![](../img/qformlayout-win.png) | ![](../img/qformlayout-mac.png) | ![](../img/qformlayout-kde.png) | ![](../img/qformlayout-qpe.png) |
| Traditional style used for Windows, GNOME, and earlier versions of KDE. Labels are left aligned, and expanding fields grow to fill the available space. (This normally corresponds to what we would get using a two-column [QGridLayout](qgridlayout.html).) | Style based on the [Mac OS X Aqua](http://developer.apple.com/documentation/UserExperience/Conceptual/AppleHIGuidelines/XHIGIntro/chapter_1_section_1.html) guidelines. Labels are right-aligned, the fields don't grow beyond their size hint, and the form is horizontally centered. | Recommended style for [KDE applications](http://www.kdedevelopers.org/node/2345). Similar to MacStyle, except that the form is left-aligned and all fields grow to fill the available space. | Default style for Qt Extended styles. Labels are right-aligned, expanding fields grow to fill the available space, and row wrapping is enabled for long lines. |

表格样式可以也可以单独通过调用被重写[setLabelAlignment](qformlayout.html#labelAlignment-prop)（ ）[setFormAlignment](qformlayout.html#formAlignment-prop)（ ）[setFieldGrowthPolicy](qformlayout.html#fieldGrowthPolicy-prop)（）和[setRowWrapPolicy](qformlayout.html#rowWrapPolicy-prop)（ ） 。例如，以模拟的形式布局美观[QMacStyle](index.htm)在所有平台上，但左对齐的标籤，你可以这样写：

```
 formLayout->setRowWrapPolicy(QFormLayout.DontWrapRows);
 formLayout->setFieldGrowthPolicy(QFormLayout.FieldsStayAtSizeHint);
 formLayout->setFormAlignment([Qt](qt.html).AlignHCenter | [Qt](qt.html).AlignTop);
 formLayout->setLabelAlignment([Qt](qt.html).AlignLeft);

```

* * *

## Type Documentation

```
QFormLayout.FieldGrowthPolicy
```

该枚举指定可以被用来控制在该表单的字段成长的方式，不同的政策。

| Constant | Value | Description |
| --- | --- | --- |
| `QFormLayout.FieldsStayAtSizeHint` | `0` | 这些字段永远长不大超出了他们的[effective size hint](qwidgetitem.html#sizeHint)。这是默认的[QMacStyle](index.htm)。 |
| `QFormLayout.ExpandingFieldsGrow` | `1` | 与横向领域[size policy](qsizepolicy.html)的[Expanding](qsizepolicy.html#Policy-enum) or [MinimumExpanding](qsizepolicy.html#Policy-enum)将增长到填满可用空间。其他栏位不得超出其有效尺寸暗示。这是PLASTIQUE的默认策略。 |
| `QFormLayout.AllNonFixedFieldsGrow` | `2` | 用大小政策，使他们能够成长各个领域将增长到填满可用空间。这是大多数款式的默认策略。 |

**See also** [fieldGrowthPolicy](qformlayout.html#fieldGrowthPolicy-prop)。

```
QFormLayout.ItemRole
```

此枚举指定部件（或其他布局项目）的类型，可能会出现一排。

| Constant | Value | Description |
| --- | --- | --- |
| `QFormLayout.LabelRole` | `0` | 一个标籤控件。 |
| `QFormLayout.FieldRole` | `1` | 字段部件。 |
| `QFormLayout.SpanningRole` | `2` | 一个小部件，跨越标籤和字段列。 |

**See also** [itemAt](qformlayout.html#itemAt)（）和[getItemPosition](qformlayout.html#getItemPosition)（ ） 。

```
QFormLayout.RowWrapPolicy
```

该枚举指定可以被用来控制在该表格中的行包的方式，不同的政策。

| Constant | Value | Description |
| --- | --- | --- |
| `QFormLayout.DontWrapRows` | `0` | 字段总是奠定了旁边的标籤。这是除了Qt的扩展风格的缺省策略为所有的风格和[QS60Style](index.htm)。 |
| `QFormLayout.WrapLongRows` | `1` | 标籤被给予足够的水平空间，以适应宽的标籤，并且该空间的剩馀部分被提供给字段。如果一个场对的最小尺寸大于可用空间更宽，该字段被换到下一行。这是为Qt扩展的风格和和默认策略[QS60Style](index.htm)。 |
| `QFormLayout.WrapAllRows` | `2` | 字段总是布置下他们的标籤。 |

**See also** [rowWrapPolicy](qformlayout.html#rowWrapPolicy-prop)。

* * *

## Method Documentation

```
QFormLayout.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的窗体布局与给定_parent_小工具。

**See also** [QWidget.setLayout](qwidget.html#setLayout)（ ） 。

```
QFormLayout.addItem (self, QLayoutItem item)
```

该_item_说法有它的所有权转移给Qt的。

从重新实现[QLayout.addItem](qlayout.html#addItem)（ ） 。

```
QFormLayout.addRow (self, QWidget label, QWidget field)
```

该_label_说法有它的所有权转移给Qt的。

该_field_说法有它的所有权转移给Qt的。

添加一新行，以这种形式布局的底部，用给定的_label_和_field_。

**See also** [insertRow](qformlayout.html#insertRow)（ ） 。

```
QFormLayout.addRow (self, QWidget label, QLayout field)
```

该_label_说法有它的所有权转移给Qt的。

该_field_说法有它的所有权转移给Qt的。

这是一个重载函数。

```
QFormLayout.addRow (self, QString labelText, QWidget field)
```

该_field_说法有它的所有权转移给Qt的。

这是一个重载函数。

此重载自动创建一个[QLabel](qlabel.html)背后的幕后_labelText_作为其文本。该_field_被设置为新的[QLabel](qlabel.html)的[buddy](qlabel.html#setBuddy)。

```
QFormLayout.addRow (self, QString labelText, QLayout field)
```

该_field_说法有它的所有权转移给Qt的。

这是一个重载函数。

此重载自动创建一个[QLabel](qlabel.html)背后的幕后_labelText_作为其文本。

```
QFormLayout.addRow (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

这是一个重载函数。

将指定的_widget_在这种形式布局的结束。该_widget_横跨两列。

```
QFormLayout.addRow (self, QLayout layout)
```

该_layout_说法有它的所有权转移给Qt的。

这是一个重载函数。

将指定的_layout_在这种形式布局的结束。该_layout_横跨两列。

```
int QFormLayout.count (self)
```

从重新实现[QLayout.count](qlayout.html#count)（ ） 。

```
Qt.Orientations QFormLayout.expandingDirections (self)
```

[](index.htm)

[从重新实现](index.htm)[QLayoutItem.expandingDirections](qlayoutitem.html#expandingDirections)（ ） 。

```
FieldGrowthPolicy QFormLayout.fieldGrowthPolicy (self)
```

[](qformlayout.html#FieldGrowthPolicy-enum)

```
Qt.Alignment QFormLayout.formAlignment (self)
```

[

```
(int rowPtr, ItemRole rolePtr) QFormLayout.getItemPosition (self, int index)
```

检索项的行和角色（列）在指定的_index_。如果_index_是出界， *_rowPtr_被设置为-1 ，否则该行被存储在*_rowPtr_和作用是存储在*_rolePtr_。

](index.htm)

[**See also**](index.htm) [itemAt](qformlayout.html#itemAt)（ ）[count](qformlayout.html#count)（ ）[getLayoutPosition](qformlayout.html#getLayoutPosition)（）和[getWidgetPosition](qformlayout.html#getWidgetPosition)（ ） 。

```
(int rowPtr, ItemRole rolePtr) QFormLayout.getLayoutPosition (self, QLayout layout)
```

检索指定的子行和作用（列）_layout_。如果_layout_是不是在形式布局， *_rowPtr_被设置为-1 ，否则该行被存储在*_rowPtr_和作用是存储在*_rolePtr_。

```
(int rowPtr, ItemRole rolePtr) QFormLayout.getWidgetPosition (self, QWidget widget)
```

检索指定的行和作用（列）_widget_在布局。如果_widget_是不是在布局， *_rowPtr_被设置为-1 ，否则该行被存储在*_rowPtr_和作用是存储在*_rolePtr_。

**See also** [getItemPosition](qformlayout.html#getItemPosition)（）和[itemAt](qformlayout.html#itemAt)（ ） 。

```
bool QFormLayout.hasHeightForWidth (self)
```

从重新实现[QLayoutItem.hasHeightForWidth](qlayoutitem.html#hasHeightForWidth)（ ） 。

```
int QFormLayout.heightForWidth (self, int width)
```

从重新实现[QLayoutItem.heightForWidth](qlayoutitem.html#heightForWidth)（ ） 。

```
int QFormLayout.horizontalSpacing (self)
```

```
QFormLayout.insertRow (self, int row, QWidget label, QWidget field)
```

该_label_说法有它的所有权转移给Qt的。

该_field_说法有它的所有权转移给Qt的。

插入新行的位置_row_在这种形式布局，与给定_label_和_field_。如果_row_是出界，新行是在后面。

**See also** [addRow](qformlayout.html#addRow)（ ） 。

```
QFormLayout.insertRow (self, int row, QWidget label, QLayout field)
```

该_label_说法有它的所有权转移给Qt的。

该_field_说法有它的所有权转移给Qt的。

这是一个重载函数。

```
QFormLayout.insertRow (self, int row, QString labelText, QWidget field)
```

该_field_说法有它的所有权转移给Qt的。

这是一个重载函数。

此重载自动创建一个[QLabel](qlabel.html)背后的幕后_labelText_作为其文本。该_field_被设置为新的[QLabel](qlabel.html)的[buddy](qlabel.html#setBuddy)。

```
QFormLayout.insertRow (self, int row, QString labelText, QLayout field)
```

该_field_说法有它的所有权转移给Qt的。

这是一个重载函数。

此重载自动创建一个[QLabel](qlabel.html)背后的幕后_labelText_作为其文本。

```
QFormLayout.insertRow (self, int row, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

这是一个重载函数。

插入指定的_widget_在位置_row_在这种形式布局。该_widget_横跨两列。如果_row_是出界，小部件是在后面。

```
QFormLayout.insertRow (self, int row, QLayout layout)
```

该_layout_说法有它的所有权转移给Qt的。

这是一个重载函数。

插入指定的_layout_在位置_row_在这种形式布局。该_layout_横跨两列。如果_row_是出界，小部件是在后面。

```
QFormLayout.invalidate (self)
```

从重新实现[QLayoutItem.invalidate](qlayoutitem.html#invalidate)（ ） 。

```
QLayoutItem QFormLayout.itemAt (self, int row, ItemRole role)
```

[

返回指定布局项目_row_用指定的_role_（列） 。返回0，如果没有这样的项目。

](qlayoutitem.html)

[**See also**](qlayoutitem.html) [QLayout.itemAt](qlayout.html#itemAt)（）和[setItem](qformlayout.html#setItem)（ ） 。

```
QLayoutItem QFormLayout.itemAt (self, int index)
```

[](qlayoutitem.html)

[从重新实现](qlayoutitem.html)[QLayout.itemAt](qlayout.html#itemAt)（ ） 。

```
Qt.Alignment QFormLayout.labelAlignment (self)
```

[](index.htm)

```
QWidget QFormLayout.labelForField (self, QWidget field)
```

[

返回与给定关联的标籤_field_。

](qwidget.html)

[**See also**](qwidget.html) [itemAt](qformlayout.html#itemAt)（ ） 。

```
QWidget QFormLayout.labelForField (self, QLayout field)
```

[

这是一个重载函数。

](qwidget.html)

```
QSize QFormLayout.minimumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.minimumSize](qlayoutitem.html#minimumSize)（ ） 。

```
int QFormLayout.rowCount (self)
```

返回行形式的数量。

**See also** [QLayout.count](qlayout.html#count)（ ） 。

```
RowWrapPolicy QFormLayout.rowWrapPolicy (self)
```

[

```
QFormLayout.setFieldGrowthPolicy (self, FieldGrowthPolicy policy)
```

```
QFormLayout.setFormAlignment (self, Qt.Alignment alignment)
```

```
QFormLayout.setGeometry (self, QRect rect)
```

](qformlayout.html#RowWrapPolicy-enum)

[从重新实现](qformlayout.html#RowWrapPolicy-enum)[QLayoutItem.setGeometry](qlayoutitem.html#setGeometry)（ ） 。

```
QFormLayout.setHorizontalSpacing (self, int spacing)
```

```
QFormLayout.setItem (self, int row, ItemRole role, QLayoutItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置在给定的项目_row_对于给定的_role_至_item_，必要时用空行延伸的布局。

如果电池已经被佔用时，_item_没有被插入且一个错误消息被发送到控制台。该_item_横跨两列。

**Warning:**请不要使用此功能来添加子布局或子部件项目。使用[setLayout](qformlayout.html#setLayout)（）或[setWidget](qformlayout.html#setWidget)（ ）来代替。

**See also** [setLayout](qformlayout.html#setLayout)（ ） 。

```
QFormLayout.setLabelAlignment (self, Qt.Alignment alignment)
```

```
QFormLayout.setLayout (self, int row, ItemRole role, QLayout layout)
```

该_layout_说法有它的所有权转移给Qt的。

设置子布局在给定的_row_对于给定的_role_至_layout_，必要时用空行延伸的形式布局。

如果电池已经被佔用时，_layout_没有被插入且一个错误消息被发送到控制台。

**Note:**对于大多数应用，[addRow](qformlayout.html#addRow)（）或[insertRow](qformlayout.html#insertRow)（ ）应该使用的的setLayout （ ） 。

**See also** [setWidget](qformlayout.html#setWidget)（ ） 。

```
QFormLayout.setRowWrapPolicy (self, RowWrapPolicy policy)
```

```
QFormLayout.setSpacing (self, int)
```

此功能可设置垂直和水平间距_spacing_。

**See also** [spacing](qformlayout.html#spacing)（ ）[setVerticalSpacing](qformlayout.html#verticalSpacing-prop)（）和[setHorizontalSpacing](qformlayout.html#horizontalSpacing-prop)（ ） 。

```
QFormLayout.setVerticalSpacing (self, int spacing)
```

```
QFormLayout.setWidget (self, int row, ItemRole role, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置部件在给定的_row_对于给定的_role_至_widget_，必要时用空行延伸的布局。

如果电池已经被佔用时，_widget_没有被插入且一个错误消息被发送到控制台。

**Note:**对于大多数应用，[addRow](qformlayout.html#addRow)（）或[insertRow](qformlayout.html#insertRow)（ ）应该使用setWidget的（ ） 。

**See also** [setLayout](qformlayout.html#setLayout)（ ） 。

```
QSize QFormLayout.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.sizeHint](qlayoutitem.html#sizeHint)（ ） 。

```
int QFormLayout.spacing (self)
```

如果垂直间距相等的水平间距，这个函数返回该值，否则返回-1 。

**See also** [setSpacing](qformlayout.html#setSpacing)（ ）[verticalSpacing](qformlayout.html#verticalSpacing-prop)（）和[horizontalSpacing](qformlayout.html#horizontalSpacing-prop)（ ） 。

```
QLayoutItem QFormLayout.takeAt (self, int index)
```

[

该_QLayoutItem_结果

](qlayoutitem.html)

[从重新实现](qlayoutitem.html)[QLayout.takeAt](qlayout.html#takeAt)（ ） 。

```
int QFormLayout.verticalSpacing (self)
```