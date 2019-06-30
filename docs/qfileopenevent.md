# QFileOpenEvent Class Reference

## [[QtGui](index.htm) module]

该QFileOpenEvent类提供当有一个请求，打开文件或URL将发送一个事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `QString file (self)`
*   `bool openFile (self, QFile file, QIODevice.OpenMode flags)`
*   `QUrl url (self)`

* * *

## Detailed Description

该QFileOpenEvent类提供当有一个请求，打开文件或URL将发送一个事件。

文件打开事件将被发送到[QApplication.instance](qcoreapplication.html#instance)（ ）当操作系统请求一个文件或URL应该被打开。这是一个可以通过根据用户的桌面环境，不同的用户操作引起的高级别事件，例如，双击Finder中的Mac OS X上的文件图标

此事件只用于通知请求的应用程序。它可以安全地忽略。

**Note:**这个类是目前支持Mac OS X和Symbian只。

* * *

## Method Documentation

```
QString QFileOpenEvent.file (self)
```

返回正在被打开的文件。

```
bool QFileOpenEvent.openFile (self, QFile file, QIODevice.OpenMode flags)
```

打开一个[QFile](qfile.html)在_file_通过本次活动中所指定的模式参考_flags_。成功返回True ，否则返回False 。

这是必要的，因为一些文件不能被名义开立，但需要存储在该事件的具体信息。例如，如果该[QFileOpenEvent](qfileopenevent.html)包含一个请求，要求打开一个Symbian笼数据文件，该[QFile](qfile.html)只能从这个事件的结构中使用了Symbian的RFile打开。

此功能被引入Qt的4.8 。

```
QUrl QFileOpenEvent.url (self)
```

[

返回要打开的URL。

此功能被引入Qt的4.6 。

](qurl.html)