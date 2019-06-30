# QSplashScreen Class Reference

## [[QtGui](index.htm) module]

该QSplashScreen小工具提供了可以在应用程序启动时显示启动画面。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QPixmap pixmap = QPixmap(), Qt.WindowFlags flags = 0)`
*   `__init__ (self, QWidget parent, QPixmap pixmap = QPixmap(), Qt.WindowFlags flags = 0)`
*   `clearMessage (self)`
*   `drawContents (self, QPainter painter)`
*   `bool event (self, QEvent e)`
*   `finish (self, QWidget w)`
*   `mousePressEvent (self, QMouseEvent)`
*   `QPixmap pixmap (self)`
*   `repaint (self)`
*   `setPixmap (self, QPixmap pixmap)`
*   `showMessage (self, QString message, int alignment = Qt.AlignLeft, QColor color = Qt.black)`

### Qt Signals

*   `void messageChanged (const QString&)`

* * *

## Detailed Description

该QSplashScreen小工具提供了可以在应用程序启动时显示启动画面。

启动画面是当一个应用程序被启动，通常是显示一个小部件。闪屏通常用于应用程序早就启动时间（如数据库或需要时间来建立连接的网络应用程序）向用户提供反馈，该应用程序加载。

在启动画面出现在屏幕中央。它可能是有用的添加[Qt.WindowStaysOnTopHint](qt.html#WindowType-enum)在飞溅小部件的窗口标志，如果你想保留它上面的所有桌面上的其他窗口。

有些X11窗口管理器不支持标志“之上停留” 。一个解决办法是设置一个定期调用一个计时器[raise_](qwidget.html#raise)（ ）闪屏模拟“停留在顶部”的效果上。

最常见的用法是显示一个启动画面的主窗口部件被显示在屏幕上之前。说明了这一点，其中一个启动画面显示和一些初始化任务执行应用程序的主窗口显示之前，下面的代码片段：

```
 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html) app(argc, argv);
     [QPixmap](qpixmap.html) pixmap(":/splash.png");
     QSplashScreen splash(pixmap);
     splash.show();
     app.processEvents();
     ...
     [QMainWindow](qmainwindow.html) window;
     window.show();
     splash.finish(&window);
     return app.exec();
 }

```

用户可以通过点击鼠标隐藏的启动画面。由于之前的事件循环已经开始运行启动画面通常显示，它以定期调用是必要的[QApplication.processEvents](qcoreapplication.html#processEvents)（）接收的鼠标点击。

它来更新消息中的闪屏有时是有用的，例如，宣布建立或加载的应用程序模块启动时连接：

```
 [QPixmap](qpixmap.html) pixmap(":/splash.png");
 QSplashScreen *splash = new QSplashScreen(pixmap);
 splash->show();

 ... // Loading some items
 splash->showMessage("Loaded modules");

 qApp->processEvents();

 ... // Establishing connections
 splash->showMessage("Established connections");

 qApp->processEvents();

```

QSplashScreen支持此同[showMessage](qsplashscreen.html#showMessage)（）函数。如果你希望做自己的绘图，你可以得到一个指向在启动画面中使用的像素图与[pixmap](qsplashscreen.html#pixmap)（ ） 。或者，你可以继承QSplashScreen和重新实现[drawContents](qsplashscreen.html#drawContents)（ ） 。

* * *

## Method Documentation

```
QSplashScreen.__init__ (self, QPixmap pixmap = QPixmap(), Qt.WindowFlags flags = 0)
```

构造一个初始屏幕，将显示_pixmap_。

应该没有必要设置窗口部件标记，_f_，也许除了[Qt.WindowStaysOnTopHint](qt.html#WindowType-enum)。

```
QSplashScreen.__init__ (self, QWidget parent, QPixmap pixmap = QPixmap(), Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

这是一个重载函数。

此功能允许您指定一个父为您的启动画面。典型的使用此构造函数是，如果你有多个屏幕，并希望有闪屏不同的屏幕比你小一上。在这种情况下，通过适当的桌面（）中作为_parent_。

```
QSplashScreen.clearMessage (self)
```

这种方法也是一个Qt槽与C + +的签名`void clearMessage()`。

删除所显示的初始屏幕上的消息

**See also** [showMessage](qsplashscreen.html#showMessage)（ ） 。

```
QSplashScreen.drawContents (self, QPainter painter)
```

用画家绘制的启动画面中的内容_painter_。默认实现绘制由传递消息[showMessage](qsplashscreen.html#showMessage)（ ） 。如果你想要做自己的绘图启动画面上重新实现这个函数。

```
bool QSplashScreen.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QSplashScreen.finish (self, QWidget w)
```

让启动画面等到小部件_mainWin_呼叫前显示[close](qwidget.html#close)（ ）自身。

```
QSplashScreen.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QPixmap QSplashScreen.pixmap (self)
```

[](qpixmap.html)

[返回用于在启动画面的像素图。图像没有任何被绘制文本](qpixmap.html)[showMessage](qsplashscreen.html#showMessage)（ ）调用。

**See also** [setPixmap](qsplashscreen.html#setPixmap)（ ） 。

```
QSplashScreen.repaint (self)
```

这将复盖[QWidget.repaint](qwidget.html#repaint)（ ） 。其不同之处在于它也调用标准重绘函数[QApplication.flush](qcoreapplication.html#flush)（） ，以确保所显示的更新时，甚至当没有事件循环存在。

```
QSplashScreen.setPixmap (self, QPixmap pixmap)
```

设置将用作启动画面的图像的像素图_pixmap_。

**See also** [pixmap](qsplashscreen.html#pixmap)（ ） 。

```
QSplashScreen.showMessage (self, QString message, int alignment = Qt.AlignLeft, QColor color = Qt.black)
```

这种方法也是一个Qt槽与C + +的签名`void showMessage(const QString&,int = Qt.AlignLeft,const QColor& = Qt.black)`。

绘制_message_文字上有颜色的闪屏_color_和对齐根据在标志的文本_alignment_。

为了确保在启动画面立即重绘，你可以调用[QCoreApplication](qcoreapplication.html)的[processEvents()](qcoreapplication.html#processEvents)调用showMessage （）之后。通常你想这确保该消息被不断更新与你的应用程序在做（例如，加载文件） 。

**See also** [Qt.Alignment](qt.html#AlignmentFlag-enum)和[clearMessage](qsplashscreen.html#clearMessage)（ ） 。

* * *

## Qt Signal Documentation

```
void messageChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时，在启动画面变化的消息。_message_是新的消息，当该消息已被删除一个空字符串。

**See also** [showMessage](qsplashscreen.html#showMessage)（）和[clearMessage](qsplashscreen.html#clearMessage)（ ） 。