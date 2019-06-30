# QGraphicsProxyWidget Class Reference

## [[QtGui](index.htm) module]

该QGraphicsProxyWidget类提供了一个代理层嵌入[QWidget](qwidget.html)在[QGraphicsScene](qgraphicsscene.html)。[More...](#details)

继承[QGraphicsWidget](qgraphicswidget.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None, Qt.WindowFlags flags = 0)`
*   `contextMenuEvent (self, QGraphicsSceneContextMenuEvent event)`
*   `QGraphicsProxyWidget createProxyForChildWidget (self, QWidget child)`
*   `dragEnterEvent (self, QGraphicsSceneDragDropEvent event)`
*   `dragLeaveEvent (self, QGraphicsSceneDragDropEvent event)`
*   `dragMoveEvent (self, QGraphicsSceneDragDropEvent event)`
*   `dropEvent (self, QGraphicsSceneDragDropEvent event)`
*   `bool event (self, QEvent event)`
*   `bool eventFilter (self, QObject object, QEvent event)`
*   `focusInEvent (self, QFocusEvent event)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent event)`
*   `grabMouseEvent (self, QEvent event)`
*   `hideEvent (self, QHideEvent event)`
*   `hoverEnterEvent (self, QGraphicsSceneHoverEvent event)`
*   `hoverLeaveEvent (self, QGraphicsSceneHoverEvent event)`
*   `hoverMoveEvent (self, QGraphicsSceneHoverEvent event)`
*   `QVariant itemChange (self, QGraphicsItem.GraphicsItemChange change, QVariant value)`
*   `keyPressEvent (self, QKeyEvent event)`
*   `keyReleaseEvent (self, QKeyEvent event)`
*   `mouseDoubleClickEvent (self, QGraphicsSceneMouseEvent event)`
*   `mouseMoveEvent (self, QGraphicsSceneMouseEvent event)`
*   `mousePressEvent (self, QGraphicsSceneMouseEvent event)`
*   `mouseReleaseEvent (self, QGraphicsSceneMouseEvent event)`
*   `QGraphicsProxyWidget newProxyWidget (self, QWidget)`
*   `paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget)`
*   `resizeEvent (self, QGraphicsSceneResizeEvent event)`
*   `setGeometry (self, QRectF rect)`
*   `setWidget (self, QWidget widget)`
*   `showEvent (self, QShowEvent event)`
*   `QSizeF sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())`
*   `QRectF subWidgetRect (self, QWidget widget)`
*   `int type (self)`
*   `ungrabMouseEvent (self, QEvent event)`
*   `wheelEvent (self, QGraphicsSceneWheelEvent event)`
*   `QWidget widget (self)`

* * *

## Detailed Description

该QGraphicsProxyWidget类提供了一个代理层嵌入[QWidget](qwidget.html)在[QGraphicsScene](qgraphicsscene.html)。

QGraphicsProxyWidget嵌入式播放器[QWidget](qwidget.html)基于窗口小部件，例如，一个[QPushButton](qpushbutton.html)，[QFontComboBox](qfontcombobox.html)或什至[QFileDialog](qfiledialog.html)，成[QGraphicsScene](qgraphicsscene.html)。转发两个对象之间的事件之间转换[QWidget](qwidget.html)的整数为基础的几何形状和[QGraphicsWidget](qgraphicswidget.html)的QREAL为基础的几何形状。 QGraphicsProxyWidget支持的所有核心功能[QWidget](qwidget.html)包括标籤焦点，键盘输入，拖放，和弹出窗口。您还可以嵌入复杂的部件，例如，小部件与subwidgets 。

例如：

```
 int main(int argc, char **argv)
 {
     [QApplication](qapplication.html) app(argc, argv);

     [QTabWidget](qtabwidget.html) *tabWidget = new [QTabWidget](qtabwidget.html);

     [QGraphicsScene](qgraphicsscene.html) scene;
     QGraphicsProxyWidget *proxy = scene.addWidget(tabWidget);

     [QGraphicsView](qgraphicsview.html) view(&scene);
     view.show();

     return app.exec();
 }

