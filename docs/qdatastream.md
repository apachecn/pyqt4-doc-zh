# QDataStream Class Reference

## [[QtCore](index.htm) module]

该QDataStream类提供的二进制数据序列化到一个[QIODevice](qiodevice.html)。[More...](#details)

### Types

*   `enum ByteOrder { BigEndian, LittleEndian }`
*   `enum FloatingPointPrecision { SinglePrecision, DoublePrecision }`
*   `enum Status { Ok, ReadPastEnd, ReadCorruptData, WriteFailed }`
*   `enum Version { Qt_1_0, Qt_2_0, Qt_2_1, Qt_3_0, ..., Qt_4_8 }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice)`
*   `__init__ (self, QByteArray, QIODevice.OpenMode flags)`
*   `__init__ (self, QByteArray)`
*   `bool atEnd (self)`
*   `ByteOrder byteOrder (self)`
*   `QIODevice device (self)`
*   `FloatingPointPrecision floatingPointPrecision (self)`
*   `bool readBool (self)`
*   `str readBytes (self)`
*   `float readDouble (self)`
*   `float readFloat (self)`
*   `int readInt (self)`
*   `int readInt16 (self)`
*   `int readInt32 (self)`
*   `int readInt64 (self)`
*   `str readInt8 (self)`
*   `QString readQString (self)`
*   `QStringList readQStringList (self)`
*   `QVariant readQVariant (self)`
*   `dict-of-QString-QVariant readQVariantHash (self)`
*   `list-of-QVariant readQVariantList (self)`
*   `dict-of-QString-QVariant readQVariantMap (self)`
*   `str readRawData (self, int len)`
*   `str readString (self)`
*   `int readUInt16 (self)`
*   `int readUInt32 (self)`
*   `int readUInt64 (self)`
*   `str readUInt8 (self)`
*   `resetStatus (self)`
*   `setByteOrder (self, ByteOrder)`
*   `setDevice (self, QIODevice)`
*   `setFloatingPointPrecision (self, FloatingPointPrecision precision)`
*   `setStatus (self, Status status)`
*   `setVersion (self, int v)`
*   `int skipRawData (self, int len)`
*   `Status status (self)`
*   `unsetDevice (self)`
*   `int version (self)`
*   `writeBool (self, bool i)`
*   `QDataStream writeBytes (self, str)`
*   `writeDouble (self, float f)`
*   `writeFloat (self, float f)`
*   `writeInt (self, int i)`
*   `writeInt16 (self, int i)`
*   `writeInt32 (self, int i)`
*   `writeInt64 (self, int i)`
*   `writeInt8 (self, str i)`
*   `writeQString (self, QString qstr)`
*   `writeQStringList (self, QStringList qstrlst)`
*   `writeQVariant (self, QVariant qvar)`
*   `writeQVariantHash (self, dict-of-QString-QVariant qvarhash)`
*   `writeQVariantList (self, list-of-QVariant qvarlst)`
*   `writeQVariantMap (self, dict-of-QString-QVariant qvarmap)`
*   `int writeRawData (self, str)`
*   `writeString (self, str str)`
*   `writeUInt16 (self, int i)`
*   `writeUInt32 (self, int i)`
*   `writeUInt64 (self, int i)`
*   `writeUInt8 (self, str i)`

### Special Methods

*   `QDataStream __lshift__ (self, QColor)`
*   `QDataStream __lshift__ (self, QNetworkCacheMetaData)`
*   `QDataStream __lshift__ (self, QScriptContextInfo)`
*   `QDataStream __lshift__ (self, QWebHistory)`
*   `QDataStream __lshift__ (self, QBrush)`
*   `QDataStream __lshift__ (self, QHostAddress)`
*   `QDataStream __lshift__ (self, QCursor cursor)`
*   `QDataStream __lshift__ (self, QFont)`
*   `QDataStream __lshift__ (self, QIcon)`
*   `QDataStream __lshift__ (self, QImage)`
*   `QDataStream __lshift__ (self, QKeySequence ks)`
*   `QDataStream __lshift__ (self, QListWidgetItem item)`
*   `QDataStream __lshift__ (self, QMatrix)`
*   `QDataStream __lshift__ (self, QMatrix4x4)`
*   `QDataStream __lshift__ (self, QPainterPath)`
*   `QDataStream __lshift__ (self, QPalette p)`
*   `QDataStream __lshift__ (self, QPen)`
*   `QDataStream __lshift__ (self, QPicture p)`
*   `QDataStream __lshift__ (self, QPixmap)`
*   `QDataStream __lshift__ (self, QPolygonF array)`
*   `QDataStream __lshift__ (self, QPolygon polygon)`
*   `QDataStream __lshift__ (self, QQuaternion)`
*   `QDataStream __lshift__ (self, QRegion)`
*   `QDataStream __lshift__ (self, QSizePolicy)`
*   `QDataStream __lshift__ (self, QStandardItem item)`
*   `QDataStream __lshift__ (self, QTableWidgetItem item)`
*   `QDataStream __lshift__ (self, QTextLength)`
*   `QDataStream __lshift__ (self, QTextFormat)`
*   `QDataStream __lshift__ (self, QTransform)`
*   `QDataStream __lshift__ (self, QTreeWidgetItem item)`
*   `QDataStream __lshift__ (self, QVector2D)`
*   `QDataStream __lshift__ (self, QVector3D)`
*   `QDataStream __lshift__ (self, QVector4D)`
*   `QDataStream __rshift__ (self, QColor)`
*   `QDataStream __rshift__ (self, QNetworkCacheMetaData)`
*   `QDataStream __rshift__ (self, QScriptContextInfo)`
*   `QDataStream __rshift__ (self, QWebHistory)`
*   `QDataStream __rshift__ (self, QBrush)`
*   `QDataStream __rshift__ (self, QHostAddress)`
*   `QDataStream __rshift__ (self, QCursor cursor)`
*   `QDataStream __rshift__ (self, QFont)`
*   `QDataStream __rshift__ (self, QIcon)`
*   `QDataStream __rshift__ (self, QImage)`
*   `QDataStream __rshift__ (self, QKeySequence ks)`
*   `QDataStream __rshift__ (self, QListWidgetItem item)`
*   `QDataStream __rshift__ (self, QMatrix)`
*   `QDataStream __rshift__ (self, QMatrix4x4)`
*   `QDataStream __rshift__ (self, QPainterPath)`
*   `QDataStream __rshift__ (self, QPalette p)`
*   `QDataStream __rshift__ (self, QPen)`
*   `QDataStream __rshift__ (self, QPicture p)`
*   `QDataStream __rshift__ (self, QPixmap)`
*   `QDataStream __rshift__ (self, QPolygonF array)`
*   `QDataStream __rshift__ (self, QPolygon polygon)`
*   `QDataStream __rshift__ (self, QQuaternion)`
*   `QDataStream __rshift__ (self, QRegion)`
*   `QDataStream __rshift__ (self, QSizePolicy)`
*   `QDataStream __rshift__ (self, QStandardItem item)`
*   `QDataStream __rshift__ (self, QTableWidgetItem item)`
*   `QDataStream __rshift__ (self, QTextLength)`
*   `QDataStream __rshift__ (self, QTextFormat)`
*   `QDataStream __rshift__ (self, QTransform)`
*   `QDataStream __rshift__ (self, QTreeWidgetItem item)`
*   `QDataStream __rshift__ (self, QVector2D)`
*   `QDataStream __rshift__ (self, QVector3D)`
*   `QDataStream __rshift__ (self, QVector4D)`
*   `QDataStream __lshift__ (self, QBitArray)`
*   `QDataStream __lshift__ (self, QByteArray)`
*   `QDataStream __lshift__ (self, QChar)`
*   `QDataStream __lshift__ (self, QDate)`
*   `QDataStream __lshift__ (self, QTime)`
*   `QDataStream __lshift__ (self, QDateTime)`
*   `QDataStream __lshift__ (self, QEasingCurve)`
*   `QDataStream __lshift__ (self, QLine)`
*   `QDataStream __lshift__ (self, QLineF)`
*   `QDataStream __lshift__ (self, QLocale)`
*   `QDataStream __lshift__ (self, QPoint)`
*   `QDataStream __lshift__ (self, QPointF)`
*   `QDataStream __lshift__ (self, QRect)`
*   `QDataStream __lshift__ (self, QRectF)`
*   `QDataStream __lshift__ (self, QRegExp regExp)`
*   `QDataStream __lshift__ (self, QSize)`
*   `QDataStream __lshift__ (self, QSizeF)`
*   `QDataStream __lshift__ (self, QString)`
*   `QDataStream __lshift__ (self, QStringList list)`
*   `QDataStream __lshift__ (self, QUrl)`
*   `QDataStream __lshift__ (self, QUuid)`
*   `QDataStream __lshift__ (self, QVariant p)`
*   `QDataStream __lshift__ (self, Type p)`
*   `QDataStream __rshift__ (self, QBitArray)`
*   `QDataStream __rshift__ (self, QByteArray)`
*   `QDataStream __rshift__ (self, QChar)`
*   `QDataStream __rshift__ (self, QDate)`
*   `QDataStream __rshift__ (self, QTime)`
*   `QDataStream __rshift__ (self, QDateTime)`
*   `QDataStream __rshift__ (self, QEasingCurve)`
*   `QDataStream __rshift__ (self, QLine)`
*   `QDataStream __rshift__ (self, QLineF)`
*   `QDataStream __rshift__ (self, QLocale)`
*   `QDataStream __rshift__ (self, QPoint)`
*   `QDataStream __rshift__ (self, QPointF)`
*   `QDataStream __rshift__ (self, QRect)`
*   `QDataStream __rshift__ (self, QRectF)`
*   `QDataStream __rshift__ (self, QRegExp regExp)`
*   `QDataStream __rshift__ (self, QSize)`
*   `QDataStream __rshift__ (self, QSizeF)`
*   `QDataStream __rshift__ (self, QString)`
*   `QDataStream __rshift__ (self, QStringList list)`
*   `QDataStream __rshift__ (self, QUrl)`
*   `QDataStream __rshift__ (self, QUuid)`
*   `QDataStream __rshift__ (self, QVariant p)`
*   `QDataStream __rshift__ (self, Type p)`

* * *

## Detailed Description

该QDataStream类提供的二进制数据序列化到一个[QIODevice](qiodevice.html)。

数据流是独立于主机的操作系统， CPU或字节顺序的100 ％的编码信息的二进制流。例如，写的是Windows下的PC机的数据流可以通过在Sun SPARC上运行的Solaris读取。

您也可以使用一个数据流读/写[raw unencoded binary data](#raw)。如果你想要一个“解析”输入流，请参阅[QTextStream](qtextstream.html)。

该QDataStream类实现了C + +的基本数据类型的序列化，如`char`，`short`，`int`，`char *`，更复杂的数据序列化等由数据分解成原始单位来完成的。

一个数据流与密切合作[QIODevice](qiodevice.html)。一[QIODevice](qiodevice.html)表示输入/输出介质1可以读取数据和写入数据到。该[QFile](qfile.html)类是一个I / O设备的一个例子。

例如（写入二进制数据流） ：

```
 [QFile](qfile.html) file("file.dat");
 file.open([QIODevice](qiodevice.html).WriteOnly);
 QDataStream out(&file);   // we will serialize the data into the file
 out << [QString](qstring.html)("the answer is");   // serialize a string
 out << ([qint32](index.htm#qint32-typedef))42;        // serialize an integer

```

示例（读取流的二进制数据） ：

```
 [QFile](qfile.html) file("file.dat");
 file.open([QIODevice](qiodevice.html).ReadOnly);
 QDataStream in(&file);    // read the data serialized from the file
 [QString](qstring.html) str;
 [qint32](index.htm#qint32-typedef) a;
 in >> str >> a;           // extract "the answer is" and 42

```

写入流中的每一项是写在根据项目的不同类型预定义的二进制格式。支持Qt的类型包括[QBrush](qbrush.html)，[QColor](qcolor.html)，[QDateTime](qdatetime.html)，[QFont](qfont.html)，[QPixmap](qpixmap.html)，[QString](qstring.html)，[QVariant](qvariant.html)和其他许多人。对于所有类型的Qt支持的数据流看的完整列表[Serializing Qt Data Types](index.htm)。

对于整数，最好是始终转换为Qt的整数类型的写作，和读回相同Qt的整数类型。这可以确保你得到你想要的大小的整数，并隔离了一些编译器和平台的差异。

举个例子，一个`char *`字符串被写入作为一个32位整数，等于包括'\ 0'字节，接着是字符串的所有字符，包括'\ 0'字节的字符串的长度。当读取一个`char *`串的4个字节被读出以创建32比特长度的值，那么这许多字符的`char *`读取字符串包括' \ 0 '终止。

最初的I / O设备通常设置在构造函数中，但可以用改变[setDevice](qdatastream.html#setDevice)（ ） 。如果你已经达到了数据的末尾（或如果没有I / O设备设置）[atEnd](qdatastream.html#atEnd)（ ）将返回True 。

### Versioning

由于Qt的1.0 QDataStream的二进制格式的演变，并有可能继续发展，以反映Qt中所作的更改。当输入或输出复杂的类型，它是非常重要的，以确保流的同一版本（[version](qdatastream.html#version)（） ）是用于读取和写入。如果你需要向前和向后兼容性，您可以硬编码在应用程序的版本号：

```
 stream.setVersion(QDataStream.Qt_4_0);

```

如果你正在制作一个新的二进制数据格式，如用于您的应用程序创建的文档的文件格式，你可以使用操作QDataStream写在便携格式的数据。通常情况下，你会写包含magic字符串和版本号给自己空间，未来扩展一个简短的标题。例如：

```
 [QFile](qfile.html) file("file.xxx");
 file.open([QIODevice](qiodevice.html).WriteOnly);
 QDataStream out(&file);

 // Write a header with a "magic number" and a version
 out << ([quint32](index.htm#quint32-typedef))0xA0B0C0D0;
 out << ([qint32](index.htm#qint32-typedef))123;

 out.setVersion(QDataStream.Qt_4_0);

 // Write the data
 out << lots_of_interesting_data;

```

然后读取它与：

```
 [QFile](qfile.html) file("file.xxx");
 file.open([QIODevice](qiodevice.html).ReadOnly);
 QDataStream in(&file);

 // Read and check the header
 [quint32](index.htm#quint32-typedef) magic;
 in >> magic;
 if (magic != 0xA0B0C0D0)
     return XXX_BAD_FILE_FORMAT;

 // Read the version
 [qint32](index.htm#qint32-typedef) version;
 in >> version;
 if (version < 100)
     return XXX_BAD_FILE_TOO_OLD;
 if (version > 123)
     return XXX_BAD_FILE_TOO_NEW;

 if (version <= 110)
     in.setVersion(QDataStream.Qt_3_2);
 else
     in.setVersion(QDataStream.Qt_4_0);

 // Read the data
 in >> lots_of_interesting_data;
 if (version >= 120)
     in >> data_new_in_XXX_version_1_2;
 in >> other_interesting_data;

```

你可以选择其中的字节顺序序列化数据时使用。默认设置为大端（高位在前） 。它改变为小端打破了便携性（除非读者也改变为小端） 。我们建议保持此设置，除非你有特殊的要求。

### Reading and writing raw binary data

你不妨读/写自己的原始二进制数据到/直接从数据流中。数据可以被从该流读取到一个预先分配的`char *` using [readRawData](qdatastream.html#readRawData)（ ） 。同样的数据可以使用被写入到该流[writeRawData](qdatastream.html#writeRawData)（ ） 。请注意，任何数据编码/解码必须由你来完成。

一对相似的功能是[readBytes](qdatastream.html#readBytes)（）和[writeBytes](qdatastream.html#writeBytes)（ ） 。这些从他们的不同_raw_对口如下：[readBytes](qdatastream.html#readBytes)（）读取被视为将要读取的数据的长度的quint32 ，则该数目的字节被读入预先分配的`char *`;[writeBytes](qdatastream.html#writeBytes)（）写入包含该数据的长度的quint32 ，然后是数据。请注意，数据（除了长度quint32 ）任何编码/解码必须由你来完成。

### Reading and writing Qt collection classes

Qt的容器类也可以被序列化到操作QDataStream 。这些措施包括[QList](index.htm)，[QLinkedList](index.htm)，[QVector](index.htm)，[QSet](index.htm)，[QHash](index.htm)和[QMap](index.htm)。流运算符被声明为类的非成员。

### Reading and writing other Qt classes.

除了重载流运算符记录在这里，任何的Qt类，你可能要序列化操作QDataStream将有声明为类的非成员适当的流运算符：

```
 QDataStream &operator<<(QDataStream &, const QXxx &);
 QDataStream &operator>>(QDataStream &, QXxx &);

```

例如，这里有流运营商宣布作为非成员[QImage](qimage.html)类：

```
 QDataStream & operator<< (QDataStream& stream, const [QImage](qimage.html)& image);
 QDataStream & operator>> (QDataStream& stream, [QImage](qimage.html)& image);

```

要看看你最喜欢的Qt类定义了类似的流运算符，请检查**Related Non-Members**类的文档页面的部分。

* * *

## Type Documentation

```
QDataStream.ByteOrder
```

用于读取/写入数据的字节顺序。

| Constant | Value | Description |
| --- | --- | --- |
| `QDataStream.BigEndian` | `QSysInfo.BigEndian` | 第一个最显着字节（默认） |
| `QDataStream.LittleEndian` | `QSysInfo.LittleEndian` | 首先至少显着字节 |

```
QDataStream.FloatingPointPrecision
```

用于读/写数据的浮点数的精度。这只会产生效果，如果数据流的版本是[Qt_4_6](qdatastream.html#Version-enum)或更高。

**Warning:**浮点精度必须被设置为相同的值，写入对象并读取数据流中的对象上。

| Constant | Value | Description |
| --- | --- | --- |
| `QDataStream.SinglePrecision` | `0` | 在数据流中的所有浮点数具有32位精度。 |
| `QDataStream.DoublePrecision` | `1` | 在数据流中的所有浮点数具有64位精度。 |

**See also** [setFloatingPointPrecision](qdatastream.html#setFloatingPointPrecision)（）和[floatingPointPrecision](qdatastream.html#floatingPointPrecision)（ ） 。

```
QDataStream.Status
```

该枚举描述了数据流的当前状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QDataStream.Ok` | `0` | 该数据流是否正常运行。 |
| `QDataStream.ReadPastEnd` | `1` | 该数据流已经读取过的底层设备中的数据的结尾。 |
| `QDataStream.ReadCorruptData` | `2` | 数据流已经读取损坏的数据。 |
| `QDataStream.WriteFailed` | `3` | 数据流不能写入到基础设备。 |

```
QDataStream.Version
```

此枚举提供了象征性的同义词，数据序列化格式的版本号。

| Constant | Value | Description |
| --- | --- | --- |
| `QDataStream.Qt_1_0` | `1` | 版本1 （ Qt的1.x中） |
| `QDataStream.Qt_2_0` | `2` | 第2版​​（ Qt的2.0） |
| `QDataStream.Qt_2_1` | `3` | 第3版（ Qt的2.1 ，2.2， 2.3 ） |
| `QDataStream.Qt_3_0` | `4` | 第4版（QT 3.0 ） |
| `QDataStream.Qt_3_1` | `5` | 第5版（QT 3.1 ， 3.2 ） |
| `QDataStream.Qt_3_3` | `6` | 第6版（QT 3.3 ） |
| `QDataStream.Qt_4_0` | `7` | 第7版（QT 4.0 ， Qt的4.1 ） |
| `QDataStream.Qt_4_1` | `Qt_4_0` | 第7版（QT 4.0 ， Qt的4.1 ） |
| `QDataStream.Qt_4_2` | `8` | 8版本（ Qt 4.2中） |
| `QDataStream.Qt_4_3` | `9` | 第9版（QT 4.3 ） |
| `QDataStream.Qt_4_4` | `10` | 第10版（QT 4.4 ） |
| `QDataStream.Qt_4_5` | `11` | 版本11 （QT 4.5 ） |
| `QDataStream.Qt_4_6` | `12` | 版本12 （QT 4.6 ， 4.7的Qt ， Qt的4.8 ） |
| `QDataStream.Qt_4_7` | `Qt_4_6` | 同Qt_4_6 。 |
| `QDataStream.Qt_4_8` | `Qt_4_7 Qt_4_9 = Qt_4_8` | 同Qt_4_6 。 |

**See also** [setVersion](qdatastream.html#setVersion)（）和[version](qdatastream.html#version)（ ） 。

* * *

## Method Documentation

```
QDataStream.__init__ (self)
```

构造一个没有I / O设备的数据流。

**See also** [setDevice](qdatastream.html#setDevice)（ ） 。

```
QDataStream.__init__ (self, QIODevice)
```

构造一个使用I / O设备的数据流_d_。

**Warning:**如果你使用[QSocket](index.htm#qsocket) or [QSocketDevice](index.htm#qsocketdevice)作为I / O设备_d_读取数据时，你必须确保有足够的数据可在套接字的操作来顺利进行;[QDataStream](qdatastream.html)没有任何手段来处理或从短读取恢复。

**See also** [setDevice](qdatastream.html#setDevice)（）和[device](qdatastream.html#device)（ ） 。

```
QDataStream.__init__ (self, QByteArray, QIODevice.OpenMode flags)
```

```
QDataStream.__init__ (self, QByteArray)
```

构造一个操作的字节数组上的数据流，_a_。该_mode_描述了设备是如何被使用的。

或者，您也可以使用[QDataStream](qdatastream.html)（常量[QByteArray](qbytearray.html)＆） ，如果你只是想从一个字节数组来读取。

自[QByteArray](qbytearray.html)是不是一个[QIODevice](qiodevice.html)子类，一个内部[QBuffer](qbuffer.html)创建包的字节数组。

```
bool QDataStream.atEnd (self)
```

返回True如果I / O设备已经到达末端位置（流或文件结束），或者如果没有I / O设备一套，否则返回False 。

**See also** [QIODevice.atEnd](qiodevice.html#atEnd)（ ） 。

```
ByteOrder QDataStream.byteOrder (self)
```

[](qdatastream.html#ByteOrder-enum)

[返回当前字节顺序设置 - 无论是](qdatastream.html#ByteOrder-enum)[BigEndian](qdatastream.html#ByteOrder-enum) or [LittleEndian](qdatastream.html#ByteOrder-enum)。

**See also** [setByteOrder](qdatastream.html#setByteOrder)（ ） 。

```
QIODevice QDataStream.device (self)
```

[

返回当前设置的I / O设备，或0，如果没有设备的当前设置。

](qiodevice.html)

[**See also**](qiodevice.html) [setDevice](qdatastream.html#setDevice)（ ） 。

```
FloatingPointPrecision QDataStream.floatingPointPrecision (self)
```

[

返回数据流的浮点精度。

此功能被引入Qt的4.6 。

](qdatastream.html#FloatingPointPrecision-enum)

[**See also**](qdatastream.html#FloatingPointPrecision-enum) [FloatingPointPrecision](qdatastream.html#FloatingPointPrecision-enum)和[setFloatingPointPrecision](qdatastream.html#setFloatingPointPrecision)（ ） 。

```
bool QDataStream.readBool (self)
```

```
str QDataStream.readBytes (self)
```

读取缓冲区_s_从流，并返回一个引用到流。

缓冲区_s_使用分配`new`。与摧毁它`delete[]`运营商。

该_l_参数被设置为缓冲区的长度。如果读取的字符串是空的，_l_被设置为0 ，并_s_设置为空指针。

序列化格式是quint32长度说明符，然后再_l_字节的数据。

**See also** [readRawData](qdatastream.html#readRawData)（）和[writeBytes](qdatastream.html#writeBytes)（ ） 。

```
float QDataStream.readDouble (self)
```

```
float QDataStream.readFloat (self)
```

```
int QDataStream.readInt (self)
```

```
int QDataStream.readInt16 (self)
```

```
int QDataStream.readInt32 (self)
```

```
int QDataStream.readInt64 (self)
```

```
str QDataStream.readInt8 (self)
```

```
QString QDataStream.readQString (self)
```

```
QStringList QDataStream.readQStringList (self)
```

```
QVariant QDataStream.readQVariant (self)
```

```
dict-of-QString-QVariant QDataStream.readQVariantHash (self)
```

```
list-of-QVariant QDataStream.readQVariantList (self)
```

```
dict-of-QString-QVariant QDataStream.readQVariantMap (self)
```

```
str QDataStream.readRawData (self, int len)
```

阅读次数最多_len_从流成字节_s_并返回读取的字节数。如果发生错误，该函数返回-1 。

缓冲区_s_必须预先分配。该数据是_not_编码。

**See also** [readBytes](qdatastream.html#readBytes)（ ）[QIODevice.read](qiodevice.html#read)（）和[writeRawData](qdatastream.html#writeRawData)（ ） 。

```
str QDataStream.readString (self)
```

```
int QDataStream.readUInt16 (self)
```

```
int QDataStream.readUInt32 (self)
```

```
int QDataStream.readUInt64 (self)
```

```
str QDataStream.readUInt8 (self)
```

```
QDataStream.resetStatus (self)
```

重置数据流的状态。

**See also** [Status](qdatastream.html#Status-enum)，[status](qdatastream.html#status)（）和[setStatus](qdatastream.html#setStatus)（ ） 。

```
QDataStream.setByteOrder (self, ByteOrder)
```

设置序列化字节顺序_bo_。

该_bo_参数可以是[QDataStream.BigEndian](qdatastream.html#ByteOrder-enum) or [QDataStream.LittleEndian](qdatastream.html#ByteOrder-enum)。

默认设置为大端。我们建议您保留此设置，除非你有特殊的要求。

**See also** [byteOrder](qdatastream.html#byteOrder)（ ） 。

```
QDataStream.setDevice (self, QIODevice)
```

无效QDataStream.setDevice （[QIODevice](qiodevice.html)* D ）

在I / O设备设置为_d_，它可以是0到未设置到当前的I / O设备。

**See also** [device](qdatastream.html#device)（ ） 。

```
QDataStream.setFloatingPointPrecision (self, FloatingPointPrecision precision)
```

设置数据流的浮点精度_precision_。如果浮点精度[DoublePrecision](qdatastream.html#FloatingPointPrecision-enum)和数据流的版本是[Qt_4_6](qdatastream.html#Version-enum)或更高，所有的浮点数字将被写入和读取与64位精度。如果浮点精度[SinglePrecision](qdatastream.html#FloatingPointPrecision-enum)和版本是[Qt_4_6](qdatastream.html#Version-enum)或更高，所有的浮点数字将被写入和读取与32位精度。

对于之前的版本[Qt_4_6](qdatastream.html#Version-enum)，的数据流中的浮点数的精度取决于流运算符调用。

默认值是[DoublePrecision](qdatastream.html#FloatingPointPrecision-enum)。

**Warning:**此属性必须被设置为相同的值，该值写入对象并读取该数据流的对象。

此功能被引入Qt的4.6 。

**See also** [floatingPointPrecision](qdatastream.html#floatingPointPrecision)（ ） 。

```
QDataStream.setStatus (self, Status status)
```

设置数据流的状态到_status_给出。

后续调用setStatus （）被忽略，直到[resetStatus](qdatastream.html#resetStatus)（）被调用。

**See also** [Status](qdatastream.html#Status-enum)，[status](qdatastream.html#status)（）和[resetStatus](qdatastream.html#resetStatus)（ ） 。

```
QDataStream.setVersion (self, int v)
```

设置数据序列化格式的版本号_v_。

你不_have_设置一个版本，如果你正在使用Qt的最新版本，但对于自己的自定义的二进制格式，我们建议你这样做，见[Versioning](qdatastream.html#versioning)在详细说明。

为了适应新的功能，一些Qt类的数据流的序列化格式在某些版本的Qt已经改变。如果你想读通过的Qt的早期版本创建的数据，或写可以由被与Qt的早期版本编译的程序可以读取数据，使用此功能来修改所使用的序列化格式[QDataStream](qdatastream.html)。

| Qt Version | [QDataStream](qdatastream.html) Version |
| --- | --- |
| Qt 4.6 | 12 |
| Qt 4.5 | 11 |
| Qt 4.4 | 10 |
| Qt 4.3 | 9 |
| Qt 4.2 | 8 |
| Qt 4.0, 4.1 | 7 |
| Qt 3.3 | 6 |
| Qt 3.1, 3.2 | 5 |
| Qt 3.0 | 4 |
| Qt 2.1, 2.2, 2.3 | 3 |
| Qt 2.0 | 2 |
| Qt 1.x | 1 |

该[Version](qdatastream.html#Version-enum)枚举提供了不同版本的Qt的符号常量。例如：

```
 [QDataStream](qdatastream.html) out(file);
 out.setVersion([QDataStream](qdatastream.html).Qt_4_0);

```

**See also** [version](qdatastream.html#version)（）和[Version](qdatastream.html#Version-enum)。

```
int QDataStream.skipRawData (self, int len)
```

跳过_len_从设备字节。返回的错误字节数居然跳过，或-1 。

这等同于调用[readRawData](qdatastream.html#readRawData)（）的长度的缓冲区_len_而忽略了缓冲区。

这个函数是Qt 4.1中引入。

**See also** [QIODevice.seek](qiodevice.html#seek)（ ） 。

```
Status QDataStream.status (self)
```

[

返回数据流的状态。

](qdatastream.html#Status-enum)

[**See also**](qdatastream.html#Status-enum) [Status](qdatastream.html#Status-enum)，[setStatus](qdatastream.html#setStatus)（）和[resetStatus](qdatastream.html#resetStatus)（ ） 。

```
QDataStream.unsetDevice (self)
```

```
int QDataStream.version (self)
```

返回的数据序列化格式的版本号。

**See also** [setVersion](qdatastream.html#setVersion)（）和[Version](qdatastream.html#Version-enum)。

```
QDataStream.writeBool (self, bool i)
```

```
QDataStream QDataStream.writeBytes (self, str)
```

[

写入长度说明_len_和缓冲_s_到流并返回一个引用到流。

该_len_被序列化为一个quint32 ，其次是_len_从字节_s_。注意，该数据是_not_编码。

](qdatastream.html)

[**See also**](qdatastream.html) [writeRawData](qdatastream.html#writeRawData)（）和[readBytes](qdatastream.html#readBytes)（ ） 。

```
QDataStream.writeDouble (self, float f)
```

```
QDataStream.writeFloat (self, float f)
```

```
QDataStream.writeInt (self, int i)
```

```
QDataStream.writeInt16 (self, int i)
```

```
QDataStream.writeInt32 (self, int i)
```

```
QDataStream.writeInt64 (self, int i)
```

```
QDataStream.writeInt8 (self, str i)
```

```
QDataStream.writeQString (self, QString qstr)
```

```
QDataStream.writeQStringList (self, QStringList qstrlst)
```

```
QDataStream.writeQVariant (self, QVariant qvar)
```

```
QDataStream.writeQVariantHash (self, dict-of-QString-QVariant qvarhash)
```

```
QDataStream.writeQVariantList (self, list-of-QVariant qvarlst)
```

```
QDataStream.writeQVariantMap (self, dict-of-QString-QVariant qvarmap)
```

```
int QDataStream.writeRawData (self, str)
```

Writes _len_从字节_s_到流。返回实际写入的字节数，或-1。该数据是_not_编码。

**See also** [writeBytes](qdatastream.html#writeBytes)（ ）[QIODevice.write](qiodevice.html#write)（）和[readRawData](qdatastream.html#readRawData)（ ） 。

```
QDataStream.writeString (self, str str)
```

```
QDataStream.writeUInt16 (self, int i)
```

```
QDataStream.writeUInt32 (self, int i)
```

```
QDataStream.writeUInt64 (self, int i)
```

```
QDataStream.writeUInt8 (self, str i)
```

```
QDataStream __lshift__ (self, QColor)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QNetworkCacheMetaData)
```

[

如果QtNetwork模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QScriptContextInfo)
```

[

如果QtScript模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QWebHistory)
```

[

如果QtWebKit的模块被导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QBrush)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QHostAddress)
```

[

如果QtNetwork模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QCursor cursor)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QFont)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QIcon)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QImage)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QKeySequence ks)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QListWidgetItem item)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QMatrix)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QMatrix4x4)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QPainterPath)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QPalette p)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QPen)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QPicture p)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QPixmap)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QPolygonF array)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QPolygon polygon)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QQuaternion)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QRegion)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QSizePolicy)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QStandardItem item)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QTableWidgetItem item)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QTextLength)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QTextFormat)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QTransform)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QTreeWidgetItem item)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QVector2D)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QVector3D)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __lshift__ (self, QVector4D)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QColor)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QNetworkCacheMetaData)
```

[

如果QtNetwork模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QScriptContextInfo)
```

