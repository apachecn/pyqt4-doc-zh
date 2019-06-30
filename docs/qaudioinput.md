# QAudioInput Class Reference

## [[QtMultimedia](index.htm) module]

该QAudioInput类提供用于从音频输入设备接收音频数据的接口。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QAudioFormat format = QAudioFormat(), QObject parent = None)`
*   `__init__ (self, QAudioDeviceInfo audioDevice, QAudioFormat format = QAudioFormat(), QObject parent = None)`
*   `int bufferSize (self)`
*   `int bytesReady (self)`
*   `int elapsedUSecs (self)`
*   `QAudio.Error error (self)`
*   `QAudioFormat format (self)`
*   `int notifyInterval (self)`
*   `int periodSize (self)`
*   `int processedUSecs (self)`
*   `reset (self)`
*   `resume (self)`
*   `setBufferSize (self, int bytes)`
*   `setNotifyInterval (self, int milliSeconds)`
*   `start (self, QIODevice device)`
*   `QIODevice start (self)`
*   `QAudio.State state (self)`
*   `stop (self)`
*   `suspend (self)`

### Qt Signals

*   `void notify ()`
*   `void stateChanged (QAudio::State)`

* * *

## Detailed Description

该QAudioInput类提供用于从音频输入设备接收音频数据的接口。

可以构造与系统的音频输入[default audio input device](qaudiodeviceinfo.html#defaultInputDevice)。它也可能与特定的创建QAudioInput[QAudioDeviceInfo](qaudiodeviceinfo.html)。当您创建了音频输入，你也应该送的[QAudioFormat](qaudioformat.html)用于记录（见[QAudioFormat](qaudioformat.html)类描述详情） 。

要录制到一个文件：

QAudioInput让您录制音频，音频输入设备。这个类的默认构造函数将使用系统默认的音频设备，但您也可以指定一个[QAudioDeviceInfo](qaudiodeviceinfo.html)对于特定的设备。您还需要通过在[QAudioFormat](qaudioformat.html)要在其中进行录制。

启动了QAudioInput是简单地调用的问题[start](qaudioinput.html#start)（ ）与[QIODevice](qiodevice.html)打开以进行写入。例如，记录到一个文件中，您可以：

```
     [QFile](qfile.html) outputFile;         // class member.
     QAudioInput *audioInput;  // class member.
     ...
     void startRecording()
     {
         outputFile.setFileName("/tmp/test.raw");
         outputFile.open( [QIODevice](qiodevice.html).WriteOnly | [QIODevice](qiodevice.html).Truncate );

         [QAudioFormat](qaudioformat.html) format;
         // set up the format you want, eg.
         format.setFrequency(8000);
         format.setChannels(1);
         format.setSampleSize(8);
         format.setCodec("audio/pcm");
         format.setByteOrder([QAudioFormat](qaudioformat.html).LittleEndian);
         format.setSampleType([QAudioFormat](qaudioformat.html).UnSignedInt);

         [QAudioDeviceInfo](qaudiodeviceinfo.html) info = [QAudioDeviceInfo](qaudiodeviceinfo.html).defaultInputDevice();
         if (!info.isFormatSupported(format)) {
             qWarning()<<"default format not supported try to use nearest";
             format = info.nearestFormat(format);
         }

         audioInput = new QAudioInput(format, this);
         [QTimer](qtimer.html).singleShot(3000, this, SLOT(stopRecording()));
         audioInput->start(&outputFile);
         // Records audio for 3000ms
     }

```

如果指定的格式是支持的输入设备即会开始拍摄（你可以通过检查[QAudioDeviceInfo.isFormatSupported](qaudiodeviceinfo.html#isFormatSupported)（ ） 。万一有任何障碍，则使用[error](qaudioinput.html#error)（ ）函数来检查哪里出了问题。我们在停止录制`stopRecording()`插槽。

```
     void stopRecording()
     {
         audioInput->stop();
         outputFile.close();
         delete audioInput;
     }

