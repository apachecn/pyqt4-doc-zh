# QSessionManager Class Reference

## [[QtGui](index.htm) module]

该QSessionManager类提供了访问会话管理器。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum RestartHint { RestartIfRunning, RestartAnyway, RestartImmediately, RestartNever }`

### Methods

*   `bool allowsErrorInteraction (self)`
*   `bool allowsInteraction (self)`
*   `cancel (self)`
*   `QStringList discardCommand (self)`
*   `bool isPhase2 (self)`
*   `release (self)`
*   `requestPhase2 (self)`
*   `QStringList restartCommand (self)`
*   `RestartHint restartHint (self)`
*   `QString sessionId (self)`
*   `QString sessionKey (self)`
*   `setDiscardCommand (self, QStringList)`
*   `setManagerProperty (self, QString name, QString value)`
*   `setManagerProperty (self, QString name, QStringList value)`
*   `setRestartCommand (self, QStringList)`
*   `setRestartHint (self, RestartHint)`

* * *

## Detailed Description

该QSessionManager类提供了访问会话管理器。

在桌面环境中（其中Qt的GUI应用程序实时）的会话管理器会跟踪会话，这是一组运行的应用程序，每个都有一个特定的状态。应用程序的状态包含（最显着的）的应用程序所打开的文件和位置，它的窗口大小。

会话管理器是用来保存会话，例如，当机器关闭，并恢复会话，例如，当机器启动。我们建议您使用[QSettings](qsettings.html)保存应用程序的设置，例如，窗口位置，最近使用的文件等。当申请是由会话管理器重新启动，就可以恢复设置。

QSessionManager提供了应用程序和会话管理器之间的接口，使程序可以与会话管理工作。在Qt中，行动会话管理请求由两个虚函数来处理[QApplication.commitData](qapplication.html#commitData)（）和[QApplication.saveState](qapplication.html#saveState)（ ） 。两者都提供一个参考的会话管理器对象作为参数，以允许应用程序与会话管理器通信。会话管理器只能通过这些函数来访问。

无需用户交互是可能的_unless_该应用程序从会话管理器得到明确的许可。你可以通过调用请求许可[allowsInteraction](qsessionmanager.html#allowsInteraction)（ ）或者，如果它是真的急了，[allowsErrorInteraction](qsessionmanager.html#allowsErrorInteraction)（ ） 。 Qt不执行这一点，但会话管理器可以。

您可以尝试通过调用中止关机程序[cancel](qsessionmanager.html#cancel)（ ） 。默认commitData （ ）函数的作用这一点，如果某些顶层窗口拒绝了的closeEvent （ ） 。

对于提供的UNIX/X11复杂的会话管理器， QSessionManager提供了进一步的可能性，以微调应用程序的会话管理的行为：[setRestartCommand](qsessionmanager.html#setRestartCommand)（ ）[setDiscardCommand](qsessionmanager.html#setDiscardCommand)（ ）[setRestartHint](qsessionmanager.html#setRestartHint)（ ）[setProperty](qobject.html#setProperty)（ ）[requestPhase2](qsessionmanager.html#requestPhase2)（ ） 。进一步详情请参阅相应的功能说明。

* * *

## Type Documentation

```
QSessionManager.RestartHint
```

这个枚举类型定义下，这项应用程序要由会话管理器重新启动的情况。该电流值是：

| Constant | Value | Description |
| --- | --- | --- |
| `QSessionManager.RestartIfRunning` | `0` | 如果在会话关闭该应用程序仍在运行，它希望在下届会议上开始重新启动。 |
| `QSessionManager.RestartAnyway` | `1` | 应用程序希望在下届会议开始时启动，不管是什么。 （这对于刚刚启动后，然后退出运行实用程序非常有用。 ） |
| `QSessionManager.RestartImmediately` | `2` | 该应用程序要立即启动时，它没有运行。 |
| `QSessionManager.RestartNever` | `3` | 应用程序不希望被自动重新启动。 |

默认提示是`RestartIfRunning`。

* * *

## Method Documentation

```
bool QSessionManager.allowsErrorInteraction (self)
```

返回True如果错误的交互是允许的，否则返回False 。

这类似于[allowsInteraction](qsessionmanager.html#allowsInteraction)（ ） ，而且还使应用程序能够讲述发生的任何错误的用户。会话管理器可发出错误交互请求更高的优先级，这意味着它更可能是错误的相互作用是允许的。但是，你仍然不能保证会话管理器将允许交互。

**See also** [allowsInteraction](qsessionmanager.html#allowsInteraction)（ ）[release](qsessionmanager.html#release)（）和[cancel](qsessionmanager.html#cancel)（ ） 。

```
bool QSessionManager.allowsInteraction (self)
```

要求权限与用户交互的会话管理器。返回True如果互动是允许的，否则返回False 。

这背后的机制的基本原理是使人们有可能停机期间同步的用户交互。高级会话管理器可能会问，所有的应用程序同时提交他们的数据，从而导致更快的关机。

当交互完成后，我们强烈建议释放用户交互信号通过调用[release](qsessionmanager.html#release)（ ） 。这样一来，其他应用程序可能得到机会与用户进行交互，而你的应用程序仍然忙于保存数据。 （该信号量，当应用程序退出隐含释放。 ）

如果用户决定在互动阶段取消关机的过程中，你必须告诉会话管理器得知此事致电[cancel](qsessionmanager.html#cancel)（ ） 。

下面是一个应用程序是如何的一个例子[QApplication.commitData](qapplication.html#commitData)（ ）可能会实施：

```
 void MyApplication.commitData([QSessionManager](qsessionmanager.html)& manager)
 {
     if (manager.allowsInteraction()) {
         int ret = [QMessageBox](qmessagebox.html).warning(
                     mainWindow,
                     tr("My Application"),
                     tr("Save changes to document?"),
                     [QMessageBox](qmessagebox.html).Save | [QMessageBox](qmessagebox.html).Discard | [QMessageBox](qmessagebox.html).Cancel);

         switch (ret) {
         case [QMessageBox](qmessagebox.html).Save:
             manager.release();
             if (!saveDocument())
                 manager.cancel();
             break;
         case [QMessageBox](qmessagebox.html).Discard:
             break;
         case [QMessageBox](qmessagebox.html).Cancel:
         default:
             manager.cancel();
         }
     } else {
         // we did not get permission to interact, then
         // do something reasonable instead
     }
 }

