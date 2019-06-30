# QBitArray Class Reference

## [[QtCore](index.htm) module]

该QBitArray类提供了一组位。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, int size, bool value = False)`
*   `__init__ (self, QBitArray other)`
*   `bool at (self, int i)`
*   `clear (self)`
*   `clearBit (self, int i)`
*   `int count (self)`
*   `int count (self, bool on)`
*   `detach (self)`
*   `fill (self, bool val, int first, int last)`
*   `bool fill (self, bool value, int size = -1)`
*   `bool isDetached (self)`
*   `bool isEmpty (self)`
*   `bool isNull (self)`
*   `resize (self, int size)`
*   `setBit (self, int i)`
*   `setBit (self, int i, bool val)`
*   `int size (self)`
*   `swap (self, QBitArray other)`
*   `bool testBit (self, int i)`
*   `bool toggleBit (self, int i)`
*   `truncate (self, int pos)`

### Special Methods

*   `QBitArray __and__ (self, QBitArray)`
*   `bool __eq__ (self, QBitArray a)`
*   `bool __getitem__ (self, int i)`
*   `int __hash__ (self)`
*   `QBitArray __iand__ (self, QBitArray)`
*   `QBitArray __invert__ (self)`
*   `QBitArray __ior__ (self, QBitArray)`
*   `QBitArray __ixor__ (self, QBitArray)`
*   `__len__ (self)`
*   `bool __ne__ (self, QBitArray a)`
*   `QBitArray __or__ (self, QBitArray)`
*   `QBitArray __xor__ (self, QBitArray)`

* * *

## Detailed Description

该QBitArray类提供了一组位。

一个QBitArray是一个数组，它可以访问各个位，并提供运营商（[AND](qbitarray.html#operator-and)，[OR](qbitarray.html#operator-7c)，[XOR](qbitarray.html#operator-5e)和[NOT](qbitarray.html#operator-7e)对位的整个数组）的工作。它使用[implicit sharing](index.htm)（复制上写的），以减少内存使用量，避免不必要的数据复制。

下面的代码创建一个包含200位的QBitArray初始化为False （ 0 ） ：

```
 QBitArray ba(200);

```

要初始化位为True ，要么通过`true`作为第二个参数的构造函数，或调用[fill](qbitarray.html#fill)（ ）以后。

QBitArray使用基于0的索引，就像C + +中的数组。要访问该位在特定索引位置，可以使用操作符[] （ ） 。对非const位阵列，操作符[ ] （ ）返回一个引用位，可以在赋值的左侧使用。例如：

```
 QBitArray ba;
 ba.resize(3);
 ba[0] = true;
 ba[1] = false;
 ba[2] = true;

```

由于技术原因，它是更有效地使用[testBit](qbitarray.html#testBit)（）和[setBit](qbitarray.html#setBit)（ ）来访问数组比运营商的位[] （ ） 。例如：

```
 QBitArray ba(3);
 ba.setBit(0, true);
 ba.setBit(1, false);
 ba.setBit(2, true);

```

QBitArray支持`&`（[AND](qbitarray.html#operator-and)） ，`|`（[OR](qbitarray.html#operator-7c)） ，`^`（[XOR](qbitarray.html#operator-5e)） ，`~`（[NOT](qbitarray.html#operator-7e)） ，以及`&=`，`|=`和`^=`。这些运营商在相同的方式相同名称的内置C + +的位运算符的工作。例如：

```
 QBitArray x(5);
 x.setBit(3, true);
 // x: [ 0, 0, 0, 1, 0 ]

 QBitArray y(5);
 y.setBit(4, true);
 // y: [ 0, 0, 0, 0, 1 ]

 x |= y;
 // x: [ 0, 0, 0, 1, 1 ]

