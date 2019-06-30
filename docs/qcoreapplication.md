# QCoreApplication Class Reference

## [[QtCore](index.htm) module]

该QCoreApplication类提供一个事件循环控制台Qt应用程序。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QApplication](qapplication.html)。

### Types

*   `enum Encoding { CodecForTr, UnicodeUTF8, DefaultCodec }`

### Methods

*   `__init__ (self, list-of-str argv)`
*   `bool event (self, QEvent)`
*   `bool notify (self, QObject, QEvent)`

### Static Methods

*   `addLibraryPath (QString)`
*   `QString applicationDirPath ()`
*   `QString applicationFilePath ()`
*   `QString applicationName ()`
*   `int applicationPid ()`
*   `QString applicationVersion ()`
*   `int argc ()`
*   `QStringList arguments ()`
*   `list-of-str argv ()`
*   `bool closingDown ()`
*   `int exec_ ()`
*   `exit (int returnCode = 0)`
*   `flush ()`
*   `bool hasPendingEvents ()`
*   `installTranslator (QTranslator)`
*   `QCoreApplication instance ()`
*   `QStringList libraryPaths ()`
*   `QString organizationDomain ()`
*   `QString organizationName ()`
*   `postEvent (QObject receiver, QEvent event)`
*   `postEvent (QObject receiver, QEvent event, int priority)`
*   `processEvents (QEventLoop.ProcessEventsFlags flags = QEventLoop.AllEvents)`
*   `processEvents (QEventLoop.ProcessEventsFlags flags, int maxtime)`
*   `quit ()`
*   `removeLibraryPath (QString)`
*   `removePostedEvents (QObject receiver)`
*   `removePostedEvents (QObject receiver, int eventType)`
*   `removeTranslator (QTranslator)`
*   `bool sendEvent (QObject receiver, QEvent event)`
*   `sendPostedEvents (QObject receiver, int event_type)`
*   `sendPostedEvents ()`
*   `setApplicationName (QString application)`
*   `setApplicationVersion (QString version)`
*   `setAttribute (Qt.ApplicationAttribute attribute, bool on = True)`
*   `setLibraryPaths (QStringList)`
*   `setOrganizationDomain (QString orgDomain)`
*   `setOrganizationName (QString orgName)`
*   `bool startingUp ()`
*   `bool testAttribute (Qt.ApplicationAttribute attribute)`
*   `QString translate (str context, str sourceText, str disambiguation = None, Encoding encoding = QCoreApplication.CodecForTr)`
*   `QString translate (str context, str sourceText, str disambiguation, Encoding encoding, int n)`

### Qt Signals

*   `void aboutToQuit ()`

* * *

## Detailed Description

该QCoreApplication类提供一个事件循环控制台Qt应用程序。

这个类用于非GUI应用程序提供自己的事件循环。对于使用Qt的非GUI的应用程序，应该有只有一个QCoreApplication对象。对于GUI应用程序，请参见[QApplication](qapplication.html)。

QCoreApplication包含主事件循环，其中从操作系统（如定时器和网络事件）和其他来源的所有事件被处理和调度。它也处理应用程序的初始化和结束，以及系统级和应用程序级设置。

### The Event Loop and Event Handling

