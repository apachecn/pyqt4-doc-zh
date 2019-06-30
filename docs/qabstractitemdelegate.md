# QAbstractItemDelegate Class Reference

## [[QtGui](index.htm) module]

该QAbstractItemDelegate类用于从模型显示和编辑数据项。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QItemDelegate](qitemdelegate.html)和[QStyledItemDelegate](qstyleditemdelegate.html)。

### Types

*   `enum EndEditHint { NoHint, EditNextItem, EditPreviousItem, SubmitModelCache, RevertModelCache }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QWidget createEditor (self, QWidget parent, QStyleOptionViewItem option, QModelIndex index)`
*   `bool editorEvent (self, QEvent event, QAbstractItemModel model, QStyleOptionViewItem option, QModelIndex index)`
*   `bool helpEvent (self, QHelpEvent event, QAbstractItemView view, QStyleOptionViewItem option, QModelIndex index)`
*   `paint (self, QPainter painter, QStyleOptionViewItem option, QModelIndex index)`
*   `setEditorData (self, QWidget editor, QModelIndex index)`
*   `setModelData (self, QWidget editor, QAbstractItemModel model, QModelIndex index)`
*   `QSize sizeHint (self, QStyleOptionViewItem option, QModelIndex index)`
*   `updateEditorGeometry (self, QWidget editor, QStyleOptionViewItem option, QModelIndex index)`

### Static Methods

*   `QString elidedText (QFontMetrics fontMetrics, int width, Qt.TextElideMode mode, QString text)`

### Qt Signals

*   `void closeEditor (QWidget *,QAbstractItemDelegate::EndEditHint = QAbstractItemDelegate.NoHint)`
*   `void commitData (QWidget *)`
*   `void sizeHintChanged (const QModelIndex&)`

* * *

## Detailed Description

该QAbstractItemDelegate类用于从模型显示和编辑数据项。

一个QAbstractItemDelegate提供了在模型/视图结构代表的接口和通用的功能。代表们显示在视图中的个别项目，并处理模型数据的编辑。

该QAbstractItemDelegate类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

