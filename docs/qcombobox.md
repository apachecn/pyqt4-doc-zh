# QComboBox Class Reference

## [[QtGui](index.htm) module]

该QComboBox表示widget是一个组合键，弹出的列表中。[More...](#details)

继承[QWidget](qwidget.html)。

通过继承[QFontComboBox](qfontcombobox.html)。

### Types

*   `enum InsertPolicy { NoInsert, InsertAtTop, InsertAtCurrent, InsertAtBottom, ..., InsertAlphabetically }`
*   `enum SizeAdjustPolicy { AdjustToContents, AdjustToContentsOnFirstShow, AdjustToMinimumContentsLength, AdjustToMinimumContentsLengthWithIcon }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `addItem (self, QString text, QVariant userData = QVariant())`
*   `addItem (self, QIcon icon, QString text, QVariant userData = QVariant())`
*   `addItems (self, QStringList texts)`
*   `bool autoCompletion (self)`
*   `Qt.CaseSensitivity autoCompletionCaseSensitivity (self)`
*   `changeEvent (self, QEvent e)`
*   `clear (self)`
*   `clearEditText (self)`
*   `QCompleter completer (self)`
*   `contextMenuEvent (self, QContextMenuEvent e)`
*   `int count (self)`
*   `int currentIndex (self)`
*   `QString currentText (self)`
*   `bool duplicatesEnabled (self)`
*   `bool event (self, QEvent event)`
*   `int findData (self, QVariant data, int role = Qt.UserRole, Qt.MatchFlags flags = Qt.MatchExactly|Qt.MatchCaseSensitive)`
*   `int findText (self, QString text, Qt.MatchFlags flags = Qt.MatchExactly|Qt.MatchCaseSensitive)`
*   `focusInEvent (self, QFocusEvent e)`
*   `focusOutEvent (self, QFocusEvent e)`
*   `bool hasFrame (self)`
*   `hideEvent (self, QHideEvent e)`
*   `hidePopup (self)`
*   `QSize iconSize (self)`
*   `initStyleOption (self, QStyleOptionComboBox option)`
*   `inputMethodEvent (self, QInputMethodEvent)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery)`
*   `insertItem (self, int index, QString text, QVariant userData = QVariant())`
*   `insertItem (self, int index, QIcon icon, QString text, QVariant userData = QVariant())`
*   `insertItems (self, int index, QStringList texts)`
*   `InsertPolicy insertPolicy (self)`
*   `insertSeparator (self, int index)`
*   `bool isEditable (self)`
*   `QVariant itemData (self, int index, int role = Qt.UserRole)`
*   `QAbstractItemDelegate itemDelegate (self)`
*   `QIcon itemIcon (self, int index)`
*   `QString itemText (self, int index)`
*   `keyPressEvent (self, QKeyEvent e)`
*   `keyReleaseEvent (self, QKeyEvent e)`
*   `QLineEdit lineEdit (self)`
*   `int maxCount (self)`
*   `int maxVisibleItems (self)`
*   `int minimumContentsLength (self)`
*   `QSize minimumSizeHint (self)`
*   `QAbstractItemModel model (self)`
*   `int modelColumn (self)`
*   `mousePressEvent (self, QMouseEvent e)`
*   `mouseReleaseEvent (self, QMouseEvent e)`
*   `paintEvent (self, QPaintEvent e)`
*   `removeItem (self, int index)`
*   `resizeEvent (self, QResizeEvent e)`
*   `QModelIndex rootModelIndex (self)`
*   `setAutoCompletion (self, bool enable)`
*   `setAutoCompletionCaseSensitivity (self, Qt.CaseSensitivity sensitivity)`
*   `setCompleter (self, QCompleter c)`
*   `setCurrentIndex (self, int index)`
*   `setDuplicatesEnabled (self, bool enable)`
*   `setEditable (self, bool editable)`
*   `setEditText (self, QString text)`
*   `setFrame (self, bool)`
*   `setIconSize (self, QSize size)`
*   `setInsertPolicy (self, InsertPolicy policy)`
*   `setItemData (self, int index, QVariant value, int role = Qt.UserRole)`
*   `setItemDelegate (self, QAbstractItemDelegate delegate)`
*   `setItemIcon (self, int index, QIcon icon)`
*   `setItemText (self, int index, QString text)`
*   `setLineEdit (self, QLineEdit edit)`
*   `setMaxCount (self, int max)`
*   `setMaxVisibleItems (self, int maxItems)`
*   `setMinimumContentsLength (self, int characters)`
*   `setModel (self, QAbstractItemModel model)`
*   `setModelColumn (self, int visibleColumn)`
*   `setRootModelIndex (self, QModelIndex index)`
*   `setSizeAdjustPolicy (self, SizeAdjustPolicy policy)`
*   `setValidator (self, QValidator v)`
*   `setView (self, QAbstractItemView itemView)`
*   `showEvent (self, QShowEvent e)`
*   `showPopup (self)`
*   `SizeAdjustPolicy sizeAdjustPolicy (self)`
*   `QSize sizeHint (self)`
*   `QValidator validator (self)`
*   `QAbstractItemView view (self)`
*   `wheelEvent (self, QWheelEvent e)`

### Special Methods

*   `__len__ (self)`

### Qt Signals

*   `void activated (int)`
*   `void activated (const QString&)`
*   `void currentIndexChanged (int)`
*   `void currentIndexChanged (const QString&)`
*   `void editTextChanged (const QString&)`
*   `void highlighted (int)`
*   `void highlighted (const QString&)`

* * *

## Detailed Description

该QComboBox表示widget是一个组合键，弹出的列表中。

一个QComboBox表示提供了展示的选项列表给用户的方式，佔用屏幕空间的最小量的一种手段。

组合框是一个选择窗口小部件，显示当前的项目，可以弹出的选项列表。一个ComboBox可编辑，允许用户修改列表中的每个项目。

组合框可以包含的像素图和字符串;的[insertItem](qcombobox.html#insertItem)（）和[setItemText](qcombobox.html#setItemText)（ ）函数进行适当超载。对于可编辑的组合框，该功能[clearEditText](qcombobox.html#clearEditText)（ ）设置，可清除显示的字符串，不改变组合框的内容。

还有，如果一个组合框改变目前的项目发出的两个信号，[currentIndexChanged](qcombobox.html#currentIndexChanged)（）和[activated](qcombobox.html#activated)（ ） 。[currentIndexChanged](qcombobox.html#currentIndexChanged)（ ）总是发出而不论这些变化以编程方式或通过用户交互来完成的，而[activated](qcombobox.html#activated)（）时的变化引起的用户交互只射出。该[highlighted](qcombobox.html#highlighted)当用户高亮显示在组合框弹出列表中的一项（ ）信号被发射。有两个版本，一个具有存在的所有三个信号[QString](qstring.html)参数和一个与`int`的说法。如果用户选择或突出显示一个像素图，只有`int`信号被发射。每当一个可编辑的组合框的文本改变了[editTextChanged](qcombobox.html#editTextChanged)（）信号被发射。

当用户进入可编辑ComboBox一个新的字符串，该部件可能会或可能不会插入它，它可以在多个位置插入。默认的策略是是[AtBottom](qcombobox.html#InsertPolicy-enum)但您可以使用此更改[setInsertPolicy](qcombobox.html#insertPolicy-prop)（ ） 。

这是可能使用的输入限制在一个可编辑的组合框[QValidator](qvalidator.html)见[setValidator](qcombobox.html#setValidator)（ ） 。默认情况下，任何输入被接受。

一个ComboBox可以使用插入功能来填充，[insertItem](qcombobox.html#insertItem)（）和[insertItems](qcombobox.html#insertItems)（ ）为例。项目可以被改变[setItemText](qcombobox.html#setItemText)（ ） 。一个项目可以被移除[removeItem](qcombobox.html#removeItem)（ ） ，所有项目可以被删除[clear](qcombobox.html#clear)（ ） 。当前项的文本被退回[currentText](qcombobox.html#currentText-prop)（ ） ，和一个编号项的文本与返回[text](index.htm#text)（ ） 。目前的项目可以设置[setCurrentIndex](qcombobox.html#currentIndex-prop)（ ） 。在组合框的项数是由返回[count](qcombobox.html#count-prop)（）;项目的最大数目可以被设置[setMaxCount](qcombobox.html#maxCount-prop)（ ） 。您可以使用允许编辑[setEditable](qcombobox.html#editable-prop)（ ） 。对于可编辑的组合框，您可以使用设置的自动完成功能[setCompleter](qcombobox.html#setCompleter)（用户）以及是否可以添加重复设置与[setDuplicatesEnabled](qcombobox.html#duplicatesEnabled-prop)（ ） 。

QComboBox表示使用[model/view framework](index.htm)其弹出的列表中，并存储其物品。默认情况下，[QStandardItemModel](qstandarditemmodel.html)存储的项目和一个[QListView](qlistview.html)子类显示popuplist 。您可以访问模型和视图直接（与[model](qcombobox.html#model)（）和[view](qcombobox.html#view)（ ） ），但QComboBox表示还提供了功能设置和获取项目数据（例如，[setItemData](qcombobox.html#setItemData)（）和[itemText](qcombobox.html#itemText)（））。您还可以设置一个新的模型和视图（带[setModel](qcombobox.html#setModel)（）和[setView](qcombobox.html#setView)（））。在组合框的标籤文本和图标，在具有该模型的数据[Qt.DisplayRole](qt.html#ItemDataRole-enum)和[Qt.DecorationRole](qt.html#ItemDataRole-enum)被使用。请注意，您不能更改[SelectionMode](qabstractitemview.html#SelectionMode-enum)的[view](qcombobox.html#view)（ ），例如，通过使用[setSelectionMode()](qabstractitemview.html#selectionMode-prop)。

![Comboboxes in the different built-in styles.](../img/qstyle-comboboxes.png)

* * *

## Type Documentation

```
QComboBox.InsertPolicy
```

此枚举指定什么[QComboBox](qcombobox.html)应该做的，当一个新的字符串是由用户输入。

| Constant | Value | Description |
| --- | --- | --- |
| `QComboBox.NoInsert` | `0` | 该字符串不会被插入到组合框。 |
| `QComboBox.InsertAtTop` | `1` | 该字符串将被插入在组合框中的第一项。 |
| `QComboBox.InsertAtCurrent` | `2` | 目前的项目将_replaced_由该字符串。 |
| `QComboBox.InsertAtBottom` | `3` | 该字符串将在ComboBox中的最后一个项目之后插入。 |
| `QComboBox.InsertAfterCurrent` | `4` | 该字符串中的组合框的当前项后插入。 |
| `QComboBox.InsertBeforeCurrent` | `5` | 该字符串中的组合框的当前项之前插入。 |
| `QComboBox.InsertAlphabetically` | `6` | 该字符串被插入在组合框中的字母顺序。 |

```
QComboBox.SizeAdjustPolicy
```

这个枚举指定的怎么尺寸暗示[QComboBox](qcombobox.html)应调整当新内容被添加或内容的变化。

| Constant | Value | Description |
| --- | --- | --- |
| `QComboBox.AdjustToContents` | `0` | 组合框会一直调整到内容 |
| `QComboBox.AdjustToContentsOnFirstShow` | `1` | 组合框将被调整到它的内容在第一次被示出。 |
| `QComboBox.AdjustToMinimumContentsLength` | `2` | 使用AdjustToContents或AdjustToContentsOnFirstShow代替。 |
| `QComboBox.AdjustToMinimumContentsLengthWithIcon` | `3` | 组合框将被调整到[minimumContentsLength](qcombobox.html#minimumContentsLength-prop)加上一个图标的空间。出于性能的考虑使用大型模型这一政策。 |

* * *

## Method Documentation

```
QComboBox.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个组合框与给定_parent_使用默认的模型[QStandardItemModel](qstandarditemmodel.html)。

