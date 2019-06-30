# QObject Class Reference

## [[QtCore](index.htm) module]

该QObject的类是所有的Qt对象的基类。[More...](#details)

通过继承[AbstractAudioOutput](index.htm)，[Notifier](index.htm)，[Effect](index.htm)，[MediaController](index.htm)，[MediaObject](index.htm)，[QAbstractAnimation](qabstractanimation.html)，[QAbstractEventDispatcher](qabstracteventdispatcher.html)，[QAbstractItemDelegate](qabstractitemdelegate.html)，[QAbstractItemModel](qabstractitemmodel.html)，[QAbstractMessageHandler](qabstractmessagehandler.html)，[QAbstractNetworkCache](qabstractnetworkcache.html)，[QAbstractState](qabstractstate.html)，[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)，[QAbstractTransition](qabstracttransition.html)，[QAbstractUriResolver](qabstracturiresolver.html)，[QAbstractVideoSurface](qabstractvideosurface.html)，[QAction](qaction.html)，[QActionGroup](qactiongroup.html)，[QAssistantClient](qassistantclient.html)，[QAudioInput](qaudioinput.html)，[QAudioOutput](qaudiooutput.html)，[QButtonGroup](qbuttongroup.html)，[QClipboard](qclipboard.html)，[QCompleter](qcompleter.html)，[QCoreApplication](qcoreapplication.html)，[QDataWidgetMapper](qdatawidgetmapper.html)，[QDBusAbstractAdaptor](qdbusabstractadaptor.html)，[QDBusAbstractInterface](qdbusabstractinterface.html)，[QDBusPendingCallWatcher](qdbuspendingcallwatcher.html)，[QDBusServiceWatcher](qdbusservicewatcher.html)，[QDeclarativeComponent](qdeclarativecomponent.html)，[QDeclarativeContext](qdeclarativecontext.html)，[QDeclarativeEngine](qdeclarativeengine.html)，[QDeclarativeExpression](qdeclarativeexpression.html)，[QDeclarativeExtensionPlugin](qdeclarativeextensionplugin.html)，[QDeclarativePropertyMap](qdeclarativepropertymap.html)，[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)，[QDesignerFormWindowManagerInterface](qdesignerformwindowmanagerinterface.html)，[QDrag](qdrag.html)，[QEventLoop](qeventloop.html)，[QExtensionFactory](qextensionfactory.html)，[QExtensionManager](qextensionmanager.html)，[QFileSystemWatcher](qfilesystemwatcher.html)，[QFtp](qftp.html)，[QGesture](qgesture.html)，[QGLShader](qglshader.html)，[QGLShaderProgram](qglshaderprogram.html)，[QGraphicsAnchor](qgraphicsanchor.html)，[QGraphicsEffect](qgraphicseffect.html)，[QGraphicsItemAnimation](qgraphicsitemanimation.html)，[QGraphicsObject](qgraphicsobject.html)，[QGraphicsScene](qgraphicsscene.html)，[QGraphicsTransform](qgraphicstransform.html)，[QHelpEngineCore](qhelpenginecore.html)，[QHelpSearchEngine](qhelpsearchengine.html)，[QHttp](qhttp.html)，[QHttpMultiPart](qhttpmultipart.html)，[QInputContext](qinputcontext.html)，[QIODevice](qiodevice.html)，[QItemSelectionModel](qitemselectionmodel.html)，[QLayout](qlayout.html)，[QLibrary](qlibrary.html)，[QLocalServer](qlocalserver.html)，[QMimeData](qmimedata.html)，[QMovie](qmovie.html)，[QNetworkAccessManager](qnetworkaccessmanager.html)，[QNetworkConfigurationManager](qnetworkconfigurationmanager.html)，[QNetworkCookieJar](qnetworkcookiejar.html)，[QNetworkSession](qnetworksession.html)，[QObjectCleanupHandler](qobjectcleanuphandler.html)，[QPluginLoader](qpluginloader.html)，[QPyDeclarativePropertyValueSource](qpydeclarativepropertyvaluesource.html)，[QPyDesignerContainerExtension](qpydesignercontainerextension.html)，[QPyDesignerCustomWidgetCollectionPlugin](qpydesignercustomwidgetcollectionplugin.html)，[QPyDesignerCustomWidgetPlugin](qpydesignercustomwidgetplugin.html)，[QPyDesignerMemberSheetExtension](qpydesignermembersheetextension.html)，[QPyDesignerPropertySheetExtension](qpydesignerpropertysheetextension.html)，[QPyDesignerTaskMenuExtension](qpydesignertaskmenuextension.html)，[QPyTextObject](qpytextobject.html)，[QScriptEngine](qscriptengine.html)，[QScriptEngineDebugger](qscriptenginedebugger.html)，[QSessionManager](qsessionmanager.html)，[QSettings](qsettings.html)，[QSharedMemory](qsharedmemory.html)，[QShortcut](qshortcut.html)，[QSignalMapper](qsignalmapper.html)，[QSocketNotifier](qsocketnotifier.html)，[QSound](qsound.html)，[QSqlDriver](qsqldriver.html)，[QStyle](qstyle.html)，[QSvgRenderer](qsvgrenderer.html)，[QSyntaxHighlighter](qsyntaxhighlighter.html)，[QSystemTrayIcon](qsystemtrayicon.html)，[QTcpServer](qtcpserver.html)，[QTextDocument](qtextdocument.html)，[QTextObject](qtextobject.html)，[QThread](qthread.html)，[QThreadPool](qthreadpool.html)，[QTimeLine](qtimeline.html)，[QTimer](qtimer.html)，[QTranslator](qtranslator.html)，[QUndoGroup](qundogroup.html)，[QUndoStack](qundostack.html)，[QValidator](qvalidator.html)，[QWebFrame](qwebframe.html)，[QWebHistoryInterface](qwebhistoryinterface.html)，[QWebPage](qwebpage.html)，[QWebPluginFactory](qwebpluginfactory.html)和[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool blockSignals (self, bool b)`
*   `childEvent (self, QChildEvent)`
*   `list-of-QObject children (self)`
*   `bool connect (self, QObject, SIGNAL(), SLOT(), Qt.ConnectionType = Qt.AutoConnection)`
*   `connectNotify (self, SIGNAL() signal)`
*   `customEvent (self, QEvent)`
*   `deleteLater (self)`
*   `disconnectNotify (self, SIGNAL() signal)`
*   `dumpObjectInfo (self)`
*   `dumpObjectTree (self)`
*   `list-of-QByteArray dynamicPropertyNames (self)`
*   `emit (self, SIGNAL(), ...)`
*   `bool event (self, QEvent)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `QObject findChild (self, type type, QString name = QString())`
*   `QObject findChild (self, tuple types, QString name = QString())`
*   `list-of-QObject findChildren (self, type type, QString name = QString())`
*   `list-of-QObject findChildren (self, tuple types, QString name = QString())`
*   `list-of-QObject findChildren (self, type type, QRegExp regExp)`
*   `list-of-QObject findChildren (self, tuple types, QRegExp regExp)`
*   `bool inherits (self, str classname)`
*   `installEventFilter (self, QObject)`
*   `bool isWidgetType (self)`
*   `killTimer (self, int id)`
*   `QMetaObject metaObject (self)`
*   `moveToThread (self, QThread thread)`
*   `QString objectName (self)`
*   `QObject parent (self)`
*   `QVariant property (self, str name)`
*   `pyqtConfigure (self, object)`
*   `int receivers (self, SIGNAL() signal)`
*   `removeEventFilter (self, QObject)`
*   `QObject sender (self)`
*   `int senderSignalIndex (self)`
*   `setObjectName (self, QString name)`
*   `setParent (self, QObject)`
*   `bool setProperty (self, str name, QVariant value)`
*   `bool signalsBlocked (self)`
*   `int startTimer (self, int interval)`
*   `QThread thread (self)`
*   `timerEvent (self, QTimerEvent)`
*   `QString tr (self, str sourceText, str disambiguation = None, int n = -1)`
*   `QString trUtf8 (self, str sourceText, str disambiguation = None, int n = -1)`

### Static Methods

*   `bool connect (QObject, SIGNAL(), QObject, SLOT(), Qt.ConnectionType = Qt.AutoConnection)`
*   `bool connect (QObject, SIGNAL(), callable, Qt.ConnectionType = Qt.AutoConnection)`
*   `bool disconnect (QObject, SIGNAL(), QObject, SLOT())`
*   `bool disconnect (QObject, SIGNAL(), callable)`

### Special Methods

*   `object __getattr__ (self, str name)`

### Qt Signals

*   `void destroyed (QObject * = 0)`

### Static Members

*   `QMetaObject **[staticMetaObject](qobject.html#staticMetaObject-var)**`

* * *

## Detailed Description

该QObject的类是所有的Qt对象的基类。

QObject的是Qt的心脏[Object Model](index.htm)。在此模型中的核心特征是一种称为非常强大的机制来无缝对象的通信[signals and slots](index.htm#signals-and-slots)。你可以用一个信号连接到槽[connect](qobject.html#connect)（ ）和destroy与连接[disconnect](qobject.html#disconnect)（ ） 。为了避免无休止的通知循环可以暂时阻止信号与[blockSignals](qobject.html#blockSignals)（ ） 。该保护功能[connectNotify](qobject.html#connectNotify)（）和[disconnectNotify](qobject.html#disconnectNotify)（）使得有可能跟踪的连接。

[QObjects](index.htm#qobjects)组织起来的[object trees](index.htm)。当你创建与另一个对象作为父项的QObject的，该对象将自己自动添加到父的[children](qobject.html#children)（ ）列表。家长需要的对象的所有权，也就是说，它会自动删除其在其析构函数的孩子。你可以找一个对象的名字和可选输入使用[findChild](qobject.html#findChild)（）或[findChildren](qobject.html#findChildren)（ ） 。

每个对象都有一个[objectName](qobject.html#objectName-prop)（ ）和它的类名可以通过相应的发现[metaObject](qobject.html#metaObject)（ ） （见[QMetaObject.className](qmetaobject.html#className)（））。你能确定对象的类是否继承另一个类中的QObject继承层次结构使用[inherits](qobject.html#inherits)（）函数。

当一个对象被删除时，它会发出一个[destroyed](qobject.html#destroyed)（）信号。你可以捕获这个信号，以避免悬空引用[QObjects](index.htm#qobjects)。

[QObjects](index.htm#qobjects)可以通过接收事件[event](qobject.html#event)（）和过滤器的其他对象的事件。看[installEventFilter](qobject.html#installEventFilter)（）和[eventFilter](qobject.html#eventFilter)（ ）了解详情。一个方便的处理程序，[childEvent](qobject.html#childEvent)（ ） ，可重新实现以赶上孩子的事件。

事件被交付于该对象被创建的线程，见[Thread Support in Qt](index.htm)和[thread](qobject.html#thread)（ ）了解详情。请注意，事件处理是根本无法完成的[QObjects](index.htm#qobjects)没有线程关联（[thread](qobject.html#thread)（ ）返回零） 。使用[moveToThread](qobject.html#moveToThread)（ ）函数来改变一个对象及其子对象的线程关联（如果它有一个父对象不能移动） 。

最后但并非最不重要的， QObject中提供了Qt的基本定时器支持;见[QTimer](qtimer.html)为定时器高层的支持。

请注意，该[Q_OBJECT](qobject.html#Q_OBJECT)宏是强制实现信号，槽或属性的对象。您还需要运行[Meta Object Compiler](index.htm#moc)在源文件中。我们强烈建议使用这个宏的QObject的子类，而不管是否与自己实际使用的信号，槽和属性，因为如果不这样做可能会导致某些功能表现出奇怪的行为。

Qt的所有控件继承QObject的。便利的功能[isWidgetType](qobject.html#isWidgetType)（ ）返回一个对象是否实际上是一个小部件。这是比要快得多[qobject_cast](qobject.html#qobject_cast)\u003c[QWidget](qwidget.html)* \u003e （_obj_）或_obj_ - \u003e[inherits](qobject.html#inherits)（ “[QWidget](qwidget.html)“ ） 。

一些QObject的功能，例如[children](qobject.html#children)（ ） ，返回一个[QObjectList](qobject.html#QObjectList-typedef)。[QObjectList](qobject.html#QObjectList-typedef)是一个typedef为[QList](index.htm)\u003cQObject *\u003e 。

### No copy constructor or assignment operator

QObject中既没有拷贝构造函数，也不是一个赋值操作符。这是设计使然。实际上，它们被声明，但在一个`private`与宏段[Q_DISABLE_COPY](qobject.html#Q_DISABLE_COPY)（ ） 。事实上，自QObject （直接或间接）派生的所有Qt类使用这个宏来声明自己的拷贝构造函数和赋值操作符是私有的。其理由是在讨论中找到[Identity vs Value](index.htm#identity-vs-value)在Qt的[Object Model](index.htm)页面。

主要的后果是，你应该使用指针的QObject （或您的QObject的子类） ，你可能被诱惑去使用QObject的子类作为值。例如，如果没有拷贝构造函数，则不能使用的QObject的子类将其存储在容器类中的一个值。你必须存储的指针。

### Auto-Connection

Qt的元对象系统提供了一种机制来自动连接QObject的子类与子女之间的信号和槽。只要对象与合适的对象名称来定义的，与插槽遵循一个简单的命名惯例，这种连接可以在运行时被执行[QMetaObject.connectSlotsByName](qmetaobject.html#connectSlotsByName)（）函数。

[uic](index.htm#uic)生成调用这个函数被用在创建窗体小部件之间进行，以启用自动连接代码_Qt Designer_。有关使用带自动连接的详细信息_Qt Designer_是由于在[Using a Designer UI File in Your Application](index.htm)的节_Qt Designer_手册。

### Dynamic Properties

从Qt 4.2中，动态属性可以被添加到和从在运行时QObject的实例中删除。动态属性不需要在编译时被声明，但它们提供了相同的优点的静态属性和使用相同的API等的操作 - 使用[property](qobject.html#property)（）来读取它们，[setProperty](qobject.html#setProperty)（ ）来写他们。

在Qt 4.3 ，动态属性是由支持[Qt Designer](index.htm#the-property-editor)，以及标准Qt控件和用户创建的表格可以给出动态属性。

### Internationalization (i18n)

所有的QObject子类支持Qt的翻译功能，使其能够翻译应用程序的用户界面为不同的语言。

为了让用户可见的文本翻译，它必须被包裹在调用[tr](qobject.html#tr)（）函数。此进行了详细的解释[Writing Source Code for Translation](index.htm)文档。

* * *

## Method Documentation

```
QObject.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个对象的父对象_parent_。

一个对象的父对象可以被视为对象的所有者。例如，一个[dialog box](qdialog.html)是父**OK**和**Cancel**按钮，它包含的内容。

父对象的析构函数销毁所有子对象。

Setting _parent_0构造一个对象没有父。如果对象是一个小部件，它会成为一个顶级窗口。

**See also** [parent](qobject.html#parent)（ ）[findChild](qobject.html#findChild)（）和[findChildren](qobject.html#findChildren)（ ） 。

```
bool QObject.blockSignals (self, bool b)
```

If _block_诚然，此对象发出的信号被阻塞（即，发射的信号不会调用任何连接到它） 。如果_block_是假的，不会发生这样的阻塞。

返回值是以前的值[signalsBlocked](qobject.html#signalsBlocked)（ ） 。

注意，这个[destroyed](qobject.html#destroyed)（ ）信号，即使此对象的信号已经被封锁发射。

**See also** [signalsBlocked](qobject.html#signalsBlocked)（ ） 。

```
QObject.childEvent (self, QChildEvent)
```

此事件处理程序可以重新实现在子类中接收子事件。该事件被传递的_event_参数。

[QEvent.ChildAdded](qevent.html#Type-enum)和[QEvent.ChildRemoved](qevent.html#Type-enum)事件被发送到对象时，孩子们被添加或删除。在这两种情况下，你只能依靠孩子作为一个[QObject](qobject.html)，或者如果[isWidgetType](qobject.html#isWidgetType)（ ）返回True ，一[QWidget](qwidget.html)。 （这是因为，在[ChildAdded](qevent.html#Type-enum)情况下，孩子还没有完全建成，并在[ChildRemoved](qevent.html#Type-enum)情况下，它可能已被破坏的话） 。

[QEvent.ChildPolished](qevent.html#Type-enum)事件发送到窗口部件时，孩子们都经过抛光处理，或打磨时，孩子们补充说。如果您收到一个孩子抛光事件，孩子的建造通常完成。然而，这并不能完全保证，并且多个抛光事件可能Widget的构造函数的执行过程中被传递。

对于每个子控件，您收到一个[ChildAdded](qevent.html#Type-enum)事件，零个或多个[ChildPolished](qevent.html#Type-enum)事件，和一个[ChildRemoved](qevent.html#Type-enum)事件。

该[ChildPolished](qevent.html#Type-enum)如果一个孩子被立即删除它被添加后，事件被省略。如果一个孩子被构造和析构过程中进行多次打磨，您可能会收到多个孩子抛光事件相同的孩子，每次使用不同的虚表。

**See also** [event](qobject.html#event)（ ） 。

```
list-of-QObject QObject.children (self)
```

返回子对象的列表。该[QObjectList](qobject.html#QObjectList-typedef)类中所定义的`&lt;QObject&gt;`头文件如下：

```
 typedef [QList](index.htm)<[QObject](qobject.html)*> [QObjectList](qobject.html#QObjectList-typedef);

```

添加的第一个孩子是[first](index.htm#first)在添加列表和最后一个子对象是[last](index.htm#last)列表中的对象，即新的儿童将被附加在最后。

请注意，该列表中的顺序改变时，[QWidget](qwidget.html)孩子们[raised](qwidget.html#raise) or [lowered](qwidget.html#lower)。所提出的一个小部件成为列表中的最后一个对象，并且被降低一个小部件成为列表中的第一个对象。

**See also** [findChild](qobject.html#findChild)（ ）[findChildren](qobject.html#findChildren)（ ）[parent](qobject.html#parent)（）和[setParent](qobject.html#setParent)（ ） 。

```
bool QObject.connect (QObject, SIGNAL(), QObject, SLOT(), Qt.ConnectionType = Qt.AutoConnection)
```

产生的给定的连接_type_从_signal_在_sender_反对_method_在_receiver_对象。返回True如果连接成功，否则返回False 。

您必须使用`SIGNAL()`和`SLOT()`当指定的宏_signal_和_method_例如：

```
 [QLabel](qlabel.html) *label = new [QLabel](qlabel.html);
 [QScrollBar](qscrollbar.html) *scrollBar = new [QScrollBar](qscrollbar.html);
 [QObject](qobject.html).connect(scrollBar, SIGNAL(valueChanged(int)),
                  label,  SLOT(setNum(int)));

```

这个例子可以确保标籤始终显示当前滚动条的值。注意，信号和槽的参数必须不包含任何变量名，只有类型。例如以下是行不通的，并返回False ：

```
 // WRONG
 [QObject](qobject.html).connect(scrollBar, SIGNAL(valueChanged(int value)),
                  label, SLOT(setNum(int value)));

```

的信号也可以被连接到另一个信号：

```
 class MyWidget : public [QWidget](qwidget.html)
 {
     Q_OBJECT

 public:
     MyWidget();

 signals:
     void buttonClicked();

 private:
     [QPushButton](qpushbutton.html) *myButton;
 };

 MyWidget.MyWidget()
 {
     myButton = new [QPushButton](qpushbutton.html)(this);
     connect(myButton, SIGNAL(clicked()),
             this, SIGNAL(buttonClicked()));
 }

```

在该示例中，`MyWidget`构造函数从一个私有成员变量继电器的信号，并使其可下，涉及到一个名称`MyWidget`。

一个信号可以连接到多个插槽和信号。很多信号可以连接到一个时隙。

如果一个信号被连接到多个槽，这些槽以相同的顺序被激活作为连接被做，当信号被发射的次序。

如果它成功地将信号与槽连接的函数返回True。它会返回False ，如果它不能建立连接，例如，如果[QObject](qobject.html)无法验证或者存在_signal_ or _method_，或者如果他们的签名是不兼容的。

默认情况下，一个信号被发射为你倾尽连接;两个信号发出重复的连接。你可以打破所有这些连接与单个[disconnect](qobject.html#disconnect)（ ）调用。如果你通过了[Qt.UniqueConnection](qt.html#ConnectionType-enum) _type_，连接将仅当它是不重复进行。如果已经有一个重复（完全相同的信号，对相同的对象完全相同的插槽） ，连接将失败，连接将返回False 。

可选的_type_参数描述了连接建立的类型。特别是，它确定一个特定的信号是否被传递到紧接在一个时隙或排队等待传递在以后的时间。如果信号排队，该参数必须是已知Qt的元对象系统类型，因为Qt的需要复制到它们存储在幕后事件的参数。如果您尝试使用一个排队的连接，并收到错误消息

```
 [QObject](qobject.html).connect: Cannot queue arguments of type 'MyType'
 (Make sure 'MyType' is registered using qRegisterMetaType().)

```

通话[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（）注册的数据类型你建立连接之前。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [disconnect](qobject.html#disconnect)（ ）[sender](qobject.html#sender)（ ）[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（）和[Q_DECLARE_METATYPE](qmetatype.html#Q_DECLARE_METATYPE)（ ） 。

```
bool QObject.connect (QObject, SIGNAL(), callable, Qt.ConnectionType = Qt.AutoConnection)
```

产生的给定的连接_type_从_signal_在_sender_反对_method_在_receiver_对象。返回True如果连接成功，否则返回False 。

该功能的工作原理相同的方式连接（常量[QObject](qobject.html)*发件人，为const char *的信号，常量[QObject](qobject.html)*接收器，为const char *的方法，[Qt.ConnectionType](qt.html#ConnectionType-enum)型），但它使用了[QMetaMethod](qmetamethod.html)指定信号和方法。

此功能被引入Qt的4.8 。

**See also**连接（常量的QObject *寄件人，为const char *的信号，常量的QObject *接收器，为const char *的方法， Qt.ConnectionType型） 。

```
bool QObject.connect (self, QObject, SIGNAL(), SLOT(), Qt.ConnectionType = Qt.AutoConnection)
```

这个函数的重载[connect](qobject.html#connect)（ ） 。

连接型_signal_从_sender_反对此对象的_method_。

相当于连接（_sender_，_signal_，`this`，_method_，_type_） 。

你让每个连接发射信号，所以重复的连接发出两个信号。您可以使用破解的连接[disconnect](qobject.html#disconnect)（ ） 。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [disconnect](qobject.html#disconnect)（ ） 。

```
QObject.connectNotify (self, SIGNAL() signal)
```

这个虚函数被调用时，事情已经连接到_signal_在这个对象。

如果你想比较_signal_与一个特定的信号，使用[QLatin1String](qlatin1string.html)和`SIGNAL()`宏如下：

```
 if (QLatin1String(signal) == SIGNAL(valueChanged(int))) {
     // signal is valueChanged(int)
 }

```

如果信号中包含有空格，调用多个参数或参数[QMetaObject.normalizedSignature](qmetaobject.html#normalizedSignature)（ ）上的结果`SIGNAL()`宏。

**Warning:**此功能违反了模块化的面向对象的原则。但是，当您需要执行昂贵的初始化只有当事情被连接到一个信号它可能是有用的。

**See also** [connect](qobject.html#connect)（）和[disconnectNotify](qobject.html#disconnectNotify)（ ） 。

```
QObject.customEvent (self, QEvent)
```

此事件处理程序可以重新实现在子类中以接收自定义事件。自定义事件是与类型值至少一样大的用户定义事件[QEvent.User](qevent.html#Type-enum)的产品[QEvent.Type](qevent.html#Type-enum)枚举，并且是一个典型的[QEvent](qevent.html)子类。该事件被传递的_event_参数。

**See also** [event](qobject.html#event)（）和[QEvent](qevent.html)。

```
QObject.deleteLater (self)
```

这种方法也是一个Qt槽与C + +的签名`void deleteLater()`。

附表这个对象为删除。

该对象将被当控制返回到事件循环中删除。如果事件循环不运行时，这个函数被调用（例如deleteLater （ ）被调用某个对象之前[QCoreApplication.exec](qcoreapplication.html#exec)（）） ，当事件循环被启动的对象都将被删除。如果deleteLater （ ）被调用后，主事件循环已经停止，对象不会被删除。由于Qt的4.8 ，如果deleteLater （ ）被调用的对象生活在一个线程没有正在运行的事件循环时，对象将在线程结束时销毁。

需要注意的是进入和离开一个新的事件循环（例如，通过打开一个模态对话框）会_not_执行延期删除，因为要删除的对象时，控件必须返回到事件循环从deleteLater （）被调用。

**Note:**它是安全的调用这个函数不止一次，当第一递延删除事件被交付，对于对象的任何挂起的事件从事件队列中删除。

**See also** [destroyed](qobject.html#destroyed)（）和[QPointer](index.htm)。

```
bool QObject.disconnect (QObject, SIGNAL(), QObject, SLOT())
```

断开连接_signal_在对象_sender_从_method_在对象_receiver_。返回True如果连接成功打破，否则返回False 。

时，无论所涉及的对象被销毁被删除的信号 - 槽连接。

断开（ ）通常用于三种方式，如下面的示例演示。

1.  断开所有连接到一个对象的信号：

    ```
     disconnect(myObject, 0, 0, 0);

    ```

    相当于非静态重载函数

    ```
     myObject-&gt;disconnect();

    ```

2.  断开所有连接到特定的信号：

    ```
     disconnect(myObject, SIGNAL(mySignal()), 0, 0);

    ```

    相当于非静态重载函数

    ```
     myObject-&gt;disconnect(SIGNAL(mySignal()));

    ```

3.  断开一个特定的接收器：

    ```
     disconnect(myObject, 0, myReceiver, 0);

    ```

    相当于非静态重载函数

    ```
     myObject-&gt;disconnect(myReceiver);

    ```

0可以用作一个通配符，意思是“任何信号” ， “任何接收对象” ，或“接收对象中的任何槽” ，分别。

该_sender_可能永远不会为0。 （你不能从一个单一的呼叫多个对象断开信号。 ）

If _signal_为0时，断开_receiver_和_method_从任何信号。如果不是这样，只有指定的信号断开。

If _receiver_为0时，断开任何连接到_signal_。如果没有，插槽对象以外_receiver_没有断开。

If _method_为0时，它断开连接到任何_receiver_。如果没有，只是插槽命名_method_将被断开，而所有其他插槽单独留在家中。该_method_必须为0 ，如果_receiver_被冷落，所以你不能断开所有对象具体命名的插槽。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [connect](qobject.html#connect)（ ） 。

```
bool QObject.disconnect (QObject, SIGNAL(), callable)
```

断开连接_signal_在对象_sender_从_method_在对象_receiver_。返回True如果连接成功打破，否则返回False 。

此功能提供了像断开（常量相同的可能性[QObject](qobject.html)*发件人，为const char *的信号，常量[QObject](qobject.html)*接收器，为const char *法），但用途[QMetaMethod](qmetamethod.html)代表要被断开的信号，并且该方法。

此外，此功能returnsFalse ，无信号和槽断开，如果：

1.  _signal_是不是发件人类的成员或其父类之一。
2.  _method_是不是接收器类的成员或其父类之一。
3.  _signal_实例表示没有信号。

QMetaMethod （ ）可以被用作通配符的意思是“任何信号”或“接收对象中的任何槽” 。以同样的方式0可用于_receiver_中的含义是“任何接收对象” 。在这种情况下，方法也应该QMetaMethod （） 。_sender_参数应该是永远不为0 。

此功能被引入Qt的4.8 。

**See also**断开（常量的QObject *寄件人，为const char *的信号，常量的QObject *接收器，为const char *的方法） 。

```
QObject.disconnectNotify (self, SIGNAL() signal)
```

当事情已经断开从这个虚函数被调用_signal_在这个对象。

See [connectNotify](qobject.html#connectNotify)（ ）对于如何比较的例子_signal_与特定的信号。

**Warning:**此功能违反了模块化的面向对象的原则。但是，它可能是最优化使用昂贵的资源是有用的。

**See also** [disconnect](qobject.html#disconnect)（）和[connectNotify](qobject.html#connectNotify)（ ） 。

```
QObject.dumpObjectInfo (self)
```

转储有关信号连接信息等，为这个对象的调试输出。

此功能对于调试非常有用，但什么都不做，如果该库已经在释放模式编译（即没有调试信息） 。

**See also** [dumpObjectTree](qobject.html#dumpObjectTree)（ ） 。

```
QObject.dumpObjectTree (self)
```

儿童转储到调试输出的一棵树。

此功能对于调试非常有用，但什么都不做，如果该库已经在释放模式编译（即没有调试信息） 。

**See also** [dumpObjectInfo](qobject.html#dumpObjectInfo)（ ） 。

```
list-of-QByteArray QObject.dynamicPropertyNames (self)
```

返回所有属性，是使用动态添加到该对象的名称[setProperty](qobject.html#setProperty)（ ） 。

这个函数中引入了Qt 4.2中。

```
QObject.emit (self, SIGNAL(), ...)
```

```
bool QObject.event (self, QEvent)
```

这个虚函数接收事件的对象，应该返回True，如果事件_e_确认和处理。

本次活动（ ）函数可重新实现以自定义对象的行为。

**See also** [installEventFilter](qobject.html#installEventFilter)（ ）[timerEvent](qobject.html#timerEvent)（ ）[QApplication.sendEvent](qcoreapplication.html#sendEvent)（ ）[QApplication.postEvent](qcoreapplication.html#postEvent)（）和[QWidget.event](qwidget.html#event)（ ） 。

```
bool QObject.eventFilter (self, QObject, QEvent)
```

过滤器的事件，如果这个对象已经被安装为一个事件过滤器_watched_对象。

在你这个函数的重新实现，如果你要筛选的_event_出，正在进一步处理即停止，返回True ，否则返回False 。

例如：

```
 class MainWindow : public [QMainWindow](qmainwindow.html)
 {
 public:
     MainWindow();

 protected:
     bool eventFilter([QObject](qobject.html) *obj, [QEvent](qevent.html) *ev);

 private:
     [QTextEdit](qtextedit.html) *textEdit;
 };

 MainWindow.MainWindow()
 {
     textEdit = new [QTextEdit](qtextedit.html);
     setCentralWidget(textEdit);

     textEdit->installEventFilter(this);
 }

 bool MainWindow.eventFilter([QObject](qobject.html) *obj, [QEvent](qevent.html) *event)
 {
     if (obj == textEdit) {
         if (event->type() == [QEvent](qevent.html).KeyPress) {
             [QKeyEvent](qkeyevent.html) *keyEvent = static_cast<[QKeyEvent](qkeyevent.html)*>(event);
             qDebug() << "Ate key press" << keyEvent->key();
             return true;
         } else {
             return false;
         }
     } else {
         // pass the event on to the parent class
         return [QMainWindow](qmainwindow.html).eventFilter(obj, event);
     }
 }

```

在上面的未处理的事件为例通知传递给基类的eventFilter （ ）函数，因为基类有可能重新实现eventFilter （ ）为自己的内部目的。

**Warning:**如果您删除的接收器对象在这个函数中，一定要返回True 。否则，将Qt的事件转发到已删除对象，程序可能会崩溃。

**See also** [installEventFilter](qobject.html#installEventFilter)（ ） 。

```
QObject QObject.findChild (self, type type, QString name = QString())
```

返回此对象的子对象可以强制转换为类型T和那个叫_name_或0，如果不存在这样的对象。省略_name_参数会导致要匹配所有对象名称。搜索被递归执行。

如果有一个以上的孩子匹配搜索，返回最直接的祖先。如果有多个直系祖先，它是不确定哪一个将被退回。在这种情况下，[findChildren](qobject.html#findChildren)（ ）应该被使用。

此示例返回一个孩子[QPushButton](qpushbutton.html)的`parentWidget` named `"button1"`：

```
 [QPushButton](qpushbutton.html) *button = parentWidget->findChild<[QPushButton](qpushbutton.html) *>("button1");

```

此示例返回一个[QListWidget](qlistwidget.html)儿童`parentWidget`：

```
 [QListWidget](qlistwidget.html) *list = parentWidget->findChild<[QListWidget](qlistwidget.html) *>();

```

**See also** [findChildren](qobject.html#findChildren)（ ） 。

```
QObject QObject.findChild (self, tuple types, QString name = QString())
```

```
list-of-QObject QObject.findChildren (self, type type, QString name = QString())
```

返回此对象的所有子具有给定_name_可以强制转换为类型T，或者一个空列表，如果没有这样的对象。省略_name_参数会导致要匹配所有对象名称。搜索被递归执行。

下面的示例演示如何找到孩子的名单[QWidget](qwidget.html)指定的第`parentWidget` named `widgetname`：

```
 [QList](index.htm)<[QWidget](qwidget.html) *> widgets = parentWidget.findChildren<[QWidget](qwidget.html) *>("widgetname");

```

此示例返回所有`QPushButton`s表示是儿童`parentWidget`：

```
 [QList](index.htm)<[QPushButton](qpushbutton.html) *> allPButtons = parentWidget.findChildren<[QPushButton](qpushbutton.html) *>();

```

**See also** [findChild](qobject.html#findChild)（ ） 。

```
list-of-QObject QObject.findChildren (self, tuple types, QString name = QString())
```

这个函数的重载[findChildren](qobject.html#findChildren)（ ） 。

返回此对象的可强制转换为类型T和其名称匹配正则表达式的孩子_regExp_，或者一个空列表，如果没有这样的对象。搜索被递归执行。

```
list-of-QObject QObject.findChildren (self, type type, QRegExp regExp)
```

```
list-of-QObject QObject.findChildren (self, tuple types, QRegExp regExp)
```

```
bool QObject.inherits (self, str classname)
```

返回True如果这个对象是一个类继承的一个实例_className_或[QObject](qobject.html)子类继承_className_否则返回False 。

一类被认为是继承本身。

例如：

```
 [QTimer](qtimer.html) *timer = new [QTimer](qtimer.html);         // QTimer inherits QObject
 timer->inherits("QTimer");          // returns true
 timer->inherits("QObject");         // returns true
 timer->inherits("QAbstractButton"); // returns false

 // QVBoxLayout inherits QObject and QLayoutItem
 [QVBoxLayout](qvboxlayout.html) *layout = new [QVBoxLayout](qvboxlayout.html);
 layout->inherits("QObject");        // returns true
 layout->inherits("QLayoutItem");    // returns true (even though QLayoutItem is not a QObject)

```

如果您需要确定一个对象是否为铸造它的目的一个特定的类的实例，可以考虑使用qobject_cast \u003cType *\u003e （对象）来代替。

**See also** [metaObject](qobject.html#metaObject)（）和[qobject_cast](qobject.html#qobject_cast)（ ） 。

```
QObject.installEventFilter (self, QObject)
```

安装一个事件过滤器_filterObj_此对象上。例如：

```
 monitoredObj->installEventFilter(filterObj);

```

事件过滤器是接收发送到该对象的所有事件的对象。该过滤器可以阻止事件或将其转发到该对象。事件过滤器_filterObj_通过接收其事件[eventFilter](qobject.html#eventFilter)（）函数。该[eventFilter](qobject.html#eventFilter)（ ）函数必须返回True，如果该事件应该被过滤， （即停止） ，否则它必须返回False 。

如果有多个事件过滤器被安装在一个单独的对象，这是最后安装的过滤器将首先启动。

这里有一个`KeyPressEater`类，吃它的被监控对象的按键：

```
 class KeyPressEater : public [QObject](qobject.html)
 {
     Q_OBJECT
     ...

 protected:
     bool eventFilter([QObject](qobject.html) *obj, [QEvent](qevent.html) *event);
 };

 bool KeyPressEater.eventFilter([QObject](qobject.html) *obj, [QEvent](qevent.html) *event)
 {
     if (event->type() == [QEvent](qevent.html).KeyPress) {
         [QKeyEvent](qkeyevent.html) *keyEvent = static_cast<[QKeyEvent](qkeyevent.html) *>(event);
         qDebug("Ate key press %d", keyEvent->key());
         return true;
     } else {
         // standard event processing
         return [QObject](qobject.html).eventFilter(obj, event);
     }
 }

```

下面是如何在两个窗口小部件安装它：

```
 KeyPressEater *keyPressEater = new KeyPressEater(this);
 [QPushButton](qpushbutton.html) *pushButton = new [QPushButton](qpushbutton.html)(this);
 [QListView](qlistview.html) *listView = new [QListView](qlistview.html)(this);

 pushButton->installEventFilter(keyPressEater);
 listView->installEventFilter(keyPressEater);

```

该[QShortcut](qshortcut.html)类，例如，使用这种技术来截取快捷按键。

**Warning:**如果您删除的接收器对象中的[eventFilter](qobject.html#eventFilter)（ ）函数时，一定要返回True 。如果返回False ， Qt的发送事件到已删除对象，程序会崩溃。

需要注意的是过滤对象必须在同一个线程中此对象。如果_filterObj_是在不同的线程，这个函数不执行任何操作。如果任_filterObj_或对该对象的调用此函数后移动到一个不同的线程，事件过滤器不会被调用，直到两个对象又具有相同的线程关联（这是_not_删除）。

**See also** [removeEventFilter](qobject.html#removeEventFilter)（ ）[eventFilter](qobject.html#eventFilter)（）和[event](qobject.html#event)（ ） 。

```
bool QObject.isWidgetType (self)
```

返回True如果该对象是一个小部件，否则返回False 。

调用此函数相当于调用继承（ “[QWidget](qwidget.html)“ ） ，不同的是它的速度要快得多。

```
QObject.killTimer (self, int id)
```

杀死定时器，具有定时器标识符，_id_。

定时器标识符由返回[startTimer](qobject.html#startTimer)（ ）启动一个计时器事件时。

**See also** [timerEvent](qobject.html#timerEvent)（）和[startTimer](qobject.html#startTimer)（ ） 。

```
QMetaObject QObject.metaObject (self)
```

[

返回一个指向该对象的元对象。

](qmetaobject.html)

[一个元对象包含有关一个继承信息](qmetaobject.html)[QObject](qobject.html)如类名，父名，属性，信号和槽。一切[QObject](qobject.html)子类，它包含了[Q_OBJECT](qobject.html#Q_OBJECT)宏将有一个元对象。

元对象信息所必需的信号/插槽连接机制和产权制度。该[inherits](qobject.html#inherits)（ ）函数也使用的元对象。

如果你没有指向一个实际的对象实例，但仍希望访问类的元对象，你可以使用[staticMetaObject](qobject.html#staticMetaObject-var)。

例如：

```
 [QObject](qobject.html) *obj = new [QPushButton](qpushbutton.html);
 obj->metaObject()->className();             // returns "QPushButton"

 [QPushButton](qpushbutton.html).staticMetaObject.className();  // returns "QPushButton"

```

**See also** [staticMetaObject](qobject.html#staticMetaObject-var)。

```
QObject.moveToThread (self, QThread thread)
```

为改变此对象及其子对象的线程关联。如果它有一个父对象不能被移动。事件处理将继续在_targetThread_。

移动对象到主线程，使用[QApplication.instance](qcoreapplication.html#instance)（ ）来检索一个指向当前的应用程序，然后使用[QApplication.thread](qobject.html#thread)（ ）来检索应用程序在其中居住的线程。例如：

```
 myObject->moveToThread([QApplication](qapplication.html).instance()->thread());

```

If _targetThread_是零，此对象及其子所有的事件处理停止。

需要注意的是所有活动的定时器对象将被重置。该定时器在当前线程先停止并重新启动（以相同的时间间隔）中的_targetThread_。因此，不断移动的对象的线程之间可以无限期地推迟计时器事件。

A [QEvent.ThreadChange](qevent.html#Type-enum)事件被发送到该对象的线程关联被改变之前。您可以处理这个事件来执行任何特殊处理。需要注意的是投递到该对象的任何新的事件将在被处理_targetThread_。

**Warning:**这个功能是_not_线程安全的;当前线程必须是与当前线程关联。换句话说，这个函数可以仅“推”从当前线程到另一个线程一个对象，它不能从任意线程“拉”的对象到当前线程。

**See also** [thread](qobject.html#thread)（ ） 。

```
QString QObject.objectName (self)
```

```
QObject QObject.parent (self)
```

[

返回一个指向父对象。

](qobject.html)

[**See also**](qobject.html) [setParent](qobject.html#setParent)（）和[children](qobject.html#children)（ ） 。

```
QVariant QObject.property (self, str name)
```

返回该对象的值_name_属性。

如果没有这样的属性存在，则返回的变量是无效的。

有关所有可用属性的信息是通过提供[metaObject](qobject.html#metaObject)（）和[dynamicPropertyNames](qobject.html#dynamicPropertyNames)（ ） 。

**See also** [setProperty](qobject.html#setProperty)(), [QVariant.isValid](qvariant.html#isValid)(), [metaObject](qobject.html#metaObject)(), and [dynamicPropertyNames](qobject.html#dynamicPropertyNames)().

```
QObject.pyqtConfigure (self, object)
```

```
int QObject.receivers (self, SIGNAL() signal)
```

返回连接到所述接收器的数量_signal_。

因为这两个槽和信号可以被用作接收器的信号，并且在同一连接可以被多次提出，接收机的数目是一样的从该信号建立的连接的数量。

当调用这个函数，你可以使用`SIGNAL()`宏来传递一个特定的信号：

```
 if (receivers(SIGNAL(valueChanged([QByteArray](qbytearray.html)))) > 0) {
     [QByteArray](qbytearray.html) data;
     get_the_value(&data);       // expensive operation
     emit valueChanged(data);
 }

```

正如上面的代码片段所示，您可以使用此功能来避免发出一个信号，即没有人听。

**Warning:**此功能违反了模块化的面向对象的原则。但是，当您需要执行昂贵的初始化只有当事情被连接到一个信号它可能是有用的。

```
QObject.removeEventFilter (self, QObject)
```

删除事件过滤器对象_obj_从该对象。如果这样的事件过滤器尚未安装该请求将被忽略。

此对象的所有事件过滤器时，这个对象被销毁被自动删除。

它始终是安全的，从删除事件过滤器，即使在事件过滤器激活（即[eventFilter](qobject.html#eventFilter)（）函数） 。

**See also** [installEventFilter](qobject.html#installEventFilter)（ ）[eventFilter](qobject.html#eventFilter)（）和[event](qobject.html#event)（ ） 。

```
QObject QObject.sender (self)
```

[

返回一个指针，指向发送的信号，如果调用了一个信号激活一个插槽中的对象，否则返回0 。仅在从该对象的线程上下文中调用这个函数插槽的执行指针是有效的。

这个函数返回的指针变为无效，如果发件人被破坏，或者如果插槽是从发件人的信号断开。

**Warning:**此功能违反了模块化的面向对象的原则。然而，当许多信号被连接到一个单一的时隙获得访问发件人可能是有用的。

](qobject.html)

[**Warning:**如上所述，该函数的返回值不是有效的，当槽是通过一个称为](qobject.html)[Qt.DirectConnection](qt.html#ConnectionType-enum)从一个线程从该对象的线程不同。不要在这种情形下使用该功能。

**See also** [senderSignalIndex](qobject.html#senderSignalIndex)（）和[QSignalMapper](qsignalmapper.html)。

```
int QObject.senderSignalIndex (self)
```

返回调用当前正在执行的插槽中的信号，这是由返回的类的一个成员的元方法指数[sender](qobject.html#sender)（ ） 。如果由一个信号激活的插槽外调用，则返回-1。

对于使用默认参数信号，该功能将始终返回索引的所有参数，无论哪个与使用[connect](qobject.html#connect)（ ） 。例如，信号`destroyed(QObject *obj = 0)`将有两个不同的索引（使用和不使用参数） ，但这个函数将总是用参数返回的索引。使用不同的参数重载信号时，这并不适用。

**Warning:**此功能违反了模块化的面向对象的原则。然而，当许多信号被连接到一个单一的时隙获得访问信号索引可能是有用的。

**Warning:**这个函数的返回值不是有效的，当槽通过一个名为[Qt.DirectConnection](qt.html#ConnectionType-enum)从一个线程从该对象的线程不同。不要在这种情形下使用该功能。

此功能被引入Qt的4.8 。

**See also** [sender](qobject.html#sender)（ ）[QMetaObject.indexOfSignal](qmetaobject.html#indexOfSignal)（）和[QMetaObject.method](qmetaobject.html#method)（ ） 。

```
QObject.setObjectName (self, QString name)
```

```
QObject.setParent (self, QObject)
```

该_QObject_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

使对象的子_parent_。

**See also** [parent](qobject.html#parent)（）和[QWidget.setParent](qwidget.html#setParent)（ ） 。

```
bool QObject.setProperty (self, str name, QVariant value)
```

设置对象的值_name_属性为_value_。

如果该属性在类使用Q_PROPERTY定义，那么真正的成功，否则为False返回。如果属性不使用Q_PROPERTY定义，因此在元对象不在列表中，它被添加为一个动态属性并返回False 。

有关所有可用属性的信息是通过提供[metaObject](qobject.html#metaObject)（）和[dynamicPropertyNames](qobject.html#dynamicPropertyNames)（ ） 。

动态属性可以再次使用查询[property](qobject.html#property)（） ，并且可以通过将属性值设置为无效去除[QVariant](qvariant.html)。更改动态属性的值将导致[QDynamicPropertyChangeEvent](qdynamicpropertychangeevent.html)要发送到的对象。

**Note:**以“ _q_ ”动态属性是供内部使用保留的。

**See also** [property](qobject.html#property)（ ）[metaObject](qobject.html#metaObject)（）和[dynamicPropertyNames](qobject.html#dynamicPropertyNames)（ ） 。

```
bool QObject.signalsBlocked (self)
```

如果返回的信号被阻断True，否则返回False 。

信号不默认情况下阻止。

**See also** [blockSignals](qobject.html#blockSignals)（ ） 。

```
int QObject.startTimer (self, int interval)
```

启动一个定时器，并返回一个定时器标识符，或返回零，如果它不能启动一个定时器。

定时器事件会发生一次_interval_直到毫秒[killTimer](qobject.html#killTimer)（）被调用。如果_interval_是0，那么该定时事件，每次有没有更多的窗口系统事件来处理发生一次。

虚拟[timerEvent](qobject.html#timerEvent)（ ）函数被调用，[QTimerEvent](qtimerevent.html)当计时器事件发生的事件参数类。重新实现这个函数来获取计时器事件。

如果多个定时器在运行，[QTimerEvent.timerId](qtimerevent.html#timerId)（ ）可以用来找出哪些定时器被激活。

例如：

```
 class MyObject : public [QObject](qobject.html)
 {
     Q_OBJECT

 public:
     MyObject([QObject](qobject.html) *parent = 0);

 protected:
     void timerEvent([QTimerEvent](qtimerevent.html) *event);
 };

 MyObject.MyObject([QObject](qobject.html) *parent)
     : [QObject](qobject.html)(parent)
 {
     startTimer(50);     // 50-millisecond timer
     startTimer(1000);   // 1-second timer
     startTimer(60000);  // 1-minute timer
 }

 void MyObject.timerEvent([QTimerEvent](qtimerevent.html) *event)
 {
     qDebug() << "Timer ID:" << event->timerId();
 }

```

需要注意的是[QTimer](qtimer.html)的精度依赖于底层的操作系统和硬件。大多数平台支持20毫秒的精度，有的提供更多。如果Qt是无法提供的定时器事件的请求数量，它会悄悄地丢弃一些。

该[QTimer](qtimer.html)类提供了一个高层次的编程接口与单次定时器和定时信号，而不是事件。还有一个[QBasicTimer](qbasictimer.html)类是比更轻巧[QTimer](qtimer.html)而不是直接使用定时器的ID少笨拙。

**See also** [timerEvent](qobject.html#timerEvent)（ ）[killTimer](qobject.html#killTimer)（）和[QTimer.singleShot](qtimer.html#singleShot)（ ） 。

```
QThread QObject.thread (self)
```

[

返回该对象所居住的线程。

](qthread.html)

[**See also**](qthread.html) [moveToThread](qobject.html#moveToThread)（ ） 。

```
QObject.timerEvent (self, QTimerEvent)
```

此事件处理程序可以重新实现在子类来接收定时器事件的对象。

[QTimer](qtimer.html)提供了一个更高层次的接口，定时器功能，也关于定时器的更多的一般信息。计时器事件被传递的_event_参数。

**See also** [startTimer](qobject.html#startTimer)（ ）[killTimer](qobject.html#killTimer)（）和[event](qobject.html#event)（ ） 。

```
QString QObject.tr (self, str sourceText, str disambiguation = None, int n = -1)
```

返回的翻译版本_sourceText_任选地基于一个_disambiguation_字符串和值_n_包含复数字符串，否则返回_sourceText_本身如果没有合适的翻译的字符串是可用的。

例如：

```
 void MainWindow.createMenus()
 {
     fileMenu = menuBar()->addMenu(tr("&File"));
     ...

```

如果同一_sourceText_同一范围内采用的是不同的角色，一个额外的标识字符串可以被传递_disambiguation_（默认为0 ） 。在Qt 4.4和更早的版本，这是通过注释来翻译的首选方式。

例如：

```
 MyWindow.MyWindow()
 {
     [QLabel](qlabel.html) *senderLabel = new [QLabel](qlabel.html)(tr("Name:"));
     [QLabel](qlabel.html) *recipientLabel = new [QLabel](qlabel.html)(tr("Name:", "recipient"));
     ...

```

See [Writing Source Code for Translation](index.htm)对于Qt的翻译机制在一般情况下，并详细描述了[Disambiguation](index.htm#disambiguation)节，以消除歧义的信息。

**Warning:**这种方法是可重入只有在安装了所有的翻译_before_调用此方法。但不支持进行翻译安装或删除翻译。这样做可能会造成崩溃或者其他不良行为。

**See also** [trUtf8](qobject.html#trUtf8)（ ）[QApplication.translate](qcoreapplication.html#translate)（ ）[QTextCodec.setCodecForTr](qtextcodec.html#setCodecForTr)（）和[Internationalization with Qt](index.htm)。

```
QString QObject.trUtf8 (self, str sourceText, str disambiguation = None, int n = -1)
```

返回的翻译版本_sourceText_，或QString.fromUtf8 （_sourceText_） ，如果没有适当的版本。它在其它方面与TR （_sourceText_，_disambiguation_，_n_） 。

请注意，使用的翻译功能utf8的变种是不是如果需要的话`CODECFORTR`已被设置为UTF -8在qmake的项目文件和QTextCodec.setCodecForTr （ “UTF - 8” ）被使用。

**Warning:**这种方法是可重入只有在安装了所有的翻译_before_调用此方法。但不支持进行翻译安装或删除翻译。这样做可能会造成崩溃或者其他不良行为。

**Warning:**对于便携性的原因，我们建议您使用转义序列在字符串中指定非ASCII字符trUtf8 （ ） 。例如：

```
 label->setText(tr("F\374r \310lise"));

```

**See also** [tr](qobject.html#tr)（ ）[QApplication.translate](qcoreapplication.html#translate)（）和[Internationalization with Qt](index.htm)。

```
object QObject.__getattr__ (self, str name)
```

* * *

## Qt Signal Documentation

```
void destroyed (QObject * = 0)
```

这是该信号的默认超载。

这个信号的对象之前立即发出_obj_被破坏，并且不能被阻塞。

所有对象的孩子被立即销毁后，这个信号被发射。

**See also** [deleteLater](qobject.html#deleteLater)（）和[QPointer](index.htm)。

* * *

## Member Documentation

```
QMetaObject staticMetaObject
```

[

此构件应被视为常数。

这个变量存储的元对象的类。

](qmetaobject.html)

[一个元对象包含有关一个继承信息](qmetaobject.html)[QObject](qobject.html)如类名，父名，属性，信号和槽。包含每个类的[Q_OBJECT](qobject.html#Q_OBJECT)宏也将有一个元对象。

元对象信息所必需的信号/插槽连接机制和产权制度。该[inherits](qobject.html#inherits)（ ）函数也使用的元对象。

如果你有一个指向对象的指针，你可以使用[metaObject](qobject.html#metaObject)（）检索与该对象关联的元对象。

例如：

```
 [QPushButton](qpushbutton.html).staticMetaObject.className();  // returns "QPushButton"

 [QObject](qobject.html) *obj = new [QPushButton](qpushbutton.html);
 obj->metaObject()->className();             // returns "QPushButton"

```

**See also** [metaObject](qobject.html#metaObject)（ ） 。