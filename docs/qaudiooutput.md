# QAudioOutput Class Reference

## [[QtMultimedia](index.htm) module]

该QAudioOutput类提供用于发送音频数据到音频输出设备的接口。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QAudioFormat format = QAudioFormat(), QObject parent = None)`
*   `__init__ (self, QAudioDeviceInfo audioDevice, QAudioFormat format = QAudioFormat(), QObject parent = None)`
*   `int bufferSize (self)`
*   `int bytesFree (self)`
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

该QAudioOutput类提供用于发送音频数据到音频输出设备的接口。

可以构造与系统的音频输出[default audio output device](qaudiodeviceinfo.html#defaultOutputDevice)。它也可能与特定的创建QAudioOutput[QAudioDeviceInfo](qaudiodeviceinfo.html)。当您创建音频输出，你也应该送的[QAudioFormat](qaudioformat.html)要用于再现（见[QAudioFormat](qaudioformat.html)类描述详情） 。

要播放的文件：

开始播放音频流是简单地调用的问题[start](qaudiooutput.html#start)（ ）与[QIODevice](qiodevice.html)。 QAudioOutput然后将它拿来从IO设备所需要的数据。所以回放音频文件就是这么简单：

```
     [QFile](qfile.html) inputFile;           // class member.
     QAudioOutput *audioOutput; // class member.
     ...
     void startPlaying()
     {
         inputFile.setFileName("/tmp/test.raw");
         inputFile.open([QIODevice](qiodevice.html).ReadOnly);

         [QAudioFormat](qaudioformat.html) format;
         // Set up the format, eg.
         format.setFrequency(8000);
         format.setChannels(1);
         format.setSampleSize(8);
         format.setCodec("audio/pcm");
         format.setByteOrder([QAudioFormat](qaudioformat.html).LittleEndian);
         format.setSampleType([QAudioFormat](qaudioformat.html).UnSignedInt);

         [QAudioDeviceInfo](qaudiodeviceinfo.html) info([QAudioDeviceInfo](qaudiodeviceinfo.html).defaultOutputDevice());
         if (!info.isFormatSupported(format)) {
             qWarning()<<"raw audio format not supported by backend, cannot play audio.";
             return;
         }

         audioOutput = new QAudioOutput(format, this);
         connect(audioOutput,SIGNAL(stateChanged([QAudio](qaudio.html).State)),SLOT(finishedPlaying([QAudio](qaudio.html).State)));
         audioOutput->start(&inputFile);
     }

```

该文件将开始播放假设音响系统和输出设备支持它。如果您运行的运气了，检查是怎么回事的[error](qaudiooutput.html#error)（）函数。

之后，该文件已经播放完毕，我们需要停止设备：

```
     void finishedPlaying([QAudio](qaudio.html).State state)
     {
         if (state == [QAudio](qaudio.html).IdleState) {
             audioOutput->stop();
             inputFile.close();
             delete audioOutput;
         }
     }

