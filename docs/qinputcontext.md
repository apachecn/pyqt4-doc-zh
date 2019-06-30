# QInputContext Class Reference

## [[QtGui](index.htm) module]

该QInputContext类抽象的输入法相关的数据和作曲的状态。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum StandardFormat { PreeditFormat, SelectionFormat }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `list-of-QAction actions (self)`
*   `bool filterEvent (self, QEvent event)`
*   `QWidget focusWidget (self)`
*   `QFont font (self)`
*   `QString identifierName (self)`
*   `bool isComposing (self)`
*   `QString language (self)`
*   `mouseHandler (self, int x, QMouseEvent event)`
*   `reset (self)`
*   `sendEvent (self, QInputMethodEvent event)`
*   `setFocusWidget (self, QWidget w)`
*   `QTextFormat standardFormat (self, StandardFormat s)`
*   `update (self)`
*   `widgetDestroyed (self, QWidget w)`

* * *

## Detailed Description

该QInputContext类抽象的输入法相关的数据和作曲的状态。

输入法是负责输入无法通过简单的键盘映射输入复杂的文本。它可以转换输入事件（通常为关键事件）的序列转换成通过输入法的具体转换过程的文本字符串。该类进程的广泛，从简单的有限状态机的复杂文本翻译器，水池与文本编辑功能的文本的一整段进行语法和语义分析。

抽象如此不同的输入法，具体中间信息， Qt的提供QInputContext作为基类。这个概念是众所周知的输入法域“输入上下文” 。一个输入上下文的文本控件在响应需求创建的。它确保了一个输入上下文制备用于输入到文本构件之前的输入方法。

属于一个单一的输入法多输入上下文可以同时共存。假设多窗口的文本编辑器。窗口A和B的每个文本控件持有不同QInputContext实例，它包含不同的状态信息，如部分组成的文本。

### Groups of Functions

