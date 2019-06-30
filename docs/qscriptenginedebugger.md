# QScriptEngineDebugger Class Reference

## [[QtScriptTools](index.htm) module]

该QScriptEngineDebugger类提供了一个[QScriptEngine](qscriptengine.html)调试器。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum DebuggerAction { InterruptAction, ContinueAction, StepIntoAction, StepOverAction, ..., GoToLineAction }`
*   `enum DebuggerState { RunningState, SuspendedState }`
*   `enum DebuggerWidget { ConsoleWidget, StackWidget, ScriptsWidget, LocalsWidget, ..., ErrorLogWidget }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QAction action (self, DebuggerAction action)`
*   `attachTo (self, QScriptEngine engine)`
*   `bool autoShowStandardWindow (self)`
*   `QMenu createStandardMenu (self, QWidget parent = None)`
*   `QToolBar createStandardToolBar (self, QWidget parent = None)`
*   `detach (self)`
*   `setAutoShowStandardWindow (self, bool autoShow)`
*   `QMainWindow standardWindow (self)`
*   `DebuggerState state (self)`
*   `QWidget widget (self, DebuggerWidget widget)`

### Qt Signals

*   `void evaluationResumed ()`
*   `void evaluationSuspended ()`

* * *

## Detailed Description

该QScriptEngineDebugger类提供了一个[QScriptEngine](qscriptengine.html)调试器。

该QScriptEngineDebugger类提供了一个可以嵌入到使用Qt脚本Qt应用程序调试器。调试器允许应用程序用户能够检查脚本环境的状态和控制脚本的执行。

为了将调试器附加到一个脚本引擎，调用[attachTo](qscriptenginedebugger.html#attachTo)（）函数。

```
     [QScriptEngine](qscriptengine.html) engine;
     QScriptEngineDebugger debugger;
     debugger.attachTo(&engine);

```

一旦调试器已附加到一个脚本引擎，你可以继续执行脚本像往常一样，例如：通过调用[QScriptEngine.evaluate](qscriptengine.html#evaluate)（ ） 。当一个未捕获的异常发生时，调试器将被触发，或当`debugger`语句在脚本中遇到的问题。它也可以通过触发中断脚本评估在任意时间[InterruptAction](qscriptenginedebugger.html#DebuggerAction-enum)。例如，当脚本评估开始启动调试器，你触发动作开始之前，你[evaluate()](qscriptengine.html#evaluate)该脚本。

```
      debugger->action(QScriptEngineDebugger.InterruptAction)->trigger();
      engine->evaluate(contents, fileName);

```

默认情况下，[standard debugger window](qscriptenginedebugger.html#standardWindow)如图评估时暂停。这可以通过调用被改变[setAutoShowStandardWindow](qscriptenginedebugger.html#setAutoShowStandardWindow)（）函数。

调试器定义了一组[actions](qscriptenginedebugger.html#DebuggerAction-enum)可用，例如停止执行或打印变量的内容。它还提供了一组小部件（组件）的显示可以从调试器和触发器要求的操作的信息。可用的操作是由所识别的[DebuggerAction](qscriptenginedebugger.html#DebuggerAction-enum)枚举和小部件是由所识别的[DebuggerWidget](qscriptenginedebugger.html#DebuggerWidget-enum)枚举。

访问各个调试窗口小部件是由提供[widget](qscriptenginedebugger.html#widget)（）函数。这使得它可以安排在一个自定义的方式在窗口小部件。类似地，[action](qscriptenginedebugger.html#action)（ ）函数提供了访问各种调试操作。

该[createStandardToolBar](qscriptenginedebugger.html#createStandardToolBar)（ ）函数创建一个标准工具栏，以及[createStandardMenu](qscriptenginedebugger.html#createStandardMenu)（ ）函数创建一个标准的菜单，如果要创建一个自定义的调试器配置这些功能可能是有用的。

该[evaluationSuspended](qscriptenginedebugger.html#evaluationSuspended)（）信号被发射时，调试器已经暂停脚本的评价和输入的交互模式下，即，在它接受来自用户的输入的方式。该[evaluationResumed](qscriptenginedebugger.html#evaluationResumed)当脚本执行恢复（ ）信号被发射，即当执行控制权还回给脚本引擎。该[state](qscriptenginedebugger.html#state)（ ）函数返回调试器的当前状态。

当调用[QScriptEngine.evaluate](qscriptengine.html#evaluate)（ ），它通过一个描述性的脚本名称（文件名）作为第二个参数是非常有用的，因为这是将被调试器中显示的名称[ScriptsWidget](qscriptenginedebugger.html#DebuggerWidget-enum)，如果一个名字不获通过，该脚本将被标记为“匿名” 。

当评估被暂停，调试器也将暂停脚本的事件循环。在下面的片段中，调用[QScriptEngine.evaluate](qscriptengine.html#evaluate)（ ）使得调试器被触发，该函数调用不会返回，直到用户完成与调试器进行交互。

```
     engine.evaluate("debugger");