```
QComboBox.addItem (self, QString text, QVariant userData = QVariant())
```

一个项添加到组合框与给定_text_，和包含指定_userData_（存储在[Qt.UserRole](qt.html#ItemDataRole-enum)） 。该项目被添加到现有的项目列表。

```
QComboBox.addItem (self, QIcon icon, QString text, QVariant userData = QVariant())
```

一个项添加到组合框与给定_icon_和_text_，和包含指定_userData_（存储在[Qt.UserRole](qt.html#ItemDataRole-enum)） 。该项目被添加到现有的项目列表。

```
QComboBox.addItems (self, QStringList texts)
```

把每个串中的给定_texts_到ComboBox 。每个项目会附加到反过来现有项目的清单。

```
bool QComboBox.autoCompletion (self)
```

```
Qt.CaseSensitivity QComboBox.autoCompletionCaseSensitivity (self)
```

[

```
QComboBox.changeEvent (self, QEvent e)
```

](qt.html#CaseSensitivity-enum)

[从重新实现](qt.html#CaseSensitivity-enum)[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QComboBox.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

清除组合框，删除所有项目。

注意：如果您已经在组合框中设置一个外部模型调用此功能时，此模式将仍然被清除。

```
QComboBox.clearEditText (self)
```

这种方法也是一个Qt槽与C + +的签名`void clearEditText()`。

清除用于编辑的组合框的行编辑的内容。

```
QCompleter QComboBox.completer (self)
```

[

返回用于自动完成文字输入的组合框的完成者。

这个函数中引入了Qt 4.2中。

](qcompleter.html)

[**See also**](qcompleter.html) [setCompleter](qcombobox.html#setCompleter)（）和[editable](qcombobox.html#editable-prop)。

```
QComboBox.contextMenuEvent (self, QContextMenuEvent e)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
int QComboBox.count (self)
```

```
int QComboBox.currentIndex (self)
```

```
QString QComboBox.currentText (self)
```

```
bool QComboBox.duplicatesEnabled (self)
```

```
bool QComboBox.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QComboBox.findData (self, QVariant data, int role = Qt.UserRole, Qt.MatchFlags flags = Qt.MatchExactly|Qt.MatchCaseSensitive)
```

返回该项目包含给定的索引_data_对于给定的_role_否则返回-1 。

该_flags_指定如何在ComboBox中的项目进行搜索。

```
int QComboBox.findText (self, QString text, Qt.MatchFlags flags = Qt.MatchExactly|Qt.MatchCaseSensitive)
```

返回该项目包含给定的索引_text_否则返回-1 。

该_flags_指定如何在ComboBox中的项目进行搜索。

```
QComboBox.focusInEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
QComboBox.focusOutEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
bool QComboBox.hasFrame (self)
```

```
QComboBox.hideEvent (self, QHideEvent e)
```

从重新实现[QWidget.hideEvent](qwidget.html#hideEvent)（ ） 。

```
QComboBox.hidePopup (self)
```

隐藏在组合框的项目列表，如果它是当前可见和复位内部状态，所以，如果自定义弹出被证明里面的重新实现[showPopup](qcombobox.html#showPopup)（ ） ，那么你还需要重新实现hidePopup （ ）函数来隐藏你的自定义弹出并调用基类的实现来复位内部状态时，您的自定义弹出窗口部件被隐藏。

**See also** [showPopup](qcombobox.html#showPopup)（ ） 。

```
QSize QComboBox.iconSize (self)
```

[

```
QComboBox.initStyleOption (self, QStyleOptionComboBox option)
```

](qsize.html)

[初始化_option_与其它的值](qsize.html)[QComboBox](qcombobox.html)。当他们需要一个这种方法是有用的子类[QStyleOptionComboBox](qstyleoptioncombobox.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QComboBox.inputMethodEvent (self, QInputMethodEvent)
```

从重新实现[QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（ ） 。

```
QVariant QComboBox.inputMethodQuery (self, Qt.InputMethodQuery)
```

从重新实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
QComboBox.insertItem (self, int index, QString text, QVariant userData = QVariant())
```

插入_text_和_userData_（存储在[Qt.UserRole](qt.html#ItemDataRole-enum)）到ComboBox在给定的_index_。

如果该指数等于或大于总项数越高，新项目被添加到现有的项目列表。如果该指数为零或负数，则新项目追加到现有的项目清单。

**See also** [insertItems](qcombobox.html#insertItems)（ ） 。

```
QComboBox.insertItem (self, int index, QIcon icon, QString text, QVariant userData = QVariant())
```

插入_icon_，_text_和_userData_（存储在[Qt.UserRole](qt.html#ItemDataRole-enum)）到ComboBox在给定的_index_。

如果该指数等于或大于总项数越高，新项目被添加到现有的项目列表。如果该指数为零或负数，则新项目追加到现有的项目清单。

**See also** [insertItems](qcombobox.html#insertItems)（ ） 。

```
QComboBox.insertItems (self, int index, QStringList texts)
```

从插入字符串_list_到ComboBox作为单独的项目，开始于_index_规定。

如果该指数等于或大于总项数越高，新项目被添加到现有的项目列表。如果该指数为零或负数，则新项目追加到现有的项目清单。

**See also** [insertItem](qcombobox.html#insertItem)（ ） 。

```
InsertPolicy QComboBox.insertPolicy (self)
```

[

```
QComboBox.insertSeparator (self, int index)
```

插入分隔项目到ComboBox在给定的_index_。

如果该指数等于或大于总项数越高，新项目被添加到现有的项目列表。如果该指数为零或负数，则新项目追加到现有的项目清单。

此功能被引入Qt的4.4 。

](qcombobox.html#InsertPolicy-enum)

[**See also**](qcombobox.html#InsertPolicy-enum) [insertItem](qcombobox.html#insertItem)（ ） 。

```
bool QComboBox.isEditable (self)
```

```
QVariant QComboBox.itemData (self, int index, int role = Qt.UserRole)
```

返回数据为给定的_role_在给定的_index_在组合框，或[QVariant.Invalid](qvariant.html#Type-enum)如果没有数据，这个作用。

**See also** [setItemData](qcombobox.html#setItemData)（ ） 。

```
QAbstractItemDelegate QComboBox.itemDelegate (self)
```

[

返回所使用的弹出列表视图中的项目委讬。

](qabstractitemdelegate.html)

[**See also**](qabstractitemdelegate.html) [setItemDelegate](qcombobox.html#setItemDelegate)（ ） 。

```
QIcon QComboBox.itemIcon (self, int index)
```

[

返回图标为给定的_index_在组合框。

](qicon.html)

[**See also**](qicon.html) [setItemIcon](qcombobox.html#setItemIcon)（ ） 。

```
QString QComboBox.itemText (self, int index)
```

返回文本为给定的_index_在组合框。

**See also** [setItemText](qcombobox.html#setItemText)（ ） 。

```
QComboBox.keyPressEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QComboBox.keyReleaseEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ） 。

```
QLineEdit QComboBox.lineEdit (self)
```

[

返回用于在组合框，或0编辑项目，如果没有行编辑的行编辑。

唯一可编辑的组合框有一个行编辑。

](qlineedit.html)

[**See also**](qlineedit.html) [setLineEdit](qcombobox.html#setLineEdit)（ ） 。

```
int QComboBox.maxCount (self)
```

```
int QComboBox.maxVisibleItems (self)
```

```
int QComboBox.minimumContentsLength (self)
```

```
QSize QComboBox.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QAbstractItemModel QComboBox.model (self)
```

[

返回所使用的组合框模型。

](qabstractitemmodel.html)

[**See also**](qabstractitemmodel.html) [setModel](qcombobox.html#setModel)（ ） 。

```
int QComboBox.modelColumn (self)
```

```
QComboBox.mousePressEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QComboBox.mouseReleaseEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QComboBox.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QComboBox.removeItem (self, int index)
```

删除给定的项目_index_从组合框。如果索引中删除这将更新当前的索引。

这个函数做什么，如果_index_超出范围。

```
QComboBox.resizeEvent (self, QResizeEvent e)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QModelIndex QComboBox.rootModelIndex (self)
```

[

返回根模型项目指数在ComboBox中的项目。

](qmodelindex.html)

[**See also**](qmodelindex.html) [setRootModelIndex](qcombobox.html#setRootModelIndex)（ ） 。

```
QComboBox.setAutoCompletion (self, bool enable)
```

```
QComboBox.setAutoCompletionCaseSensitivity (self, Qt.CaseSensitivity sensitivity)
```

```
QComboBox.setCompleter (self, QCompleter c)
```

设置_completer_使用而不是目前的完成者的。如果_completer_为0 ，自动完成被禁用。

默认情况下，一个可编辑的组合框，一个[QCompleter](qcompleter.html)执行不区分大小写的直列完成自动创建。

这个函数中引入了Qt 4.2中。

**See also** [completer](qcombobox.html#completer)（ ） 。

```
QComboBox.setCurrentIndex (self, int index)
```

```
QComboBox.setDuplicatesEnabled (self, bool enable)
```

```
QComboBox.setEditable (self, bool editable)
```

```
QComboBox.setEditText (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void setEditText(const QString&)`。

设置_text_在组合框的文本编辑。

```
QComboBox.setFrame (self, bool)
```

```
QComboBox.setIconSize (self, QSize size)
```

```
QComboBox.setInsertPolicy (self, InsertPolicy policy)
```

```
QComboBox.setItemData (self, int index, QVariant value, int role = Qt.UserRole)
```

设置数据_role_在给定的产品_index_在组合框来指定_value_。

**See also** [itemData](qcombobox.html#itemData)（ ） 。

```
QComboBox.setItemDelegate (self, QAbstractItemDelegate delegate)
```

设置项_delegate_在弹出的列表视图。组合框采用委讬的所有权。

**Warning:**你不应该共享组合框，控件映射程序或视图之间的委讬的同一实例。否则会导致不正确或不直观的编辑行为，因为在一个给定的委讬每个视图可能会收到[closeEditor()](qabstractitemdelegate.html#closeEditor)信号，并试图访问，修改或关闭一个已经被关闭的编辑器。

**See also** [itemDelegate](qcombobox.html#itemDelegate)（ ） 。

```
QComboBox.setItemIcon (self, int index, QIcon icon)
```

设置_icon_在给定的产品_index_在组合框。

**See also** [itemIcon](qcombobox.html#itemIcon)（ ） 。

```
QComboBox.setItemText (self, int index, QString text)
```

设置_text_在给定的产品_index_在组合框。

**See also** [itemText](qcombobox.html#itemText)（ ） 。

```
QComboBox.setLineEdit (self, QLineEdit edit)
```

该_edit_说法有它的所有权转移给Qt的。

设置行_edit_使用而不是目前的行编辑widget的。

组合框取行编辑的所有权。

**See also** [lineEdit](qcombobox.html#lineEdit)（ ） 。

```
QComboBox.setMaxCount (self, int max)
```

```
QComboBox.setMaxVisibleItems (self, int maxItems)
```

```
QComboBox.setMinimumContentsLength (self, int characters)
```

```
QComboBox.setModel (self, QAbstractItemModel model)
```

设置模型是_model_。_model_不能为0 。如果你想清除一个模型的内容，请致电[clear](qcombobox.html#clear)（ ） 。

**See also** [model](qcombobox.html#model)（）和[clear](qcombobox.html#clear)（ ） 。

```
QComboBox.setModelColumn (self, int visibleColumn)
```

```
QComboBox.setRootModelIndex (self, QModelIndex index)
```

设置根模型项目_index_在ComboBox中的项目。

**See also** [rootModelIndex](qcombobox.html#rootModelIndex)（ ） 。

```
QComboBox.setSizeAdjustPolicy (self, SizeAdjustPolicy policy)
```

```
QComboBox.setValidator (self, QValidator v)
```

设置_validator_使用而不是目前的验证器。

**See also** [validator](qcombobox.html#validator)（ ） 。

```
QComboBox.setView (self, QAbstractItemView itemView)
```

该_itemView_说法有它的所有权转移给Qt的。

设置要使用的组合框弹出给定的视图_itemView_。组合框采用该视图的所有权。

注意：如果你想使用的便利性意见（如[QListWidget](qlistwidget.html)，[QTableWidget](qtablewidget.html) or [QTreeWidget](qtreewidget.html)） ，请确保调用[setModel](qcombobox.html#setModel)（ ）在调用此函数之前的组合框与便利的小部件的模型。

**See also** [view](qcombobox.html#view)（ ） 。

```
QComboBox.showEvent (self, QShowEvent e)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QComboBox.showPopup (self)
```

显示在组合框的项目列表。如果列表为空，则没有项目将会显示。

如果你重新实现这个函数来显示一个自定义弹出，请确保您致电[hidePopup](qcombobox.html#hidePopup)（）复位内部状态。

**See also** [hidePopup](qcombobox.html#hidePopup)（ ） 。

```
SizeAdjustPolicy QComboBox.sizeAdjustPolicy (self)
```

[](qcombobox.html#SizeAdjustPolicy-enum)

```
QSize QComboBox.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

此实现缓存大小提示，以避免在调整大小时的内容动态改变。无效缓存的值改变[sizeAdjustPolicy](qcombobox.html#sizeAdjustPolicy-prop)。

```
QValidator QComboBox.validator (self)
```

[

返回用来限制文字输入组合框的验证。

](qvalidator.html)

[**See also**](qvalidator.html) [setValidator](qcombobox.html#setValidator)（）和[editable](qcombobox.html#editable-prop)。

```
QAbstractItemView QComboBox.view (self)
```

[

返回用于组合框弹出列表视图。

](qabstractitemview.html)

[**See also**](qabstractitemview.html) [setView](qcombobox.html#setView)（ ） 。

```
QComboBox.wheelEvent (self, QWheelEvent e)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

```
 QComboBox.__len__ (self)
```

* * *

## Qt Signal Documentation

```
void activated (int)
```

这是该信号的默认超载。

当用户选择在ComboBox中的项目，这个信号被发送。该项目的_index_被传递。请注意，即使在选择时不改变此信号被发送。如果你需要知道什么时候该选择实际上改变，使用信号[currentIndexChanged](qcombobox.html#currentIndexChanged)（ ） 。

```
void activated (const QString&)
```

当用户选择在ComboBox中的项目，这个信号被发送。该项目的_text_被传递。请注意，即使在选择时不改变此信号被发送。如果你需要知道什么时候该选择实际上改变，使用信号[currentIndexChanged](qcombobox.html#currentIndexChanged)（ ） 。

```
void currentIndexChanged (int)
```

这是该信号的默认超载。

这个信号被发送时的[currentIndex](qcombobox.html#currentIndex-prop)在组合框的变化既可以通过用户交互或编程方式。该项目的_index_通过或-1，如果组合框为空或[currentIndex](qcombobox.html#currentIndex-prop)被重置。

这个函数是Qt 4.1中引入。

```
void currentIndexChanged (const QString&)
```

这个信号被发送时的[currentIndex](qcombobox.html#currentIndex-prop)在组合框的变化既可以通过用户交互或编程方式。该项目的_text_被传递。

这个函数是Qt 4.1中引入。

```
void editTextChanged (const QString&)
```

这是该信号的默认超载。

当在组合框的行编辑插件的文本更改这个信号被发射。新的文本由指定_text_。

```
void highlighted (int)
```

这是该信号的默认超载。

当在组合框弹出列表中的项目是由用户突出显示该信号被发送。该项目的_index_被传递。

```
void highlighted (const QString&)
```

当在组合框弹出列表中的项目是由用户突出显示该信号被发送。该项目的_text_被传递。