| Context | Functions |
| --- | --- |
| Receiving information | [x11FilterEvent](qinputcontext.html#x11FilterEvent)(), [filterEvent](qinputcontext.html#filterEvent)(), [mouseHandler](qinputcontext.html#mouseHandler)() |
| Sending back composed text | [sendEvent](qinputcontext.html#sendEvent)() |
| State change notification | [setFocusWidget](qinputcontext.html#setFocusWidget)(), [reset](qinputcontext.html#reset)() |
| Context information | [identifierName](qinputcontext.html#identifierName)(), [language](qinputcontext.html#language)(), [font](qinputcontext.html#font)(), [isComposing](qinputcontext.html#isComposing)() |

### Licensing Information

版权所有（C ）2003-2004 immodule Qt的项目。保留所有权利。

该文件是写在自己的许可以促进诺基亚公司和/或其附属公司（ - IES ） 。你可以使用这个文件在你的Qt许可。下面的描述是从原来的文件头复制。联系immodule-qt@freedesktop.org如果是这种许可的条件不明确给你。

* * *

## Type Documentation

```
QInputContext.StandardFormat
```

| Constant | Value | Description |
| --- | --- | --- |
| `QInputContext.PreeditFormat` | `0` | 预编辑文本。 |
| `QInputContext.SelectionFormat` | `1` | 选择文本。 |

**See also** [standardFormat](qinputcontext.html#standardFormat)（ ） 。

* * *

## Method Documentation

```
QInputContext.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个输入上下文与给定_parent_。

```
list-of-QAction QInputContext.actions (self)
```

这是为Qt 4的初步接口。

```
bool QInputContext.filterEvent (self, QEvent event)
```

此功能可以在子类中重新实现过滤输入事件。

返回True，如果_event_已被消耗。否则，未过滤的_event_将被转发到微件作为普通的方式。虽然输入事件已接受（）和忽略（ ）方法，让它不变。

_event_目前仅限于这些类型的事件：

*   CloseSoftwareInputPanel
*   KeyPress
*   KeyRelease
*   MouseButtonDblClick
*   MouseButtonPress
*   MouseButtonRelease
*   MouseMove
*   RequestSoftwareInputPanel

但有些输入法相关的事件，如[QWheelEvent](qwheelevent.html) or [QTabletEvent](qtabletevent.html)可能在将来增加。

滤波机会总是提供给输入上下文尽快。它必须发生的任何其他关键事件消费者如eventfilters和加速器之前因为一些输入法需要相当不同的按键组合和顺序。它常与加速器等冲突，所以我们必须给输入上下文滤波机会首先要保证所有的输入法正常工作，而不管应用程序设计。

普通输入法需要离散关键事件才能正常工作，所以Qt的键压缩始终是任何输入上下文停用。

**See also** [QKeyEvent](qkeyevent.html)和[x11FilterEvent](qinputcontext.html#x11FilterEvent)（ ） 。

```
QWidget QInputContext.focusWidget (self)
```

[

返回具有输入焦点此输入上下文的部件。

返回值可能不同于holderWidget （ ）如果输入上下文几个文本组件之间共享。

**Warning:**为了保证平台的独立性，并支持小部件的灵活配置，普通的输入方法不应该直接调用此函数。

](qwidget.html)

[**See also**](qwidget.html) [setFocusWidget](qinputcontext.html#setFocusWidget)（ ） 。

```
QFont QInputContext.font (self)
```

[

返回当前输入小部件的字体

```
QString QInputContext.identifierName (self)
```

这种方法是抽象的，应在任何子类中重新实现。

该功能必须在任何子类中实现，返回输入法的识别名称。

](qfont.html)

[返回值是确定并指定输入法的输入法切换机制等名称。该名称必须一致](qfont.html)[QInputContextPlugin.keys](index.htm#keys)（ ） 。该名称必须只包含ASCII字符。

有两个不同的名字，在该输入法域不同的责任。这个函数返回其中之一。另一名被称为是代表名称为终端用户出现在菜单等等“显示名称” 。

**See also** [QInputContextPlugin.keys](index.htm#keys)（）和[QInputContextPlugin.displayName](index.htm#displayName)（ ） 。

```
bool QInputContext.isComposing (self)
```

这种方法是抽象的，应在任何子类中重新实现。

该函数表示InputMethodStart事件是否已被发送到当前焦点控件。它是确保输入上下文可以发送InputMethodCompose或InputMethodEnd安全事件，如果这个函数返回True 。

该状态会自动被通过跟踪[sendEvent](qinputcontext.html#sendEvent)（ ） 。

**See also** [sendEvent](qinputcontext.html#sendEvent)（ ） 。

```
QString QInputContext.language (self)
```

这种方法是抽象的，应在任何子类中重新实现。

该功能必须在任何子类中实现，返回的输入上下文的语言代码（如“ zh_CN的” ， “ ZH_TW ” ， “了zh_HK ” ， “ JA ” ， “KO” ， ... ） 。如果输入的情况下能处理多种语言，返回当前使用的之一。该名称必须与QInputContextPlugin.language （ ）是一致的。

这些信息将被用于语言标记功能[QInputMethodEvent](qinputmethodevent.html)。这是需要正确区分统一汉字。它使正确的字体和字符代码处理。假设CJK- awared多种语言的网页浏览器（自动修改字体中日韩混合文本）和XML编辑器（即自动插入郎ATTR ） 。

```
QInputContext.mouseHandler (self, int x, QMouseEvent event)
```

此功能可重新实现在子类中处理鼠标按下，释放，双击，然后将预编辑文本中的事件。您可以使用该功能来实现鼠标为导向的用户界面，例如文本或选择弹出菜单中选择候选人。

该_x_参数是所发送的InputMethodCompose事件串中的偏移量。的改变边界_x_确保为预编辑字符串的字符边界准确。

该_event_参数是被送到编辑器插件的事件。事件类型是[QEvent.MouseButtonPress](qevent.html#Type-enum)，[QEvent.MouseButtonRelease](qevent.html#Type-enum)，[QEvent.MouseButtonDblClick](qevent.html#Type-enum) or [QEvent.MouseMove](qevent.html#Type-enum)。本次活动的按钮和状态显示已执行的一种操作。

```
QInputContext.reset (self)
```

这种方法是抽象的，应在任何子类中重新实现。

此功能可重新实现在子类中重新设置输入法的状态。

此功能称为由几个部件复位输入状态。例如，一个文本组件插入文字，使小工具准备好接受一个文本之前调用这个函数。

默认的实现是足够简单的输入法。你可以重载这个函数来在复杂的输入法复位外部的输入法引擎。在该情况下，调用QInputContext.reset （ ），以确保正确的端接输入的。

在复位（ ）的重新实现，您不能发送任何[QInputMethodEvent](qinputmethodevent.html)含预编辑文本。您只能提交字符串和属性，否则，你的风险断裂输入状态的一致性。

```
QInputContext.sendEvent (self, QInputMethodEvent event)
```

通过发送指定的输入法事件_event_以目前的重点部件。的实现[QInputContext](qinputcontext.html)应该调用此方法来发送生成的输入法事件，而不是[QApplication.sendEvent](qcoreapplication.html#sendEvent)（ ） ，因为事件可能要被分派到一些平台上的不同应用程序。

一些复杂的输入法路线的处理到几个子上下文（例如，使语言切换） 。考虑到这一点，[QInputContext](qinputcontext.html)将检查如果父对象是[QInputContext](qinputcontext.html)。如果是的话，它会调用父母的SendEvent （ ）实现，而不是直接发送该事件。

**See also** [QInputMethodEvent](qinputmethodevent.html)。

```
QInputContext.setFocusWidget (self, QWidget w)
```

设置_widget_具有输入焦点此输入上下文。

**Warning:**普通的输入法不能直接调用此函数。

**See also** [focusWidget](qinputcontext.html#focusWidget)（ ） 。

```
QTextFormat QInputContext.standardFormat (self, StandardFormat s)
```

[](qtextformat.html)

[返回](qtextformat.html)[QTextFormat](qtextformat.html)对象，指定组件的格式_s_。

```
QInputContext.update (self)
```

这个虚函数被调用时，在焦点部件的状态发生了变化。[QInputContext](qinputcontext.html)然后可以使用[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ）来查询widget的新状态。

```
QInputContext.widgetDestroyed (self, QWidget w)
```

指定当该虚拟函数调用_widget_被破坏。该_widget_是安装在此输入上下文上的一个小部件。