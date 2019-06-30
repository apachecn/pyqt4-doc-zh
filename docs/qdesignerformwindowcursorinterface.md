# QDesignerFormWindowCursorInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerFormWindowCursorInterface类允许您查询和修改表单窗口部件的选择，而且除了修改窗体的所有控件的属性。[More...](#details)

### Types

*   `enum MoveMode { MoveAnchor, KeepAnchor }`
*   `enum MoveOperation { NoMove, Start, End, Next, ..., Down }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDesignerFormWindowCursorInterface)`
*   `QWidget current (self)`
*   `QDesignerFormWindowInterface formWindow (self)`
*   `bool hasSelection (self)`
*   `bool isWidgetSelected (self, QWidget widget)`
*   `bool movePosition (self, MoveOperation op, MoveMode mode = QDesignerFormWindowCursorInterface.MoveAnchor)`
*   `int position (self)`
*   `resetWidgetProperty (self, QWidget widget, QString name)`
*   `QWidget selectedWidget (self, int index)`
*   `int selectedWidgetCount (self)`
*   `setPosition (self, int pos, MoveMode mode = QDesignerFormWindowCursorInterface.MoveAnchor)`
*   `setProperty (self, QString name, QVariant value)`
*   `setWidgetProperty (self, QWidget widget, QString name, QVariant value)`
*   `QWidget widget (self, int index)`
*   `int widgetCount (self)`

* * *

## Detailed Description

该QDesignerFormWindowCursorInterface类允许您查询和修改表单窗口部件的选择，而且除了修改窗体的所有控件的属性。