呈现在一个自定义的方法的项目，则必须实现[paint](qabstractitemdelegate.html#paint)（）和[sizeHint](qabstractitemdelegate.html#sizeHint)（ ） 。该[QItemDelegate](qitemdelegate.html)类提供默认实现这些功能，如果你不需要自定义的渲染，继承这个类来代替。

我们给画中的项目一个进度条的例子，在我们的例子中的一个包管理程序。

![](../img/widgetdelegate.png)

我们创造的`WidgetDelegate`类，它继承自[QStyledItemDelegate](qstyleditemdelegate.html)。我们在绘图[paint](qabstractitemdelegate.html#paint)（ ）函数：

```
 void WidgetDelegate.paint([QPainter](qpainter.html) *painter, const [QStyleOptionViewItem](qstyleoptionviewitem.html) &option,
                            const [QModelIndex](qmodelindex.html) &index) const
 {
     if (index.column() == 1) {
         int progress = index.data().toInt();

         [QStyleOptionProgressBar](qstyleoptionprogressbar.html) progressBarOption;
         progressBarOption.rect = option.rect;
         progressBarOption.minimum = 0;
         progressBarOption.maximum = 100;
         progressBarOption.progress = progress;
         progressBarOption.text = [QString](qstring.html).number(progress) + "%";
         progressBarOption.textVisible = true;

         [QApplication](qapplication.html).style()->drawControl([QStyle](qstyle.html).CE_ProgressBar,
                                            &progressBarOption, painter);
     } else
         [QStyledItemDelegate](qstyleditemdelegate.html).paint(painter, option, index);

```

请注意，我们使用了[QStyleOptionProgressBar](qstyleoptionprogressbar.html)并初始化它的成员。然后，我们可以使用当前[QStyle](qstyle.html)绘制它。

提供自定义编辑，有可以使用的两种方法。第一种方法是创建一个编辑器窗口小部件，并直接对项目的顶部显示。要做到这一点，你必须重新实现[createEditor](qabstractitemdelegate.html#createEditor)（ ）提供一个编辑器部件，[setEditorData](qabstractitemdelegate.html#setEditorData)（）来填充从模型数据编辑器中，[setModelData](qabstractitemdelegate.html#setModelData)（ ），使得代理可以更新模型以从编辑数据。

第二种方法是直接通过重新实现处理用户事件[editorEvent](qabstractitemdelegate.html#editorEvent)（ ） 。

* * *

## Type Documentation

```
QAbstractItemDelegate.EndEditHint
```

这个枚举变量描述了不同的提示，该委讬可以给模型和视图组件使编辑数据的用户模型中的舒适体验。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemDelegate.NoHint` | `0` | 没有要执行建议的操作。 |

这些提示让代表影响视图的行为：

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemDelegate.EditNextItem` | `1` | 认为应使用委讬在视图中打开的下一个项目的编辑器。 |
| `QAbstractItemDelegate.EditPreviousItem` | `2` | 认为应使用委讬在视图中打开的前一个条目的编辑器。 |

请注意，自定义视图可以解释的下一个和以前不同的概念。

当模型被用于下面的提示是最有用的高速缓存数据，如那些在本地操作数据，以便提高性能或节约网络带宽。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemDelegate.SubmitModelCache` | `3` | 如果模型缓存数据，它应该写出来缓存数据到底层数据存储。 |
| `QAbstractItemDelegate.RevertModelCache` | `4` | 如果模型缓存数据，应该丢弃缓存数据，并将其与底层数据存储的数据替换。 |

虽然模型和视图应以适当方式对这些提示作出反应，自定义组件可能会忽略其中任何一个或全部，如果他们是不相关的。

* * *

## Method Documentation

```
QAbstractItemDelegate.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的抽象项目委讬给定的_parent_。

```
QWidget QAbstractItemDelegate.createEditor (self, QWidget parent, QStyleOptionViewItem option, QModelIndex index)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

返回编辑器用于编辑的数据项与给定的_index_。请注意，该指数包含了所使用的模型信息。编辑器的父窗口部件被指定_parent_，且该项目由选项_option_。

该基地实现返回0 。如果你想自定义编辑，你需要重写本函数。

](qwidget.html)

[返回编辑器部件应该有](qwidget.html)[Qt.StrongFocus](qt.html#FocusPolicy-enum)否则，[QMouseEvent](qmouseevent.html)由小工具收到的S将传播到视图。除非编辑器绘制自己的背景视图的背景将彪炳（例如，用[setAutoFillBackground()](qwidget.html#autoFillBackground-prop)） 。

**See also** [setModelData](qabstractitemdelegate.html#setModelData)（）和[setEditorData](qabstractitemdelegate.html#setEditorData)（ ） 。

```
bool QAbstractItemDelegate.editorEvent (self, QEvent event, QAbstractItemModel model, QStyleOptionViewItem option, QModelIndex index)
```

的项目开始编辑时，这个函数被调用的_event_触发编辑的_model_时，_index_该项目，并在_option_用于呈现的资料。

鼠标事件发送到editorEvent （ ），即使它们不启动项目进行编辑。如果你想打开上下文菜单时，鼠标右键是在项目上按下这可以，例如，是有用的。

（表示它没有处理的事件）基本实现返回False 。

```
QString QAbstractItemDelegate.elidedText (QFontMetrics fontMetrics, int width, Qt.TextElideMode mode, QString text)
```

```
bool QAbstractItemDelegate.helpEvent (self, QHelpEvent event, QAbstractItemView view, QStyleOptionViewItem option, QModelIndex index)
```

这种方法也是一个Qt槽与C + +的签名`bool helpEvent(QHelpEvent *,QAbstractItemView *,const QStyleOptionViewItem&,const QModelIndex&)`。

每当有帮助的事件发生时，这个函数被调用，_event_ _view_ _option_和_index_对应于其中发生该事件的资料。

返回True如果委讬可以处理该事件，否则返回False 。的返回值为True表示使用索引获得的数据有必要的作用。

为[QEvent.ToolTip](qevent.html#Type-enum)和[QEvent.WhatsThis](qevent.html#Type-enum)已成功处理的事件时，有关弹出窗口可能取决于用户的系统配置被显示。

此功能被引入Qt的4.3 。

**See also** [QHelpEvent](qhelpevent.html)。

```
QAbstractItemDelegate.paint (self, QPainter painter, QStyleOptionViewItem option, QModelIndex index)
```

这种方法是抽象的，应在任何子类中重新实现。

如果您想提供定制渲染这种纯粹抽象函数必须被重新实现。使用_painter_和风格_option_呈现由该项目指定的项目_index_。

如果你重新实现这一点，你也必须重新实现[sizeHint](qabstractitemdelegate.html#sizeHint)（ ） 。

```
QAbstractItemDelegate.setEditorData (self, QWidget editor, QModelIndex index)
```

设定的给定的内容_editor_以在给定的数据项_index_。请注意，该指数包含了所使用的模型信息。

基实现不执行任何操作。如果你想自定义编辑，你需要重写本函数。

**See also** [setModelData](qabstractitemdelegate.html#setModelData)（ ） 。

```
QAbstractItemDelegate.setModelData (self, QWidget editor, QAbstractItemModel model, QModelIndex index)
```

设置项目的数据在给定的_index_在_model_到给定的内容_editor_。

基实现不执行任何操作。如果你想自定义编辑，你需要重写本函数。

**See also** [setEditorData](qabstractitemdelegate.html#setEditorData)（ ） 。

```
QSize QAbstractItemDelegate.sizeHint (self, QStyleOptionViewItem option, QModelIndex index)
```

[

这种方法是抽象的，应在任何子类中重新实现。

如果您想提供定制渲染这种纯粹抽象函数必须被重新实现。该选项由指定_option_并通过模型项目_index_。

](qsize.html)

[如果你重新实现这一点，你也必须重新实现](qsize.html)[paint](qabstractitemdelegate.html#paint)（ ） 。

```
QAbstractItemDelegate.updateEditorGeometry (self, QWidget editor, QStyleOptionViewItem option, QModelIndex index)
```

更新的几何_editor_与给定的项目_index_，根据在指定的矩形_option_。如果该项目有一个内部的布局，编辑器会相应布局。请注意，该指数包含了所使用的模型信息。

基实现不执行任何操作。如果你想自定义编辑你必须重新实现此功能。

* * *

## Qt Signal Documentation

```
void closeEditor (QWidget *,QAbstractItemDelegate::EndEditHint = QAbstractItemDelegate.NoHint)
```

这是该信号的默认超载。

当用户完成使用指定的编辑项目，该信号被发射_editor_。

该_hint_提供了一种方法的委讬来影响如何编辑后的模型和视图的行为已经完成。这表明这些组件执行的动作旁，为用户提供了舒适的编辑体验进行。例如，如果`EditNextItem`被指定，视图应该使用委讬来打开在模型中的下一个项目的编辑器。

**See also** [EndEditHint](qabstractitemdelegate.html#EndEditHint-enum)。

```
void commitData (QWidget *)
```

这是该信号的默认超载。

这个信号必须被发射时的_editor_小部件已经完成编辑数据，并希望将它写回模式。

```
void sizeHintChanged (const QModelIndex&)
```

这是该信号的默认超载。

这个信号必须被发射时的[sizeHint](qabstractitemdelegate.html#sizeHint)的（ ）_index_改变。

视图会自动连接到这个信号，并重新布局的项目是必要的。

此功能被引入Qt的4.4 。