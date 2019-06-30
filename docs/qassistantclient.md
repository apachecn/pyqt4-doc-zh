# QAssistantClient Class Reference

## [[QtAssistant](index.htm) module]

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QString path, QObject parent = None)`
*   `closeAssistant (self)`
*   `bool isOpen (self)`
*   `openAssistant (self)`
*   `setArguments (self, QStringList arguments)`
*   `showPage (self, QString page)`

### Qt Signals

*   `void assistantClosed ()`
*   `void assistantOpened ()`
*   `void error (const QString&)`

* * *

## Detailed Description

* * *

## Method Documentation

```
QAssistantClient.__init__ (self, QString path, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
QAssistantClient.closeAssistant (self)
```

这种方法也是一个Qt槽与C + +的签名`void closeAssistant()`。

```
bool QAssistantClient.isOpen (self)
```

```
QAssistantClient.openAssistant (self)
```

这种方法也是一个Qt槽与C + +的签名`void openAssistant()`。

```
QAssistantClient.setArguments (self, QStringList arguments)
```

```
QAssistantClient.showPage (self, QString page)
```

这种方法也是一个Qt槽与C + +的签名`void showPage(const QString&)`。

* * *

## Qt Signal Documentation

```
void assistantClosed ()
```

这是该信号的默认超载。

```
void assistantOpened ()
```

这是该信号的默认超载。

```
void error (const QString&)
```

这是该信号的默认超载。