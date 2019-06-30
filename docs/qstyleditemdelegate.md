# QStyledItemDelegate Class Reference

## [[QtGui](index.htm) module]

该QStyledItemDelegate类提供了从模型中的数据项的显示和编辑功能。[More...](#details)

继承[QAbstractItemDelegate](qabstractitemdelegate.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QWidget createEditor (self, QWidget parent, QStyleOptionViewItem option, QModelIndex index)`
*   `QString displayText (self, QVariant value, QLocale locale)`
*   `bool editorEvent (self, QEvent event, QAbstractItemModel model, QStyleOptionViewItem option, QModelIndex index)`
*   `bool eventFilter (self, QObject object, QEvent event)`
*   `initStyleOption (self, QStyleOptionViewItem option, QModelIndex index)`
*   `QItemEditorFactory itemEditorFactory (self)`
*   `paint (self, QPainter painter, QStyleOptionViewItem option, QModelIndex index)`
*   `setEditorData (self, QWidget editor, QModelIndex index)`
*   `setItemEditorFactory (self, QItemEditorFactory factory)`
*   `setModelData (self, QWidget editor, QAbstractItemModel model, QModelIndex index)`
*   `QSize sizeHint (self, QStyleOptionViewItem option, QModelIndex index)`
*   `updateEditorGeometry (self, QWidget editor, QStyleOptionViewItem option, QModelIndex index)`

* * *

## Detailed Description

该QStyledItemDelegate类提供了从模型中的数据项的显示和编辑功能。

当显示从模型数据中的Qt项目的意见，例如，一个[QTableView](qtableview.html)，个别项目被委讬绘制。此外，当一个项目被编辑时，它提供了一个编辑器窗口小部件，它被放置在项目视图的顶部，同时编辑发生的位置。 QStyledItemDelegate是默认的委讬对所有的Qt项目的意见，并在安装后，他们在创建时。

该QStyledItemDelegate类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。委讬允许项的显示和编辑，以独立于模型和视图开发的。

在模型项的数据分配一个[ItemDataRole](qt.html#ItemDataRole-enum);每个项目可以存储[QVariant](qvariant.html)为每个角色。 QStyledItemDelegate实现显示和编辑的预期用户最常用的数据类型，包括布尔，整数和字符串。

这些数据将被绘制不同，这取决于他们在模型中的作用。下表描述的角色和数据类型的委讬可以处理它们。它往往是足以确保模型返回每个角色的适当的数据，以确定项目的意见的外观。

| Role | Accepted Types |
| --- | --- |
| [Qt.BackgroundRole](qt.html#ItemDataRole-enum) | [QBrush](qbrush.html) |
| [Qt.BackgroundColorRole](qt.html#ItemDataRole-enum) | [QColor](qcolor.html) (obsolete; use [Qt.BackgroundRole](qt.html#ItemDataRole-enum) instead) |
| [Qt.CheckStateRole](qt.html#ItemDataRole-enum) | [Qt.CheckState](qt.html#CheckState-enum) |
| [Qt.DecorationRole](qt.html#ItemDataRole-enum) | [QIcon](qicon.html), [QPixmap](qpixmap.html), [QImage](qimage.html) and [QColor](qcolor.html) |
| [Qt.DisplayRole](qt.html#ItemDataRole-enum) | [QString](qstring.html) and types with a string representation |
| [Qt.EditRole](qt.html#ItemDataRole-enum) | See [QItemEditorFactory](qitemeditorfactory.html) for details |
| [Qt.FontRole](qt.html#ItemDataRole-enum) | [QFont](qfont.html) |
| [Qt.SizeHintRole](qt.html#ItemDataRole-enum) | [QSize](qsize.html) |
| [Qt.TextAlignmentRole](qt.html#ItemDataRole-enum) | [Qt.Alignment](qt.html#AlignmentFlag-enum) |
| [Qt.ForegroundRole](qt.html#ItemDataRole-enum) | [QBrush](qbrush.html) |
| [Qt.TextColorRole](qt.html#ItemDataRole-enum) | [QColor](qcolor.html) (obsolete; use [Qt.ForegroundRole](qt.html#ItemDataRole-enum) instead) |

编辑器都具有创建[QItemEditorFactory](qitemeditorfactory.html);通过提供一个默认的静态实例[QItemEditorFactory](qitemeditorfactory.html)安装在所有项目的代表。您可以使用设置一个自定义的工厂[setItemEditorFactory](qstyleditemdelegate.html#setItemEditorFactory)（ ）或设置新的默认出厂带[QItemEditorFactory.setDefaultFactory](qitemeditorfactory.html#setDefaultFactory)（ ） 。它是存储在项目模型与数据[EditRole](qt.html#ItemDataRole-enum)被编辑。请参阅[QItemEditorFactory](qitemeditorfactory.html)类为更高层的介绍项目编辑器的工厂。该[Color Editor Factory](index.htm)示例显示了如何创建自定义编辑器的工厂。

### Subclassing QStyledItemDelegate

如果代理不支持绘画你需要的数据类型，或者您要自定义项目的图纸，你需要继承QStyledItemDelegate ，并重新实现[paint](qstyleditemdelegate.html#paint)（ ）和可能[sizeHint](qstyleditemdelegate.html#sizeHint)（ ） 。该[paint](qstyleditemdelegate.html#paint)（）函数被单独地调用的每个项目，并与[sizeHint](qstyleditemdelegate.html#sizeHint)（ ） ，您可以为每个人指定的提示。

当重新实现[paint](qstyleditemdelegate.html#paint)（ ） ，人们通常会处理的数据类型一想绘制和使用超类实现其他类型。

的复选框指标的绘画是由当前样式进行。样式还指定了大小和边界矩形在其中绘制的数据不同的数据的作用。项目本身的边框也被计算的风格。当图纸已经支持的数据类型，因此它是一个好主意，要求风格这些边界矩形。该[QStyle](qstyle.html)类的描述更详细地描述这一点。

如果你想改变任何通过复选框指标的样式或绘画计算的边界矩形的，你可以继承[QStyle](qstyle.html)。但是请注意，这些项的大小也可以受到重新实现[sizeHint](qstyleditemdelegate.html#sizeHint)（ ） 。

这是可能的自定义委讬来提供编辑器，无需使用一个编辑器项目工厂。在这种情况下，下面的虚函数必须被重新实现：

*   [createEditor](qstyleditemdelegate.html#createEditor)() returns the widget used to change data from the model and can be reimplemented to customize editing behavior.
*   [setEditorData](qstyleditemdelegate.html#setEditorData)() provides the widget with data to manipulate.
*   [updateEditorGeometry](qstyleditemdelegate.html#updateEditorGeometry)() ensures that the editor is displayed correctly with respect to the item view.
*   [setModelData](qstyleditemdelegate.html#setModelData)() returns updated data to the model.

该[Star Delegate](index.htm)例如，通过重新实现这些方法创建编辑器。

### QStyledItemDelegate vs. QItemDelegate

由于Qt的4.4 ，有两个委讬类：[QItemDelegate](qitemdelegate.html)和QStyledItemDelegate 。不过，默认的委讬是QStyledItemDelegate 。这两个类是独立的替代品来画，并提供编辑器的项目中的观点。它们之间的区别在于QStyledItemDelegate使用当前样式来绘制它的项目。因此，我们建议实现自定义委讬或与Qt样式表工作时，在使用QStyledItemDelegate作为基类。需要的不是类的代码应该是平等的，除非自定义委讬需要使用的样式绘制。

如果你想自定义的项目意见的画，你应该实现一个自定义样式。请参阅[QStyle](qstyle.html)类文档。

* * *

## Method Documentation

```
QStyledItemDelegate.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个项目委讬给定的_parent_。

```
QWidget QStyledItemDelegate.createEditor (self, QWidget parent, QStyleOptionViewItem option, QModelIndex index)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qwidget.html)

[从重新实现](qwidget.html)[QAbstractItemDelegate.createEditor](qabstractitemdelegate.html#createEditor)（ ） 。

返回用于编辑由指定的项目小组件_index_进行编辑。该_parent_小工具和风格_option_用于控制如何显示在编辑器部件。

**See also** [QAbstractItemDelegate.createEditor](qabstractitemdelegate.html#createEditor)（ ） 。

```
QString QStyledItemDelegate.displayText (self, QVariant value, QLocale locale)
```

该函数返回一个委讬将用于显示的字符串[Qt.DisplayRole](qt.html#ItemDataRole-enum)该模型中的_locale_。_value_是的价值[Qt.DisplayRole](qt.html#ItemDataRole-enum)提供的模型。

默认实现使用的QLocale.toString转换_value_成[QString](qstring.html)。

这个功能没有要求空模型指数，即指数的模型返回一个无效[QVariant](qvariant.html)。

**See also** [QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

```
bool QStyledItemDelegate.editorEvent (self, QEvent event, QAbstractItemModel model, QStyleOptionViewItem option, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.editorEvent](qabstractitemdelegate.html#editorEvent)（ ） 。

```
bool QStyledItemDelegate.eventFilter (self, QObject object, QEvent event)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

返回True如果给定的_editor_是一个有效的[QWidget](qwidget.html)和给定的_event_处理，否则返回False 。下面的按键事件在默认情况下的处理：

*   **Tab**
*   **Backtab**
*   **Enter**
*   **Return**
*   **Esc**

在的情况下**Tab**，**Backtab**，**Enter**和**Return**按键事件，_editor_的数据被COMITTED到模型和编辑器被关闭。如果_event_是**Tab**按键的视图将在视图上的下一个项目打开一个编辑器。同样地，如果_event_是**Backtab**按键视图将在打开一个编辑器_previous_在视图中的项目。

如果该事件是**Esc**按键事件时，_editor_关闭_without_提交其数据。

**See also** [commitData](qabstractitemdelegate.html#commitData)（）和[closeEditor](qabstractitemdelegate.html#closeEditor)（ ） 。

```
QStyledItemDelegate.initStyleOption (self, QStyleOptionViewItem option, QModelIndex index)
```

初始化_option_与使用索引值_index_。当他们需要一个这种方法是有用的子类[QStyleOptionViewItem](qstyleoptionviewitem.html)，但不希望在所有的信息填写自己。此功能将检查的版本[QStyleOptionViewItem](qstyleoptionviewitem.html)并填写了附加价值[QStyleOptionViewItemV2](qstyleoptionviewitemv2.html)，[QStyleOptionViewItemV3](qstyleoptionviewitemv3.html)和[QStyleOptionViewItemV4](qstyleoptionviewitemv4.html)。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QItemEditorFactory QStyledItemDelegate.itemEditorFactory (self)
```

[

返回使用的项目委讬编辑工厂。如果没有编辑器出厂设置，该函数将返回null 。

](qitemeditorfactory.html)

[**See also**](qitemeditorfactory.html) [setItemEditorFactory](qstyleditemdelegate.html#setItemEditorFactory)（ ） 。

```
QStyledItemDelegate.paint (self, QPainter painter, QStyleOptionViewItem option, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.paint](qabstractitemdelegate.html#paint)（ ） 。

使用给定的呈现委讬_painter_和风格_option_由指定的项目_index_。

使用视图的此功能涂料项目[QStyle](qstyle.html)。

当在子类中重新实现的油漆。使用[initStyleOption](qstyleditemdelegate.html#initStyleOption)（ ）来设置_option_以同样的方式作为[QStyledItemDelegate](qstyleditemdelegate.html);该选项将始终是一个实例[QStyleOptionViewItemV4](qstyleoptionviewitemv4.html)。请参阅其类描述其内容的信息。

只要有可能，使用_option_而画。尤其是其[rect](qstyleoption.html#rect-var)变量来决定在哪里绘制和其[state](qstyleoption.html#state-var)以确定它是否被启用或选定。

喷漆后，您应确保画家返回到其它时，这个函数被调用的供给状态。例如，它可能是有用的呼叫[QPainter.save](qpainter.html#save)（ ）之前，绘画和[QPainter.restore](qpainter.html#restore)（ ）之后。

**See also** [QItemDelegate.paint](qitemdelegate.html#paint)（ ）[QStyle.drawControl](qstyle.html#drawControl)（）和[QStyle.CE_ItemViewItem](qstyle.html#ControlElement-enum)。

```
QStyledItemDelegate.setEditorData (self, QWidget editor, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.setEditorData](qabstractitemdelegate.html#setEditorData)（ ） 。

设置由显示和编辑数据_editor_从模型中指定的数据模型项目_index_。

默认实现存储在数据_editor_widget的[user property](index.htm#qt-s-property-system)。

**See also** [QMetaProperty.isUser](qmetaproperty.html#isUser)（ ） 。

```
QStyledItemDelegate.setItemEditorFactory (self, QItemEditorFactory factory)
```

设置编辑工厂中使用的项目的委讬是_factory_规定。如果没有编辑器出厂设置，该项目代表将使用默认编辑器工厂。

**See also** [itemEditorFactory](qstyleditemdelegate.html#itemEditorFactory)（ ） 。

```
QStyledItemDelegate.setModelData (self, QWidget editor, QAbstractItemModel model, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.setModelData](qabstractitemdelegate.html#setModelData)（ ） 。

获取数据从_editor_插件和将其存储在指定的_model_在项目_index_。

默认实现得到的值也可以从存储在数据模型_editor_widget的[user property](index.htm#qt-s-property-system)。

**See also** [QMetaProperty.isUser](qmetaproperty.html#isUser)（ ） 。

```
QSize QStyledItemDelegate.sizeHint (self, QStyleOptionViewItem option, QModelIndex index)
```

[](qsize.html)

[从重新实现](qsize.html)[QAbstractItemDelegate.sizeHint](qabstractitemdelegate.html#sizeHint)（ ） 。

返回显示由指定的项目需要由委讬的大小_index_考虑到所提供的样式信息_option_。

该函数使用视图的[QStyle](qstyle.html)以确定该项目的大小。

**See also** [QStyle.sizeFromContents](qstyle.html#sizeFromContents)（）和[QStyle.CT_ItemViewItem](qstyle.html#ContentsType-enum)。

```
QStyledItemDelegate.updateEditorGeometry (self, QWidget editor, QStyleOptionViewItem option, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.updateEditorGeometry](qabstractitemdelegate.html#updateEditorGeometry)（ ） 。

更新_editor_由指定的项目_index_根据风格_option_给出。