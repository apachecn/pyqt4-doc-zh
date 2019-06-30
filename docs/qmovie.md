# QMovie Class Reference

## [[QtGui](index.htm) module]

该QMovie类是一个方便的类，用于播放电影的[QImageReader](qimagereader.html)。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum CacheMode { CacheNone, CacheAll }`
*   `enum MovieState { NotRunning, Paused, Running }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QIODevice device, QByteArray format = QByteArray(), QObject parent = None)`
*   `__init__ (self, QString fileName, QByteArray format = QByteArray(), QObject parent = None)`
*   `QColor backgroundColor (self)`
*   `CacheMode cacheMode (self)`
*   `int currentFrameNumber (self)`
*   `QImage currentImage (self)`
*   `QPixmap currentPixmap (self)`
*   `QIODevice device (self)`
*   `QString fileName (self)`
*   `QByteArray format (self)`
*   `int frameCount (self)`
*   `QRect frameRect (self)`
*   `bool isValid (self)`
*   `bool jumpToFrame (self, int frameNumber)`
*   `bool jumpToNextFrame (self)`
*   `int loopCount (self)`
*   `int nextFrameDelay (self)`
*   `QSize scaledSize (self)`
*   `setBackgroundColor (self, QColor color)`
*   `setCacheMode (self, CacheMode mode)`
*   `setDevice (self, QIODevice device)`
*   `setFileName (self, QString fileName)`
*   `setFormat (self, QByteArray format)`
*   `setPaused (self, bool paused)`
*   `setScaledSize (self, QSize size)`
*   `setSpeed (self, int percentSpeed)`
*   `int speed (self)`
*   `start (self)`
*   `MovieState state (self)`
*   `stop (self)`

### Static Methods

*   `list-of-QByteArray supportedFormats ()`

### Qt Signals

*   `void error (QImageReader::ImageReaderError)`
*   `void finished ()`
*   `void frameChanged (int)`
*   `void resized (const QSize&)`
*   `void started ()`
*   `void stateChanged (QMovie::MovieState)`
*   `void updated (const QRect&)`

* * *

## Detailed Description

该QMovie类是一个方便的类，用于播放电影的[QImageReader](qimagereader.html)。

这个类是用来显示简单的动画没有声音。如果你想显示的视频和媒体内容，使用[Phonon](index.htm)多媒体框架来代替。

首先，通过传递一个文件的名称或一个指向创建QMovie对象[QIODevice](qiodevice.html)含动画图像格式QMovie的构造函数。您可以致电[isValid](qmovie.html#isValid)（） ，以检查是否在图像数据是有效的，从电影之前。开始播放影片，通话[start](qmovie.html#start)（ ） 。 QMovie将进入[Running](qmovie.html#MovieState-enum)状态，并放出[started](qmovie.html#started)（）和[stateChanged](qmovie.html#stateChanged)（ ） 。为了得到影片的当前状态，请致电[state](qmovie.html#state)（ ） 。

若要显示影片在您的应用程序，你可以通过你的QMovie对象[QLabel.setMovie](qlabel.html#setMovie)（ ） 。例如：

```
 [QLabel](qlabel.html) label;
 QMovie *movie = new QMovie("animations/fire.gif");

 label.setMovie(movie);
 movie->start();

```

每当一个新的框架是在电影中使用， QMovie会发出[updated](qmovie.html#updated)（ ） 。如果该帧的大小变化，[resized](qmovie.html#resized)（）被发射。您可以致电[currentImage](qmovie.html#currentImage)（）或[currentPixmap](qmovie.html#currentPixmap)（ ）来获得当前帧的副本。当影片完成后， QMovie发出[finished](qmovie.html#finished)（ ） 。如果播放（即图像文件已损坏）过程中发生任何错误， QMovie会发出[error](qmovie.html#error)（ ） 。

你可以通过调用控制影片的播放速度[setSpeed](qmovie.html#speed-prop)（），它采用原始速度的百分比作为参数。通过调用setPaused （真）暂停电影。 QMovie将进入[Paused](qmovie.html#MovieState-enum)国家和EMIT[stateChanged](qmovie.html#stateChanged)（ ） 。如果调用setPaused （假） ， QMovie将重新进入[Running](qmovie.html#MovieState-enum)状态，然后再次开始播放电影。停止播放视频，呼叫[stop](qmovie.html#stop)（ ） 。

某些动画格式允许您设置背景颜色。您可以致电[setBackgroundColor](qmovie.html#setBackgroundColor)（）来设置颜色，或[backgroundColor](qmovie.html#backgroundColor)（）来获取当前背景色。

[currentFrameNumber](qmovie.html#currentFrameNumber)（）返回在当前帧的序列号。在动画的第一帧具有序列号0。[frameCount](qmovie.html#frameCount)（）返回的帧的总数目在动画中，如果图像格式支持这一点。您可以致电[loopCount](qmovie.html#loopCount)（ ）来获得本次电影应该在完成循环之前的数量。[nextFrameDelay](qmovie.html#nextFrameDelay)（）返回毫秒为单位的当前帧应该显示的数目。

QMovie可以通过调用被指示动画的帧缓存[setCacheMode](qmovie.html#cacheMode-prop)（ ） 。

Call [supportedFormats](qmovie.html#supportedFormats)（ ）对于格式的列表QMovie支持。

* * *

## Type Documentation

```
QMovie.CacheMode
```

这个枚举变量描述了不同的缓存模式[QMovie](qmovie.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QMovie.CacheNone` | `0` | 没有帧缓存（默认值） 。 |
| `QMovie.CacheAll` | `1` | 所有的帧缓存。 |

