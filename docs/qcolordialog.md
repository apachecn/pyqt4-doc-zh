# QColorDialog Class Reference

## [[QtGui](index.htm) module]

该QColorDialog类提供了一个对话框控件指定颜色。[More...](#details)

继承[QDialog](qdialog.html)。

### Types

*   `enum ColorDialogOption { ShowAlphaChannel, NoButtons, DontUseNativeDialog }`
*   `class **[ColorDialogOptions](index.htm)**`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QColor initial, QWidget parent = None)`
*   `changeEvent (self, QEvent e)`
*   `QColor currentColor (self)`
*   `done (self, int result)`
*   `open (self)`
*   `open (self, QObject receiver, SLOT()SLOT() member)`
*   `open (self, callable receiver)`
*   `ColorDialogOptions options (self)`
*   `QColor selectedColor (self)`
*   `setCurrentColor (self, QColor color)`
*   `setOption (self, ColorDialogOption option, bool on = True)`
*   `setOptions (self, ColorDialogOptions options)`
*   `setVisible (self, bool visible)`
*   `bool testOption (self, ColorDialogOption option)`

### Static Methods

*   `int customColor (int)`
*   `int customCount ()`
*   `QColor getColor (QColor initial = Qt.white, QWidget parent = None)`
*   `QColor getColor (QColor initial, QWidget parent, QString title, ColorDialogOptions options = 0)`
*   `(int, bool ok) getRgba (int initial = 4294967295, QWidget parent = None)`
*   `setCustomColor (int, int)`
*   `setStandardColor (int, int)`

### Qt Signals

*   `void colorSelected (const QColor&)`
*   `void currentColorChanged (const QColor&)`

* * *

## Detailed Description

该QColorDialog类提供了一个对话框控件指定颜色。

颜色对话框的功能是让用户选择的颜色。例如，您可以使用这一个绘图程序，以允许用户设置画笔的颜色。

静态函数提供了模态对话框的颜色。

静[getColor](qcolordialog.html#getColor)（）函数显示对话框，并且允许用户指定颜色。此功能也可以用来让用户选择一种颜色与透明度级别：通过[ShowAlphaChannel](qcolordialog.html#ColorDialogOption-enum)选项作为附加参数。

用户可以存储[customCount](qcolordialog.html#customCount)（ ）不同的自定义颜色。自定义颜色是由所有的颜色对话框共享，程序的执行过程中记住。使用[setCustomColor](qcolordialog.html#setCustomColor)（ ）来设置自定义颜色，并使用[customColor](qcolordialog.html#customColor)（）来获取它们。

该[Standard Dialogs](index.htm)示例显示了如何使用QColorDialog以及其他内置Qt对话框。

![A color dialog in the Plastique widget style.](../img/plastique-colordialog.png)

* * *

## Type Documentation

```
QColorDialog.ColorDialogOption
```

此枚举指定了影响颜色对话框的外观和感觉的各种选项。

| Constant | Value | Description |
| --- | --- | --- |
| `QColorDialog.ShowAlphaChannel` | `0x00000001` | 允许用户选择一种颜色的alpha分量。 |
| `QColorDialog.NoButtons` | `0x00000002` | 不显示**OK**和**Cancel**按钮。 （有用的“现场对话” 。 ） |
| `QColorDialog.DontUseNativeDialog` | `0x00000004` | 使用Qt的Mac上的标准颜色对话框，而不是苹果的原生颜色面板。 |

这个枚举被引入或修改的Qt 4.5 。

该ColorDialogOptions类型是一个typedef为[QFlags](index.htm)\u003cColorDialogOption\u003e 。它存储ColorDialogOption值的或组合。

**See also** [options](qcolordialog.html#options-prop)，[setOption](qcolordialog.html#setOption)（ ）[testOption](qcolordialog.html#testOption)（）和[windowModality](qwidget.html#windowModality-prop)（ ） 。

* * *

## Method Documentation

```
QColorDialog.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个颜色对话框与给定_parent_。

此功能被引入Qt的4.5 。

