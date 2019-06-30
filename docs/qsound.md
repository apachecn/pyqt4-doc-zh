# QSound Class Reference

## [[QtGui](index.htm) module]

该QSound的类提供了访问平台的音频设备。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QString filename, QObject parent = None)`
*   `QString fileName (self)`
*   `bool isFinished (self)`
*   `int loops (self)`
*   `int loopsRemaining (self)`
*   `play (self)`
*   `setLoops (self, int)`
*   `stop (self)`

### Static Methods

*   `bool isAvailable ()`
*   `play (QString filename)`

* * *

## Detailed Description

该QSound的类提供了访问平台的音频设备。

Qt提供了最常用的音频需要在运行GUI应用程序：异步播放声音文件。这是通过使用静态最容易实现[play](qsound.html#play)（ ）函数：

```
 QSound.play("mysounds/bells.wav");

```

另外，从声音文件首先创建一个QSound的对象，然后调用[play](qsound.html#play)（）槽：

```
 QSound bells("mysounds/bells.wav");
 bells.play();

```

一旦创建了QSound的对象可以查询其[fileName](qsound.html#fileName)（）和总数[loops](qsound.html#loops)（） （即次数声音的播放方式） 。重复的次数可以使用被改变的[setLoops](qsound.html#setLoops)（）函数。当演奏声中，[loopsRemaining](qsound.html#loopsRemaining)（）函数返回重复的剩馀数量。使用[isFinished](qsound.html#isFinished)（ ）函数来确定声音是否已经播放完毕。

使用QSound的对象可能会使用更多的内存比静态的声音发挥[play](qsound.html#play)（ ）函数，但它也可能更立即播放（取决于底层平台的音频设备） 。使用静态[isAvailable](qsound.html#isAvailable)（ ）函数来确定是否在该平台上存在的音响设备。这是实际使用的设备各不相同：

| Platform | Audio Facility |
| --- | --- |
| Microsoft Windows | The underlying multimedia system is used; only WAVE format sound files are supported. |
| X11 | The [resources](http://pyqt4doc.appspot.com/resources.html)。这可能会在将来的版本的Qt 。

* * *

## Method Documentation

```
QSound.__init__ (self, QString filename, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。构造一个[QSound](qsound.html)由给定的所指定的文件中的对象_filename_并用给定的_parent_。这可能会使用更多的内存比静态[play](qsound.html#play)（ ）函数，但它也可能更立即播放（取决于底层平台的音频设备） 。**See also** [play](qsound.html#play)（ ） 。

```
QString QSound.fileName (self)
```

返回与此相关联的文件名[QSound](qsound.html)对象。**See also** [QSound](qsound.html#QSound)（ ） 。

```
bool QSound.isAvailable ()
```

返回True如果平台上存在的音响设备，否则返回False 。如果没有健全的可用，所有[QSound](qsound.html)操作默默工作，迅速。应用程序可以选择要么通知用户，如果声音是至关重要的应用程序，或在后台运行而不打扰用户。注意：在Windows这个总是因为一些声卡驱动没有实现的方式，找出它是否适用或不返回True 。

```
bool QSound.isFinished (self)
```

返回True如果声音播放完毕，否则返回False 。**Warning:**在Windows中这个函数总是不成圈的声音返回True 。

```
int QSound.loops (self)
```

返回的时候声音会玩的次数。**See also** [loopsRemaining](qsound.html#loopsRemaining)（）和[setLoops](qsound.html#setLoops)（ ） 。

```
int QSound.loopsRemaining (self)
```

返回剩馀次数的声音将循环（这个值每个声音被播放的时间减少）。**See also** [loops](qsound.html#loops)（）和[isFinished](qsound.html#isFinished)（ ） 。

```
QSound.play (QString filename)
```

播放声音存储由给定指定的文件中_filename_。**See also** [stop](qsound.html#stop)（ ）[loopsRemaining](qsound.html#loopsRemaining)（）和[isFinished](qsound.html#isFinished)（ ） 。

```
QSound.play (self)
```

这种方法也是一个Qt槽与C + +的签名`void play()`。这是一个重载函数。开始播放由这个指定的声音[QSound](qsound.html)对象。该函数立即返回。根据平台的音频设备，其他声音可能会停止或与新的声音混合。声音可以再次在任何时间进行播放，可能混合或替换的声音以前次。**See also** [fileName](qsound.html#fileName)（ ） 。

```
QSound.setLoops (self, int)
```

设置重复给出的声音_number_当它被播放的时间。注意，传递的值-1会导致声音无限循环。**See also** [loops](qsound.html#loops)（ ） 。

```
QSound.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。停止播放声音。请注意，在Windows上的电流回路将完成，如果一个播放声音在一个循环。**See also** [play](qsound.html#play)（ ） 。 |