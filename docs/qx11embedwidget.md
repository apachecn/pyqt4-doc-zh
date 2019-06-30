# QX11EmbedWidget Class Reference

## [[QtGui](index.htm) module]

该QX11EmbedWidget类提供了一个XEMBED客户端插件。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum Error { Unknown, Internal, InvalidWindowID }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `int containerWinId (self)`
*   `embedInto (self, int id)`
*   `Error error (self)`
*   `bool event (self, QEvent)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `resizeEvent (self, QResizeEvent)`

### Qt Signals

*   `void containerClosed ()`
*   `void embedded ()`
*   `void error (QX11EmbedWidget::Error)`

* * *

## Detailed Description

该QX11EmbedWidget类提供了一个XEMBED客户端插件。

XEMBED是支持从一个应用程序中的窗口小部件的嵌入到另一个应用程序的X11协议。

一个XEMBED_client widget_是嵌入到一个窗口_container_。容器是图形的位置嵌入（或_swallows_）外部应用程序。

QX11EmbedWidget是用于编写小程序XEMBED或插件窗口小部件。当它已经嵌入与容器接收标籤焦点，焦点被传递到窗口小部件。当部件达到其焦点链的末端，焦点被传递回容器中。窗口激活，加速器的支持，模式和拖放（ XDND ）也被处理。

窗口小部件和容器可以同时发起的嵌入。如果部件是发起者，它希望将自己嵌入到容器的X11窗口的ID必须被传递给[embedInto](qx11embedwidget.html#embedInto)（ ） 。

如果容器发起的嵌入，嵌入的小部件的窗口ID必须是已知的。容器调用嵌入（ ） ，通过窗口ID 。

这个例子表明，嵌入了一个QX11EmbedWidget子类到其ID传递作为命令行参数的窗口的应用程序：

```
 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html) app(argc, argv);

     if (app.arguments().count() != 2) {
         qFatal("Error - expected window id as argument");
         return 1;
     }

     [QString](qstring.html) windowId(app.arguments()[1]);
     EmbedWidget window;
     window.embedInto(windowId.toULong());
     window.show();

     return app.exec();
 }

```

获取窗口ID的问题往往是由容器调用，它提供了插件的应用程序作为一个单独的进程（如面板调用停靠的小程序） ，通过它的窗口的ID给新进程的命令行参数解决。那么新进程可以调用[embedInto](qx11embedwidget.html#embedInto)（）与容器的窗口ID ，如图所示在上面的例子中的代码。类似地，新方法可以通过IPC到容器报告其窗口ID ，在这种情况下，容器可以嵌入部件。

当部件已经被嵌入，它发出的信号[embedded](qx11embedwidget.html#embedded)（ ） 。如果它是由在容器关闭时，小窗口发射[containerClosed](qx11embedwidget.html#containerClosed)（ ） 。如果嵌入时出现错误，[error](qx11embedwidget.html#error)（）被发射。

有可用于KDE和GTK + XEMBED部件。 GTK +的当量QX11EmbedWidget是GtkPlug组件。相应的KDE 3的部件被称为QXEmbed 。

* * *

## Type Documentation

```
QX11EmbedWidget.Error
```

| Constant | Value | Description |
| --- | --- | --- |
| `QX11EmbedWidget.Unknown` | `0` | 出现无法识别的错误。 |
| `QX11EmbedWidget.InvalidWindowID` | `2` | 容器的X11窗口ID是无效的。此错误通常是通过传递一个无效的窗口ID来触发[embedInto](qx11embedwidget.html#embedInto)（ ） 。 |

* * *

## Method Documentation

```
QX11EmbedWidget.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QX11EmbedWidget](qx11embedwidget.html)与给定对象_parent_。

```
int QX11EmbedWidget.containerWinId (self)
```

如果窗口部件被嵌入时，返回该容器的窗口ID ; otherwize返回0。

```
QX11EmbedWidget.embedInto (self, int id)
```

当该功能被调用时，插件本身嵌入到容器中的窗口编号是_id_。

If _id_ is _not_容器的窗口ID这个函数的行为不可预测。

```
Error QX11EmbedWidget.error (self)
```

[

返回上次发生错误的类型。这是由误差（）信号发射相同的错误代码。

](qx11embedwidget.html#Error-enum)

[**See also**](qx11embedwidget.html#Error-enum) [Error](qx11embedwidget.html#Error-enum)。

```
bool QX11EmbedWidget.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QX11EmbedWidget.eventFilter (self, QObject, QEvent)
```

```
QX11EmbedWidget.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

* * *

## Qt Signal Documentation

```
void containerClosed ()
```

这是该信号的默认超载。

这个信号是由客户端插件射出当容器关闭该窗口小部件。如果容器本身关闭这可能发生，或者如果控件将被拒绝。

该容器可以拒绝一个部件以任何理由，但是拒绝的最常见的原因是当试图以嵌入一个插件到已嵌入的部件的容器。

```
void embedded ()
```

这是该信号的默认超载。

这个信号是由已被嵌入由XEMBED容器的部件射出。

```
void error (QX11EmbedWidget::Error)
```

这是该信号的默认超载。

这个信号被发射，如果发生错误，如嵌入或与容器连通的结果。指定_error_描述发生的问题。

**See also** [QX11EmbedWidget.Error](qx11embedwidget.html#Error-enum)。