```

QGraphicsProxyWidget需要通过创建为每个弹出一个子代理自动弹出嵌入嵌入部件的孩子照顾。这意味着，当一个嵌入式[QComboBox](qcombobox.html)显示其弹出的列表中，一个新的QGraphicsProxyWidget会自动创建，嵌入弹出，正确定位它。这只有在弹出是嵌入式控件的子工程（例如[QToolButton.setMenu](qtoolbutton.html#setMenu)（ ）要求[QMenu](qmenu.html)实例是孩子[QToolButton](qtoolbutton.html)） 。

### Embedding a Widget with QGraphicsProxyWidget

有两种方式来嵌入使用QGraphicsProxyWidget一个小部件。最常见的方法是将一个部件指针传递给[QGraphicsScene.addWidget](qgraphicsscene.html#addWidget)（ ）连同任何相关[Qt.WindowFlags](qt.html#WindowType-enum)。这个函数返回一个指针，指向一个QGraphicsProxyWidget 。然后，您可以选择reparent或位置无论是代理，或嵌入部件本身。

例如，下面的代码片段中，我们嵌入一个组框入代理：

```
 [QGroupBox](qgroupbox.html) *groupBox = new [QGroupBox](qgroupbox.html)("Contact Details");
 [QLabel](qlabel.html) *numberLabel = new [QLabel](qlabel.html)("Telephone number");
 [QLineEdit](qlineedit.html) *numberEdit = new [QLineEdit](qlineedit.html);

 [QFormLayout](qformlayout.html) *layout = new [QFormLayout](qformlayout.html);
 layout->addRow(numberLabel, numberEdit);
 groupBox->setLayout(layout);

 [QGraphicsScene](qgraphicsscene.html) scene;
 QGraphicsProxyWidget *proxy = scene.addWidget(groupBox);

 [QGraphicsView](qgraphicsview.html) view(&scene);
 view.show();

```

下面的图片是其内容利润率和内容获得RECT标记输出。

![](../img/qgraphicsproxywidget-embed.png)

或者，您也可以通过创建一个新的QGraphicsProxyWidget项目开始，然后调用[setWidget](qgraphicsproxywidget.html#setWidget)（ ）嵌入[QWidget](qwidget.html)后来。该[widget](qgraphicsproxywidget.html#widget)（ ）函数返回一个指向嵌入部件。 QGraphicsProxyWidget股份拥有权[QWidget](qwidget.html)，所以如果两个部件被破坏，其他部件将被自动销毁。

### Synchronizing Widget States

QGraphicsProxyWidget保持其状态与嵌入式部件同步。例如，如果代理是隐藏或禁用，嵌入式部件将被隐藏或禁用为好，反之亦然。当插件被嵌入通过调用addWidget （） ， QGraphicsProxyWidget副本从窗口小部件的状态到代理，并在这之后，两个将保持同步，其中可能的。默认情况下，当你嵌入一个widget到一个代理，无论是部件和代理将是可见的，因为一[QGraphicsWidget](qgraphicswidget.html)创建时是可见的（你不必调用[show](qgraphicsitem.html#show)（））。如果你明确地隐藏嵌入部件，代理也将成为无形的。

例如：

```
 [QGraphicsScene](qgraphicsscene.html) scene;

 [QLineEdit](qlineedit.html) *edit = new [QLineEdit](qlineedit.html);
 QGraphicsProxyWidget *proxy = scene.addWidget(edit);

 edit->isVisible();  // returns true
 proxy->isVisible(); // also returns true

 edit->hide();

 edit->isVisible();  // returns false
 proxy->isVisible(); // also returns false

