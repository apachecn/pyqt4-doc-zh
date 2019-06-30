# QIODevice Class Reference

## [[QtCore](index.htm) module]

The QIODevice class is the base interface class of all I/O devices in Qt. [More...](#details)

继承[QObject](qobject.html)。

通过继承[QAbstractSocket](qabstractsocket.html)，[QBuffer](qbuffer.html)，[QFile](qfile.html)，[QLocalSocket](qlocalsocket.html)，[QNetworkReply](qnetworkreply.html)和[QProcess](qprocess.html)。

### Types

*   `class **[OpenMode](index.htm)**`
*   `enum OpenModeFlag { NotOpen, ReadOnly, WriteOnly, ReadWrite, ..., Unbuffered }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QObject parent)`
*   `bool atEnd (self)`
*   `int bytesAvailable (self)`
*   `int bytesToWrite (self)`
*   `bool canReadLine (self)`
*   `close (self)`
*   `QString errorString (self)`
*   `(bool, str c) getChar (self)`
*   `bool isOpen (self)`
*   `bool isReadable (self)`
*   `bool isSequential (self)`
*   `bool isTextModeEnabled (self)`
*   `bool isWritable (self)`
*   `bool open (self, OpenMode mode)`
*   `OpenMode openMode (self)`
*   `QByteArray peek (self, int maxlen)`
*   `int pos (self)`
*   `bool putChar (self, str c)`
*   `str read (self, int maxlen)`
*   `QByteArray readAll (self)`
*   `str readData (self, int maxlen)`
*   `str readLine (self, int maxlen = 0)`
*   `str readLineData (self, int maxlen)`
*   `bool reset (self)`
*   `bool seek (self, int pos)`
*   `setErrorString (self, QString errorString)`
*   `setOpenMode (self, OpenMode openMode)`
*   `setTextModeEnabled (self, bool enabled)`
*   `int size (self)`
*   `ungetChar (self, str c)`
*   `bool waitForBytesWritten (self, int msecs)`
*   `bool waitForReadyRead (self, int msecs)`
*   `int write (self, QByteArray data)`
*   `int writeData (self, str data)`

### Qt Signals

*   `void aboutToClose ()`
*   `void bytesWritten (qint64)`
*   `void readChannelFinished ()`
*   `void readyRead ()`

* * *

## Detailed Description

该QIODevice中类是Qt中所有的I / O设备的基本接口类。

QIODevice中提供了一个通用的实现和抽象接口用于支持读数据块，写装置，如[QFile](qfile.html)，[QBuffer](qbuffer.html)和[QTcpSocket](qtcpsocket.html)。 QIODevice中是抽象的，并且不能被实例化，但是通常使用它定义提供设备无关的I / O特性的接口。例如， Qt的XML类上的QIODevice指针操作，使他们能够与各种设备（如文件和缓冲区）使用。

访问该设备之前，[open](qiodevice.html#open)（ ）必须被调用来设置正确的[OpenMode](qiodevice.html#OpenModeFlag-enum)（如[ReadOnly](qiodevice.html#OpenModeFlag-enum) or [ReadWrite](qiodevice.html#OpenModeFlag-enum)） 。然后，您可以写信给装置[write](qiodevice.html#write)（）或[putChar](qiodevice.html#putChar)（ ） ，并宣读通过调用[read](qiodevice.html#read)（ ）[readLine](qiodevice.html#readLine)（） ，或[readAll](qiodevice.html#readAll)（ ） 。通话[close](qiodevice.html#close)（）当你的设备完成的。

随机存取设备和顺序装置：两种类型的设备之间的QIODevice区分。

*   Random-access devices support seeking to arbitrary positions using [seek](qiodevice.html#seek)(). The current position in the file is available by calling [pos](qiodevice.html#pos)(). [QFile](qfile.html) and [QBuffer](qbuffer.html) are examples of random-access devices.
*   Sequential devices don't support seeking to arbitrary positions. The data must be read in one pass. The functions [pos](qiodevice.html#pos)() and [size](qiodevice.html#size)() don't work for sequential devices. [QTcpSocket](qtcpsocket.html) and [QProcess](qprocess.html) are examples of sequential devices.

您可以使用[isSequential](qiodevice.html#isSequential)（）来确定设备的类型。

QIODevice中发出[readyRead](qiodevice.html#readyRead)（ ）当新的数据可供读取，例如，如果新数据到达网络上，或者额外的数据附加到正在读取的文件。您可以致电[bytesAvailable](qiodevice.html#bytesAvailable)（ ）来确定当前可用来读取的字节数。这是常见的使用[bytesAvailable](qiodevice.html#bytesAvailable)（）连同[readyRead](qiodevice.html#readyRead)（）信号与异步设备，如编程[QTcpSocket](qtcpsocket.html)其中数据的片段可以在时间的任意时刻到达。 QIODevice中放出[bytesWritten](qiodevice.html#bytesWritten)（）信号的每一个数据的有效载荷中已被写入到该设备的时间。使用[bytesToWrite](qiodevice.html#bytesToWrite)（）来确定数据等待写入的电流量。

QIODevice中的某些亚类，如[QTcpSocket](qtcpsocket.html)和[QProcess](qprocess.html)，是异步的。这意味着， I / O功能，如[write](qiodevice.html#write)（）或[read](qiodevice.html#read)（ ）总是立刻返回，而当控制返回到事件循环与设备本身的通信可能发生。 QIODevice中提供的功能，让您可以强制这些操作必须立即执行的，而阻塞调用线程，并没有进入事件循环。这允许用户在没有事件循环，或者在单独的线程中使用的QIODevice子类：

*   [waitForReadyRead](qiodevice.html#waitForReadyRead)() - This function suspends operation in the calling thread until new data is available for reading.
*   [waitForBytesWritten](qiodevice.html#waitForBytesWritten)() - This function suspends operation in the calling thread until one payload of data has been written to the device.
*   waitFor....() - Subclasses of QIODevice implement blocking functions for device-specific operations. For example, [QProcess](qprocess.html) has a function called waitForStarted() which suspends operation in the calling thread until the process has started.

从主， GUI线程中调用这些功能，可能会导致你的用户界面冻结。例如：

```
 [QProcess](qprocess.html) gzip;
 gzip.start("gzip", [QStringList](qstringlist.html)() << "-c");
 if (!gzip.waitForStarted())
     return false;

 gzip.write("uncompressed data");

 [QByteArray](qbytearray.html) compressed;
 while (gzip.waitForReadyRead())
     compressed += gzip.readAll();

```

通过子类QIODevice中，您可以提供相同的接口，以你自己的I / O设备。 QIODevice中的子类来实现保护时，才需要[readData](qiodevice.html#readData)（）和[writeData](qiodevice.html#writeData)（）函数。 QIODevice中使用这些函数执行所有它的便利功能，如[getChar](qiodevice.html#getChar)（ ）[readLine](qiodevice.html#readLine)（）和[write](qiodevice.html#write)（ ） 。 QIODevice中还为您处理访问控制，这样你就可以安全地假定该设备在写模式打开，如果[writeData](qiodevice.html#writeData)（）被调用。

一些子类，如[QFile](qfile.html)和[QTcpSocket](qtcpsocket.html)，使用的内存缓冲区用于数据的中间存储实现。这减少了所需的设备访问调用，这通常是非常慢的数量。使缓冲功能，如[getChar](qiodevice.html#getChar)（）和[putChar](qiodevice.html#putChar)（）快，因为它们可以在设备本身上的存储器缓冲操作，而不是直接。某些I / O操作，但是，不具有缓冲工作。例如，如果多个用户打开相同的设备和由字符阅读的字符，它们最终可能读取相同的数据时，为了读取一个单独的组块的每个。出于这个原因， QIODevice中允许你通过将无缓冲标志来绕过任何缓冲[open](qiodevice.html#open)（ ） 。当继承了QIODevice ，记得要绕过你可以使用时，设备处于无缓冲模式打开的任何缓冲区。

* * *

## Type Documentation

```
QIODevice.OpenModeFlag
```

此枚举是使用[open](qiodevice.html#open)（ ）来描述，其中一个装置被打开的模式。它也被返回[openMode](qiodevice.html#openMode)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QIODevice.NotOpen` | `0x0000` | 该设备未打开。 |
| `QIODevice.ReadOnly` | `0x0001` | 该设备是开放式的阅读。 |
| `QIODevice.WriteOnly` | `0x0002` | 该设备是开放式的写作。 |
| `QIODevice.ReadWrite` | `ReadOnly &#124; WriteOnly` | 该设备是开放式的阅读和写作。 |
| `QIODevice.Append` | `0x0004` | 该器件采用追加模式打开，让所有的数据写入到文件的末尾。 |
| `QIODevice.Truncate` | `0x0008` | 如果可能的话，该装置被打开之前被截断。该设备的所有早期的内容会丢失。 |
| `QIODevice.Text` | `0x0010` | 阅读时，行尾的终结被翻译成的'\ n ' 。写作时，行尾的终结将被转换为本地编码，例如' \ r \ ñ'为Win32 。 |
| `QIODevice.Unbuffered` | `0x0020` | 任何缓冲设备中被绕过。 |

某些标志，如`Unbuffered`和`Truncate`一些子类中使用时，是没有意义的。其中的一些限制是由器件的是由子类所表示的类型暗示。在其他情况下，该限制可能是由于在实施方式中，或者可以通过对底层平台的罚款;例如[QTcpSocket](qtcpsocket.html)不支持`Unbuffered`模式，和本机API中的限制阻止[QFile](qfile.html)从支持`Unbuffered`在Windows上。

为openMode类型是一个typedef为[QFlags](index.htm)\u003cOpenModeFlag\u003e 。它存储OpenModeFlag值的或组合。

* * *

## Method Documentation

```
QIODevice.__init__ (self)
```

构造一个[QIODevice](qiodevice.html)对象。

```
QIODevice.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QIODevice](qiodevice.html)与给定对象_parent_。

```
bool QIODevice.atEnd (self)
```

返回True如果当前读写位置是在设备上（即没有可用于读取设备上没有更多的数据）的末尾，否则返回False 。

对于某些设备，了atEnd （ ）可以返回True ，即使有更多的数据读取。这种特殊的情况下只适用于产生直接回应你打电话数据设备[read](qiodevice.html#read)（ ）（例如，`/dev` or `/proc`在Unix和Mac OS X的文件，或者控制台输入/`stdin`在所有平台） 。

**See also** [bytesAvailable](qiodevice.html#bytesAvailable)（ ）[read](qiodevice.html#read)（）和[isSequential](qiodevice.html#isSequential)（ ） 。

```
int QIODevice.bytesAvailable (self)
```

返回可用于读出的字节数。这个函数是常用的使用顺序的设备，以确定的字节数读数之前在缓冲器中分配。

即重新实现这个函数的子类必须调用为了基实现，以包括QIODevices '缓冲区的大小。例如：

```
 [long](index.htm#qint64-typedef) CustomDevice.bytesAvailable() const
 {
     return buffer.size() + [QIODevice](qiodevice.html).bytesAvailable();
 }

```

**See also** [bytesToWrite](qiodevice.html#bytesToWrite)（ ）[readyRead](qiodevice.html#readyRead)（）和[isSequential](qiodevice.html#isSequential)（ ） 。

```
int QIODevice.bytesToWrite (self)
```

对于缓冲装置，该函数返回字节等待写入的数量。对于没有缓冲装置，该函数返回0 。

**See also** [bytesAvailable](qiodevice.html#bytesAvailable)（ ）[bytesWritten](qiodevice.html#bytesWritten)（）和[isSequential](qiodevice.html#isSequential)（ ） 。

```
bool QIODevice.canReadLine (self)
```

返回True如果一个完整的数据线可以从设备中读取，否则返回False 。

需要注意的是缓冲装置，这也没有办法确定哪些可以读取，总是返回False 。

这个功能通常被称为与结合[readyRead](qiodevice.html#readyRead)（）信号。

即重新实现这个函数的子类必须调用基实现，以包括的内容[QIODevice](qiodevice.html)的缓冲。例如：

```
 bool CustomDevice.canReadLine() const
 {
     return buffer.contains('\n') || [QIODevice](qiodevice.html).canReadLine();
 }

```

**See also** [readyRead](qiodevice.html#readyRead)（）和[readLine](qiodevice.html#readLine)（ ） 。

```
QIODevice.close (self)
```

首先发出[aboutToClose](qiodevice.html#aboutToClose)（） ，然后关闭该装置，并将其[OpenMode](qiodevice.html#OpenModeFlag-enum)至[NotOpen](qiodevice.html#OpenModeFlag-enum)。错误字符串也被重置。

**See also** [setOpenMode](qiodevice.html#setOpenMode)（）和[OpenMode](qiodevice.html#OpenModeFlag-enum)。

```
QString QIODevice.errorString (self)
```

返回上次发生设备错误的人类可读的描述。

**See also** [setErrorString](qiodevice.html#setErrorString)（ ） 。

```
(bool, str c) QIODevice.getChar (self)
```

读取从设备并将其存储在一个字符_c_。如果_c_是0时，字符被丢弃。成功时返回TRUE ，否则返回False 。

**See also** [read](qiodevice.html#read)（ ）[putChar](qiodevice.html#putChar)（）和[ungetChar](qiodevice.html#ungetChar)（ ） 。

```
bool QIODevice.isOpen (self)
```

返回True如果该设备已打开，否则返回False 。设备是开放的，如果它可以读取和/或写入。默认情况下，这个函数返回False ，如果[openMode](qiodevice.html#openMode)（）返回`NotOpen`。

**See also** [openMode](qiodevice.html#openMode)（）和[OpenMode](qiodevice.html#OpenModeFlag-enum)。

```
bool QIODevice.isReadable (self)
```

返回True如果数据可以从设备读取，否则返回False 。使用[bytesAvailable](qiodevice.html#bytesAvailable)（）来确定多少字节可以被读取。

这是一个方便的功能，如果它检查[OpenMode](qiodevice.html#OpenModeFlag-enum)该装置包含[ReadOnly](qiodevice.html#OpenModeFlag-enum)标志。

**See also** [openMode](qiodevice.html#openMode)（）和[OpenMode](qiodevice.html#OpenModeFlag-enum)。

```
bool QIODevice.isSequential (self)
```

返回True如果该设备是连续的，否则返回False 。

连续的设备，而不是一个随机存取设备，还没有任何概念的一个开始，结束，大小，或当前位置，并且它们不支持寻求。您只能从设备读取时，它报告的数据是可用的。顺序设备的最常见的例子是网络套接字。在Unix上，特殊文件如/ dev / zero的和FIFO管道是连续的。

常规文件，另一方面，也支持随机访问。它们既具有大小和当前位置，并且它们还支持寻求向后和向前的数据流中。普通文件是不连续的。

该[QIODevice](qiodevice.html)实现返回False 。

**See also** [bytesAvailable](qiodevice.html#bytesAvailable)（ ） 。

```
bool QIODevice.isTextModeEnabled (self)
```

返回True如果[Text](qiodevice.html#OpenModeFlag-enum)标志为启用，否则返回False 。

**See also** [setTextModeEnabled](qiodevice.html#setTextModeEnabled)（ ） 。

```
bool QIODevice.isWritable (self)
```

返回True如果数据可以被写入到该设备，否则返回False 。

这是一个方便的功能，如果它检查[OpenMode](qiodevice.html#OpenModeFlag-enum)该装置包含[WriteOnly](qiodevice.html#OpenModeFlag-enum)标志。

**See also** [openMode](qiodevice.html#openMode)（）和[OpenMode](qiodevice.html#OpenModeFlag-enum)。

```
bool QIODevice.open (self, OpenMode mode)
```

打开该设备，并将其[OpenMode](qiodevice.html#OpenModeFlag-enum)至_mode_。成功返回True ，否则返回False 。这个函数应该被称为从open（）或其他函数打开设备的任何重新实现。

**See also** [openMode](qiodevice.html#openMode)（）和[OpenMode](qiodevice.html#OpenModeFlag-enum)。

```
OpenMode QIODevice.openMode (self)
```

[](index.htm)

[返回在该设备已被打开的模式，即](index.htm)[ReadOnly](qiodevice.html#OpenModeFlag-enum) or [WriteOnly](qiodevice.html#OpenModeFlag-enum)。

**See also** [setOpenMode](qiodevice.html#setOpenMode)（）和[OpenMode](qiodevice.html#OpenModeFlag-enum)。

```
QByteArray QIODevice.peek (self, int maxlen)
```

[](qbytearray.html)

[阅读次数最多_maxSize_从设备到字节_data_，无副作用（即，如果你调用](qbytearray.html)[read](qiodevice.html#read)（ ） PEEK （）之后，您将获得相同的数据） 。返回读取的字节数。如果发生错误，企图偷看在打开设备时，如[WriteOnly](qiodevice.html#OpenModeFlag-enum)模式下，该函数返回-1 。

当没有更多的数据可供读取返回0。

例如：

```
 bool isExeFile([QFile](qfile.html) *file)
 {
     char buf[2];
     if (file->peek(buf, sizeof(buf)) == sizeof(buf))
         return (buf[0] == 'M' && buf[1] == 'Z');
     return false;
 }

```

这个函数是Qt 4.1中引入。

**See also** [read](qiodevice.html#read)（ ） 。

```
int QIODevice.pos (self)
```

对于随机存取设备，此函数返回的数据被写入或读出的位置。对于顺序装置或封闭装置，其中有一个“当前位置”的概念，则返回0 。

该设备的当前读/写位置在内部保持由[QIODevice](qiodevice.html)，所以重新实现这个功能是没有必要的。当子类[QIODevice](qiodevice.html)，使用[QIODevice.seek](qiodevice.html#seek)（ ）通知[QIODevice](qiodevice.html)的变化在设备中的位置。

**See also** [isSequential](qiodevice.html#isSequential)（）和[seek](qiodevice.html#seek)（ ） 。

```
bool QIODevice.putChar (self, str c)
```

写入字符_c_到设备。成功时返回TRUE ，否则返回False 。

**See also** [write](qiodevice.html#write)（ ）[getChar](qiodevice.html#getChar)（）和[ungetChar](qiodevice.html#ungetChar)（ ） 。

```
str QIODevice.read (self, int maxlen)
```

阅读次数最多_maxSize_从设备到字节_data_，并返回读取的字节数。如果发生错误，则尝试从在打开的设备来读取时，如[WriteOnly](qiodevice.html#OpenModeFlag-enum)模式下，该函数返回-1 。

当没有更多的数据可供读取返回0。不过，过去读的流的末尾被认为是一个错误，所以这个函数返回-1在这种情况下（即，读一个已关闭的套接字或之后的过程已经去世） 。

**See also** [readData](qiodevice.html#readData)（ ）[readLine](qiodevice.html#readLine)（）和[write](qiodevice.html#write)（ ） 。

```
QByteArray QIODevice.readAll (self)
```

[

这是一个重载函数。

](qbytearray.html)

[从设备上读取所有可用的数据，并将其作为一个](qbytearray.html)[QByteArray](qbytearray.html)。

此函数没有办法报告错误;返回一个空QByteArray中（ ）可能意味着要么没有数据是目前可用于阅读，或发生了错误。

```
str QIODevice.readData (self, int maxlen)
```

这种方法是抽象的，应在任何子类中重新实现。

读取高达_maxSize_从设备到字节_data_，并返回读取的字节数或-1，如果发生了错误。

如果没有字节被读取并永远不会有更多可用的字节（例子包括插座关闭，管道关闭，子进程结束） ，该函数返回-1 。

调用此函数由[QIODevice](qiodevice.html)。创建的子类时重新实现此功能[QIODevice](qiodevice.html)。

当重新实现这个功能是很重要的，这个函数读取所有需要的数据，然后返回。这是必需的，以便[QDataStream](qdatastream.html)要能够对类进行操作。[QDataStream](qdatastream.html)假设所有请求的信息被读取，因此不会重试阅读，如果有问题。

**See also** [read](qiodevice.html#read)（ ）[readLine](qiodevice.html#readLine)（）和[writeData](qiodevice.html#writeData)（ ） 。

```
str QIODevice.readLine (self, int maxlen = 0)
```

该函数读取一行的从设备的ASCII字符，最多的_maxSize_ - 1个字节，存储在字符_data_，并返回读取的字节数。如果某行不能被读取，但没有错误发生，则该函数返回0 。如果发生错误，此函数返回什么可以读取的长度，或-1，如果没有被读取。

一个终端'\ 0'字节总是附加到_data_，所以_maxSize_必须大于1。

数据被读取，直到下列任一条件满足：

*   The first '\n' character is read.
*   _maxSize_ - 1 bytes are read.
*   The end of the device data is detected.

例如，下面的代码读取一行从文件中的字符：

```
 [QFile](qfile.html) file("box.txt");
 if (file.open([QFile](qfile.html).ReadOnly)) {
     char buf[1024];
     [long](index.htm#qint64-typedef) lineLength = file.readLine(buf, sizeof(buf));
     if (lineLength != -1) {
         // the line is available in buf
     }
 }

```

换行符（ '\ n'）时包含在缓冲区中。如果一个换行符MAXSIZE之前没有遇到过 - 1字节被读取，换行不会被插入到缓冲区。在windows换行符替换为'\ n ' 。

此函数调用[readLineData](qiodevice.html#readLineData)（ ） ，这是使用重复调用实现[getChar](qiodevice.html#getChar)（ ） 。您可以通过重新实现提供更有效的实现[readLineData](qiodevice.html#readLineData)（ ）在自己的子类。

**See also** [getChar](qiodevice.html#getChar)（ ）[read](qiodevice.html#read)（）和[write](qiodevice.html#write)（ ） 。

```
str QIODevice.readLineData (self, int maxlen)
```

读取高达_maxSize_字符转换成_data_并返回读取的字符数。

调用此函数由[readLine](qiodevice.html#readLine)（ ） ，并提供了其基本的实现，用[getChar](qiodevice.html#getChar)（ ） 。缓冲装置可改善性能[readLine](qiodevice.html#readLine)（ ）通过重新实现此功能。

[readLine](qiodevice.html#readLine)（ ）添加一个'\ 0'字节_data_; readLineData （ ）并不需要这样做。

如果你重新实现这个功能，要小心返回正确的值：它应该返回读取此行的字节数，包括终止换行符，或者0，如果没有行被读取了这一点。如果发生错误，它应该返回-1 ，当且仅当没有字节被读取。阅读过去的EOF被认为是一个错误。

```
bool QIODevice.reset (self)
```

搜索到输入的开始随机访问设备。成功时返回TRUE ，否则返回False （例如，如果设备没有打开） 。

使用时需要注意的是一[QTextStream](qtextstream.html)上一个[QFile](qfile.html)，在调用复位（ ）[QFile](qfile.html)不会有预期的结果，因为[QTextStream](qtextstream.html)缓冲文件。使用[QTextStream.seek](qtextstream.html#seek)（ ）函数来代替。

**See also** [seek](qiodevice.html#seek)（ ） 。

```
bool QIODevice.seek (self, int pos)
```

对于随机存取设备，此函数设置当前位置_pos_，返回True表示成功，或False，如果发生了错误。对于顺序的设备，默认的行为是什么都不做，返回False 。

当子类[QIODevice](qiodevice.html)，你必须调用QIODevice.seek （ ）在你的函数的开头，以确保与诚信[QIODevice](qiodevice.html)的内置缓冲。基实现总是返回True 。

**See also** [pos](qiodevice.html#pos)（）和[isSequential](qiodevice.html#isSequential)（ ） 。

```
QIODevice.setErrorString (self, QString errorString)
```

设置发生在最后一个设备错误的可读描述_str_。

**See also** [errorString](qiodevice.html#errorString)（ ） 。

```
QIODevice.setOpenMode (self, OpenMode openMode)
```

设置[OpenMode](qiodevice.html#OpenModeFlag-enum)该设备的_openMode_。调用此函数来设置开放模式，如果该设备已被打开后旗更改。

**See also** [openMode](qiodevice.html#openMode)（）和[OpenMode](qiodevice.html#OpenModeFlag-enum)。

```
QIODevice.setTextModeEnabled (self, bool enabled)
```

If _enabled_诚然，这个功能设置[Text](qiodevice.html#OpenModeFlag-enum)标志装置上，否则[Text](qiodevice.html#OpenModeFlag-enum)标志被清除。此功能对于提供定制行尾类的处理上很有用[QIODevice](qiodevice.html)。

IO设备应调用此函数之前被打开。

**See also** [isTextModeEnabled](qiodevice.html#isTextModeEnabled)（ ）[open](qiodevice.html#open)（）和[setOpenMode](qiodevice.html#setOpenMode)（ ） 。

```
int QIODevice.size (self)
```

为开放的随机存取设备，则该函数返回该装置的尺寸。对于打开的顺序设备，[bytesAvailable](qiodevice.html#bytesAvailable)（ ）返回。

如果设备被关闭，返回的大小不会反映设备的实际大小。

**See also** [isSequential](qiodevice.html#isSequential)（）和[pos](qiodevice.html#pos)（ ） 。

```
QIODevice.ungetChar (self, str c)
```

把字符_c_返回到设备，并减少当前位置，除非该位置为0 。此功能通常被称为“撤销”一[getChar](qiodevice.html#getChar)（）操作，记录一个回溯解析器时，例如。

If _c_是不是从以前的设备读取，行为是未定义的。

```
bool QIODevice.waitForBytesWritten (self, int msecs)
```

用于缓冲的装置，该函数将等待直到缓冲写入的数据的有效载荷中已写入的装置和[bytesWritten](qiodevice.html#bytesWritten)（）信号已被发出，或直到_msecs_毫秒过去了。如果毫秒为-1 ，此功能将不会超时。对于无缓冲装置，它会立即返回。

返回True如果数据的有效载荷被写入到设备，否则返回False （也就是说，如果操作超时，或者如果发生错误） 。

此功能可以操作没有一个事件循环。编写非GUI的应用程序和在非GUI线程执行I / O操作时，它是有用的。

如果从连接到一个时隙内的称为[bytesWritten](qiodevice.html#bytesWritten)（ ）信号，[bytesWritten](qiodevice.html#bytesWritten)（ ）将不会被重新发射。

重新实现这个函数提供一个阻塞的API自定义设备。默认实现不执行任何操作，并返回False 。

**Warning:**从主（图形用户界面）线程调用该函数可能会导致你的用户界面冻结。

**See also** [waitForReadyRead](qiodevice.html#waitForReadyRead)（ ） 。

```
bool QIODevice.waitForReadyRead (self, int msecs)
```

阻塞，直到新的数据可供读取和[readyRead](qiodevice.html#readyRead)（）信号已被发出，或直到_msecs_毫秒过去了。如果毫秒为-1 ，此功能将不会超时。

如果新的数据可供读取，则返回True ，否则返回False （如果操作超时，或者如果发生错误） 。

此功能可以操作没有一个事件循环。编写非GUI的应用程序和在非GUI线程执行I / O操作时，它是有用的。

如果从连接到一个时隙内的称为[readyRead](qiodevice.html#readyRead)（ ）信号，[readyRead](qiodevice.html#readyRead)（ ）将不会被重新发射。

重新实现这个函数提供一个阻塞的API自定义设备。默认实现不执行任何操作，并返回False 。

**Warning:**从主（图形用户界面）线程调用该函数可能会导致你的用户界面冻结。

**See also** [waitForBytesWritten](qiodevice.html#waitForBytesWritten)（ ） 。

```
int QIODevice.write (self, QByteArray data)
```

写在最_maxSize_数据从字节_data_到设备。返回实际写入的，或者-1如果发生错误的字节数。

**See also** [read](qiodevice.html#read)（）和[writeData](qiodevice.html#writeData)（ ） 。

```
int QIODevice.writeData (self, str data)
```

这种方法是抽象的，应在任何子类中重新实现。

写入速度达_maxSize_从字节_data_到设备。返回写入的字节数，或-1，如果发生了错误。

调用此函数由[QIODevice](qiodevice.html)。创建的子类时重新实现此功能[QIODevice](qiodevice.html)。

当重新实现这个功能是很重要的，这个函数将所有可用的返回之前的数据。这是必需的，以便[QDataStream](qdatastream.html)要能够对类进行操作。[QDataStream](qdatastream.html)假设所有的信息写入，因此不会重试写，如果有一个问题。

**See also** [read](qiodevice.html#read)（）和[write](qiodevice.html#write)（ ） 。

* * *

## Qt Signal Documentation

```
void aboutToClose ()
```

这是该信号的默认超载。

时，该设备在关闭这个信号被发射。如果您有需要装置关闭之前执行（例如，如果你有数据需要被写入到设备的单独缓冲器）操作连接这个信号。

```
void bytesWritten (qint64)
```

这是该信号的默认超载。

每一数据的有效载荷已经被写入到设备时，这个信号被发射。该_bytes_参数设置为写在这个有效载荷的字节数。

bytesWritten （ ）是不是递归发出，如果你重新进入事件循环或致电[waitForBytesWritten](qiodevice.html#waitForBytesWritten)（）连接到bytesWritten一个时隙内（）信号，该信号将不会再发射（尽管[waitForBytesWritten](qiodevice.html#waitForBytesWritten)（ ）可能仍然返回True ） 。

**See also** [readyRead](qiodevice.html#readyRead)（ ） 。

```
void readChannelFinished ()
```

这是该信号的默认超载。

当输入（读出）数据流在该装置关闭时，这个信号被发射。它刚一闭幕时探测的发射，这意味着仍有可能适用于读取数据[read](qiodevice.html#read)（ ） 。

此功能被引入Qt的4.4 。

**See also** [atEnd](qiodevice.html#atEnd)（）和[read](qiodevice.html#read)（ ） 。

```
void readyRead ()
```

这是该信号的默认超载。

每一次新的数据是可用于从设备中读取这个信号被发射。它只会再次发出一次新的数据是可用的，比如当网络数据的一个新的有效载荷已经到达您的网络套接字，或者当一个新的数据块是否已经被添加到您的设备。

的readyRead （ ）是不是递归发出，如果你重新进入事件循环或致电[waitForReadyRead](qiodevice.html#waitForReadyRead)（）连接到所述的readyRead一个时隙内（）信号，该信号将不会再发射（尽管[waitForReadyRead](qiodevice.html#waitForReadyRead)（ ）可能仍然返回True ） 。

注意执行从派生类开发商[QIODevice](qiodevice.html)：你应该总是散发出的readyRead （ ）时，新的数据已经到达（不散发这不仅是因为有数据仍然可以读取你的缓冲区） 。不要发出的readyRead （ ）在其他条件。

**See also** [bytesWritten](qiodevice.html#bytesWritten)（ ） 。