```
QColorDialog.__init__ (self, QColor initial, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个颜色对话框与给定_parent_并指定_initial_颜色。

此功能被引入Qt的4.5 。

```
QColorDialog.changeEvent (self, QEvent e)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QColor QColorDialog.currentColor (self)
```

[

```
int QColorDialog.customColor (int)
```

](qcolor.html)

[返回自定义颜色在给定的_index_作为](qcolor.html)[QRgb](qcolor.html#QRgb-typedef)值。

此功能被引入Qt的4.5 。

**See also** [setCustomColor](qcolordialog.html#setCustomColor)（ ） 。

```
int QColorDialog.customCount ()
```

返回所支持的自定义颜色数[QColorDialog](qcolordialog.html)。所有的颜色对话框共用相同的自定义颜色。

```
QColorDialog.done (self, int result)
```

从重新实现[QDialog.done](qdialog.html#done)（ ） 。

关闭对话框，并将其结果代码_result_。如果显示此对话框[exec_](qdialog.html#exec)（ ） ， （）完成将导致本地事件循环来完成，并[exec_](qdialog.html#exec)（ ）返回_result_。

**See also** [QDialog.done](qdialog.html#done)（ ） 。

```
QColor QColorDialog.getColor (QColor initial = Qt.white, QWidget parent = None)
```

[](qcolor.html)

[弹出的窗口给出一个模式对话框的颜色_title_（或“选择颜色” ，如果没有指定） ，让用户选择一种颜色，并返回该颜色。彩色初始设定为_initial_。对话框是一个孩子_parent_。它返回一个无效的（见](qcolor.html)[QColor.isValid](qcolor.html#isValid)（ ） ）如果用户取消该对话框的颜色。

该_options_参数允许您自定义对话框。

在Symbian ，这个静态函数将使用原生颜色对话框，而不是一个[QColorDialog](qcolordialog.html)。在Symbian的参数_title_和_parent_有没有相关性和_options_参数仅用于定义是否被使用或不是天然颜色对话框。

此功能被引入Qt的4.5 。

```
QColor QColorDialog.getColor (QColor initial, QWidget parent, QString title, ColorDialogOptions options = 0)
```

[](qcolor.html)

[弹出一个模态对话框颜色，让用户选择一种颜色，并返回该颜色。彩色初始设定为_initial_。对话框是一个孩子_parent_。它返回一个无效的（见](qcolor.html)[QColor.isValid](qcolor.html#isValid)（ ） ）如果用户取消该对话框的颜色。

在Symbian ，这个静态函数将使用原生颜色对话框，而不是一个[QColorDialog](qcolordialog.html)。

```
(int, bool ok) QColorDialog.getRgba (int initial = 4294967295, QWidget parent = None)
```

```
QColorDialog.open (self)
```

显示该对话框的[window modal dialog](qdialog.html#modal-dialogs)，立即返回。

此功能被引入Qt的4.5 。

**See also** [QDialog.open](qdialog.html#open)（ ） 。

```
QColorDialog.open (self, QObject receiver, SLOT()SLOT() member)
```

这是一个重载函数。

在打开的对话框并连接其[colorSelected](qcolordialog.html#colorSelected)（）信号到由指定的槽_receiver_和_member_。

该信号会从插槽中断开时，关闭对话框。

此功能被引入Qt的4.5 。

```
QColorDialog.open (self, callable receiver)
```

```
ColorDialogOptions QColorDialog.options (self)
```

[](index.htm)

```
QColor QColorDialog.selectedColor (self)
```

[

返回用户选择通过单击颜色**OK**或等效按钮。

](qcolor.html)

[**Note:**这种颜色并非总是一样的保持的颜色](qcolor.html)[currentColor](qcolordialog.html#currentColor-prop)因为用户属性终于可以选择一个使用之前选择不同的颜色。

```
QColorDialog.setCurrentColor (self, QColor color)
```

```
QColorDialog.setCustomColor (int, int)
```

设置在自定义颜色_index_到[QRgb](qcolor.html#QRgb-typedef) _color_值。

**Note:**此功能并不适用于本机颜色对话框上的Mac OS X平台。如果您仍然需要使用此功能，请使用[QColorDialog.DontUseNativeDialog](qcolordialog.html#ColorDialogOption-enum)选项。

**See also** [customColor](qcolordialog.html#customColor)（ ） 。

```
QColorDialog.setOption (self, ColorDialogOption option, bool on = True)
```

设置给定_option_被启用，如果_on_是真的，否则，清除给定的_option_。

**See also** [options](qcolordialog.html#options-prop)和[testOption](qcolordialog.html#testOption)（ ） 。

```
QColorDialog.setOptions (self, ColorDialogOptions options)
```

```
QColorDialog.setStandardColor (int, int)
```

设置标准色在_index_到[QRgb](qcolor.html#QRgb-typedef) _color_值。

**Note:**此功能并不适用于本机颜色对话框上的Mac OS X平台。如果您仍然需要使用此功能，请使用[QColorDialog.DontUseNativeDialog](qcolordialog.html#ColorDialogOption-enum)选项。

```
QColorDialog.setVisible (self, bool visible)
```

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

更改对话框的可见性。如果_visible_为真，则显示的对话框，否则，它是隐藏的。

```
bool QColorDialog.testOption (self, ColorDialogOption option)
```

返回True如果给定的_option_被启用，否则返回False 。

此功能被引入Qt的4.5 。

**See also** [options](qcolordialog.html#options-prop)和[setOption](qcolordialog.html#setOption)（ ） 。

* * *

## Qt Signal Documentation

```
void colorSelected (const QColor&)
```

这是该信号的默认超载。

这个信号被发射的用户点击后刚**OK**选择要使用的颜色。所选择的颜色是由指定的_color_。

**See also** [color](index.htm)和[currentColorChanged](qcolordialog.html#currentColorChanged)（ ） 。

```
void currentColorChanged (const QColor&)
```

这是该信号的默认超载。

这个信号被发射时的对话在当前的颜色变化。当前颜色被指定_color_。

**See also** [color](index.htm)和[colorSelected](qcolordialog.html#colorSelected)（ ） 。