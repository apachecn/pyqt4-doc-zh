# QCompleter Class Reference

## [[QtGui](index.htm) module]

该QCompleter类提供了基于项目模型落成。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum CompletionMode { PopupCompletion, UnfilteredPopupCompletion, InlineCompletion }`
*   `enum ModelSorting { UnsortedModel, CaseSensitivelySortedModel, CaseInsensitivelySortedModel }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QAbstractItemModel model, QObject parent = None)`
*   `__init__ (self, QStringList list, QObject parent = None)`
*   `Qt.CaseSensitivity caseSensitivity (self)`
*   `complete (self, QRect rect = QRect())`
*   `int completionColumn (self)`
*   `int completionCount (self)`
*   `CompletionMode completionMode (self)`
*   `QAbstractItemModel completionModel (self)`
*   `QString completionPrefix (self)`
*   `int completionRole (self)`
*   `QString currentCompletion (self)`
*   `QModelIndex currentIndex (self)`
*   `int currentRow (self)`
*   `bool event (self, QEvent)`
*   `bool eventFilter (self, QObject o, QEvent e)`
*   `int maxVisibleItems (self)`
*   `QAbstractItemModel model (self)`
*   `ModelSorting modelSorting (self)`
*   `QString pathFromIndex (self, QModelIndex index)`
*   `QAbstractItemView popup (self)`
*   `setCaseSensitivity (self, Qt.CaseSensitivity caseSensitivity)`
*   `setCompletionColumn (self, int column)`
*   `setCompletionMode (self, CompletionMode mode)`
*   `setCompletionPrefix (self, QString prefix)`
*   `setCompletionRole (self, int role)`
*   `bool setCurrentRow (self, int row)`
*   `setMaxVisibleItems (self, int maxItems)`
*   `setModel (self, QAbstractItemModel c)`
*   `setModelSorting (self, ModelSorting sorting)`
*   `setPopup (self, QAbstractItemView popup)`
*   `setWidget (self, QWidget widget)`
*   `setWrapAround (self, bool wrap)`
*   `QStringList splitPath (self, QString path)`
*   `QWidget widget (self)`
*   `bool wrapAround (self)`

### Qt Signals

*   `void activated (const QString&)`
*   `void activated (const QModelIndex&)`
*   `void highlighted (const QString&)`
*   `void highlighted (const QModelIndex&)`

* * *

## Detailed Description

该QCompleter类提供了基于项目模型落成。

您可以使用QCompleter提供自动完成功能在任何Qt的窗口小部件，如[QLineEdit](qlineedit.html)和[QComboBox](qcombobox.html)。当用户开始输入一个字， QCompleter提示完成单词根据单词列表的可能途径。单词列表是作为一个[QAbstractItemModel](qabstractitemmodel.html)。 （对于简单的应用，这里所说的列表是静态的，你可以通过一个[QStringList](qstringlist.html)到QCompleter的构造函数。 ）

### Basic Usage

一个QCompleter通常用于与[QLineEdit](qlineedit.html) or [QComboBox](qcombobox.html)。例如，这里是如何从一个简单的单词列表提供自动补全[QLineEdit](qlineedit.html)：

```
 [QStringList](qstringlist.html) wordList;
 wordList << "alpha" << "omega" << "omicron" << "zeta";

 [QLineEdit](qlineedit.html) *lineEdit = new [QLineEdit](qlineedit.html)(this);

 QCompleter *completer = new QCompleter(wordList, this);
 completer->setCaseSensitivity([Qt](qt.html).CaseInsensitive);
 lineEdit->setCompleter(completer);

```

A [QFileSystemModel](qfilesystemmodel.html)可用于提供文件名的自动完成。例如：

```
 QCompleter *completer = new QCompleter(this);
 completer->setModel(new [QDirModel](qdirmodel.html)(completer));
 lineEdit->setCompleter(completer);

