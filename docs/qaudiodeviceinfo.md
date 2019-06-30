# QAudioDeviceInfo Class Reference

## [[QtMultimedia](index.htm) module]

该QAudioDeviceInfo类提供查询音频设备及其功能的接口。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QAudioDeviceInfo other)`
*   `QString deviceName (self)`
*   `bool isFormatSupported (self, QAudioFormat format)`
*   `bool isNull (self)`
*   `QAudioFormat nearestFormat (self, QAudioFormat format)`
*   `QAudioFormat preferredFormat (self)`
*   `list-of-QAudioFormat.Endian supportedByteOrders (self)`
*   `list-of-int supportedChannelCounts (self)`
*   `list-of-int supportedChannels (self)`
*   `QStringList supportedCodecs (self)`
*   `list-of-int supportedFrequencies (self)`
*   `list-of-int supportedSampleRates (self)`
*   `list-of-int supportedSampleSizes (self)`
*   `list-of-QAudioFormat.SampleType supportedSampleTypes (self)`

### Static Methods

*   `list-of-QAudioDeviceInfo availableDevices (QAudio.Mode mode)`
*   `QAudioDeviceInfo defaultInputDevice ()`
*   `QAudioDeviceInfo defaultOutputDevice ()`

* * *

## Detailed Description

该QAudioDeviceInfo类提供查询音频设备及其功能的接口。

QAudioDeviceInfo让您查询的音频设备 - 如声卡和USB耳机 - 当前可用的系统上。可用的音频设备都依赖安装在平台或音频插件上。

您也可以查询每个设备所支持的格式。在此上下文中的一种格式是一组由特定的字节顺序，信道编解码器，频率，采样率，和样品的类型。的一种格式是由代表[QAudioFormat](qaudioformat.html)类。

由该设备为每一个参数所支持的值可以与提取[supportedByteOrders](qaudiodeviceinfo.html#supportedByteOrders)（ ）[supportedChannelCounts](qaudiodeviceinfo.html#supportedChannelCounts)（ ）[supportedCodecs](qaudiodeviceinfo.html#supportedCodecs)（ ）[supportedSampleRates](qaudiodeviceinfo.html#supportedSampleRates)（ ）[supportedSampleSizes](qaudiodeviceinfo.html#supportedSampleSizes)（）和[supportedSampleTypes](qaudiodeviceinfo.html#supportedSampleTypes)（ ） 。支持的组合是依赖于平台，安装音频插件和音频设备的能力上。如果你需要一个特定的格式，您可以检查设备是否支持它[isFormatSupported](qaudiodeviceinfo.html#isFormatSupported)（ ） ，或者获取一个支持的格式是尽可能接近的格式[nearestFormat](qaudiodeviceinfo.html#nearestFormat)（ ） 。例如：

```
         [QAudioFormat](qaudioformat.html) format;
         format.setFrequency(44100);
         ...
         format.setSampleType([QAudioFormat](qaudioformat.html).SignedInt);

         QAudioDeviceInfo info(QAudioDeviceInfo.defaultOutputDevice());

         if (!info.isFormatSupported(format))
             format = info.nearestFormat(format);

```

一个QAudioDeviceInfo所使用的Qt构建类与设备进行通信 - 如[QAudioInput](qaudioinput.html)和[QAudioOutput](qaudiooutput.html)。静态函数[defaultInputDevice](qaudiodeviceinfo.html#defaultInputDevice)（ ）[defaultOutputDevice](qaudiodeviceinfo.html#defaultOutputDevice)（）和[availableDevices](qaudiodeviceinfo.html#availableDevices)（ ）让你得到所有可用设备的列表。器件读取根据mode的值，这是由指定的[QAudio.Mode](qaudio.html#Mode-enum)枚举。该QAudioDeviceInfo返回仅适用于本[QAudio.Mode](qaudio.html#Mode-enum)。

例如：

```
 foreach(const QAudioDeviceInfo &deviceInfo, QAudioDeviceInfo.availableDevices([QAudio](qaudio.html).AudioOutput))
     qDebug() << "Device name: " << deviceInfo.deviceName();