```

由于历史原因， QBitArray一个空位阵列和一个空的位阵列之间的区别。一_null_位阵列是使用QBitArray的默认构造函数初始化一个位阵列。一个_empty_位阵列中的任何位数组大小为0 。空阵位总是空的，但一个空的位阵列不一定空：

```
 QBitArray().isNull();           // returns true
 QBitArray().isEmpty();          // returns true

 QBitArray(0).isNull();          // returns false
 QBitArray(0).isEmpty();         // returns true

 QBitArray(3).isNull();          // returns false
 QBitArray(3).isEmpty();         // returns false

```

之外的全部功能[isNull](qbitarray.html#isNull)（ ）把空位阵列一样空位阵列，例如，[QBitArray](qbitarray.html#QBitArray)（）比较等于QBitArray （0）。我们建议您始终使用[isEmpty](qbitarray.html#isEmpty)（）和避免[isNull](qbitarray.html#isNull)（ ） 。

* * *

## Method Documentation

```
QBitArray.__init__ (self)
```

构造一个空数组位。

**See also** [isEmpty](qbitarray.html#isEmpty)（ ） 。

```
QBitArray.__init__ (self, int size, bool value = False)
```

构造一个位阵列包含_size_位。该位与初始化_value_，默认为False （ 0 ） 。

```
QBitArray.__init__ (self, QBitArray other)
```

构造的副本_other_。

该操作需要[constant time](index.htm#constant-time)，因为[QBitArray](qbitarray.html) is [implicitly shared](index.htm#implicitly-shared)。这使得返回一个[QBitArray](qbitarray.html)从非常快的函数。如果共享的实例被改性时，其将被复制（复制写入时） ，而这需要[linear time](index.htm#linear-time)。

**See also** [operator=](qbitarray.html#operator-eq)（ ） 。

```
bool QBitArray.at (self, int i)
```

返回索引位置的位值_i_。

_i_必须是位阵列中的一个有效的索引位置（即0 \u003c =_i_\u003c[size](qbitarray.html#size)（））。

**See also** [operator[]](qbitarray.html#operator-5b-5d)（ ） 。

```
QBitArray.clear (self)
```

清除该位阵列的内容，并使其为空。

**See also** [resize](qbitarray.html#resize)（）和[isEmpty](qbitarray.html#isEmpty)（ ） 。

```
QBitArray.clearBit (self, int i)
```

设置位索引位置_i_为0。

_i_必须是位阵列中的一个有效的索引位置（即0 \u003c =_i_\u003c[size](qbitarray.html#size)（））。

**See also** [setBit](qbitarray.html#setBit)（）和[toggleBit](qbitarray.html#toggleBit)（ ） 。

```
int QBitArray.count (self)
```

同[size](qbitarray.html#size)（ ） 。

```
int QBitArray.count (self, bool on)
```

If _on_诚然，此函数返回所存储的比特数组中1位的号码，否则返回0位的数量。

```
QBitArray.detach (self)
```

```
QBitArray.fill (self, bool val, int first, int last)
```

设置该位阵列中每一个位_value_如果成功，则返回True ，否则返回False 。如果_size_是从-1 （默认值）不同，该位阵列大小调整为_size_事前。

例如：

```
 [QBitArray](qbitarray.html) ba(8);
 ba.fill(true);
 // ba: [ 1, 1, 1, 1, 1, 1, 1, 1 ]

 ba.fill(false, 2);
 // ba: [ 0, 0 ]

```

**See also** [resize](qbitarray.html#resize)（ ） 。

```
bool QBitArray.fill (self, bool value, int size = -1)
```

这是一个重载函数。

设置位在索引位置_begin_达，但不包括_end_至_value_。

_begin_和_end_必须是位阵列中的一个有效的索引位置（即0 \u003c =_begin_\u003c =[size](qbitarray.html#size)（）和0 \u003c=_end_\u003c =[size](qbitarray.html#size)（））。

```
bool QBitArray.isDetached (self)
```

```
bool QBitArray.isEmpty (self)
```

返回True如果该位数组的大小为0 ，否则返回False 。

**See also** [size](qbitarray.html#size)（ ） 。

```
bool QBitArray.isNull (self)
```

返回True如果该位数组为null ，否则返回False 。

例如：

```
 [QBitArray](qbitarray.html)().isNull();           // returns true
 [QBitArray](qbitarray.html)(0).isNull();          // returns false
 [QBitArray](qbitarray.html)(3).isNull();          // returns false