```

要设置哪些QCompleter应操作模式，通话时间[setModel](qcompleter.html#setModel)（ ） 。默认情况下， QCompleter将尝试匹配[completion prefix](qcompleter.html#completionPrefix-prop)（也就是说，用户已经开始键入单词）对[Qt.EditRole](qt.html#ItemDataRole-enum)存储在模型的情况下0列数据敏感。这可以使用被改变[setCompletionRole](qcompleter.html#completionRole-prop)（ ）[setCompletionColumn](qcompleter.html#completionColumn-prop)（）和[setCaseSensitivity](qcompleter.html#caseSensitivity-prop)（ ） 。

如果模型进行排序了用于完成列和作用，可以调用[setModelSorting](qcompleter.html#modelSorting-prop)（ ）与任何[QCompleter.CaseSensitivelySortedModel](qcompleter.html#ModelSorting-enum) or [QCompleter.CaseInsensitivelySortedModel](qcompleter.html#ModelSorting-enum)作为参数。在大型模型，这可能会导致显着的性能提升，因为QCompleter就可以使用二进制搜索，而不是线性搜索。

该模型可以是一[list model](qabstractlistmodel.html)，一[table model](qabstracttablemodel.html)或[tree model](qabstractitemmodel.html)。完成对树模型是稍微更复杂，并复盖在[Handling Tree Models](#handling-tree-models)下面一节。

该[completionMode](qcompleter.html#completionMode-prop)（）确定用于提供完井给用户的方式。

### Iterating Through Completions

检索单个候选字符串，调用[setCompletionPrefix](qcompleter.html#completionPrefix-prop)（）与需要完成的文本和通话[currentCompletion](qcompleter.html#currentCompletion)（ ） 。您可以通过补全列表迭代如下：

```
 for (int i = 0; completer->setCurrentRow(i); i++)
     qDebug() << completer->currentCompletion() << " is match number " << i;

