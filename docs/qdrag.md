# QDrag Class Reference

## [[QtGui](index.htm) module]

该QDrag类提供了基于MIME的拖放支持拖放的数据传输。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QWidget dragSource)`
*   `Qt.DropAction exec (self, Qt.DropActions supportedActions, Qt.DropAction defaultDropAction)`
*   `Qt.DropAction exec_ (self, Qt.DropActions supportedActions = Qt.MoveAction)`
*   `Qt.DropAction exec_ (self, Qt.DropActions supportedActions, Qt.DropAction defaultDropAction)`
*   `QPoint hotSpot (self)`
*   `QMimeData mimeData (self)`
*   `QPixmap pixmap (self)`
*   `setDragCursor (self, QPixmap cursor, Qt.DropAction action)`
*   `setHotSpot (self, QPoint hotspot)`
*   `setMimeData (self, QMimeData data)`
*   `setPixmap (self, QPixmap)`
*   `QWidget source (self)`
*   `Qt.DropAction start (self, Qt.DropActions supportedActions = Qt.CopyAction)`
*   `QWidget target (self)`

### Qt Signals

*   `void actionChanged (Qt::DropAction)`
*   `void targetChanged (QWidget *)`

* * *

## Detailed Description

该QDrag类提供了基于MIME的拖放支持拖放的数据传输。

拖放是一种直观的方式为用户在应用程序中各地复制或移动数据，并且被用在许多桌面环境作为一种机制来复制应用程序之间的数据。拖动和Qt中的拖放支持是围绕该处理大部分的拖放操作的细节QDrag类。

通过拖放操作要传输的数据被包含在一个[QMimeData](qmimedata.html)对象。这是指定的[setMimeData](qdrag.html#setMimeData)（）函数以下面的方式：

```
         QDrag *drag = new QDrag(this);
         [QMimeData](qmimedata.html) *mimeData = new [QMimeData](qmimedata.html);

         mimeData->setText(commentEdit->toPlainText());
         drag->setMimeData(mimeData);

```

需要注意的是[setMimeData](qdrag.html#setMimeData)（ ）分配的所有权[QMimeData](qmimedata.html)反对QDrag对象。该QDrag必须在堆上与父构造[QWidget](qwidget.html)确保Qt可以拖动后清理和删除操作已经完成。

一个像素图可以用来表示数据，而拖动操作正在进行，并将光标移动到放置目标。这个像素图通常显示一个图标，表示该MIME类型正在传送的数据的，但任何像素映像可以被设置[setPixmap](qdrag.html#setPixmap)（ ） 。光标的热点可以给出相对位置一个与该像素图的左上角[setHotSpot](qdrag.html#setHotSpot)（）函数。下面的代码位置的像素图，使光标的热点点，其底边的中心：

```
     drag->setHotSpot([QPoint](qpoint.html)(drag->pixmap().width()/2,
                             drag->pixmap().height()));

