# QApplication Class Reference

## [[QtGui](index.htm) module]

该的QApplication类管理图形用户界面应用程序的控制流和主要设置。[More...](#details)

继承[QCoreApplication](qcoreapplication.html)。

### Types

*   `enum ColorSpec { NormalColor, CustomColor, ManyColor }`
*   `enum Type { Tty, GuiClient, GuiServer }`

### Methods

*   `__init__ (self, list-of-str argv)`
*   `__init__ (self, list-of-str argv, bool GUIenabled)`
*   `__init__ (self, list-of-str argv, Type)`
*   `__init__ (self, Display display, int visual = 0, int colormap = 0)`
*   `__init__ (self, Display dpy, list-of-str argv, int visual = 0, int cmap = 0)`
*   `bool autoSipEnabled (self)`
*   `commitData (self, QSessionManager sm)`
*   `bool event (self, QEvent)`
*   `QInputContext inputContext (self)`
*   `bool isSessionRestored (self)`
*   `bool notify (self, QObject, QEvent)`
*   `saveState (self, QSessionManager sm)`
*   `QString sessionId (self)`
*   `QString sessionKey (self)`
*   `setAutoSipEnabled (self, bool enabled)`
*   `setInputContext (self, QInputContext)`
*   `setStyleSheet (self, QString sheet)`
*   `QString styleSheet (self)`
*   `bool x11EventFilter (self, sip.voidptr)`
*   `int x11ProcessEvent (self, sip.voidptr)`

### Static Methods

*   `aboutQt ()`
*   `QWidget activeModalWidget ()`
*   `QWidget activePopupWidget ()`
*   `QWidget activeWindow ()`
*   `alert (QWidget widget, int msecs = 0)`
*   `list-of-QWidget allWidgets ()`
*   `beep ()`
*   `changeOverrideCursor (QCursor)`
*   `QClipboard clipboard ()`
*   `closeAllWindows ()`
*   `int colorSpec ()`
*   `int cursorFlashTime ()`
*   `QDesktopWidget desktop ()`
*   `bool desktopSettingsAware ()`
*   `int doubleClickInterval ()`
*   `int exec_ ()`
*   `QWidget focusWidget ()`
*   `QFont font ()`
*   `QFont font (QWidget)`
*   `QFont font (str className)`
*   `QFontMetrics fontMetrics ()`
*   `QSize globalStrut ()`
*   `bool isEffectEnabled (Qt.UIEffect)`
*   `bool isLeftToRight ()`
*   `bool isRightToLeft ()`
*   `Qt.LayoutDirection keyboardInputDirection ()`
*   `int keyboardInputInterval ()`
*   `QLocale keyboardInputLocale ()`
*   `Qt.KeyboardModifiers keyboardModifiers ()`
*   `Qt.LayoutDirection layoutDirection ()`
*   `Qt.MouseButtons mouseButtons ()`
*   `QCursor overrideCursor ()`
*   `QPalette palette ()`
*   `QPalette palette (QWidget)`
*   `QPalette palette (str className)`
*   `Qt.KeyboardModifiers queryKeyboardModifiers ()`
*   `bool quitOnLastWindowClosed ()`
*   `restoreOverrideCursor ()`
*   `setActiveWindow (QWidget act)`
*   `setColorSpec (int)`
*   `setCursorFlashTime (int)`
*   `setDesktopSettingsAware (bool)`
*   `setDoubleClickInterval (int)`
*   `setEffectEnabled (Qt.UIEffect effect, bool enabled = True)`
*   `setFont (QFont font, str className = None)`
*   `setGlobalStrut (QSize)`
*   `setGraphicsSystem (QString)`
*   `setKeyboardInputInterval (int)`
*   `setLayoutDirection (Qt.LayoutDirection direction)`
*   `setOverrideCursor (QCursor)`
*   `setPalette (QPalette palette, str className = None)`
*   `setQuitOnLastWindowClosed (bool quit)`
*   `setStartDragDistance (int l)`
*   `setStartDragTime (int ms)`
*   `setStyle (QStyle)`
*   `QStyle setStyle (QString)`
*   `setWheelScrollLines (int)`
*   `setWindowIcon (QIcon icon)`
*   `int startDragDistance ()`
*   `int startDragTime ()`
*   `QStyle style ()`
*   `syncX ()`
*   `QWidget topLevelAt (QPoint p)`
*   `QWidget topLevelAt (int x, int y)`
*   `list-of-QWidget topLevelWidgets ()`
*   `Type type ()`
*   `int wheelScrollLines ()`
*   `QWidget widgetAt (QPoint p)`
*   `QWidget widgetAt (int x, int y)`
*   `QIcon windowIcon ()`

### Qt Signals

*   `void commitDataRequest (QSessionManager&)`
*   `void focusChanged (QWidget *,QWidget *)`
*   `void fontDatabaseChanged ()`
*   `void lastWindowClosed ()`
*   `void saveStateRequest (QSessionManager&)`

* * *

## Detailed Description

该的QApplication类管理图形用户界面应用程序的控制流和主要设置。

的QApplication包含主事件循环，其中来自窗口系统和其他来源的所有事件被处理和调度。它也处理应用程序的初始化，最后定稿，并提供会话管理。此外，的QApplication处理大部分的系统范围和应用范围的设置。

对于使用Qt的任何GUI应用程序，有正**one**QApplication对象，无论应用程序是否具有0 ，1，2或更多个窗口在任何给定时间。对于非GUI Qt应用程序，使用[QCoreApplication](qcoreapplication.html)相反，因为它不依赖于[QtGui](index.htm)库。

QApplication对象是通过访问[instance](qcoreapplication.html#instance)（ ）函数返回一个指针相当于全球[qApp](index.htm#qApp-var)指针。

的QApplication的主要责任领域是：

*   It initializes the application with the user's desktop settings such as [palette](qapplication.html#palette)(), [font](qapplication.html#font)() and [doubleClickInterval](qapplication.html#doubleClickInterval-prop)(). It keeps track of these properties in case the user changes the desktop globally, for example through some kind of control panel.
*   It performs event handling, meaning that it receives events from the underlying window system and dispatches them to the relevant widgets. By using [sendEvent](qcoreapplication.html#sendEvent)() and [postEvent](qcoreapplication.html#postEvent)() you can send your own events to widgets.
*   It parses common command line arguments and sets its internal state accordingly. See the [constructor documentation](qapplication.html#QApplication) below for more details.
*   It defines the application's look and feel, which is encapsulated in a [QStyle](qstyle.html) object. This can be changed at runtime with [setStyle](qapplication.html#setStyle)().
*   It specifies how the application is to allocate colors. See [setColorSpec](qapplication.html#setColorSpec)() for details.
*   It provides localization of strings that are visible to the user via [translate](qcoreapplication.html#translate)().
*   It provides some magical objects like the [desktop](qapplication.html#desktop)() and the [clipboard](qapplication.html#clipboard)().
*   It knows about the application's windows. You can ask which widget is at a certain position using [widgetAt](qapplication.html#widgetAt)(), get a list of [topLevelWidgets](qapplication.html#topLevelWidgets)() and [closeAllWindows](qapplication.html#closeAllWindows)(), etc.
*   It manages the application's mouse cursor handling, see [setOverrideCursor](qapplication.html#setOverrideCursor)()
*   On the X window system, it provides functions to flush and sync the communication stream, see [flushX](index.htm#flushX)() and [syncX](qapplication.html#syncX)().
*   It provides support for sophisticated [session management](index.htm). This makes it possible for applications to terminate gracefully when the user logs out, to cancel a shutdown process if termination isn't possible and even to preserve the entire application's state for a future session. See [isSessionRestored](qapplication.html#isSessionRestored)(), [sessionId](qapplication.html#sessionId)() and [commitData](qapplication.html#commitData)() and [saveState](qapplication.html#saveState)() for details.

由于QApplication对象做了如此多的初始化，它_must_创建与用户界面的任何其他对象之前被创建。的QApplication也处理命令行参数。因此，它通常是一个好主意来创建它_before_任何解释或修改`argv`在该应用程序本身就完成了。

| Groups of functions |
| --- |
| System settings | [desktopSettingsAware](qapplication.html#desktopSettingsAware)(), [setDesktopSettingsAware](qapplication.html#setDesktopSettingsAware)(), [cursorFlashTime](qapplication.html#cursorFlashTime-prop)(), [setCursorFlashTime](qapplication.html#cursorFlashTime-prop)(), [doubleClickInterval](qapplication.html#doubleClickInterval-prop)(), [setDoubleClickInterval](qapplication.html#doubleClickInterval-prop)(), [setKeyboardInputInterval](qapplication.html#keyboardInputInterval-prop)(), [wheelScrollLines](qapplication.html#wheelScrollLines-prop)(), [setWheelScrollLines](qapplication.html#wheelScrollLines-prop)(), [palette](qapplication.html#palette)(), [setPalette](qapplication.html#setPalette)(), [font](qapplication.html#font)(), [setFont](qapplication.html#setFont)(), [fontMetrics](qapplication.html#fontMetrics)(). |
| Event handling | [exec_](qapplication.html#exec)(), [processEvents](qcoreapplication.html#processEvents)(), [exit](qcoreapplication.html#exit)(), [quit](qcoreapplication.html#quit)(). [sendEvent](qcoreapplication.html#sendEvent)(), [postEvent](qcoreapplication.html#postEvent)(), [sendPostedEvents](qcoreapplication.html#sendPostedEvents)(), [removePostedEvents](qcoreapplication.html#removePostedEvents)(), [hasPendingEvents](qcoreapplication.html#hasPendingEvents)(), [notify](qapplication.html#notify)(), [macEventFilter](qapplication.html#macEventFilter)(), [qwsEventFilter](qapplication.html#qwsEventFilter)(), [x11EventFilter](qapplication.html#x11EventFilter)(), [x11ProcessEvent](qapplication.html#x11ProcessEvent)(), [winEventFilter](qcoreapplication.html#winEventFilter)(). |
| GUI Styles | [style](qapplication.html#style)(), [setStyle](qapplication.html#setStyle)(). |
| Color usage | [colorSpec](qapplication.html#colorSpec)(), [setColorSpec](qapplication.html#setColorSpec)(), [qwsSetCustomColors](qapplication.html#qwsSetCustomColors)(). |
| Text handling | [installTranslator](qcoreapplication.html#installTranslator)(), [removeTranslator](qcoreapplication.html#removeTranslator)() [translate](qcoreapplication.html#translate)(). |
| Widgets | [allWidgets](qapplication.html#allWidgets)(), [topLevelWidgets](qapplication.html#topLevelWidgets)(), [desktop](qapplication.html#desktop)(), [activePopupWidget](qapplication.html#activePopupWidget)(), [activeModalWidget](qapplication.html#activeModalWidget)(), [clipboard](qapplication.html#clipboard)(), [focusWidget](qapplication.html#focusWidget)(), [activeWindow](qapplication.html#activeWindow)(), [widgetAt](qapplication.html#widgetAt)(). |
| Advanced cursor handling | [overrideCursor](qapplication.html#overrideCursor)(), [setOverrideCursor](qapplication.html#setOverrideCursor)(), [restoreOverrideCursor](qapplication.html#restoreOverrideCursor)(). |
| X Window System synchronization | [flushX](index.htm#flushX)(), [syncX](qapplication.html#syncX)(). |
| Session management | [isSessionRestored](qapplication.html#isSessionRestored)(), [sessionId](qapplication.html#sessionId)(), [commitData](qapplication.html#commitData)(), [saveState](qapplication.html#saveState)(). |
| Miscellaneous | [closeAllWindows](qapplication.html#closeAllWindows)(), [startingUp](qcoreapplication.html#startingUp)(), [closingDown](qcoreapplication.html#closingDown)(), [type](qapplication.html#type)(). |

* * *

## Type Documentation

```
QApplication.ColorSpec
```

| Constant | Value | Description |
| --- | --- | --- |
| `QApplication.NormalColor` | `0` | 默认的颜色分配策略 |
| `QApplication.CustomColor` | `1` | NormalColor一样的X11 ，在Windows下需要一个调色板颜色分配 |
| `QApplication.ManyColor` | `2` | 对于使用上千种颜色的应用的理想选择 |

See [setColorSpec](qapplication.html#setColorSpec)（ ）的全部细节。

```
QApplication.Type
```

| Constant | Value | Description |
| --- | --- | --- |
| `QApplication.Tty` | `0` | 一个控制台应用程序 |
| `QApplication.GuiClient` | `1` | 一个GUI客户端应用程序 |
| `QApplication.GuiServer` | `2` | 一个GUI服务器应用程序（ Qt嵌入式Linux的） |

* * *

## Method Documentation

```
QApplication.__init__ (self, list-of-str argv)
```

初始化窗口系统，并构造一个应用程序对象_argc_在命令行参数_argv_。

**Warning:**由所述资料_argc_和_argv_必须保持有效的整个生命周期[QApplication](qapplication.html)对象。另外，_argc_必须大于零和_argv_必须至少包含一个有效的字符串。

全球`qApp`指针指到这个应用程序对象。只有一个应用程序对象应该被创建。

此应用程序对象必须在任何构造[paint devices](qpaintdevice.html)（包括窗口小部件，像素图，位图等）。

**Note:** _argc_和_argv_作为Qt的删除，它承认命令行参数可能会改变。

Qt的调试选项（如果Qt未经定义的QT_DEBUG标志编译） ：

*   -nograb, tells Qt that it must never grab the mouse or the keyboard.
*   -dograb (only under X11), running under a debugger can cause an implicit -nograb, use -dograb to override.
*   -sync (only under X11), switches to synchronous mode for debugging.

See [Debugging Techniques](index.htm)对于更详细的解释。

所有Qt程序自动支持以下命令行选项：

*   -style= _style_, sets the application GUI style. Possible values are `motif`, `windows`, and `platinum`. If you compiled Qt with additional styles or have additional styles as plugins these will be available to the `-style` command line option.
*   -style _style_, is the same as listed above.
*   -stylesheet= _stylesheet_, sets the application [styleSheet](qapplication.html#styleSheet-prop). The value must be a path to a file that contains the Style Sheet. **Note:** Relative URLs in the Style Sheet file are relative to the Style Sheet file's path.
*   -stylesheet _stylesheet_, is the same as listed above.
*   -session= _session_, restores the application from an earlier [session](index.htm).
*   -session _session_, is the same as listed above.
*   -widgetcount, prints debug message at the end about number of widgets left undestroyed and maximum number of widgets existed at the same time
*   -reverse, sets the application's layout direction to [Qt.RightToLeft](qt.html#LayoutDirection-enum)
*   -graphicssystem, sets the backend to be used for on-screen widgets and QPixmaps. Available options are `raster` and `opengl`.
*   -qmljsdebugger=, activates the QML/JS debugger with a specified port. The value must be of format port:1234[,block], where block is optional and will make the application wait until a debugger connects to it.

在X11版本的Qt支持一些传统的X11命令行选项：

*   -display _display_, sets the X display (default is $DISPLAY).
*   -geometry _geometry_, sets the client geometry of the first window that is shown.
*   -fn or `-font` _font_, defines the application font. The font should be specified using an X logical font description. Note that this option is ignored when Qt is built with fontconfig support enabled.
*   -bg or `-background` _color_, sets the default background color and an application palette (light and dark shades are calculated).
*   -fg or `-foreground` _color_, sets the default foreground color.
*   -btn or `-button` _color_, sets the default button color.
*   -name _name_, sets the application name.
*   -title _title_, sets the application title.
*   -visual `TrueColor`, forces the application to use a TrueColor visual on an 8-bit display.
*   -ncols _count_, limits the number of colors allocated in the color cube on an 8-bit display, if the application is using the [QApplication.ManyColor](qapplication.html#ColorSpec-enum) color specification. If _count_ is 216 then a 6x6x6 color cube is used (i.e. 6 levels of red, 6 of green, and 6 of blue); for other values, a cube approximately proportional to a 2x3x1 cube is used.
*   -cmap, causes the application to install a private color map on an 8-bit display.
*   -im, sets the input method server (equivalent to setting the XMODIFIERS environment variable)
*   -inputstyle, defines how the input is inserted into the given widget, e.g., `onTheSpot` makes the input appear directly in the widget, while `overTheSpot` makes the input appear in a box floating over the widget and is not inserted until the editing is done.

#### X11 Notes

If [QApplication](qapplication.html)无法打开X11显示，它会终止进程。此行为与大多数X11应用程序是一致的。

**See also** [arguments](qcoreapplication.html#arguments)（ ） 。

```
QApplication.__init__ (self, list-of-str argv, bool GUIenabled)
```

构造一个应用程序对象_argc_在命令行参数_argv_。如果_GUIenabled_诚然，一个GUI应用程序的构造，否则非图形用户界面（控制台）应用程序创建的。

**Warning:**由所述资料_argc_和_argv_必须保持有效的整个生命周期[QApplication](qapplication.html)对象。另外，_argc_必须大于零和_argv_必须至少包含一个有效的字符串。

集_GUIenabled_为False，不，应该是能够在没有窗口系统上运行的图形用户界面程序。

在X11中，窗口系统，如果初始化_GUIenabled_是真实的。如果_GUIenabled_是假的，应用程序不连接到X服务器。在Windows和Mac OS ，现在窗口系统总是会被初始化，无论GUIenabled的价值。这可能会改变的Qt的未来版本。

下面的示例显示了如何创建一个使用图形界面时，可用的应用程序。

```
 int main(int argc, char **argv)
 {
 #ifdef Q_WS_X11
     bool useGUI = getenv("DISPLAY") != 0;
 #else
     bool useGUI = true;
 #endif
     [QApplication](qapplication.html) app(argc, argv, useGUI);

     if (useGUI) {
        // start GUI version
        ...
     } else {
        // start non-GUI version
        ...
     }
     return app.exec();
 }

```

```
QApplication.__init__ (self, list-of-str argv, Type)
```

构造一个应用程序对象_argc_在命令行参数_argv_。

**Warning:**由所述资料_argc_和_argv_必须保持有效的整个生命周期[QApplication](qapplication.html)对象。另外，_argc_必须大于零和_argv_必须至少包含一个有效的字符串。

与Qt嵌入式Linux的，路过[QApplication.GuiServer](qapplication.html#Type-enum)为_type_这使得应用程序的服务器（相当于与运行`-qws`选项）。

```
QApplication.__init__ (self, Display display, int visual = 0, int colormap = 0)
```

创建一个应用程序，给定一个已经打开的显示器_display_。如果_visual_和_colormap_非零，应用程序将使用这些值作为默认的Visual和Colormap上下文。

**Warning:**的Qt只支持TrueColor模式在深度大于8位每像素高。

此功能仅适用于X11 。

```
QApplication.__init__ (self, Display dpy, list-of-str argv, int visual = 0, int cmap = 0)
```

创建一个应用程序，给定一个已经打开_display_并使用_argc_在命令行参数_argv_。如果_visual_和_colormap_非零，应用程序将使用这些值作为默认的Visual和Colormap上下文。

**Warning:**的Qt只支持TrueColor模式在深度大于8位每像素高。

此功能仅适用于X11 。

```
QApplication.aboutQt ()
```

这种方法也是一个Qt槽与C + +的签名`void aboutQt()`。

显示关于Qt的一个简单的消息框。该消息包括对Qt的正在使用的应用程序的版本号。

这是纳入有用**Help**一个应用程序的菜单，如图中[Menus](index.htm)例子。

此函数是一个方便的槽，用于[QMessageBox.aboutQt](qmessagebox.html#aboutQt)（ ） 。

```
QWidget QApplication.activeModalWidget ()
```

[

返回有效的模态窗口小部件。

](qwidget.html)

[模态窗口小部件是一种特殊的顶级窗口部件这是一个子类](qwidget.html)[QDialog](qdialog.html)指定构造函数作为真正的模态参数。模态窗口小部件，必须关闭之前，用户可以继续使用该程序的其他部分。

模态窗口部件被组织在一个栈中。该函数返回有效的模态窗口小部件在堆栈的顶部。

**See also** [activePopupWidget](qapplication.html#activePopupWidget)（）和[topLevelWidgets](qapplication.html#topLevelWidgets)（ ） 。

```
QWidget QApplication.activePopupWidget ()
```

[

返回激活弹出窗口部件。

](qwidget.html)

[一个弹出窗口部件是一个特殊的顶级窗口部件设置`Qt.WType_Popup`小部件标志，例如该](qwidget.html)[QMenu](qmenu.html)小工具。当应用程序打开一个弹出式窗口小部件，所有事件都发送到弹出。前弹出窗口部件被关闭正常的部件和模态窗口部件不能被访问。

只有其他弹出窗口部件可以打开一个弹出式窗口小部件时显示。在弹出的窗口部件被组织在一个栈中。这个函数返回弹出窗口部件在堆栈的顶部。

**See also** [activeModalWidget](qapplication.html#activeModalWidget)（）和[topLevelWidgets](qapplication.html#topLevelWidgets)（ ） 。

```
QWidget QApplication.activeWindow ()
```

[](qwidget.html)

[返回应用程序顶层窗口拥有键盘输入焦点，或者0，如果没有应用程序窗口具有焦点。有可能是一个则activeWindow （ ），即使没有](qwidget.html)[focusWidget](qapplication.html#focusWidget)（ ） ，例如，如果该窗口没有窗口部件接收键盘事件。

**See also** [setActiveWindow](qapplication.html#setActiveWindow)（ ）[QWidget.setFocus](qwidget.html#setFocus)（ ）[QWidget.hasFocus](qwidget.html#focus-prop)（）和[focusWidget](qapplication.html#focusWidget)（ ） 。

```
QApplication.alert (QWidget widget, int msecs = 0)
```

导致警报显示为_widget_如果窗口不是活动窗口。警报显示为_msec_毫秒。如果_msec_为0（默认），则显示警报下去，直到窗口再次变得活跃。

目前，该函数不起作用的Qt嵌入式Linux操作系统。

在Mac OS X上，这个作品更在应用程序级别，并会导致应用程序图标在Dock上弹跳。

在Windows上，这会导致窗口的任务栏条目闪烁一段时间。如果_msec_是零，那么停止闪烁，并在任务栏条目将变成不同的颜色（目前橙色） 。

在X11 ，这会导致窗口被标记为“需要注意” ，窗口不能被隐藏（即没有隐藏（）调用它，但在某种方式中可见） ，为了这个工作。

此功能被引入Qt的4.3 。

```
list-of-QWidget QApplication.allWidgets ()
```

返回应用程序的所有窗口部件的列表。

该列表是空的（[QList.isEmpty](index.htm#isEmpty)（ ） ）如果没有小部件。

**Note:**一些小部件可能会被隐藏。

例如：

```
 void updateAllWidgets()
 {
     foreach ([QWidget](qwidget.html) *widget, [QApplication](qapplication.html).allWidgets())
         widget->update();
 }

```

**See also** [topLevelWidgets](qapplication.html#topLevelWidgets)（）和[QWidget.isVisible](qwidget.html#visible-prop)（ ） 。

```
bool QApplication.autoSipEnabled (self)
```

```
QApplication.beep ()
```

听起来钟，使用默认音量和声音。该函数是_not_在现有的Qt嵌入式Linux 。

```
QApplication.changeOverrideCursor (QCursor)
```

改变当前激活的应用程序复盖光标_cursor_。

这个功能有没有影响，如果[setOverrideCursor](qapplication.html#setOverrideCursor)（ ）没有被调用。

**See also** [setOverrideCursor](qapplication.html#setOverrideCursor)（ ）[overrideCursor](qapplication.html#overrideCursor)（ ）[restoreOverrideCursor](qapplication.html#restoreOverrideCursor)（）和[QWidget.setCursor](qwidget.html#cursor-prop)（ ） 。

```
QClipboard QApplication.clipboard ()
```

[

返回一个指向应用程序的全局剪贴板。

](qclipboard.html)

[**Note:**该](qclipboard.html)[QApplication](qapplication.html)对象应该已经访问剪贴板之前建造。

```
QApplication.closeAllWindows ()
```

这种方法也是一个Qt槽与C + +的签名`void closeAllWindows()`。

关闭所有顶层窗口。

此功能适用于许多顶层窗口的应用程序特别有用。它可以，例如，被连接到一个**Exit**在该条目**File**菜单：

```
     exitAct = new [QAction](qaction.html)(tr("E&xit"), this);
     exitAct->setShortcuts([QKeySequence](qkeysequence.html).Quit);
     exitAct->setStatusTip(tr("Exit the application"));
     connect(exitAct, SIGNAL(triggered()), qApp, SLOT(closeAllWindows()));

```

该窗口都关闭以随机顺序，直到一个窗口不接受close事件。在应用程序退出时，最后一个窗口被成功关闭，这可以通过设置关闭[quitOnLastWindowClosed](qapplication.html#quitOnLastWindowClosed-prop)为False。

**See also** [quitOnLastWindowClosed](qapplication.html#quitOnLastWindowClosed-prop)，[lastWindowClosed](qapplication.html#lastWindowClosed)（ ）[QWidget.close](qwidget.html#close)（ ）[QWidget.closeEvent](qwidget.html#closeEvent)（ ）[lastWindowClosed](qapplication.html#lastWindowClosed)（ ）[quit](qcoreapplication.html#quit)（ ）[topLevelWidgets](qapplication.html#topLevelWidgets)（）和[QWidget.isWindow](qwidget.html#isWindow)（ ） 。

```
int QApplication.colorSpec ()
```

返回颜色规格。

**See also** [QApplication.setColorSpec](qapplication.html#setColorSpec)（ ） 。

```
QApplication.commitData (self, QSessionManager sm)
```

这个函数处理[session management](index.htm)。它被调用时，[QSessionManager](qsessionmanager.html)想让应用程序提交的所有数据。

通常，这意味着保存所有打开的文件，从用户得到允许后。此外，您可能需要提供由用户可以取消关机的手段。

你不应该退出这个函数中的应用。相反，会话管理器可以或可以不这样做之后，这取决于上下文。

**Warning:**在这个函数中，没有用户交互是可能的，_unless_你问_manager_为明确许可。看[QSessionManager.allowsInteraction](qsessionmanager.html#allowsInteraction)（）和[QSessionManager.allowsErrorInteraction](qsessionmanager.html#allowsErrorInteraction)（ ）了解详情和用法示例。

默认实现请求交互和发送一个close事件给所有可见的顶层窗口部件。如果任何一个事件被拒绝，关机将被取消。

**See also** [isSessionRestored](qapplication.html#isSessionRestored)（ ）[sessionId](qapplication.html#sessionId)（ ）[saveState](qapplication.html#saveState)（）和[Session Management](index.htm)。

```
int QApplication.cursorFlashTime ()
```

```
QDesktopWidget QApplication.desktop ()
```

[

返回桌面窗口小部件（也称为根窗口）。

](qdesktopwidget.html)

[桌面可以由多个屏幕，因此它是不正确的，例如，以试图_center_一些小工具在桌面的几何形状。](qdesktopwidget.html)[QDesktopWidget](qdesktopwidget.html)具有各种功能的桌面在获得有用的几何形状，如[QDesktopWidget.screenGeometry](qdesktopwidget.html#screenGeometry)（）和[QDesktopWidget.availableGeometry](qdesktopwidget.html#availableGeometry)（ ） 。

在X11上，但也可以绘制在桌面上。

```
bool QApplication.desktopSettingsAware ()
```

返回True如果Qt的设置为使用系统的标准颜色，字体等，否则返回False 。默认值为True 。

**See also** [setDesktopSettingsAware](qapplication.html#setDesktopSettingsAware)（ ） 。

```
int QApplication.doubleClickInterval ()
```

```
bool QApplication.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QApplication.exec_ ()
```

进入主事件循环并等待，直到[exit](qcoreapplication.html#exit)（）被调用，然后返回被设置为值[exit](qcoreapplication.html#exit)（）（它是0，如果[exit](qcoreapplication.html#exit)（ ）通过调用[quit](qcoreapplication.html#quit)（））。

有必要调用这个函数来启动事件处理。主事件循环接收事件从窗口系统并调度这些应用程序的部件。

一般情况下，没有用户交互可以调用exec （ ）之前发生。作为一种特殊的情况下，模式对话框喜欢[QMessageBox](qmessagebox.html)调用exec （之前可以使用） ，因为模式对话框调用exec （ ）来启动一个本地事件循环。

为了使您的应用程序执行閒置处理，即执行一个特殊的功能，每当有没有挂起的事件，使用[QTimer](qtimer.html)与0超时。更高级的空閒处理方案可以用来实现[processEvents](qcoreapplication.html#processEvents)（ ） 。

我们建议您清理代码连接到[aboutToQuit()](qcoreapplication.html#aboutToQuit)信号，而不是把它在你的应用程序，`main()`功能。这是因为，在某些平台上的QApplication.exec （ ）调用可能不会返回。例如，在Windows平台上，当用户注销时，系统终止进程的Qt关闭所有顶层窗口之后。因此，有_no guarantee_该应用程序将有时间退出事件循环，并执行代码的结束`main()`功能， QApplication.exec （ ）调用之后。

**See also** [quitOnLastWindowClosed](qapplication.html#quitOnLastWindowClosed-prop)，[quit](qcoreapplication.html#quit)（ ）[exit](qcoreapplication.html#exit)（ ）[processEvents](qcoreapplication.html#processEvents)（）和[QCoreApplication.exec](qcoreapplication.html#exec)（ ） 。

```
QWidget QApplication.focusWidget ()
```

[

返回应用程序窗口部件拥有键盘输入焦点，或者0，如果在这个应用程序中没有窗口部件具有焦点。

](qwidget.html)

[**See also**](qwidget.html) [QWidget.setFocus](qwidget.html#setFocus)（ ）[QWidget.hasFocus](qwidget.html#focus-prop)（ ）[activeWindow](qapplication.html#activeWindow)（）和[focusChanged](qapplication.html#focusChanged)（ ） 。

```
QFont QApplication.font ()
```

[

返回默认应用程序字体。

](qfont.html)

[**See also**](qfont.html) [setFont](qapplication.html#setFont)（ ）[fontMetrics](qapplication.html#fontMetrics)（）和[QWidget.font](qwidget.html#font-prop)（ ） 。

```
QFont QApplication.font (QWidget)
```

[

这是一个重载函数。

返回的默认字体_widget_。

](qfont.html)

[**See also**](qfont.html) [fontMetrics](qapplication.html#fontMetrics)（）和[QWidget.setFont](qwidget.html#font-prop)（ ） 。

```
QFont QApplication.font (str className)
```

[

这是一个重载函数。

返回该字体的指定部件_className_。

](qfont.html)

[**See also**](qfont.html) [setFont](qapplication.html#setFont)（）和[QWidget.font](qwidget.html#font-prop)（ ） 。

```
QFontMetrics QApplication.fontMetrics ()
```

[

回报显示应用程序的字体（屏）字体度量。

](qfontmetrics.html)

[**See also**](qfontmetrics.html) [font](qapplication.html#font)（ ）[setFont](qapplication.html#setFont)（ ）[QWidget.fontMetrics](qwidget.html#fontMetrics)（）和[QPainter.fontMetrics](qpainter.html#fontMetrics)（ ） 。

```
QSize QApplication.globalStrut ()
```

[](qsize.html)

```
QInputContext QApplication.inputContext (self)
```

[](qinputcontext.html)

[返回](qinputcontext.html)[QInputContext](qinputcontext.html)比如所使用的应用程序。

**See also** [setInputContext](qapplication.html#setInputContext)（ ） 。

```
bool QApplication.isEffectEnabled (Qt.UIEffect)
```

返回True如果_effect_被启用，否则返回False 。

默认情况下， Qt会尝试使用桌面设置。为了防止这种情况，请致电setDesktopSettingsAware （假） 。

**Note:**所有的效果都上不到16位色彩深度运行屏幕禁用。

**See also** [setEffectEnabled](qapplication.html#setEffectEnabled)（）和[Qt.UIEffect](qt.html#UIEffect-enum)。

```
bool QApplication.isLeftToRight ()
```

返回True如果应用程序的布局方向[Qt.LeftToRight](qt.html#LayoutDirection-enum)否则返回False 。

**See also** [layoutDirection](qapplication.html#layoutDirection-prop)（）和[isRightToLeft](qapplication.html#isRightToLeft)（ ） 。

```
bool QApplication.isRightToLeft ()
```

返回True如果应用程序的布局方向[Qt.RightToLeft](qt.html#LayoutDirection-enum)否则返回False 。

**See also** [layoutDirection](qapplication.html#layoutDirection-prop)（）和[isLeftToRight](qapplication.html#isLeftToRight)（ ） 。

```
bool QApplication.isSessionRestored (self)
```

返回True如果该应用程序已恢复从以前的[session](index.htm)否则返回False 。

**See also** [sessionId](qapplication.html#sessionId)（ ）[commitData](qapplication.html#commitData)（）和[saveState](qapplication.html#saveState)（ ） 。

```
Qt.LayoutDirection QApplication.keyboardInputDirection ()
```

[

返回当前的键盘输入方向。

这个函数中引入了Qt 4.2中。

```
int QApplication.keyboardInputInterval ()
```

](qt.html#LayoutDirection-enum)

```
QLocale QApplication.keyboardInputLocale ()
```

[

返回当前的键盘输入法区域设置。

这个函数中引入了Qt 4.2中。

](qlocale.html)

```
Qt.KeyboardModifiers QApplication.keyboardModifiers ()
```

[](index.htm)

[返回键盘上的组合键的当前状态。目前的状态是合同步更新事件队列被清空，将自发地改变键盘状态的事件（](index.htm)[QEvent.KeyPress](qevent.html#Type-enum)和[QEvent.KeyRelease](qevent.html#Type-enum)事件）。

应该指出，这可能无法反映所保持的输入设备上的实际按键的时候调用的，而是修饰符作为最后报告在上述事件之一。如果没有键被关押[Qt.NoModifier](qt.html#KeyboardModifier-enum)返回。

**See also** [mouseButtons](qapplication.html#mouseButtons)（）和[queryKeyboardModifiers](qapplication.html#queryKeyboardModifiers)（ ） 。

```
Qt.LayoutDirection QApplication.layoutDirection ()
```

[](qt.html#LayoutDirection-enum)

```
Qt.MouseButtons QApplication.mouseButtons ()
```

[](index.htm)

[返回鼠标上的按钮的当前状态。目前的状态是syncronously更新事件队列被清空，将自发地改变鼠标状态的事件（](index.htm)[QEvent.MouseButtonPress](qevent.html#Type-enum)和[QEvent.MouseButtonRelease](qevent.html#Type-enum)事件）。

应该指出，这可能不是反映在打电话，而是在鼠标按键作为最后报告在上述事件之一时举行的输入设备上的实际按钮。如果没有鼠标按钮被关押[Qt.NoButton](qt.html#MouseButton-enum)返回。

**See also** [keyboardModifiers](qapplication.html#keyboardModifiers)（ ） 。

```
bool QApplication.notify (self, QObject, QEvent)
```

从重新实现[QCoreApplication.notify](qcoreapplication.html#notify)（ ） 。

```
QCursor QApplication.overrideCursor ()
```

[

返回当前应用程序强制光标。

此函数返回0，如果没有应用程序的光标已经定义（即内部光标栈为空） 。

](qcursor.html)

[**See also**](qcursor.html) [setOverrideCursor](qapplication.html#setOverrideCursor)（）和[restoreOverrideCursor](qapplication.html#restoreOverrideCursor)（ ） 。

```
QPalette QApplication.palette ()
```

[

返回应用程序的调色板。

](qpalette.html)

[**See also**](qpalette.html) [setPalette](qapplication.html#setPalette)（）和[QWidget.palette](qwidget.html#palette-prop)（ ） 。

```
QPalette QApplication.palette (QWidget)
```

[

这是一个重载函数。

如果_widget_通过，则返回默认调色板中的控件的类。这可能是也可能不是该应用程序的调色板。在大多数情况下，对某些类型的部件没有特别的调色板，但一个值得注意的例外是Windows下的弹出菜单，如果用户已经定义了一个特殊的背景颜色菜单中的显示设置。

](qpalette.html)

[**See also**](qpalette.html) [setPalette](qapplication.html#setPalette)（）和[QWidget.palette](qwidget.html#palette-prop)（ ） 。

```
QPalette QApplication.palette (str className)
```

[

这是一个重载函数。

返回调色板的特定部件_className_。

](qpalette.html)

[**See also**](qpalette.html) [setPalette](qapplication.html#setPalette)（）和[QWidget.palette](qwidget.html#palette-prop)（ ） 。

```
Qt.KeyboardModifiers QApplication.queryKeyboardModifiers ()
```

[

查询并返回键盘上的组合键的状态。不像keyboardModifiers ，此方法返回在调用该方法时所保持的输入设备上的实际按键。

](index.htm)

[它不依赖于已收到由该过程中，这使得它可以检查改性剂而移动窗口，比如按键事件。请注意，在大多数情况下，你应该使用](index.htm)[keyboardModifiers](qapplication.html#keyboardModifiers)（），这是更快和更精确，因为它包含的改性剂的状态，因为它们是在接收到当前处理的事件时。

此功能被引入Qt的4.8 。

**See also** [keyboardModifiers](qapplication.html#keyboardModifiers)（ ） 。

```
bool QApplication.quitOnLastWindowClosed ()
```

```
QApplication.restoreOverrideCursor ()
```

撤消上一个[setOverrideCursor](qapplication.html#setOverrideCursor)（ ） 。

If [setOverrideCursor](qapplication.html#setOverrideCursor)（ ）被调用两次，调用的restoreOverrideCursor （ ）时将激活第一个光标集。调用此函数第二次恢复原来的小部件'游标。

**See also** [setOverrideCursor](qapplication.html#setOverrideCursor)（）和[overrideCursor](qapplication.html#overrideCursor)（ ） 。

```
QApplication.saveState (self, QSessionManager sm)
```

这个函数处理[session management](index.htm)。它被调用时，[session manager](qsessionmanager.html)想让应用程序保存其状态为今后的会议。

例如，文本编辑器会创建一个临时文件，其中包括它的编辑缓冲区，在当前编辑会话的游标等方面的位置的当前内容。

你不应该退出这个函数中的应用。相反，会话管理器可以或可以不这样做之后，这取决于上下文。 Futhermore ，大多数会话管理器很可能会立即要求保存状态的应用程序已经开始之后。这允许会话管理器来了解应用程序的重新启动策略。

**Warning:**在这个函数中，没有用户交互是可能的，_unless_你问_manager_为明确许可。看[QSessionManager.allowsInteraction](qsessionmanager.html#allowsInteraction)（）和[QSessionManager.allowsErrorInteraction](qsessionmanager.html#allowsErrorInteraction)（ ）了解详情。

**See also** [isSessionRestored](qapplication.html#isSessionRestored)（ ）[sessionId](qapplication.html#sessionId)（ ）[commitData](qapplication.html#commitData)（）和[Session Management](index.htm)。

```
QString QApplication.sessionId (self)
```

返回当前[session's](index.htm)标识符。

如果应用程序已恢复从以前的会话，这个标识符是因为它是在先前的对话一样。会话标识符保证是唯一既为不同的应用程序和同一应用程序的不同实例。

**See also** [isSessionRestored](qapplication.html#isSessionRestored)（ ）[sessionKey](qapplication.html#sessionKey)（ ）[commitData](qapplication.html#commitData)（）和[saveState](qapplication.html#saveState)（ ） 。

```
QString QApplication.sessionKey (self)
```

返回在当前会话密钥[session](index.htm)。

如果应用程序已恢复从以前的会话，这个键是一样的，当前一交易日结束它。

随着每次调用会话密钥的变化[commitData](qapplication.html#commitData)（）或[saveState](qapplication.html#saveState)（ ） 。

**See also** [isSessionRestored](qapplication.html#isSessionRestored)（ ）[sessionId](qapplication.html#sessionId)（ ）[commitData](qapplication.html#commitData)（）和[saveState](qapplication.html#saveState)（ ） 。

```
QApplication.setActiveWindow (QWidget act)
```

设置活动窗口到_active_小工具响应于系统事件。该功能是从特定于平台的事件处理程序调用。

**Warning:**这个函数_not_设置键盘焦点到活动部件。通话[QWidget.activateWindow](qwidget.html#activateWindow)（ ）来代替。

它集[activeWindow](qapplication.html#activeWindow)（）和[focusWidget](qapplication.html#focusWidget)（ ）属性，并发送适当的[WindowActivate](qevent.html#Type-enum)/[WindowDeactivate](qevent.html#Type-enum)和[FocusIn](qevent.html#Type-enum)/[FocusOut](qevent.html#Type-enum)活动以所有适当的部件。该窗口就会处于活跃状态涂漆（如光标在编辑行会闪烁） ，于是也有工具提示启用。

**See also** [activeWindow](qapplication.html#activeWindow)（）和[QWidget.activateWindow](qwidget.html#activateWindow)（ ） 。

```
QApplication.setAutoSipEnabled (self, bool enabled)
```

这种方法也是一个Qt槽与C + +的签名`void setAutoSipEnabled(const bool)`。

```
QApplication.setColorSpec (int)
```

设置颜色规格为应用程序_spec_。

颜色规格控制应用程序在有限的颜色数量的显示器上运行时，如何分配颜色，例如8位/ 256色显示。

您之前创建的颜色规范必须设置[QApplication](qapplication.html)对象。

选项有：

*   [QApplication.NormalColor](qapplication.html#ColorSpec-enum). This is the default color allocation strategy. Use this option if your application uses buttons, menus, texts and pixmaps with few colors. With this option, the application uses system global colors. This works fine for most applications under X11, but on the Windows platform, it may cause dithering of non-standard colors.
*   [QApplication.CustomColor](qapplication.html#ColorSpec-enum). Use this option if your application needs a small number of custom colors. On X11, this option is the same as [NormalColor](qapplication.html#ColorSpec-enum). On Windows, Qt creates a Windows palette, and allocates colors to it on demand.
*   [QApplication.ManyColor](qapplication.html#ColorSpec-enum). Use this option if your application is very color hungry, e.g., it requires thousands of colors.
    Under X11 the effect is:
    *   For 256-color displays which have at best a 256 color true color visual, the default visual is used, and colors are allocated from a color cube. The color cube is the 6x6x6 (216 color) "Web palette" (the red, green, and blue components always have one of the following values: 0x00, 0x33, 0x66, 0x99, 0xCC, or 0xFF), but the number of colors can be changed by the _-ncols_ option. The user can force the application to use the true color visual with the [-visual](qapplication.html#QApplication) option.
    *   For 256-color displays which have a true color visual with more than 256 colors, use that visual. Silicon Graphics X servers this feature, for example. They provide an 8 bit visual by default but can deliver true color when asked.

    在Windows下，Qt创建一个Windows调色板，并配以彩色立方体填充它。

请注意，[CustomColor](qapplication.html#ColorSpec-enum)和[ManyColor](qapplication.html#ColorSpec-enum)选择可能导致颜色映射闪烁：前台应用程序获取（大多数）的可用的颜色，而背景窗口会显得那么有吸引力。

例如：

```
 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html).setColorSpec([QApplication](qapplication.html).ManyColor);
     [QApplication](qapplication.html) app(argc, argv);
     ...
     return app.exec();
 }

```

**See also** [colorSpec](qapplication.html#colorSpec)（ ） 。

```
QApplication.setCursorFlashTime (int)
```

```
QApplication.setDesktopSettingsAware (bool)
```

Qt的设置是否应使用系统的标准颜色，字体等，_on_。默认情况下，这是事实。

这个函数必须在创建之前调用的[QApplication](qapplication.html)对象，像这样：

```
 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html).setDesktopSettingsAware(false);
     [QApplication](qapplication.html) app(argc, argv);
     ...
     return app.exec();
 }

```

**See also** [desktopSettingsAware](qapplication.html#desktopSettingsAware)（ ） 。

```
QApplication.setDoubleClickInterval (int)
```

```
QApplication.setEffectEnabled (Qt.UIEffect effect, bool enabled = True)
```

使用户界面效果_effect_如果_enable_为真，否则效果将不被使用。

**Note:**所有的效果都上不到16位色彩深度运行屏幕禁用。

**See also** [isEffectEnabled](qapplication.html#isEffectEnabled)（ ）[Qt.UIEffect](qt.html#UIEffect-enum)和[setDesktopSettingsAware](qapplication.html#setDesktopSettingsAware)（ ） 。

```
QApplication.setFont (QFont font, str className = None)
```

更改默认应用程序字体_font_。如果_className_通过后，改变只适用于继承类_className_（所报告的[QObject.inherits](qobject.html#inherits)（））。

在应用程序启动时，默认字体依赖于窗口系统。它可以根据这两个窗口系统版本和语言环境而有所不同。此功能可让您复盖默认的字体，但压倒一切的可能是一个坏主意，因为，例如，某些区域设置需要额外的大字体，以支持他们的特殊字符。

**Warning:**请勿在结合使用此功能[Qt Style Sheets](index.htm)。一个应用程序的字体可以使用“字体”样式表属性来定制。要设置粗体所有QPushButtons ，设置应用程序[styleSheet](qapplication.html#styleSheet-prop)（）作为“[QPushButton](qpushbutton.html)【字体：黑体} “

**See also** [font](qapplication.html#font)（ ）[fontMetrics](qapplication.html#fontMetrics)（）和[QWidget.setFont](qwidget.html#font-prop)（ ） 。

```
QApplication.setGlobalStrut (QSize)
```

```
QApplication.setGraphicsSystem (QString)
```

设置默认的图形后端_system_，这将用于在屏幕上的小部件和QPixmaps 。可用的系统`"native"`，`"raster"`和`"opengl"`。

有几种方法来设置图形后端，以优先级递减的：

*   the application commandline `-graphicssystem` switch
*   QApplication.setGraphicsSystem()
*   the QT_GRAPHICSSYSTEM environment variable
*   the Qt configure `-graphicssystem` switch

如果优先级最高的交换机设置了一个无效的名称，该错误将被忽略，默认后端将被使用。

**Warning:**此功能之前，唯一有效的[QApplication](qapplication.html)构造函数被调用。

**Note:**该`"opengl"`选项当前实验。

此功能被引入Qt的4.5 。

```
QApplication.setInputContext (self, QInputContext)
```

该_QInputContext_说法有它的所有权转移给Qt的。

此函数替换了[QInputContext](qinputcontext.html)例如使用与该应用程序_inputContext_。

Qt可以给定所有权_inputContext_。

**See also** [inputContext](qapplication.html#inputContext)（ ） 。

```
QApplication.setKeyboardInputInterval (int)
```

```
QApplication.setLayoutDirection (Qt.LayoutDirection direction)
```

```
QApplication.setOverrideCursor (QCursor)
```

设置应用程序复盖光标_cursor_。

应用程序强制光标是为了显示该应用程序是在一个特殊的状态，例如，可能需要一段时间的操作过程中的用户。

这将光标直到显示在应用程序的所有窗口部件[restoreOverrideCursor](qapplication.html#restoreOverrideCursor)（）或另一个一个setOverrideCursor （）被调用。

应用程序光标被存储在一个内部堆栈。一个setOverrideCursor （ ）推光标入堆栈，并[restoreOverrideCursor](qapplication.html#restoreOverrideCursor)（ ）弹出活动光标堆栈。[changeOverrideCursor](qapplication.html#changeOverrideCursor)（ ）改变了活跃的会员...应用复盖光标。

每一个setOverrideCursor （ ）最终必须后跟一个相应的[restoreOverrideCursor](qapplication.html#restoreOverrideCursor)（ ），否则栈将永远不会被清空。

例如：

```
 [QApplication](qapplication.html).setOverrideCursor([QCursor](qcursor.html)([Qt](qt.html).WaitCursor));
 calculateHugeMandelbrot();              // lunch time...
 [QApplication](qapplication.html).restoreOverrideCursor();

```

**See also** [overrideCursor](qapplication.html#overrideCursor)（ ）[restoreOverrideCursor](qapplication.html#restoreOverrideCursor)（ ）[changeOverrideCursor](qapplication.html#changeOverrideCursor)（）和[QWidget.setCursor](qwidget.html#cursor-prop)（ ） 。

```
QApplication.setPalette (QPalette palette, str className = None)
```

更改默认的应用程序调色板_palette_。

If _className_通过后，改变只适用于继承部件_className_（所报告的[QObject.inherits](qobject.html#inherits)（））。如果_className_剩下0 ，则更改会影响所有部件，从而复盖任何先前设置的类特定的调色板。

调色板可以根据当前的GUI样式中被改变[QStyle.polish](qstyle.html#polish)（ ） 。

**Warning:**请勿在结合使用此功能[Qt Style Sheets](index.htm)。当使用样式表，一个小部件的调色板可以使用“颜色” ， “背景色” ， “选择颜色” ， “选择 - 背景色”和“复用背景色”进行自定义。

**Note:**有些样式不使用调色板的所有图纸，举例来说，如果他们利用原生主题引擎。这是Windows XP ， Windows Vista和Mac OS X的风格的情况下。

**See also** [QWidget.setPalette](qwidget.html#palette-prop)（ ）[palette](qapplication.html#palette)（）和[QStyle.polish](qstyle.html#polish)（ ） 。

```
QApplication.setQuitOnLastWindowClosed (bool quit)
```

```
QApplication.setStartDragDistance (int l)
```

```
QApplication.setStartDragTime (int ms)
```

```
QApplication.setStyle (QStyle)
```

该_QStyle_说法有它的所有权转移给Qt的。

设置应用程序的图形用户界面风格_style_。样式对象的所有权被转移到[QApplication](qapplication.html)，所以[QApplication](qapplication.html)将删除应用程序退出或者当一个新样式设置和旧风格仍然是应用程序对象的父项的样式对象。

用法示例：

```
 [QApplication](qapplication.html).setStyle(new [QWindowsStyle](index.htm));

```

当切换应用的样式，颜色调色板设置恢复到初始的颜色或系统默认值。这是必要的，因为某些样式必须适应调色板是完全风格指南标准。

调色板之前，设置样式已定，即之前创建[QApplication](qapplication.html)，会导致应用程序使用[QStyle.standardPalette](qstyle.html#standardPalette)（ ）的调色板。

**Warning:**目前不支持Qt的样式表定制[QStyle](qstyle.html)子类。我们计划在未来的版本解决这个问题。

**See also** [style](qapplication.html#style)（ ）[QStyle](qstyle.html)，[setPalette](qapplication.html#setPalette)（）和[desktopSettingsAware](qapplication.html#desktopSettingsAware)（ ） 。

```
QStyle QApplication.setStyle (QString)
```

[

这是一个重载函数。

](qstyle.html)

[请求](qstyle.html)[QStyle](qstyle.html)对于对象_style_从[QStyleFactory](qstylefactory.html)。

该字符串必须是一个[QStyleFactory.keys](qstylefactory.html#keys)（） ，典型的“窗口”， 1 ， “基序”，“ CDE ”，“ PLASTIQUE ”，“ WindowsXP的”或“苹果” 。样式名不区分大小写。

返回0，如果一个未知_style_通过，否则[QStyle](qstyle.html)返回的对象被设置为应用程序的图形用户界面风格。

**Warning:**为了确保应用程序的风格设置是否正确，最好是前调用这个函数[QApplication](qapplication.html)构造函数，如果可能的话。

```
QApplication.setStyleSheet (self, QString sheet)
```

这种方法也是一个Qt槽与C + +的签名`void setStyleSheet(const QString&)`。

```
QApplication.setWheelScrollLines (int)
```

```
QApplication.setWindowIcon (QIcon icon)
```

```
int QApplication.startDragDistance ()
```

```
int QApplication.startDragTime ()
```

```
QStyle QApplication.style ()
```

[

返回应用程序的样式对象。

](qstyle.html)

[**See also**](qstyle.html) [setStyle](qapplication.html#setStyle)() and [QStyle](qstyle.html).

```
QString QApplication.styleSheet (self)
```

```
QApplication.syncX ()
```

与同步在X11实现X服务器。这通常需要一些时间。什么都不做在其他平台上。

```
QWidget QApplication.topLevelAt (QPoint p)
```

[

返回顶层窗口部件在给定的_point_;返回0，如果没有这样的小部件。

](qwidget.html)

```
QWidget QApplication.topLevelAt (int x, int y)
```

[

这是一个重载函数。

返回顶层窗口部件在点（_x_，_y_） ;返回0 ，如果不存在这样的窗口小部件。

```
list-of-QWidget QApplication.topLevelWidgets ()
```

返回顶层窗口小部件（窗口）中的应用程序的列表。

**Note:**一些顶级小部件可能会被隐藏，例如工具提示，如果没有提示当前显示。

例如：

](qwidget.html)

```
 void showAllHiddenTopLevelWidgets()
 {
     foreach (QWidget *widget, [QApplication](qapplication.html).topLevelWidgets()) {
         if (widget->isHidden())
             widget->show();
     }
 }

```

**See also** [allWidgets](qapplication.html#allWidgets)（ ）[QWidget.isWindow](qwidget.html#isWindow)（）和[QWidget.isHidden](qwidget.html#isHidden)（ ） 。

```
Type QApplication.type ()
```

[](qapplication.html#Type-enum)

[返回应用程序的类型（](qapplication.html#Type-enum)[Tty](qapplication.html#Type-enum)，[GuiClient](qapplication.html#Type-enum)或[GuiServer](qapplication.html#Type-enum)） 。该类型是施工时设置[QApplication](qapplication.html)对象。

```
int QApplication.wheelScrollLines ()
```

```
QWidget QApplication.widgetAt (QPoint p)
```

[

返回小部件在全局屏幕位置_point_或0，如果没有Qt插件那里。

此功能可能会很慢。

](qwidget.html)

[**See also**](qwidget.html) [QCursor.pos](qcursor.html#pos)（ ）[QWidget.grabMouse](qwidget.html#grabMouse)（）和[QWidget.grabKeyboard](qwidget.html#grabKeyboard)（ ） 。

```
QWidget QApplication.widgetAt (int x, int y)
```

[](qwidget.html)

```
QIcon QApplication.windowIcon ()
```

[

```
bool QApplication.x11EventFilter (self, sip.voidptr)
```

**Warning:**这个虚函数仅X11下实现的。

](qicon.html)

[如果你创建一个继承的应用程序](qicon.html)[QApplication](qapplication.html)并且重新实现这个功能，你可以直接访问该从X服务器接收到的所有X事件。该事件传递的_event_参数。

如果你想从被处理停止事件，则返回True 。返回False对于普通事件分派。默认实现返回False 。

这是唯一的解决直接被过滤的邮件。您必须直接在事件调度程序，这是由返回安装一个事件过滤器[QAbstractEventDispatcher.instance](qabstracteventdispatcher.html#instance)（ ） ，以处理全系统的消息。

**See also** [x11ProcessEvent](qapplication.html#x11ProcessEvent)（ ） 。

```
int QApplication.x11ProcessEvent (self, sip.voidptr)
```

这个函数做个体X的核心处理_event_秒，通常由调度Qt的事件到正确的目的地。

它返回1，如果该事件被消耗了特殊处理， 0如果_event_由正常的处理消耗， -1，如果_event_是一个无法识别的部件。

**See also** [x11EventFilter](qapplication.html#x11EventFilter)（ ） 。

* * *

## Qt Signal Documentation

```
void commitDataRequest (QSessionManager&)
```

这是该信号的默认超载。

该信号处理[session management](index.htm)。它被发射时的[QSessionManager](qsessionmanager.html)想让应用程序提交的所有数据。

通常，这意味着保存所有打开的文件，从用户得到允许后。此外，您可能需要提供由用户可以取消关机的手段。

你不应该离开这个信号中的应用。相反，会话管理器可以或可以不这样做之后，这取决于上下文。

**Warning:**在这个信号，无用户交互是可能的，_unless_你问_manager_为明确许可。看[QSessionManager.allowsInteraction](qsessionmanager.html#allowsInteraction)（）和[QSessionManager.allowsErrorInteraction](qsessionmanager.html#allowsErrorInteraction)（ ）了解详情和用法示例。

**Note:**您应该使用[Qt.DirectConnection](qt.html#ConnectionType-enum)连接到这个信号时。

这个函数中引入了Qt 4.2中。

**See also** [isSessionRestored](qapplication.html#isSessionRestored)（ ）[sessionId](qapplication.html#sessionId)（ ）[saveState](qapplication.html#saveState)（）和[Session Management](index.htm)。

```
void focusChanged (QWidget *,QWidget *)
```

这是该信号的默认超载。

这个信号被发射时具有键盘焦点的窗口小部件的改变_old_至_now_，即，因为用户按下Tab键，点击进入小部件或改变活动窗口。两_old_和_now_可以是空指针。

该信号发出后两个部件都经过已经被告知了变化[QFocusEvent](qfocusevent.html)。

这个函数是Qt 4.1中引入。

**See also** [QWidget.setFocus](qwidget.html#setFocus)（ ）[QWidget.clearFocus](qwidget.html#clearFocus)（）和[Qt.FocusReason](qt.html#FocusReason-enum)。

```
void fontDatabaseChanged ()
```

这是该信号的默认超载。

这个信号时应用的字体被加载或移除射出。

此功能被引入Qt的4.5 。

**See also** [QFontDatabase.addApplicationFont](qfontdatabase.html#addApplicationFont)（ ）[QFontDatabase.addApplicationFontFromData](qfontdatabase.html#addApplicationFontFromData)（ ）[QFontDatabase.removeAllApplicationFonts](qfontdatabase.html#removeAllApplicationFonts)（）和[QFontDatabase.removeApplicationFont](qfontdatabase.html#removeApplicationFont)（ ） 。

```
void lastWindowClosed ()
```

这是该信号的默认超载。

这个信号从发射[QApplication.exec](qapplication.html#exec)（ ）当最后一个可见的主窗口（即窗口没有父）与[Qt.WA_QuitOnClose](qt.html#WidgetAttribute-enum)属性设置是关闭的。

默认情况下，

*   this attribute is set for all widgets except transient windows such as splash screens, tool windows, and popup menus
*   [QApplication](qapplication.html) implicitly quits when this signal is emitted.

此功能可以通过设置关闭[quitOnLastWindowClosed](qapplication.html#quitOnLastWindowClosed-prop)为False。

**See also** [QWidget.close](qwidget.html#close)（ ） 。

```
void saveStateRequest (QSessionManager&)
```

这是该信号的默认超载。

该信号处理[session management](index.htm)。它被调用时，[session manager](qsessionmanager.html)想让应用程序保存其状态为今后的会议。

例如，文本编辑器会创建一个临时文件，其中包括它的编辑缓冲区，在当前编辑会话的游标等方面的位置的当前内容。

你不应该离开这个信号中的应用。相反，会话管理器可以或可以不这样做之后，这取决于上下文。 Futhermore ，大多数会话管理器很可能会立即要求保存状态的应用程序已经开始之后。这允许会话管理器来了解应用程序的重新启动策略。

**Warning:**在这个函数中，没有用户交互是可能的，_unless_你问_manager_为明确许可。看[QSessionManager.allowsInteraction](qsessionmanager.html#allowsInteraction)（）和[QSessionManager.allowsErrorInteraction](qsessionmanager.html#allowsErrorInteraction)（ ）了解详情。

**Note:**您应该使用[Qt.DirectConnection](qt.html#ConnectionType-enum)连接到这个信号时。

这个函数中引入了Qt 4.2中。

**See also** [isSessionRestored](qapplication.html#isSessionRestored)（ ）[sessionId](qapplication.html#sessionId)（ ）[commitData](qapplication.html#commitData)（）和[Session Management](index.htm)。