```

[completionCount](qcompleter.html#completionCount)（）返回完井的总数为当前前缀。[completionCount](qcompleter.html#completionCount)（）时，应避免可能的，因为它要求在整个模型的扫描。

### The Completion Model

[completionModel](qcompleter.html#completionModel)（ ）返回一个包含所有可能的补全当前完成前缀列表模式，在它们出现在模型中的顺序。该模型可用于显示当前的落成在自定义视图。调用[setCompletionPrefix](qcompleter.html#completionPrefix-prop)（ ）自动刷新完成模型。

### Handling Tree Models

QCompleter可以寻找在树模型的完成，假设任何项目（或子项或子分项）可以明确指定该项目的路径表示为一个字符串。完成，然后进行一个级别的时间。

让我们在一个文件系统中的路径的用户输入的示例。该模型是一个（分层）[QFileSystemModel](qfilesystemmodel.html)。完成出现在路径中的每个元素。例如，如果当前的文本是`C:\Wind`， QCompleter可能会建议`Windows`完成当前路径元素。同样，如果当前的文本是`C:\Windows\Sy`， QCompleter可能会建议`System`。

对于这种完成工作的， QCompleter需要能够将路径分割成匹配在每个级别的字符串列表。为`C:\Windows\Sy`，它需要被分割为“C ：”，“窗口”和“施” 。的默认实现[splitPath](qcompleter.html#splitPath)（ ） ，分裂[completionPrefix](qcompleter.html#completionPrefix-prop) using [QDir.separator](qdir.html#separator)（ ）如果模型是一个[QFileSystemModel](qfilesystemmodel.html)。

提供完井， QCompleter需要从索引知道路径。这是通过提供[pathFromIndex](qcompleter.html#pathFromIndex)（ ） 。的默认实现[pathFromIndex](qcompleter.html#pathFromIndex)（ ） ，返回的数据[edit role](qt.html#ItemDataRole-enum)为列表模式和绝对文件路径，如果模式是[QFileSystemModel](qfilesystemmodel.html)。

* * *

## Type Documentation

```
QCompleter.CompletionMode
```

该枚举指定如何完井提供给用户。

| Constant | Value | Description |
| --- | --- | --- |
| `QCompleter.PopupCompletion` | `0` | 目前完井显示在一个弹出窗口。 |
| `QCompleter.InlineCompletion` | `2` | 完井行内显示（选定文本）。 |
| `QCompleter.UnfilteredPopupCompletion` | `1` | 所有可能的完成与指示为当前最有可能的建议，显示在一个弹出窗口中。 |

**See also** [setCompletionMode](qcompleter.html#completionMode-prop)（ ） 。

```
QCompleter.ModelSorting
```

此枚举指定如何在模型中的项目进行排序。

| Constant | Value | Description |
| --- | --- | --- |
| `QCompleter.UnsortedModel` | `0` | 该模型是未排序。 |
| `QCompleter.CaseSensitivelySortedModel` | `1` | 该模型是敏感排序的情况。 |
| `QCompleter.CaseInsensitivelySortedModel` | `2` | 该模型是不区分大小写排序的情况。 |

**See also** [setModelSorting](qcompleter.html#modelSorting-prop)（ ） 。

* * *

## Method Documentation

```
QCompleter.__init__ (self, QObject parent = None)
```

该_parent_争论

构造一个完成者对象与给定_parent_。

```
QCompleter.__init__ (self, QAbstractItemModel model, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个完成者对象与给定_parent_提供完井从指定的_model_。

```
QCompleter.__init__ (self, QStringList list, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QCompleter](qcompleter.html)与给定对象_parent_使用指定的_list_作为尽可能完整的源代码。

```
Qt.CaseSensitivity QCompleter.caseSensitivity (self)
```

[

```
QCompleter.complete (self, QRect rect = QRect())
```

这种方法也是一个Qt槽与C + +的签名`void complete(const QRect& = QRect())`。

](qt.html#CaseSensitivity-enum)

[为](qt.html#CaseSensitivity-enum)[QCompleter.PopupCompletion](qcompleter.html#CompletionMode-enum)和QCompletion.UnfilteredPopupCompletion模式，调用这个函数显示显示当前落成弹出。默认情况下，如果_rect_没有指定，则弹出窗口显示的底部[widget](qcompleter.html#widget)（ ） 。如果_rect_指定了弹出窗口被显示在矩形的左边缘。

为[QCompleter.InlineCompletion](qcompleter.html#CompletionMode-enum)模式下，[highlighted](qcompleter.html#highlighted)（ ）信号被发射了与当前的完成。

```
int QCompleter.completionColumn (self)
```

```
int QCompleter.completionCount (self)
```

返回完井的数量为当前前缀。对于有大量项目的未排序的模型可以是昂贵的。使用[setCurrentRow](qcompleter.html#setCurrentRow)（）和[currentCompletion](qcompleter.html#currentCompletion)（ ）遍历所有的补全。

```
CompletionMode QCompleter.completionMode (self)
```

[](qcompleter.html#CompletionMode-enum)

```
QAbstractItemModel QCompleter.completionModel (self)
```

[

返回完成模型。在完成模型是包含所有当前完成前缀可能的匹配一个只读列表模式。完成模型自动更新，以反映当前的落成。

](qabstractitemmodel.html)

[**Note:**这个函数的返回值被定义为一个](qabstractitemmodel.html)[QAbstractItemModel](qabstractitemmodel.html)纯粹是为了通用性。这实际返回的一种模型是一个实例[QAbstractProxyModel](qabstractproxymodel.html)子类。

**See also** [completionPrefix](qcompleter.html#completionPrefix-prop)和[model](qcompleter.html#model)（ ） 。

```
QString QCompleter.completionPrefix (self)
```

```
int QCompleter.completionRole (self)
```

```
QString QCompleter.currentCompletion (self)
```

返回当前完井管柱。这包括[completionPrefix](qcompleter.html#completionPrefix-prop)。当一起使用[setCurrentRow](qcompleter.html#setCurrentRow)（ ） ，它可以用来遍历所有的比赛。

**See also** [setCurrentRow](qcompleter.html#setCurrentRow)（）和[currentIndex](qcompleter.html#currentIndex)（ ） 。

```
QModelIndex QCompleter.currentIndex (self)
```

[](qmodelindex.html)

[返回在当前完成的模型索引](qmodelindex.html)[completionModel](qcompleter.html#completionModel)（ ） 。

**See also** [setCurrentRow](qcompleter.html#setCurrentRow)（ ）[currentCompletion](qcompleter.html#currentCompletion)（）和[model](qcompleter.html#model)（ ） 。

```
int QCompleter.currentRow (self)
```

返回当前行。

**See also** [setCurrentRow](qcompleter.html#setCurrentRow)（ ） 。

```
bool QCompleter.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QCompleter.eventFilter (self, QObject o, QEvent e)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
int QCompleter.maxVisibleItems (self)
```

```
QAbstractItemModel QCompleter.model (self)
```

[

返回提供完井管柱模型。

](qabstractitemmodel.html)

[**See also**](qabstractitemmodel.html) [setModel](qcompleter.html#setModel)（）和[completionModel](qcompleter.html#completionModel)（ ） 。

```
ModelSorting QCompleter.modelSorting (self)
```

[

```
QString QCompleter.pathFromIndex (self, QModelIndex index)
```

返回路径为给定的_index_。完成者对象使用这个从底层模型得到完成文本。

](qcompleter.html#ModelSorting-enum)

[默认实现返回](qcompleter.html#ModelSorting-enum)[edit role](qt.html#ItemDataRole-enum)为列表模式的项目。它返回文件的绝对路径，如果这个模型是一个[QFileSystemModel](qfilesystemmodel.html)。

**See also** [splitPath](qcompleter.html#splitPath)（ ） 。

```
QAbstractItemView QCompleter.popup (self)
```

[

返回用于显示落成弹出。

](qabstractitemview.html)

[**See also**](qabstractitemview.html) [setPopup](qcompleter.html#setPopup)（ ） 。

```
QCompleter.setCaseSensitivity (self, Qt.CaseSensitivity caseSensitivity)
```

```
QCompleter.setCompletionColumn (self, int column)
```

```
QCompleter.setCompletionMode (self, CompletionMode mode)
```

```
QCompleter.setCompletionPrefix (self, QString prefix)
```

这种方法也是一个Qt槽与C + +的签名`void setCompletionPrefix(const QString&)`。

```
QCompleter.setCompletionRole (self, int role)
```

```
bool QCompleter.setCurrentRow (self, int row)
```

当前行设置为_row_规定。成功返回True ，否则返回False 。

这个功能可以随着所用[currentCompletion](qcompleter.html#currentCompletion)（ ）遍历所有可能的补全。

**See also** [currentRow](qcompleter.html#currentRow)（ ）[currentCompletion](qcompleter.html#currentCompletion)（）和[completionCount](qcompleter.html#completionCount)（ ） 。

```
QCompleter.setMaxVisibleItems (self, int maxItems)
```

```
QCompleter.setModel (self, QAbstractItemModel c)
```

设置提供完井模型_model_。该_model_可以列表模式或树模型。如果模型已经被预先设置，并具有[QCompleter](qcompleter.html)作为其母公司，将被删除。

为方便起见，如果_model_是[QFileSystemModel](qfilesystemmodel.html)，[QCompleter](qcompleter.html)其切换[caseSensitivity](qcompleter.html#caseSensitivity-prop)至[Qt.CaseInsensitive](qt.html#CaseSensitivity-enum)在Windows和[Qt.CaseSensitive](qt.html#CaseSensitivity-enum)在其他平台上。

**See also** [completionModel](qcompleter.html#completionModel)（ ）[modelSorting](qcompleter.html#modelSorting-prop)和[Handling Tree Models](qcompleter.html#handling-tree-models)。

```
QCompleter.setModelSorting (self, ModelSorting sorting)
```

```
QCompleter.setPopup (self, QAbstractItemView popup)
```

该_popup_说法有它的所有权转移给Qt的。

设置用于显示完井弹出_popup_。[QCompleter](qcompleter.html)采用该视图的所有权。

A [QListView](qlistview.html)时自动创建的[completionMode](qcompleter.html#completionMode-prop)（ ）被设置为[QCompleter.PopupCompletion](qcompleter.html#CompletionMode-enum) or [QCompleter.UnfilteredPopupCompletion](qcompleter.html#CompletionMode-enum)。默认的弹出窗口显示[completionColumn](qcompleter.html#completionColumn-prop)（ ） 。

确保这个函数被调用视图设置被修改之前。这是必需的，因为视图的属性可能需要一个模型已经被设置的视图（例如，隐藏在视图中的列需要一个模型要在视图中设置） 。

**See also** [popup](qcompleter.html#popup)（ ） 。

```
QCompleter.setWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置用来完成所规定的小部件_widget_。这个函数被自动调用，当[QCompleter](qcompleter.html)设置在[QLineEdit](qlineedit.html) using [QLineEdit.setCompleter](qlineedit.html#setCompleter)（）或上一个[QComboBox](qcombobox.html) using [QComboBox.setCompleter](qcombobox.html#setCompleter)（ ） 。该部件需要明确规定完成为自定义控件时进行设置。

**See also** [widget](qcompleter.html#widget)（ ）[setModel](qcompleter.html#setModel)（）和[setPopup](qcompleter.html#setPopup)（ ） 。

```
QCompleter.setWrapAround (self, bool wrap)
```

这种方法也是一个Qt槽与C + +的签名`void setWrapAround(bool)`。

```
QStringList QCompleter.splitPath (self, QString path)
```

拆分给定的_path_成用于匹配在每个级别的字符串[model](qcompleter.html#model)（ ） 。

splitPath的默认实现（ ）分割基于文件系统路径[QDir.separator](qdir.html#separator)（）当sourceModel （）是一个[QFileSystemModel](qfilesystemmodel.html)。

当与表模型中使用，在返回列表中的第一个项目是用于匹配。

**See also** [pathFromIndex](qcompleter.html#pathFromIndex)（）和[Handling Tree Models](qcompleter.html#handling-tree-models)。

```
QWidget QCompleter.widget (self)
```

[

返回其完成者对象提供的补全部件。

](qwidget.html)

[**See also**](qwidget.html) [setWidget](qcompleter.html#setWidget)（ ） 。

```
bool QCompleter.wrapAround (self)
```

* * *

## Qt Signal Documentation

```
void activated (const QString&)
```

这是该信号的默认超载。

这个信号被发送时，在一个项目[popup](qcompleter.html#popup)（ ）是由用户（通过单击或按回车键）激活。该项目的_text_给出。

```
void activated (const QModelIndex&)
```

这个信号被发送时，在一个项目[popup](qcompleter.html#popup)（）是由用户激活。 （通过单击或按回车键） 。该项目的_index_在[completionModel](qcompleter.html#completionModel)（）给出。

```
void highlighted (const QString&)
```

这是该信号的默认超载。

这个信号被发送时，在一个项目[popup](qcompleter.html#popup)（）是由用户突出显示。它也被发送，如果[complete](qcompleter.html#complete)（ ）被调用，[completionMode](qcompleter.html#completionMode-prop)（）设定为[QCompleter.InlineCompletion](qcompleter.html#CompletionMode-enum)。该项目的_text_给出。

```
void highlighted (const QModelIndex&)
```

这个信号被发送时，在一个项目[popup](qcompleter.html#popup)（）是由用户突出显示。它也被发送，如果[complete](qcompleter.html#complete)（ ）被调用，[completionMode](qcompleter.html#completionMode-prop)（）设定为[QCompleter.InlineCompletion](qcompleter.html#CompletionMode-enum)。该项目的_index_在[completionModel](qcompleter.html#completionModel)（）给出。