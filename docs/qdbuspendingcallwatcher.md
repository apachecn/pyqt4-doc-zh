# QDBusPendingCallWatcher Class Reference

## [[QtDBus](index.htm) module]

该QDBusPendingCallWatcher类提供了一个便捷的途径等待异步回复[More...](#details)

继承[QObject](qobject.html)和[QDBusPendingCall](qdbuspendingcall.html)。

### Methods

*   `__init__ (self, QDBusPendingCall call, QObject parent = None)`
*   `bool isFinished (self)`
*   `waitForFinished (self)`

### Qt Signals

*   `void finished (QDBusPendingCallWatcher *)`

* * *

## Detailed Description

该QDBusPendingCallWatcher类提供了一个便捷的途径等待异步回复

该QDBusPendingCallWatcher提供[finished](qdbuspendingcallwatcher.html#finished)（ ）信号，当回复到达将要发射。

它通常用于像下面的例子：

```
     [QDBusPendingCall](qdbuspendingcall.html) async = iface->asyncCall("RemoteMethod", value1, value2);
     QDBusPendingCallWatcher *watcher = new QDBusPendingCallWatcher(async, this);

     [QObject](qobject.html).connect(watcher, SIGNAL(finished(QDBusPendingCallWatcher*)),
                      this, SLOT(callFinishedSlot(QDBusPendingCallWatcher*)));

```

注意，这是没有必要的，以保持原始[QDBusPendingCall](qdbuspendingcall.html)对象周围因为QDBusPendingCallWatcher从该类继承了。

通过上面的代码连接到插槽中可能出现类似下面的内容：

```
 void MyClass.callFinishedSlot(QDBusPendingCallWatcher *call)
 {
     [QDBusPendingReply](qdbuspendingreply.html)<[QString](qstring.html), [QByteArray](qbytearray.html)> reply = *call;
     if (reply.isError()) {
         showError();
     } else {
         [QString](qstring.html) text = reply.argumentAt<0>();
         [QByteArray](qbytearray.html) data = reply.argumentAt<1>();
         showReply(text, data);
     }
     call->deleteLater();
 }

```

使用注意事项[QDBusPendingReply](qdbuspendingreply.html)验证在回复的参数类型。如果回复并不恰好包含两个参数（一个字符串和一个[QByteArray](qbytearray.html)） ，[QDBusPendingReply.isError](qdbuspendingreply.html#isError)（ ）将返回True 。

* * *

## Method Documentation

```
QDBusPendingCallWatcher.__init__ (self, QDBusPendingCall call, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QDBusPendingCallWatcher](qdbuspendingcallwatcher.html)对象，以观察在异步等待受理回复_call_并设置该对象的父到_parent_。

```
bool QDBusPendingCallWatcher.isFinished (self)
```

返回True，如果待处理的呼叫完成处理和回复已经收到。

注意，这个函数只有改变状态，如果你调用[waitForFinished](qdbuspendingcallwatcher.html#waitForFinished)（ ），或者如果外部D-Bus的事件发生，这在一般如果返回到事件循环执行只发生。

**See also** [QDBusPendingReply.isFinished](qdbuspendingreply.html#isFinished)（ ） 。

```
QDBusPendingCallWatcher.waitForFinished (self)
```

挂起调用线程，直到收到回复和处理的执行。在此之后函数返回，[isFinished](qdbuspendingcallwatcher.html#isFinished)（ ）应该返回True，表示该回复的内容是准备进行处理。

**See also** [QDBusPendingReply.waitForFinished](qdbuspendingreply.html#waitForFinished)（ ） 。

* * *

## Qt Signal Documentation

```
void finished (QDBusPendingCallWatcher *)
```

这是该信号的默认超载。

这个信号被发射时挂起调用完成，其答复是可用的。该_self_参数是一个指向对象本身，通过为方便起见，这样的插槽可以访问属性，并确定答复的内容。