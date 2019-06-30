# QDBusInterface Class Reference

## [[QtDBus](index.htm) module]

该QDBusInterface类是对远程对象接口的代理。[More...](#details)

继承[QDBusAbstractInterface](qdbusabstractinterface.html)。

### Methods

*   `__init__ (self, QString service, QString path, QString interface = QString(), QDBusConnection connection = QDBusConnection.sessionBus(), QObject parent = None)`

* * *

## Detailed Description

该QDBusInterface类是对远程对象接口的代理。

QDBusInterface是用来放置调用远程对象，连接到远程对象导出的信号，并获取/设置远程属性值的通用方法类。这个类是动态访问远程对象很有用：即当你没有一个生成代码，表示该远程接口。

呼叫通常放置使用[call](qdbusabstractinterface.html#call)（ ）函数，它构造消息，发送过来的大巴，等待答复和解码的答复。信号是通过使用正常连接到[QObject.connect](qobject.html#connect)（）函数。最后，属性是使用访问[QObject.property](qobject.html#property)（）和[QObject.setProperty](qobject.html#setProperty)（）函数。

下面的代码片断演示了如何执行数学运算`"2 + 2"`在所谓的远程应用程序`com.example.Calculator`通过会话总线，访问。

```
 QDBusInterface remoteApp( "com.example.Calculator", "/Calculator/Operations",
                           "org.mathematics.RPNCalculator" );
 remoteApp.call( "PushOperand", 2 );
 remoteApp.call( "PushOperand", 2 );
 remoteApp.call( "ExecuteOperation", "+" );
 [QDBusReply](qdbusreply.html)<int> reply = remoteApp.call( "PopOperand" );

 if ( reply.isValid() )
     printf( "%d", reply.value() );          // prints 4

```

* * *

## Method Documentation

```
QDBusInterface.__init__ (self, QString service, QString path, QString interface = QString(), QDBusConnection connection = QDBusConnection.sessionBus(), QObject parent = None)
```

创建一个动态[QDBusInterface](qdbusinterface.html)与接口相关联的对象_interface_在对路径物件_path_对服务_service_，使用给定的_connection_。如果_interface_是一个空字符串，创建的对象将引用该对象中找到的所有接口的合并。

_parent_传递给基类构造函数。

如果该远程服务_service_不存在，或者如果发生错误试图获取远程接口的描述_interface_，创建的对象将是无效的（见[isValid](qdbusabstractinterface.html#isValid)（））。