```

在任何时间点， QAudioInput将在四种状态之一：主动，暂停，停止或閒置。这些状态是由指定的[QAudio.State](qaudio.html#State-enum)枚举。您可以直接通过请求状态变化[suspend](qaudioinput.html#suspend)（ ）[resume](qaudioinput.html#resume)（ ）[stop](qaudioinput.html#stop)（ ）[reset](qaudioinput.html#reset)（）和[start](qaudioinput.html#start)（ ） 。当前状态被报告的[state](qaudioinput.html#state)（ ） 。[QAudioOutput](qaudiooutput.html)也将标志着你当状态变化（[stateChanged](qaudioinput.html#stateChanged)（））。

QAudioInput提供测量时间的几种方法以来已经经过的[start](qaudioinput.html#start)记录的（） 。该`processedUSecs()`函数返回流的长度以书面微秒，即，它留下了时代的音频输入被暂停或閒置。该[elapsedUSecs](qaudioinput.html#elapsedUSecs)（ ）函数返回自所经过的时间[start](qaudioinput.html#start)（ ）被调用，无论哪种状态下QAudioInput已经英寸的

如果发生错误，您可以获取其原因与[error](qaudioinput.html#error)（ ） 。可能的错误的原因是由所描述的[QAudio.Error](qaudio.html#Error-enum)枚举。该QAudioInput将进入[StoppedState](qaudio.html#State-enum)当遇到错误。连接到[stateChanged](qaudioinput.html#stateChanged)（ ）信号来处理错误：

```
     void stateChanged([QAudio](qaudio.html).State newState)
     {
         switch(newState) {
             case [QAudio](qaudio.html).StoppedState:
             if (audioInput->error() != [QAudio](qaudio.html).NoError) {
                  // Perform error handling
             } else {

             }
             break;

```

### Symbian Platform Security Requirements

在Symbian ，它使用这个类的进程必须有`UserEnvironment`平台的安全能力。如果客户端程序缺乏这种能力，调用任过载[start](qaudioinput.html#start)（ ）将失败。此故障是由QAudioInput对象设置表示其[error](qaudioinput.html#error)（ ）值[QAudio.OpenError](qaudio.html#Error-enum)然后散发出[stateChanged](qaudioinput.html#stateChanged)（[QAudio.StoppedState](qaudio.html#State-enum)）信号。

平台的安全功能是通过添加[TARGET.CAPABILITY](index.htm#target-capability)qmake的变量。

* * *

## Method Documentation

```
QAudioInput.__init__ (self, QAudioFormat format = QAudioFormat(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的音频输入，并将它附加到_parent_。默认的音频输入设备是用来与输出_format_参数。

```
QAudioInput.__init__ (self, QAudioDeviceInfo audioDevice, QAudioFormat format = QAudioFormat(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的音频输入，并将它附加到_parent_。通过引用的设备_audioDevice_用于与所述输入_format_参数。

```
int QAudioInput.bufferSize (self)
```

返回以毫秒为单位的音频缓冲器的大小。

如果之前调用[start](qaudioinput.html#start)（ ） ，返回平台的默认值。如果之前调用[start](qaudioinput.html#start)（），但[setBufferSize](qaudioinput.html#setBufferSize)（ ）之前被调用，返回值被设置[setBufferSize](qaudioinput.html#setBufferSize)（ ） 。如果所谓的后[start](qaudioinput.html#start)（）时，返回所使用的实际的缓冲区大小。这可能不是通过预先设定的[setBufferSize](qaudioinput.html#setBufferSize)（ ） 。

**See also** [setBufferSize](qaudioinput.html#setBufferSize)（ ） 。

```
int QAudioInput.bytesReady (self)
```

返回的音频数据提供给读出以字节为单位的量。

注：返回值是唯一有效的，而在[QAudio.ActiveState](qaudio.html#State-enum) or [QAudio.IdleState](qaudio.html#State-enum)状态，否则返回零。

```
int QAudioInput.elapsedUSecs (self)
```

返回微秒，因为[start](qaudioinput.html#start)（ ）被调用，包括时间，空閒和待机状态。

```
QAudio.Error QAudioInput.error (self)
```

[

返回的错误状态。

](qaudio.html#Error-enum)

```
QAudioFormat QAudioInput.format (self)
```

[](qaudioformat.html)

[返回](qaudioformat.html)[QAudioFormat](qaudioformat.html)被使用。

```
int QAudioInput.notifyInterval (self)
```

返回以毫秒为单位的通知时间间隔。

**See also** [setNotifyInterval](qaudioinput.html#setNotifyInterval)（ ） 。

```
int QAudioInput.periodSize (self)
```

返回以字节为单位的周期大小。

注：这是在字节读取的所建议的大小。

```
int QAudioInput.processedUSecs (self)
```

返回音频数据的自处理的量[start](qaudioinput.html#start)（ ）被调用以微秒为单位。

```
QAudioInput.reset (self)
```

滴在缓冲区所有的音频数据，缓冲区复位到零。

```
QAudioInput.resume (self)
```

恢复后处理音频数据[suspend](qaudioinput.html#suspend)（ ） 。

Sets [error](qaudioinput.html#error)（）来[QAudio.NoError](qaudio.html#Error-enum)。套[state](qaudioinput.html#state)（）来[QAudio.ActiveState](qaudio.html#State-enum)如果您以前调用start （[QIODevice](qiodevice.html)*）。套[state](qaudioinput.html#state)（）来[QAudio.IdleState](qaudio.html#State-enum)如果您以前叫[start](qaudioinput.html#start)（ ） 。发射[stateChanged](qaudioinput.html#stateChanged)（）信号。

```
QAudioInput.setBufferSize (self, int bytes)
```

设置音频缓冲区的大小为_value_毫秒。

注：此功能可以在任何时候之前调用[start](qaudioinput.html#start)（ ） ，调用此之后将被忽略[start](qaudioinput.html#start)（ ） 。它不应该被假定缓冲区的大小设置为实际使用的缓冲区大小，调用[bufferSize](qaudioinput.html#bufferSize)（）后随时[start](qaudioinput.html#start)（）将返回所用的实际的缓冲区大小。

**See also** [bufferSize](qaudioinput.html#bufferSize)（ ） 。

```
QAudioInput.setNotifyInterval (self, int milliSeconds)
```

设置的时间间隔[notify](qaudioinput.html#notify)（）信号被发射。这是基于_ms_处理不实际的实时音频数据。定时器的最小分辨率为特定平台和值应进行检查[notifyInterval](qaudioinput.html#notifyInterval)（ ）确认正在使用的实际值。

**See also** [notifyInterval](qaudioinput.html#notifyInterval)（ ） 。

```
QAudioInput.start (self, QIODevice device)
```

使用_device_作为[QIODevice](qiodevice.html)来传输数据。传递[QIODevice](qiodevice.html)允许数据被无任何额外的代码传输。所有需要的是打开[QIODevice](qiodevice.html)。[QAudioInput](qaudioinput.html)不采取所有权_device_。

该[QAudioInput](qaudioinput.html)将数据写入设备时，新的数据是可用的。你可以继承[QIODevice](qiodevice.html)并重新实现[writeData()](qiodevice.html#writeData)如果你想访问的数据。如果您只是想将数据保存到一个文件中，你可以通过一个[QFile](qfile.html)此功能。

如果能够成功地获得音频数据从系统音频设备[state](qaudioinput.html#state)（）被设置为[QAudio.ActiveState](qaudio.html#State-enum) or [QAudio.IdleState](qaudio.html#State-enum)，[error](qaudioinput.html#error)（ ）被设置为[QAudio.NoError](qaudio.html#Error-enum)和[stateChanged](qaudioinput.html#stateChanged)（）信号被发射。

如果在这个过程中发生问题的[error](qaudioinput.html#error)（ ）被设置为[QAudio.OpenError](qaudio.html#Error-enum)，[state](qaudioinput.html#state)（ ）被设置为[QAudio.StoppedState](qaudio.html#State-enum)和[stateChanged](qaudioinput.html#stateChanged)（）信号被发射。

[QAudioInput#Symbian Platform Security Requirements](qaudioinput.html#symbian-platform-security-requirements)

**See also** [QIODevice](qiodevice.html)。

```
QIODevice QAudioInput.start (self)
```

[](qiodevice.html)

[返回一个指针，一个新的](qiodevice.html)[QIODevice](qiodevice.html)将用于处理数据传输。这[QIODevice](qiodevice.html)可用于[read()](qiodevice.html#read)音频数据直接。你通常会连接到[readyRead()](qiodevice.html#readyRead)信号，并从该设备中的时隙读取您连接到。[QAudioInput](qaudioinput.html)保持设备的所有权。

如果能够访问该系统音频设备的[state](qaudioinput.html#state)（ ）被设置为[QAudio.IdleState](qaudio.html#State-enum)，[error](qaudioinput.html#error)（ ）被设置为[QAudio.NoError](qaudio.html#Error-enum)和[stateChanged](qaudioinput.html#stateChanged)（）信号被发射。

如果在这个过程中发生问题的[error](qaudioinput.html#error)（ ）被设置为[QAudio.OpenError](qaudio.html#Error-enum)，[state](qaudioinput.html#state)（ ）被设置为[QAudio.StoppedState](qaudio.html#State-enum)和[stateChanged](qaudioinput.html#stateChanged)（）信号被发射。

[QAudioInput#Symbian Platform Security Requirements](qaudioinput.html#symbian-platform-security-requirements)

**See also** [QIODevice](qiodevice.html)。

```
QAudio.State QAudioInput.state (self)
```

[

返回音频处理的状态。

```
QAudioInput.stop (self)
```

停止音频输入，从系统资源分离。

](qaudio.html#State-enum)

[Sets](qaudio.html#State-enum) [error](qaudioinput.html#error)（）来[QAudio.NoError](qaudio.html#Error-enum)，[state](qaudioinput.html#state)（）来[QAudio.StoppedState](qaudio.html#State-enum)并放出[stateChanged](qaudioinput.html#stateChanged)（）信号。

```
QAudioInput.suspend (self)
```

停止处理的音频数据，保存缓冲音频数据。

Sets [error](qaudioinput.html#error)（）来[QAudio.NoError](qaudio.html#Error-enum)，[state](qaudioinput.html#state)（）来[QAudio.SuspendedState](qaudio.html#State-enum)并放出[stateChanged](qaudioinput.html#stateChanged)（）信号。

* * *

## Qt Signal Documentation

```
void notify ()
```

这是该信号的默认超载。

当音频数据x毫秒已被处理的时间间隔由setNotifyInterval （ x）的设置这个信号被发射。

```
void stateChanged (QAudio::State)
```

这是该信号的默认超载。

这个信号被发射时，该设备_state_已经改变。