# QBuffer Class Reference

## [[QtCore](index.htm) module]

该Q缓冲器类提供了一个[QIODevice](qiodevice.html)接口为一[QByteArray](qbytearray.html)。[More...](#details)

继承[QIODevice](qiodevice.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QByteArray byteArray, QObject parent = None)`
*   `bool atEnd (self)`
*   `QByteArray buffer (self)`
*   `bool canReadLine (self)`
*   `close (self)`
*   `connectNotify (self, SIGNAL())`
*   `QByteArray data (self)`
*   `disconnectNotify (self, SIGNAL())`
*   `bool open (self, QIODevice.OpenMode openMode)`
*   `int pos (self)`
*   `str readData (self, int maxlen)`
*   `bool seek (self, int off)`
*   `setBuffer (self, QByteArray a)`
*   `setData (self, QByteArray data)`
*   `setData (self, str adata)`
*   `int size (self)`
*   `int writeData (self, str data)`

* * *

## Detailed Description

该Q缓冲器类提供了一个[QIODevice](qiodevice.html)接口为一[QByteArray](qbytearray.html)。

Q缓冲器允许你访问一个[QByteArray](qbytearray.html)使用[QIODevice](qiodevice.html)接口。该[QByteArray](qbytearray.html)被视为只是作为一个标准的随机访问的文件。例如：

```
     QBuffer buffer;
     char ch;

     buffer.open(QBuffer.ReadWrite);
     buffer.write("Qt rocks!");
     buffer.seek(0);
     buffer.getChar(&ch);  // ch == 'Q'
     buffer.getChar(&ch);  // ch == 't'
     buffer.getChar(&ch);  // ch == ' '
     buffer.getChar(&ch);  // ch == 'r'

```

默认情况下，内部[QByteArray](qbytearray.html)缓冲区是为你，当你创建一个Q缓冲器创建。您可以直接通过调用访问该缓冲区[buffer](qbuffer.html#buffer)（ ） 。也可以使用ΣQ缓冲与现有[QByteArray](qbytearray.html)通过调用[setBuffer](qbuffer.html#setBuffer)（ ） ，或者通过你的数组Q缓冲器的构造函数。

Call [open](qbuffer.html#open)（）打开缓冲区。然后调用[write](qiodevice.html#write)（）或[putChar](qiodevice.html#putChar)（ ）写入到缓冲区，并[read](qiodevice.html#read)（ ）[readLine](qiodevice.html#readLine)（ ）[readAll](qiodevice.html#readAll)（） ，或[getChar](qiodevice.html#getChar)（）读取它。[size](qbuffer.html#size)（）返回缓冲区的当前大小，并且可以通过调用试图在缓冲区中的任意位置[seek](qbuffer.html#seek)（ ） 。当你与访问缓冲完成后，调用[close](qbuffer.html#close)（ ） 。

下面的代码片段显示了如何将数据写入到[QByteArray](qbytearray.html) using [QDataStream](qdatastream.html)和Q缓冲器：

```
     [QByteArray](qbytearray.html) byteArray;
     QBuffer buffer(&byteArray);
     buffer.open([QIODevice](qiodevice.html).WriteOnly);

     [QDataStream](qdatastream.html) out(&buffer);
     out << [QApplication](qapplication.html).palette();

```

实际上，我们把应用程序的[QPalette](qpalette.html)成一个字节数组。以下是如何从读取数据[QByteArray](qbytearray.html)：

```
     [QPalette](qpalette.html) palette;
     QBuffer buffer(&byteArray);
     buffer.open([QIODevice](qiodevice.html).ReadOnly);

     [QDataStream](qdatastream.html) in(&buffer);
     in >> palette;

```

[QTextStream](qtextstream.html)和[QDataStream](qdatastream.html)还提供了方便的构造函数，它接受一个[QByteArray](qbytearray.html)并创建一个Q缓冲器幕后。

Q缓冲器发出[readyRead](qiodevice.html#readyRead)（ ）当新的数据到达缓冲区。通过连接到这个信号，就可以使用Q缓冲器处理之前来存储临时数据。例如，您可以将缓冲区传递到[QFtp](qftp.html)从FTP服务器上下载一个文件时。每当一个新的数据有效载荷被下载，[readyRead](qiodevice.html#readyRead)（ ）被发射，并且可以处理刚到的数据。 Q缓冲器还发出[bytesWritten](qiodevice.html#bytesWritten)（ ）每次新的数据已经被写入到缓冲区。

* * *

## Method Documentation

```
QBuffer.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的缓冲区与给定_parent_。您可以致电[setData](qbuffer.html#setData)（）来填充数据的缓冲区，也可以在写入模式，并使用它打开[write](qiodevice.html#write)（ ） 。

**See also** [open](qbuffer.html#open)（ ） 。

```
QBuffer.__init__ (self, QByteArray byteArray, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QBuffer](qbuffer.html)使用该[QByteArray](qbytearray.html)指向_byteArray_作为其内部缓冲器，并与给定的_parent_。来电者是负责确保_byteArray_保持有效，直到[QBuffer](qbuffer.html)被破坏，或直到[setBuffer](qbuffer.html#setBuffer)（ ）被调用来更改缓冲区。[QBuffer](qbuffer.html)不走的所有权[QByteArray](qbytearray.html)。

如果您在只写模式打开的缓冲区或读写模式和写的东西进入[QBuffer](qbuffer.html)，_byteArray_将被修改。

例如：

```
     [QByteArray](qbytearray.html) byteArray("abc");
     [QBuffer](qbuffer.html) buffer(&byteArray);
     buffer.open([QIODevice](qiodevice.html).WriteOnly);
     buffer.seek(3);
     buffer.write("def", 3);
     buffer.close();
     // byteArray == "abcdef"

```

**See also** [open](qbuffer.html#open)（ ）[setBuffer](qbuffer.html#setBuffer)（）和[setData](qbuffer.html#setData)（ ） 。

```
bool QBuffer.atEnd (self)
```

从重新实现[QIODevice.atEnd](qiodevice.html#atEnd)（ ） 。

```
QByteArray QBuffer.buffer (self)
```

[](qbytearray.html)

[返回一个引用](qbytearray.html)[QBuffer](qbuffer.html)的内部缓冲区。你可以用它来修改[QByteArray](qbytearray.html)后面的[QBuffer](qbuffer.html)的背部。

**See also** [setBuffer](qbuffer.html#setBuffer)（）和[data](qbuffer.html#data)（ ） 。

```
bool QBuffer.canReadLine (self)
```

从重新实现[QIODevice.canReadLine](qiodevice.html#canReadLine)（ ） 。

```
QBuffer.close (self)
```

从重新实现[QIODevice.close](qiodevice.html#close)（ ） 。

```
QBuffer.connectNotify (self, SIGNAL())
```

```
QByteArray QBuffer.data (self)
```

[

返回包含在缓冲区中的数据。

](qbytearray.html)

[这是相同的](qbytearray.html)[buffer](qbuffer.html#buffer)（ ） 。

**See also** [setData](qbuffer.html#setData)（）和[setBuffer](qbuffer.html#setBuffer)（ ） 。

```
QBuffer.disconnectNotify (self, SIGNAL())
```

```
bool QBuffer.open (self, QIODevice.OpenMode openMode)
```

从重新实现[QIODevice.open](qiodevice.html#open)（ ） 。

```
int QBuffer.pos (self)
```

从重新实现[QIODevice.pos](qiodevice.html#pos)（ ） 。

```
str QBuffer.readData (self, int maxlen)
```

从重新实现[QIODevice.readData](qiodevice.html#readData)（ ） 。

```
bool QBuffer.seek (self, int off)
```

从重新实现[QIODevice.seek](qiodevice.html#seek)（ ） 。

```
QBuffer.setBuffer (self, QByteArray a)
```

品牌[QBuffer](qbuffer.html)使用[QByteArray](qbytearray.html)指向_byteArray_作为其内部缓冲器中。来电者是负责确保_byteArray_保持有效，直到[QBuffer](qbuffer.html)被破坏，或直到setBuffer （ ）被调用来更改缓冲区。[QBuffer](qbuffer.html)不走的所有权[QByteArray](qbytearray.html)。

什么都不做，如果[isOpen](qiodevice.html#isOpen)（）是真实的。

如果您在只写模式打开的缓冲区或读写模式和写的东西进入[QBuffer](qbuffer.html)，_byteArray_将被修改。

例如：

```
     [QByteArray](qbytearray.html) byteArray("abc");
     [QBuffer](qbuffer.html) buffer;
     buffer.setBuffer(&byteArray);
     buffer.open([QIODevice](qiodevice.html).WriteOnly);
     buffer.seek(3);
     buffer.write("def", 3);
     buffer.close();
     // byteArray == "abcdef"

```

If _byteArray_为0时，缓存器创建其自己的内部[QByteArray](qbytearray.html)去努力。这个字节数组初始为空。

**See also** [buffer](qbuffer.html#buffer)（ ）[setData](qbuffer.html#setData)（）和[open](qbuffer.html#open)（ ） 。

```
QBuffer.setData (self, QByteArray data)
```

设置内部缓冲区的内容被_data_。这是相同的分配_data_至[buffer](qbuffer.html#buffer)（ ） 。

什么都不做，如果[isOpen](qiodevice.html#isOpen)（）是真实的。

**See also** [data](qbuffer.html#data)（）和[setBuffer](qbuffer.html#setBuffer)（ ） 。

```
QBuffer.setData (self, str adata)
```

这是一个重载函数。

设置内部缓冲区的内容是第一_size_字节_data_。

```
int QBuffer.size (self)
```

从重新实现[QIODevice.size](qiodevice.html#size)（ ） 。

```
int QBuffer.writeData (self, str data)
```

从重新实现[QIODevice.writeData](qiodevice.html#writeData)（ ） 。