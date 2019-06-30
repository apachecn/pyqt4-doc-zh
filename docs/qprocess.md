# QProcess Class Reference

## [[QtCore](index.htm) module]

使用QProcess类，用来启动外部程序，并与他们沟通。[More...](#details)

继承[QIODevice](qiodevice.html)。

### Types

*   `enum ExitStatus { NormalExit, CrashExit }`
*   `enum ProcessChannel { StandardOutput, StandardError }`
*   `enum ProcessChannelMode { SeparateChannels, MergedChannels, ForwardedChannels }`
*   `enum ProcessError { FailedToStart, Crashed, Timedout, ReadError, WriteError, UnknownError }`
*   `enum ProcessState { NotRunning, Starting, Running }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool atEnd (self)`
*   `int bytesAvailable (self)`
*   `int bytesToWrite (self)`
*   `bool canReadLine (self)`
*   `close (self)`
*   `closeReadChannel (self, ProcessChannel channel)`
*   `closeWriteChannel (self)`
*   `QStringList environment (self)`
*   `ProcessError error (self)`
*   `int exitCode (self)`
*   `ExitStatus exitStatus (self)`
*   `bool isSequential (self)`
*   `kill (self)`
*   `int pid (self)`
*   `ProcessChannelMode processChannelMode (self)`
*   `QProcessEnvironment processEnvironment (self)`
*   `QByteArray readAllStandardError (self)`
*   `QByteArray readAllStandardOutput (self)`
*   `ProcessChannel readChannel (self)`
*   `ProcessChannelMode readChannelMode (self)`
*   `str readData (self, int maxlen)`
*   `setEnvironment (self, QStringList environment)`
*   `setProcessChannelMode (self, ProcessChannelMode mode)`
*   `setProcessEnvironment (self, QProcessEnvironment environment)`
*   `setProcessState (self, ProcessState state)`
*   `setReadChannel (self, ProcessChannel channel)`
*   `setReadChannelMode (self, ProcessChannelMode mode)`
*   `setStandardErrorFile (self, QString fileName, QIODevice.OpenMode mode = QIODevice.Truncate)`
*   `setStandardInputFile (self, QString fileName)`
*   `setStandardOutputFile (self, QString fileName, QIODevice.OpenMode mode = QIODevice.Truncate)`
*   `setStandardOutputProcess (self, QProcess destination)`
*   `setupChildProcess (self)`
*   `setWorkingDirectory (self, QString dir)`
*   `start (self, QString program, QStringList arguments, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `start (self, QString program, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `ProcessState state (self)`
*   `terminate (self)`
*   `bool waitForBytesWritten (self, int msecs = 30000)`
*   `bool waitForFinished (self, int msecs = 30000)`
*   `bool waitForReadyRead (self, int msecs = 30000)`
*   `bool waitForStarted (self, int msecs = 30000)`
*   `QString workingDirectory (self)`
*   `int writeData (self, str data)`

### Static Methods

*   `int execute (QString program, QStringList arguments)`
*   `int execute (QString program)`
*   `(bool, int pid) startDetached (QString program, QStringList arguments, QString workingDirectory)`
*   `bool startDetached (QString program, QStringList arguments)`
*   `bool startDetached (QString program)`
*   `QStringList systemEnvironment ()`

### Qt Signals

*   `void error (QProcess::ProcessError)`
*   `void finished (int,QProcess::ExitStatus)`
*   `void finished (int)`
*   `void readyReadStandardError ()`
*   `void readyReadStandardOutput ()`
*   `void started ()`
*   `void stateChanged (QProcess::ProcessState)`

* * *

## Detailed Description

使用QProcess类，用来启动外部程序，并与他们沟通。

### Running a Process

要启动一个过程，传递你想要作为参数来运行程序的名称和命令行参数[start](qprocess.html#start)（ ） 。参数被作为一个单独的字符串[QStringList](qstringlist.html)。

例如，下面的代码片段使含有“风格”和“主题”中的参数列表中两个项目的字符串运行在X11平台上的Motif风格的模拟时钟的例子：

```
     [QObject](qobject.html) *parent;
     ...
     [QString](qstring.html) program = "./path/to/Qt/examples/widgets/analogclock";
     [QStringList](qstringlist.html) arguments;
     arguments << "-style" << "motif";

     QProcess *myProcess = new QProcess(parent);
     myProcess->start(program, arguments);

```

另外，QProcess然后进入[Starting](qprocess.html#ProcessState-enum)状态，当程序已经启动，另外，QProcess进入[Running](qprocess.html#ProcessState-enum)状态并发出[started](qprocess.html#started)（ ） 。

另外，QProcess允许你把一个进程顺序I / O设备。你可以写信给从进程读取，就像您使用访问网络连接[QTcpSocket](qtcpsocket.html)。然后，您可以通过调用写入进程的标准输入[write](qiodevice.html#write)（ ） ，并通过调用读取标准输出[read](qiodevice.html#read)（ ）[readLine](qiodevice.html#readLine)（）和[getChar](qiodevice.html#getChar)（ ） 。因为它继承[QIODevice](qiodevice.html)，另外，QProcess也可以被用作输入源[QXmlReader](qxmlreader.html)或者，用于产生数据，以使用被上传[QFtp](qftp.html)。

**Note:**在VxWorks中， Windows CE和Symbian的，读取和写入的过程是不支持。

当进程退出，另外，QProcess重新进入[NotRunning](qprocess.html#ProcessState-enum)状态（初始状态） ，并且发射[finished](qprocess.html#finished)（ ） 。

该[finished](qprocess.html#finished)（ ）信号提供了退出代码和过程作为参数退出状态，您也可以致电[exitCode](qprocess.html#exitCode)（）来获取完成的最后一个进程的退出代码，[exitStatus](qprocess.html#exitStatus)（）来获取它的退出状态。如果发生在任何时间点的误差，另外，QProcess将发出的[error](qprocess.html#error)（）信号。您也可以拨打[error](qprocess.html#error)（）找到最后发生的错误的类型，[state](qprocess.html#state)（）找到当前进程的状态。

### Communicating via Channels

流程有两个预定义的输出通道：标准输出通道（`stdout`）定期提供控制台输出，标准错误通道（`stderr`）通常提供了由印刷过程中的错误。这些通道代表两个独立的数据流。你可以通过调用它们之间进行切换[setReadChannel](qprocess.html#setReadChannel)（ ） 。另外，QProcess发出[readyRead](qiodevice.html#readyRead)（ ）时，数据可在当前的读通道。它还发出[readyReadStandardOutput](qprocess.html#readyReadStandardOutput)（）时，新的标准输出数据是可用的，并且当新的标准误差数据是可用的，[readyReadStandardError](qprocess.html#readyReadStandardError)（）被发射。而不是调用[read](qiodevice.html#read)（ ）[readLine](qiodevice.html#readLine)（） ，或[getChar](qiodevice.html#getChar)（ ） ，您也可以通过调用读取无论是从两个通道的所有数据[readAllStandardOutput](qprocess.html#readAllStandardOutput)（）或[readAllStandardError](qprocess.html#readAllStandardError)（ ） 。

该术语的渠道可能会产生误导。请注意，该过程的输出通道对应QProcess中的_read_通道，而这个过程的输入通道对应QProcess中的_write_频道。这是因为我们阅读使用QProcess中什么是过程的输出，而我们写什么成为过程的输入。

另外，QProcess可以合并两个输出通道，使标准输出，并从运行中的进程的标准误差数据两者都使用标准的输出通道。通话[setProcessChannelMode](qprocess.html#setProcessChannelMode)（ ）与[MergedChannels](qprocess.html#ProcessChannelMode-enum)在开始之前，过程中activative此功能。你还可以在转发运行过程的输出到调用，主处理的选项，通过使[ForwardedChannels](qprocess.html#ProcessChannelMode-enum)作为参数。

某些过程中为了操作需要特殊环境设置。你可以通过调用设置环境变量为你的进程[setEnvironment](qprocess.html#setEnvironment)（ ） 。要设置一个工作目录，呼叫[setWorkingDirectory](qprocess.html#setWorkingDirectory)（ ） 。默认情况下，进程在调用进程的当前工作目录运行。

**Note:**在VxWorks中，通过渠道与进程进行通信，不支持。

**Note:**在Symbian ，设置环境或工作目录是不支持。该工作目录将永远是正在运行的进程的私有目录。

**Note:**QNX的，设置工作目录可能会导致所有应用程序线程，除了使用QProcess调用者线程的，暂时冻结，由于在操作系统的限制。

### Synchronous Process API

另外，QProcess提供了一组功能，允许它被用于没有一个事件循环，通过挂起调用线程，直到某个信号发出：

*   [waitForStarted](qprocess.html#waitForStarted)() blocks until the process has started.
*   [waitForReadyRead](qprocess.html#waitForReadyRead)() blocks until new data is available for reading on the current read channel.
*   [waitForBytesWritten](qprocess.html#waitForBytesWritten)() blocks until one payload of data has been written to the process.
*   [waitForFinished](qprocess.html#waitForFinished)() blocks until the process has finished.

从主线程（即调用线程调用这些函数[QApplication.exec](qapplication.html#exec)（ ） ）可能会导致你的用户界面冻结。

下面的示例运行`gzip`压缩字符串“ Qt的岩石！ ”无事件循环：

```
     QProcess gzip;
     gzip.start("gzip", [QStringList](qstringlist.html)() << "-c");
     if (!gzip.waitForStarted())
         return false;

     gzip.write("Qt rocks!");
     gzip.closeWriteChannel();

     if (!gzip.waitForFinished())
         return false;

     [QByteArray](qbytearray.html) result = gzip.readAll();

```

### Notes for Windows Users

有些Windows的命令（例如，`dir`）不提供单独的应用程序，而由命令解释程序本身。如果您尝试使用QProcess中直接执行这些命令，它不会工作。一个可能的解决方案是要执行的命令解释器本身（`cmd.exe`在某些Windows系统） ，并要求执行所需的命令解释器。

### Notes for VxWorks Users

另外，QProcess支持仅适用于RTP模式，并且只提供了有限的功能。当使用QProcess中启动Qt应用程序，启动的应用程序都必须有下面的代码：

* * *

## Type Documentation

```
QProcess.ExitStatus
```

这个枚举变量描述了不同的退出状态[QProcess](qprocess.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QProcess.NormalExit` | `0` | 这个过程正常退出。 |
| `QProcess.CrashExit` | `1` | 该进程崩溃。 |

**See also** [exitStatus](qprocess.html#exitStatus)（ ） 。

```
QProcess.ProcessChannel
```

该枚举描述了所使用的运行过程中的工艺通道。通过这些值之一[setReadChannel](qprocess.html#setReadChannel)（）设定的当前的读通道[QProcess](qprocess.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QProcess.StandardOutput` | `0` | 正在运行的进程的标准输出（stdout ） 。 |
| `QProcess.StandardError` | `1` | 正在运行的进程的标准错误（错误） 。 |

**See also** [setReadChannel](qprocess.html#setReadChannel)（ ） 。

```
QProcess.ProcessChannelMode
```

这个枚举变量描述的过程通道模式[QProcess](qprocess.html)。通过这些值之一[setProcessChannelMode](qprocess.html#setProcessChannelMode)（ ）来设置当前的读通道模式。

| Constant | Value | Description |
| --- | --- | --- |
| `QProcess.SeparateChannels` | `0` | [QProcess](qprocess.html)管理正在运行的进程的输出，保持标准输出和标准错误的数据在单独的内部缓冲区。您可以选择[QProcess](qprocess.html)通过调用目前的读取通道[setReadChannel](qprocess.html#setReadChannel)（ ） 。这是缺省信道模式[QProcess](qprocess.html)。 |
| `QProcess.MergedChannels` | `1` | [QProcess](qprocess.html)合并运行过程中的输出到标准输出通道（`stdout`） 。标准错误通道（`stderr`）将不会收到任何数据。标准输出和正在运行的进程的标准错误数据交错。 |
| `QProcess.ForwardedChannels` | `2` | [QProcess](qprocess.html)运行过程中的转发到主处理的输出。任何事物的子进程写入其标准输出和标准错误将被写入标准输出和标准错误的主要过程。 |

**See also** [setProcessChannelMode](qprocess.html#setProcessChannelMode)（ ） 。

```
QProcess.ProcessError
```

这个枚举变量描述了不同类型的错误报告由[QProcess](qprocess.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QProcess.FailedToStart` | `0` | 该进程无法启动。无论是调用的程序丢失，或者您可能没有足够的权限来调用该程序。 |
| `QProcess.Crashed` | `1` | 该工艺成功地坠毁后，开始一段时间。 |
| `QProcess.Timedout` | `2` | 最后WAITFOR ... （ ）函数超时。状态[QProcess](qprocess.html)是不变的，你可以尝试调用WAITFOR ... （ ）一次。 |
| `QProcess.WriteError` | `4` | 试图写入过程时发生错误。例如，该过程可能未运行，或者它可能已经关闭了其输入通道。 |
| `QProcess.ReadError` | `3` | 试图从进程读取时发生错误。例如，程序可能无法运行。 |
| `QProcess.UnknownError` | `5` | 发生未知错误。这是默认的返回值[error](qprocess.html#error)（ ） 。 |

**See also** [error](qprocess.html#error)（ ） 。

```
QProcess.ProcessState
```

该枚举描述的不同状态[QProcess](qprocess.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QProcess.NotRunning` | `0` | 该进程不运行。 |
| `QProcess.Starting` | `1` | 该过程开始，但该程序尚未被调用。 |
| `QProcess.Running` | `2` | 该进程正在运行，并已准备好进行读取和写入。 |

**See also** [state](qprocess.html#state)（ ） 。

* * *

## Method Documentation

```
QProcess.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QProcess](qprocess.html)与给定对象_parent_。

```
bool QProcess.atEnd (self)
```

从重新实现[QIODevice.atEnd](qiodevice.html#atEnd)（ ） 。

返回True如果进程不运行，并没有更多的数据可供读取，否则返回False 。

```
int QProcess.bytesAvailable (self)
```

从重新实现[QIODevice.bytesAvailable](qiodevice.html#bytesAvailable)（ ） 。

```
int QProcess.bytesToWrite (self)
```

从重新实现[QIODevice.bytesToWrite](qiodevice.html#bytesToWrite)（ ） 。

```
bool QProcess.canReadLine (self)
```

从重新实现[QIODevice.canReadLine](qiodevice.html#canReadLine)（ ） 。

此功能可在当前的读通道。

**See also** [readChannel](qprocess.html#readChannel)（）和[setReadChannel](qprocess.html#setReadChannel)（ ） 。

```
QProcess.close (self)
```

从重新实现[QIODevice.close](qiodevice.html#close)（ ） 。

关闭所有与沟通的过程中，并杀死它。调用此函数后，[QProcess](qprocess.html)将不再放出[readyRead](qiodevice.html#readyRead)（）和数据无法再被读取或写入。

```
QProcess.closeReadChannel (self, ProcessChannel channel)
```

关闭读取通道_channel_。调用此函数后，[QProcess](qprocess.html)将不再接收该通道上的数据。已接收到的任何数据仍然可以读取。

调用这个函数来节省内存，如果你不感兴趣，这个过程的输出。

**See also** [closeWriteChannel](qprocess.html#closeWriteChannel)（）和[setReadChannel](qprocess.html#setReadChannel)（ ） 。

```
QProcess.closeWriteChannel (self)
```

附表的写通道[QProcess](qprocess.html)被关闭。所有数据已被写入的过程中的信道将关闭一次。调用该函数后，任何试图写入过程将失败。

关闭写通道是必要的读取输入数据，直到该通道已被关闭的程序。例如，程序“更”是用来在Unix和Windows控制台显示文本数据。但它不会显示文本数据，直到[QProcess](qprocess.html)' s的写入通道已经关闭。例如：

```
 [QProcess](qprocess.html) more;
 more.start("more");
 more.write("Text to display");
 more.closeWriteChannel();
 // QProcess will emit readyRead() once "more" starts printing

```

写通道被隐含地打开时[start](qprocess.html#start)（）被调用。

**See also** [closeReadChannel](qprocess.html#closeReadChannel)（ ） 。

```
QStringList QProcess.environment (self)
```

此功能已被弃用。

返回环境，[QProcess](qprocess.html)启动进程的时候，还是一个空将使用[QStringList](qstringlist.html)如果没有环境一直使用设置[setEnvironment](qprocess.html#setEnvironment)（）或setEnvironmentHash （） 。如果没有环境已被设置，则调用进程的环境将被使用。

**Note:**环境设置将被忽略在Windows CE和Symbian ，因为有一个环境的概念。

**See also** [processEnvironment](qprocess.html#processEnvironment)（ ）[setEnvironment](qprocess.html#setEnvironment)（）和[systemEnvironment](qprocess.html#systemEnvironment)（ ） 。

```
ProcessError QProcess.error (self)
```

[

返回上次发生错误的类型。

](qprocess.html#ProcessError-enum)

[**See also**](qprocess.html#ProcessError-enum) [state](qprocess.html#state)（ ） 。

```
int QProcess.execute (QString program, QStringList arguments)
```

启动程序_program_与参数_arguments_在一个新的进程，等待它完成，然后返回该进程的退出代码。新进程写入控制台的任何数据转发到调用进程。

环境和工作目录是从调用进程继承。

在Windows上，包含空格的参数被包装在引号中。

如果进程不能启动，则返回-2。如果进程崩溃，则返回-1。否则，将返回进程的退出代码。

```
int QProcess.execute (QString program)
```

这是一个重载函数。

启动程序_program_在一个新的进程。_program_是一个同时包含程序名和参数单个文本字符串。该参数由一个或多个空格隔开。

```
int QProcess.exitCode (self)
```

返回完成的最后一个进程的退出代码。

```
ExitStatus QProcess.exitStatus (self)
```

[

返回完成的最后一个进程的退出状态。

](qprocess.html#ExitStatus-enum)

[在Windows上，如果该进程是从另一个应用程序终止TerminateProcess （ ）这个函数仍然会返回](qprocess.html#ExitStatus-enum)[NormalExit](qprocess.html#ExitStatus-enum)除非退出代码小于0 。

这个函数是Qt 4.1中引入。

```
bool QProcess.isSequential (self)
```

从重新实现[QIODevice.isSequential](qiodevice.html#isSequential)（ ） 。

```
QProcess.kill (self)
```

这种方法也是一个Qt槽与C + +的签名`void kill()`。

杀死当前进程，使其立即退出。

在Windows上，杀（）使用TerminateProcess ，并在Unix和Mac OS X上， SIGKILL信号发送到进程。

在Symbian ，此功能需要平台的安全能力`PowerMgmt`。如果不存在，该过程将恐慌与KERN - EXEC 46 。

**Note:**杀死其他进程正在运行的进程通常会导致Symbian的恐慌，由于平台的安全性。

**See also** [Symbian Platform Security Requirements](index.htm)和[terminate](qprocess.html#terminate)（ ） 。

```
int QProcess.pid (self)
```

返回运行过程中本机进程标识符（如果可用） 。如果没有进程正在运行，则返回0 。

```
ProcessChannelMode QProcess.processChannelMode (self)
```

[](qprocess.html#ProcessChannelMode-enum)

[返回的渠道模式](qprocess.html#ProcessChannelMode-enum)[QProcess](qprocess.html)标准输出和标准错误通道。

这个函数中引入了Qt 4.2中。

**See also** [setProcessChannelMode](qprocess.html#setProcessChannelMode)（ ）[ProcessChannelMode](qprocess.html#ProcessChannelMode-enum)和[setReadChannel](qprocess.html#setReadChannel)（ ） 。

```
QProcessEnvironment QProcess.processEnvironment (self)
```

[](qprocessenvironment.html)

[返回环境，](qprocessenvironment.html)[QProcess](qprocess.html)将启动一个进程时，或一个空的对象，如果没有环境一直使用设置使用[setEnvironment](qprocess.html#setEnvironment)（）或[setProcessEnvironment](qprocess.html#setProcessEnvironment)（ ） 。如果没有环境已被设置，则调用进程的环境将被使用。

**Note:**环境设置将被忽略在Windows CE上，因为有一个环境的概念。

此功能被引入Qt的4.6 。

**See also** [setProcessEnvironment](qprocess.html#setProcessEnvironment)（ ）[setEnvironment](qprocess.html#setEnvironment)（）和[QProcessEnvironment.isEmpty](qprocessenvironment.html#isEmpty)（ ） 。

```
QByteArray QProcess.readAllStandardError (self)
```

[](qbytearray.html)

[不管当前的读通道，这个函数返回一个可用的所有数据处理的标准误差为](qbytearray.html)[QByteArray](qbytearray.html)。

**See also** [readyReadStandardError](qprocess.html#readyReadStandardError)（ ）[readAllStandardOutput](qprocess.html#readAllStandardOutput)（ ）[readChannel](qprocess.html#readChannel)（）和[setReadChannel](qprocess.html#setReadChannel)（ ） 。

```
QByteArray QProcess.readAllStandardOutput (self)
```

[](qbytearray.html)

[不管当前的读通道，这个函数返回一个可用的所有数据处理的标准输出作为](qbytearray.html)[QByteArray](qbytearray.html)。

**See also** [readyReadStandardOutput](qprocess.html#readyReadStandardOutput)（ ）[readAllStandardError](qprocess.html#readAllStandardError)（ ）[readChannel](qprocess.html#readChannel)（）和[setReadChannel](qprocess.html#setReadChannel)（ ） 。

```
ProcessChannel QProcess.readChannel (self)
```

[](qprocess.html#ProcessChannel-enum)

[返回的当前读取通道](qprocess.html#ProcessChannel-enum)[QProcess](qprocess.html)。

**See also** [setReadChannel](qprocess.html#setReadChannel)（ ） 。

```
ProcessChannelMode QProcess.readChannelMode (self)
```

[

```
str QProcess.readData (self, int maxlen)
```

](qprocess.html#ProcessChannelMode-enum)

[从重新实现](qprocess.html#ProcessChannelMode-enum)[QIODevice.readData](qiodevice.html#readData)（ ） 。

```
QProcess.setEnvironment (self, QStringList environment)
```

此功能已被弃用。

设置环境[QProcess](qprocess.html)启动进程的时候会用_environment_指定它由key = value对的列表。

例如，下面的代码添加`C:\\BIN`目录的可执行文件的路径列表（`PATHS`）在Windows上：

```
 [QProcess](qprocess.html) process;
 [QStringList](qstringlist.html) env = [QProcess](qprocess.html).systemEnvironment();
 env << "TMPDIR=C:\\MyApp\\temp"; // Add an environment variable
 env.replaceInStrings([QRegExp](qregexp.html)("^PATH=(.*)", [Qt](qt.html).CaseInsensitive), "PATH=\\1;C:\\Bin");
 process.setEnvironment(env);
 process.start("myapp");

```

**Note:**这个函数是比低效率[setProcessEnvironment](qprocess.html#setProcessEnvironment)（）函数。

**See also** [environment](qprocess.html#environment)（ ）[setProcessEnvironment](qprocess.html#setProcessEnvironment)（）和[systemEnvironment](qprocess.html#systemEnvironment)（ ） 。

```
QProcess.setProcessChannelMode (self, ProcessChannelMode mode)
```

设置的通道模式[QProcess](qprocess.html)标准输出和标准错误通道到_mode_规定。此模式将在下一次使用[start](qprocess.html#start)（）被调用。例如：

```
 [QProcess](qprocess.html) builder;
 builder.setProcessChannelMode([QProcess](qprocess.html).MergedChannels);
 builder.start("make", [QStringList](qstringlist.html)() << "-j2");

 if (!builder.waitForFinished())
     qDebug() << "Make failed:" << builder.errorString();
 else
     qDebug() << "Make output:" << builder.readAll();

```

这个函数中引入了Qt 4.2中。

**See also** [processChannelMode](qprocess.html#processChannelMode)（ ）[ProcessChannelMode](qprocess.html#ProcessChannelMode-enum)和[setReadChannel](qprocess.html#setReadChannel)（ ） 。

```
QProcess.setProcessEnvironment (self, QProcessEnvironment environment)
```

设置环境[QProcess](qprocess.html)启动进程的时候会用_environment_对象。

例如，下面的代码添加`C:\\BIN`目录的可执行文件的路径列表（`PATHS`）在Windows和套`TMPDIR`：

```
 [QProcess](qprocess.html) process;
 [QProcessEnvironment](qprocessenvironment.html) env = [QProcessEnvironment](qprocessenvironment.html).systemEnvironment();
 env.insert("TMPDIR", "C:\\MyApp\\temp"); // Add an environment variable
 env.insert("PATH", env.value("Path") + ";C:\\Bin");
 process.setProcessEnvironment(env);
 process.start("myapp");

```

请注意如何在Windows上，环境变量名称是区分大小写的。

此功能被引入Qt的4.6 。

**See also** [processEnvironment](qprocess.html#processEnvironment)（ ）[QProcessEnvironment.systemEnvironment](qprocessenvironment.html#systemEnvironment)（）和[setEnvironment](qprocess.html#setEnvironment)（ ） 。

```
QProcess.setProcessState (self, ProcessState state)
```

设置的当前状态[QProcess](qprocess.html)到_state_规定。

**See also** [state](qprocess.html#state)（ ） 。

```
QProcess.setReadChannel (self, ProcessChannel channel)
```

设置的当前读取通道[QProcess](qprocess.html)为给定的_channel_。当前输入信道是所使用的函数[read](qiodevice.html#read)（ ）[readAll](qiodevice.html#readAll)（ ）[readLine](qiodevice.html#readLine)（）和[getChar](qiodevice.html#getChar)（ ） 。这也决定了通道的触发[QProcess](qprocess.html) to emit [readyRead](qiodevice.html#readyRead)（ ） 。

**See also** [readChannel](qprocess.html#readChannel)（ ） 。

```
QProcess.setReadChannelMode (self, ProcessChannelMode mode)
```

```
QProcess.setStandardErrorFile (self, QString fileName, QIODevice.OpenMode mode = QIODevice.Truncate)
```

重定向进程的标准错误到文件_fileName_。当重定向到位，标准错误读取通道被关闭：使用从它读[read](qiodevice.html#read)（ ）总是会失败，因为意志[readAllStandardError](qprocess.html#readAllStandardError)（ ） 。该文件将被追加到，如果_mode_被追加，否则会被截断。

See [setStandardOutputFile](qprocess.html#setStandardOutputFile)（ ）有关如何打开该文件的详细信息。

注：如果[setProcessChannelMode](qprocess.html#setProcessChannelMode)（ ）被调用时的参数[QProcess.MergedChannels](qprocess.html#ProcessChannelMode-enum)时，此功能没有任何影响。

这个函数中引入了Qt 4.2中。

**See also** [setStandardInputFile](qprocess.html#setStandardInputFile)（ ）[setStandardOutputFile](qprocess.html#setStandardOutputFile)（）和[setStandardOutputProcess](qprocess.html#setStandardOutputProcess)（ ） 。

```
QProcess.setStandardInputFile (self, QString fileName)
```

重定向进程的标准输入到由指定的文件_fileName_。当输入重定向到位，[QProcess](qprocess.html)对象将在只读模式（调用[write](qiodevice.html#write)（ ）将导致错误）。

如果文件_fileName_此刻不存在[start](qprocess.html#start)（）被调用或者不可读，启动过程将失败。

调用setStandardInputFile （）之后的过程中已经开始没有任何效果。

这个函数中引入了Qt 4.2中。

**See also** [setStandardOutputFile](qprocess.html#setStandardOutputFile)（ ）[setStandardErrorFile](qprocess.html#setStandardErrorFile)（）和[setStandardOutputProcess](qprocess.html#setStandardOutputProcess)（ ） 。

```
QProcess.setStandardOutputFile (self, QString fileName, QIODevice.OpenMode mode = QIODevice.Truncate)
```

重定向进程的标准输出到文件_fileName_。当重定向到位，标准输出读取通道被关闭：使用从它读[read](qiodevice.html#read)（ ）总是会失败，因为意志[readAllStandardOutput](qprocess.html#readAllStandardOutput)（ ） 。

如果文件_fileName_此刻不存在[start](qprocess.html#start)（ ）被调用时，它会被创建。如果它不能被创建，起始将会失败。

如果该文件存在，并且_mode_ is [QIODevice.Truncate](qiodevice.html#OpenModeFlag-enum)，该文件将被截断。否则（如果_mode_ is [QIODevice.Append](qiodevice.html#OpenModeFlag-enum)） ，该文件将被追加到。

调用setStandardOutputFile （）之后的过程中已经开始没有任何效果。

这个函数中引入了Qt 4.2中。

**See also** [setStandardInputFile](qprocess.html#setStandardInputFile)（ ）[setStandardErrorFile](qprocess.html#setStandardErrorFile)（）和[setStandardOutputProcess](qprocess.html#setStandardOutputProcess)（ ） 。

```
QProcess.setStandardOutputProcess (self, QProcess destination)
```

管这个过程的标准输出流的_destination_进程的标准输入。

下面的shell命令：

```
 command1 | command2

```

可以完成与QProcesses用下面的代码：

```
 [QProcess](qprocess.html) process1;
 [QProcess](qprocess.html) process2;

 process1.setStandardOutputProcess(&process2);

 process1.start("command1");
 process2.start("command2");

```

这个函数中引入了Qt 4.2中。

```
QProcess.setupChildProcess (self)
```

这个函数被调用的子进程的上下文，即，经过之前的程序是在Unix或Mac OS X （执行_fork()_，但在此之前_execve()_） 。重新实现这个功能做的子进程的最后一分钟的初始化。例如：

```
 class SandboxProcess : public [QProcess](qprocess.html)
 {
     ...
  protected:
      void setupChildProcess();
     ...
 };

 void SandboxProcess.setupChildProcess()
 {
     // Drop all privileges in the child process, and enter
     // a chroot jail.
 #if defined Q_OS_UNIX
     .setgroups(0, 0);
     .chroot("/etc/safe");
     .chdir("/");
     .setgid(safeGid);
     .setuid(safeUid);
     .umask(0);
 #endif
 }

```

你不能从这个函数退出过程（通过调用exit （ ） ，例如） 。如果你需要在开始执行前停止程序，你的解决方法是发出[finished](qprocess.html#finished)（），然后调用exit （ ） 。

**Warning:**调用此函数由[QProcess](qprocess.html)在Unix和Mac OS X只。在Windows和QNX ，那就不叫。

```
QProcess.setWorkingDirectory (self, QString dir)
```

设置工作目录_dir_。[QProcess](qprocess.html)将启动此目录中的过程。默认行为是启动该进程在调用进程的工作目录。

**Note:**工作目录设置将被忽略在Symbian ，这个过程的私有目录被认为是其工作目录。

**Note:**QNX的，这可能导致所有应用程序线程暂时冻结。

**See also** [workingDirectory](qprocess.html#workingDirectory)（）和[start](qprocess.html#start)（ ） 。

```
QProcess.start (self, QString program, QStringList arguments, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

开始定_program_在一个新的进程，如果没有已经在运行，通过命令行参数中_arguments_。该[OpenMode](qiodevice.html#OpenModeFlag-enum)被设置为_mode_。

该[QProcess](qprocess.html)对象将立即进入启动状态。如果进程启动成功，[QProcess](qprocess.html)会发出[started](qprocess.html#started)（ ），否则，[error](qprocess.html#error)（）将被发射。如果[QProcess](qprocess.html)对象已在运行的过程中，一个警告可能会打印在控制台，而现有的程序将继续运行。

**Note:**过程是异步启动，这意味着[started](qprocess.html#started)（）和[error](qprocess.html#error)（ ）信号可能会被延迟。通话[waitForStarted](qprocess.html#waitForStarted)（ ），以确保这一进程已经开始（或无法启动），和这些信号已经发出。

**Note:**被执行的参数没有进一步分裂。

**Windows:**包含空格的参数被包装在引号中。

**See also** [pid](qprocess.html#pid)（ ）[started](qprocess.html#started)（）和[waitForStarted](qprocess.html#waitForStarted)（ ） 。

```
QProcess.start (self, QString program, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

这是一个重载函数。

启动程序_program_在一个新的进程，如果尚未运行。_program_是一个同时包含程序名和参数单个文本字符串。该参数由一个或多个空格隔开。例如：

```
 [QProcess](qprocess.html) process;
 process.start("del /s *.txt");
 // same as process.start("del", QStringList() << "/s" << "*.txt");
 ...

```

该_program_字符串也可以包含引号，以确保含有空格的参数是否正确提供给新的进程。例如：

```
 [QProcess](qprocess.html) process;
 process.start("dir \"My Documents\"");

```

如果[QProcess](qprocess.html)对象已在运行的过程中，一个警告可能会打印在控制台，而现有的程序将继续运行。

需要注意的是，在Windows上，报价需要既逃脱了，并引述。例如，上面的代码会以下面的方式被指定，以确保`"My Documents"`作为参数传递给`dir`可执行文件：

```
 [QProcess](qprocess.html) process;
 process.start("dir \"\"\"My Documents\"\"\"");

```

该[OpenMode](qiodevice.html#OpenModeFlag-enum)被设置为_mode_。

```
(bool, int pid) QProcess.startDetached (QString program, QStringList arguments, QString workingDirectory)
```

启动程序_program_与参数_arguments_在一个新的进程，并从分离它。成功时返回TRUE ，否则返回False 。如果调用进程退出，脱离的进程将继续生活。

需要注意的是包含空格的参数不传递到过程作为单独的参数。

**Unix:**在启动过程中会在它自己的会话中运行，并作为守护程序运行。

**Windows:**包含空格的参数被包装在引号中。在启动过程中会作为一个经常性的独立的进程中运行。

这一过程将在目录中开始_workingDirectory_。

**Note:**QNX的，这可能导致所有应用程序线程暂时冻结。

**Note:**VxWorks的，这将启动RTP过程中始终具有优先级设置为220 。

如果函数成功，则*_pid_被设定为启动的过程的进程标识符。

```
bool QProcess.startDetached (QString program, QStringList arguments)
```

启动程序_program_用给定的_arguments_在一个新的进程，并从分离它。成功时返回TRUE ，否则返回False 。如果调用进程退出，脱离的进程将继续生活。

**Note:**包含空格的参数没有被传递给进程作为独立参数。

**Unix:**在启动过程中会在它自己的会话中运行，并作为守护程序运行。

**Windows:**包含空格的参数被包装在引号中。在启动过程中会作为一个经常性的独立的进程中运行。

```
bool QProcess.startDetached (QString program)
```

这是一个重载函数。

启动程序_program_在一个新的进程。_program_是一个同时包含程序名和参数单个文本字符串。该参数由一个或多个空格隔开。

该_program_字符串也可以包含引号，以确保含有空格的参数是否正确提供给新的进程。

```
ProcessState QProcess.state (self)
```

[

返回该过程的当前状态。

](qprocess.html#ProcessState-enum)

[**See also**](qprocess.html#ProcessState-enum) [stateChanged](qprocess.html#stateChanged)（）和[error](qprocess.html#error)（ ） 。

```
QStringList QProcess.systemEnvironment ()
```

返回调用进程的环境为key = value对的列表。例如：

```
 [QStringList](qstringlist.html) environment = [QProcess](qprocess.html).systemEnvironment();
 // environment = {"PATH=/usr/bin:/usr/local/bin",
 //                "USER=greg", "HOME=/home/greg"}

```

这个函数不缓存系统环境。因此，有可能获得环境的更新版本，如果低级别的C库函数如`setenv`OT`putenv`已被调用。

但是请注意，重复调用此函数将重新创建的环境变量列表，这是一个不平凡的操作。

**Note:**为新的代码，它是推荐使用[QProcessEnvironment.systemEnvironment](qprocessenvironment.html#systemEnvironment)（ ）

这个函数是Qt 4.1中引入。

**See also** [QProcessEnvironment.systemEnvironment](qprocessenvironment.html#systemEnvironment)（ ）[environment](qprocess.html#environment)（）和[setEnvironment](qprocess.html#setEnvironment)（ ） 。

```
QProcess.terminate (self)
```

这种方法也是一个Qt槽与C + +的签名`void terminate()`。

试图终止进程。

这个过程可能不会退出作为调用这个函数（它被赋予机会提示用户输入任何未保存的文件等）的结果。

在Windows中，终止（ ）投递一个WM_CLOSE消息过程中的所有顶层窗口，然后在过程本身的主线程。在Unix和Mac OS X SIGTERM信号被发送。

在不运行一个事件循环，或者其事件循环不处理WM_CLOSE消息的Windows控制台应用程序，只能通过调用被终止[kill](qprocess.html#kill)（ ） 。

在Symbian ，此功能需要平台的安全能力`PowerMgmt`。如果不存在，该过程将恐慌与KERN - EXEC 46 。

**Note:**终止其他进程正在运行的进程通常会导致Symbian的恐慌，由于平台的安全性。

**See also** [Symbian Platform Security Requirements](index.htm)和[kill](qprocess.html#kill)（ ） 。

```
bool QProcess.waitForBytesWritten (self, int msecs = 30000)
```

从重新实现[QIODevice.waitForBytesWritten](qiodevice.html#waitForBytesWritten)（ ） 。

```
bool QProcess.waitForFinished (self, int msecs = 30000)
```

块，直到该进程已结束，[finished](qprocess.html#finished)（）信号已被发出，或直到_msecs_毫秒过去了。

返回True如果这个过程完成，否则返回False （如果操作超时，如果出现错误，或者如果这[QProcess](qprocess.html)已经完成） 。

此功能可以操作没有一个事件循环。编写非GUI的应用程序和在非GUI线程执行I / O操作时，它是有用的。

**Warning:**从主（图形用户界面）线程调用该函数可能会导致你的用户界面冻结。

如果毫秒为-1 ，此功能将不会超时。

**See also** [finished](qprocess.html#finished)（ ）[waitForStarted](qprocess.html#waitForStarted)（ ）[waitForReadyRead](qprocess.html#waitForReadyRead)（）和[waitForBytesWritten](qprocess.html#waitForBytesWritten)（ ） 。

```
bool QProcess.waitForReadyRead (self, int msecs = 30000)
```

从重新实现[QIODevice.waitForReadyRead](qiodevice.html#waitForReadyRead)（ ） 。

```
bool QProcess.waitForStarted (self, int msecs = 30000)
```

块，直到该进程已经开始，[started](qprocess.html#started)（）信号已被发出，或直到_msecs_毫秒过去了。

返回True如果该进程已成功启动，否则返回False （如果操作超时，或者如果发生错误） 。

此功能可以操作没有一个事件循环。编写非GUI的应用程序和在非GUI线程执行I / O操作时，它是有用的。

**Warning:**从主（图形用户界面）线程调用该函数可能会导致你的用户界面冻结。

如果毫秒为-1 ，此功能将不会超时。

**See also** [started](qprocess.html#started)（ ）[waitForReadyRead](qprocess.html#waitForReadyRead)（ ）[waitForBytesWritten](qprocess.html#waitForBytesWritten)（）和[waitForFinished](qprocess.html#waitForFinished)（ ） 。

```
QString QProcess.workingDirectory (self)
```

If [QProcess](qprocess.html)已指派一个工作目录，这个函数返回的工作目录，该[QProcess](qprocess.html)将进入程序启动之前。否则， （即，没有目录已分配， ）一个空字符串返回，[QProcess](qprocess.html)将使用应用程序的当前工作目录中。

**See also** [setWorkingDirectory](qprocess.html#setWorkingDirectory)（ ） 。

```
int QProcess.writeData (self, str data)
```

从重新实现[QIODevice.writeData](qiodevice.html#writeData)（ ） 。

* * *

## Qt Signal Documentation

```
void error (QProcess::ProcessError)
```

这是该信号的默认超载。

当使用过程中发生错误，这个信号被发射。指定_error_描述发生错误的类型。

```
void finished (int,QProcess::ExitStatus)
```

这是该信号的默认超载。

当该过程完成时，这个信号被发射。_exitCode_是该进程的退出代码，_exitStatus_是的退出状态。之后的过程完成后，该缓冲器中[QProcess](qprocess.html)仍然完好无损。你仍然可以读取该进程可能已写入之前，完成所有数据。

**See also** [exitStatus](qprocess.html#exitStatus)（ ） 。

```
void finished (int)
```

```
void readyReadStandardError ()
```

这是该信号的默认超载。

这个信号被发射时的过程中取得了新的数据可通过其标准错误通道（`stderr`） 。目前它是不管发射[read channel](qprocess.html#readChannel)。

**See also** [readAllStandardError](qprocess.html#readAllStandardError)（）和[readChannel](qprocess.html#readChannel)（ ） 。

```
void readyReadStandardOutput ()
```

这是该信号的默认超载。

这个信号被发射时的过程中取得了新的数据可以通过它的标准输出通道（`stdout`） 。目前它是不管发射[read channel](qprocess.html#readChannel)。

**See also** [readAllStandardOutput](qprocess.html#readAllStandardOutput)（）和[readChannel](qprocess.html#readChannel)（ ） 。

```
void started ()
```

这是该信号的默认超载。

这个信号是由发射[QProcess](qprocess.html)当这个过程已经开始，[state](qprocess.html#state)（）返回[Running](qprocess.html#ProcessState-enum)。

```
void stateChanged (QProcess::ProcessState)
```

这是该信号的默认超载。

这个信号被发射时的状态[QProcess](qprocess.html)变化。该_newState_参数是状态[QProcess](qprocess.html)更改为。