```

Qt后，由于历史的原因空位阵列和空bit数组之间的区别。对于大多数应用来说，重要的是一个位阵列中是否包含任何数据，这可以通过确定[isEmpty](qbitarray.html#isEmpty)（ ） 。

**See also** [isEmpty](qbitarray.html#isEmpty)（ ） 。

```
QBitArray.resize (self, int size)
```

调整大小的位阵列_size_位。

If _size_大于该电流的大小，位阵列被扩展以使其_size_与额外的比特位添加到末尾。新的位被初始化为False （ 0 ） 。

If _size_小于该电流的大小，比特被从端部除去。

**See also** [size](qbitarray.html#size)（ ） 。

```
QBitArray.setBit (self, int i)
```

设置位索引位置_i_为1。

_i_必须是位阵列中的一个有效的索引位置（即0 \u003c =_i_\u003c[size](qbitarray.html#size)（））。

**See also** [clearBit](qbitarray.html#clearBit)（）和[toggleBit](qbitarray.html#toggleBit)（ ） 。

```
QBitArray.setBit (self, int i, bool val)
```

这是一个重载函数。

设置位索引位置_i_至_value_。

```
int QBitArray.size (self)
```

返回所存储的比特阵列中的比特数。

**See also** [resize](qbitarray.html#resize)（ ） 。

```
QBitArray.swap (self, QBitArray other)
```

掉期位阵列_other_与此位阵列。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
bool QBitArray.testBit (self, int i)
```

返回True ，如果该位索引位置_i_为1 ，否则返回False 。

_i_必须是位阵列中的一个有效的索引位置（即0 \u003c =_i_\u003c[size](qbitarray.html#size)（））。

**See also** [setBit](qbitarray.html#setBit)（）和[clearBit](qbitarray.html#clearBit)（ ） 。

```
bool QBitArray.toggleBit (self, int i)
```

反转索引位置的位值_i_，返回该位为任一真（如果它被设置）或False （如果它是未设置）的前一个值。

如果以前的值为0 ，则新值将是1 。如果以前的值为1 ，新值将为0 。

_i_必须是位阵列中的一个有效的索引位置（即0 \u003c =_i_\u003c[size](qbitarray.html#size)（））。

**See also** [setBit](qbitarray.html#setBit)（）和[clearBit](qbitarray.html#clearBit)（ ） 。

```
QBitArray.truncate (self, int pos)
```

截断位阵列索引位置_pos_。

If _pos_超出了数组的结尾，没有任何反应。

**See also** [resize](qbitarray.html#resize)（ ） 。

```
QBitArray QBitArray.__and__ (self, QBitArray)
```

[

```
bool QBitArray.__eq__ (self, QBitArray a)
```

```
bool QBitArray.__getitem__ (self, int i)
```

```
int QBitArray.__hash__ (self)
```

](qbitarray.html)

```
QBitArray QBitArray.__iand__ (self, QBitArray)
```

[](qbitarray.html)

```
QBitArray QBitArray.__invert__ (self)
```

[](qbitarray.html)

```
QBitArray QBitArray.__ior__ (self, QBitArray)
```

[](qbitarray.html)

```
QBitArray QBitArray.__ixor__ (self, QBitArray)
```

[

```
 QBitArray.__len__ (self)
```

```
bool QBitArray.__ne__ (self, QBitArray a)
```

](qbitarray.html)

```
QBitArray QBitArray.__or__ (self, QBitArray)
```

[](qbitarray.html)

```
QBitArray QBitArray.__xor__ (self, QBitArray)
```

[](qbitarray.html)