QDesignerFormWindowCursorInterface是一个方便的类，它提供了一个接口，相关表单窗口的文本光标，它提供的功能的集合，使您能够查询一个给定的表单窗口的选择和改变选择的重点，根据定义的模式（[MoveMode](qdesignerformwindowcursorinterface.html#MoveMode-enum)）和运动（[MoveOperation](qdesignerformwindowcursorinterface.html#MoveOperation-enum)） 。您也可以使用该接口来查询窗体的控件和改变它们的属性。

该接口不打算直接实例化，而是提供访问的选择和窗口小部件_Qt Designer_目前的形式窗口。[QDesignerFormWindowInterface](qdesignerformwindowinterface.html)始终提供一个相关的游标接口。可以使用静态的要检索的表格窗口对于给定窗口小部件[QDesignerFormWindowInterface.findFormWindow](qdesignerformwindowinterface.html#findFormWindow)（）函数。例如：

```
     [QDesignerFormWindowInterface](qdesignerformwindowinterface.html) *formWindow = 0;
     formWindow = [QDesignerFormWindowInterface](qdesignerformwindowinterface.html).findFormWindow(myWidget);

     formWindow->cursor()->setProperty(myWidget, myProperty, newValue);

```

你可以检索任何_Qt Designer_通过目前的形式窗口_Qt Designer_的[form window manager](qdesignerformwindowmanagerinterface.html)。

一旦你有一个表单窗口的光标的界面，你可以检查表格窗口具有在所有使用选择的[hasSelection](qdesignerformwindowcursorinterface.html#hasSelection)（）函数。您可以查询窗体窗口，其总[widgetCount](qdesignerformwindowcursorinterface.html#widgetCount)（）和[selectedWidgetCount](qdesignerformwindowcursorinterface.html#selectedWidgetCount)（ ） 。您可以使用检索当前选中的控件（或者部件）的[current](qdesignerformwindowcursorinterface.html#current)（）或[selectedWidget](qdesignerformwindowcursorinterface.html#selectedWidget)（）函数。

您可以使用检索任何形式的窗口小部件的[widget](qdesignerformwindowcursorinterface.html#widget)（ ）函数，并检查是否使用被选择的插件的[isWidgetSelected](qdesignerformwindowcursorinterface.html#isWidgetSelected)（）函数。您可以使用[setProperty](qdesignerformwindowcursorinterface.html#setProperty)（ ）函数来设置选定控件的属性，以及[setWidgetProperty](qdesignerformwindowcursorinterface.html#setWidgetProperty)（）或[resetWidgetProperty](qdesignerformwindowcursorinterface.html#resetWidgetProperty)（）函数来修改任何给定窗口小部件的属性。

最后，您可以通过更改更改选择文本光标的[position](qdesignerformwindowcursorinterface.html#position)（）使用[setPosition](qdesignerformwindowcursorinterface.html#setPosition)（）和[movePosition](qdesignerformwindowcursorinterface.html#movePosition)（）函数。

* * *

## Type Documentation

```
QDesignerFormWindowCursorInterface.MoveMode
```

这个枚举变量描述了当文本光标移动正在使用的不同模式。

| Constant | Value | Description |
| --- | --- | --- |
| `QDesignerFormWindowCursorInterface.MoveAnchor` | `0` | 锚光标移动到新的位置。 |
| `QDesignerFormWindowCursorInterface.KeepAnchor` | `1` | 锚保持在光标的老位置。 |

```
QDesignerFormWindowCursorInterface.MoveOperation
```

这个枚举描述文本光标的操作，可以发生在一个窗体窗口的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QDesignerFormWindowCursorInterface.NoMove` | `0` | 光标不移动。 |
| `QDesignerFormWindowCursorInterface.Start` | `1` | 将光标移动到焦点链的开始。 |
| `QDesignerFormWindowCursorInterface.End` | `2` | 将光标移动到焦点链的末端。 |
| `QDesignerFormWindowCursorInterface.Next` | `3` | 将光标移动到焦点链中的下一个控件。 |
| `QDesignerFormWindowCursorInterface.Prev` | `4` | 将光标移动到前面的小部件中的焦点链。 |
| `QDesignerFormWindowCursorInterface.Left` | `5` | 光标移动到左侧。 |
| `QDesignerFormWindowCursorInterface.Right` | `6` | 光标移动到右侧。 |
| `QDesignerFormWindowCursorInterface.Up` | `7` | 光标向上移动。 |
| `QDesignerFormWindowCursorInterface.Down` | `8` | 光标向下移动。 |

* * *

## Method Documentation

```
QDesignerFormWindowCursorInterface.__init__ (self)
```

```
QDesignerFormWindowCursorInterface.__init__ (self, QDesignerFormWindowCursorInterface)
```

```
QWidget QDesignerFormWindowCursorInterface.current (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回在窗体窗口当前选定的控件。

](qwidget.html)

[**See also**](qwidget.html) [selectedWidget](qdesignerformwindowcursorinterface.html#selectedWidget)（ ） 。

```
QDesignerFormWindowInterface QDesignerFormWindowCursorInterface.formWindow (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回与此游标接口关联的表格窗口界面。

```
bool QDesignerFormWindowCursorInterface.hasSelection (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果表单窗口包含一个选择，否则返回False 。

```
bool QDesignerFormWindowCursorInterface.isWidgetSelected (self, QWidget widget)
```

返回True如果指定的_widget_被选中，否则返回False 。

```
bool QDesignerFormWindowCursorInterface.movePosition (self, MoveOperation op, MoveMode mode = QDesignerFormWindowCursorInterface.MoveAnchor)
```

这种方法是抽象的，应在任何子类中重新实现。

执行给定的_operation_在使用指定的光标_mode_，并返回True，如果它成功完成，否则返回False 。

](qdesignerformwindowinterface.html)

[**See also**](qdesignerformwindowinterface.html) [position](qdesignerformwindowcursorinterface.html#position)（）和[setPosition](qdesignerformwindowcursorinterface.html#setPosition)（ ） 。

```
int QDesignerFormWindowCursorInterface.position (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回光标位置。

**See also** [setPosition](qdesignerformwindowcursorinterface.html#setPosition)（）和[movePosition](qdesignerformwindowcursorinterface.html#movePosition)（ ） 。

```
QDesignerFormWindowCursorInterface.resetWidgetProperty (self, QWidget widget, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

重置属性与给定的_name_为指定的_widget_它的默认值。

**See also** [setProperty](qdesignerformwindowcursorinterface.html#setProperty)（）和[setWidgetProperty](qdesignerformwindowcursorinterface.html#setWidgetProperty)（ ） 。

```
QWidget QDesignerFormWindowCursorInterface.selectedWidget (self, int index)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回该插件与给定的_index_在所选窗口小部件的列表。

](qwidget.html)

[**See also**](qwidget.html) [current](qdesignerformwindowcursorinterface.html#current)（）和[widget](qdesignerformwindowcursorinterface.html#widget)（ ） 。

```
int QDesignerFormWindowCursorInterface.selectedWidgetCount (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回选定的部件在窗体窗口的数量。

**See also** [widgetCount](qdesignerformwindowcursorinterface.html#widgetCount)（ ） 。

```
QDesignerFormWindowCursorInterface.setPosition (self, int pos, MoveMode mode = QDesignerFormWindowCursorInterface.MoveAnchor)
```

这种方法是抽象的，应在任何子类中重新实现。

设置光标的位置，以给定的_position_使用_mode_指定它是如何搬到那里。

**See also** [position](qdesignerformwindowcursorinterface.html#position)（）和[movePosition](qdesignerformwindowcursorinterface.html#movePosition)（ ） 。

```
QDesignerFormWindowCursorInterface.setProperty (self, QString name, QVariant value)
```

这种方法是抽象的，应在任何子类中重新实现。

设置该属性与给定_name_为当前选择的窗口小部件的指定的_value_。

**See also** [setWidgetProperty](qdesignerformwindowcursorinterface.html#setWidgetProperty)（）和[resetWidgetProperty](qdesignerformwindowcursorinterface.html#resetWidgetProperty)（ ） 。

```
QDesignerFormWindowCursorInterface.setWidgetProperty (self, QWidget widget, QString name, QVariant value)
```

这种方法是抽象的，应在任何子类中重新实现。

设置该属性与给定_name_对于给定的_widget_到指定的_value_。

**See also** [resetWidgetProperty](qdesignerformwindowcursorinterface.html#resetWidgetProperty)（）和[setProperty](qdesignerformwindowcursorinterface.html#setProperty)（ ） 。

```
QWidget QDesignerFormWindowCursorInterface.widget (self, int index)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回该插件与给定的_index_在窗体窗口小部件的列表。

](qwidget.html)

[**See also**](qwidget.html) [selectedWidget](qdesignerformwindowcursorinterface.html#selectedWidget)（ ） 。

```
int QDesignerFormWindowCursorInterface.widgetCount (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回小部件在窗体窗口的数量。

**See also** [selectedWidgetCount](qdesignerformwindowcursorinterface.html#selectedWidgetCount)（ ） 。