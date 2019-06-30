# QVariant Class Reference

## [[QtCore](index.htm) module]

该的QVariant类的行为像最常见的Qt数据类型的联合。[More...](#details)

### Types

*   `enum Type { Invalid, Bool, Int, UInt, ..., UserType }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, Type type)`
*   `__init__ (self, int typeOrUserType, sip.voidptr copy)`
*   `__init__ (self, QVariant other)`
*   `__init__ (self, object)`
*   `bool canConvert (self, Type t)`
*   `clear (self)`
*   `bool convert (self, Type t)`
*   `sip.voidptr data (self)`
*   `detach (self)`
*   `bool isDetached (self)`
*   `bool isNull (self)`
*   `bool isValid (self)`
*   `load (self, QDataStream ds)`
*   `save (self, QDataStream ds)`
*   `swap (self, QVariant other)`
*   `QBitArray toBitArray (self)`
*   `bool toBool (self)`
*   `QByteArray toByteArray (self)`
*   `QChar toChar (self)`
*   `QDate toDate (self)`
*   `QDateTime toDateTime (self)`
*   `(float, bool ok) toDouble (self)`
*   `QEasingCurve toEasingCurve (self)`
*   `(float, bool ok) toFloat (self)`
*   `dict-of-QString-QVariant toHash (self)`
*   `(int, bool ok) toInt (self)`
*   `QLine toLine (self)`
*   `QLineF toLineF (self)`
*   `list-of-QVariant toList (self)`
*   `QLocale toLocale (self)`
*   `(int, bool ok) toLongLong (self)`
*   `dict-of-QString-QVariant toMap (self)`
*   `QPoint toPoint (self)`
*   `QPointF toPointF (self)`
*   `object toPyObject (self)`
*   `(float, bool ok) toReal (self)`
*   `QRect toRect (self)`
*   `QRectF toRectF (self)`
*   `QRegExp toRegExp (self)`
*   `QSize toSize (self)`
*   `QSizeF toSizeF (self)`
*   `QString toString (self)`
*   `QStringList toStringList (self)`
*   `QTime toTime (self)`
*   `(int, bool ok) toUInt (self)`
*   `(int, bool ok) toULongLong (self)`
*   `QUrl toUrl (self)`
*   `Type type (self)`
*   `str typeName (self)`
*   `int userType (self)`

### Static Methods

*   `QVariant fromList (list-of-QVariant list)`
*   `QVariant fromMap (dict-of-QString-QVariant map)`
*   `Type nameToType (str name)`
*   `str typeToName (Type type)`

### Special Methods

*   `bool __eq__ (self, QVariant v)`
*   `bool __ne__ (self, QVariant v)`

* * *

## Detailed Description

可以使用任何Python对象每当一个[QVariant](qvariant.html)预计。没有人会被解释为无效的QVariant 。

该的QVariant类的行为像最常见的Qt数据类型的联合。

因为C + +不允许从包括具有非默认的构造函数或析构函数类型的工会，最有趣的Qt类不能在工会使用。没有的QVariant ，这将是一个问题[QObject.property](qobject.html#property)（ ）和数据库的工作，等等。

一个的QVariant对象持有一个单一的单个值[type](qvariant.html#type)（）的时间。 （有些[type](qvariant.html#type)（ ） S是多值，例如一个字符串列表。 ）你可以找出哪些类型，T变种持有，使用它转换为不同的类型[convert](qvariant.html#convert)（ ） ，取得使用TOT之一，它的值（ ）函数（例如，[toSize](qvariant.html#toSize)（） ），并检查是否该类型可以使用被转换成特定类型的[canConvert](qvariant.html#canConvert)（ ） 。

名为TOT （）的方法（例如，[toInt](qvariant.html#toInt)（ ）[toString](qvariant.html#toString)（ ） ）是常量。如果你问的存储类型，它们返回的存储对象的一个副本。如果要求，可以从所存储的类型， TOT （ ）的拷贝和转换来生成和叶对象本身不变型。如果你问的是不能从存储的类型生成的类型，其结果取决于类型，详见函数文档。

下面是一些示例代码来演示使用的QVariant的：

```
 [QDataStream](qdatastream.html) out(...);
 QVariant v(123);                // The variant now contains an int
 int x = v.toInt();              // x = 123
 out << v;                       // Writes a type tag and an int to out
 v = QVariant("hello");          // The variant now contains a QByteArray
 v = QVariant(tr("hello"));      // The variant now contains a QString
 int y = v.toInt();              // y = 0 since v cannot be converted to an int
 [QString](qstring.html) s = v.toString();       // s = tr("hello")  (see QObject.tr())
 out << v;                       // Writes a type tag and a QString to out
 ...
 [QDataStream](qdatastream.html) in(...);            // (opening the previously written stream)
 in >> v;                        // Reads an Int variant
 int z = v.toInt();              // z = 123
 qDebug("Type is %s",            // prints "Type is int"
         v.typeName());
 v = v.toInt() + 100;            // The variant now hold the value 223
 v = QVariant([QStringList](qstringlist.html)());

```

你甚至可以存储[QList](index.htm)\u003cQVariant\u003e和[QMap](index.htm)\u003c[QString](qstring.html)在一个变体的QVariant \u003e的值，这样你就可以很容易地构造任意类型的任意复杂的数据结构。这是非常强大和灵活，但可能证明较少的内存和速度效率比存储特定类型的标准数据结构。

的QVariant还支持空值，在那里你可以有一个定义的类型，没有值集的概念。但是请注意，当他们有一个值集的QVariant类型只能被施放。

```
 QVariant x, y([QString](qstring.html)()), z([QString](qstring.html)(""));
 x.convert(QVariant.Int);
 // x.isNull() == true
 // y.isNull() == true, z.isNull() == false

```

的QVariant可以扩展到支持其他类型比在提及[Type](qvariant.html#Type-enum)枚举。请参阅[QMetaType](qmetatype.html)文档。

### A Note on GUI Types

因为是的QVariant的部分[QtCore](index.htm)库，它不能提供转换功能，以定义数据类型[QtGui](index.htm)如[QColor](qcolor.html)，[QImage](qimage.html)和[QPixmap](qpixmap.html)。换句话说，没有`toColor()`功能。相反，你可以使用[QVariant.value](qvariant.html#value)（）或[qvariant_cast](qvariant.html#qvariant_cast)（ ）模板函数。例如：

```
 QVariant variant;
 ...
 [QColor](qcolor.html) color = variant.value<[QColor](qcolor.html)>();

```

逆变换（例如，从[QColor](qcolor.html)到的QVariant ）是自动通过的QVariant支持的所有数据类型，包括GUI相关的类：

```
 [QColor](qcolor.html) color = palette().background().color();
 QVariant variant = color;

```

### Using canConvert() and convert() Consecutively

当使用[canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（）连续，它有可能为[canConvert](qvariant.html#canConvert)（ ）返回True ，但[convert](qvariant.html#convert)（ ）返回False 。这通常是因为[canConvert](qvariant.html#canConvert)（）只报告的QVariant来给出合适的数据类型之间进行转换的一般能力，它仍然是可能的，以提供其实际上不能被转换的数据。

例如，[canConvert](qvariant.html#canConvert)（ ）会叫上一个包含字符串变量的时候，因为在原则上，是的QVariant能够数字字符串转换为整数返回True 。然而，如果字符串中包含非数字字符时，它不能被转换成一个整数，并且任何试图将其转换将失败。因此，有两个函数返回True，对于一个成功的转换是非常重要的。

* * *

## Type Documentation

```
QVariant.Type
```

这个枚举类型定义变量的类型，一个[QVariant](qvariant.html)可以包含。

| Constant | Value | Description |
| --- | --- | --- |
| `QVariant.Invalid` | `0` | 没有类型 |
| `QVariant.BitArray` | `13` | 一[QBitArray](qbitarray.html) |
| `QVariant.Bitmap` | `73` | 一[QBitmap](qbitmap.html) |
| `QVariant.Bool` | `1` | 一个bool |
| `QVariant.Brush` | `66` | 一[QBrush](qbrush.html) |
| `QVariant.ByteArray` | `12` | 一[QByteArray](qbytearray.html) |
| `QVariant.Char` | `7` | 一[QChar](qchar.html) |
| `QVariant.Color` | `67` | 一[QColor](qcolor.html) |
| `QVariant.Cursor` | `74` | 一[QCursor](qcursor.html) |
| `QVariant.Date` | `14` | 一[QDate](qdate.html) |
| `QVariant.DateTime` | `16` | 一[QDateTime](qdatetime.html) |
| `QVariant.Double` | `6` | 双 |
| `QVariant.EasingCurve` | `29` | 一[QEasingCurve](qeasingcurve.html) |
| `QVariant.Font` | `64` | 一[QFont](qfont.html) |
| `QVariant.Hash` | `28` | 一[QVariantHash](qvariant.html#QVariantHash-typedef) |
| `QVariant.Icon` | `69` | 一[QIcon](qicon.html) |
| `QVariant.Image` | `70` | 一[QImage](qimage.html) |
| `QVariant.Int` | `2` | 一个int |
| `QVariant.KeySequence` | `76` | 一[QKeySequence](qkeysequence.html) |
| `QVariant.Line` | `23` | 一[QLine](qline.html) |
| `QVariant.LineF` | `24` | 一[QLineF](qlinef.html) |
| `QVariant.List` | `9` | 一[QVariantList](qvariant.html#QVariantList-typedef) |
| `QVariant.Locale` | `18` | 一[QLocale](qlocale.html) |
| `QVariant.LongLong` | `4` | 一[qlonglong](index.htm#qlonglong-typedef) |
| `QVariant.Map` | `8` | 一[QVariantMap](qvariant.html#QVariantMap-typedef) |
| `QVariant.Matrix` | `80` | 一[QMatrix(obsolete)](qmatrix.html) |
| `QVariant.Transform` | `81` | 一[QTransform](qtransform.html) |
| `QVariant.Matrix4x4` | `82` | 一[QMatrix4x4](qmatrix4x4.html) |
| `QVariant.Palette` | `68` | 一[QPalette](qpalette.html) |
| `QVariant.Pen` | `77` | 一[QPen](qpen.html) |
| `QVariant.Pixmap` | `65` | 一[QPixmap](qpixmap.html) |
| `QVariant.Point` | `25` | 一[QPoint](qpoint.html) |
| `QVariant.PointArray` | `Polygon` | 一[QPointArray](index.htm#qpointarray) |
| `QVariant.PointF` | `26` | 一[QPointF](qpointf.html) |
| `QVariant.Polygon` | `71` | 一[QPolygon](qpolygon.html) |
| `QVariant.Quaternion` | `86` | 一[QQuaternion](qquaternion.html) |
| `QVariant.Rect` | `19` | 一[QRect](qrect.html) |
| `QVariant.RectF` | `20` | 一[QRectF](qrectf.html) |
| `QVariant.RegExp` | `27` | 一[QRegExp](qregexp.html) |
| `QVariant.Region` | `72` | 一[QRegion](qregion.html) |
| `QVariant.Size` | `21` | 一[QSize](qsize.html) |
| `QVariant.SizeF` | `22` | 一[QSizeF](qsizef.html) |
| `QVariant.SizePolicy` | `75` | 一[QSizePolicy](qsizepolicy.html) |
| `QVariant.String` | `10` | 一[QString](qstring.html) |
| `QVariant.StringList` | `11` | 一[QStringList](qstringlist.html) |
| `QVariant.TextFormat` | `79` | 一[QTextFormat](qtextformat.html) |
| `QVariant.TextLength` | `78` | 一[QTextLength](qtextlength.html) |
| `QVariant.Time` | `15` | 一[QTime](qtime.html) |
| `QVariant.UInt` | `3` | 一[uint](index.htm#uint-typedef) |
| `QVariant.ULongLong` | `5` | 一[qulonglong](index.htm#qulonglong-typedef) |
| `QVariant.Url` | `17` | 一[QUrl](qurl.html) |
| `QVariant.Vector2D` | `83` | 一[QVector2D](qvector2d.html) |
| `QVariant.Vector3D` | `84` | 一[QVector3D](qvector3d.html) |
| `QVariant.Vector4D` | `85` | 一[QVector4D](qvector4d.html) |
| `QVariant.UserType` | `127` | 对于用户自定义类型的基础值。 |

* * *

## Method Documentation

```
QVariant.__init__ (self)
```

构造一个无效的变体。

```
QVariant.__init__ (self, Type type)
```

构造类型的空变种_type_。

```
QVariant.__init__ (self, int typeOrUserType, sip.voidptr copy)
```

构造类型的变种_typeOrUserType_以及与初始化_copy_如果_copy_不为0。

请注意，你必须通过你想要保存的变量的地址。

通常情况下，你从来没有使用此构造函数，使用[QVariant.fromValue](qvariant.html#fromValue)（ ）而不是由所代表的指针类型构造变形`QMetaType.VoidStar`，`QMetaType.QObjectStar`和`QMetaType.QWidgetStar`。

**See also** [QVariant.fromValue](qvariant.html#fromValue)（）和[Type](qvariant.html#Type-enum)。

```
QVariant.__init__ (self, QVariant other)
```

```
QVariant.__init__ (self, object)
```

构造变形的副本，_p_，作为参数传递给此构造函数。

```
bool QVariant.canConvert (self, Type t)
```

返回True如果变量的类型可以转换为所请求的类型，_t_。当调用此类铸件是自动完成的[toInt](qvariant.html#toInt)（ ）[toBool](qvariant.html#toBool)（ ），...的方法。

下面的类型转换是自动完成的：

| Type | Automatically Cast To |
| --- | --- |
| [Bool](qvariant.html#Type-enum) | [Char](qvariant.html#Type-enum), [Double](qvariant.html#Type-enum), [Int](qvariant.html#Type-enum), [LongLong](qvariant.html#Type-enum), [String](qvariant.html#Type-enum), [UInt](qvariant.html#Type-enum), [ULongLong](qvariant.html#Type-enum) |
| [ByteArray](qvariant.html#Type-enum) | [Double](qvariant.html#Type-enum), [Int](qvariant.html#Type-enum), [LongLong](qvariant.html#Type-enum), [String](qvariant.html#Type-enum), [UInt](qvariant.html#Type-enum), [ULongLong](qvariant.html#Type-enum) |
| [Char](qvariant.html#Type-enum) | [Bool](qvariant.html#Type-enum), [Int](qvariant.html#Type-enum), [UInt](qvariant.html#Type-enum), [LongLong](qvariant.html#Type-enum), [ULongLong](qvariant.html#Type-enum) |
| [Color](qvariant.html#Type-enum) | [String](qvariant.html#Type-enum) |
| [Date](qvariant.html#Type-enum) | [DateTime](qvariant.html#Type-enum), [String](qvariant.html#Type-enum) |
| [DateTime](qvariant.html#Type-enum) | [Date](qvariant.html#Type-enum), [String](qvariant.html#Type-enum), [Time](qvariant.html#Type-enum) |
| [Double](qvariant.html#Type-enum) | [Bool](qvariant.html#Type-enum), [Int](qvariant.html#Type-enum), [LongLong](qvariant.html#Type-enum), [String](qvariant.html#Type-enum), [UInt](qvariant.html#Type-enum), [ULongLong](qvariant.html#Type-enum) |
| [Font](qvariant.html#Type-enum) | [String](qvariant.html#Type-enum) |
| [Int](qvariant.html#Type-enum) | [Bool](qvariant.html#Type-enum), [Char](qvariant.html#Type-enum), [Double](qvariant.html#Type-enum), [LongLong](qvariant.html#Type-enum), [String](qvariant.html#Type-enum), [UInt](qvariant.html#Type-enum), [ULongLong](qvariant.html#Type-enum) |
| [KeySequence](qvariant.html#Type-enum) | [Int](qvariant.html#Type-enum), [String](qvariant.html#Type-enum) |
| [List](qvariant.html#Type-enum) | [StringList](qvariant.html#Type-enum) (if the list's items can be converted to strings) |
| [LongLong](qvariant.html#Type-enum) | [Bool](qvariant.html#Type-enum), [ByteArray](qvariant.html#Type-enum), [Char](qvariant.html#Type-enum), [Double](qvariant.html#Type-enum), [Int](qvariant.html#Type-enum), [String](qvariant.html#Type-enum), [UInt](qvariant.html#Type-enum), [ULongLong](qvariant.html#Type-enum) |
| [Point](qvariant.html#Type-enum) | [PointF](qvariant.html#Type-enum) |
| [Rect](qvariant.html#Type-enum) | [RectF](qvariant.html#Type-enum) |
| [String](qvariant.html#Type-enum) | [Bool](qvariant.html#Type-enum), [ByteArray](qvariant.html#Type-enum), [Char](qvariant.html#Type-enum), [Color](qvariant.html#Type-enum), [Date](qvariant.html#Type-enum), [DateTime](qvariant.html#Type-enum), [Double](qvariant.html#Type-enum), [Font](qvariant.html#Type-enum), [Int](qvariant.html#Type-enum), [KeySequence](qvariant.html#Type-enum), [LongLong](qvariant.html#Type-enum), [StringList](qvariant.html#Type-enum), [Time](qvariant.html#Type-enum), [UInt](qvariant.html#Type-enum), [ULongLong](qvariant.html#Type-enum) |
| [StringList](qvariant.html#Type-enum) | [List](qvariant.html#Type-enum), [String](qvariant.html#Type-enum) (if the list contains exactly one item) |
| [Time](qvariant.html#Type-enum) | [String](qvariant.html#Type-enum) |
| [UInt](qvariant.html#Type-enum) | [Bool](qvariant.html#Type-enum), [Char](qvariant.html#Type-enum), [Double](qvariant.html#Type-enum), [Int](qvariant.html#Type-enum), [LongLong](qvariant.html#Type-enum), [String](qvariant.html#Type-enum), [ULongLong](qvariant.html#Type-enum) |
| [ULongLong](qvariant.html#Type-enum) | [Bool](qvariant.html#Type-enum), [Char](qvariant.html#Type-enum), [Double](qvariant.html#Type-enum), [Int](qvariant.html#Type-enum), [LongLong](qvariant.html#Type-enum), [String](qvariant.html#Type-enum), [UInt](qvariant.html#Type-enum) |

**See also** [convert](qvariant.html#convert)（ ） 。

```
QVariant.clear (self)
```

转换这个变种输入无效，并释放使用的资源。

```
bool QVariant.convert (self, Type t)
```

注塑变种所请求的类型，_t_。如果转换无法完成，该变种被清除。返回True如果变量的当前类型已成功投，否则返回False 。

**Warning:**由于历史的原因，将空[QVariant](qvariant.html)结果在所希望的类型（例如，一个空字符串的空值[QString](qstring.html)）和虚假的结果。

**See also** [canConvert](qvariant.html#canConvert)（）和[clear](qvariant.html#clear)（ ） 。

```
sip.voidptr QVariant.data (self)
```

```
QVariant.detach (self)
```

```
QVariant QVariant.fromList (list-of-QVariant list)
```

```
QVariant QVariant.fromMap (dict-of-QString-QVariant map)
```

```
bool QVariant.isDetached (self)
```

```
bool QVariant.isNull (self)
```

返回True如果这是一个空变量，否则返回False。

```
bool QVariant.isValid (self)
```

返回True如果这个变种的存储类型是不[QVariant.Invalid](qvariant.html#Type-enum)否则返回False 。

```
QVariant.load (self, QDataStream ds)
```

```
Type QVariant.nameToType (str name)
```

[

在给定的存储类型的字符串表示形式转换_name_，其枚举表示。

如果字符串表示不能转换为任何枚举表示，变量被设置为`Invalid`。

```
QVariant.save (self, QDataStream ds)
```

```
QVariant.swap (self, QVariant other)
```

掉期变种_other_这种变体。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

](index.htm#Type-enum)

```
QBitArray QVariant.toBitArray (self)
```

[](qbitarray.html)

[返回变量作为](qbitarray.html)[QBitArray](qbitarray.html)如果该变体具有[type](qvariant.html#type)（ ）[BitArray](qvariant.html#Type-enum)否则返回一个空的位阵列。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
bool QVariant.toBool (self)
```

返回变量为bool如果有变异[type](qvariant.html#type)（ ）布尔。

如果变量有，则返回True[type](qvariant.html#type)（ ）[Bool](qvariant.html#Type-enum)，[Char](qvariant.html#Type-enum)，[Double](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)，[LongLong](qvariant.html#Type-enum)，[UInt](qvariant.html#Type-enum)或[ULongLong](qvariant.html#Type-enum)和的值是非零，或者如果所述变体的类型为[String](qvariant.html#Type-enum) or [ByteArray](qvariant.html#Type-enum)和其小写内容不为空， “0”或“假” ，否则返回假。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QByteArray QVariant.toByteArray (self)
```

[](qbytearray.html)

[返回变量作为](qbytearray.html)[QByteArray](qbytearray.html)如果该变体具有[type](qvariant.html#type)（ ）[ByteArray](qvariant.html#Type-enum) or [String](qvariant.html#Type-enum)使用（兑换[QString.fromAscii](qstring.html#fromAscii)（ ） ） ，否则返回一个空字节数组。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QChar QVariant.toChar (self)
```

返回变量作为[QChar](qchar.html)如果该变体具有[type](qvariant.html#type)（ ）[Char](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)或[UInt](qvariant.html#Type-enum)否则返回一个无效的[QChar](qchar.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QDate QVariant.toDate (self)
```

[](qdate.html)

[返回变量作为](qdate.html)[QDate](qdate.html)如果该变体具有[type](qvariant.html#type)（ ）[Date](qvariant.html#Type-enum)，[DateTime](qvariant.html#Type-enum)或[String](qvariant.html#Type-enum)否则返回一个无效的日期。

如果[type](qvariant.html#type)（）是[String](qvariant.html#Type-enum)，一个无效的日期，如果该字符串不能解析为一个将被退回[Qt.ISODate](qt.html#DateFormat-enum)格式的日期。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QDateTime QVariant.toDateTime (self)
```

[](qdatetime.html)

[返回变量作为](qdatetime.html)[QDateTime](qdatetime.html)如果该变体具有[type](qvariant.html#type)（ ）[DateTime](qvariant.html#Type-enum)，[Date](qvariant.html#Type-enum)或[String](qvariant.html#Type-enum)否则返回一个无效的日期/时间。

如果[type](qvariant.html#type)（）是[String](qvariant.html#Type-enum)，一个无效的日期/时间，如果该字符串不能解析为一个将被退回[Qt.ISODate](qt.html#DateFormat-enum)格式的日期/时间。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
(float, bool ok) QVariant.toDouble (self)
```

返回变体作为双如果所述变体具有[type](qvariant.html#type)（ ）[Double](qvariant.html#Type-enum)，[QMetaType.Float](qmetatype.html#Type-enum)，[Bool](qvariant.html#Type-enum)，[ByteArray](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)，[LongLong](qvariant.html#Type-enum)，[String](qvariant.html#Type-enum)，[UInt](qvariant.html#Type-enum)或[ULongLong](qvariant.html#Type-enum)否则返回0.0 。

If _ok_不为null ：`*`_ok_被设置为True，如果该值可以转换为double ，否则`*`_ok_设置为False 。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QEasingCurve QVariant.toEasingCurve (self)
```

[](qeasingcurve.html)

[返回变量作为](qeasingcurve.html)[QEasingCurve](qeasingcurve.html)如果该变体具有[type](qvariant.html#type)（ ）[EasingCurve](qvariant.html#Type-enum)否则返回一个默认的缓动曲线。

此功能被引入Qt的4.7 。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
(float, bool ok) QVariant.toFloat (self)
```

返回变量为float ，如果该变体具有[type](qvariant.html#type)（ ）[Double](qvariant.html#Type-enum)，[QMetaType.Float](qmetatype.html#Type-enum)，[Bool](qvariant.html#Type-enum)，[ByteArray](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)，[LongLong](qvariant.html#Type-enum)，[String](qvariant.html#Type-enum)，[UInt](qvariant.html#Type-enum)或[ULongLong](qvariant.html#Type-enum)否则返回0.0 。

If _ok_不为null ：`*`_ok_被设置为True，如果该值可以转换为double ，否则`*`_ok_设置为False 。

此功能被引入Qt的4.6 。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
dict-of-QString-QVariant QVariant.toHash (self)
```

返回变量作为[QHash](index.htm)\u003c[QString](qstring.html)，[QVariant](qvariant.html)\u003e如果所述变体具有[type](qvariant.html#type)（ ）[Hash](qvariant.html#Type-enum)否则返回一个空映射。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
(int, bool ok) QVariant.toInt (self)
```

返回变量为int如果该变体具有[type](qvariant.html#type)（ ）[Int](qvariant.html#Type-enum)，[Bool](qvariant.html#Type-enum)，[ByteArray](qvariant.html#Type-enum)，[Char](qvariant.html#Type-enum)，[Double](qvariant.html#Type-enum)，[LongLong](qvariant.html#Type-enum)，[String](qvariant.html#Type-enum)，[UInt](qvariant.html#Type-enum)或[ULongLong](qvariant.html#Type-enum)否则返回0 。

If _ok_不为null ：`*`_ok_被设置为True，如果该值可以转换为int ，否则`*`_ok_设置为False 。

**Warning:**如果该值可以转换为一个[LongLong](qvariant.html#Type-enum)但过大的一个int来表示，由此产生的算术溢出将不会反映在_ok_。一个简单的解决方法是使用[QString.toInt](qstring.html#toInt)（ ） 。修复这个bug已经被推迟到5的Qt为了避免破坏现有的代码。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QLine QVariant.toLine (self)
```

[](qline.html)

[返回变量作为](qline.html)[QLine](qline.html)如果该变体具有[type](qvariant.html#type)（ ）[Line](qvariant.html#Type-enum)否则返回一个无效的[QLine](qline.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QLineF QVariant.toLineF (self)
```

[](qlinef.html)

[返回变量作为](qlinef.html)[QLineF](qlinef.html)如果该变体具有[type](qvariant.html#type)（ ）[LineF](qvariant.html#Type-enum)否则返回一个无效的[QLineF](qlinef.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
list-of-QVariant QVariant.toList (self)
```

返回变量作为[QVariantList](qvariant.html#QVariantList-typedef)如果该变体具有[type](qvariant.html#type)（ ）[List](qvariant.html#Type-enum) or [StringList](qvariant.html#Type-enum)否则返回空列表。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QLocale QVariant.toLocale (self)
```

[](qlocale.html)

[返回变量作为](qlocale.html)[QLocale](qlocale.html)如果该变体具有[type](qvariant.html#type)（ ）[Locale](qvariant.html#Type-enum)否则返回一个无效的[QLocale](qlocale.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
(int, bool ok) QVariant.toLongLong (self)
```

返回变量为long long int的，如果有变异[type](qvariant.html#type)（ ）[LongLong](qvariant.html#Type-enum)，[Bool](qvariant.html#Type-enum)，[ByteArray](qvariant.html#Type-enum)，[Char](qvariant.html#Type-enum)，[Double](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)，[String](qvariant.html#Type-enum)，[UInt](qvariant.html#Type-enum)或[ULongLong](qvariant.html#Type-enum)否则返回0 。

If _ok_不为null ：`*``ok`被设置为True，如果该值可以转换为int ，否则`*``ok`设置为False 。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
dict-of-QString-QVariant QVariant.toMap (self)
```

返回变量作为[QMap](index.htm)\u003c[QString](qstring.html)，[QVariant](qvariant.html)\u003e如果所述变体具有[type](qvariant.html#type)（ ）[Map](qvariant.html#Type-enum)否则返回一个空映射。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QPoint QVariant.toPoint (self)
```

[](qpoint.html)

[返回变量作为](qpoint.html)[QPoint](qpoint.html)如果该变体具有[type](qvariant.html#type)（ ）[Point](qvariant.html#Type-enum) or [PointF](qvariant.html#Type-enum)否则返回空[QPoint](qpoint.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QPointF QVariant.toPointF (self)
```

[](qpointf.html)

[返回变量作为](qpointf.html)[QPointF](qpointf.html)如果该变体具有[type](qvariant.html#type)（ ）[Point](qvariant.html#Type-enum) or [PointF](qvariant.html#Type-enum)否则返回空[QPointF](qpointf.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
object QVariant.toPyObject (self)
```

```
(float, bool ok) QVariant.toReal (self)
```

返回变体作为QREAL如果​​所述变体具有[type](qvariant.html#type)（ ）[Double](qvariant.html#Type-enum)，[QMetaType.Float](qmetatype.html#Type-enum)，[Bool](qvariant.html#Type-enum)，[ByteArray](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)，[LongLong](qvariant.html#Type-enum)，[String](qvariant.html#Type-enum)，[UInt](qvariant.html#Type-enum)或[ULongLong](qvariant.html#Type-enum)否则返回0.0 。

If _ok_不为null ：`*`_ok_被设置为True，如果该值可以转换为double ，否则`*`_ok_设置为False 。

此功能被引入Qt的4.6 。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QRect QVariant.toRect (self)
```

[](qrect.html)

[返回变量作为](qrect.html)[QRect](qrect.html)如果该变体具有[type](qvariant.html#type)（ ）[Rect](qvariant.html#Type-enum)否则返回一个无效的[QRect](qrect.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QRectF QVariant.toRectF (self)
```

[](qrectf.html)

[返回变量作为](qrectf.html)[QRectF](qrectf.html)如果该变体具有[type](qvariant.html#type)（ ）[Rect](qvariant.html#Type-enum) or [RectF](qvariant.html#Type-enum)否则返回一个无效的[QRectF](qrectf.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QRegExp QVariant.toRegExp (self)
```

[](qregexp.html)

[返回变量作为](qregexp.html)[QRegExp](qregexp.html)如果该变体具有[type](qvariant.html#type)（ ）[RegExp](qvariant.html#Type-enum)否则返回一个空[QRegExp](qregexp.html)。

这个函数是Qt 4.1中引入。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QSize QVariant.toSize (self)
```

[](qsize.html)

[返回变量作为](qsize.html)[QSize](qsize.html)如果该变体具有[type](qvariant.html#type)（ ）[Size](qvariant.html#Type-enum)否则返回一个无效的[QSize](qsize.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QSizeF QVariant.toSizeF (self)
```

[](qsizef.html)

[返回变量作为](qsizef.html)[QSizeF](qsizef.html)如果该变体具有[type](qvariant.html#type)（ ）[SizeF](qvariant.html#Type-enum)否则返回一个无效的[QSizeF](qsizef.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QString QVariant.toString (self)
```

返回变量作为[QString](qstring.html)如果该变体具有[type](qvariant.html#type)（ ）[String](qvariant.html#Type-enum)，[Bool](qvariant.html#Type-enum)，[ByteArray](qvariant.html#Type-enum)，[Char](qvariant.html#Type-enum)，[Date](qvariant.html#Type-enum)，[DateTime](qvariant.html#Type-enum)，[Double](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)，[LongLong](qvariant.html#Type-enum)，[StringList](qvariant.html#Type-enum)，[Time](qvariant.html#Type-enum)，[UInt](qvariant.html#Type-enum)或[ULongLong](qvariant.html#Type-enum)否则返回一个空字符串。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QStringList QVariant.toStringList (self)
```

返回变量作为[QStringList](qstringlist.html)如果该变体具有[type](qvariant.html#type)（ ）[StringList](qvariant.html#Type-enum)，[String](qvariant.html#Type-enum)或[List](qvariant.html#Type-enum)这可以转换为一个类型的[QString](qstring.html)否则返回空列表。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QTime QVariant.toTime (self)
```

[](qtime.html)

[返回变量作为](qtime.html)[QTime](qtime.html)如果该变体具有[type](qvariant.html#type)（ ）[Time](qvariant.html#Type-enum)，[DateTime](qvariant.html#Type-enum)或[String](qvariant.html#Type-enum)否则返回一个无效的时间。

如果[type](qvariant.html#type)（）是[String](qvariant.html#Type-enum)，一个无效的时间，如果该字符串不能解析为一个将被退回[Qt.ISODate](qt.html#DateFormat-enum)格式时间。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
(int, bool ok) QVariant.toUInt (self)
```

返回变量为一个unsigned int如果该变体具有[type](qvariant.html#type)（ ）[UInt](qvariant.html#Type-enum)，[Bool](qvariant.html#Type-enum)，[ByteArray](qvariant.html#Type-enum)，[Char](qvariant.html#Type-enum)，[Double](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)，[LongLong](qvariant.html#Type-enum)，[String](qvariant.html#Type-enum)或[ULongLong](qvariant.html#Type-enum)否则返回0 。

If _ok_不为null ：`*`_ok_被设置为True，如果该值可以转换为一个unsigned int ，否则`*`_ok_设置为False 。

**Warning:**如果该值可以转换为一个[ULongLong](qvariant.html#Type-enum)但过大的一个unsigned int来表示，由此产生的算术溢出将不会反映在_ok_。一个简单的解决方法是使用[QString.toUInt](qstring.html#toUInt)（ ） 。修复这个bug已经被推迟到5的Qt为了避免破坏现有的代码。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
(int, bool ok) QVariant.toULongLong (self)
```

返回变体为unsigned long long int的，如果有变异[type](qvariant.html#type)（ ）[ULongLong](qvariant.html#Type-enum)，[Bool](qvariant.html#Type-enum)，[ByteArray](qvariant.html#Type-enum)，[Char](qvariant.html#Type-enum)，[Double](qvariant.html#Type-enum)，[Int](qvariant.html#Type-enum)，[LongLong](qvariant.html#Type-enum)，[String](qvariant.html#Type-enum)或[UInt](qvariant.html#Type-enum)否则返回0 。

If _ok_不为null ：`*`_ok_被设置为True，如果该值可以转换为int ，否则`*`_ok_设置为False 。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
QUrl QVariant.toUrl (self)
```

[](qurl.html)

[返回变量作为](qurl.html)[QUrl](qurl.html)如果该变体具有[type](qvariant.html#type)（ ）[Url](qvariant.html#Type-enum)否则返回一个无效的[QUrl](qurl.html)。

**See also** [canConvert](qvariant.html#canConvert)（）和[convert](qvariant.html#convert)（ ） 。

```
Type QVariant.type (self)
```

[](index.htm#Type-enum)

[返回存储在变量值的存储类型。虽然这个函数被声明为返回](index.htm#Type-enum)[QVariant.Type](qvariant.html#Type-enum)，返回值应解释为[QMetaType.Type](qmetatype.html#Type-enum)。特别地，[QVariant.UserType](qvariant.html#Type-enum)这里只返回该值是否等于或大于[QMetaType.User](qmetatype.html#Type-enum)。

请注意，在该范围内的返回值[QVariant.Char](qvariant.html#Type-enum)通过[QVariant.RegExp](qvariant.html#Type-enum)和[QVariant.Font](qvariant.html#Type-enum)通过[QVariant.Transform](qvariant.html#Type-enum)对应于在范围中的值[QMetaType.QChar](qmetatype.html#Type-enum)通过[QMetaType.QRegExp](qmetatype.html#Type-enum)和[QMetaType.QFont](qmetatype.html#Type-enum)通过[QMetaType.QQuaternion](qmetatype.html#Type-enum)。

用char工作时，要特别注意和[QChar](qchar.html)变种。需要注意的是，没有[QVariant](qvariant.html)构造函数专门为char类型，但有一个用于[QChar](qchar.html)。对于类型的变体[QChar](qchar.html)，这个函数返回[QVariant.Char](qvariant.html#Type-enum)，这是相同的[QMetaType.QChar](qmetatype.html#Type-enum)，但是对于类型的变体`char`，这个函数返回[QMetaType.Char](qmetatype.html#Type-enum)，这是_not_一样[QVariant.Char](qvariant.html#Type-enum)。

还要注意的是类型`void*`，`long`，`short`，`unsigned` `long`，`unsigned` `short`，`unsigned` `char`，`float`，`QObject*`和`QWidget*`都派代表参加[QMetaType.Type](qmetatype.html#Type-enum)但不是在[QVariant.Type](qvariant.html#Type-enum)，并且它们可以由该函数返回。然而，它们都被认为是用户定义的类型时，对测试[QVariant.Type](qvariant.html#Type-enum)。

为了测试是否实例[QVariant](qvariant.html)包含与你感兴趣的数据类型，使用兼容的数据类型[canConvert](qvariant.html#canConvert)（ ） 。

```
str QVariant.typeName (self)
```

返回存储在所述变体的类型的名称。返回的字符串描述了C + +的数据类型来存储数据：例如， “[QFont](qfont.html)“，”[QString](qstring.html)“或”[QVariantList](qvariant.html#QVariantList-typedef)“一个无效的变量返回0 。

```
str QVariant.typeToName (Type type)
```

存储类型的枚举表示转换，_typ_，其字符串表示形式。

返回一个空指针的类型是[QVariant.Invalid](qvariant.html#Type-enum)或不存在。

```
int QVariant.userType (self)
```

返回存储在变量值的存储类型。对于非用户类型，这是相同的[type](qvariant.html#type)（ ） 。

**See also** [type](qvariant.html#type)（ ） 。

```
bool QVariant.__eq__ (self, QVariant v)
```

```
bool QVariant.__ne__ (self, QVariant v)
```