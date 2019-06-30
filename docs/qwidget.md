# QWidget Class Reference

## [[QtGui](index.htm) module]

QWidget的类是所有用户界面对象的基类。[More...](#details)

继承[QObject](qobject.html)和[QPaintDevice](qpaintdevice.html)。

通过继承[EffectWidget](index.htm)，[SeekSlider](index.htm)，[VideoPlayer](index.htm)，[VideoWidget](index.htm)，[VolumeSlider](index.htm)，[QAbstractButton](qabstractbutton.html)，[QAbstractSlider](qabstractslider.html)，[QAbstractSpinBox](qabstractspinbox.html)，[QCalendarWidget](qcalendarwidget.html)，[QComboBox](qcombobox.html)，[QDesignerActionEditorInterface](qdesigneractioneditorinterface.html)，[QDesignerFormWindowInterface](qdesignerformwindowinterface.html)，[QDesignerObjectInspectorInterface](qdesignerobjectinspectorinterface.html)，[QDesignerPropertyEditorInterface](qdesignerpropertyeditorinterface.html)，[QDesignerWidgetBoxInterface](qdesignerwidgetboxinterface.html)，[QDesktopWidget](qdesktopwidget.html)，[QDialog](qdialog.html)，[QDialogButtonBox](qdialogbuttonbox.html)，[QDockWidget](qdockwidget.html)，[QFocusFrame](qfocusframe.html)，[QFrame](qframe.html)，[QGLWidget](qglwidget.html)，[QGroupBox](qgroupbox.html)，[QHelpSearchQueryWidget](qhelpsearchquerywidget.html)，[QHelpSearchResultWidget](qhelpsearchresultwidget.html)，[QLineEdit](qlineedit.html)，[QMainWindow](qmainwindow.html)，[QMdiSubWindow](qmdisubwindow.html)，[QMenu](qmenu.html)，[QMenuBar](qmenubar.html)，[QPrintPreviewWidget](qprintpreviewwidget.html)，[QProgressBar](qprogressbar.html)，[QRubberBand](qrubberband.html)，[QSizeGrip](qsizegrip.html)，[QSplashScreen](qsplashscreen.html)，[QSplitterHandle](qsplitterhandle.html)，[QStatusBar](qstatusbar.html)，[QSvgWidget](qsvgwidget.html)，[QTabBar](qtabbar.html)，[QTabWidget](qtabwidget.html)，[QToolBar](qtoolbar.html)，[QWebInspector](qwebinspector.html)，[QWebView](qwebview.html)，[QWizardPage](qwizardpage.html)，[QWorkspace](qworkspace.html)，[QX11EmbedContainer](qx11embedcontainer.html)和[QX11EmbedWidget](qx11embedwidget.html)。

### Types

*   `enum RenderFlag { DrawWindowBackground, DrawChildren, IgnoreMask }`
*   `class **[RenderFlags](index.htm)**`

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `bool acceptDrops (self)`
*   `QString accessibleDescription (self)`
*   `QString accessibleName (self)`
*   `actionEvent (self, QActionEvent)`
*   `list-of-QAction actions (self)`
*   `activateWindow (self)`
*   `addAction (self, QAction action)`
*   `addActions (self, list-of-QAction actions)`
*   `adjustSize (self)`
*   `bool autoFillBackground (self)`
*   `QPalette.ColorRole backgroundRole (self)`
*   `QSize baseSize (self)`
*   `changeEvent (self, QEvent)`
*   `QWidget childAt (self, QPoint p)`
*   `QWidget childAt (self, int ax, int ay)`
*   `QRect childrenRect (self)`
*   `QRegion childrenRegion (self)`
*   `clearFocus (self)`
*   `clearMask (self)`
*   `bool close (self)`
*   `closeEvent (self, QCloseEvent)`
*   `QMargins contentsMargins (self)`
*   `QRect contentsRect (self)`
*   `contextMenuEvent (self, QContextMenuEvent)`
*   `Qt.ContextMenuPolicy contextMenuPolicy (self)`
*   `create (self, int window = 0, bool initializeWindow = True, bool destroyOldWindow = True)`
*   `QCursor cursor (self)`
*   `destroy (self, bool destroyWindow = True, bool destroySubWindows = True)`
*   `int devType (self)`
*   `dragEnterEvent (self, QDragEnterEvent)`
*   `dragLeaveEvent (self, QDragLeaveEvent)`
*   `dragMoveEvent (self, QDragMoveEvent)`
*   `dropEvent (self, QDropEvent)`
*   `int effectiveWinId (self)`
*   `enabledChange (self, bool)`
*   `ensurePolished (self)`
*   `enterEvent (self, QEvent)`
*   `bool event (self, QEvent)`
*   `focusInEvent (self, QFocusEvent)`
*   `bool focusNextChild (self)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent)`
*   `Qt.FocusPolicy focusPolicy (self)`
*   `bool focusPreviousChild (self)`
*   `QWidget focusProxy (self)`
*   `QWidget focusWidget (self)`
*   `QFont font (self)`
*   `fontChange (self, QFont)`
*   `QFontInfo fontInfo (self)`
*   `QFontMetrics fontMetrics (self)`
*   `QPalette.ColorRole foregroundRole (self)`
*   `QRect frameGeometry (self)`
*   `QSize frameSize (self)`
*   `QRect geometry (self)`
*   `(int left, int top, int right, int bottom) getContentsMargins (self)`
*   `grabGesture (self, Qt.GestureType type, Qt.GestureFlags flags = Qt.GestureFlags(0))`
*   `grabKeyboard (self)`
*   `grabMouse (self)`
*   `grabMouse (self, QCursor)`
*   `int grabShortcut (self, QKeySequence key, Qt.ShortcutContext context = Qt.WindowShortcut)`
*   `QGraphicsEffect graphicsEffect (self)`
*   `QGraphicsProxyWidget graphicsProxyWidget (self)`
*   `int handle (self)`
*   `bool hasFocus (self)`
*   `bool hasMouseTracking (self)`
*   `int height (self)`
*   `int heightForWidth (self, int)`
*   `hide (self)`
*   `hideEvent (self, QHideEvent)`
*   `QInputContext inputContext (self)`
*   `inputMethodEvent (self, QInputMethodEvent)`
*   `Qt.InputMethodHints inputMethodHints (self)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery)`
*   `insertAction (self, QAction before, QAction action)`
*   `insertActions (self, QAction before, list-of-QAction actions)`
*   `bool isActiveWindow (self)`
*   `bool isAncestorOf (self, QWidget child)`
*   `bool isEnabled (self)`
*   `bool isEnabledTo (self, QWidget)`
*   `bool isEnabledToTLW (self)`
*   `bool isFullScreen (self)`
*   `bool isHidden (self)`
*   `bool isLeftToRight (self)`
*   `bool isMaximized (self)`
*   `bool isMinimized (self)`
*   `bool isModal (self)`
*   `bool isRightToLeft (self)`
*   `bool isTopLevel (self)`
*   `bool isVisible (self)`
*   `bool isVisibleTo (self, QWidget)`
*   `bool isWindow (self)`
*   `bool isWindowModified (self)`
*   `keyPressEvent (self, QKeyEvent)`
*   `keyReleaseEvent (self, QKeyEvent)`
*   `languageChange (self)`
*   `QLayout layout (self)`
*   `Qt.LayoutDirection layoutDirection (self)`
*   `leaveEvent (self, QEvent)`
*   `QLocale locale (self)`
*   `lower (self)`
*   `QPoint mapFrom (self, QWidget, QPoint)`
*   `QPoint mapFromGlobal (self, QPoint)`
*   `QPoint mapFromParent (self, QPoint)`
*   `QPoint mapTo (self, QWidget, QPoint)`
*   `QPoint mapToGlobal (self, QPoint)`
*   `QPoint mapToParent (self, QPoint)`
*   `QRegion mask (self)`
*   `int maximumHeight (self)`
*   `QSize maximumSize (self)`
*   `int maximumWidth (self)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric)`
*   `int minimumHeight (self)`
*   `QSize minimumSize (self)`
*   `QSize minimumSizeHint (self)`
*   `int minimumWidth (self)`
*   `mouseDoubleClickEvent (self, QMouseEvent)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `move (self, QPoint)`
*   `move (self, int ax, int ay)`
*   `moveEvent (self, QMoveEvent)`
*   `QWidget nativeParentWidget (self)`
*   `QWidget nextInFocusChain (self)`
*   `QRect normalGeometry (self)`
*   `overrideWindowFlags (self, Qt.WindowFlags type)`
*   `overrideWindowState (self, Qt.WindowStates state)`
*   `QPaintEngine paintEngine (self)`
*   `paintEvent (self, QPaintEvent)`
*   `QPalette palette (self)`
*   `paletteChange (self, QPalette)`
*   `QWidget parentWidget (self)`
*   `QPoint pos (self)`
*   `QWidget previousInFocusChain (self)`
*   `raise_ (self)`
*   `QRect rect (self)`
*   `releaseKeyboard (self)`
*   `releaseMouse (self)`
*   `releaseShortcut (self, int id)`
*   `removeAction (self, QAction action)`
*   `render (self, QPaintDevice target, QPoint targetOffset = QPoint(), QRegion sourceRegion = QRegion(), RenderFlags flags = QWidget.DrawWindowBackground|QWidget.DrawChildren)`
*   `render (self, QPainter painter, QPoint targetOffset = QPoint(), QRegion sourceRegion = QRegion(), RenderFlags flags = QWidget.DrawWindowBackground|QWidget.DrawChildren)`
*   `repaint (self)`
*   `repaint (self, int x, int y, int w, int h)`
*   `repaint (self, QRect)`
*   `repaint (self, QRegion)`
*   `resetInputContext (self)`
*   `resize (self, QSize)`
*   `resize (self, int w, int h)`
*   `resizeEvent (self, QResizeEvent)`
*   `bool restoreGeometry (self, QByteArray geometry)`
*   `QByteArray saveGeometry (self)`
*   `scroll (self, int dx, int dy)`
*   `scroll (self, int dx, int dy, QRect)`
*   `setAcceptDrops (self, bool on)`
*   `setAccessibleDescription (self, QString description)`
*   `setAccessibleName (self, QString name)`
*   `setAttribute (self, Qt.WidgetAttribute attribute, bool on = True)`
*   `setAutoFillBackground (self, bool enabled)`
*   `setBackgroundRole (self, QPalette.ColorRole)`
*   `setBaseSize (self, int basew, int baseh)`
*   `setBaseSize (self, QSize s)`
*   `setContentsMargins (self, int left, int top, int right, int bottom)`
*   `setContentsMargins (self, QMargins margins)`
*   `setContextMenuPolicy (self, Qt.ContextMenuPolicy policy)`
*   `setCursor (self, QCursor)`
*   `setDisabled (self, bool)`
*   `setEnabled (self, bool)`
*   `setFixedHeight (self, int h)`
*   `setFixedSize (self, QSize)`
*   `setFixedSize (self, int w, int h)`
*   `setFixedWidth (self, int w)`
*   `setFocus (self)`
*   `setFocus (self, Qt.FocusReason reason)`
*   `setFocusPolicy (self, Qt.FocusPolicy policy)`
*   `setFocusProxy (self, QWidget)`
*   `setFont (self, QFont)`
*   `setForegroundRole (self, QPalette.ColorRole)`
*   `setGeometry (self, QRect)`
*   `setGeometry (self, int ax, int ay, int aw, int ah)`
*   `setGraphicsEffect (self, QGraphicsEffect effect)`
*   `setHidden (self, bool hidden)`
*   `setInputContext (self, QInputContext)`
*   `setInputMethodHints (self, Qt.InputMethodHints hints)`
*   `setLayout (self, QLayout)`
*   `setLayoutDirection (self, Qt.LayoutDirection direction)`
*   `setLocale (self, QLocale locale)`
*   `setMask (self, QBitmap)`
*   `setMask (self, QRegion)`
*   `setMaximumHeight (self, int maxh)`
*   `setMaximumSize (self, int maxw, int maxh)`
*   `setMaximumSize (self, QSize s)`
*   `setMaximumWidth (self, int maxw)`
*   `setMinimumHeight (self, int minh)`
*   `setMinimumSize (self, int minw, int minh)`
*   `setMinimumSize (self, QSize s)`
*   `setMinimumWidth (self, int minw)`
*   `setMouseTracking (self, bool enable)`
*   `setPalette (self, QPalette)`
*   `setParent (self, QWidget parent)`
*   `setParent (self, QWidget parent, Qt.WindowFlags f)`
*   `setShortcutAutoRepeat (self, int id, bool enabled = True)`
*   `setShortcutEnabled (self, int id, bool enabled = True)`
*   `setShown (self, bool shown)`
*   `setSizeIncrement (self, int w, int h)`
*   `setSizeIncrement (self, QSize s)`
*   `setSizePolicy (self, QSizePolicy)`
*   `setSizePolicy (self, QSizePolicy.Policy hor, QSizePolicy.Policy ver)`
*   `setStatusTip (self, QString)`
*   `setStyle (self, QStyle)`
*   `setStyleSheet (self, QString styleSheet)`
*   `setToolTip (self, QString)`
*   `setUpdatesEnabled (self, bool enable)`
*   `setVisible (self, bool visible)`
*   `setWhatsThis (self, QString)`
*   `setWindowFilePath (self, QString filePath)`
*   `setWindowFlags (self, Qt.WindowFlags type)`
*   `setWindowIcon (self, QIcon icon)`
*   `setWindowIconText (self, QString)`
*   `setWindowModality (self, Qt.WindowModality windowModality)`
*   `setWindowModified (self, bool)`
*   `setWindowOpacity (self, float level)`
*   `setWindowRole (self, QString)`
*   `setWindowState (self, Qt.WindowStates state)`
*   `setWindowTitle (self, QString)`
*   `show (self)`
*   `showEvent (self, QShowEvent)`
*   `showFullScreen (self)`
*   `showMaximized (self)`
*   `showMinimized (self)`
*   `showNormal (self)`
*   `QSize size (self)`
*   `QSize sizeHint (self)`
*   `QSize sizeIncrement (self)`
*   `QSizePolicy sizePolicy (self)`
*   `stackUnder (self, QWidget)`
*   `QString statusTip (self)`
*   `QStyle style (self)`
*   `QString styleSheet (self)`
*   `tabletEvent (self, QTabletEvent)`
*   `bool testAttribute (self, Qt.WidgetAttribute attribute)`
*   `QString toolTip (self)`
*   `QWidget topLevelWidget (self)`
*   `bool underMouse (self)`
*   `ungrabGesture (self, Qt.GestureType type)`
*   `unsetCursor (self)`
*   `unsetLayoutDirection (self)`
*   `unsetLocale (self)`
*   `update (self)`
*   `update (self, QRect)`
*   `update (self, QRegion)`
*   `update (self, int ax, int ay, int aw, int ah)`
*   `updateGeometry (self)`
*   `updateMicroFocus (self)`
*   `bool updatesEnabled (self)`
*   `QRegion visibleRegion (self)`
*   `QString whatsThis (self)`
*   `wheelEvent (self, QWheelEvent)`
*   `int width (self)`
*   `QWidget window (self)`
*   `windowActivationChange (self, bool)`
*   `QString windowFilePath (self)`
*   `Qt.WindowFlags windowFlags (self)`
*   `QIcon windowIcon (self)`
*   `QString windowIconText (self)`
*   `Qt.WindowModality windowModality (self)`
*   `float windowOpacity (self)`
*   `QString windowRole (self)`
*   `Qt.WindowStates windowState (self)`
*   `QString windowTitle (self)`
*   `Qt.WindowType windowType (self)`
*   `int winId (self)`
*   `int x (self)`
*   `QX11Info x11Info (self)`
*   `int x11PictureHandle (self)`
*   `int y (self)`

### Static Methods

*   `QWidget find (int)`
*   `QWidget keyboardGrabber ()`
*   `QWidget mouseGrabber ()`
*   `setTabOrder (QWidget, QWidget)`

### Qt Signals

*   `void customContextMenuRequested (const QPoint&)`

* * *

## Detailed Description

QWidget的类是所有用户界面对象的基类。

窗口小部件是用户界面的原子：它接收从窗口系统的鼠标，键盘和其它事件，并且描绘了自身的表示在屏幕上。每一小窗口是矩形的，并且它们被排序在Z次序。小部件是由其父，并在它前面的小部件裁剪。

未嵌入在父窗口部件一个部件被称为窗口。通常，窗口有一个框架和一个标题栏，尽管它也可以将创建的窗口，没有这样的装饰用合适的[window flags](qt.html#WindowType-enum)） 。在Qt中，[QMainWindow](qmainwindow.html)和各亚类[QDialog](qdialog.html)是最常见的窗口类型。

每一个部件的构造函数接受一个或两个标准参数：

1.  `QWidget *parent = 0`是新的小部件的父。如果为0 （默认值） ，则新的部件会出现一个窗口。如果不是这样，这将是一个子_parent_以及由被约束_parent_的几何形状（除非您指定[Qt.Window](qt.html#WindowType-enum)作为窗口标志） 。
2.  `Qt.WindowFlags f = 0`（如果有的话）设置窗口的标志，缺省值是适用于几乎所有的小工具，但要获得，例如，没有窗口系统框架的一个窗口，你必须使用特殊标志。

QWidget中有很多成员函数，但其中一些并没有很多直接的功能，例如， QWidget的有一个字体属性，但从来没有使用这个本身。有很多的子类，提供真正的功能，如[QLabel](qlabel.html)，[QPushButton](qpushbutton.html)，[QListWidget](qlistwidget.html)和[QTabWidget](qtabwidget.html)。

### Top-Level and Child Widgets

没有父窗口部件widget是始终是一个独立的窗口（顶层窗口小部件） 。对于这些部件，[setWindowTitle](qwidget.html#windowTitle-prop)（）和[setWindowIcon](qwidget.html#windowIcon-prop)（ ）设置标题栏和图标分别。

非窗口小部件子部件，它们的父窗口部件中显示。大多数部件在Qt的主要可用作子部件。例如，它可以显示一个按钮，一个顶层窗口，但大多数人更愿意把自己的按钮，里面的其他部件，如[QDialog](qdialog.html)。

![A parent widget containing various child widgets.](../img/parent-child-widgets.png)

上图显示了一个[QGroupBox](qgroupbox.html)小工具被用来举办各种子控件中提供的一个布局[QGridLayout](qgridlayout.html)。该[QLabel](qlabel.html)子部件进行了概述，以表明自己的全尺寸。

如果你想使用一个QWidget来保存子控件你通常会希望将布局添加到父QWidget的。看[Layout Management](index.htm)了解更多信息。

### Composite Widgets

当一个部件被用作容器以将一些子部件，它被称为一个复合部件。这些可以通过构造一个小部件所需要的视觉属性来创建 - 一个[QFrame](qframe.html)例如 - 和添加子控件给它，通常由布局管理。上图显示了使用已创建这样一个复合控件[Qt Designer](index.htm#qt-designer)。

复合小部件，也可以通过继承一个标准部件，如QWidget的或创建的[QFrame](qframe.html)，并在子类的构造函数中添加必要的布局和子部件。许多的[examples provided with Qt](index.htm)使用这种方法，而且它也包含在了Qt[Tutorials](index.htm)。

### Custom Widgets and Painting

既然是QWidget的一个子类[QPaintDevice](qpaintdevice.html)，子类可以用来显示正在使用的一系列绘图操作与的实例组成的自定义内容[QPainter](qpainter.html)类。这种方法的对比与所用的帆布风格的方法[Graphics View Framework](index.htm#graphics-view)其中项目被添加到场景的应用程序和框架本身的呈现方式。

每个插件执行所有绘制操作从在其[paintEvent](qwidget.html#paintEvent)（）函数。这就是所谓每当小部件需要重新绘制，无论是作为应用程序所请求的一些外在的改变，或当所致。

该[Analog Clock example](index.htm)显示了一个简单的小工具如何处理绘制事件。

### Size Hints and Size Policies

当实现一个新的部件，它几乎总是有用的重新实现[sizeHint](qwidget.html#sizeHint-prop)（ ）提供合理的默认大小的小部件，并设置正确的大小与政策[setSizePolicy](qwidget.html#sizePolicy-prop)（ ） 。

默认情况下，复合材料部件不提供尺寸暗示将根据其子控件的空间要求的尺寸。

大小策略可以提供良好的默认行为的布局管理系统，使其他部件可以包含并管理你的轻松。默认大小政策表明尺寸暗示代表widget的首选大小，而这往往是许多小部件不够好。

**Note:**顶层窗口小部件的大小被限制到桌面的高度和宽度的2/3。您可以[resize](qwidget.html#size-prop)（ ）小工具手动如果这些边界是不够的。

### Events

小部件是通常是由于用户操作事件进行响应。的Qt通过调用特定的事件处理函数的实例把事件的小部件[QEvent](qevent.html)子类包含有关每个事件的信息。

如果你的widget只包含子控件，你也许并不需要实现任何事件处理程序。如果要检测一个鼠标点击的子控件调用子的[underMouse](qwidget.html#underMouse)（ ）内的部件的功能[mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

该[Scribble example](index.htm)实现了一组事件来处理鼠标移动，按键操作，窗口大小调整为宽。

你需要提供你自己的小部件的行为和内容，但这里是相关的QWidget的，从最常见的事件的简要介绍：

*   [paintEvent](qwidget.html#paintEvent)() is called whenever the widget needs to be repainted. Every widget displaying custom content must implement it. Painting using a [QPainter](qpainter.html) can only take place in a [paintEvent](qwidget.html#paintEvent)() or a function called by a [paintEvent](qwidget.html#paintEvent)().
*   [resizeEvent](qwidget.html#resizeEvent)() is called when the widget has been resized.
*   [mousePressEvent](qwidget.html#mousePressEvent)() is called when a mouse button is pressed while the mouse cursor is inside the widget, or when the widget has grabbed the mouse using [grabMouse](qwidget.html#grabMouse)(). Pressing the mouse without releasing it is effectively the same as calling [grabMouse](qwidget.html#grabMouse)().
*   [mouseReleaseEvent](qwidget.html#mouseReleaseEvent)() is called when a mouse button is released. A widget receives mouse release events when it has received the corresponding mouse press event. This means that if the user presses the mouse inside _your_ widget, then drags the mouse somewhere else before releasing the mouse button, _your_ widget receives the release event. There is one exception: if a popup menu appears while the mouse button is held down, this popup immediately steals the mouse events.
*   [mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)() is called when the user double-clicks in the widget. If the user double-clicks, the widget receives a mouse press event, a mouse release event and finally this event instead of a second mouse press event. (Some mouse move events may also be received if the mouse is not held steady during this operation.) It is _not possible_ to distinguish a click from a double-click until the second click arrives. (This is one reason why most GUI books recommend that double-clicks be an extension of single-clicks, rather than trigger a different action.)

接受键盘输入的小部件需要重新实现几个事件处理程序：

*   [keyPressEvent](qwidget.html#keyPressEvent)() is called whenever a key is pressed, and again when a key has been held down long enough for it to auto-repeat. The **Tab** and **Shift+Tab** keys are only passed to the widget if they are not used by the focus-change mechanisms. To force those keys to be processed by your widget, you must reimplement [QWidget.event](qwidget.html#event)().
*   [focusInEvent](qwidget.html#focusInEvent)() is called when the widget gains keyboard focus (assuming you have called [setFocusPolicy](qwidget.html#focusPolicy-prop)()). Well-behaved widgets indicate that they own the keyboard focus in a clear but discreet way.
*   [focusOutEvent](qwidget.html#focusOutEvent)() is called when the widget loses keyboard focus.

您可能需要重新实现还有些不常见的事件处理程序：

*   [mouseMoveEvent](qwidget.html#mouseMoveEvent)() is called whenever the mouse moves while a mouse button is held down. This can be useful during drag and drop operations. If you call [setMouseTracking](qwidget.html#mouseTracking-prop)(true), you get mouse move events even when no buttons are held down. (See also the [Drag and Drop](index.htm) guide.)
*   [keyReleaseEvent](qwidget.html#keyReleaseEvent)() is called whenever a key is released and while it is held down (if the key is auto-repeating). In that case, the widget will receive a pair of key release and key press event for every repeat. The **Tab** and **Shift+Tab** keys are only passed to the widget if they are not used by the focus-change mechanisms. To force those keys to be processed by your widget, you must reimplement [QWidget.event](qwidget.html#event)().
*   [wheelEvent](qwidget.html#wheelEvent)() is called whenever the user turns the mouse wheel while the widget has the focus.
*   [enterEvent](qwidget.html#enterEvent)() is called when the mouse enters the widget's screen space. (This excludes screen space owned by any of the widget's children.)
*   [leaveEvent](qwidget.html#leaveEvent)() is called when the mouse leaves the widget's screen space. If the mouse enters a child widget it will not cause a [leaveEvent](qwidget.html#leaveEvent)().
*   [moveEvent](qwidget.html#moveEvent)() is called when the widget has been moved relative to its parent.
*   [closeEvent](qwidget.html#closeEvent)() is called when the user closes the widget (or when [close](qwidget.html#close)() is called).

也有对文档中描述的一些默默无闻的事件[QEvent.Type](qevent.html#Type-enum)。为了处理这些事件，你需要重新实现[event](qwidget.html#event)（ ）直接。

的默认实现[event](qwidget.html#event)（ ）句柄**Tab**和**Shift+Tab**（移动键盘焦点） ，并通过对大多数其他活动向更加专业化的处理上面之一。

用于传递他们的活动和机制都包含在[The Event System](index.htm)。

### Groups of Functions and Properties

| Context | Functions and Properties |
| --- | --- |
| Window functions | [show](qwidget.html#show)(), [hide](qwidget.html#hide)(), [raise_](qwidget.html#raise)(), [lower](qwidget.html#lower)(), [close](qwidget.html#close)(). |
| Top-level windows | [windowModified](qwidget.html#windowModified-prop), [windowTitle](qwidget.html#windowTitle-prop), [windowIcon](qwidget.html#windowIcon-prop), [windowIconText](qwidget.html#windowIconText-prop), [isActiveWindow](qwidget.html#isActiveWindow-prop), [activateWindow](qwidget.html#activateWindow)(), [minimized](qwidget.html#minimized-prop), [showMinimized](qwidget.html#showMinimized)(), [maximized](qwidget.html#maximized-prop), [showMaximized](qwidget.html#showMaximized)(), [fullScreen](qwidget.html#fullScreen-prop), [showFullScreen](qwidget.html#showFullScreen)(), [showNormal](qwidget.html#showNormal)(). |
| Window contents | [update](qwidget.html#update)(), [repaint](qwidget.html#repaint)(), [scroll](qwidget.html#scroll)(). |
| Geometry | [pos](qwidget.html#pos-prop), [x](qwidget.html#x-prop)(), [y](qwidget.html#y-prop)(), [rect](qwidget.html#rect-prop), [size](qwidget.html#size-prop), [width](qwidget.html#width-prop)(), [height](qwidget.html#height-prop)(), [move](qwidget.html#pos-prop)(), [resize](qwidget.html#size-prop)(), [sizePolicy](qwidget.html#sizePolicy-prop), [sizeHint](qwidget.html#sizeHint-prop)(), [minimumSizeHint](qwidget.html#minimumSizeHint-prop)(), [updateGeometry](qwidget.html#updateGeometry)(), [layout](qwidget.html#layout)(), [frameGeometry](qwidget.html#frameGeometry-prop), [geometry](qwidget.html#geometry-prop), [childrenRect](qwidget.html#childrenRect-prop), [childrenRegion](qwidget.html#childrenRegion-prop), [adjustSize](qwidget.html#adjustSize)(), [mapFromGlobal](qwidget.html#mapFromGlobal)(), [mapToGlobal](qwidget.html#mapToGlobal)(), [mapFromParent](qwidget.html#mapFromParent)(), [mapToParent](qwidget.html#mapToParent)(), [maximumSize](qwidget.html#maximumSize-prop), [minimumSize](qwidget.html#minimumSize-prop), [sizeIncrement](qwidget.html#sizeIncrement-prop), [baseSize](qwidget.html#baseSize-prop), [setFixedSize](qwidget.html#setFixedSize)() |
| Mode | [visible](qwidget.html#visible-prop), [isVisibleTo](qwidget.html#isVisibleTo)(), [enabled](qwidget.html#enabled-prop), [isEnabledTo](qwidget.html#isEnabledTo)(), [modal](qwidget.html#modal-prop), [isWindow](qwidget.html#isWindow)(), [mouseTracking](qwidget.html#mouseTracking-prop), [updatesEnabled](qwidget.html#updatesEnabled-prop), [visibleRegion](qwidget.html#visibleRegion)(). |
| Look and feel | [style](qwidget.html#style)(), [setStyle](qwidget.html#setStyle)(), [styleSheet](qwidget.html#styleSheet-prop), [cursor](qwidget.html#cursor-prop), [font](qwidget.html#font-prop), [palette](qwidget.html#palette-prop), [backgroundRole](qwidget.html#backgroundRole)(), [setBackgroundRole](qwidget.html#setBackgroundRole)(), [fontInfo](qwidget.html#fontInfo)(), [fontMetrics](qwidget.html#fontMetrics)(). |
| Keyboard focus functions | [focus](qwidget.html#focus-prop), [focusPolicy](qwidget.html#focusPolicy-prop), [setFocus](qwidget.html#setFocus)(), [clearFocus](qwidget.html#clearFocus)(), [setTabOrder](qwidget.html#setTabOrder)(), [setFocusProxy](qwidget.html#setFocusProxy)(), [focusNextChild](qwidget.html#focusNextChild)(), [focusPreviousChild](qwidget.html#focusPreviousChild)(). |
| Mouse and keyboard grabbing | [grabMouse](qwidget.html#grabMouse)(), [releaseMouse](qwidget.html#releaseMouse)(), [grabKeyboard](qwidget.html#grabKeyboard)(), [releaseKeyboard](qwidget.html#releaseKeyboard)(), [mouseGrabber](qwidget.html#mouseGrabber)(), [keyboardGrabber](qwidget.html#keyboardGrabber)(). |
| Event handlers | [event](qwidget.html#event)(), [mousePressEvent](qwidget.html#mousePressEvent)(), [mouseReleaseEvent](qwidget.html#mouseReleaseEvent)(), [mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)(), [mouseMoveEvent](qwidget.html#mouseMoveEvent)(), [keyPressEvent](qwidget.html#keyPressEvent)(), [keyReleaseEvent](qwidget.html#keyReleaseEvent)(), [focusInEvent](qwidget.html#focusInEvent)(), [focusOutEvent](qwidget.html#focusOutEvent)(), [wheelEvent](qwidget.html#wheelEvent)(), [enterEvent](qwidget.html#enterEvent)(), [leaveEvent](qwidget.html#leaveEvent)(), [paintEvent](qwidget.html#paintEvent)(), [moveEvent](qwidget.html#moveEvent)(), [resizeEvent](qwidget.html#resizeEvent)(), [closeEvent](qwidget.html#closeEvent)(), [dragEnterEvent](qwidget.html#dragEnterEvent)(), [dragMoveEvent](qwidget.html#dragMoveEvent)(), [dragLeaveEvent](qwidget.html#dragLeaveEvent)(), [dropEvent](qwidget.html#dropEvent)(), [childEvent](qobject.html#childEvent)(), [showEvent](qwidget.html#showEvent)(), [hideEvent](qwidget.html#hideEvent)(), [customEvent](qobject.html#customEvent)(). [changeEvent](qwidget.html#changeEvent)(), |
| System functions | [parentWidget](qwidget.html#parentWidget)(), [window](qwidget.html#window)(), [setParent](qwidget.html#setParent)(), [winId](qwidget.html#winId)(), [find](qwidget.html#find)(), [metric](qwidget.html#metric)(). |
| Interactive help | [setToolTip](qwidget.html#toolTip-prop)(), [setWhatsThis](qwidget.html#whatsThis-prop)() |

### Widget Style Sheets

除了标准窗口小部件的样式为每个平台，窗口小部件，也可根据在指定的规则样式[style sheet](qwidget.html#styleSheet-prop)。此功能使您可以自定义特定的部件来提供视觉线索来了解他们的目的用户的外观。例如，按钮可以被装饰以一种特定的方式，以表明它执行一个破坏性的动作。

使用插件的样式表中有更详细的描述[Qt Style Sheets](index.htm)文档。

### Transparency and Double Buffering

由于Qt的4.0 ， QWidget的自动双缓冲的画，所以没有必要在写双缓冲的代码[paintEvent](qwidget.html#paintEvent)（）来避免闪烁。

由于Qt的4.1 ，该[Qt.WA_ContentsPropagated](qt.html#WidgetAttribute-enum)部件属性已被否决。相反，父窗口部件的内容默认情况下每个孩子只要传播[Qt.WA_PaintOnScreen](qt.html#WidgetAttribute-enum)未设置。自定义部件可以被写入到利用此功能通过更新不规则区域（创建非矩形子部件） ，或绘画与具有低于全alpha分量的颜色。下图显示了如何属性和自定义窗口小部件的属性可以微调，以达到不同的效果。

![](../img/propagation-custom.png)

在上面的图中，一个半透明的矩形子构件与删除的区域构造并添加到父控件（一个[QLabel](qlabel.html)显示一个像素映射） 。然后，不同的特性和部件的属性都设置为实现不同的效果：

*   The left widget has no additional properties or widget attributes set. This default state suits most custom widgets using transparency, are irregularly-shaped, or do not paint over their entire area with an opaque brush.
*   The center widget has the [autoFillBackground](qwidget.html#autoFillBackground-prop) property set. This property is used with custom widgets that rely on the widget to supply a default background, and do not paint over their entire area with an opaque brush.
*   The right widget has the [Qt.WA_OpaquePaintEvent](qt.html#WidgetAttribute-enum) widget attribute set. This indicates that the widget will paint over its entire area with opaque colors. The widget's area will initially be _uninitialized_, represented in the diagram with a red diagonal grid pattern that shines through the overpainted area. The Qt.WA_OpaquePaintArea attribute is useful for widgets that need to paint their own specialized contents quickly and do not need a default filled background.

快速更新的自定义部件与简单的背景颜色，比如实时绘图或图形元件，它是更好地定义一个合适的背景色（使用[setBackgroundRole](qwidget.html#setBackgroundRole)（）与[QPalette.Window](qpalette.html#ColorRole-enum)作用） ，设置[autoFillBackground](qwidget.html#autoFillBackground-prop)财产，只有落实在widget的必要的绘图功能[paintEvent](qwidget.html#paintEvent)（ ） 。

快速更新的自定义部件，他们的整个领域不断油漆过不透明的内容，如视频流部件，最好是设置widget的[Qt.WA_OpaquePaintEvent](qt.html#WidgetAttribute-enum)，避免与重画窗口部件的背景相关的任何不必要的开销。

如果某个部件有两个[Qt.WA_OpaquePaintEvent](qt.html#WidgetAttribute-enum)部件属性_and_该[autoFillBackground](qwidget.html#autoFillBackground-prop)属性集，[Qt.WA_OpaquePaintEvent](qt.html#WidgetAttribute-enum)属性优先。根据您的要求，您应该选择其中任何一个。

由于Qt的4.1 ，父窗口部件的内容也传播到标准的Qt部件。这可能会导致一些意想不到的结果，如果父窗口部件都装饰以非标准的方式，如下图所示图中。

![](../img/propagation-standard.png)

范围为自定义的标准Qt控件的绘制行为，而不诉诸子类，比可能略有不足为自定义控件。通常，一个标准窗口小部件的所需的外观可以通过设置来实现其[autoFillBackground](qwidget.html#autoFillBackground-prop)属性。

### Creating Translucent Windows

由于Qt的4.5 ，已经可以用在支持合成窗口系统半透明区域创建窗口。

要启用此功能在顶层窗口部件，设置其[Qt.WA_TranslucentBackground](qt.html#WidgetAttribute-enum)带属性[setAttribute](qwidget.html#setAttribute)（） ，并确保其背景是画与非不透明的颜色，你想是部分透明的区域。

平台注意事项：

*   X11: This feature relies on the use of an X server that supports ARGB visuals and a compositing window manager.
*   Windows: The widget needs to have the [Qt.FramelessWindowHint](qt.html#WindowType-enum) window flag set for the translucency to work.

### Native Widgets vs Alien Widgets

在Qt的4.4推出，外星人小部件小部件未知的窗口系统。他们没有与之关联的本地窗口句柄。此功能显着加快小部件涂装，调整大小和删除闪烁。

如果您需要使用本机窗口旧的行为，您可以选择下列选项之一：

1.  使用`QT_USE_NATIVE_WINDOWS=1`在您的环境。
2.  设置[Qt.AA_NativeWindows](qt.html#ApplicationAttribute-enum)属性在你的应用程序。所有的部件将是原生窗口部件。
3.  设置[Qt.WA_NativeWindow](qt.html#WidgetAttribute-enum)属性上的小部件：该部件本身及其所有祖先将成为本机（除非[Qt.WA_DontCreateNativeAncestors](qt.html#WidgetAttribute-enum)设置） 。
4.  呼叫QWidget.winId执行本机窗口（这意味着3 ） 。
5.  设置[Qt.WA_PaintOnScreen](qt.html#WidgetAttribute-enum)属性来执行本机窗口（这意味着3 ） 。

### Softkeys

自的Qt 4.6 ，软键通常是一个装置，其具有一般旁其物理副本位于屏幕上的一个对应的标籤或其它视觉表示上的物理键。它们最常在手机平台上找到。在现代的基于触摸的用户界面，也可以向具有不对应于任何物理键的软键。软键从其他屏幕上的标籤，因为它们的上下文不同。

在Qt中，上下文软键通过调用加入到一个widget[addAction](qwidget.html#addAction)（ ），并传递`QAction`用软键角色设置就可以了。当含有软键操作的控件具有焦点时，它的功能键应该会出现在用户界面中。软键被发现通过遍历控件层次结构，以便它可以通过调用定义一组自定义功能键，是目前在任何时候都[addAction](qwidget.html#addAction)（ ）对于给定的顶级窗口部件。

在某些平台上，这个概念有重叠`QMenuBar`这样，如果没有其他软键发现和顶级窗口部件是一个[QMainWindow](qmainwindow.html)含[QMenuBar](qmenubar.html)，菜单栏的操作可能会出现在软键之一。

注：目前软键只支持Symbian平台上。

* * *

## Type Documentation

```
QWidget.RenderFlag
```

这个枚举变量描述了如何调用时呈现控件[QWidget.render](qwidget.html#render)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QWidget.DrawWindowBackground` | `0x1` | 如果启用此选项， widget的背景渲染到目标，即使[autoFillBackground](qwidget.html#autoFillBackground-prop)未设置。默认情况下，启用此选项。 |
| `QWidget.DrawChildren` | `0x2` | 如果启用此选项， widget的孩子们递归渲染到目标。默认情况下，启用此选项。 |
| `QWidget.IgnoreMask` | `0x4` | 如果启用此选项， widget的[QWidget.mask](qwidget.html#mask)（ ）被渲染到目标时忽略。默认情况下，该选项被禁用。 |

这个枚举被引入或修改的Qt 4.3 。

该RenderFlags类型是一个typedef为[QFlags](index.htm)\u003cRenderFlag\u003e 。它存储RenderFlag值的或组合。

* * *

## Method Documentation

```
QWidget.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个控件这是一个孩子_parent_，与窗口部件标记设置为_f_。

If _parent_为0时，新的小部件变成一个窗口。如果_parent_是另一个小工具，这个小工具变成里面的一个子窗口_parent_。新的部件将被删除时，其_parent_被删除。

窗口小部件flags参数，_f_，通常是0，但它可以被设置来定制窗口的框架（即_parent_必须为0 ） 。要自定义的框架，选用显示一个从任何的按位OR值组成[window flags](qt.html#WindowType-enum)。

如果您添加一个子部件到一个已经可见小工具你必须明确地表明孩子以使其可见。

请注意， X11版本的Qt可能无法提供风格标志的所有组合在所有系统上。这是因为在X11上， Qt可以只问了窗口管理器，窗口管理器可以复盖应用程序的设置。在Windows上， Qt可以设置任何标志你想要的。

**See also** [windowFlags](qwidget.html#windowFlags-prop)。

```
bool QWidget.acceptDrops (self)
```

```
QString QWidget.accessibleDescription (self)
```

```
QString QWidget.accessibleName (self)
```

```
QWidget.actionEvent (self, QActionEvent)
```

此事件处理程序被调用给定的_event_每当控件的行为被改变。

**See also** [addAction](qwidget.html#addAction)（ ）[insertAction](qwidget.html#insertAction)（ ）[removeAction](qwidget.html#removeAction)（ ）[actions](qwidget.html#actions)（）和[QActionEvent](qactionevent.html)。

```
list-of-QAction QWidget.actions (self)
```

返回这个窗口部件的动作（可能为空）列表。

**See also** [contextMenuPolicy](qwidget.html#contextMenuPolicy-prop)，[insertAction](qwidget.html#insertAction)（）和[removeAction](qwidget.html#removeAction)（ ） 。

```
QWidget.activateWindow (self)
```

设置包含该控件是活动窗口中的顶级窗口部件。

活动窗口是可见的顶层窗口拥有键盘输入焦点。

此函数执行相同的操作，点击一个顶层窗口的标题栏上的鼠标。在X11上，其结果取决于窗口管理器。如果你想确保窗口被堆放在顶部以及你也应该调用[raise_](qwidget.html#raise)（ ） 。注意，这个窗口必须是可见的，否则activateWindow （）没有任何影响。

在Windows中，如果要调用这个应用程序时，当前不是活跃的地区之一那么它不会使其成为活动窗口。它将改变任务栏项的颜色，以指示该窗口已经以某种方式改变。这是因为微软不允许应用程序中断当前用户正在做的另一个应用是什么。

**See also** [isActiveWindow](qwidget.html#isActiveWindow-prop)（ ）[window](qwidget.html#window)（）和[show](qwidget.html#show)（ ） 。

```
QWidget.addAction (self, QAction action)
```

追加行动_action_以行动这个小工具的列表。

所有QWidgets具有列表[QAction](qaction.html)秒，但是它们可以被以图形方式在许多不同的方式来表示。在默认情况下使用的[QAction](qaction.html)列表（所返回[actions](qwidget.html#actions)（））是创建一个上下文[QMenu](qmenu.html)。

A [QWidget](qwidget.html)应该只有每个动作中的一个，并将其添加已经有一个操作不会导致相同的动作是在插件的两倍。

所有权_action_不转移到该[QWidget](qwidget.html)。

**See also** [removeAction](qwidget.html#removeAction)（ ）[insertAction](qwidget.html#insertAction)（ ）[actions](qwidget.html#actions)（）和[QMenu](qmenu.html)。

```
QWidget.addActions (self, list-of-QAction actions)
```

追加行动_actions_以行动这个小工具的列表。

**See also** [removeAction](qwidget.html#removeAction)（ ）[QMenu](qmenu.html)和[addAction](qwidget.html#addAction)（ ） 。

```
QWidget.adjustSize (self)
```

调整小部件的大小，以适合其内容。

此函数使用[sizeHint](qwidget.html#sizeHint-prop)（）如果它是有效的，即尺寸暗示的宽度和高度都\u003e = 0 。否则，将大小设置为子女矩形复盖所有子控件（所有子控件矩形的联合） 。

对于Windows，屏幕尺寸也考虑在内。如果[sizeHint](qwidget.html#sizeHint-prop)（）是小于（200， 100）和大小策略是[expanding](qsizepolicy.html#Policy-enum)时，窗口将至少（200 ，100）。窗口的最大尺寸就是屏幕的宽度和高度的2/3 。

**See also** [sizeHint](qwidget.html#sizeHint-prop)（）和[childrenRect](qwidget.html#childrenRect-prop)（ ） 。

```
bool QWidget.autoFillBackground (self)
```

```
QPalette.ColorRole QWidget.backgroundRole (self)
```

[

返回构件的背景的角色。

](qpalette.html#ColorRole-enum)

[背景角色定义的画笔从部件的](qpalette.html#ColorRole-enum)[palette](qwidget.html#palette-prop)用于呈现的背景。

如果没有明确的背景角色设置，窗口小部件继承了变量其父控件的背景作用。

**See also** [setBackgroundRole](qwidget.html#setBackgroundRole)（）和[foregroundRole](qwidget.html#foregroundRole)（ ） 。

```
QSize QWidget.baseSize (self)
```

[

```
QWidget.changeEvent (self, QEvent)
```

此事件处理程序可以重新实现来处理状态的变化。

在这种情况下被改变的状态可以通过检索_event_提供。

](qsize.html)

[更改事件包括：](qsize.html)[QEvent.ToolBarChange](qevent.html#Type-enum)，[QEvent.ActivationChange](qevent.html#Type-enum)，[QEvent.EnabledChange](qevent.html#Type-enum)，[QEvent.FontChange](qevent.html#Type-enum)，[QEvent.StyleChange](qevent.html#Type-enum)，[QEvent.PaletteChange](qevent.html#Type-enum)，[QEvent.WindowTitleChange](qevent.html#Type-enum)，[QEvent.IconTextChange](qevent.html#Type-enum)，[QEvent.ModifiedChange](qevent.html#Type-enum)，[QEvent.MouseTrackingChange](qevent.html#Type-enum)，[QEvent.ParentChange](qevent.html#Type-enum)，[QEvent.WindowStateChange](qevent.html#Type-enum)，[QEvent.LanguageChange](qevent.html#Type-enum)，[QEvent.LocaleChange](qevent.html#Type-enum)，[QEvent.LayoutDirectionChange](qevent.html#Type-enum)。

```
QWidget QWidget.childAt (self, QPoint p)
```

[

返回该位置的可见子控件（_x_，_y_） widget的坐标系中。如果没有可见的子窗口部件在指定位置，则函数返回0 。

](qwidget.html)

```
QWidget QWidget.childAt (self, int ax, int ay)
```

[](qwidget.html)

```
QRect QWidget.childrenRect (self)
```

[](qrect.html)

```
QRegion QWidget.childrenRegion (self)
```

[

```
QWidget.clearFocus (self)
```

采用键盘输入焦点从窗口小部件。

](qregion.html)

[如果部件有主动对焦，一](qregion.html)[focus out event](qwidget.html#focusOutEvent)被送到这个小工具来告诉它，它是即将失去焦点。

这个小工具必须以获得键盘输入焦点使对焦设定，也就是说，它必须调用[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ） 。

**See also** [hasFocus](qwidget.html#focus-prop)（ ）[setFocus](qwidget.html#setFocus)（ ）[focusInEvent](qwidget.html#focusInEvent)（ ）[focusOutEvent](qwidget.html#focusOutEvent)（ ）[setFocusPolicy](qwidget.html#focusPolicy-prop)（）和[QApplication.focusWidget](qapplication.html#focusWidget)（ ） 。

```
QWidget.clearMask (self)
```

删除通过设置任何面膜[setMask](qwidget.html#setMask)（ ） 。

**See also** [setMask](qwidget.html#setMask)（ ） 。

```
bool QWidget.close (self)
```

这种方法也是一个Qt槽与C + +的签名`bool close()`。

关闭此窗口小部件。返回True如果部件被关闭，否则返回False 。

首先，它发送一个部件[QCloseEvent](qcloseevent.html)。该部件是[hidden](qwidget.html#hide)如果[accepts](qevent.html#accept)close事件。如果[ignores](qevent.html#ignore)的情况下，没有任何反应。的默认实现[QWidget.closeEvent](qwidget.html#closeEvent)（）接受close事件。

如果部件有[Qt.WA_DeleteOnClose](qt.html#WidgetAttribute-enum)国旗，小部件也将被删除。密切的事件被传递到插件不管小窗口是可见或不可见。

该[QApplication.lastWindowClosed](qapplication.html#lastWindowClosed)（ ）信号被发射时的最后一个可见的主窗口（即没有父窗口）与[Qt.WA_QuitOnClose](qt.html#WidgetAttribute-enum)属性设置是关闭的。默认情况下，此属性设置为所有部件，除了短暂的窗口，如闪屏，工具窗口，以及弹出式菜单。

```
QWidget.closeEvent (self, QCloseEvent)
```

此事件处理程序被调用给定的_event_当Qt的接收来自窗口系统的顶层窗口部件的窗口关闭请求。

默认情况下，事件被接受和小部件被关闭。您可以重新实现这个函数来改变窗口部件响应窗口关闭请求的方式。例如，你可以通过调用阻止窗口关闭[ignore()](qevent.html#ignore)在所有的事件。

主窗口的应用程序通常使用此功能的重新实现来检查用户的工作是否已经被保存和关闭之前请求许可。例如，本[Application Example](index.htm)使用一个辅助函数来决定是否关闭该窗口：

```
 void MainWindow.closeEvent([QCloseEvent](qcloseevent.html) *event)
 {
     if (maybeSave()) {
         writeSettings();
         event->accept();
     } else {
         event->ignore();
     }
 }

```

**See also** [event](qwidget.html#event)（ ）[hide](qwidget.html#hide)（ ）[close](qwidget.html#close)（ ）[QCloseEvent](qcloseevent.html)和[Application Example](index.htm)。

```
QMargins QWidget.contentsMargins (self)
```

[

该contentsMargins函数返回控件的内容利润率。

此功能被引入Qt的4.6 。

](qmargins.html)

[**See also**](qmargins.html) [getContentsMargins](qwidget.html#getContentsMargins)（ ）[setContentsMargins](qwidget.html#setContentsMargins)（）和[contentsRect](qwidget.html#contentsRect)（ ） 。

```
QRect QWidget.contentsRect (self)
```

[

返回小部件的边距之内的区域。

](qrect.html)

[**See also**](qrect.html) [setContentsMargins](qwidget.html#setContentsMargins)（）和[getContentsMargins](qwidget.html#getContentsMargins)（ ） 。

```
QWidget.contextMenuEvent (self, QContextMenuEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收部件的上下文菜单事件。

该处理程序被调用时，窗口小部件的[contextMenuPolicy](qwidget.html#contextMenuPolicy-prop) is [Qt.DefaultContextMenu](qt.html#ContextMenuPolicy-enum)。

默认实现忽略上下文的事件。请参阅[QContextMenuEvent](qcontextmenuevent.html)文档了解更多信息。

**See also** [event](qwidget.html#event)（ ）[QContextMenuEvent](qcontextmenuevent.html)和[customContextMenuRequested](qwidget.html#customContextMenuRequested)（ ） 。

```
Qt.ContextMenuPolicy QWidget.contextMenuPolicy (self)
```

[

```
QWidget.create (self, int window = 0, bool initializeWindow = True, bool destroyOldWindow = True)
```

创建一个新的小部件窗口，如果_window_为0 ，否则设置widget的窗口_window_。

初始化窗口（设置几何等） ，如果_initializeWindow_是真实的。如果_initializeWindow_是假的，没有执行初始化。此参数才有意义，如果_window_是一个有效的窗口。

销毁旧的窗口，如果_destroyOldWindow_是真实的。如果_destroyOldWindow_是假的，你有责任销毁自己的窗口（使用平台的本机代码） 。

](qt.html#ContextMenuPolicy-enum)

[该](qt.html#ContextMenuPolicy-enum)[QWidget](qwidget.html)构造函数调用创建（ 0 ， TRUE，TRUE ）来创建这个小工具的窗口。

```
QCursor QWidget.cursor (self)
```

[

```
QWidget.destroy (self, bool destroyWindow = True, bool destroySubWindows = True)
```

释放窗口系统资源。销毁小部件窗口，如果_destroyWindow_是真实的。

destroy（）方法调用自身的递归所有子控件，通过_destroySubWindows_为_destroyWindow_参数。为了更好地控制破坏subwidgets ，灭subwidgets选择性第一。

](qcursor.html)

[这个功能通常是从称为](qcursor.html)[QWidget](qwidget.html)析构函数。

```
int QWidget.devType (self)
```

```
QWidget.dragEnterEvent (self, QDragEnterEvent)
```

当拖动正在进行中，鼠标进入这个小工具此事件处理程序被调用。该事件被传递的_event_参数。

如果事件被忽略，小部件将无法接收任何[drag move events](qwidget.html#dragMoveEvent)。

请参阅[Drag-and-drop documentation](index.htm)对于如何提供拖放和拖放在你的应用程序的概述。

**See also** [QDrag](qdrag.html)和[QDragEnterEvent](qdragenterevent.html)。

```
QWidget.dragLeaveEvent (self, QDragLeaveEvent)
```

当拖动正在进行中，鼠标离开这个小工具此事件处理程序被调用。该事件被传递的_event_参数。

请参阅[Drag-and-drop documentation](index.htm)对于如何提供拖放和拖放在你的应用程序的概述。

**See also** [QDrag](qdrag.html)和[QDragLeaveEvent](qdragleaveevent.html)。

```
QWidget.dragMoveEvent (self, QDragMoveEvent)
```

此事件处理程序被调用，如果拖动操作正在进行，并以下任一情况发生时：光标进入这个小工具，将光标移到这个小工具中，或者修改键是在键盘上按下了这个widget具有焦点。该事件被传递的_event_参数。

请参阅[Drag-and-drop documentation](index.htm)对于如何提供拖放和拖放在你的应用程序的概述。

**See also** [QDrag](qdrag.html)和[QDragMoveEvent](qdragmoveevent.html)。

```
QWidget.dropEvent (self, QDropEvent)
```

当拖动被丢弃这个widget此事件处理程序被调用。该事件被传递的_event_参数。

请参阅[Drag-and-drop documentation](index.htm)对于如何提供拖放和拖放在你的应用程序的概述。

**See also** [QDrag](qdrag.html)和[QDropEvent](qdropevent.html)。

```
int QWidget.effectiveWinId (self)
```

返回小部件的有效窗口系统标识符，即原生父母的视窗系统标识符。

如果widget是本地的，则该函数返回本地部件编号。否则，第一款原生父控件的窗口ID ，即包含此插件的顶级窗口部件，返回。

**Note:**我们建议您不要存储这个值，因为它很可能会改变在运行时。

此功能被引入Qt的4.4 。

**See also** [nativeParentWidget](qwidget.html#nativeParentWidget)（ ） 。

```
QWidget.enabledChange (self, bool)
```

```
QWidget.ensurePolished (self)
```

确保插件已被抛光以[QStyle](qstyle.html)（即，具有适当的字体和调色板） 。

[QWidget](qwidget.html)调用这个函数已经完全构造，但它显示的第一时间后前。如果你想确保部件是做一个操作，比如之前抛光就可以调用这个函数，正确的字体大小，可能需要在widget的[sizeHint](qwidget.html#sizeHint-prop)（ ）重新实现。注意，该函数_is_从默认实现所谓的[sizeHint](qwidget.html#sizeHint-prop)（ ） 。

抛光是所有构造函数（从基类，以及从子类）后，必须发生的被称为最后的初始化非常有用。

如果您需要更改一些设置，当一个部件进行抛光，重新实现[event](qwidget.html#event)（）和处理[QEvent.Polish](qevent.html#Type-enum)事件类型。

**Note:**该函数声明为const ，以便它可以从其他的const函数（例如被调用，[sizeHint](qwidget.html#sizeHint-prop)（））。

**See also** [event](qwidget.html#event)（ ） 。

```
QWidget.enterEvent (self, QEvent)
```

此事件处理程序可以重新实现在子类来接收窗口部件进入其传递的事件_event_参数。

一个事件被发送到插件当鼠标光标进入窗口小部件。

**See also** [leaveEvent](qwidget.html#leaveEvent)（ ）[mouseMoveEvent](qwidget.html#mouseMoveEvent)（）和[event](qwidget.html#event)（ ） 。

```
bool QWidget.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

这是主要的事件处理程序，它处理事件_event_。您可以在子类中重新实现这个功能，但是我们建议您使用一个专门的事件处理程序来代替。

按键和释放事件的处理方式不同的其他活动。为Tab和Shift + Tab键事件（）检查，并尝试适当地移动焦点。如果没有小部件将焦点移动到（或者按键不是Tab或Shift + Tab键） ，事件（ ）的调用[keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

鼠标和平板事件处理也略显特殊：只有当小部件是[enabled](qwidget.html#enabled-prop)，事件（ ）将调用专门的处理程序，如[mousePressEvent](qwidget.html#mousePressEvent)（ ） ，否则将丢弃该事件。

这个函数返回，如果该事件被确认True，否则返回False 。如果识别出事件被接受（见[QEvent.accepted](qevent.html#accepted-prop)） ，任何进一步的处理，如事件传播到父widget停止。

**See also** [closeEvent](qwidget.html#closeEvent)（ ）[focusInEvent](qwidget.html#focusInEvent)（ ）[focusOutEvent](qwidget.html#focusOutEvent)（ ）[enterEvent](qwidget.html#enterEvent)（ ）[keyPressEvent](qwidget.html#keyPressEvent)（ ）[keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ）[leaveEvent](qwidget.html#leaveEvent)（ ）[mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ）[mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ）[mousePressEvent](qwidget.html#mousePressEvent)（ ）[mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ）[moveEvent](qwidget.html#moveEvent)（ ）[paintEvent](qwidget.html#paintEvent)（ ）[resizeEvent](qwidget.html#resizeEvent)（ ）[QObject.event](qobject.html#event)（）和[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QWidget QWidget.find (int)
```

[

返回一个指向与窗口标识符/句柄的小工具_id_。

窗口标识符类型取决于底层窗口系统上，见`qwindowdefs.h`对于实际的定义。如果没有与此标识符没有小部件，则返回0 。

```
QWidget.focusInEvent (self, QFocusEvent)
```

此事件处理程序可以重新实现在子类中接收键盘焦点事件（收到的焦点）的部件。该事件被传递的_event_参数

](qwidget.html)

[窗口小部件通常必须](qwidget.html)[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）的东西比其他[Qt.NoFocus](qt.html#FocusPolicy-enum)为了获得焦点事件。 （请注意，应用程序员可以调用[setFocus](qwidget.html#setFocus)（ ）上的任何部件，即使是那些通常不接受焦点。 ）

默认实现更新微件（除了窗户，不指定[focusPolicy](qwidget.html#focusPolicy-prop)（））。

**See also** [focusOutEvent](qwidget.html#focusOutEvent)（ ）[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）[keyPressEvent](qwidget.html#keyPressEvent)（ ）[keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ）[event](qwidget.html#event)（）和[QFocusEvent](qfocusevent.html)。

```
bool QWidget.focusNextChild (self)
```

发现一个新的widget ，让键盘焦点，以适合**Tab**，并返回True，如果能找到一个新的部件，还是假的，如果它不能。

**See also** [focusPreviousChild](qwidget.html#focusPreviousChild)（ ） 。

```
bool QWidget.focusNextPrevChild (self, bool next)
```

发现一个新的widget ，让键盘焦点，以适合Tab和Shift + Tab键，如果能找到一个新的widget返回True ，否则返回FALSE ，如果它不能。

If _next_诚然，这个函数向前搜索，如果_next_是假的，它向后搜索。

有时候，你会希望重新实现这个函数。例如，一个Web浏览器可能会重新实现它来移动它的“当前活动链接”向前或向后，并调用focusNextPrevChild （）只有当它达到“页”上的最后一个或第一个链接。

子控件调用focusNextPrevChild （ ）对它们的父窗口部件，但只有包含的子控件的窗口决定重定向到哪里焦点。通过重新实现这个函数的对象，因此你获得控制焦点遍历所有子控件。

**See also** [focusNextChild](qwidget.html#focusNextChild)（）和[focusPreviousChild](qwidget.html#focusPreviousChild)（ ） 。

```
QWidget.focusOutEvent (self, QFocusEvent)
```

此事件处理程序可以重新实现在子类中接收键盘焦点事件（焦点丢失）的部件。该事件被传递的_event_参数。

窗口小部件通常必须[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）的东西比其他[Qt.NoFocus](qt.html#FocusPolicy-enum)为了获得焦点事件。 （请注意，应用程序员可以调用[setFocus](qwidget.html#setFocus)（ ）上的任何部件，即使是那些通常不接受焦点。 ）

默认实现更新微件（除了窗户，不指定[focusPolicy](qwidget.html#focusPolicy-prop)（））。

**See also** [focusInEvent](qwidget.html#focusInEvent)（ ）[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）[keyPressEvent](qwidget.html#keyPressEvent)（ ）[keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ）[event](qwidget.html#event)（）和[QFocusEvent](qfocusevent.html)。

```
Qt.FocusPolicy QWidget.focusPolicy (self)
```

[

```
bool QWidget.focusPreviousChild (self)
```

发现一个新的widget ，让键盘焦点，以适合**Shift+Tab**，并返回True，如果能找到一个新的部件，还是假的，如果它不能。

](qt.html#FocusPolicy-enum)

[**See also**](qt.html#FocusPolicy-enum) [focusNextChild](qwidget.html#focusNextChild)（ ） 。

```
QWidget QWidget.focusProxy (self)
```

[

返回焦点代理，或者0 ，如果没有焦点代理。

](qwidget.html)

[**See also**](qwidget.html) [setFocusProxy](qwidget.html#setFocusProxy)（ ） 。

```
QWidget QWidget.focusWidget (self)
```

[

返回这个窗口部件的setFocus一直呼吁的最后一个孩子。对于顶级窗口部件，这是小部件，将获得焦点的情况下这个窗口被激活

](qwidget.html)

[这是不一样的](qwidget.html)[QApplication.focusWidget](qapplication.html#focusWidget)（ ），它返回的焦点部件在当前活动窗口。

```
QFont QWidget.font (self)
```

[

```
QWidget.fontChange (self, QFont)
```

](qfont.html)

```
QFontInfo QWidget.fontInfo (self)
```

[](qfontinfo.html)

[返回控件的当前字体的字体信息。相当于QFontInto （小部件 - \u003e](qfontinfo.html)[font](qwidget.html#font-prop)（））。

**See also** [font](qwidget.html#font-prop)（ ）[fontMetrics](qwidget.html#fontMetrics)（）和[setFont](qwidget.html#font-prop)（ ） 。

```
QFontMetrics QWidget.fontMetrics (self)
```

[](qfontmetrics.html)

[返回字体度量小部件的当前字体。相当于](qfontmetrics.html)[QFontMetrics](qfontmetrics.html)（小部件 - \u003e[font](qwidget.html#font-prop)（））。

**See also** [font](qwidget.html#font-prop)（ ）[fontInfo](qwidget.html#fontInfo)（）和[setFont](qwidget.html#font-prop)（ ） 。

```
QPalette.ColorRole QWidget.foregroundRole (self)
```

[

返回前台的角色。

](qpalette.html#ColorRole-enum)

[前台角色定义的颜色从部件的](qpalette.html#ColorRole-enum)[palette](qwidget.html#palette-prop)用于绘制前台。

如果没有明确的前景角色设置，该函数将返回与背景的角色对比的作用。

**See also** [setForegroundRole](qwidget.html#setForegroundRole)（）和[backgroundRole](qwidget.html#backgroundRole)（ ） 。

```
QRect QWidget.frameGeometry (self)
```

[](qrect.html)

```
QSize QWidget.frameSize (self)
```

[](qsize.html)

```
QRect QWidget.geometry (self)
```

[

```
(int left, int top, int right, int bottom) QWidget.getContentsMargins (self)
```

返回widget的内容利润率_left_，_top_，_right_和_bottom_。

](qrect.html)

[**See also**](qrect.html) [setContentsMargins](qwidget.html#setContentsMargins)（）和[contentsRect](qwidget.html#contentsRect)（ ） 。

```
QWidget.grabGesture (self, Qt.GestureType type, Qt.GestureFlags flags = Qt.GestureFlags(0))
```

Subscribes the widget to a given _gesture_ with specific _flags_.

此功能被引入Qt的4.6 。

**See also** [ungrabGesture](qwidget.html#ungrabGesture)（）和[QGestureEvent](qgestureevent.html)。

```
QWidget.grabKeyboard (self)
```

抓起键盘输入。

这个小工具接收所有键盘事件，直到[releaseKeyboard](qwidget.html#releaseKeyboard)（）被调用，其他部件得不到键盘事件的。鼠标事件不会受到影响。使用[grabMouse](qwidget.html#grabMouse)（ ）如果你想抓住这一点。

不同之处在于它不接受任何键盘事件的焦点部件不受影响。[setFocus](qwidget.html#setFocus)（ ）将焦点移动像往常一样，但新的焦点部件后，才接收键盘事件[releaseKeyboard](qwidget.html#releaseKeyboard)（）被调用。

如果使用不同的部件被抓住当前的键盘输入，该widget的抢是首次发布。

**See also** [releaseKeyboard](qwidget.html#releaseKeyboard)（ ）[grabMouse](qwidget.html#grabMouse)（ ）[releaseMouse](qwidget.html#releaseMouse)（）和[focusWidget](qwidget.html#focusWidget)（ ） 。

```
QWidget.grabMouse (self)
```

抓起鼠标输入。

这个小工具接收所有的鼠标事件，直到[releaseMouse](qwidget.html#releaseMouse)（）被调用，其他部件没有得到鼠标事件的。键盘事件都不会受到影响。使用[grabKeyboard](qwidget.html#grabKeyboard)（ ）如果你想抓住这一点。

**Warning:**在鼠标抓取应用程序的bug往往锁定终端。使用这个功能非常谨慎，并考虑使用`-nograb`在调试命令行选项。

这几乎是从来没有必要使用Qt时抢鼠标，因为Qt的争夺并释放它理智。特别是， Qt的劫掠当按下鼠标按钮鼠标，并保持它，直到最后一个按钮被释放。

**Note:**唯一可见的小工具可以抓取鼠标输入。如果[isVisible](qwidget.html#visible-prop)（ ）返回False的控件，该控件不能调用grabMouse （ ） 。

**Note:** **(Mac OS X developers)**为_Cocoa_上一个widget调用grabMouse （ ）仅当鼠标是widget的框架内。为_Carbon_，它的工作部件的框架之外为好，像Windows和X11 。

**See also** [releaseMouse](qwidget.html#releaseMouse)（ ）[grabKeyboard](qwidget.html#grabKeyboard)（）和[releaseKeyboard](qwidget.html#releaseKeyboard)（ ） 。

```
QWidget.grabMouse (self, QCursor)
```

这个函数的重载[grabMouse](qwidget.html#grabMouse)（ ） 。

抓起鼠标输入并改变光标形状。

光标将呈现形状_cursor_（只要鼠标焦点被抓住） ，该部件将是唯一一个接收鼠标事件，直到[releaseMouse](qwidget.html#releaseMouse)（ ）被称为（ ） 。

**Warning:**抓住鼠标可能会锁定终端。

**Note:** **(Mac OS X developers)**见注中[QWidget.grabMouse](qwidget.html#grabMouse)（ ） 。

**See also** [releaseMouse](qwidget.html#releaseMouse)（ ）[grabKeyboard](qwidget.html#grabKeyboard)（ ）[releaseKeyboard](qwidget.html#releaseKeyboard)（）和[setCursor](qwidget.html#cursor-prop)（ ） 。

```
int QWidget.grabShortcut (self, QKeySequence key, Qt.ShortcutContext context = Qt.WindowShortcut)
```

增加了一个快捷方式到Qt的快捷键系统，手表对于给定的_key_序列中的给定_context_。如果_context_ is [Qt.ApplicationShortcut](qt.html#ShortcutContext-enum)，快捷适用于应用程序作为一个整体。否则，要么是本地的这个小工具，[Qt.WidgetShortcut](qt.html#ShortcutContext-enum)，或者窗口本身，[Qt.WindowShortcut](qt.html#ShortcutContext-enum)。

如果同一_key_序列已经抓住了几个小工具，当_key_序列发生[QEvent.Shortcut](qevent.html#Type-enum)事件被发送到所有的，它适用于非确定性的顺序小部件，而是用``暧昧''标志设置为True 。

**Warning:**你不应该通常需要使用此功能，而是创建[QAction](qaction.html)s的您需要的快捷键顺序（如果你也想等效的菜单选项和工具栏按钮） ，或创建[QShortcut](qshortcut.html)■如果您只需要按键顺序。两[QAction](qaction.html)和[QShortcut](qshortcut.html)处理所有的事件过滤的你，提供当用户触发键序列触发信号，所以更容易比这个低层次的功能使用。

**See also** [releaseShortcut](qwidget.html#releaseShortcut)（）和[setShortcutEnabled](qwidget.html#setShortcutEnabled)（ ） 。

```
QGraphicsEffect QWidget.graphicsEffect (self)
```

[

该graphicsEffect函数返回一个指向Widget的图形效果。

如果部件有没有图形效果，则返回0 。

此功能被引入Qt的4.6 。

](qgraphicseffect.html)

[**See also**](qgraphicseffect.html) [setGraphicsEffect](qwidget.html#setGraphicsEffect)（ ） 。

```
QGraphicsProxyWidget QWidget.graphicsProxyWidget (self)
```

[

返回代理部件在图形视图中相应的嵌入式部件，否则返回0 。

此功能被引入Qt的4.5 。

](qgraphicsproxywidget.html)

[**See also**](qgraphicsproxywidget.html) [QGraphicsProxyWidget.createProxyForChildWidget](qgraphicsproxywidget.html#createProxyForChildWidget)（）和[QGraphicsScene.addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
int QWidget.handle (self)
```

```
bool QWidget.hasFocus (self)
```

```
bool QWidget.hasMouseTracking (self)
```

```
int QWidget.height (self)
```

```
int QWidget.heightForWidth (self, int)
```

返回此插件的首选高度，给出的宽度_w_。

如果这个部件有一个布局，默认实现返回布局的首选高度。如果没有布局，默认实现返回-1 ，表明首选高度不依赖于宽度。

```
QWidget.hide (self)
```

这种方法也是一个Qt槽与C + +的签名`void hide()`。

隐藏部件。此功能相当于其setVisible （假） 。

**Note:**如果您正在使用[QDialog](qdialog.html)或者它的子类，并调用了[show](qwidget.html#show)（ ）函数这个函数后，对话框将显示在原来的位置。

**See also** [hideEvent](qwidget.html#hideEvent)（ ）[isHidden](qwidget.html#isHidden)（ ）[show](qwidget.html#show)（ ）[setVisible](qwidget.html#visible-prop)（ ）[isVisible](qwidget.html#visible-prop)（）和[close](qwidget.html#close)（ ） 。

```
QWidget.hideEvent (self, QHideEvent)
```

此事件处理程序可以重新实现在子类中接收部件隐藏事件。该事件被传递的_event_参数。

隐藏事件会立即发送到窗口小部件，他们已被隐藏之后。

注：控件接收自发的显示和隐藏事件时，其对应的状态是由窗口系统改变，如当用户最小化窗口，当窗口再次恢复自发show事件自发的隐藏事件。接收自发的隐藏事件之后，一个小部件仍然被认为是在这个意义上可见[isVisible](qwidget.html#visible-prop)（ ） 。

**See also** [visible](qwidget.html#visible-prop)，[event](qwidget.html#event)（）和[QHideEvent](qhideevent.html)。

```
QInputContext QWidget.inputContext (self)
```

[](qinputcontext.html)

[该函数返回](qinputcontext.html)[QInputContext](qinputcontext.html)这个小工具。默认情况下，输入上下文是从父窗口部件继承。对于toplevels它是从继承[QApplication](qapplication.html)。

您可以复盖此，并通过使用设置一个特殊的输入上下文返回此插件的[setInputContext](qwidget.html#setInputContext)（）方法。

**See also** [setInputContext](qwidget.html#setInputContext)（ ） 。

```
QWidget.inputMethodEvent (self, QInputMethodEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类来接收输入法组成的事件。这个处理程序被调用时，输入法的状态发生改变。

请注意，创建自定义的文本编辑窗口部件时，该[Qt.WA_InputMethodEnabled](qt.html#WidgetAttribute-enum)窗口属性必须显式设置（使用[setAttribute](qwidget.html#setAttribute)（ ）函数） ，以便接收输入方法事件。

默认实现调用事件 - \u003e忽略（），它拒绝输入法事件。请参阅[QInputMethodEvent](qinputmethodevent.html)文档了解更多信息。

**See also** [event](qwidget.html#event)（）和[QInputMethodEvent](qinputmethodevent.html)。

```
Qt.InputMethodHints QWidget.inputMethodHints (self)
```

[

```
QVariant QWidget.inputMethodQuery (self, Qt.InputMethodQuery)
```

此方法仅适用于输入窗口小部件。它是由输入法查询一组小部件要能支持复杂的输入法操作为周围的文字和reconversions支持的特性。

_query_指定哪些属性进行查询。

](index.htm)

[**See also**](index.htm) [inputMethodEvent](qwidget.html#inputMethodEvent)（ ）[QInputMethodEvent](qinputmethodevent.html)，[QInputContext](qinputcontext.html)和[inputMethodHints](qwidget.html#inputMethodHints-prop)。

```
QWidget.insertAction (self, QAction before, QAction action)
```

插入动作_action_以行动，在行动之前，这个小工具的列表_before_。其附加的行动，如果_before_是0或_before_是不是这个小工具的有效行动。

A [QWidget](qwidget.html)应该只有每个动作之一。

**See also** [removeAction](qwidget.html#removeAction)（ ）[addAction](qwidget.html#addAction)（ ）[QMenu](qmenu.html)，[contextMenuPolicy](qwidget.html#contextMenuPolicy-prop)和[actions](qwidget.html#actions)（ ） 。

```
QWidget.insertActions (self, QAction before, list-of-QAction actions)
```

插入动作_actions_以行动，在行动之前，这个小工具的列表_before_。其附加的行动，如果_before_是0或_before_是不是这个小工具的有效行动。

A [QWidget](qwidget.html)最多可以有各一个动作。

**See also** [removeAction](qwidget.html#removeAction)（ ）[QMenu](qmenu.html)，[insertAction](qwidget.html#insertAction)（）和[contextMenuPolicy](qwidget.html#contextMenuPolicy-prop)。

```
bool QWidget.isActiveWindow (self)
```

```
bool QWidget.isAncestorOf (self, QWidget child)
```

返回给定True，如果这个小工具是父母（或祖父母等，以任何级别） ，_child_，和两个小部件是相同的窗口内，否则返回False 。

```
bool QWidget.isEnabled (self)
```

```
bool QWidget.isEnabledTo (self, QWidget)
```

返回True如果这个widget会变成如果启用_ancestor_被启用，否则返回False 。

这种情况下，如果既不是小部件本身也不是每一个家长最多，但不包括_ancestor_已被明确禁用。

isEnabledTo （0 ）等效于[isEnabled](qwidget.html#enabled-prop)（ ） 。

**See also** [setEnabled](qwidget.html#enabled-prop)（）和[enabled](qwidget.html#enabled-prop)。

```
bool QWidget.isEnabledToTLW (self)
```

```
bool QWidget.isFullScreen (self)
```

```
bool QWidget.isHidden (self)
```

返回True如果控件被隐藏，否则返回False 。

一个隐藏的小工具只会成为可见的，当[show](qwidget.html#show)（）被调用就可以了。它不会在父显示时会自动显示。

要检查的知名度，使用！[isVisible](qwidget.html#visible-prop)（）代替（注意感叹号） 。

isHidden （ ）暗示！[isVisible](qwidget.html#visible-prop)（ ） ，但一个部件可以是不可见的，而不是藏在同一时间。这是一个小部件是小部件的不可见孩子的情况。

Widget是隐藏的，如果：

*   they were created as independent windows,
*   they were created as children of visible widgets,
*   [hide](qwidget.html#hide)() or setVisible(false) was called.

```
bool QWidget.isLeftToRight (self)
```

```
bool QWidget.isMaximized (self)
```

```
bool QWidget.isMinimized (self)
```

```
bool QWidget.isModal (self)
```

```
bool QWidget.isRightToLeft (self)
```

```
bool QWidget.isTopLevel (self)
```

```
bool QWidget.isVisible (self)
```

```
bool QWidget.isVisibleTo (self, QWidget)
```

返回True如果这个widget会变成可见的，如果_ancestor_示，否则返回False 。

真实的情况发生时，如果既不是小部件本身也没有任何父母到不包括_ancestor_已经明确地隐藏。

此功能仍然会返回True，如果部件是由屏幕上的其他窗口遮挡，但可能是身体上可见，如果它或它们移动。

isVisibleTo （0）是相同的[isVisible](qwidget.html#visible-prop)（ ） 。

**See also** [show](qwidget.html#show)（ ）[hide](qwidget.html#hide)（）和[isVisible](qwidget.html#visible-prop)（ ） 。

```
bool QWidget.isWindow (self)
```

返回True如果该控件是一个独立的窗口，否则返回False 。

窗口是一个小部件，目前还没有任何其他部件在视觉上的孩子，通常有一个框架和一[window title](qwidget.html#windowTitle-prop)。

一个窗口可以有一个[parent widget](qwidget.html#parentWidget)。然后，它会被分组与其父当父对象被删除删除，当父最小化等，如果由窗口管理器支持，它也将有一个共同的任务栏条目，其父最小化。

[QDialog](qdialog.html)和[QMainWindow](qmainwindow.html)Widget是默认的窗口，即使在构造函数中指定一个父部件。由指定的这个行为[Qt.Window](qt.html#WindowType-enum)标志。

**See also** [window](qwidget.html#window)（ ）[isModal](qwidget.html#modal-prop)（）和[parentWidget](qwidget.html#parentWidget)（ ） 。

```
bool QWidget.isWindowModified (self)
```

```
QWidget QWidget.keyboardGrabber ()
```

[

返回当前抓住了键盘输入的窗口小部件。

如果在这个应用程序中没有部件被抓住当前的键盘，则返回0 。

](qwidget.html)

[**See also**](qwidget.html) [grabMouse](qwidget.html#grabMouse)（）和[mouseGrabber](qwidget.html#mouseGrabber)（ ） 。

```
QWidget.keyPressEvent (self, QKeyEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类来接收按键事件的小部件。

一个widget必须调用[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）最初接受焦点，并且有重点，以接收按键事件。

如果你重新实现这个处理程序，您调用基类的实现，如果你不经的关键作用是非常重要的。

默认实现关闭弹出窗口部件，如果用户按下Esc键。否则，事件被忽略，从而使部件的家长可以解释它。

需要注意的是[QKeyEvent](qkeyevent.html)开始isAccepted （ ） == True，所以你不需要调用[QKeyEvent.accept](qevent.html#accept)（ ） - 只是不调用基类的实现，如果你在关键行动。

**See also** [keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ）[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）[focusInEvent](qwidget.html#focusInEvent)（ ）[focusOutEvent](qwidget.html#focusOutEvent)（ ）[event](qwidget.html#event)（ ）[QKeyEvent](qkeyevent.html)和[Tetrix Example](index.htm)。

```
QWidget.keyReleaseEvent (self, QKeyEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收键释放事件的小部件。

一个widget必须的[accept focus](qwidget.html#focusPolicy-prop)最初和[have focus](qwidget.html#focus-prop)为了获得一个键释放事件。

如果你重新实现这个处理程序，您调用基类的实现，如果你不经的关键作用是非常重要的。

默认实现忽略该事件，从而使部件的家长可以解释它。

需要注意的是[QKeyEvent](qkeyevent.html)开始isAccepted （ ） == True，所以你不需要调用[QKeyEvent.accept](qevent.html#accept)（ ） - 只是不调用基类的实现，如果你在关键行动。

**See also** [keyPressEvent](qwidget.html#keyPressEvent)（ ）[QKeyEvent.ignore](qevent.html#ignore)（ ）[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）[focusInEvent](qwidget.html#focusInEvent)（ ）[focusOutEvent](qwidget.html#focusOutEvent)（ ）[event](qwidget.html#event)（）和[QKeyEvent](qkeyevent.html)。

```
QWidget.languageChange (self)
```

```
QLayout QWidget.layout (self)
```

[

返回安装这个小工具，或者0 ，如果没有安装布局管理器的布局管理器。

布局管理器设置的部件的儿童已被添加到布局的几何形状。

](qlayout.html)

[**See also**](qlayout.html) [setLayout](qwidget.html#setLayout)（ ）[sizePolicy](qwidget.html#sizePolicy-prop)（）和[Layout Management](index.htm)。

```
Qt.LayoutDirection QWidget.layoutDirection (self)
```

[

```
QWidget.leaveEvent (self, QEvent)
```

此事件处理程序可以重新实现在子类中以接收传递在widget假期活动_event_参数。

休假事件发送到窗口小部件当鼠标光标离开窗口小部件。

](qt.html#LayoutDirection-enum)

[**See also**](qt.html#LayoutDirection-enum) [enterEvent](qwidget.html#enterEvent)（ ）[mouseMoveEvent](qwidget.html#mouseMoveEvent)（）和[event](qwidget.html#event)（ ） 。

```
QLocale QWidget.locale (self)
```

[

```
QWidget.lower (self)
```

这种方法也是一个Qt槽与C + +的签名`void lower()`。

降低小部件的父控件的堆栈的底部。

在此之后调用部件将在视觉上落后（因此被掩盖）任何重叠的兄弟窗口小部件。

](qlocale.html)

[**See also**](qlocale.html) [raise_](qwidget.html#raise)（）和[stackUnder](qwidget.html#stackUnder)（ ） 。

```
QPoint QWidget.mapFrom (self, QWidget, QPoint)
```

[

翻译小工具坐标_pos_从坐标系_parent_这个小部件的坐标系。该_parent_不能为0 ，且必须调用控件的父。

](qpoint.html)

[**See also**](qpoint.html) [mapTo](qwidget.html#mapTo)（ ）[mapFromParent](qwidget.html#mapFromParent)（ ）[mapFromGlobal](qwidget.html#mapFromGlobal)（）和[underMouse](qwidget.html#underMouse)（ ） 。

```
QPoint QWidget.mapFromGlobal (self, QPoint)
```

[

将全局屏幕坐标_pos_到窗口小部件坐标。

](qpoint.html)

[**See also**](qpoint.html) [mapToGlobal](qwidget.html#mapToGlobal)（ ）[mapFrom](qwidget.html#mapFrom)（）和[mapFromParent](qwidget.html#mapFromParent)（ ） 。

```
QPoint QWidget.mapFromParent (self, QPoint)
```

[

转换的父控件的坐标_pos_到窗口小部件坐标。

](qpoint.html)

[同](qpoint.html)[mapFromGlobal](qwidget.html#mapFromGlobal)（ ）如果该控件没有父。

**See also** [mapToParent](qwidget.html#mapToParent)（ ）[mapFrom](qwidget.html#mapFrom)（ ）[mapFromGlobal](qwidget.html#mapFromGlobal)（）和[underMouse](qwidget.html#underMouse)（ ） 。

```
QPoint QWidget.mapTo (self, QWidget, QPoint)
```

[

翻译小工具坐标_pos_到的坐标系_parent_。该_parent_不能为0 ，且必须调用控件的父。

](qpoint.html)

[**See also**](qpoint.html) [mapFrom](qwidget.html#mapFrom)（ ）[mapToParent](qwidget.html#mapToParent)（ ）[mapToGlobal](qwidget.html#mapToGlobal)（）和[underMouse](qwidget.html#underMouse)（ ） 。

```
QPoint QWidget.mapToGlobal (self, QPoint)
```

[

翻译小工具坐标_pos_全球屏幕坐标。例如，`mapToGlobal(QPoint(0,0))`将给小窗口的左上角的像素的全局坐标。

](qpoint.html)

[**See also**](qpoint.html) [mapFromGlobal](qwidget.html#mapFromGlobal)（ ）[mapTo](qwidget.html#mapTo)（）和[mapToParent](qwidget.html#mapToParent)（ ） 。

```
QPoint QWidget.mapToParent (self, QPoint)
```

[

翻译小工具坐标_pos_在父窗口部件的坐标。

](qpoint.html)

[同](qpoint.html)[mapToGlobal](qwidget.html#mapToGlobal)（ ）如果该控件没有父。

**See also** [mapFromParent](qwidget.html#mapFromParent)（ ）[mapTo](qwidget.html#mapTo)（ ）[mapToGlobal](qwidget.html#mapToGlobal)（）和[underMouse](qwidget.html#underMouse)（ ） 。

```
QRegion QWidget.mask (self)
```

[

返回上一个窗口部件当前设置的掩码。如果没有掩码被设置的返回值将是一个空白区域。

](qregion.html)

[**See also**](qregion.html) [setMask](qwidget.html#setMask)（ ）[clearMask](qwidget.html#clearMask)（ ）[QRegion.isEmpty](qregion.html#isEmpty)（）和[Shaped Clock Example](index.htm)。

```
int QWidget.maximumHeight (self)
```

```
QSize QWidget.maximumSize (self)
```

[

```
int QWidget.maximumWidth (self)
```

```
int QWidget.metric (self, QPaintDevice.PaintDeviceMetric)
```

](qsize.html)

[从重新实现](qsize.html)[QPaintDevice.metric](qpaintdevice.html#metric)（ ） 。

内部实现虚拟的[QPaintDevice.metric](qpaintdevice.html#metric)（）函数。

_m_是获得指标。

```
int QWidget.minimumHeight (self)
```

```
QSize QWidget.minimumSize (self)
```

[](qsize.html)

```
QSize QWidget.minimumSizeHint (self)
```

[

```
int QWidget.minimumWidth (self)
```

```
QWidget.mouseDoubleClickEvent (self, QMouseEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收鼠标双击事件的小部件。

默认实现会产生一个正常的鼠标按下事件。

**Note:**窗口小部件也将获得鼠标按下和鼠标释放事件，除了双击事件。它是由开发人员，以确保应用程序正确地解释这些事件。

](qsize.html)

[**See also**](qsize.html) [mousePressEvent](qwidget.html#mousePressEvent)（ ）[mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ）[mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ）[event](qwidget.html#event)（）和[QMouseEvent](qmouseevent.html)。

```
QWidget QWidget.mouseGrabber ()
```

[

返回当前抓取鼠标输入的窗口小部件。

如果在这个应用程序中没有部件被抓住当前鼠标，则返回0 。

](qwidget.html)

[**See also**](qwidget.html) [grabMouse](qwidget.html#grabMouse)（）和[keyboardGrabber](qwidget.html#keyboardGrabber)（ ） 。

```
QWidget.mouseMoveEvent (self, QMouseEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收鼠标移动事件的小部件。

如果鼠标跟踪被关闭，如果按下鼠标按钮，当鼠标被移动，鼠标移动事件才会发生。如果鼠标跟踪处于开机状态，即使没有按下鼠标按钮会出现鼠标移动事件。

[QMouseEvent.pos](qmouseevent.html#pos)（）报告鼠标光标的位置，相对于这个小工具。对于按下和释放事件，该位置通常是一样的，最后鼠标移动事件的立场，但也可能是不同的，如果用户的手抖动。这是底层窗口系统，而不是Qt的一个特点。

如果你想立即显示一个工具提示，当鼠标移动（例如，获取鼠标坐标与[QMouseEvent.pos](qmouseevent.html#pos)（ ） ，并显示它们作为一个工具提示） ，您必须首先启用鼠标跟踪如上所述。然后，以保证工具提示会立即更新，您必须调用[QToolTip.showText](qtooltip.html#showText)（）而不是[setToolTip](qwidget.html#toolTip-prop)（ ）在实现的mouseMoveEvent的（ ） 。

**See also** [setMouseTracking](qwidget.html#mouseTracking-prop)（ ）[mousePressEvent](qwidget.html#mousePressEvent)（ ）[mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ）[mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ）[event](qwidget.html#event)（ ）[QMouseEvent](qmouseevent.html)和[Scribble Example](index.htm)。

```
QWidget.mousePressEvent (self, QMouseEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收鼠标按下事件的小部件。

如果您在mousePressEvent创建新的部件（ ）的[mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ）可能不会结束，你期望的，这取决于底层窗口系统（或X11窗口管理器）上，小部件的位置和可能更多。

默认实现实现弹出小窗口的关闭，当您单击窗外。对于其他构件类型它什么都不做。

**See also** [mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ）[mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ）[mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ）[event](qwidget.html#event)（ ）[QMouseEvent](qmouseevent.html)和[Scribble Example](index.htm)。

```
QWidget.mouseReleaseEvent (self, QMouseEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收鼠标释放事件的小部件。

**See also** [mousePressEvent](qwidget.html#mousePressEvent)（ ）[mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ）[mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ）[event](qwidget.html#event)（ ）[QMouseEvent](qmouseevent.html)和[Scribble Example](index.htm)。

```
QWidget.move (self, QPoint)
```

```
QWidget.move (self, int ax, int ay)
```

```
QWidget.moveEvent (self, QMoveEvent)
```

此事件处理程序可以重新实现在子类中以接收传递在widget移动事件_event_参数。当控件接收这个事件，这已经是在新的位置。

旧的立场是通过访问[QMoveEvent.oldPos](qmoveevent.html#oldPos)（ ） 。

**See also** [resizeEvent](qwidget.html#resizeEvent)（ ）[event](qwidget.html#event)（ ）[move](qwidget.html#pos-prop)（）和[QMoveEvent](qmoveevent.html)。

```
QWidget QWidget.nativeParentWidget (self)
```

[

返回原生母体此插件，即下一个祖先插件，其具有系统标识符，或者0 ，如果它不具有任何原生母体。

此功能被引入Qt的4.4 。

](qwidget.html)

[**See also**](qwidget.html) [effectiveWinId](qwidget.html#effectiveWinId)（ ） 。

```
QWidget QWidget.nextInFocusChain (self)
```

[

返回这个窗口部件的焦点链中的下一个控件。

](qwidget.html)

[**See also**](qwidget.html) [previousInFocusChain](qwidget.html#previousInFocusChain)（ ） 。

```
QRect QWidget.normalGeometry (self)
```

[

```
QWidget.overrideWindowFlags (self, Qt.WindowFlags type)
```

设置窗口标志的小部件_flags_，_without_告诉窗口系统。

**Warning:**不要调用这个函数，除非你真的知道自己在做什么。

](qrect.html)

[**See also**](qrect.html) [setWindowFlags](qwidget.html#windowFlags-prop)（ ） 。

```
QWidget.overrideWindowState (self, Qt.WindowStates state)
```

```
QPaintEngine QWidget.paintEngine (self)
```

[](qpaintengine.html)

[从重新实现](qpaintengine.html)[QPaintDevice.paintEngine](qpaintdevice.html#paintEngine)（ ） 。

返回widget的绘图引擎。

注意，这个函数不应该显式调用的用户，因为它意味着只有重新实现的目的。该函数调用Qt的内部，并默认实现可能并不总是返回一个有效的指针。

```
QWidget.paintEvent (self, QPaintEvent)
```

此事件处理程序可以在子类来接收传入paint事件重新实现_event_。

Paint事件是一个请求重绘所有的窗口小部件的全部或部分。它可以发生于下列原因之一：

*   [repaint](qwidget.html#repaint)() or [update](qwidget.html#update)() was invoked,
*   the widget was obscured and has now been uncovered, or
*   many other reasons.

许多部件可以简单地重新绘制自己的整个表面当记者问到，但有些慢的部件需要通过绘画只有被请求的区域进行优化：[QPaintEvent.region](qpaintevent.html#region)（ ） 。这个速度优化不会改变结果，如绘画是在事件处理期间剪切到该区域。[QListView](qlistview.html)和[QTableView](qtableview.html)为此，例如。

Qt还试图通过合并多个paint事件到一个加快绘画。何时[update](qwidget.html#update)（）被调用几次或者窗口系统发送几个油漆事件， Qt的合并这些事件转换为一个事件有一个较大的区域（见[QRegion.united](qregion.html#united)（））。该[repaint](qwidget.html#repaint)（ ）函数不允许这样的优化，所以我们建议您使用[update](qwidget.html#update)（ ）只要有可能。

当绘画事件发生时，更新区域被正常删除，所以要绘制的控件的背景。

背景可以使用设置[setBackgroundRole](qwidget.html#setBackgroundRole)（）和[setPalette](qwidget.html#palette-prop)（ ） 。

由于Qt的4.0 ，[QWidget](qwidget.html)自动双缓冲的画，所以没有必要写双缓冲的代码中的paintEvent （）来避免闪烁。

**Note for the X11 platform**：可以通过调用切换全局双缓冲`qt_x11_set_global_double_buffer()`。例如，

```
 ...
 extern void qt_x11_set_global_double_buffer(bool);
 qt_x11_set_global_double_buffer(false);
 ...

```

**Note:**一般来说，你应该避免调用[update](qwidget.html#update)（）或[repaint](qwidget.html#repaint)（ ）**inside**一的paintEvent （ ） 。例如，调用[update](qwidget.html#update)（）或[repaint](qwidget.html#repaint)（ ）上的paintEvent里面的孩子（ ）产生不确定的行为，孩子可能会或可能不会得到一个绘画事件。

**Warning:**如果您正在使用一个自定义的绘图引擎没有Qt的备份存储，[Qt.WA_PaintOnScreen](qt.html#WidgetAttribute-enum)必须设置。否则，[QWidget.paintEngine](qwidget.html#paintEngine)（ ）将永远不会被调用;的备份存储将被使用。

**See also** [event](qwidget.html#event)（ ）[repaint](qwidget.html#repaint)（ ）[update](qwidget.html#update)（ ）[QPainter](qpainter.html)，[QPixmap](qpixmap.html)，[QPaintEvent](qpaintevent.html)和[Analog Clock Example](index.htm)。

```
QPalette QWidget.palette (self)
```

[

```
QWidget.paletteChange (self, QPalette)
```

](qpalette.html)

```
QWidget QWidget.parentWidget (self)
```

[

返回这个窗口部件的父，或者0，如果它不具有任何父控件。

](qwidget.html)

```
QPoint QWidget.pos (self)
```

[](qpoint.html)

```
QWidget QWidget.previousInFocusChain (self)
```

[

该previousInFocusChain函数返回前一个窗口小部件在这个widget的焦点链。

此功能被引入Qt的4.6 。

](qwidget.html)

[**See also**](qwidget.html) [nextInFocusChain](qwidget.html#nextInFocusChain)（ ） 。

```
QWidget.raise_ (self)
```

这种方法也是一个Qt槽与C + +的签名`void raise()`。

引发此控件的父控件的堆栈的顶部。

在此之后调用部件将在视觉上的任何重叠的兄弟姐妹部件前面。

**Note:**当使用[activateWindow](qwidget.html#activateWindow)（ ） ，你可以调用这个函数来确保窗口堆放在上面。

**See also** [lower](qwidget.html#lower)（）和[stackUnder](qwidget.html#stackUnder)（ ） 。

```
QRect QWidget.rect (self)
```

[

```
QWidget.releaseKeyboard (self)
```

释放键盘捕获。

](qrect.html)

[**See also**](qrect.html) [grabKeyboard](qwidget.html#grabKeyboard)（ ）[grabMouse](qwidget.html#grabMouse)（）和[releaseMouse](qwidget.html#releaseMouse)（ ） 。

```
QWidget.releaseMouse (self)
```

释放鼠标抢。

**See also** [grabMouse](qwidget.html#grabMouse)（ ）[grabKeyboard](qwidget.html#grabKeyboard)（）和[releaseKeyboard](qwidget.html#releaseKeyboard)（ ） 。

```
QWidget.releaseShortcut (self, int id)
```

删除快捷方式与给定_id_从Qt的快捷键系统。该部件将不再接收[QEvent.Shortcut](qevent.html#Type-enum)事件的快捷方式的按键顺序（除非它使用相同的密钥序列的其他快捷方式） 。

**Warning:**你不应该通常需要使用此功能，因为Qt的快捷键系统自动删除快捷方式时，他们的父窗口部件被销毁。最好是使用[QAction](qaction.html) or [QShortcut](qshortcut.html)处理快捷方式，因为它们更容易比这低级别的功能来使用。还请注意，这是一个昂贵的操作。

**See also** [grabShortcut](qwidget.html#grabShortcut)（）和[setShortcutEnabled](qwidget.html#setShortcutEnabled)（ ） 。

```
QWidget.removeAction (self, QAction action)
```

删除动作_action_从操作这个小工具的列表。

**See also** [insertAction](qwidget.html#insertAction)（ ）[actions](qwidget.html#actions)（）和[insertAction](qwidget.html#insertAction)（ ） 。

```
QWidget.render (self, QPaintDevice target, QPoint targetOffset = QPoint(), QRegion sourceRegion = QRegion(), RenderFlags flags = QWidget.DrawWindowBackground|QWidget.DrawChildren)
```

呈现_sourceRegion_这个小工具到的_target_ using _renderFlags_来确定如何呈现。在开始绘制_targetOffset_在_target_。例如：

```
 [QPixmap](qpixmap.html) pixmap(widget->size());
 widget->render(&pixmap);

```

If _sourceRegion_是一个空区，这个功能将使用[QWidget.rect](qwidget.html#rect-prop)（）作为该区域，即整个部件。

确保你调用[QPainter.end](qpainter.html#end)（ ）为_target_器件的有源画家（如果有的话）之前渲染。例如：

```
 [QPainter](qpainter.html) painter(this);
 ...
 painter.end();
 myWidget->render(this);

```

**Note:**要获得一个OpenGL窗口小部件，使用内容[QGLWidget.grabFrameBuffer](qglwidget.html#grabFrameBuffer)（）或[QGLWidget.renderPixmap](qglwidget.html#renderPixmap)（ ）来代替。

此功能被引入Qt的4.3 。

```
QWidget.render (self, QPainter painter, QPoint targetOffset = QPoint(), QRegion sourceRegion = QRegion(), RenderFlags flags = QWidget.DrawWindowBackground|QWidget.DrawChildren)
```

这是一个重载函数。

呈现小部件进入_painter_的[QPainter.device](qpainter.html#device)（ ） 。

变换和施加到设置_painter_渲染时将被使用。

**Note:**该_painter_必须是活动的。在Mac OS X的部件将被渲染成[QPixmap](qpixmap.html)然后由拉伸_painter_。

**See also** [QPainter.device](qpainter.html#device)（ ） 。

```
QWidget.repaint (self)
```

这种方法也是一个Qt槽与C + +的签名`void repaint()`。

直接通过调用重画窗口小部件[paintEvent](qwidget.html#paintEvent)（）立即，除非更新被禁用或部件是隐藏的。

我们建议只使用重绘（ ） ，如果你的动画时需要立即重绘，例如。在几乎所有情况下，[update](qwidget.html#update)（ ）是更好的，因为它允许的Qt来优化速度和减少闪烁。

**Warning:**如果您在其中本身可以从调用的函数调用repaint （ ）[paintEvent](qwidget.html#paintEvent)（ ） ，你可能会得到无限递归。该[update](qwidget.html#update)（ ）函数永远不会导致递归。

**See also** [update](qwidget.html#update)（ ）[paintEvent](qwidget.html#paintEvent)（）和[setUpdatesEnabled](qwidget.html#updatesEnabled-prop)（ ） 。

```
QWidget.repaint (self, int x, int y, int w, int h)
```

```
QWidget.repaint (self, QRect)
```

```
QWidget.repaint (self, QRegion)
```

```
QWidget.resetInputContext (self)
```

```
QWidget.resize (self, QSize)
```

```
QWidget.resize (self, int w, int h)
```

```
QWidget.resizeEvent (self, QResizeEvent)
```

此事件处理程序可以重新实现在子类中接收部件调整它们传递的事件_event_参数。当resizeEvent （）被调用时，插件已经拥有新的几何结构。旧的大小是通过访问[QResizeEvent.oldSize](qresizeevent.html#oldSize)（ ） 。

该部件将被删除，并处理resize事件后立即收到一个绘画事件。没有图纸需要的话（或者应该是）这个处理程序中完成的。

**See also** [moveEvent](qwidget.html#moveEvent)（ ）[event](qwidget.html#event)（ ）[resize](qwidget.html#size-prop)（ ）[QResizeEvent](qresizeevent.html)，[paintEvent](qwidget.html#paintEvent)（）和[Scribble Example](index.htm)。

```
bool QWidget.restoreGeometry (self, QByteArray geometry)
```

恢复存储在字节数组中的几何和国家顶级部件_geometry_。成功时返回TRUE ，否则返回False 。

如果还原的几何形状是关闭屏幕，它将被修改为可用的屏幕几何里面。

要使用恢复保存几何[QSettings](qsettings.html)，你可以使用如下代码：

```
 [QSettings](qsettings.html) settings("MyCompany", "MyApp");
 myWidget->restoreGeometry(settings.value("myWidget/geometry").toByteArray());

```

请参阅[Window Geometry](index.htm#window-geometry)文档与窗口几何问题的概述。

使用[QMainWindow.restoreState](qmainwindow.html#restoreState)（ ）来恢复几何和工具栏和停靠小部件的状态。

这个函数中引入了Qt 4.2中。

**See also** [saveGeometry](qwidget.html#saveGeometry)（ ）[QSettings](qsettings.html)，[QMainWindow.saveState](qmainwindow.html#saveState)（）和[QMainWindow.restoreState](qmainwindow.html#restoreState)（ ） 。

```
QByteArray QWidget.saveGeometry (self)
```

[

保存当前的几何形状和国家顶级部件。

要保存窗口关闭时的几何形状，可以实现这样一个close事件：

](qbytearray.html)

```
 void MyWidget.closeEvent([QCloseEvent](qcloseevent.html) *event)
 {
     [QSettings](qsettings.html) settings("MyCompany", "MyApp");
     settings.setValue("geometry", saveGeometry());
     [QWidget](qwidget.html).closeEvent(event);
 }

```

请参阅[Window Geometry](index.htm#window-geometry)文档与窗口几何问题的概述。

使用[QMainWindow.saveState](qmainwindow.html#saveState)（ ）保存的几何形状和工具栏和停靠小部件的状态。

这个函数中引入了Qt 4.2中。

**See also** [restoreGeometry](qwidget.html#restoreGeometry)（ ）[QMainWindow.saveState](qmainwindow.html#saveState)（）和[QMainWindow.restoreState](qmainwindow.html#restoreState)（ ） 。

```
QWidget.scroll (self, int dx, int dy)
```

滚动窗口小部件，包括其子_dx_像素向右和_dy_向下。两_dx_和_dy_可能是负的。

滚动后，小部件会收到paint事件为需要重新绘制的区域。如果希望组件的Qt知道是不透明的，这仅仅是新暴露的部位。例如，如果一个不透明的插件被滚动8个像素的左侧，只有一个8个像素的右边缘的需要更新的宽条纹。

由于小部件默认情况下传播他们的父母的内容，您需要设置[autoFillBackground](qwidget.html#autoFillBackground-prop)财产，或使用[setAttribute](qwidget.html#setAttribute)（ ）来设置[Qt.WA_OpaquePaintEvent](qt.html#WidgetAttribute-enum)属性，以使一个部件不透明。

对于使用内容传播窗口小部件，涡旋将导致整个滚动区域的更新。

**See also** [Transparency and Double Buffering](qwidget.html#transparency-and-double-buffering)。

```
QWidget.scroll (self, int dx, int dy, QRect)
```

这是一个重载函数。

只有这个版本春联_r_并且不移动widget的孩子。

If _r_为空或无效，其结果是不确定的。

**See also** [QScrollArea](qscrollarea.html).

```
QWidget.setAcceptDrops (self, bool on)
```

```
QWidget.setAccessibleDescription (self, QString description)
```

```
QWidget.setAccessibleName (self, QString name)
```

```
QWidget.setAttribute (self, Qt.WidgetAttribute attribute, bool on = True)
```

设置属性_attribute_这个小工具，如果_on_为True，否则清除该属性。

**See also** [testAttribute](qwidget.html#testAttribute)（ ） 。

```
QWidget.setAutoFillBackground (self, bool enabled)
```

```
QWidget.setBackgroundRole (self, QPalette.ColorRole)
```

设置构件的背景的角色_role_。

背景角色定义的画笔从部件的[palette](qwidget.html#palette-prop)用于呈现的背景。

If _role_ is [QPalette.NoRole](qpalette.html#ColorRole-enum)，那么小部件继承了其父的背景作用。

需要注意的是款式可以自由从调色板中选择任何颜色。您可以修改调色板或设置一个样式表，如果你没有达到你想要的结果与setBackgroundRole （ ） 。

**See also** [backgroundRole](qwidget.html#backgroundRole)（）和[foregroundRole](qwidget.html#foregroundRole)（ ） 。

```
QWidget.setBaseSize (self, int basew, int baseh)
```

```
QWidget.setBaseSize (self, QSize s)
```

```
QWidget.setContentsMargins (self, int left, int top, int right, int bottom)
```

周围设置widget的内容的利润有大小_left_，_top_，_right_和_bottom_。边缘所使用的布局系统，并且可以由子类来指定的区域绘制（如不包括帧） 。

更改页边距将触发[resizeEvent](qwidget.html#resizeEvent)（ ） 。

**See also** [contentsMargins](qwidget.html#contentsMargins)（ ）[contentsRect](qwidget.html#contentsRect)（）和[getContentsMargins](qwidget.html#getContentsMargins)（ ） 。

```
QWidget.setContentsMargins (self, QMargins margins)
```

这是一个重载函数。

该setContentsMargins函数周围设置控件的内容的利润。

设置围绕插件的内容边距以具有所确定的大小的_margins_。边缘所使用的布局系统，并且可以由子类来指定的区域绘制（如不包括帧） 。

更改页边距将触发[resizeEvent](qwidget.html#resizeEvent)（ ） 。

此功能被引入Qt的4.6 。

**See also** [contentsRect](qwidget.html#contentsRect)（）和[getContentsMargins](qwidget.html#getContentsMargins)（ ） 。

```
QWidget.setContextMenuPolicy (self, Qt.ContextMenuPolicy policy)
```

```
QWidget.setCursor (self, QCursor)
```

```
QWidget.setDisabled (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setDisabled(bool)`。

禁用控件输入事件，如果_disable_为True，否则使输入事件。

请参阅[enabled](qwidget.html#enabled-prop)文档了解更多信息。

**See also** [isEnabledTo](qwidget.html#isEnabledTo)（ ）[QKeyEvent](qkeyevent.html)，[QMouseEvent](qmouseevent.html)和[changeEvent](qwidget.html#changeEvent)（ ） 。

```
QWidget.setEnabled (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setEnabled(bool)`。

```
QWidget.setFixedHeight (self, int h)
```

设定最小和小部件的最大高度，以_h_在不改变宽度。提供了方便。

**See also** [sizeHint](qwidget.html#sizeHint-prop)（ ）[minimumSize](qwidget.html#minimumSize-prop)（ ）[maximumSize](qwidget.html#maximumSize-prop)（）和[setFixedSize](qwidget.html#setFixedSize)（ ） 。

```
QWidget.setFixedSize (self, QSize)
```

设定最小和小部件的最大尺寸，以_s_，从而防止其不断增长或收缩。

这将复盖通过设置默认的尺寸限制[QLayout](qlayout.html)。

消除障碍，将大小设置为[QWIDGETSIZE_MAX](qwidget.html#QWIDGETSIZE_MAX)。

或者，如果您想要的小工具有一个固定的大小根据其内容，您可以拨打QLayout.setSizeConstraint （[QLayout.SetFixedSize](qlayout.html#SizeConstraint-enum)） ;

**See also** [maximumSize](qwidget.html#maximumSize-prop)和[minimumSize](qwidget.html#minimumSize-prop)。

```
QWidget.setFixedSize (self, int w, int h)
```

这是一个重载函数。

设置插件的宽度，以_w_和高度，以_h_。

```
QWidget.setFixedWidth (self, int w)
```

设定最小和小部件的最大宽度，以_w_在不改变高度。提供了方便。

**See also** [sizeHint](qwidget.html#sizeHint-prop)（ ）[minimumSize](qwidget.html#minimumSize-prop)（ ）[maximumSize](qwidget.html#maximumSize-prop)（）和[setFixedSize](qwidget.html#setFixedSize)（ ） 。

```
QWidget.setFocus (self)
```

这种方法也是一个Qt槽与C + +的签名`void setFocus()`。

使键盘输入焦点将这个小工具（或它的焦点代理） ，如果这个widget或其父母之一是[active window](qwidget.html#isActiveWindow-prop)。该_reason_参数将被传递到这个函数发送的任何焦点事件，它是用来给的是什么引起的小工具来获得焦点的解释。如果窗口不活跃，该部件将被给予重点当窗口被激活。

首先，集中了事件发送到焦点窗口小部件（如果有的话）来告诉它，它是即将失去焦点。然后在事件的焦点被送到这个小工具来告诉它，它刚刚收到的焦点。 （如果在和焦点集中出部件都是一样的，没有任何反应。 ）

**Note:**在嵌入式平台上，的setFocus （ ）不会导致由输入法打开输入面板。如果你想做到这一点，你必须发送一个[QEvent.RequestSoftwareInputPanel](qevent.html#Type-enum)事件的小部件自己。

的setFocus （ ）将焦点移到一个小部件，无论它的重点政策，但不会清除任何键盘捕获（见[grabKeyboard](qwidget.html#grabKeyboard)（））。

请注意，如果该控件是隐藏的，它不会接受焦点，直到它被显示。

**Warning:**如果您在其中本身可以从调用的函数调用的setFocus （ ）[focusOutEvent](qwidget.html#focusOutEvent)（）或[focusInEvent](qwidget.html#focusInEvent)（ ） ，你可能会得到一个无限递归。

**See also** [hasFocus](qwidget.html#focus-prop)（ ）[clearFocus](qwidget.html#clearFocus)（ ）[focusInEvent](qwidget.html#focusInEvent)（ ）[focusOutEvent](qwidget.html#focusOutEvent)（ ）[setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）[focusWidget](qwidget.html#focusWidget)（ ）[QApplication.focusWidget](qapplication.html#focusWidget)（ ）[grabKeyboard](qwidget.html#grabKeyboard)（ ）[grabMouse](qwidget.html#grabMouse)（ ）[Keyboard Focus](index.htm)和[QEvent.RequestSoftwareInputPanel](qevent.html#Type-enum)。

```
QWidget.setFocus (self, Qt.FocusReason reason)
```

这是一个重载函数。

使键盘输入焦点将这个小工具（或它的焦点代理） ，如果这个widget或其父母之一是[active window](qwidget.html#isActiveWindow-prop)。

```
QWidget.setFocusPolicy (self, Qt.FocusPolicy policy)
```

```
QWidget.setFocusProxy (self, QWidget)
```

设置控件的焦点代理窗口小部件_w_。如果_w_为0时，函数重置这个小工具有没有焦点代理。

有些部件可以“有重点”，而是创建一个子窗口小部件，如[QLineEdit](qlineedit.html)，实际处理的重点。在这种情况下，小部件可以设置行编辑是它的焦点代理。

setFocusProxy （）设置，将实际获得焦点时， “这个小工具”得到它的部件。如果有一个重点代理，[setFocus](qwidget.html#setFocus)（）和[hasFocus](qwidget.html#focus-prop)（ ）上的焦点代理操作。

**See also** [focusProxy](qwidget.html#focusProxy)（ ） 。

```
QWidget.setFont (self, QFont)
```

```
QWidget.setForegroundRole (self, QPalette.ColorRole)
```

设置构件的背景的角色_role_。

前台角色定义的颜色从部件的[palette](qwidget.html#palette-prop)用于绘制前台。

If _role_ is [QPalette.NoRole](qpalette.html#ColorRole-enum)，小窗口使用，与背景反差作用前景的作用。

需要注意的是款式可以自由从调色板中选择任何颜色。您可以修改调色板或设置一个样式表，如果你没有达到你想要的结果与setForegroundRole （ ） 。

**See also** [foregroundRole](qwidget.html#foregroundRole)（）和[backgroundRole](qwidget.html#backgroundRole)（ ） 。

```
QWidget.setGeometry (self, QRect)
```

```
QWidget.setGeometry (self, int ax, int ay, int aw, int ah)
```

```
QWidget.setGraphicsEffect (self, QGraphicsEffect effect)
```

该_effect_说法有它的所有权转移给Qt的。

该setGraphicsEffect功能是设置控件的图形效果。

Sets _effect_作为widget的效果。如果已经安装了这个小工具的效果，[QWidget](qwidget.html)将安装新的前删除现有的影响_effect_。

If _effect_是安装在不同的小部件， setGraphicsEffect （ ）会从部件中删除的影响，这个widget安装它。

[QWidget](qwidget.html)采取所有权_effect_。

**Note:**此功能适用于本身及其所有儿童的影响。

**Note:**不支持在Mac的图形效果，所以他们不会造成任何差异widget的渲染。

此功能被引入Qt的4.6 。

**See also** [graphicsEffect](qwidget.html#graphicsEffect)（ ） 。

```
QWidget.setHidden (self, bool hidden)
```

这种方法也是一个Qt槽与C + +的签名`void setHidden(bool)`。

便利的功能，相当于其setVisible （ ！_hidden_） 。

**See also** [isHidden](qwidget.html#isHidden)（ ） 。

```
QWidget.setInputContext (self, QInputContext)
```

该_QInputContext_说法有它的所有权转移给Qt的。

该函数设置输入上下文_context_这个小工具。

Qt可以给定输入的所有权_context_。

**See also** [inputContext](qwidget.html#inputContext)（ ） 。

```
QWidget.setInputMethodHints (self, Qt.InputMethodHints hints)
```

```
QWidget.setLayout (self, QLayout)
```

该_QLayout_说法有它的所有权转移给Qt的。

设置此插件的布局管理器_layout_。

如果已经安装了这个小工具布局管理器，[QWidget](qwidget.html)不会让你安装另一个。您必须先删除现有的布局管理器（由返回[layout](qwidget.html#layout)（ ） ） ，然后才能调用的setLayout （ ）使用新的布局。

If _layout_是在不同的小窗口的布局管理器，的setLayout （ ）将reparent的布局，并使其为这个插件的布局管理器。

例如：

```
     [QVBoxLayout](qvboxlayout.html) *layout = new [QVBoxLayout](qvboxlayout.html);
     layout->addWidget(formWidget);
     setLayout(layout);

```

另一种方法来调用这个函数就是这个小部件传递到布局的构造函数。

该[QWidget](qwidget.html)将采取的所有权_layout_。

**See also** [layout](qwidget.html#layout)（）和[Layout Management](index.htm)。

```
QWidget.setLayoutDirection (self, Qt.LayoutDirection direction)
```

```
QWidget.setLocale (self, QLocale locale)
```

```
QWidget.setMask (self, QBitmap)
```

导致部件的唯一的像素的量_bitmap_都有一个对应的1位是可见的。如果该区域包括外部的像素[rect](qwidget.html#rect-prop)（ ） widget的，在这方面的窗口系统的控制可能会或可能不可见，具体取决于平台。

注意，该效果可以是缓慢的，如果该区域是特别复杂的。

下面的代码显示了如何使用alpha通道的图像可以被用来生成一个widget口罩：

```
     [QLabel](qlabel.html) topLevelLabel;
     [QPixmap](qpixmap.html) pixmap(":/../img/tux.png");
     topLevelLabel.setPixmap(pixmap);
     topLevelLabel.setMask(pixmap.mask());

```

通过该代码所示的标籤用它包含，给其一个不规则形状的图像被直接绘制到屏幕上的外观的图像屏蔽。

幪面部件只接收他们的可见部分的鼠标事件。

**See also** [mask](qwidget.html#mask)（ ）[clearMask](qwidget.html#clearMask)（ ）[windowOpacity](qwidget.html#windowOpacity-prop)（）和[Shaped Clock Example](index.htm)。

```
QWidget.setMask (self, QRegion)
```

这是一个重载函数。

这会导致重叠的窗口小部件的唯一的部件_region_可见。如果该区域包括外部的像素[rect](qwidget.html#rect-prop)（ ） widget的，在这方面的窗口系统的控制可能会或可能不可见，具体取决于平台。

注意，该效果可以是缓慢的，如果该区域是特别复杂的。

**See also** [windowOpacity](qwidget.html#windowOpacity-prop)。

```
QWidget.setMaximumHeight (self, int maxh)
```

```
QWidget.setMaximumSize (self, int maxw, int maxh)
```

```
QWidget.setMaximumSize (self, QSize s)
```

```
QWidget.setMaximumWidth (self, int maxw)
```

```
QWidget.setMinimumHeight (self, int minh)
```

```
QWidget.setMinimumSize (self, int minw, int minh)
```

```
QWidget.setMinimumSize (self, QSize s)
```

```
QWidget.setMinimumWidth (self, int minw)
```

```
QWidget.setMouseTracking (self, bool enable)
```

```
QWidget.setPalette (self, QPalette)
```

```
QWidget.setParent (self, QWidget parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

设置控件的父_parent_，并重置窗口的标志。窗口小部件被移动到位置（ 0 ， 0 ）在其新的母公司。

如果新的父控件是在不同的窗口中，重设父窗口部件和它的孩子被附加到的结束[tab chain](qwidget.html#focusPolicy-prop)新的父控件的，在相同的内部秩序和以前一样。如果移动的部件之一，具有键盘焦点， setParent的（ ）的调用[clearFocus](qwidget.html#clearFocus)（）该部件。

如果新的父控件是在同一个窗口的老上级，设置家长不改变Tab键顺序或键盘焦点。

如果“新”的父控件是旧的父窗口部件，这个函数不执行任何操作。

**Note:**窗口小部件变为不可见的改变其父的一部分，即使是以前可见。你必须调用[show](qwidget.html#show)（ ）使控件再次可见。

**Warning:**这是非常不可能的，你永远都需要这个功能。如果你有一个动态改变其内容的小工具，它更容易使用[QStackedWidget](qstackedwidget.html)。

**See also** [setWindowFlags](qwidget.html#windowFlags-prop)（ ） 。

```
QWidget.setParent (self, QWidget parent, Qt.WindowFlags f)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

这是一个重载函数。

此功能还需要窗口部件标记，_f_作为参数。

```
QWidget.setShortcutAutoRepeat (self, int id, bool enabled = True)
```

If _enable_诚然，汽车与给定的快捷方式重复_id_被启用，否则它被禁用。

这个函数中引入了Qt 4.2中。

**See also** [grabShortcut](qwidget.html#grabShortcut)（）和[releaseShortcut](qwidget.html#releaseShortcut)（ ） 。

```
QWidget.setShortcutEnabled (self, int id, bool enabled = True)
```

If _enable_诚然，使用快捷给定的_id_被启用，否则快捷方式被禁用。

**Warning:**你不应该通常需要使用此功能，因为Qt的快捷键系统启用/禁用自动快捷方式小部件变为隐藏/可见和获得或失去焦点。最好是使用[QAction](qaction.html) or [QShortcut](qshortcut.html)处理快捷方式，因为它们更容易比这低级别的功能来使用。

**See also** [grabShortcut](qwidget.html#grabShortcut)（）和[releaseShortcut](qwidget.html#releaseShortcut)（ ） 。

```
QWidget.setShown (self, bool shown)
```

这种方法也是一个Qt槽与C + +的签名`void setShown(bool)`。

```
QWidget.setSizeIncrement (self, int w, int h)
```

```
QWidget.setSizeIncrement (self, QSize s)
```

```
QWidget.setSizePolicy (self, QSizePolicy)
```

```
QWidget.setSizePolicy (self, QSizePolicy.Policy hor, QSizePolicy.Policy ver)
```

```
QWidget.setStatusTip (self, QString)
```

```
QWidget.setStyle (self, QStyle)
```

设置Widget的界面风格_style_。样式对象的所有权不转让。

如果没有样式设置，小部件使用应用程序的风格，[QApplication.style](qapplication.html#style)（ ）来代替。

设置widget的样式对现有或未来的子控件没有影响。

**Warning:**此功能是用于演示目的，在这里要显示Qt的样式功能特别有用。实际应用中应尽量避免它，并使用一个一致的界面风格代替。

**Warning:**目前不支持Qt的样式表定制[QStyle](qstyle.html)子类。我们计划在未来的版本解决这个问题。

**See also** [style](qwidget.html#style)（ ）[QStyle](qstyle.html)，[QApplication.style](qapplication.html#style)（）和[QApplication.setStyle](qapplication.html#setStyle)（ ） 。

```
QWidget.setStyleSheet (self, QString styleSheet)
```

```
QWidget.setTabOrder (QWidget, QWidget)
```

放_second_窗口小部件后_first_窗口小部件中的焦点顺序。

需要注意的是，因为的Tab键顺序_second_窗口小部件被改变，你应该订购链是这样的：

```
 setTabOrder(a, b); // a to b
 setTabOrder(b, c); // a to b to c
 setTabOrder(c, d); // a to b to c to d

```

_not_像这样：

```
 // WRONG
 setTabOrder(c, d); // c to d
 setTabOrder(a, b); // a to b AND c to d
 setTabOrder(b, c); // a to b to c, but not c to d

```

If _first_ or _second_有一个重点代理， setTabOrder （ ）正确地替换代理。

**See also** [setFocusPolicy](qwidget.html#focusPolicy-prop)（ ）[setFocusProxy](qwidget.html#setFocusProxy)（）和[Keyboard Focus](index.htm)。

```
QWidget.setToolTip (self, QString)
```

```
QWidget.setUpdatesEnabled (self, bool enable)
```

```
QWidget.setVisible (self, bool visible)
```

这种方法也是一个Qt槽与C + +的签名`void setVisible(bool)`。

```
QWidget.setWhatsThis (self, QString)
```

```
QWidget.setWindowFilePath (self, QString filePath)
```

```
QWidget.setWindowFlags (self, Qt.WindowFlags type)
```

```
QWidget.setWindowIcon (self, QIcon icon)
```

```
QWidget.setWindowIconText (self, QString)
```

```
QWidget.setWindowModality (self, Qt.WindowModality windowModality)
```

```
QWidget.setWindowModified (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setWindowModified(bool)`。

```
QWidget.setWindowOpacity (self, float level)
```

```
QWidget.setWindowRole (self, QString)
```

设置窗口的作用，_role_。这仅是有道理的，在X11窗口。

**See also** [windowRole](qwidget.html#windowRole)（ ） 。

```
QWidget.setWindowState (self, Qt.WindowStates state)
```

设置窗口状态_windowState_。窗口状态是一个组合逻辑或运算[Qt.WindowState](qt.html#WindowState-enum)：[Qt.WindowMinimized](qt.html#WindowState-enum)，[Qt.WindowMaximized](qt.html#WindowState-enum)，[Qt.WindowFullScreen](qt.html#WindowState-enum)和[Qt.WindowActive](qt.html#WindowState-enum)。

如果该窗口不可见（即[isVisible](qwidget.html#visible-prop)（ ）返回False ） ，窗口状态将生效时[show](qwidget.html#show)（）被调用。对于可见的窗口中，更改会立即生效。例如，全屏和普通模式之间切换，使用下面的代码：

```
 w->setWindowState(w->windowState() ^ [Qt](qt.html).WindowFullScreen);

```

为了恢复和激活一个最小化的窗口（同时保持其最大化和/或全屏幕状态） ，使用以下命令：

```
 w->setWindowState(w->windowState() & ~[Qt](qt.html).WindowMinimized | [Qt](qt.html).WindowActive);

```

调用此函数将隐藏的小工具。你必须调用[show](qwidget.html#show)（ ）使控件再次可见。

**Note:**在某些窗口系统[Qt.WindowActive](qt.html#WindowState-enum)不是即时的，并且在某些情况下可能会被忽略。

当窗口状态改变时，窗口小部件接收到一个[changeEvent](qwidget.html#changeEvent)（类型）[QEvent.WindowStateChange](qevent.html#Type-enum)。

**See also** [Qt.WindowState](qt.html#WindowState-enum)和[windowState](qwidget.html#windowState)（ ） 。

```
QWidget.setWindowTitle (self, QString)
```

```
QWidget.show (self)
```

这种方法也是一个Qt槽与C + +的签名`void show()`。

显示部件和子部件。此功能相当于其setVisible （真） 。

**See also** [raise_](qwidget.html#raise)（ ）[showEvent](qwidget.html#showEvent)（ ）[hide](qwidget.html#hide)（ ）[setVisible](qwidget.html#visible-prop)（ ）[showMinimized](qwidget.html#showMinimized)（ ）[showMaximized](qwidget.html#showMaximized)（ ）[showNormal](qwidget.html#showNormal)（）和[isVisible](qwidget.html#visible-prop)（ ） 。

```
QWidget.showEvent (self, QShowEvent)
```

此事件处理程序可以重新实现在子类中以接收传递在widget显示事件_event_参数。

非自发的表演活动会立即发送到窗口部件才能显示。窗口的自发表演事件之后交付。

注：控件接收自发的显示和隐藏事件时，其对应的状态是由窗口系统改变，如当用户最小化窗口，当窗口再次恢复自发show事件自发的隐藏事件。接收自发的隐藏事件之后，一个小部件仍然被认为是在这个意义上可见[isVisible](qwidget.html#visible-prop)（ ） 。

**See also** [visible](qwidget.html#visible-prop)，[event](qwidget.html#event)（）和[QShowEvent](qshowevent.html)。

```
QWidget.showFullScreen (self)
```

这种方法也是一个Qt槽与C + +的签名`void showFullScreen()`。

显示了在全屏模式下的部件。

调用此函数只影响[windows](qwidget.html#isWindow)。

若要从全屏模式返回，调用[showNormal](qwidget.html#showNormal)（ ） 。

Windows下的全屏幕模式下工作正常，但在十一定的问题，这些问题都是由于ICCCM协议，规定X11客户端和窗口管理器之间的通信的限制。 ICCCM根本不明白的非装饰的全屏窗口的概念。因此，我们可以做的最好的是要求一个无国界的窗口和地点，并调整其大小，以填满整个屏幕。根据不同的窗口管理器，这可能会或可能无法正常工作。使用MOTIF提示，这是至少部分由几乎所有的现代窗口管理器支持请求的无边框窗口。

另一种方法是完全绕过窗口管理器，并创建了一个窗口[Qt.X11BypassWindowManagerHint](qt.html#WindowType-enum)标志。这有其他严重问题，虽然，像完全打破键盘焦点，很奇怪的效果在桌面上的变化或在用户将其他窗口。

遵循现代后ICCCM规格的X11窗口管理器支持全屏模式下正常工作。

**See also** [showNormal](qwidget.html#showNormal)（ ）[showMaximized](qwidget.html#showMaximized)（ ）[show](qwidget.html#show)（ ）[hide](qwidget.html#hide)（）和[isVisible](qwidget.html#visible-prop)（ ） 。

```
QWidget.showMaximized (self)
```

这种方法也是一个Qt槽与C + +的签名`void showMaximized()`。

显示小工具最大化。

调用此函数只影响[windows](qwidget.html#isWindow)。

在X11上，此功能可能无法正常使用某些窗口管理工作。请参阅[Window Geometry](index.htm#window-geometry)文档说明。

**See also** [setWindowState](qwidget.html#setWindowState)（ ）[showNormal](qwidget.html#showNormal)（ ）[showMinimized](qwidget.html#showMinimized)（ ）[show](qwidget.html#show)（ ）[hide](qwidget.html#hide)（）和[isVisible](qwidget.html#visible-prop)（ ） 。

```
QWidget.showMinimized (self)
```

这种方法也是一个Qt槽与C + +的签名`void showMinimized()`。

显示了部件最小化，为图标。

调用此函数只影响[windows](qwidget.html#isWindow)。

**See also** [showNormal](qwidget.html#showNormal)（ ）[showMaximized](qwidget.html#showMaximized)（ ）[show](qwidget.html#show)（ ）[hide](qwidget.html#hide)（ ）[isVisible](qwidget.html#visible-prop)（）和[isMinimized](qwidget.html#minimized-prop)（ ） 。

```
QWidget.showNormal (self)
```

这种方法也是一个Qt槽与C + +的签名`void showNormal()`。

恢复插件它已被最大化或最小化之后。

调用此函数只影响[windows](qwidget.html#isWindow)。

**See also** [setWindowState](qwidget.html#setWindowState)（ ）[showMinimized](qwidget.html#showMinimized)（ ）[showMaximized](qwidget.html#showMaximized)（ ）[show](qwidget.html#show)（ ）[hide](qwidget.html#hide)（）和[isVisible](qwidget.html#visible-prop)（ ） 。

```
QSize QWidget.size (self)
```

[](qsize.html)

```
QSize QWidget.sizeHint (self)
```

[](qsize.html)

```
QSize QWidget.sizeIncrement (self)
```

[](qsize.html)

```
QSizePolicy QWidget.sizePolicy (self)
```

[

```
QWidget.stackUnder (self, QWidget)
```

下放置小工具_w_在父窗口部件的堆栈。

为了使这项工作中，窗口小部件本身_w_必须是兄弟姐妹。

](qsizepolicy.html)

[**See also**](qsizepolicy.html) [raise_](qwidget.html#raise)（）和[lower](qwidget.html#lower)（ ） 。

```
QString QWidget.statusTip (self)
```

```
QStyle QWidget.style (self)
```

[](qstyle.html)

[**See also**](qstyle.html) [QWidget.setStyle](qwidget.html#setStyle)（ ）[QApplication.setStyle](qapplication.html#setStyle)（）和[QApplication.style](qapplication.html#style)（ ） 。

```
QString QWidget.styleSheet (self)
```

```
QWidget.tabletEvent (self, QTabletEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类来接收事件平板电脑的部件。

如果你重新实现这个处理程序，这是非常重要的，你[ignore()](qtabletevent.html)如果你不处理它，从而使部件的家长可以把它解释事件。

默认的实现将忽略该事件。

**See also** [QTabletEvent.ignore](qevent.html#ignore)（ ）[QTabletEvent.accept](qevent.html#accept)（ ）[event](qwidget.html#event)（）和[QTabletEvent](qtabletevent.html)。

```
bool QWidget.testAttribute (self, Qt.WidgetAttribute attribute)
```

返回True ，如果属性_attribute_设置这个小工具，否则返回False 。

**See also** [setAttribute](qwidget.html#setAttribute)（ ） 。

```
QString QWidget.toolTip (self)
```

```
QWidget QWidget.topLevelWidget (self)
```

[

```
bool QWidget.underMouse (self)
```

返回True如果该控件是鼠标光标下，否则返回False 。

这个值是不是在拖放操作正确更新。

](qwidget.html)

[**See also**](qwidget.html) [enterEvent](qwidget.html#enterEvent)（）和[leaveEvent](qwidget.html#leaveEvent)（ ） 。

```
QWidget.ungrabGesture (self, Qt.GestureType type)
```

从一个给定的退订的插件_gesture_类型

此功能被引入Qt的4.6 。

**See also** [grabGesture](qwidget.html#grabGesture)（）和[QGestureEvent](qgestureevent.html)。

```
QWidget.unsetCursor (self)
```

```
QWidget.unsetLayoutDirection (self)
```

```
QWidget.unsetLocale (self)
```

```
QWidget.update (self)
```

这种方法也是一个Qt槽与C + +的签名`void update()`。

更新小部件，除非更新被禁用或小部件是隐藏的。

此功能不会导致立即重绘，相反，它安排一个Paint事件处理时的Qt返回到主事件循环。这使得Qt的优化更多的速度和更少的闪烁比调用[repaint](qwidget.html#repaint)（ ）一样。

调用update （ ）多次通常会导致只有一个[paintEvent](qwidget.html#paintEvent)（ ）调用。

Qt的前通常会删除Widget的区域[paintEvent](qwidget.html#paintEvent)（ ）调用。如果[Qt.WA_OpaquePaintEvent](qt.html#WidgetAttribute-enum)插件属性被设置，插件是负责绘制它的所有像素具有不透明颜色。

**See also** [repaint](qwidget.html#repaint)（ ）[paintEvent](qwidget.html#paintEvent)（ ）[setUpdatesEnabled](qwidget.html#updatesEnabled-prop)（）和[Analog Clock Example](index.htm)。

```
QWidget.update (self, QRect)
```

这是一个重载函数。

此版本更新的矩形（_x_，_y_，_w_，_h_）内的部件。

```
QWidget.update (self, QRegion)
```

这是一个重载函数。

此版本更新的矩形_rect_内部的部件。

```
QWidget.update (self, int ax, int ay, int aw, int ah)
```

这是一个重载函数。

这个版本重新绘制的区域_rgn_内部的部件。

```
QWidget.updateGeometry (self)
```

通知这个小工具已经改变，可能需要改变几何布局系统。

调用此函数的[sizeHint](qwidget.html#sizeHint-prop)（）或[sizePolicy](qwidget.html#sizePolicy-prop)（ ）已经改变。

对于显式隐藏小部件， updateGeometry （ ）是一个空操作。布局系统将尽快为小部件显示通知。

```
QWidget.updateMicroFocus (self)
```

更新微件的微焦点。

**See also** [QInputContext](qinputcontext.html)。

```
bool QWidget.updatesEnabled (self)
```

```
QRegion QWidget.visibleRegion (self)
```

[

返回在paint事件可以发生在视野开阔的区域。

为可见的部件，这是不包括在其他窗口小部件的区域的近似，否则，这是一个空的区域。

](qregion.html)

[该](qregion.html)[repaint](qwidget.html#repaint)（ ）函数调用这个函数，如果有必要，所以一般你不需要调用它。

```
QString QWidget.whatsThis (self)
```

```
QWidget.wheelEvent (self, QWheelEvent)
```

此事件处理程序，对于事件_event_，可重新实现在子类来接收滚轮事件的小部件。

如果你重新实现这个处理程序，这是非常重要的，你[ignore()](qwheelevent.html)如果你不处理它，从而使部件的家长可以把它解释事件。

默认的实现将忽略该事件。

**See also** [QWheelEvent.ignore](qevent.html#ignore)（ ）[QWheelEvent.accept](qevent.html#accept)（ ）[event](qwidget.html#event)（）和[QWheelEvent](qwheelevent.html)。

```
int QWidget.width (self)
```

```
QWidget QWidget.window (self)
```

[

返回此插件的窗口，也就是下一个祖先窗口小部件，有（或可能有）一个窗口系统框架。

如果部件是一个窗口，则返回小部件本身。

典型的用法是改变窗口标题：

](qwidget.html)

```
 aWidget->window()->setWindowTitle("New Window Title");

```

**See also** [isWindow](qwidget.html#isWindow)（ ） 。

```
QWidget.windowActivationChange (self, bool)
```

```
QString QWidget.windowFilePath (self)
```

```
Qt.WindowFlags QWidget.windowFlags (self)
```

[](index.htm)

```
QIcon QWidget.windowIcon (self)
```

[

```
QString QWidget.windowIconText (self)
```

](qicon.html)

```
Qt.WindowModality QWidget.windowModality (self)
```

[

```
float QWidget.windowOpacity (self)
```

```
QString QWidget.windowRole (self)
```

返回窗口的角色，或一个空字符串。

](qt.html#WindowModality-enum)

[**See also**](qt.html#WindowModality-enum) [setWindowRole](qwidget.html#setWindowRole)（ ）[windowIcon](qwidget.html#windowIcon-prop)和[windowTitle](qwidget.html#windowTitle-prop)。

```
Qt.WindowStates QWidget.windowState (self)
```

[](index.htm)

[返回当前窗口状态。窗口状态是一个组合逻辑或运算](index.htm)[Qt.WindowState](qt.html#WindowState-enum)：[Qt.WindowMinimized](qt.html#WindowState-enum)，[Qt.WindowMaximized](qt.html#WindowState-enum)，[Qt.WindowFullScreen](qt.html#WindowState-enum)和[Qt.WindowActive](qt.html#WindowState-enum)。

**See also** [Qt.WindowState](qt.html#WindowState-enum)和[setWindowState](qwidget.html#setWindowState)（ ） 。

```
QString QWidget.windowTitle (self)
```

```
Qt.WindowType QWidget.windowType (self)
```

[](qt.html#WindowType-enum)

[返回这个窗口部件的窗口类型。这是相同的](qt.html#WindowType-enum)[windowFlags](qwidget.html#windowFlags-prop)（）和[Qt.WindowType_Mask](qt.html#WindowType-enum)。

**See also** [windowFlags](qwidget.html#windowFlags-prop)。

```
int QWidget.winId (self)
```

返回该窗口小部件的窗口系统标识符。

便携式原则，但如果你使用它，你可能是在做一件不可移植的。一定要小心。

如果一个widget是母语非（外星人）和winId （ ）是在其上调用，该小工具将提供一个原生手柄。

在Mac OS X ，返回的类型取决于哪个框架Qt的被挂反对。如果Qt是使用碳时， { WID }实际上是一个HIViewRef 。如果Qt是用可可， { WID }是一个指针，指向一个NSView的。

这个值可能会改变在运行时。同类型的事件[QEvent.WinIdChange](qevent.html#Type-enum)以下在窗口系统标识符的改变将被发送到窗口小部件。

**See also** [find](qwidget.html#find)（ ） 。

```
int QWidget.x (self)
```

```
QX11Info QWidget.x11Info (self)
```

[

返回有关用于显示插件的X显示的配置信息。

**Warning:**此功能仅适用于X11 。

```
int QWidget.x11PictureHandle (self)
```

返回widget的X11图片句柄XRender的支持。这个函数的使用是不可移植的。这个函数将返回0，如果XRender的支持是不会被编译到Qt的，如果XRender的扩展不支持X11的显示器上，或者如果无法创建的句柄。

```
int QWidget.y (self)
```

* * *

## Qt Signal Documentation

```
void customContextMenuRequested (const QPoint&)
```

这是该信号的默认超载。

](qx11info.html)

[这个信号被发射时，窗口小部件的](qx11info.html)[contextMenuPolicy](qwidget.html#contextMenuPolicy-prop) is [Qt.CustomContextMenu](qt.html#ContextMenuPolicy-enum)，并且用户已经请求对小部件的上下文菜单。位置_pos_是该插件接收的上下文菜单事件的位置。通常，这是在小部件坐标。唯一的例外规则[QAbstractScrollArea](qabstractscrollarea.html)和它的子类映射的上下文菜单事件的坐标[viewport()](qabstractscrollarea.html#viewport)。

**See also** [mapToGlobal](qwidget.html#mapToGlobal)（ ）[QMenu](qmenu.html)和[contextMenuPolicy](qwidget.html#contextMenuPolicy-prop)。