```

如果在保存其数据的应用程序中发生了错误，你可能需要尝试[allowsErrorInteraction](qsessionmanager.html#allowsErrorInteraction)（ ）来代替。

**See also** [QApplication.commitData](qapplication.html#commitData)（ ）[release](qsessionmanager.html#release)（）和[cancel](qsessionmanager.html#cancel)（ ） 。

```
QSessionManager.cancel (self)
```

告诉会话管理器来取消关机过程。应用程序不应在没有先询问用户调用这个函数。

**See also** [allowsInteraction](qsessionmanager.html#allowsInteraction)（）和[allowsErrorInteraction](qsessionmanager.html#allowsErrorInteraction)（ ） 。

```
QStringList QSessionManager.discardCommand (self)
```

返回当前设置的丢弃命令。

遍历列表中，您可以使用[foreach](index.htm#foreach)伪关键字：

```
 foreach (const [QString](qstring.html) &command, mySession.discardCommand())
     do_something(command);

```

**See also** [setDiscardCommand](qsessionmanager.html#setDiscardCommand)（ ）[restartCommand](qsessionmanager.html#restartCommand)（）和[setRestartCommand](qsessionmanager.html#setRestartCommand)（ ） 。

```
bool QSessionManager.isPhase2 (self)
```

返回True如果会话管理器目前正在进行第二阶段管理阶段，否则返回False 。

**See also** [requestPhase2](qsessionmanager.html#requestPhase2)（ ） 。

```
QSessionManager.release (self)
```

交互阶段后释放会话管理器的交互信号。

**See also** [allowsInteraction](qsessionmanager.html#allowsInteraction)（）和[allowsErrorInteraction](qsessionmanager.html#allowsErrorInteraction)（ ） 。

```
QSessionManager.requestPhase2 (self)
```

请求第二次会议管理阶段应用程序。该应用程序然后可从立即返回[QApplication.commitData](qapplication.html#commitData)（）或[QApplication.saveState](qapplication.html#saveState)（ ）函数，它们将被再次调用一次大部分或所有其他应用程序已经完成了他们的会话管理。

这两个阶段是应用，如X11窗口管理器，需要存储有关其他应用程序的窗口的信息很有用，所以一定要等到这些申请都完成各自的会话管理任务。

**Note:**如果另一个应用程序已经请求了第二阶段它可能会调用之前，同时或应用程序的第二阶段之后。

**See also** [isPhase2](qsessionmanager.html#isPhase2)（ ） 。

```
QStringList QSessionManager.restartCommand (self)
```

返回当前设置的重新启动命令。

遍历列表中，您可以使用[foreach](index.htm#foreach)伪关键字：

```
 foreach (const [QString](qstring.html) &command, mySession.restartCommand())
     do_something(command);