事件循环的开始调用[exec_](qcoreapplication.html#exec)（ ） 。长时间运行的操作可以调用[processEvents](qcoreapplication.html#processEvents)（ ），以保持应用程序的响应。

一般情况下，我们建议您创建一个QCoreApplication或[QApplication](qapplication.html)在你的对象`main()`功能尽可能早。[exec_](qcoreapplication.html#exec)（ ）将不会返回，直到事件循环退出，比如，当[quit](qcoreapplication.html#quit)（）被调用。

还提供了一些静态的便利功能。该QCoreApplication对象可从[instance](qcoreapplication.html#instance)（ ） 。事件可以使用发送或张贴[sendEvent](qcoreapplication.html#sendEvent)（ ）[postEvent](qcoreapplication.html#postEvent)（）和[sendPostedEvents](qcoreapplication.html#sendPostedEvents)（ ） 。待处理的事件可以以去除[removePostedEvents](qcoreapplication.html#removePostedEvents)（）或冲洗[flush](qcoreapplication.html#flush)（ ） 。

这个类提供了一个[quit](qcoreapplication.html#quit)（ ）插槽和一个[aboutToQuit](qcoreapplication.html#aboutToQuit)（）信号。

### Application and Library Paths

一个应用程序有一个[applicationDirPath](qcoreapplication.html#applicationDirPath)（）和一个[applicationFilePath](qcoreapplication.html#applicationFilePath)（ ） 。库路径（见[QLibrary](qlibrary.html)）可以检索与[libraryPaths](qcoreapplication.html#libraryPaths)（）和通过操纵[setLibraryPaths](qcoreapplication.html#setLibraryPaths)（ ）[addLibraryPath](qcoreapplication.html#addLibraryPath)（）和[removeLibraryPath](qcoreapplication.html#removeLibraryPath)（ ） 。

### Internationalization and Translations

翻译文件，可以添加或删除使用[installTranslator](qcoreapplication.html#installTranslator)（）和[removeTranslator](qcoreapplication.html#removeTranslator)（ ） 。应用程序的字符串可以使用翻译[translate](qcoreapplication.html#translate)（ ） 。该[QObject.tr](qobject.html#tr)（）和[QObject.trUtf8](qobject.html#trUtf8)（ ）函数在以下方面实施[translate](qcoreapplication.html#translate)（ ） 。

### Accessing Command Line Arguments

这是传递给QCoreApplication的构造函数中的命令行参数，应使用被访问的[arguments](qcoreapplication.html#arguments)（）函数。注意，由用户提供某些参数可能已经被处理并通过QCoreApplication除去。

在情况下，命令行参数需要使用估计可得的[argv](index.htm#argv)（ ）函数，则必须使用本地字符串编码将它们转换[QString.fromLocal8Bit](qstring.html#fromLocal8Bit)（ ） 。

### Locale Settings

在Unix / Linux上的Qt配置默认使用系统区域设置。这可以使用时， POSIX函数，例如，数据类型，如浮点数和字符串之间进行转换时引起冲突，因为符号的语言环境可能有所不同。为了解决这个问题，调用POSIX函数`setlocale(LC_NUMERIC,"C")`初始化之后[QApplication](qapplication.html)或QCoreApplication重置，用于数字格式为“C”语言环境的语言环境。

* * *

## Type Documentation

```
QCoreApplication.Encoding
```

这个枚举类型定义的字符串参数的8位编码[translate](qcoreapplication.html#translate)（）：

| Constant | Value | Description |
| --- | --- | --- |
| `QCoreApplication.CodecForTr` | `0` | 由指定的编码[QTextCodec.codecForTr](qtextcodec.html#codecForTr)（ ） （ Latin-1的，如果没有设置） 。 |
| `QCoreApplication.UnicodeUTF8` | `1` | UTF - 8 。 |
| `QCoreApplication.DefaultCodec` | `CodecForTr` | （过时）使用CodecForTr代替。 |

**See also** [QObject.tr](qobject.html#tr)（ ）[QObject.trUtf8](qobject.html#trUtf8)（）和[QString.fromUtf8](qstring.html#fromUtf8)（ ） 。

* * *

## Method Documentation

```
QCoreApplication.__init__ (self, list-of-str argv)
```

构造一个内核的Qt应用程序。核心应用是没有图形用户界面应用程序。这些类型的应用程序用于在控制台或服务器进程。

该_argc_和_argv_参数由应用程序进行处理，并通过在一个更方便的形式提供[arguments](qcoreapplication.html#arguments)（）函数。

**Warning:**由所述资料_argc_和_argv_必须保持有效的整个生命周期[QCoreApplication](qcoreapplication.html)对象。另外，_argc_必须大于零和_argv_必须至少包含一个有效的字符串。

```
QCoreApplication.addLibraryPath (QString)
```

预先考虑_path_到库路径列表，以确保它是搜索库首的开始。如果_path_是空的，或者已经在路径列表中的路径列表中不被改变。

默认路径列表包含一个条目，用于插件的安装目录。对于插件的默认安装目录为`INSTALL/plugins`，其中`INSTALL`在这里安装Qt的目录。

在Symbian此功能仅适用于添加路径查找Qt的扩展插件存根有用的，因为从操作系统只能加载库`/sys/bin`目录。

**See also** [removeLibraryPath](qcoreapplication.html#removeLibraryPath)（ ）[libraryPaths](qcoreapplication.html#libraryPaths)（）和[setLibraryPaths](qcoreapplication.html#setLibraryPaths)（ ） 。

```
QString QCoreApplication.applicationDirPath ()
```

返回包含应用程序的可执行文件的目录。

例如，如果您在安装的Qt`C:\Trolltech\Qt`目录，并运行`regexp`例如，此函数将返回“C :/奇趣/ QT /例子/工具/正则表达式” 。

在Mac OS X ，这将指向实际上包含可执行文件的目录，这可能是一个应用程序包（如果应用程序捆绑）内。

**Warning:**在Linux上，此功能将尝试从一开始的路径`/proc`文件系统。如果失败，它假定`argv[0]`包含可执行文件的绝对文件名。该功能还假定当前目录没有被应用程序修改。

在Symbian这个函数将返回该应用程序私有目录，而不是路径到可执行文件本身，那些总是在`/sys/bin`。如果应用程序是在一个只读驱动器，即光盘，然后在系统驱动器上的专用路径将被退回。

**See also** [applicationFilePath](qcoreapplication.html#applicationFilePath)（ ） 。

```
QString QCoreApplication.applicationFilePath ()
```

返回应用程序的可执行文件的文件路径。

例如，如果您在安装的Qt`/usr/local/qt`目录，并运行`regexp`例如，此函数将返回“的/ usr /本地/ QT /例子/工具/正则表达式/正则表达式” 。

**Warning:**在Linux上，此功能将尝试从一开始的路径`/proc`文件系统。如果失败，它假定`argv[0]`包含可执行文件的绝对文件名。该功能还假定当前目录没有被应用程序修改。

**See also** [applicationDirPath](qcoreapplication.html#applicationDirPath)（ ） 。

```
QString QCoreApplication.applicationName ()
```

```
int QCoreApplication.applicationPid ()
```

返回当前进程的ID为应用。

此功能被引入Qt的4.4 。

```
QString QCoreApplication.applicationVersion ()
```

```
int QCoreApplication.argc ()
```

```
QStringList QCoreApplication.arguments ()
```

返回的命令行参数列表。

通常参数（ ），在（ 0 ）是程序名称，参数（ ），在（ 1）的第一个参数，并且参数（ ） ，最后（ ）是最后一个参数。见下面的注释关于Windows 。

调用此函数是缓慢的 - 你应该在解析命令行的时候将结果存储在变量中。

**Warning:**在Unix中，这个名单是从传递给构造函数在main（ ）函数的argc和argv参数建成。 argv中的字符串数据是使用解释[QString.fromLocal8Bit](qstring.html#fromLocal8Bit)（ ） ，因此它是不可能通过，例如，日本的命令行参数运行在拉丁文的语言环境的系统上。大多数现代的Unix系统没有这个限制，因为它们是基于Unicode的。

在基于NT的Windows中，这一限制并不适用于任。在Windows中， （）的参数不是从ARGV / ARGC的内容建成，作为内容不支持Unicode 。相反， （）的参数是从的返回值构造[GetCommandLine()](http://msdn2.microsoft.com/en-us/library/ms683156(VS.85).aspx)。作为这样的结果， ）由参数（给定的字符串。在（0）可能没有在Windows程序名称，这取决于应用程序的启动方式。

对于Symbian应用程序开始`RApaLsSession.StartApp`可以使用指定的参数`CApaCommandLine.SetTailEndL`功能。这种论调只能通过这种方法，他们将不会被传递到`main`功能。另外请注意，与只设置8位字符串数据`CApaCommandLine.SetTailEndL`此函数支持。

这个函数是Qt 4.1中引入。

**See also** [applicationFilePath](qcoreapplication.html#applicationFilePath)（ ） 。

```
list-of-str QCoreApplication.argv ()
```

```
bool QCoreApplication.closingDown ()
```

返回如果应用程序对象被销毁True，否则返回False 。

**See also** [startingUp](qcoreapplication.html#startingUp)（ ） 。

```
bool QCoreApplication.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QCoreApplication.exec_ ()
```

进入主事件循环并等待，直到[exit](qcoreapplication.html#exit)（）被调用。返回被设置为值[exit](qcoreapplication.html#exit)（）（它是0，如果[exit](qcoreapplication.html#exit)（ ）通过调用[quit](qcoreapplication.html#quit)（））。

有必要调用这个函数来启动事件处理。主事件循环接收事件从窗口系统并调度这些应用程序的部件。

为了使您的应用程序执行閒置处理（即执行一个特殊的功能，每当有没有挂起的事件） ，请使用[QTimer](qtimer.html)与0超时。更高级的空閒处理方案可以用来实现[processEvents](qcoreapplication.html#processEvents)（ ） 。

我们建议您清理代码连接到[aboutToQuit()](qcoreapplication.html#aboutToQuit)信号，而不是把它在你的应用程序，`main()`函数，因为在某些平台上的QCoreApplication.exec （ ）调用可能不会返回。例如，在Windows上，当用户注销时，系统终止进程的Qt关闭所有顶层窗口之后。因此，也不能保证该应用程序将有时间退出事件循环，并执行代码的结束`main()`该QCoreApplication.exec （ ）调用后的功能。

**See also** [quit](qcoreapplication.html#quit)（ ）[exit](qcoreapplication.html#exit)（ ）[processEvents](qcoreapplication.html#processEvents)（）和[QApplication.exec](qapplication.html#exec)（ ） 。

```
QCoreApplication.exit (int returnCode = 0)
```

告诉应用程序退出，并返回代码。

在此之后函数被调用，应用程序离开主事件循环，并从调用返回[exec_](qcoreapplication.html#exec)（ ） 。该[exec_](qcoreapplication.html#exec)（ ）函数返回_returnCode_。如果事件循环没有运行，这个函数不执行任何操作。

按照惯例，_returnCode_0意味着成功，而任何非零值表示错误。

请注意，与同名的C库函数，这个函数_does_返回给调用者 - 它是事件处理，停止。

**See also** [quit](qcoreapplication.html#quit)（）和[exec_](qcoreapplication.html#exec)（ ） 。

```
QCoreApplication.flush ()
```

刷新特定于平台的事件队列。

如果你正在做一个循环中的图形的变化，不返回到异步窗口系统，例如X11或者双缓冲窗口系统，例如Mac OS X中的事件循环，并要立即显现这些变化（如闪屏） ，调用这个函数。

**See also** [sendPostedEvents](qcoreapplication.html#sendPostedEvents)（ ） 。

```
bool QCoreApplication.hasPendingEvents ()
```

如果有未完成的事件这个函数返回True，否则返回False 。挂起的事件可以是从窗口系统或使用posted事件[postEvent](qcoreapplication.html#postEvent)（ ） 。

**See also** [QAbstractEventDispatcher.hasPendingEvents](qabstracteventdispatcher.html#hasPendingEvents)（ ） 。

```
QCoreApplication.installTranslator (QTranslator)
```

添加翻译文件_translationFile_到的翻译文件以用于翻译的列表。

多重翻译文件安装即可。翻译是在它们被安装在其相反的顺序搜索的，所以最近安装的翻译文件首先搜索并安装了第一个翻译文件最后搜索。搜索一旦被发现包含匹配的字符串翻译停止。

安装或拆卸[QTranslator](qtranslator.html)或改变已安装的[QTranslator](qtranslator.html)生成一个[LanguageChange](qevent.html#Type-enum)事件为[QCoreApplication](qcoreapplication.html)实例。一[QApplication](qapplication.html)例如将传播事件给所有顶层窗口，其中changeEvent中的一个重新实现可以通过通过通过用户可见的字符串重新翻译的用户界面[tr](qobject.html#tr)（ ）函数将相应的属性setter方法​​。通过生成用户界面的类[Qt Designer](index.htm#qt-designer)提供`retranslateUi()`函数可以被调用。

**See also** [removeTranslator](qcoreapplication.html#removeTranslator)（ ）[translate](qcoreapplication.html#translate)（ ）[QTranslator.load](qtranslator.html#load)（）和[Dynamic Translation](index.htm#dynamic-translation)。

```
QCoreApplication QCoreApplication.instance ()
```

[](qcoreapplication.html)

[返回一个指向应用程序的](qcoreapplication.html)[QCoreApplication](qcoreapplication.html)（或[QApplication](qapplication.html)）实例。

如果没有实例已分配，`null`返回。

```
QStringList QCoreApplication.libraryPaths ()
```

返回该应用程序将搜索时动态加载库的路径列表。

Qt提供了默认的库路径，但它们也可以使用设置[qt.conf](index.htm)文件中。在该文件中指定的路径将复盖默认值。

如果存在的话（对于插件的默认安装目录是这份名单将包括插件的安装目录`INSTALL/plugins`，其中`INSTALL`在这里安装Qt的目录） 。该应用程序的可执行文件（而不是工作目录）的目录总是被添加，以及冒号分隔的QT_PLUGIN_PATH环境变量的条目。

如果你想遍历列表中，您可以使用[foreach](index.htm#foreach)伪关键字：

```
 foreach (const [QString](qstring.html) &path, app.libraryPaths())
     do_something(path);

```

**See also** [setLibraryPaths](qcoreapplication.html#setLibraryPaths)（ ）[addLibraryPath](qcoreapplication.html#addLibraryPath)（ ）[removeLibraryPath](qcoreapplication.html#removeLibraryPath)（ ）[QLibrary](qlibrary.html)和[How to Create Qt Plugins](index.htm)。

```
bool QCoreApplication.notify (self, QObject, QEvent)
```

发送_event_至_receiver_：_receiver_ - \u003e事件（_event_） 。返回从接收器的事件处理程序中返回的值。注意，该函数用于在任何线程中发送到任何对象的所有事件。

对于某些类型的事件（例如鼠标和键盘事件） ，事件将被传播到接收器的父，所以一直到顶层对象，如果接收器是不感兴趣的事件（即，它返回False ） 。

有迹象表明，事件可以被处理五种不同的方法;重新实现该虚拟函数只是其中之一。所有五个途径如下：

1.  重新实现的paintEvent （） ， mousePressEvent （）等等。这是最常见，最简单，最有力的方式。
2.  重新实现此功能。这是非常强大，提供了完整的控制，但只有一个子类可以同时处于活动状态。
3.  上安装一个事件过滤器[QCoreApplication.instance](qcoreapplication.html#instance)（ ） 。这样的事件过滤器能够处理所有部件的所有事件，所以它只是一样强大的重新实现notify（）方法，此外，它可能有一个以上的应用程序全局事件过滤器。全局事件过滤器甚至可以看到鼠标事件[disabled widgets](qwidget.html#enabled-prop)。请注意，应用程序事件过滤器只要求居住在主线程中的对象。
4.  重新实现[QObject.event](qobject.html#event)（ ） （如[QWidget](qwidget.html)一样） 。如果你这样做你会得到Tab键按下，你会得到之前的任何部件特定的事件筛选器查看的事件。
5.  在对象上安装事件过滤器。这样的事件过滤器得到所有的活动，包括Tab键和Shift + Tab键的按键事件，只要他们不改变的重点部件。

**See also** [QObject.event](qobject.html#event)（）和[installEventFilter](qobject.html#installEventFilter)（ ） 。

```
QString QCoreApplication.organizationDomain ()
```

```
QString QCoreApplication.organizationName ()
```

```
QCoreApplication.postEvent (QObject receiver, QEvent event)
```

该_event_说法有它的所有权转移给Qt的。

添加事件_event_，与对象_receiver_作为该事件的接收器，立刻事件队列并返回。

该事件必须被分配在堆上，因为后期的事件队列会借此事件的所有权，并删除它一旦被发布。这是_not safe_访问事件已张贴后。

当控制返回到主事件循环，存储在队列中的所有事件将要使用的发送[notify](qcoreapplication.html#notify)（）函数。

事件在张贴的顺序处理。为了更好地控制处理顺序，使用下面的postEvent （）重载，它接受一个优先级参数。这个函数的职位的所有事件与[Qt.NormalEventPriority](qt.html#EventPriority-enum)。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [sendEvent](qcoreapplication.html#sendEvent)（ ）[notify](qcoreapplication.html#notify)（）和[sendPostedEvents](qcoreapplication.html#sendPostedEvents)（ ） 。

```
QCoreApplication.postEvent (QObject receiver, QEvent event, int priority)
```

该_event_说法有它的所有权转移给Qt的。

这个函数的重载[postEvent](qcoreapplication.html#postEvent)（ ） 。

添加事件_event_，与对象_receiver_作为该事件的接收器，立刻事件队列并返回。

该事件必须被分配在堆上，因为后期的事件队列会借此事件的所有权，并删除它一旦被发布。这是_not safe_访问事件已张贴后。

当控制返回到主事件循环，存储在队列中的所有事件将要使用的发送[notify](qcoreapplication.html#notify)（）函数。

活动按降序_priority_秩序，即事件的高_priority_具有较低的事件之前排队_priority_。该_priority_可以是任意整数值，即INT_MAX和INT_MIN （含）之间，见[Qt.EventPriority](qt.html#EventPriority-enum)更多的细节。以同样的活动_priority_将发布的顺序进行处理。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

此功能被引入Qt的4.3 。

**See also** [sendEvent](qcoreapplication.html#sendEvent)（ ）[notify](qcoreapplication.html#notify)（ ）[sendPostedEvents](qcoreapplication.html#sendPostedEvents)（）和[Qt.EventPriority](qt.html#EventPriority-enum)。

```
QCoreApplication.processEvents (QEventLoop.ProcessEventsFlags flags = QEventLoop.AllEvents)
```

流程根据指定的调用线程的所有等待事件_flags_直到有没有更多的事件来处理。

你可以偶尔调用此函数时，你的程序是忙于执行一个长时间的操作（例如，复制文件） 。

在事件中，你正在运行一个本地环路的不断调用这个函数，没有一个事件循环，[DeferredDelete](qevent.html#Type-enum)事件将不会被处理。这可能会影响部件的性能，例如[QToolTip](qtooltip.html)，依赖于[DeferredDelete](qevent.html#Type-enum)事件才能正常工作。另一种方法是调用[sendPostedEvents()](qcoreapplication.html#sendPostedEvents)从内本地环路。

调用此功能仅适用于调用线程处理事件。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [exec_](qcoreapplication.html#exec)（ ）[QTimer](qtimer.html)，[QEventLoop.processEvents](qeventloop.html#processEvents)（ ）[flush](qcoreapplication.html#flush)（）和[sendPostedEvents](qcoreapplication.html#sendPostedEvents)（ ） 。

```
QCoreApplication.processEvents (QEventLoop.ProcessEventsFlags flags, int maxtime)
```

这个函数的重载[processEvents](qcoreapplication.html#processEvents)（ ） 。

为调用线程的进程挂起的事件_maxtime_毫秒，直到没有更多的事件来处理，以较短者为准。

你可以偶尔调用此函数时，你的程序是忙着做一个长时间的操作（例如，复制文件） 。

调用此功能仅适用于调用线程处理事件。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [exec_](qcoreapplication.html#exec)（ ）[QTimer](qtimer.html)和[QEventLoop.processEvents](qeventloop.html#processEvents)（ ） 。

```
QCoreApplication.quit ()
```

这种方法也是一个Qt槽与C + +的签名`void quit()`。

告诉应用程序退出，返回代码为0（成功） 。等效于调用QCoreApplication.exit （ 0 ） 。

这是常见的连接[QApplication.lastWindowClosed](qapplication.html#lastWindowClosed)（ ）信号退出（ ） ，你也经常连接如[QAbstractButton.clicked](qabstractbutton.html#clicked)（）或信号[QAction](qaction.html)，[QMenu](qmenu.html)或[QMenuBar](qmenubar.html)到它。

例如：

```
 [QPushButton](qpushbutton.html) *quitButton = new [QPushButton](qpushbutton.html)("Quit");
 connect(quitButton, SIGNAL(clicked()), &app, SLOT(quit()));

```

**See also** [exit](qcoreapplication.html#exit)（ ）[aboutToQuit](qcoreapplication.html#aboutToQuit)（）和[QApplication.lastWindowClosed](qapplication.html#lastWindowClosed)（ ） 。

```
QCoreApplication.removeLibraryPath (QString)
```

移除_path_从库路径列表。如果_path_为空或不是路径列表中，该列表不会改变。

**See also** [addLibraryPath](qcoreapplication.html#addLibraryPath)（ ）[libraryPaths](qcoreapplication.html#libraryPaths)（）和[setLibraryPaths](qcoreapplication.html#setLibraryPaths)（ ） 。

```
QCoreApplication.removePostedEvents (QObject receiver)
```

删除所有的事件发表使用[postEvent](qcoreapplication.html#postEvent)（ ）为_receiver_。

该事件是_not_出动，而是被从队列中删除。你不应该需要调用这个函数。如果你调用它，要知道，杀事件可能造成_receiver_打破一个或多个变量。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

```
QCoreApplication.removePostedEvents (QObject receiver, int eventType)
```

这个函数的重载[removePostedEvents](qcoreapplication.html#removePostedEvents)（ ） 。

删除给定的所有事件_eventType_这是用贴[postEvent](qcoreapplication.html#postEvent)（ ）为_receiver_。

该事件是_not_出动，而是被从队列中删除。你不应该需要调用这个函数。如果你调用它，要知道，杀事件可能造成_receiver_打破一个或多个变量。

If _receiver_为null ，发生的事件_eventType_被删除的所有对象。如果_eventType_为0 ，所有的事件都将被删除_receiver_。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

此功能被引入Qt的4.3 。

```
QCoreApplication.removeTranslator (QTranslator)
```

删除的文件翻译_translationFile_从该应用程序使用翻译文件的列表。 （它不会从文件系统中删除翻译文件。 ）

**See also** [installTranslator](qcoreapplication.html#installTranslator)（ ）[translate](qcoreapplication.html#translate)（）和[QObject.tr](qobject.html#tr)（ ） 。

```
bool QCoreApplication.sendEvent (QObject receiver, QEvent event)
```

发送事件_event_直接到接收器_receiver_使用[notify](qcoreapplication.html#notify)（）函数。返回从事件处理程序返回的值。

本次活动是_not_当事件已发送删除。正常的方法是创建事件的堆栈，例如：

```
 [QMouseEvent](qmouseevent.html) event([QEvent](qevent.html).MouseButtonPress, pos, 0, 0, 0);
 [QApplication](qapplication.html).sendEvent(mainWindow, &event);

```

**See also** [postEvent](qcoreapplication.html#postEvent)（）和[notify](qcoreapplication.html#notify)（ ） 。

```
QCoreApplication.sendPostedEvents (QObject receiver, int event_type)
```

立即调度已与以前排队的所有事件[QCoreApplication.postEvent](qcoreapplication.html#postEvent)（）和它们的对象_receiver_和具有事件类型_event_type_。

从窗口系统事件_not_通过此功能布控，而是由[processEvents](qcoreapplication.html#processEvents)（ ） 。

If _receiver_为null ，发生的事件_event_type_被发送的所有对象。如果_event_type_是0 ，所有的事件都被发送给_receiver_。

**Note:**此方法必须从同一个线程中调用它[QObject](qobject.html)参数，_receiver_。

**See also** [flush](qcoreapplication.html#flush)（）和[postEvent](qcoreapplication.html#postEvent)（ ） 。

```
QCoreApplication.sendPostedEvents ()
```

这个函数的重载[sendPostedEvents](qcoreapplication.html#sendPostedEvents)（ ） 。

调度所有的posted事件，即清空事件队列。

```
QCoreApplication.setApplicationName (QString application)
```

```
QCoreApplication.setApplicationVersion (QString version)
```

```
QCoreApplication.setAttribute (Qt.ApplicationAttribute attribute, bool on = True)
```

设置属性_attribute_如果_on_为True，否则清除该属性。

之一，可以用这种方法来设置的属性是[Qt.AA_ImmediateWidgetCreation](qt.html#ApplicationAttribute-enum)。它告诉Qt立即创建顶层窗口。通常情况下，对于小部件的资源按需分配，提高效率，减少资源的使用。因此，如果要最大限度地减少资源消耗是很重要的，不要设置此属性。

**See also** [testAttribute](qcoreapplication.html#testAttribute)（ ） 。

```
QCoreApplication.setLibraryPaths (QStringList)
```

设置目录列表加载库时要搜索_paths_。所有现有的路径将被删除，路径列表将包含在给定路径_paths_。

在Symbian此功能仅用于设置路径查找Qt的扩展插件存根有用的，因为从操作系统只能加载库`/sys/bin`目录。

**See also** [libraryPaths](qcoreapplication.html#libraryPaths)（ ）[addLibraryPath](qcoreapplication.html#addLibraryPath)（ ）[removeLibraryPath](qcoreapplication.html#removeLibraryPath)（）和[QLibrary](qlibrary.html)。

```
QCoreApplication.setOrganizationDomain (QString orgDomain)
```

```
QCoreApplication.setOrganizationName (QString orgName)
```

```
bool QCoreApplication.startingUp ()
```

如果一个应用程序对象尚未创建，则返回True ，否则返回False 。

**See also** [closingDown](qcoreapplication.html#closingDown)().

```
bool QCoreApplication.testAttribute (Qt.ApplicationAttribute attribute)
```

返回True ，如果属性_attribute_被置位，否则返回False 。

**See also** [setAttribute](qcoreapplication.html#setAttribute)（ ） 。

```
QString QCoreApplication.translate (str context, str sourceText, str disambiguation = None, Encoding encoding = QCoreApplication.CodecForTr)
```

返回翻译文本_sourceText_，通过查询已安装的翻译文件。翻译文件中搜索从最近安装的文件恢复到第一次安装文件。

[QObject.tr](qobject.html#tr)（）和[QObject.trUtf8](qobject.html#trUtf8)（ ）更方便地提供了这种功能。

_context_通常是一个类名称（例如，“程序MyDialog ” ）和_sourceText_要么是英文的文字或短识别文字。

_disambiguation_是一个识别字符串，当相同的_sourceText_采用的是同一个范围内不同的角色。默认情况下，它是空的。

请参阅[QTranslator](qtranslator.html)和[QObject.tr](qobject.html#tr)（ ）文档以了解有关背景， disambiguations和注释的详细信息。

_encoding_表示字符串的8位编码。

_n_用于与结合`%n`支持复数形式。看[QObject.tr](qobject.html#tr)（ ）了解详情。

如果没有翻译文件中包含了翻译_sourceText_在_context_，这个函数返回一个[QString](qstring.html)相当于_sourceText_。的编码_sourceText_通过指定_encoding_它默认为[CodecForTr](qcoreapplication.html#Encoding-enum)。

这个函数是不是虚拟的。你可以通过继承使用其他翻译技巧[QTranslator](qtranslator.html)。

**Warning:**这种方法是可重入只有在安装了所有的翻译_before_调用此方法。但不支持进行翻译安装或删除翻译。这样做很可能会导致崩溃或其他不良行为。

**Note:**这个功能是[reentrant](index.htm#reentrant)。

此功能被引入Qt的4.5 。

**See also** [QObject.tr](qobject.html#tr)（ ）[installTranslator](qcoreapplication.html#installTranslator)（）和[QTextCodec.codecForTr](qtextcodec.html#codecForTr)（ ） 。

```
QString QCoreApplication.translate (str context, str sourceText, str disambiguation, Encoding encoding, int n)
```

这个函数的重载[translate](qcoreapplication.html#translate)（ ） 。

* * *

## Qt Signal Documentation

```
void aboutToQuit ()
```

这是该信号的默认超载。

当应用程序即将退出主事件循环，比如这个信号被发射当事件循环水平下降到零。要么在调用这可能发生[quit](qcoreapplication.html#quit)（ ）从内部的应用程序，或当用户关闭整个桌面会话。

如果你的应用程序需要做一些最后一秒清理的信号特别有用。请注意，没有用户交互可能处于这种状态。

**See also** [quit](qcoreapplication.html#quit)（ ） 。