[

如果QtScript模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QWebHistory)
```

[

如果QtWebKit的模块被导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QBrush)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QHostAddress)
```

[

如果QtNetwork模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QCursor cursor)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QFont)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QIcon)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QImage)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QKeySequence ks)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QListWidgetItem item)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QMatrix)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QMatrix4x4)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QPainterPath)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QPalette p)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QPen)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QPicture p)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QPixmap)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QPolygonF array)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QPolygon polygon)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QQuaternion)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QRegion)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QSizePolicy)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QStandardItem item)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QTableWidgetItem item)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QTextLength)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QTextFormat)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QTransform)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QTreeWidgetItem item)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QVector2D)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QVector3D)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream __rshift__ (self, QVector4D)
```

[

如果QtGui模块导入此方法仅适用。

](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QBitArray)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QByteArray)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QChar)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QDate)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QTime)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QDateTime)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QEasingCurve)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QLine)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QLineF)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QLocale)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QPoint)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QPointF)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QRect)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QRectF)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QRegExp regExp)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QSize)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QSizeF)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QString)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QStringList list)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QUrl)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QUuid)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, QVariant p)
```

[](qdatastream.html)

```
QDataStream QDataStream.__lshift__ (self, Type p)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QBitArray)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QByteArray)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QChar)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QDate)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QTime)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QDateTime)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QEasingCurve)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QLine)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QLineF)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QLocale)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QPoint)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QPointF)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QRect)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QRectF)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QRegExp regExp)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QSize)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QSizeF)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QString)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QStringList list)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QUrl)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QUuid)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, QVariant p)
```

[](qdatastream.html)

```
QDataStream QDataStream.__rshift__ (self, Type p)
```

[](qdatastream.html)