```

在任何给定时间， QAudioOutput将在四种状态之一：活动，暂停，停止或閒置。这些状态是由所述[QAudio.State](qaudio.html#State-enum)枚举。状态的改变是通过报导[stateChanged](qaudiooutput.html#stateChanged)（）信号。你可以使用这个信号，例如，更新应用程序的图形用户界面，在这里平凡的例子被改变的状态`play/pause`按钮。你直接请求的状态与变化[suspend](qaudiooutput.html#suspend)（ ）[stop](qaudiooutput.html#stop)（ ）[reset](qaudiooutput.html#reset)（ ）[resume](qaudiooutput.html#resume)（）和[start](qaudiooutput.html#start)（ ） 。

当流播放过程中，你可以设置一个通知的时间间隔，单位为毫秒与[setNotifyInterval](qaudiooutput.html#setNotifyInterval)（ ） 。这个时间间隔指定的两个排放之间的时间[notify](qaudiooutput.html#notify)（）信号。这是相对于数据流中的位置，即，如果QAudioOutput是在SuspendedState或IdleState ，本[notify](qaudiooutput.html#notify)（）信号不被发射。一个典型的用例是将一个更新[slider](qslider.html)允许寻求流中。如果你想的时候，因为开始播放，无论哪种状态下音频输出一直在，[elapsedUSecs](qaudiooutput.html#elapsedUSecs)（ ）的功能是给你的。

如果出现错误，你可以取[error type](qaudio.html#Error-enum)与[error](qaudiooutput.html#error)（）函数。请参阅[QAudio.Error](qaudio.html#Error-enum)枚举为所报告可能出现的错误的描述。当遇到错误时，状态更改为[QAudio.StoppedState](qaudio.html#State-enum)。您可以通过连接到检查错误[stateChanged](qaudiooutput.html#stateChanged)（ ）信号：

```
     void stateChanged([QAudio](qaudio.html).State newState)
     {
         switch (newState) {
             case [QAudio](qaudio.html).StoppedState:
                 if (audioOutput->error() != [QAudio](qaudio.html).NoError) {
                     // Perform error handling
                 } else {
                     // Normal stop
                 }
                 break;

```

* * *

## Method Documentation

```
QAudioOutput.__init__ (self, QAudioFormat format = QAudioFormat(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的音频输出，并将它附加到_parent_。默认的音频输出装置是用来与输出_format_参数。

```
QAudioOutput.__init__ (self, QAudioDeviceInfo audioDevice, QAudioFormat format = QAudioFormat(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的音频输出，并将它附加到_parent_。通过引用的设备_audioDevice_用于与输出_format_参数。

```
int QAudioOutput.bufferSize (self)
```

返回以字节为单位的音频缓冲器的大小。

如果之前调用[start](qaudiooutput.html#start)（ ） ，返回平台的默认值。如果之前调用[start](qaudiooutput.html#start)（），但[setBufferSize](qaudiooutput.html#setBufferSize)（ ）之前被调用，返回值被设置[setBufferSize](qaudiooutput.html#setBufferSize)（ ） 。如果所谓的后[start](qaudiooutput.html#start)（）时，返回所使用的实际的缓冲区大小。这可能不是通过预先设定的[setBufferSize](qaudiooutput.html#setBufferSize)（ ） 。

**See also** [setBufferSize](qaudiooutput.html#setBufferSize)（ ） 。

```
int QAudioOutput.bytesFree (self)
```

返回以字节为单位的可用空间在音频缓冲器。

注：返回值是唯一有效的，而在[QAudio.ActiveState](qaudio.html#State-enum) or [QAudio.IdleState](qaudio.html#State-enum)状态，否则返回零。

```
int QAudioOutput.elapsedUSecs (self)
```

返回微秒，因为[start](qaudiooutput.html#start)（ ）被调用，包括时间，空閒和待机状态。

```
QAudio.Error QAudioOutput.error (self)
```

[

返回的错误状态。

](qaudio.html#Error-enum)

```
QAudioFormat QAudioOutput.format (self)
```

[](qaudioformat.html)

[返回](qaudioformat.html)[QAudioFormat](qaudioformat.html)被使用。

```
int QAudioOutput.notifyInterval (self)
```

返回以毫秒为单位的通知时间间隔。

**See also** [setNotifyInterval](qaudiooutput.html#setNotifyInterval)（ ） 。

```
int QAudioOutput.periodSize (self)
```

返回以字节为单位的周期大小。

注：这是在字节写推荐大小。

```
int QAudioOutput.processedUSecs (self)
```

返回由类处理后的音频数据的量，因为[start](qaudiooutput.html#start)（ ）被调用以微秒为单位。

注意：播放的音频数据的量可以通过减去音频数据仍然在系统中的音频缓冲器的微秒来决定。

```
 [long](index.htm#qint64-typedef) bytesInBuffer = bufferSize() - bytesFree();
 [long](index.htm#qint64-typedef) usInBuffer = ([long](index.htm#qint64-typedef))(1000000) * bytesInBuffer / ( channels() * sampleSize() / 8 ) / frequency();
 [long](index.htm#qint64-typedef) usPlayed = processedUSecs() - usInBuffer;

```

```
QAudioOutput.reset (self)
```

滴在缓冲区所有的音频数据，缓冲区复位到零。

```
QAudioOutput.resume (self)
```

恢复后处理音频数据[suspend](qaudiooutput.html#suspend)（ ） 。

Sets [error](qaudiooutput.html#error)（）来[QAudio.NoError](qaudio.html#Error-enum)。套[state](qaudiooutput.html#state)（）来[QAudio.ActiveState](qaudio.html#State-enum)如果您以前调用start （[QIODevice](qiodevice.html)*）。套[state](qaudiooutput.html#state)（）来[QAudio.IdleState](qaudio.html#State-enum)如果您以前叫[start](qaudiooutput.html#start)（ ） 。发射[stateChanged](qaudiooutput.html#stateChanged)（）信号。

注：信号总是会执行的简历（ ）函数的过程中发出的。

```
QAudioOutput.setBufferSize (self, int bytes)
```

设置音频缓冲区的大小为_value_以字节为单位。

注：此功能可以在任何时候之前调用[start](qaudiooutput.html#start)（ ） ，调用此之后将被忽略[start](qaudiooutput.html#start)（ ） 。它不应该被假定缓冲区的大小设置为实际使用的缓冲区大小，调用[bufferSize](qaudiooutput.html#bufferSize)（）后随时[start](qaudiooutput.html#start)（）将返回所用的实际的缓冲区大小。

**See also** [bufferSize](qaudiooutput.html#bufferSize)（ ） 。

```
QAudioOutput.setNotifyInterval (self, int milliSeconds)
```

设置的时间间隔[notify](qaudiooutput.html#notify)（）信号被发射。这是基于_ms_处理不实际的实时音频数据。定时器的最小分辨率为特定平台和值应进行检查[notifyInterval](qaudiooutput.html#notifyInterval)（ ）确认正在使用的实际值。

**See also** [notifyInterval](qaudiooutput.html#notifyInterval)（ ） 。

```
QAudioOutput.start (self, QIODevice device)
```

使用_device_作为[QIODevice](qiodevice.html)来传输数据。传递[QIODevice](qiodevice.html)允许数据被无任何额外的代码传输。所有需要的是打开[QIODevice](qiodevice.html)。

如果能够成功地输出音频数据的系统音频设备的[state](qaudiooutput.html#state)（ ）被设置为[QAudio.ActiveState](qaudio.html#State-enum)，[error](qaudiooutput.html#error)（ ）被设置为[QAudio.NoError](qaudio.html#Error-enum)和[stateChanged](qaudiooutput.html#stateChanged)（）信号被发射。

如果在这个过程中发生问题的[error](qaudiooutput.html#error)（ ）被设置为[QAudio.OpenError](qaudio.html#Error-enum)，[state](qaudiooutput.html#state)（ ）被设置为[QAudio.StoppedState](qaudio.html#State-enum)和[stateChanged](qaudiooutput.html#stateChanged)（）信号被发射。

在任一情况下，本[stateChanged](qaudiooutput.html#stateChanged)（ ）信号可以执行start（）函数或开始后异步（ ）返回给调用者过程中，可以同步发出。

**See also** [QIODevice](qiodevice.html)。

```
QIODevice QAudioOutput.start (self)
```

[](qiodevice.html)

[返回一个指针](qiodevice.html)[QIODevice](qiodevice.html)被使用来处理数据传输。这[QIODevice](qiodevice.html)可用于直接写（）的音频数据。

如果能够访问该系统音频设备的[state](qaudiooutput.html#state)（ ）被设置为[QAudio.IdleState](qaudio.html#State-enum)，[error](qaudiooutput.html#error)（ ）被设置为[QAudio.NoError](qaudio.html#Error-enum)和[stateChanged](qaudiooutput.html#stateChanged)（）信号被发射。

如果在这个过程中发生问题的[error](qaudiooutput.html#error)（ ）被设置为[QAudio.OpenError](qaudio.html#Error-enum)，[state](qaudiooutput.html#state)（ ）被设置为[QAudio.StoppedState](qaudio.html#State-enum)和[stateChanged](qaudiooutput.html#stateChanged)（）信号被发射。

在任一情况下，本[stateChanged](qaudiooutput.html#stateChanged)（ ）信号可以执行的过程中，可以同步发出[start](qaudiooutput.html#start)（ ）函数或异步后[start](qaudiooutput.html#start)（ ）返回给调用者。

**See also** [QIODevice](qiodevice.html)。

```
QAudio.State QAudioOutput.state (self)
```

[

返回音频处理的状态。

```
QAudioOutput.stop (self)
```

停止音频输出，从系统资源分离。

](qaudio.html#State-enum)

[Sets](qaudio.html#State-enum) [error](qaudiooutput.html#error)（）来[QAudio.NoError](qaudio.html#Error-enum)，[state](qaudiooutput.html#state)（）来[QAudio.StoppedState](qaudio.html#State-enum)并放出[stateChanged](qaudiooutput.html#stateChanged)（）信号。

```
QAudioOutput.suspend (self)
```

停止处理的音频数据，保存缓冲音频数据。

Sets [error](qaudiooutput.html#error)（）来[QAudio.NoError](qaudio.html#Error-enum)，[state](qaudiooutput.html#state)（）来[QAudio.SuspendedState](qaudio.html#State-enum)并放出[stateChanged](qaudiooutput.html#stateChanged)（）信号。

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

这个信号被发射时，该设备_state_已经改变。这是音频输出的当前状态。