```

当Qt的脚本调试器运行时，C + +应用程序本身并没有“冻结” 。这意味着，有可能是多个脚本进行评估，尽管调试器已暂停的评价**current**脚本的评价。例如，一个C + +计时器可能引发导致被调用的脚本函数，或者用户可能会在主应用程序用户界面的点击（ ）信号连接到一个脚本功能，点击一个按钮。这种嵌套的评价是允许的。调试器将进入交互模式为新的脚本，如果有异常抛出，或到达断点。需要注意的是，当遇到它不会停止`debugger`语句。

嵌套的评价需要一些思考决定调试器是如何呈现给用户时，例如，一个模态对话框是否适合，还是主应用程序用户界面的某些部分应在调试器运行时被禁用。

调试的内[paintEvent](qwidget.html#paintEvent)（ ）目前不支持。如果你需要调试绘画相关的脚本代码，该代码应在C + +中的paintEvent （外部评价） ，如通过绘制一个图像，像Context2D和蚱[QtScript](index.htm)例子做。这将使得代码安全进行调试。

调试器添加了一些特殊性能的脚本引擎：`__FILE__`保存在其中的当前评估产生的脚本的名称，并`__LINE__`保持当前的行号。这些做的print（）风格的调试（该消息出现在调试器的调试输出窗口小部件）时是有用的。

该[Qt Script Debugger Manual](index.htm)介绍如何使用调试器。该[Context2D example](index.htm)显示了如何将调试器集成在应用程序中。

* * *

## Type Documentation

```
QScriptEngineDebugger.DebuggerAction
```

这个枚举变量指定动作的[action](qscriptenginedebugger.html#action)（ ）函数应该找回。检索到的动作可以被连接到任何槽，并连接到任何插件。请参阅[Qt Script Debugger Manual](index.htm)的[Console Command Reference](index.htm#console-command-reference)这些动作的详细描述。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptEngineDebugger.InterruptAction` | `0` | 只要下一个脚本语句达到暂停脚本的执行。 |
| `QScriptEngineDebugger.ContinueAction` | `1` | 给人的执行控制权交还给脚本引擎。 |
| `QScriptEngineDebugger.StepIntoAction` | `2` | 执行步骤操作。 |
| `QScriptEngineDebugger.StepOverAction` | `3` | 进行下一个动作。 |
| `QScriptEngineDebugger.StepOutAction` | `4` | 执行脚本，直到当前函数返回。 |
| `QScriptEngineDebugger.RunToCursorAction` | `5` | 继续执行到所选择的行（其中包含光标）在[CodeWidget](qscriptenginedebugger.html#DebuggerWidget-enum)。 |
| `QScriptEngineDebugger.RunToNewScriptAction` | `6` | 将控制返回给脚本引擎，直到一个新的脚本被执行。 |
| `QScriptEngineDebugger.ToggleBreakpointAction` | `7` | 切换断点在选定的线路[CodeWidget](qscriptenginedebugger.html#DebuggerWidget-enum)。 |
| `QScriptEngineDebugger.ClearDebugOutputAction` | `8` | 清除的内容[DebugOutputWidget](qscriptenginedebugger.html#DebuggerWidget-enum)。 |
| `QScriptEngineDebugger.ClearErrorLogAction` | `9` | 清除的内容[ErrorLogWidget](qscriptenginedebugger.html#DebuggerWidget-enum)。 |
| `QScriptEngineDebugger.ClearConsoleAction` | `10` | 清除的内容[ConsoleWidget](qscriptenginedebugger.html#DebuggerWidget-enum)。 |
| `QScriptEngineDebugger.FindInScriptAction` | `11` | 显示[CodeFinderWidget](qscriptenginedebugger.html#DebuggerWidget-enum)。 |
| `QScriptEngineDebugger.FindNextInScriptAction` | `12` | 查找下一个出现在[CodeWidget](qscriptenginedebugger.html#DebuggerWidget-enum)。 |
| `QScriptEngineDebugger.FindPreviousInScriptAction` | `13` | 查找以前发生在[CodeWidget](qscriptenginedebugger.html#DebuggerWidget-enum)。 |
| `QScriptEngineDebugger.GoToLineAction` | `14` | 显示“转至行”对话框。 |

```
QScriptEngineDebugger.DebuggerState
```

这个枚举指定调试器的当前状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptEngineDebugger.RunningState` | `0` | 在调试器运行。 （脚本的评价是允许的。 ） |
| `QScriptEngineDebugger.SuspendedState` | `1` | 该调试器已暂停脚本的评价。 |

这个枚举被引入或修改的Qt 4.6 。

```
QScriptEngineDebugger.DebuggerWidget
```

这个枚举变量决定了小部件的[widget](qscriptenginedebugger.html#widget)（ ）函数应该找回。我们在详细对待这些小部件[Qt Script Debugger Manual](index.htm)。

| Constant | Value | Description |
| --- | --- | --- |
| `QScriptEngineDebugger.ConsoleWidget` | `0` | 提供了一个命令行界面的调试器。 |
| `QScriptEngineDebugger.StackWidget` | `1` | 显示脚本的执行状态的回溯。 |
| `QScriptEngineDebugger.ScriptsWidget` | `2` | 显示当前加载的脚本列表。 |
| `QScriptEngineDebugger.LocalsWidget` | `3` | 显示当前堆栈帧的局部变量。 |
| `QScriptEngineDebugger.CodeWidget` | `4` | 显示当前脚本的代码。 |
| `QScriptEngineDebugger.CodeFinderWidget` | `5` | 提供可搜索在CodeWidget所示的脚本文本的小工具。 |
| `QScriptEngineDebugger.BreakpointsWidget` | `6` | 显示已设置的断点。 |
| `QScriptEngineDebugger.DebugOutputWidget` | `7` | 包含从输出`print()`脚本函数。 |
| `QScriptEngineDebugger.ErrorLogWidget` | `8` | 显示已生成的错误消息。 |

* * *

## Method Documentation

```
QScriptEngineDebugger.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QScriptEngineDebugger](qscriptenginedebugger.html)与给定对象_parent_。

要附加[QScriptEngine](qscriptengine.html)到调试器，使用[attachTo](qscriptenginedebugger.html#attachTo)（）函数。

```
QAction QScriptEngineDebugger.action (self, DebuggerAction action)
```

[](qaction.html)

[返回一个指向指定的_action_。可用的操作是由给定的](qaction.html)[DebuggerAction](qscriptenginedebugger.html#DebuggerAction-enum)枚举。

有了这个功能，你可以添加动作，将自己的小部件，工具栏和菜单。这也是方便的，如果你，例如，希望香料的东西用自己的常规图标。下面的代码示例演示如何将动作添加到[QToolBar](qtoolbar.html)。

```
     [QAction](qaction.html) *continueAction = debugger->action([QScriptEngineDebugger](qscriptenginedebugger.html).ContinueAction);
     [QAction](qaction.html) *stepOverAction = debugger->action([QScriptEngineDebugger](qscriptenginedebugger.html).StepOverAction);
     [QAction](qaction.html) *stepIntoAction = debugger->action([QScriptEngineDebugger](qscriptenginedebugger.html).StepIntoAction);

     [QToolBar](qtoolbar.html) *toolBar = new [QToolBar](qtoolbar.html);
     toolBar->addAction(continueAction);

```

需要注意的是[QScriptEngineDebugger](qscriptenginedebugger.html)已经添加了行动，其[standard widgets](qscriptenginedebugger.html#DebuggerWidget-enum)和[standard window](qscriptenginedebugger.html#standardWindow)。

**See also** [widget](qscriptenginedebugger.html#widget)（ ）[createStandardMenu](qscriptenginedebugger.html#createStandardMenu)（ ）[createStandardToolBar](qscriptenginedebugger.html#createStandardToolBar)（）和[standardWindow](qscriptenginedebugger.html#standardWindow)（ ） 。

```
QScriptEngineDebugger.attachTo (self, QScriptEngine engine)
```

附加到给定的_engine_。

调试器将安装一个自定义代理（使用[QScriptEngine.setAgent](qscriptengine.html#setAgent)（））来监测发动机。虽然附加调试器，你不应该改变的代理，但是，如果你必须执行额外的监控，你必须设置一个代理程序，它会将所有事件到调试器的代理。

**See also** [detach](qscriptenginedebugger.html#detach)（ ） 。

```
bool QScriptEngineDebugger.autoShowStandardWindow (self)
```

返回是否评估时被挂起的标准调试器窗口会自动显示。

默认值为True 。

**See also** [setAutoShowStandardWindow](qscriptenginedebugger.html#setAutoShowStandardWindow)（ ） 。

```
QMenu QScriptEngineDebugger.createStandardMenu (self, QWidget parent = None)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建具有给定一个标准的调试器菜单_parent_。返回新的菜单对象。

](qmenu.html)

[**See also**](qmenu.html) [createStandardToolBar](qscriptenginedebugger.html#createStandardToolBar)（ ） 。

```
QToolBar QScriptEngineDebugger.createStandardToolBar (self, QWidget parent = None)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

建立一个标准的调试器工具栏与给定_parent_。返回新的工具栏对象。

](qtoolbar.html)

[**See also**](qtoolbar.html) [createStandardMenu](qscriptenginedebugger.html#createStandardMenu)（ ） 。

```
QScriptEngineDebugger.detach (self)
```

分离从目前的脚本引擎，如果有的话。

**See also** [attachTo](qscriptenginedebugger.html#attachTo)（ ） 。

```
QScriptEngineDebugger.setAutoShowStandardWindow (self, bool autoShow)
```

设置是否在评估被暂停的标准调试器窗口会自动显示。如果_autoShow_为True，则窗口会自动显示，否则不会。

**See also** [autoShowStandardWindow](qscriptenginedebugger.html#autoShowStandardWindow)（ ） 。

```
QMainWindow QScriptEngineDebugger.standardWindow (self)
```

[

返回主窗口与调试器的组件的标准配置。

](qmainwindow.html)

[**See also**](qmainwindow.html) [createStandardMenu](qscriptenginedebugger.html#createStandardMenu)（）和[createStandardToolBar](qscriptenginedebugger.html#createStandardToolBar)（ ） 。

```
DebuggerState QScriptEngineDebugger.state (self)
```

[

返回调试器的当前状态。

此功能被引入Qt的4.6 。

](qscriptenginedebugger.html#DebuggerState-enum)

[**See also**](qscriptenginedebugger.html#DebuggerState-enum) [evaluationResumed](qscriptenginedebugger.html#evaluationResumed)（）和[evaluationSuspended](qscriptenginedebugger.html#evaluationSuspended)（ ） 。

```
QWidget QScriptEngineDebugger.widget (self, DebuggerWidget widget)
```

[](qwidget.html)

[返回一个指向指定标准的实例_widget_。可用的窗口小部件是由定义](qwidget.html)[DebuggerWidget](qscriptenginedebugger.html#DebuggerWidget-enum)枚举。

通过返回一个包含所有小部件的主窗口[standardWindow](qscriptenginedebugger.html#standardWindow)（ ） 。如果你不想使用这个窗口中，您可以获取各个部件使用此功能。例如，下面的代码示例显示了如何设置包含布局[code window](qscriptenginedebugger.html#DebuggerWidget-enum)和[stack widget](qscriptenginedebugger.html#DebuggerWidget-enum)。

```
     [QWidget](qwidget.html) *codeWindow = debugger->widget([QScriptEngineDebugger](qscriptenginedebugger.html).CodeWidget);
     [QWidget](qwidget.html) *stackWidget = debugger->widget([QScriptEngineDebugger](qscriptenginedebugger.html).StackWidget);

     [QLayout](qlayout.html) *layout = new [QHBoxLayout](qhboxlayout.html);
     layout->addWidget(codeWindow);
     layout->addWidget(stackWidget);

```

请注意，您需要设置[setAutoShowStandardWindow](qscriptenginedebugger.html#setAutoShowStandardWindow)（ ）为False ;若否，标准的窗口将不分显示。

**See also** [action](qscriptenginedebugger.html#action)（ ）[standardWindow](qscriptenginedebugger.html#standardWindow)（）和[setAutoShowStandardWindow](qscriptenginedebugger.html#setAutoShowStandardWindow)（ ） 。

* * *

## Qt Signal Documentation

```
void evaluationResumed ()
```

这是该信号的默认超载。

当调试器已经恢复脚本的评价（如用户给予“继续”命令），这个信号被发射。

**See also** [evaluationSuspended](qscriptenginedebugger.html#evaluationSuspended)（ ） 。

```
void evaluationSuspended ()
```

这是该信号的默认超载。

这个信号被发射时，调试器已因任何原因而暂停脚本执行（例如由于未捕获到脚本异常，或由于断点被触发） 。

**See also** [evaluationResumed](qscriptenginedebugger.html#evaluationResumed)（ ） 。