```

**See also** [setRestartCommand](qsessionmanager.html#setRestartCommand)（）和[restartHint](qsessionmanager.html#restartHint)（ ） 。

```
RestartHint QSessionManager.restartHint (self)
```

[

返回应用程序的当前重启提示。默认值是`RestartIfRunning`。

](qsessionmanager.html#RestartHint-enum)

[**See also**](qsessionmanager.html#RestartHint-enum) [setRestartHint](qsessionmanager.html#setRestartHint)（ ） 。

```
QString QSessionManager.sessionId (self)
```

返回当前会话的标识符。

如果应用程序已恢复从以前的会话，这个标识符是因为它是在早期阶段相同。

**See also** [sessionKey](qsessionmanager.html#sessionKey)（）和[QApplication.sessionId](qapplication.html#sessionId)（ ） 。

```
QString QSessionManager.sessionKey (self)
```

返回在当前会话的会话密钥。

如果应用程序已恢复从以前的会话，这个键是一样的，当前一交易日结束它。

与commitData的每次调用（ ）或saveState和（ ）的会话密钥的变化。

**See also** [sessionId](qsessionmanager.html#sessionId)（）和[QApplication.sessionKey](qapplication.html#sessionKey)（ ） 。

```
QSessionManager.setDiscardCommand (self, QStringList)
```

设置丢弃命令给定的_list_。

**See also** [discardCommand](qsessionmanager.html#discardCommand)（）和[setRestartCommand](qsessionmanager.html#setRestartCommand)（ ） 。

```
QSessionManager.setManagerProperty (self, QString name, QString value)
```

低级别的写访问应用程序的识别和状态记录都保存在会话管理器。

所谓的财产_name_已经将其值设置为字符串列表_value_。

```
QSessionManager.setManagerProperty (self, QString name, QStringList value)
```

这是一个重载函数。

低级别的写访问应用程序的识别和状态记录保存在会话管理器。

所谓的财产_name_已经将其值设置为字符串_value_。

```
QSessionManager.setRestartCommand (self, QStringList)
```

如果会话管理器能够恢复会话将执行的_command_为了恢复应用程序。该命令默认为

```
 appname -session id

```

该`-session`选项是必需的，否则[QApplication](qapplication.html)无法分辨它是否已经恢复或者什么当前会话标识符。看[QApplication.isSessionRestored](qapplication.html#isSessionRestored)（）和[QApplication.sessionId](qapplication.html#sessionId)（ ）了解详情。

如果你的应用程序是非常简单的，它可能会存储在额外的命令行选项整个应用程序的状态。这通常是一个非常糟糕的主意，因为命令行往往局限于几百个字节。相反，使用[QSettings](qsettings.html)，临时文件，或用于此目的的数据库。通过用独特的标记数据[sessionId](qsessionmanager.html#sessionId)（ ） ，你就可以恢复应用程序在今后的会议。

**See also** [restartCommand](qsessionmanager.html#restartCommand)（ ）[setDiscardCommand](qsessionmanager.html#setDiscardCommand)（）和[setRestartHint](qsessionmanager.html#setRestartHint)（ ） 。

```
QSessionManager.setRestartHint (self, RestartHint)
```

设置应用程序的重启提示_hint_。在应用程序启动时，提示设置为`RestartIfRunning`。

**Note:**这些标志只是提示，一个会话管理器可能会或可能不会尊重他们。

我们建议设置重启的提示[QApplication.saveState](qapplication.html#saveState)（ ），因为一个应用程序的启动后不久，大多数会话管理器执行检查点。

**See also** [restartHint](qsessionmanager.html#restartHint)（ ） 。