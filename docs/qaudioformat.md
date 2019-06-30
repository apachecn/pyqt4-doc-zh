# QAudioFormat Class Reference

## [[QtMultimedia](index.htm) module]

该QAudioFormat类存储音频的参数信息。[More...](#details)

### Types

*   `enum Endian { BigEndian, LittleEndian }`
*   `enum SampleType { Unknown, SignedInt, UnSignedInt, Float }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QAudioFormat other)`
*   `Endian byteOrder (self)`
*   `int channelCount (self)`
*   `int channels (self)`
*   `QString codec (self)`
*   `int frequency (self)`
*   `bool isValid (self)`
*   `int sampleRate (self)`
*   `int sampleSize (self)`
*   `SampleType sampleType (self)`
*   `setByteOrder (self, Endian byteOrder)`
*   `setChannelCount (self, int channelCount)`
*   `setChannels (self, int channels)`
*   `setCodec (self, QString codec)`
*   `setFrequency (self, int frequency)`
*   `setSampleRate (self, int sampleRate)`
*   `setSampleSize (self, int sampleSize)`
*   `setSampleType (self, SampleType sampleType)`

### Special Methods

*   `bool __eq__ (self, QAudioFormat other)`
*   `bool __ne__ (self, QAudioFormat other)`

* * *

## Detailed Description

该QAudioFormat类存储音频的参数信息。

一种音频格式指定如何在一个音频数据流的数据排列，即，如何将数据流将被解释。编码本身是由指定的[codec](qaudioformat.html#codec)（）用于视频流。

除了编码， QAudioFormat包含进一步指定的音频数据是如何排列的其它参数。这些是频率，信道数，样本大小，样本类型和字节顺序。下表详细描述了这些。

| Parameter | Description |
| --- | --- |
| Sample Rate | Samples per second of audio data in Hertz. |
| Number of channels | The number of audio channels (typically one for mono or two for stereo) |
| Sample size | How much data is stored in each sample (typically 8 or 16 bits) |
| Sample type | Numerical representation of sample (typically signed integer, unsigned integer or float) |
| Byte order | Byte ordering of sample (typically little endian, big endian) |

您可以获取通过在函数中使用的音频设备兼容的音频格式[QAudioDeviceInfo](qaudiodeviceinfo.html)。这个类也可以让你查询一个设备可用的参数值，这样你可以自己设置参数。请参阅[QAudioDeviceInfo](qaudiodeviceinfo.html)类描述的细节。你需要知道你想要播放的音频流的格式。 Qt不设置格式为您服务。

* * *

## Type Documentation

```
QAudioFormat.Endian
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAudioFormat.BigEndian` | `QSysInfo.BigEndian` | 样品是Big Endian字节序 |
| `QAudioFormat.LittleEndian` | `QSysInfo.LittleEndian` | 样品是little endian字节顺序 |

```
QAudioFormat.SampleType
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAudioFormat.Unknown` | `0` | 没有设置 |
| `QAudioFormat.SignedInt` | `1` | 样品有符号整数 |
| `QAudioFormat.UnSignedInt` | `2` | 样品是无符号intergers |
| `QAudioFormat.Float` | `3` | 样品彩车 |

* * *

## Method Documentation

```
QAudioFormat.__init__ (self)
```

构造一个新的音频格式。

值被初始化如下：

*   [sampleRate](qaudioformat.html#sampleRate)() = -1
*   [channelCount](qaudioformat.html#channelCount)() = -1
*   [sampleSize](qaudioformat.html#sampleSize)() = -1
*   [byteOrder](qaudioformat.html#byteOrder)() = [QAudioFormat.Endian](qaudioformat.html#Endian-enum)([QSysInfo.ByteOrder](qsysinfo.html#Endian-enum))
*   [sampleType](qaudioformat.html#sampleType)() = [QAudioFormat.Unknown](qaudioformat.html#SampleType-enum) `codec()` = ""

```
QAudioFormat.__init__ (self, QAudioFormat other)
```

构造采用了全新的音频格式_other_。

```
Endian QAudioFormat.byteOrder (self)
```

[

返回当前byteOrder值。

](qaudioformat.html#Endian-enum)

[**See also**](qaudioformat.html#Endian-enum) [setByteOrder](qaudioformat.html#setByteOrder)（ ） 。

```
int QAudioFormat.channelCount (self)
```

返回当前通道的计数值。

此功能被引入Qt的4.7 。

**See also** [setChannelCount](qaudioformat.html#setChannelCount)（ ） 。

```
int QAudioFormat.channels (self)
```

```
QString QAudioFormat.codec (self)
```

返回当前的编解码器值。

**See also** [setCodec](qaudioformat.html#setCodec)（）和[QAudioDeviceInfo.supportedCodecs](qaudiodeviceinfo.html#supportedCodecs)（ ） 。

```
int QAudioFormat.frequency (self)
```

```
bool QAudioFormat.isValid (self)
```

返回True如果所有的参数都是有效的。

```
int QAudioFormat.sampleRate (self)
```

返回赫兹的电流采样率。

此功能被引入Qt的4.7 。

**See also** [setSampleRate](qaudioformat.html#setSampleRate)（ ） 。

```
int QAudioFormat.sampleSize (self)
```

返回当前采样大小的值。

**See also** [setSampleSize](qaudioformat.html#setSampleSize)（ ） 。

```
SampleType QAudioFormat.sampleType (self)
```

[](qaudioformat.html#SampleType-enum)

[返回当前](qaudioformat.html#SampleType-enum)[SampleType](qaudioformat.html#SampleType-enum)值。

**See also** [setSampleType](qaudioformat.html#setSampleType)（ ） 。

```
QAudioFormat.setByteOrder (self, Endian byteOrder)
```

设置byteOrder到_byteOrder_。

**See also** [byteOrder](qaudioformat.html#byteOrder)（ ） 。

```
QAudioFormat.setChannelCount (self, int channelCount)
```

设置通道数_channels_。

此功能被引入Qt的4.7 。

**See also** [channelCount](qaudioformat.html#channelCount)（ ） 。

```
QAudioFormat.setChannels (self, int channels)
```

```
QAudioFormat.setCodec (self, QString codec)
```

设置编解码器_codec_。

**See also** [codec](qaudioformat.html#codec)（）和[QAudioDeviceInfo.supportedCodecs](qaudiodeviceinfo.html#supportedCodecs)（ ） 。

```
QAudioFormat.setFrequency (self, int frequency)
```

```
QAudioFormat.setSampleRate (self, int sampleRate)
```

设置采样率_samplerate_赫兹。

此功能被引入Qt的4.7 。

**See also** [sampleRate](qaudioformat.html#sampleRate)（ ） 。

```
QAudioFormat.setSampleSize (self, int sampleSize)
```

将样本大小对_sampleSize_规定。

**See also** [sampleSize](qaudioformat.html#sampleSize)（ ） 。

```
QAudioFormat.setSampleType (self, SampleType sampleType)
```

设置sampleType到_sampleType_。

**See also** [sampleType](qaudioformat.html#sampleType)（ ） 。

```
bool QAudioFormat.__eq__ (self, QAudioFormat other)
```

```
bool QAudioFormat.__ne__ (self, QAudioFormat other)
```