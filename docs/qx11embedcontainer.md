# QX11EmbedContainer Class Reference

## [[QtGui](index.htm) module]

该QX11EmbedContainer类提供了一个XEMBED容器部件。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum Error { Unknown, Internal, InvalidWindowID }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `int clientWinId (self)`
*   `discardClient (self)`
*   `embedClient (self, int id)`
*   `Error error (self)`
*   `bool event (self, QEvent)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `hideEvent (self, QHideEvent)`
*   `QSize minimumSizeHint (self)`
*   `paintEvent (self, QPaintEvent e)`
*   `resizeEvent (self, QResizeEvent)`
*   `showEvent (self, QShowEvent)`

### Qt Signals

*   `void clientClosed ()`
*   `void clientIsEmbedded ()`
*   `void error (QX11EmbedContainer::Error)`

* * *

## Detailed Description

该QX11EmbedContainer类提供了一个XEMBED容器部件。

XEMBED是支持从一个应用程序中的窗口小部件的嵌入到另一个应用程序的X11协议。

一个XEMBED_container_是图形的位置嵌入外部_client widget_。客户端插件是嵌入到容器中的一个窗口。

当一个部件被嵌入与容器接收标籤焦点，焦点被传递到窗口小部件。当部件达到其焦点链的末端，焦点被传递回容器中。窗口激活，加速器的支持，模式和拖放（ XDND ）也被处理。

QX11EmbedContainer通常用于书写板或工具栏持有小程序，或_swallowing_X11应用程序。当写一个面板应用程序，一个容器小部件工具栏上创建的，然后它可以吞下使用嵌入另一个控件（ ） ，或允许XEMBED小工具嵌入到自己。容器的X11窗口的ID ，这是与检索[winId](qwidget.html#winId)（） ，然后必须知道的客户端插件。嵌入后，客户端的窗口ID可以检索与[clientWinId](qx11embedcontainer.html#clientWinId)（ ） 。

在下面的例子中，一个容器控件被创建为主要部件。然后，它调用名为“ playmovie ”的应用程序，通过它的窗口ID作为命令行参数。在“ playmovie ”计划是一个XEMBED客户端插件。该插件嵌入自身到使用容器的窗口ID的容器。

```
 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html) app(argc, argv);

     if (app.arguments().count() != 2) {
         qFatal("Error - expected executable path as argument");
         return 1;
     }

     QX11EmbedContainer container;
     container.show();

     [QProcess](qprocess.html) process(&container);
     [QString](qstring.html) executable(app.arguments()[1]);
     [QStringList](qstringlist.html) arguments;
     arguments << [QString](qstring.html).number(container.winId());
     process.start(executable, arguments);

     int status = app.exec();
     process.close();
     return status;
 }

```

当客户端插件被嵌入时，容器会发出信号[clientIsEmbedded](qx11embedcontainer.html#clientIsEmbedded)（ ） 。信号[clientClosed](qx11embedcontainer.html#clientClosed)（）当一个部件被关闭射出。

这是可能的QX11EmbedContainer从工具包比其他的Qt ，比如GTK +的嵌入XEMBED部件。任意（非XEMBED ） X11的部件也可以嵌入，但XEMBED特定的功能，如窗口激活并集中处理，然后消失。

GTK +的当量QX11EmbedContainer是GtkSocket容器，另外。相应的KDE 3的部件被称为QXEmbed 。

* * *

## Type Documentation

```
QX11EmbedContainer.Error
```

| Constant | Value | Description |
| --- | --- | --- |
| `QX11EmbedContainer.Unknown` | `0` | 出现无法识别的错误。 |
| `QX11EmbedContainer.InvalidWindowID` | `2` | 容器的X11窗口ID是无效的。此错误通常是通过传递一个无效的窗口ID嵌入（ ）触发。 |

* * *

## Method Documentation

```
QX11EmbedContainer.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QX11EmbedContainer](qx11embedcontainer.html)与给定对象_parent_。

```
int QX11EmbedContainer.clientWinId (self)
```

如果容器有一个嵌入的控件，该函数返回客户端的X11窗口的ID ，否则返回0 。

```
QX11EmbedContainer.discardClient (self)
```

分离客户端从嵌入。客户端会出现在桌面上的独立窗口。

```
QX11EmbedContainer.embedClient (self, int id)
```

指示容器嵌入X11窗口与窗口ID_id_。该客户端插件将移动的容器窗口的顶部，并调整大小以适合容器。

该_id_应该是由一个启用XEMBED应用所控制的窗口的ID，但这不是强制性的。如果_id_不属于一个XEMBED客户端控件，然后集中处理，活化，加速器和其他功能将无法正常工作。

```
Error QX11EmbedContainer.error (self)
```

[

返回所发生的最后一个错误。

```
bool QX11EmbedContainer.event (self, QEvent)
```

](qx11embedcontainer.html#Error-enum)

[从重新实现](qx11embedcontainer.html#Error-enum)[QObject.event](qobject.html#event)（ ） 。

```
bool QX11EmbedContainer.eventFilter (self, QObject, QEvent)
```

```
QX11EmbedContainer.hideEvent (self, QHideEvent)
```

```
QSize QX11EmbedContainer.minimumSizeHint (self)
```

[

```
QX11EmbedContainer.paintEvent (self, QPaintEvent e)
```

](qsize.html)

[从重新实现](qsize.html)[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QX11EmbedContainer.resizeEvent (self, QResizeEvent)
```

```
QX11EmbedContainer.showEvent (self, QShowEvent)
```

* * *

## Qt Signal Documentation

```
void clientClosed ()
```

这是该信号的默认超载。

这个信号是由所述容器射出的客户端插件关闭时。

```
void clientIsEmbedded ()
```

这是该信号的默认超载。

这个信号是由当客户端插件已经被嵌入所述容器射出。

```
void error (QX11EmbedContainer::Error)
```

这是该信号的默认超载。

这个信号被发射，如果嵌入或与客户端进行通信时发生了错误。指定_error_描述发生的问题。

**See also** [QX11EmbedContainer.Error](qx11embedcontainer.html#Error-enum)。