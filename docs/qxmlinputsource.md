# QXmlInputSource Class Reference

## [[QtXml](index.htm) module]

该QXmlInputSource类提供​​输入数据为[QXmlReader](qxmlreader.html)子类。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice dev)`
*   `__init__ (self, QXmlInputSource)`
*   `QString data (self)`
*   `fetchData (self)`
*   `QString fromRawData (self, QByteArray data, bool beginning = False)`
*   `QChar next (self)`
*   `reset (self)`
*   `setData (self, QString dat)`
*   `setData (self, QByteArray dat)`

### Static Members

*   `int **[EndOfData](qxmlinputsource.html#EndOfData-var)**`
*   `int **[EndOfDocument](qxmlinputsource.html#EndOfDocument-var)**`

* * *

## Detailed Description

该QXmlInputSource类提供​​输入数据为[QXmlReader](qxmlreader.html)子类。

的所有子类[QXmlReader](qxmlreader.html)阅读从这个类的输入XML文档。

这个类识别数据通过读取编码声明在XML文件中的编码，如果找到一个，并使用相应的编码读出的数据。如果它没有找到一个编码声明，那么它假定数据是用UTF -8或UTF-16 ，这取决于它是否能找到一个字节顺序标记。

有两种方法来填充数据输入源：你可以用它构建[QIODevice](qiodevice.html)*使输入源读取该设备的数据。或者您也可以显式设置数据与之一[setData](qxmlinputsource.html#setData)（）函数。

通常你要么建立在这一个工作QXmlInputSource[QIODevice](qiodevice.html)*或者你构造一个空QXmlInputSource和设置数据[setData](qxmlinputsource.html#setData)（ ） 。目前只有极少数情况下，您都需要混合这两种方法。

该[QXmlReader](qxmlreader.html)子类使用[next](qxmlinputsource.html#next)（ ）函数按字符读取输入的字符。如果你想从头开始，使用[reset](qxmlinputsource.html#reset)（ ） 。

该功能[data](qxmlinputsource.html#data)（）和[fetchData](qxmlinputsource.html#fetchData)如果你想做一件事，比解析，如其他数据（ ）是有用的显示原始XML文件。使用QXmlInputClass在这种情况下的好处是，它会尝试使用正确的编码。

* * *

## Method Documentation

```
QXmlInputSource.__init__ (self)
```

构造一个其中不包含任何数据的输入源。

**See also** [setData](qxmlinputsource.html#setData)（ ） 。

```
QXmlInputSource.__init__ (self, QIODevice dev)
```

构造一个输入源，并从设备获取数据_dev_。如果_dev_是不是开放的，它在只读模式打开。如果_dev_是0或不可能从设备读取，输入信号源将不包含任何数据。

**See also** [setData](qxmlinputsource.html#setData)（ ）[fetchData](qxmlinputsource.html#fetchData)（）和[QIODevice](qiodevice.html)。

```
QXmlInputSource.__init__ (self, QXmlInputSource)
```

```
QString QXmlInputSource.data (self)
```

返回输入源中包含的数据或空字符串，如果输入信号源不包含任何数据。

**See also** [setData](qxmlinputsource.html#setData)（ ）[QXmlInputSource](qxmlinputsource.html#QXmlInputSource)（）和[fetchData](qxmlinputsource.html#fetchData)（ ） 。

```
QXmlInputSource.fetchData (self)
```

该函数读取从施工过程中设置的设备更多的数据。如果输入源已经包含数据，这个功能会删除该数据首次。

这个对象包含调用此函数后没有数据，如果该对象没有一个设备读取数据，或者如果这个功能是无法从设备得到更多的数据构成。

有两次，其中一个是隐含另一个函数调用来完成取：施工期间（使物体开始与一些初始数据如果有的话） ，以及在通话期间[next](qxmlinputsource.html#next)（ ） （如果数据已经用完） 。

你通常不需要，如果你用它来使用这个功能[next](qxmlinputsource.html#next)（ ） 。

**See also** [data](qxmlinputsource.html#data)（ ）[next](qxmlinputsource.html#next)（）和[QXmlInputSource](qxmlinputsource.html#QXmlInputSource)（ ） 。

```
QString QXmlInputSource.fromRawData (self, QByteArray data, bool beginning = False)
```

该函数读取XML文件_data_并试图识别的编码。它把原始数据_data_成[QString](qstring.html)并返回它。它试图尽力获取XML文件的正确编码。

If _beginning_诚然，这个函数假设数据开始于一个新的XML文档的开始，并寻找一个编码声明。如果_beginning_是假的，它使用从调用之前确定的编码转换的原始数据。

```
QChar QXmlInputSource.next (self)
```

返回输入源的下一个字符。如果这个函数达到可用数据的末尾时，它返回[QXmlInputSource.EndOfData](qxmlinputsource.html#EndOfData-var)。如果你的next（）之后调用，它会尝试通过调用来获取更多数据[fetchData](qxmlinputsource.html#fetchData)（ ） 。如果[fetchData](qxmlinputsource.html#fetchData)（ ）调用会导致新的数据，这个函数返回数据的第一个字符，否则返回[QXmlInputSource.EndOfDocument](qxmlinputsource.html#EndOfDocument-var)。

读者如[QXmlSimpleReader](qxmlsimplereader.html)，将假设XML文档的结尾已经达到，如果这个函数返回[QXmlInputSource.EndOfDocument](qxmlinputsource.html#EndOfDocument-var)，并且将检查所提供的输入是良好的。因此，重新实现这个函数的时候，一定要确保这种行为是重复是很重要的。

**See also** [reset](qxmlinputsource.html#reset)（ ）[fetchData](qxmlinputsource.html#fetchData)（ ）[QXmlSimpleReader.parse](qxmlsimplereader.html#parse)（）和[QXmlSimpleReader.parseContinue](qxmlsimplereader.html#parseContinue)（ ） 。

```
QXmlInputSource.reset (self)
```

这个函数设置使用的位置[next](qxmlinputsource.html#next)（）来返回的数据的开头[data](qxmlinputsource.html#data)（ ） 。如果你想使用的输入源不止一个解析，这是很有用的。

**Note:**在该情况下，底层的数据源是一个[QIODevice](qiodevice.html)在设备的当前位置是不会自动设置为输入的开始。该设备做这个呼吁QIODevice.seek （ 0 ） 。

**See also** [next](qxmlinputsource.html#next)（ ） 。

```
QXmlInputSource.setData (self, QString dat)
```

输入源的数据集，以_dat_。

如果输入源已经包含数据，这个功能会删除该数据首次。

**See also** [data](qxmlinputsource.html#data)（ ） 。

```
QXmlInputSource.setData (self, QByteArray dat)
```

这是一个重载函数。

数据_dat_通过正确的文本编解码器通过了，它被设置之前。

* * *

## Member Documentation

```
int EndOfData
```

此构件应被视为常数。

```
int EndOfDocument
```

此构件应被视为常数。