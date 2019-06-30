# QItemDelegate Class Reference

## [[QtGui](index.htm) module]

该QItemDelegate类提供了从模型中的数据项的显示和编辑功能。[More...](#details)

继承[QAbstractItemDelegate](qabstractitemdelegate.html)。

通过继承[QSqlRelationalDelegate](qsqlrelationaldelegate.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QWidget createEditor (self, QWidget parent, QStyleOptionViewItem option, QModelIndex index)`
*   `drawBackground (self, QPainter painter, QStyleOptionViewItem option, QModelIndex index)`
*   `drawCheck (self, QPainter painter, QStyleOptionViewItem option, QRect rect, Qt.CheckState state)`
*   `drawDecoration (self, QPainter painter, QStyleOptionViewItem option, QRect rect, QPixmap pixmap)`
*   `drawDisplay (self, QPainter painter, QStyleOptionViewItem option, QRect rect, QString text)`
*   `drawFocus (self, QPainter painter, QStyleOptionViewItem option, QRect rect)`
*   `bool editorEvent (self, QEvent event, QAbstractItemModel model, QStyleOptionViewItem option, QModelIndex index)`
*   `bool eventFilter (self, QObject object, QEvent event)`
*   `bool hasClipping (self)`
*   `QItemEditorFactory itemEditorFactory (self)`
*   `paint (self, QPainter painter, QStyleOptionViewItem option, QModelIndex index)`
*   `setClipping (self, bool clip)`
*   `setEditorData (self, QWidget editor, QModelIndex index)`
*   `setItemEditorFactory (self, QItemEditorFactory factory)`
*   `setModelData (self, QWidget editor, QAbstractItemModel model, QModelIndex index)`
*   `QSize sizeHint (self, QStyleOptionViewItem option, QModelIndex index)`
*   `updateEditorGeometry (self, QWidget editor, QStyleOptionViewItem option, QModelIndex index)`

* * *

## Detailed Description

该QItemDelegate类提供了从模型中的数据项的显示和编辑功能。

QItemDelegate可用于基于项目视图提供了自定义显示功能和编辑器部件[QAbstractItemView](qabstractitemview.html)子类。使用委讬为此目的允许显示和编辑机制，从模型和视图定制和自主开发。

该QItemDelegate类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。需要注意的是[QStyledItemDelegate](qstyleditemdelegate.html)接管绘制Qt的项目视图的工作。我们建议使用[QStyledItemDelegate](qstyleditemdelegate.html)创建新的委讬时。

当从一个标准视图自定义模型显示的项目，它往往是足够简单地确保模型返回相应的数据为每个[roles](qt.html#ItemDataRole-enum)确定项目的视图的外观。使用Qt的标准视图中的默认代理使用这个角色信息中的大部分预期用户的常见形式显示项目。然而，有时需要有更多的控制比默认代理可以提供物品的外观。

这个类提供了用于从项目模型视图和编辑数据的绘画项目数据的功能默认实现。的默认实现[paint](qitemdelegate.html#paint)（）和[sizeHint](qitemdelegate.html#sizeHint)（ ）虚函数，定义[QAbstractItemDelegate](qabstractitemdelegate.html)，提供了确保委讬实现了预期的看法正确的基本行为。您可以在子类中重新实现这些功能可以自定义项的外观。

当一个项目视图中编辑数据， QItemDelegate提供了一个编辑器部件，这是放置在视图的顶部编辑时发生的一个小部件。编辑器都具有创建[QItemEditorFactory](qitemeditorfactory.html);通过提供一个默认的静态实例[QItemEditorFactory](qitemeditorfactory.html)安装在所有项目的代表。您可以使用设置一个自定义的工厂[setItemEditorFactory](qitemdelegate.html#setItemEditorFactory)（ ）或设置新的默认出厂带[QItemEditorFactory.setDefaultFactory](qitemeditorfactory.html#setDefaultFactory)（ ） 。它是存储在项目模型与数据[Qt.EditRole](qt.html#ItemDataRole-enum)被编辑。

仅适用于部件为基础的代表的标准编辑功能都在这里重新实现：

*   [createEditor](qitemdelegate.html#createEditor)() returns the widget used to change data from the model and can be reimplemented to customize editing behavior.
*   [setEditorData](qitemdelegate.html#setEditorData)() provides the widget with data to manipulate.
*   [updateEditorGeometry](qitemdelegate.html#updateEditorGeometry)() ensures that the editor is displayed correctly with respect to the item view.
*   [setModelData](qitemdelegate.html#setModelData)() returns updated data to the model.

该[closeEditor](qabstractitemdelegate.html#closeEditor)（）信号表明用户已经完成了编辑数据，并且该编辑器部件可以被摧毁。

### Standard Roles and Data Types

通过使用Qt提供的标准视图中的默认代理将每个标准角色（定义为[Qt.ItemDataRole](qt.html#ItemDataRole-enum)）与某些数据类型。模型返回的数据在这些类型可以影响代表的，如下表中所述的外观。

| Role | Accepted Types |
| --- | --- |
| [Qt.BackgroundRole](qt.html#ItemDataRole-enum) | [QBrush](qbrush.html) |
| [Qt.BackgroundColorRole](qt.html#ItemDataRole-enum) | [QColor](qcolor.html) (obsolete; use [Qt.BackgroundRole](qt.html#ItemDataRole-enum) instead) |
| [Qt.CheckStateRole](qt.html#ItemDataRole-enum) | [Qt.CheckState](qt.html#CheckState-enum) |
| [Qt.DecorationRole](qt.html#ItemDataRole-enum) | [QIcon](qicon.html), [QPixmap](qpixmap.html) and [QColor](qcolor.html) |
| [Qt.DisplayRole](qt.html#ItemDataRole-enum) | [QString](qstring.html) and types with a string representation |
| [Qt.EditRole](qt.html#ItemDataRole-enum) | See [QItemEditorFactory](qitemeditorfactory.html) for details |
| [Qt.FontRole](qt.html#ItemDataRole-enum) | [QFont](qfont.html) |
| [Qt.SizeHintRole](qt.html#ItemDataRole-enum) | [QSize](qsize.html) |
| [Qt.TextAlignmentRole](qt.html#ItemDataRole-enum) | [Qt.Alignment](qt.html#AlignmentFlag-enum) |
| [Qt.ForegroundRole](qt.html#ItemDataRole-enum) | [QBrush](qbrush.html) |
| [Qt.TextColorRole](qt.html#ItemDataRole-enum) | [QColor](qcolor.html) (obsolete; use [Qt.ForegroundRole](qt.html#ItemDataRole-enum) instead) |

如果默认的委讬不允许你需要的定制化水平，无论是用于显示目的或编辑数据，就可以继承QItemDelegate实施所需的行为。

### Subclassing

当子类QItemDelegate创建一个使用自定义渲染器显示的项目委讬，重要的是要确保委讬可以适当渲染项目所需的所有国家;如选择禁用，检查。该文档为[paint](qitemdelegate.html#paint)（ ）函数包含一些提示，说明如何可以做到这一点。

您可以通过使用一个提供自定义编辑器[QItemEditorFactory](qitemeditorfactory.html)。该[Color Editor Factory Example](index.htm)展示了如何自定义编辑器，可以提供给与会代表使用默认项目编辑器的工厂。这样一来，就没有必要向子类QItemDelegate 。另一种方法是重新实现[createEditor](qitemdelegate.html#createEditor)（ ）[setEditorData](qitemdelegate.html#setEditorData)（ ）[setModelData](qitemdelegate.html#setModelData)（）和[updateEditorGeometry](qitemdelegate.html#updateEditorGeometry)（ ） 。这个过程是在所描述的[Spin Box Delegate Example](index.htm)。

### QStyledItemDelegate vs. QItemDelegate

由于Qt的4.4 ，有两个委讬类： QItemDelegate和[QStyledItemDelegate](qstyleditemdelegate.html)。不过，默认的委讬是[QStyledItemDelegate](qstyleditemdelegate.html)。这两个类是独立的替代品来画，并提供编辑器的项目中的观点。它们之间的不同之处在于[QStyledItemDelegate](qstyleditemdelegate.html)使用当前的样式来绘制它的项目。因此，我们建议您使用[QStyledItemDelegate](qstyleditemdelegate.html)作为基类实现自定义委讬或与Qt样式表时，工作时。需要的不是类的代码应该是平等的，除非自定义委讬需要使用的样式绘制。

* * *

## Method Documentation

```
QItemDelegate.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个项目委讬给定的_parent_。

```
QWidget QItemDelegate.createEditor (self, QWidget parent, QStyleOptionViewItem option, QModelIndex index)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qwidget.html)

[从重新实现](qwidget.html)[QAbstractItemDelegate.createEditor](qabstractitemdelegate.html#createEditor)（ ） 。

返回用于编辑由指定的项目小组件_index_进行编辑。该_parent_小工具和风格_option_用于控制如何显示在编辑器部件。

**See also** [QAbstractItemDelegate.createEditor](qabstractitemdelegate.html#createEditor)（ ） 。

```
QItemDelegate.drawBackground (self, QPainter painter, QStyleOptionViewItem option, QModelIndex index)
```

呈现项目背景为给定的_index_，使用给定的_painter_和风格_option_。

这个函数中引入了Qt 4.2中。

```
QItemDelegate.drawCheck (self, QPainter painter, QStyleOptionViewItem option, QRect rect, Qt.CheckState state)
```

呈现由指定的矩形内的检查指标_rect_，使用给定的_painter_和风格_option_，使用给定的_state_。

```
QItemDelegate.drawDecoration (self, QPainter painter, QStyleOptionViewItem option, QRect rect, QPixmap pixmap)
```

渲染装饰_pixmap_由指定的矩形内_rect_使用给定的_painter_和风格_option_。

```
QItemDelegate.drawDisplay (self, QPainter painter, QStyleOptionViewItem option, QRect rect, QString text)
```

呈现项目视图_text_由指定的矩形内_rect_使用给定的_painter_和风格_option_。

```
QItemDelegate.drawFocus (self, QPainter painter, QStyleOptionViewItem option, QRect rect)
```

呈现由指定的矩形区域内的_rect_，这表明它具有焦点，使用给定的_painter_和风格_option_。

```
bool QItemDelegate.editorEvent (self, QEvent event, QAbstractItemModel model, QStyleOptionViewItem option, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.editorEvent](qabstractitemdelegate.html#editorEvent)（ ） 。

```
bool QItemDelegate.eventFilter (self, QObject object, QEvent event)
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
bool QItemDelegate.hasClipping (self)
```

```
QItemEditorFactory QItemDelegate.itemEditorFactory (self)
```

[

返回使用的项目委讬编辑工厂。如果没有编辑器出厂设置，该函数将返回null 。

](qitemeditorfactory.html)

[**See also**](qitemeditorfactory.html) [setItemEditorFactory](qitemdelegate.html#setItemEditorFactory)（ ） 。

```
QItemDelegate.paint (self, QPainter painter, QStyleOptionViewItem option, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.paint](qabstractitemdelegate.html#paint)（ ） 。

使用给定的呈现委讬_painter_和风格_option_由指定的项目_index_。

当重新实现在子类中这个功能，你应该更新的选项持的区域[rect](qstyleoption.html#rect-var)变量，使用选项的[state](qstyleoption.html#state-var)变量来确定要显示的项的状态，并调整其相应绘的方式。

例如，所选择的项目，可能需要不同地未被选择的项目显示，如显示在下面的代码：

```
     if (option.state & [QStyle](qstyle.html).State_Selected)
         painter->fillRect(option.rect, option.palette.highlight());

     int size = qMin(option.rect.width(), option.rect.height());
     int brightness = index.model()->data(index, [Qt](qt.html).DisplayRole).toInt();
     double radius = (size/2.0) - (brightness/255.0 * size/2.0);
     if (radius == 0.0)
         return;

     painter->save();
     painter->setRenderHint([QPainter](qpainter.html).Antialiasing, true);
     painter->setPen([Qt](qt.html).NoPen);
     if (option.state & [QStyle](qstyle.html).State_Selected)
         painter->setBrush(option.palette.highlightedText());
     else
     ...

```

喷漆后，您应确保画家返回到其它时，这个函数被调用的供给状态。例如，它可能是有用的呼叫[QPainter.save](qpainter.html#save)（ ）之前，绘画和[QPainter.restore](qpainter.html#restore)（ ）之后。

**See also** [QStyle.State](qstyle.html#StateFlag-enum)。

```
QItemDelegate.setClipping (self, bool clip)
```

```
QItemDelegate.setEditorData (self, QWidget editor, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.setEditorData](qabstractitemdelegate.html#setEditorData)（ ） 。

设置由显示和编辑数据_editor_从模型中指定的数据模型项目_index_。

默认实现存储在数据_editor_widget的[user property](index.htm#qt-s-property-system)。

**See also** [QMetaProperty.isUser](qmetaproperty.html#isUser)（ ） 。

```
QItemDelegate.setItemEditorFactory (self, QItemEditorFactory factory)
```

设置编辑工厂中使用的项目的委讬是_factory_规定。如果没有编辑器出厂设置，该项目代表将使用默认编辑器工厂。

**See also** [itemEditorFactory](qitemdelegate.html#itemEditorFactory)（ ） 。

```
QItemDelegate.setModelData (self, QWidget editor, QAbstractItemModel model, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.setModelData](qabstractitemdelegate.html#setModelData)（ ） 。

获取数据从_editor_插件和将其存储在指定的_model_在项目_index_。

默认实现得到的值也可以从存储在数据模型_editor_widget的[user property](index.htm#qt-s-property-system)。

**See also** [QMetaProperty.isUser](qmetaproperty.html#isUser)（ ） 。

```
QSize QItemDelegate.sizeHint (self, QStyleOptionViewItem option, QModelIndex index)
```

[](qsize.html)

[从重新实现](qsize.html)[QAbstractItemDelegate.sizeHint](qabstractitemdelegate.html#sizeHint)（ ） 。

返回显示由指定的项目需要由委讬的大小_index_考虑到所提供的样式信息_option_。

当重新实现此功能，请注意，在案件的文本项，[QItemDelegate](qitemdelegate.html)增加了利润率（即2 *[QStyle.PM_FocusFrameHMargin](qstyle.html#PixelMetric-enum)）以文本的长度。

```
QItemDelegate.updateEditorGeometry (self, QWidget editor, QStyleOptionViewItem option, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.updateEditorGeometry](qabstractitemdelegate.html#updateEditorGeometry)（ ） 。

更新_editor_由指定的项目_index_根据风格_option_给出。