```

QGraphicsProxyWidget保持对称性以下国家：

| [QWidget](qwidget.html) state | QGraphicsProxyWidget state | Notes |
| --- | --- | --- |
| [QWidget.enabled](qwidget.html#enabled-prop) | [QGraphicsProxyWidget.enabled](qgraphicsobject.html#enabled-prop) |  |
| [QWidget.visible](qwidget.html#visible-prop) | [QGraphicsProxyWidget.visible](qgraphicsobject.html#visible-prop) | The explicit state is also symmetric. |
| [QWidget.geometry](qwidget.html#geometry-prop) | [QGraphicsProxyWidget.geometry](qgraphicswidget.html#geometry-prop) | Geometry is only guaranteed to be symmetric while the embedded widget is visible. |
| [QWidget.layoutDirection](qwidget.html#layoutDirection-prop) | [QGraphicsProxyWidget.layoutDirection](qgraphicswidget.html#layoutDirection-prop) |  |
| QWidget.style | QGraphicsProxyWidget.style |  |
| [QWidget.palette](qwidget.html#palette-prop) | [QGraphicsProxyWidget.palette](qgraphicswidget.html#palette-prop) |  |
| [QWidget.font](qwidget.html#font-prop) | [QGraphicsProxyWidget.font](qgraphicswidget.html#font-prop) |  |
| [QWidget.cursor](qwidget.html#cursor-prop) | QGraphicsProxyWidget.cursor | The embedded widget overrides the proxy widget cursor. The proxy cursor changes depending on which embedded subwidget is currently under the mouse. |
| [QWidget.sizeHint](qwidget.html#sizeHint-prop)() | [QGraphicsProxyWidget.sizeHint](qgraphicsproxywidget.html#sizeHint)() | All size hint functionality from the embedded widget is forwarded by the proxy. |
| [QWidget.getContentsMargins](qwidget.html#getContentsMargins)() | [QGraphicsProxyWidget.getContentsMargins](qgraphicswidget.html#getContentsMargins)() | Updated once by [setWidget](qgraphicsproxywidget.html#setWidget)(). |
| [QWidget.windowTitle](qwidget.html#windowTitle-prop) | [QGraphicsProxyWidget.windowTitle](qgraphicswidget.html#windowTitle-prop) | Updated once by [setWidget](qgraphicsproxywidget.html#setWidget)(). |

**Note:** [QGraphicsScene](qgraphicsscene.html)保存在一个特殊的状态，防止它干扰其他部件（包括嵌入式和不嵌入），而小部件嵌入嵌入部件。在这种状态下，小部件可以略微在从行为时，它不是嵌入不同。

**Warning:**该类提供了方便，当桥接QWidgets和QGraphicsItems ，它不应该被用于高性能的场景。

* * *

## Method Documentation

```
QGraphicsProxyWidget.__init__ (self, QGraphicsItem parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的QGraphicsProxy部件。_parent_和_wFlags_被传递到[QGraphicsItem](qgraphicsitem.html)的构造。

```
QGraphicsProxyWidget.contextMenuEvent (self, QGraphicsSceneContextMenuEvent event)
```

从重新实现[QGraphicsItem.contextMenuEvent](qgraphicsitem.html#contextMenuEvent)（ ） 。

```
QGraphicsProxyWidget QGraphicsProxyWidget.createProxyForChildWidget (self, QWidget child)
```

[

创建一个代理部件给定的_child_包含在这个代理的小工具。

此功能使得它可以获取代理非顶层窗口部件。例如，你可以嵌入一个对话框，然后只是它的小部件一个转换。

如果部件已经嵌入，返回现有的代理部件。

此功能被引入Qt的4.5 。

](qgraphicsproxywidget.html)

[**See also**](qgraphicsproxywidget.html) [newProxyWidget](qgraphicsproxywidget.html#newProxyWidget)（）和[QGraphicsScene.addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsProxyWidget.dragEnterEvent (self, QGraphicsSceneDragDropEvent event)
```

从重新实现[QGraphicsItem.dragEnterEvent](qgraphicsitem.html#dragEnterEvent)（ ） 。

```
QGraphicsProxyWidget.dragLeaveEvent (self, QGraphicsSceneDragDropEvent event)
```

从重新实现[QGraphicsItem.dragLeaveEvent](qgraphicsitem.html#dragLeaveEvent)（ ） 。

```
QGraphicsProxyWidget.dragMoveEvent (self, QGraphicsSceneDragDropEvent event)
```

从重新实现[QGraphicsItem.dragMoveEvent](qgraphicsitem.html#dragMoveEvent)（ ） 。

```
QGraphicsProxyWidget.dropEvent (self, QGraphicsSceneDragDropEvent event)
```

从重新实现[QGraphicsItem.dropEvent](qgraphicsitem.html#dropEvent)（ ） 。

```
bool QGraphicsProxyWidget.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QGraphicsProxyWidget.eventFilter (self, QObject object, QEvent event)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
QGraphicsProxyWidget.focusInEvent (self, QFocusEvent event)
```

从重新实现[QGraphicsItem.focusInEvent](qgraphicsitem.html#focusInEvent)（ ） 。

```
bool QGraphicsProxyWidget.focusNextPrevChild (self, bool next)
```

从重新实现[QGraphicsWidget.focusNextPrevChild](qgraphicswidget.html#focusNextPrevChild)（ ） 。

```
QGraphicsProxyWidget.focusOutEvent (self, QFocusEvent event)
```

从重新实现[QGraphicsItem.focusOutEvent](qgraphicsitem.html#focusOutEvent)（ ） 。

```
QGraphicsProxyWidget.grabMouseEvent (self, QEvent event)
```

从重新实现[QGraphicsWidget.grabMouseEvent](qgraphicswidget.html#grabMouseEvent)（ ） 。

```
QGraphicsProxyWidget.hideEvent (self, QHideEvent event)
```

从重新实现[QGraphicsWidget.hideEvent](qgraphicswidget.html#hideEvent)（ ） 。

```
QGraphicsProxyWidget.hoverEnterEvent (self, QGraphicsSceneHoverEvent event)
```

从重新实现[QGraphicsItem.hoverEnterEvent](qgraphicsitem.html#hoverEnterEvent)（ ） 。

```
QGraphicsProxyWidget.hoverLeaveEvent (self, QGraphicsSceneHoverEvent event)
```

从重新实现[QGraphicsItem.hoverLeaveEvent](qgraphicsitem.html#hoverLeaveEvent)（ ） 。

```
QGraphicsProxyWidget.hoverMoveEvent (self, QGraphicsSceneHoverEvent event)
```

从重新实现[QGraphicsItem.hoverMoveEvent](qgraphicsitem.html#hoverMoveEvent)（ ） 。

```
QVariant QGraphicsProxyWidget.itemChange (self, QGraphicsItem.GraphicsItemChange change, QVariant value)
```

从重新实现[QGraphicsItem.itemChange](qgraphicsitem.html#itemChange)（ ） 。

```
QGraphicsProxyWidget.keyPressEvent (self, QKeyEvent event)
```

从重新实现[QGraphicsItem.keyPressEvent](qgraphicsitem.html#keyPressEvent)（ ） 。

```
QGraphicsProxyWidget.keyReleaseEvent (self, QKeyEvent event)
```

从重新实现[QGraphicsItem.keyReleaseEvent](qgraphicsitem.html#keyReleaseEvent)（ ） 。

```
QGraphicsProxyWidget.mouseDoubleClickEvent (self, QGraphicsSceneMouseEvent event)
```

从重新实现[QGraphicsItem.mouseDoubleClickEvent](qgraphicsitem.html#mouseDoubleClickEvent)（ ） 。

```
QGraphicsProxyWidget.mouseMoveEvent (self, QGraphicsSceneMouseEvent event)
```

从重新实现[QGraphicsItem.mouseMoveEvent](qgraphicsitem.html#mouseMoveEvent)（ ） 。

```
QGraphicsProxyWidget.mousePressEvent (self, QGraphicsSceneMouseEvent event)
```

从重新实现[QGraphicsItem.mousePressEvent](qgraphicsitem.html#mousePressEvent)（ ） 。

```
QGraphicsProxyWidget.mouseReleaseEvent (self, QGraphicsSceneMouseEvent event)
```

从重新实现[QGraphicsItem.mouseReleaseEvent](qgraphicsitem.html#mouseReleaseEvent)（ ） 。

```
QGraphicsProxyWidget QGraphicsProxyWidget.newProxyWidget (self, QWidget)
```

[

创建一个代理部件给定的_child_包含在这个代理的小工具。

](qgraphicsproxywidget.html)

[你不应该直接调用此函数;使用](qgraphicsproxywidget.html)[QGraphicsProxyWidget.createProxyForChildWidget](qgraphicsproxywidget.html#createProxyForChildWidget)（ ）来代替。

此功能是假的虚拟插槽，你可以在你的子类重新实现，以控制如何将新的代理部件被创建。默认实现返回与创建一个代理[QGraphicsProxyWidget](qgraphicsproxywidget.html#QGraphicsProxyWidget)（ ）构造函数与此代理插件作为父。

此功能被引入Qt的4.5 。

**See also** [createProxyForChildWidget](qgraphicsproxywidget.html#createProxyForChildWidget)（ ） 。

```
QGraphicsProxyWidget.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QGraphicsProxyWidget.resizeEvent (self, QGraphicsSceneResizeEvent event)
```

从重新实现[QGraphicsWidget.resizeEvent](qgraphicswidget.html#resizeEvent)（ ） 。

```
QGraphicsProxyWidget.setGeometry (self, QRectF rect)
```

从重新实现[QGraphicsLayoutItem.setGeometry](qgraphicslayoutitem.html#setGeometry)（ ） 。

```
QGraphicsProxyWidget.setWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

Embeds _widget_这个代理部件。嵌入式构件必须完全位于内部或图形视图之外。你不能嵌入一个小部件，只要它是在UI别处可见，在相同的时间。

_widget_必须是一个顶级窗口部件，其母公司为0 。

当小部件是嵌入式的，它的状态（例如，可见，启用，几何形状，大小的提示）复制到代理服务器控件。如果嵌入式部件被明确隐藏或禁用，代理部件将成为明确地隐藏或禁用嵌入完成后。类文档有一个完整的概述共享状态。

[QGraphicsProxyWidget](qgraphicsproxywidget.html)的窗口标志确定是否小部件，嵌入后，将获得的窗口装饰与否。

在此之后函数返回，[QGraphicsProxyWidget](qgraphicsproxywidget.html)将保持其状态与同步_widget_只要有可能。

如果一个部件已经嵌入了这个代理，当这个函数被调用，即部件将首先自动未嵌入。传递0的_widget_争吵只会解除嵌入的控件，和当前嵌入式部件的所有权将被传递给调用者。嵌入每个子部件也将被嵌入和他们的代理部件损坏。

需要注意的是小部件与[Qt.WA_PaintOnScreen](qt.html#WidgetAttribute-enum)部件属性集和部件的包装外部应用程序或控制器无法嵌入。例子是[QGLWidget](qglwidget.html)和[QAxWidget](index.htm)。

**See also** [widget](qgraphicsproxywidget.html#widget)（ ） 。

```
QGraphicsProxyWidget.showEvent (self, QShowEvent event)
```

从重新实现[QGraphicsWidget.showEvent](qgraphicswidget.html#showEvent)（ ） 。

```
QSizeF QGraphicsProxyWidget.sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())
```

[](qsizef.html)

[从重新实现](qsizef.html)[QGraphicsLayoutItem.sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QRectF QGraphicsProxyWidget.subWidgetRect (self, QWidget widget)
```

[](qrectf.html)

[返回矩形_widget_，它必须是一个后裔](qrectf.html)[widget](qgraphicsproxywidget.html#widget)（） ，或[widget](qgraphicsproxywidget.html#widget)（ ）本身，这个代理项目的本地坐标。

如果没有部件被嵌入_widget_为0，或_widget_是不是嵌入部件的后裔，这个函数返回一个空[QRectF](qrectf.html)。

**See also** [widget](qgraphicsproxywidget.html#widget)（ ） 。

```
int QGraphicsProxyWidget.type (self)
```

从重新实现[QGraphicsItem.type](qgraphicsitem.html#type)（ ） 。

```
QGraphicsProxyWidget.ungrabMouseEvent (self, QEvent event)
```

从重新实现[QGraphicsWidget.ungrabMouseEvent](qgraphicswidget.html#ungrabMouseEvent)（ ） 。

```
QGraphicsProxyWidget.wheelEvent (self, QGraphicsSceneWheelEvent event)
```

从重新实现[QGraphicsItem.wheelEvent](qgraphicsitem.html#wheelEvent)（ ） 。

```
QWidget QGraphicsProxyWidget.widget (self)
```

[

返回一个指向嵌入的部件。

](qwidget.html)

[**See also**](qwidget.html) [setWidget](qgraphicsproxywidget.html#setWidget)（ ） 。