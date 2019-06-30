# QStringList Class Reference

## [[QtCore](index.htm) module]

QStringList中的类提供的字符串列表。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString i)`
*   `__init__ (self, QStringList l)`
*   `append (self, QString str)`
*   `clear (self)`
*   `bool contains (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int count (self, QString str)`
*   `int count (self)`
*   `QStringList filter (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QStringList filter (self, QRegExp rx)`
*   `QString first (self)`
*   `int indexOf (self, QString value, int from = 0)`
*   `int indexOf (self, QRegExp rx, int from = 0)`
*   `insert (self, int i, QString str)`
*   `bool isEmpty (self)`
*   `QString join (self, QString sep)`
*   `QString last (self)`
*   `int lastIndexOf (self, QString value, int from = -1)`
*   `int lastIndexOf (self, QRegExp rx, int from = -1)`
*   `QStringList mid (self, int pos, int length = -1)`
*   `move (self, int from, int to)`
*   `prepend (self, QString str)`
*   `int removeAll (self, QString str)`
*   `removeAt (self, int i)`
*   `int removeDuplicates (self)`
*   `replace (self, int i, QString str)`
*   `QStringList replaceInStrings (self, QString before, QString after, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QStringList replaceInStrings (self, QRegExp rx, QString after)`
*   `sort (self)`
*   `swap (self, int i, int j)`
*   `QString takeAt (self, int i)`
*   `QString takeFirst (self)`
*   `QString takeLast (self)`

### Special Methods

*   `QStringList __add__ (self, QStringList other)`
*   `int __contains__ (self, QString str)`
*   `__delitem__ (self, int i)`
*   `__delitem__ (self, slice slice)`
*   `bool __eq__ (self, QStringList other)`
*   `QString __getitem__ (self, int i)`
*   `QStringList __getitem__ (self, slice slice)`
*   `QStringList __iadd__ (self, QStringList other)`
*   `QStringList __iadd__ (self, QString value)`
*   `QStringList __imul__ (self, int by)`
*   `__len__ (self)`
*   `QStringList __lshift__ (self, QString str)`
*   `QStringList __lshift__ (self, QStringList l)`
*   `QStringList __mul__ (self, int by)`
*   `bool __ne__ (self, QStringList other)`
*   `__setitem__ (self, int i, QString str)`
*   `__setitem__ (self, slice slice, QStringList list)`

* * *

## Detailed Description

Python字符串或Unicode对象的Python列表或[QString](qstring.html)实例可用于每当一个[QStringList](qstringlist.html)预计。

QStringList中的类提供的字符串列表。

QStringList中的继承[QList](index.htm)\u003c[QString](qstring.html)\u003e 。喜欢[QList](index.htm)， QStringList中是[implicitly shared](index.htm#implicitly-shared)。它提供了快速基于索引的访问以及快速插入和删除。传递字符串列表作为值参数既快速又安全。

所有[QList](index.htm)的功能也适用于QStringList中。例如，您可以使用[isEmpty](index.htm#isEmpty)（ ）来测试列表是否为空，你可以调用函数如[append](index.htm#append)（ ）[prepend](index.htm#prepend)（ ）[insert](index.htm#insert)（ ）[replace](index.htm#replace)（ ）[removeAll](index.htm#removeAll)（ ）[removeAt](index.htm#removeAt)（ ）[removeFirst](index.htm#removeFirst)（ ）[removeLast](index.htm#removeLast)（）和[removeOne](index.htm#removeOne)（ ）来修改一个QStringList中。此外， QStringList中提供了一些方便的功能，使操作字符串容易列表：

### Adding strings

字符串可以使用被添加到列表中的[append()](index.htm#append)，[operator+=](index.htm#operator-2b-eq)（）和[operator&lt;&lt;](qstringlist.html#operator-lt-lt)（）函数。例如：

```
     QStringList fonts;
     fonts << "Arial" << "Helvetica" << "Times" << "Courier";

```

### Iterating over the strings

遍历一个列表，你可以使用的索引位置，或[QList](index.htm)的Java风格和STL风格的迭代器类型：

索引：

```
     for (int i = 0; i < fonts.size(); ++i)
          cout << fonts.at(i).toLocal8Bit().constData() << endl;

```

Java风格的迭代器：

```
     [QStringListIterator](qstringlist.html#QStringListIterator-typedef) javaStyleIterator(fonts);
     while (javaStyleIterator.hasNext())
          cout << javaStyleIterator.next().toLocal8Bit().constData() << endl;

```

STL风格的迭代器：

```
     QStringList.const_iterator constIterator;
     for (constIterator = fonts.constBegin(); constIterator != fonts.constEnd();
            ++constIterator)
         cout << (*constIterator).toLocal8Bit().constData() << endl;

```

该[QStringListIterator](qstringlist.html#QStringListIterator-typedef)类只是一个类型定义[QListIterator](index.htm)\u003c[QString](qstring.html)\u003e 。 QStringList中还提供了[QMutableStringListIterator](qstringlist.html#QMutableStringListIterator-typedef)类，这是一个类型定义[QMutableListIterator](index.htm)\u003c[QString](qstring.html)\u003e 。

### Manipulating the strings

QStringList中提供了几个功能，让你操作一个列表的内容。您可以使用串连在一个字符串列表转换成一个字符串的所有字符串（带有可选的分隔符）的[join](qstringlist.html#join)（）函数。例如：

```
     [QString](qstring.html) str = fonts.join(",");
      // str == "Arial,Helvetica,Times,Courier"

```

打破一个字符串转换成一个字符串列表，使用[QString.split](qstring.html#split)（ ）函数：

```
     QStringList list;
     list = str.split(",");
      // list: ["Arial", "Helvetica", "Times", "Courier"]

```

该参数分割可以是单个字符，字符串，或[QRegExp](qregexp.html)。

此外，该[operator+](qstringlist.html#operator-2b)（ ）功能可让您连接两个字符串列表为一体。要排序的字符串列表，使用[sort](qstringlist.html#sort)（）函数。

[QString](qstring.html)名单中还提供了[filter](qstringlist.html#filter)（ ）函数，它可以让你提取一个新的列表，其中包含只有那些包含特定字符串（或匹配特定的正则表达式）字符串：

```
     QStringList monospacedFonts = fonts.filter([QRegExp](qregexp.html)("Courier|Fixed"));

```

该[contains](qstringlist.html#contains)（ ）函数告诉你的列表中是否包含给定的字符串，而[indexOf](qstringlist.html#indexOf)（ ）函数返回给定字符串的第一个匹配项的索引。该[lastIndexOf](qstringlist.html#lastIndexOf)在另一方面（ ）函数，返回字符串中最后一次出现的索引。

最后，该[replaceInStrings](qstringlist.html#replaceInStrings)（ ）函数调用[QString.replace](qstring.html#replace)（ ）在字符串列表中依次每个字符串。例如：

```
     QStringList files;
     files << "$QTDIR/src/moc/moc.y"
           << "$QTDIR/src/moc/moc.l"
           << "$QTDIR/include/qconfig.h";

     files.replaceInStrings("$QTDIR", "/usr/lib/qt");
     // files: [ "/usr/lib/qt/src/moc/moc.y", ...]

```

* * *

## Method Documentation

```
QStringList.__init__ (self)
```

构造一个空字符串列表。

```
QStringList.__init__ (self, QString i)
```

构造一个字符串列表，其中包含给定的字符串，_str_。较长的列表很容易像这样创建：

```
     [QStringList](qstringlist.html) longerList = ([QStringList](qstringlist.html)() << str1 << str2 << str3);

```

**See also** [append](index.htm#append)（ ） 。

```
QStringList.__init__ (self, QStringList l)
```

构造的一个副本_other_字符串列表。

该操作需要[constant time](index.htm#constant-time)因为[QStringList](qstringlist.html) is [implicitly shared](index.htm#implicitly-shared)，使得返回一个过程[QStringList](qstringlist.html)从非常快的函数。如果共享的实例被改性时，其将被复制（复制写入时） ，而这需要[linear time](index.htm#linear-time)。

**See also** [operator=](index.htm#operator-eq)（ ） 。

```
QStringList.append (self, QString str)
```

```
QStringList.clear (self)
```

```
bool QStringList.contains (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

如果列表中包含该字符串，则返回True_str_否则返回False 。搜索不区分大小写，如果_cs_ is [Qt.CaseInsensitive](qt.html#CaseSensitivity-enum);搜索是区分默认敏感。

**See also** [indexOf](qstringlist.html#indexOf)（ ）[lastIndexOf](qstringlist.html#lastIndexOf)（）和[QString.contains](qstring.html#contains)（ ） 。

```
int QStringList.count (self, QString str)
```

```
int QStringList.count (self)
```

```
QStringList QStringList.filter (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回所有的字符串包含子列表_str_。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认值） ，字符串比较是区分大小写的，否则比较不区分大小写。

```
     [QStringList](qstringlist.html) list;
     list << "Bill Murray" << "John Doe" << "Bill Clinton";

     [QStringList](qstringlist.html) result;
     result = list.filter("Bill");
     // result: ["Bill Murray", "Bill Clinton"]

```

这等效于

```
     [QStringList](qstringlist.html) result;
     foreach (const [QString](qstring.html) &str, list) {
         if (str.contains("Bill"))
             result += str;
     }

```

**See also** [contains](qstringlist.html#contains)（ ） 。

```
QStringList QStringList.filter (self, QRegExp rx)
```

这是一个重载函数。

返回所有匹配正则表达式的字符串列表_rx_。

```
QString QStringList.first (self)
```

```
int QStringList.indexOf (self, QString value, int from = 0)
```

返回的第一个精确匹配的索引位置_rx_在列表中，向前搜索从索引位置_from_。返回-1，如果没有项目匹配。

默认情况下，这个功能是区分大小写的。

**See also** [lastIndexOf](qstringlist.html#lastIndexOf)（ ）[contains](qstringlist.html#contains)（）和[QRegExp.exactMatch](qregexp.html#exactMatch)（ ） 。

```
int QStringList.indexOf (self, QRegExp rx, int from = 0)
```

返回第一次出现的索引位置_value_在列表中，向前搜索从索引位置_from_。返回-1，如果没有项目匹配。

**See also** [lastIndexOf](qstringlist.html#lastIndexOf)（ ）[contains](qstringlist.html#contains)（）和[QList.indexOf](index.htm#indexOf)（ ） 。

```
QStringList.insert (self, int i, QString str)
```

```
bool QStringList.isEmpty (self)
```

```
QString QStringList.join (self, QString sep)
```

加入所有的字符串列表的字符串与由给定的分隔每个元素的单个字符串_separator_（可以是空字符串） 。

**See also** [QString.split](qstring.html#split)（ ） 。

```
QString QStringList.last (self)
```

```
int QStringList.lastIndexOf (self, QString value, int from = -1)
```

返回的最后一个精确匹配的索引位置_rx_在列表中，从索引位置向后搜索_from_。如果_from_为-1 （默认值） ，该搜索从最后一个项目。返回-1，如果没有项目匹配。

默认情况下，这个功能是区分大小写的。

**See also** [indexOf](qstringlist.html#indexOf)（ ）[contains](qstringlist.html#contains)（）和[QRegExp.exactMatch](qregexp.html#exactMatch)（ ） 。

```
int QStringList.lastIndexOf (self, QRegExp rx, int from = -1)
```

返回最后一次出现的索引位置_value_在列表中，从索引位置向后搜索_from_。如果_from_为-1 （默认值） ，该搜索从最后一个项目。返回-1，如果没有项目匹配。

默认情况下，这个功能是区分大小写的。

**See also** [indexOf](qstringlist.html#indexOf)（）和[QList.lastIndexOf](index.htm#lastIndexOf)（ ） 。

```
QStringList QStringList.mid (self, int pos, int length = -1)
```

```
QStringList.move (self, int from, int to)
```

```
QStringList.prepend (self, QString str)
```

```
int QStringList.removeAll (self, QString str)
```

```
QStringList.removeAt (self, int i)
```

```
int QStringList.removeDuplicates (self)
```

此函数删除重复项列表。条目不必进行排序。他们将保留原来的顺序。

返回删除条目的数量。

此功能被引入Qt的4.5 。

```
QStringList.replace (self, int i, QString str)
```

```
QStringList QStringList.replaceInStrings (self, QString before, QString after, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回一个字符串列表，其中每个字符串发生了_before_文本与替换_after_文本的地方_before_文字被发现。该_before_文本匹配大小写敏感或不依赖于_cs_标志。

例如：

```
     [QStringList](qstringlist.html) list;
     list << "alpha" << "beta" << "gamma" << "epsilon";
     list.replaceInStrings("a", "o");
     // list == ["olpho", "beto", "gommo", "epsilon"]

```

**See also** [QString.replace](qstring.html#replace)（ ） 。

```
QStringList QStringList.replaceInStrings (self, QRegExp rx, QString after)
```

这是一个重载函数。

取代了正则表达式的每个实例_rx_在每个字符串列表的字符串，以_after_。返回一个引用的字符串列表。

例如：

```
     [QStringList](qstringlist.html) list;
     list << "alpha" << "beta" << "gamma" << "epsilon";
     list.replaceInStrings([QRegExp](qregexp.html)("^a"), "o");
     // list == ["olpha", "beta", "gamma", "epsilon"]

```

对于包含正则表达式[capturing parentheses](qregexp.html#capturing-parentheses)，出现的**\1**，**\2**，...，在_after_被替换为_rx_。帽（ 1 ） ，_rx_。盖（2 ） ， ...

例如：

```
     [QStringList](qstringlist.html) list;
     list << "Bill Clinton" << "Murray, Bill";
     list.replaceInStrings([QRegExp](qregexp.html)("^(.*), (.*)$"), "\\2 \\1");
     // list == ["Bill Clinton", "Bill Murray"]

```

```
QStringList.sort (self)
```

按升序排列（敏感的情况下）的字符串列表。

使用Qt的进行排序[qSort](index.htm#qSort)（ ）算法，该算法在运行[linear-logarithmic time](index.htm#linear-logarithmic-time)，即澳（_n_登录_n_） 。

如果你想以任意顺序的字符串进行排序，请考虑使用[QMap](index.htm)类。例如，您可以使用[QMap](index.htm)\u003c[QString](qstring.html)，[QString](qstring.html)\u003e创建一个不区分大小写的排序（例如，使用按键作为字符串的小写版本，并作为字符串值） ，或[QMap](index.htm)\u003c整数，[QString](qstring.html)\u003e由一些整数索引的字符串进行排序。

**See also** [qSort](index.htm#qSort)（ ） 。

```
QStringList.swap (self, int i, int j)
```

```
QString QStringList.takeAt (self, int i)
```

```
QString QStringList.takeFirst (self)
```

```
QString QStringList.takeLast (self)
```

```
QStringList QStringList.__add__ (self, QStringList other)
```

```
int QStringList.__contains__ (self, QString str)
```

```
QStringList.__delitem__ (self, int i)
```

```
QStringList.__delitem__ (self, slice slice)
```

```
bool QStringList.__eq__ (self, QStringList other)
```

```
QString QStringList.__getitem__ (self, int i)
```

```
QStringList QStringList.__getitem__ (self, slice slice)
```

```
QStringList QStringList.__iadd__ (self, QStringList other)
```

```
QStringList QStringList.__iadd__ (self, QString value)
```

```
QStringList QStringList.__imul__ (self, int by)
```

```
 QStringList.__len__ (self)
```

```
QStringList QStringList.__lshift__ (self, QString str)
```

```
QStringList QStringList.__lshift__ (self, QStringList l)
```

```
QStringList QStringList.__mul__ (self, int by)
```

```
bool QStringList.__ne__ (self, QStringList other)
```

```
QStringList.__setitem__ (self, int i, QString str)
```

```
QStringList.__setitem__ (self, slice slice, QStringList list)
```