```
QMovie.MovieState
```

该枚举描述的不同状态[QMovie](qmovie.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QMovie.NotRunning` | `0` | 这部电影没有运行。这是[QMovie](qmovie.html)的初始状态，并且状态后，它进入[stop](qmovie.html#stop)（ ）被调用或电影结束。 |
| `QMovie.Paused` | `1` | 电影被暂停，并[QMovie](qmovie.html)停止发光[updated](qmovie.html#updated)（）或[resized](qmovie.html#resized)（ ） 。调用后进入此状态[pause](index.htm#pause)（ ）或setPaused （真） 。当前帧号是蒙了，这部电影将继续与下一帧时[unpause](index.htm#unpause)（）或setPaused （假）被调用。 |
| `QMovie.Running` | `2` | 这部电影正在运行。 |

* * *

## Method Documentation

```
QMovie.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QMovie](qmovie.html)对象，通过_parent_反对[QObject](qobject.html)的构造。

**See also** [setFileName](qmovie.html#setFileName)（ ）[setDevice](qmovie.html#setDevice)（）和[setFormat](qmovie.html#setFormat)（ ） 。

```
QMovie.__init__ (self, QIODevice device, QByteArray format = QByteArray(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QMovie](qmovie.html)对象。[QMovie](qmovie.html)将使用读取的图像数据从_device_，它假定为开放性和可读性。如果_format_不为空，[QMovie](qmovie.html)将使用的图像格式_format_对图像数据进行解码。否则，[QMovie](qmovie.html)会尝试猜测的格式。

该_parent_对象被传递给[QObject](qobject.html)的构造。

```
QMovie.__init__ (self, QString fileName, QByteArray format = QByteArray(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QMovie](qmovie.html)对象。[QMovie](qmovie.html)将使用读取的图像数据从_fileName_。如果_format_不为空，[QMovie](qmovie.html)将使用的图像格式_format_对图像数据进行解码。否则，[QMovie](qmovie.html)会尝试猜测的格式。

该_parent_对象被传递给[QObject](qobject.html)的构造。

```
QColor QMovie.backgroundColor (self)
```

[](qcolor.html)

[返回电影的背景颜色。如果没有背景色已经被分配，一个无效的](qcolor.html)[QColor](qcolor.html)返回。

**See also** [setBackgroundColor](qmovie.html#setBackgroundColor)（ ） 。

```
CacheMode QMovie.cacheMode (self)
```

[

```
int QMovie.currentFrameNumber (self)
```

返回当前帧的序列号。在电影的第一帧的数目是0。

](qmovie.html#CacheMode-enum)

```
QImage QMovie.currentImage (self)
```

[](qimage.html)

[返回当前帧作为](qimage.html)[QImage](qimage.html)。

**See also** [currentPixmap](qmovie.html#currentPixmap)（）和[updated](qmovie.html#updated)（ ） 。

```
QPixmap QMovie.currentPixmap (self)
```

[](qpixmap.html)

[返回当前帧作为](qpixmap.html)[QPixmap](qpixmap.html)。

**See also** [currentImage](qmovie.html#currentImage)（）和[updated](qmovie.html#updated)（ ） 。

```
QIODevice QMovie.device (self)
```

[](qiodevice.html)

[返回设备](qiodevice.html)[QMovie](qmovie.html)从读取图像数据。如果没有设备目前已被分配，则返回0 。

**See also** [setDevice](qmovie.html#setDevice)（）和[fileName](qmovie.html#fileName)（ ） 。

```
QString QMovie.fileName (self)
```

返回的文件的名称[QMovie](qmovie.html)从读取图像数据。如果没有文件名已经被分配，或者如果指定的设备是不是一个文件，一个空[QString](qstring.html)返回。

**See also** [setFileName](qmovie.html#setFileName)（）和[device](qmovie.html#device)（ ） 。

```
QByteArray QMovie.format (self)
```

[](qbytearray.html)

[返回格式](qbytearray.html)[QMovie](qmovie.html)图像数据进行解码时使用。如果没有指定格式已经被分配，一个空QByteArray中（ ）返回。

**See also** [setFormat](qmovie.html#setFormat)（ ） 。

```
int QMovie.frameCount (self)
```

返回帧的电影数量。

某些动画格式不支持此功能，在这种情况下，返回0。

```
QRect QMovie.frameRect (self)
```

[](qrect.html)

[返回的最后一帧的正确。如果没有框架至今尚未更新，无效](qrect.html)[QRect](qrect.html)返回。

**See also** [currentImage](qmovie.html#currentImage)（）和[currentPixmap](qmovie.html#currentPixmap)（ ） 。

```
bool QMovie.isValid (self)
```

返回True如果影片是有效的（例如，图像数据是可读的，并且所支持的图像格式），否则返回False 。

```
bool QMovie.jumpToFrame (self, int frameNumber)
```

跳转到帧号_frameNumber_。成功时返回TRUE ，否则返回False 。

```
bool QMovie.jumpToNextFrame (self)
```

这种方法也是一个Qt槽与C + +的签名`bool jumpToNextFrame()`。

跳转到下一帧。成功时返回TRUE ，否则返回False 。

```
int QMovie.loopCount (self)
```

返回的次数这部电影将循环完成之前。如果影片只能播放一次（无循环） ， loopCount返回0 。如果影片永远循环， loopCount返回-1 。

需要注意的是，如果图像数据是来自一个连续的设备（例如一插座）[QMovie](qmovie.html)如果只能回路的电影[cacheMode](qmovie.html#cacheMode-prop)被设置为[QMovie.CacheAll](qmovie.html#CacheMode-enum)。

```
int QMovie.nextFrameDelay (self)
```

返回的毫秒数[QMovie](qmovie.html)更新在动画中的下一帧之前，将等待。

```
QSize QMovie.scaledSize (self)
```

[

返回的帧的缩放大小。

这个函数是Qt 4.1中引入。

](qsize.html)

[**See also**](qsize.html) [setScaledSize](qmovie.html#setScaledSize)（）和[QImageReader.scaledSize](qimagereader.html#scaledSize)（ ） 。

```
QMovie.setBackgroundColor (self, QColor color)
```

对于支持它的图像格式，该函数设置背景颜色为_color_。

**See also** [backgroundColor](qmovie.html#backgroundColor)（ ） 。

```
QMovie.setCacheMode (self, CacheMode mode)
```

```
QMovie.setDevice (self, QIODevice device)
```

设置当前设备_device_。[QMovie](qmovie.html)会从电影运行时该设备读取的图像数据。

**See also** [device](qmovie.html#device)（）和[setFormat](qmovie.html#setFormat)（ ） 。

```
QMovie.setFileName (self, QString fileName)
```

载的文件的名称[QMovie](qmovie.html)读取图像数据，以_fileName_。

**See also** [fileName](qmovie.html#fileName)（ ）[setDevice](qmovie.html#setDevice)（）和[setFormat](qmovie.html#setFormat)（ ） 。

```
QMovie.setFormat (self, QByteArray format)
```

设置格式[QMovie](qmovie.html)解码图像数据时，要会用_format_。默认情况下，[QMovie](qmovie.html)会尝试猜测的图像数据的格式。

您可以致电[supportedFormats](qmovie.html#supportedFormats)（ ）对于格式的完整列表[QMovie](qmovie.html)支持。

**See also** [format](qmovie.html#format)（）和[QImageReader.supportedImageFormats](qimagereader.html#supportedImageFormats)（ ） 。

```
QMovie.setPaused (self, bool paused)
```

这种方法也是一个Qt槽与C + +的签名`void setPaused(bool)`。

If _paused_是真的，[QMovie](qmovie.html)将进入[Paused](qmovie.html#MovieState-enum)状态并放出stateChanged （暂停） ，否则将进入[Running](qmovie.html#MovieState-enum)状态并放出stateChanged （运行） 。

**See also** [paused](index.htm#paused)（）和[state](qmovie.html#state)（ ） 。

```
QMovie.setScaledSize (self, QSize size)
```

设置缩放帧尺寸为_size_。

这个函数是Qt 4.1中引入。

**See also** [scaledSize](qmovie.html#scaledSize)（）和[QImageReader.setScaledSize](qimagereader.html#setScaledSize)（ ） 。

```
QMovie.setSpeed (self, int percentSpeed)
```

```
int QMovie.speed (self)
```

```
QMovie.start (self)
```

这种方法也是一个Qt槽与C + +的签名`void start()`。

开始播放电影。[QMovie](qmovie.html)将进入[Running](qmovie.html#MovieState-enum)状态，并开始发光[updated](qmovie.html#updated)（）和[resized](qmovie.html#resized)（ ）作为电影的进展。

If [QMovie](qmovie.html)在[Paused](qmovie.html#MovieState-enum)状态时，此功能相当于调用setPaused （假） 。如果[QMovie](qmovie.html)已经在[Running](qmovie.html#MovieState-enum)状态，这个函数什么都不做。

**See also** [stop](qmovie.html#stop)（）和[setPaused](qmovie.html#setPaused)（ ） 。

```
MovieState QMovie.state (self)
```

[](qmovie.html#MovieState-enum)

[返回的当前状态](qmovie.html#MovieState-enum)[QMovie](qmovie.html)。

**See also** [MovieState](qmovie.html#MovieState-enum)和[stateChanged](qmovie.html#stateChanged)（ ） 。

```
QMovie.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。

停止该影片。[QMovie](qmovie.html)进入[NotRunning](qmovie.html#MovieState-enum)状态，并停止发出[updated](qmovie.html#updated)（）和[resized](qmovie.html#resized)（ ） 。如果[start](qmovie.html#start)（ ）再次被调用时，影片将从头开始重新启动。

If [QMovie](qmovie.html)已经在[NotRunning](qmovie.html#MovieState-enum)状态，这个函数什么都不做。

**See also** [start](qmovie.html#start)（）和[setPaused](qmovie.html#setPaused)（ ） 。

```
list-of-QByteArray QMovie.supportedFormats ()
```

传回的图像格式所支持的列表[QMovie](qmovie.html)。

这个函数是Qt 4.1中引入。

**See also** [QImageReader.supportedImageFormats](qimagereader.html#supportedImageFormats)（ ） 。

* * *

## Qt Signal Documentation

```
void error (QImageReader::ImageReaderError)
```

这是该信号的默认超载。

这个信号是由发射[QMovie](qmovie.html)当错误_error_在播放过程中发生的。[QMovie](qmovie.html)将停止播放电影，并输入[QMovie.NotRunning](qmovie.html#MovieState-enum)状态。

```
void finished ()
```

这是该信号的默认超载。

当影片结束这个信号被发射。

**See also** [QMovie.stop](qmovie.html#stop)（ ） 。

```
void frameChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的帧编号变更为_frameNumber_。您可以致电[currentImage](qmovie.html#currentImage)（）或[currentPixmap](qmovie.html#currentPixmap)（ ）来获取帧的副本。

这个函数是Qt 4.1中引入。

```
void resized (const QSize&)
```

这是该信号的默认超载。

当当前帧已经被改变到这一信号被发射_size_。这种效果有时用于动画作为替代更换帧。您可以致电[currentImage](qmovie.html#currentImage)（）或[currentPixmap](qmovie.html#currentPixmap)（ ）来获取更新的帧的副本。

```
void started ()
```

这是该信号的默认超载。

之后此信号被发射[QMovie.start](qmovie.html#start)（ ）被调用，并[QMovie](qmovie.html)已进入[QMovie.Running](qmovie.html#MovieState-enum)状态。

```
void stateChanged (QMovie::MovieState)
```

这是该信号的默认超载。

每当这个信号被发射的电影的状态发生改变。新的状态被指定_state_。

**See also** [QMovie.state](qmovie.html#state)（ ） 。

```
void updated (const QRect&)
```

这是该信号的默认超载。

这个信号被发射时的RECT_rect_在当前帧中已被更新。您可以致电[currentImage](qmovie.html#currentImage)（）或[currentPixmap](qmovie.html#currentPixmap)（ ）来获取更新的帧的副本。