```

**Note:**在X11上，像素图可能无法跟上鼠标移动，如果热点直接导致光标下要显示的像素图。

源和目标部件可与发现[source](qdrag.html#source)（）和[target](qdrag.html#target)（ ） 。这些功能通常是用来确定是否拖放操作开始和结束于相同的部件，因此，特殊的行为可以被实现。

QDrag只处理拖放操作本身。它是由开发人员来决定拖动操作开始时，以及如何QDrag对象应该被构建和使用。对于给定窗口小部件，它通常需要重新实现[mousePressEvent()](qwidget.html#mousePressEvent)确定用户是否按下鼠标按钮，并重新实现[mouseMoveEvent()](qwidget.html#mouseMoveEvent)检查一个QDrag是否是必需的。

* * *

## Method Documentation

```
QDrag.__init__ (self, QWidget dragSource)
```

该_dragSource_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的拖动对象通过指定的窗口小部件_dragSource_。

```
Qt.DropAction QDrag.exec (self, Qt.DropActions supportedActions, Qt.DropAction defaultDropAction)
```

[

开始拖放操作，并返回一个值，指示请求的拖放操作何时完成。下拉的动作，用户可以选择在指定_supportedActions_。默认建议的行动会按以下顺序允许的动作中进行选择：移动，复制和链接。

**Note:**在Linux和Mac OS X上，拖放操作可能需要一些时间，但这个功能不会阻止事件循环。其他事件仍传送到应用程序，同时执行操作。在Windows上， Qt的事件循环的操作过程中受阻时。

此功能被引入Qt的4.3 。

](qt.html#DropAction-enum)

```
Qt.DropAction QDrag.exec_ (self, Qt.DropActions supportedActions = Qt.MoveAction)
```

[

开始拖放操作，并返回一个值，指示请求的拖放操作何时完成。下拉的动作，用户可以选择在指定_supportedActions_。默认建议的行动会按以下顺序允许的动作中进行选择：移动，复制和链接。

**Note:**在Linux和Mac OS X上，拖放操作可能需要一些时间，但这个功能不会阻止事件循环。其他事件仍传送到应用程序，同时执行操作。在Windows上， Qt的事件循环的操作过程中受阻时。

此功能被引入Qt的4.3 。

](qt.html#DropAction-enum)

```
Qt.DropAction QDrag.exec_ (self, Qt.DropActions supportedActions, Qt.DropAction defaultDropAction)
```

[

开始拖放操作，并返回一个值，指示请求的拖放操作何时完成。下拉的动作，用户可以选择在指定_supportedActions_。

该_defaultDropAction_决定当用户执行一拖而不使用组合键的操作将被提出。

](qt.html#DropAction-enum)

[**Note:**在Linux和Mac OS X上，拖放操作可能需要一些时间，但这个功能不会阻止事件循环。其他事件仍传送到应用程序，同时执行操作。在Windows上， Qt的事件循环的操作过程中受阻。但是，](qt.html#DropAction-enum)[QDrag.exec](qdrag.html#exec)（ ）在Windows上导致processEvents （ ）被频繁调用，以保证GUI作出响应。如果有任何循环或操作被调用，而拖动操作是积极的，它会阻止拖动操作。

此功能被引入Qt的4.3 。

```
QPoint QDrag.hotSpot (self)
```

[

返回到光标的左上角相对于热点的位置。

](qpoint.html)

[**See also**](qpoint.html) [setHotSpot](qdrag.html#setHotSpot)（ ） 。

```
QMimeData QDrag.mimeData (self)
```

[

返回由所述拖动对象所封装的MIME数据。

](qmimedata.html)

[**See also**](qmimedata.html) [setMimeData](qdrag.html#setMimeData)（ ） 。

```
QPixmap QDrag.pixmap (self)
```

[

返回用于表示在拖动的数据拖放操作的像素图。

](qpixmap.html)

[**See also**](qpixmap.html) [setPixmap](qdrag.html#setPixmap)（ ） 。

```
QDrag.setDragCursor (self, QPixmap cursor, Qt.DropAction action)
```

设置拖动_cursor_为_action_。这使您可以复盖默认的本地游标。要恢复到使用本地光标_action_传递一个空[QPixmap](qpixmap.html)如_cursor_。

该_action_只能是CopyAction ， MoveAction或LinkAction 。 DropAction的所有其他值将被忽略。

```
QDrag.setHotSpot (self, QPoint hotspot)
```

设定相对于热点的位置，以用于通过指定的点的像素图的左上角_hotspot_。

**Note:**在X11上，像素图可能无法跟上鼠标移动，如果热点直接导致光标下要显示的像素图。

**See also** [hotSpot](qdrag.html#hotSpot)（ ） 。

```
QDrag.setMimeData (self, QMimeData data)
```

该_data_说法有它的所有权转移给Qt的。

设置要发送到给定的MIME数据_data_。该数据的所有权被转移到[QDrag](qdrag.html)对象。

**See also** [mimeData](qdrag.html#mimeData)（ ） 。

```
QDrag.setPixmap (self, QPixmap)
```

Sets _pixmap_作为像素图用来表示在一个拖动数据拖放操作。你可以拖动操作开始之前，只设置一个像素图。

**See also** [pixmap](qdrag.html#pixmap)（ ） 。

```
QWidget QDrag.source (self)
```

[

返回拖动对象的源。这是其中的拖放操作起源的部件。

](qwidget.html)

```
Qt.DropAction QDrag.start (self, Qt.DropActions supportedActions = Qt.CopyAction)
```

[](qt.html#DropAction-enum)

```
QWidget QDrag.target (self)
```

[

返回拖放操作的目标。这是一个小部件，这是拖动物体跌。

* * *

## Qt Signal Documentation

```
void actionChanged (Qt::DropAction)
```

这是该信号的默认超载。

这个信号被发射时的_action_与拖变化有关。

](qwidget.html)

[**See also**](qwidget.html) [targetChanged](qdrag.html#targetChanged)（ ） 。

```
void targetChanged (QWidget *)
```

这是该信号的默认超载。

这个信号被发射时的拖放操作改变目标，以_newTarget_新的目标。

**See also** [target](qdrag.html#target)（）和[actionChanged](qdrag.html#actionChanged)（ ） 。