```

在此代码示例中，我们遍历所有的都能够输出声音，即设备，支持的格式播放音频流。对于发现的每个设备，我们只需打印[deviceName](qaudiodeviceinfo.html#deviceName)（ ） 。

* * *

## Method Documentation

```
QAudioDeviceInfo.__init__ (self)
```

构造一个空[QAudioDeviceInfo](qaudiodeviceinfo.html)对象。

```
QAudioDeviceInfo.__init__ (self, QAudioDeviceInfo other)
```

构造的副本_other_。

```
list-of-QAudioDeviceInfo QAudioDeviceInfo.availableDevices (QAudio.Mode mode)
```

返回支持的音频设备列表_mode_。

```
QAudioDeviceInfo QAudioDeviceInfo.defaultInputDevice ()
```

[

返回默认的输入音频设备的名称。所有的平台和音频插件的实现提供了一个默认的音频设备使用。

](qaudiodeviceinfo.html)

```
QAudioDeviceInfo QAudioDeviceInfo.defaultOutputDevice ()
```

[

返回缺省输出音频设备的名称。所有的平台和音频插件的实现提供了一个默认的音频设备使用。

```
QString QAudioDeviceInfo.deviceName (self)
```

返回音频设备的可读名称。

设备名称具体取决于正在使用的平台/音频插件有所不同。

他们是一个唯一的字符串识别为音频设备。

例如： 。默认情况下，英特尔， U0x46d0x9a4

```
bool QAudioDeviceInfo.isFormatSupported (self, QAudioFormat format)
```

](qaudiodeviceinfo.html)

[返回True如果_settings_通过这种音频设备所支持](qaudiodeviceinfo.html)[QAudioDeviceInfo](qaudiodeviceinfo.html)。

```
bool QAudioDeviceInfo.isNull (self)
```

返回是否该[QAudioDeviceInfo](qaudiodeviceinfo.html)对象持有设备的定义。

```
QAudioFormat QAudioDeviceInfo.nearestFormat (self, QAudioFormat format)
```

[](qaudioformat.html)

[最接近的回报](qaudioformat.html)[QAudioFormat](qaudioformat.html)至_settings_该系统的音频支持。

由平台/音频插件被用来提供这些设置。

他们也都依赖于[QAudio.Mode](qaudio.html#Mode-enum)被使用。

```
QAudioFormat QAudioDeviceInfo.preferredFormat (self)
```

[](qaudioformat.html)

[Returns](qaudioformat.html) [QAudioFormat](qaudioformat.html)的默认设置。

由平台/音频插件被用来提供这些设置。

他们也都依赖于[QAudio.Mode](qaudio.html#Mode-enum)被使用。

一个典型的音响系统可以提供这样的：

*   Input settings: 8000Hz mono 8 bit.
*   Output settings: 44100Hz stereo 16 bit little endian.

```
list-of-QAudioFormat.Endian QAudioDeviceInfo.supportedByteOrders (self)
```

返回所支持的字节顺序列表。

```
list-of-int QAudioDeviceInfo.supportedChannelCounts (self)
```

返回所支持的通道数的列表。

此功能被引入Qt的4.7 。

```
list-of-int QAudioDeviceInfo.supportedChannels (self)
```

```
QStringList QAudioDeviceInfo.supportedCodecs (self)
```

返回所支持的编解码器的列表。

所有的平台和插件的实现应该对其提供支持：

“音频/ PCM ” - 线性PCM

对于编写插件以支持更多的编解码器是指：

http://www.iana.org/assignments/media-types/audio/

```
list-of-int QAudioDeviceInfo.supportedFrequencies (self)
```

```
list-of-int QAudioDeviceInfo.supportedSampleRates (self)
```

返回所支持的采样率的清单。

此功能被引入Qt的4.7 。

```
list-of-int QAudioDeviceInfo.supportedSampleSizes (self)
```

返回支持的采样大小的列表。

```
list-of-QAudioFormat.SampleType QAudioDeviceInfo.supportedSampleTypes (self)
```

返回支持的采样类型的列表。