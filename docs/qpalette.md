# QPalette Class Reference

## [[QtGui](index.htm) module]

该QPalette类包含的颜色组每个插件的状态。[More...](#details)

### Types

*   `enum ColorGroup { Active, Disabled, Inactive, NColorGroups, ..., Normal }`
*   `enum ColorRole { WindowText, Foreground, Button, Light, ..., NoRole }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QColor button)`
*   `__init__ (self, Qt.GlobalColor button)`
*   `__init__ (self, QColor button, QColor background)`
*   `__init__ (self, QBrush foreground, QBrush button, QBrush light, QBrush dark, QBrush mid, QBrush text, QBrush bright_text, QBrush base, QBrush background)`
*   `__init__ (self, QColor foreground, QColor background, QColor light, QColor dark, QColor mid, QColor text, QColor base)`
*   `__init__ (self, QPalette palette)`
*   `__init__ (self, QVariant variant)`
*   `QBrush alternateBase (self)`
*   `QBrush background (self)`
*   `QBrush base (self)`
*   `QBrush brightText (self)`
*   `QBrush brush (self, ColorGroup cg, ColorRole cr)`
*   `QBrush brush (self, ColorRole cr)`
*   `QBrush button (self)`
*   `QBrush buttonText (self)`
*   `int cacheKey (self)`
*   `QColor color (self, ColorGroup cg, ColorRole cr)`
*   `QColor color (self, ColorRole cr)`
*   `ColorGroup currentColorGroup (self)`
*   `QBrush dark (self)`
*   `QBrush foreground (self)`
*   `QBrush highlight (self)`
*   `QBrush highlightedText (self)`
*   `bool isBrushSet (self, ColorGroup cg, ColorRole cr)`
*   `bool isCopyOf (self, QPalette p)`
*   `bool isEqual (self, ColorGroup cr1, ColorGroup cr2)`
*   `QBrush light (self)`
*   `QBrush link (self)`
*   `QBrush linkVisited (self)`
*   `QBrush mid (self)`
*   `QBrush midlight (self)`
*   `QPalette resolve (self, QPalette)`
*   `int resolve (self)`
*   `resolve (self, int mask)`
*   `int serialNumber (self)`
*   `setBrush (self, ColorGroup cg, ColorRole cr, QBrush brush)`
*   `setBrush (self, ColorRole acr, QBrush abrush)`
*   `setColor (self, ColorGroup acg, ColorRole acr, QColor acolor)`
*   `setColor (self, ColorRole acr, QColor acolor)`
*   `setColorGroup (self, ColorGroup cr, QBrush foreground, QBrush button, QBrush light, QBrush dark, QBrush mid, QBrush text, QBrush bright_text, QBrush base, QBrush background)`
*   `setCurrentColorGroup (self, ColorGroup cg)`
*   `QBrush shadow (self)`
*   `QBrush text (self)`
*   `QBrush toolTipBase (self)`
*   `QBrush toolTipText (self)`
*   `QBrush window (self)`
*   `QBrush windowText (self)`

### Special Methods

*   `bool __eq__ (self, QPalette p)`
*   `bool __ne__ (self, QPalette p)`

* * *

## Detailed Description

该QPalette类包含的颜色组每个插件的状态。

调色板由三个颜色组：_Active_，_Disabled_和_Inactive_。 Qt中的所有部件包含一个调色板，用自己的调色板画出自己。这使得用户界面易于配置和更容易保持一致。

如果您创建一个新的widget ，我们强烈建议您使用的颜色在调色板中，而非硬编码特定的颜色。

色组：

*   The Active group is used for the window that has keyboard focus.
*   The Inactive group is used for other windows.
*   The Disabled group is used for widgets (not windows) that are disabled for some reason.

活动和非活动窗口可以包含禁用的部件。 （残疾人士使用的部件通常被称为_inaccessible_ or _grayed out_。 ）

在大多数款式，活动和非活动看起来是一样的。

颜色和画笔可以在任何一个调色板中的颜色组与被设置为特定的角色[setColor](qpalette.html#setColor)（）和[setBrush](qpalette.html#setBrush)（ ） 。颜色组中包含的一组颜色绘制自己使用的小工具。我们建议小部件使用颜色组的角色从调色板中，如“前台”和“基地” ，而不是字面的颜色，如“红色”或“绿松石” 。色彩的角色列举和定义的[ColorRole](qpalette.html#ColorRole-enum)文档。

我们强烈建议您使用当前样式的默认调色板（通过返回[QApplication.palette](qapplication.html#palette)（））和修改是必要的。这是由Qt的部件进行绘制，当他们。

要修改调用函数的颜色组[setColor](qpalette.html#setColor)（）和[setBrush](qpalette.html#setBrush)（ ） ，这取决于你是否想要一个纯粹的颜色或像素图的图案。

也有相应[color](qpalette.html#color)（）和[brush](qpalette.html#brush)（ ） getter方法​​和常用的便利函数来获得[ColorRole](qpalette.html#ColorRole-enum)对于当前[ColorGroup](qpalette.html#ColorGroup-enum)：[window](qpalette.html#window)（ ）[windowText](qpalette.html#windowText)（ ）[base](qpalette.html#base)（）等

您可以使用拷贝构造函数和测试，看看如果两个调色板拷贝调色板_identical_ using [isCopyOf](qpalette.html#isCopyOf)（ ） 。

QPalette是通过使用优化[implicit sharing](index.htm)，所以它是非常有效的传递QPalette对象作为参数。

**Warning:**有些样式不使用调色板的所有图纸，举例来说，如果他们利用原生主题引擎。这对于在Windows XP中， Windows Vista和Mac OS X的风格的情况下。

* * *

## Type Documentation

```
QPalette.ColorGroup
```

| Constant | Value | Description |
| --- | --- | --- |
| `QPalette.Disabled` | `1` |   |
| `QPalette.Active` | `0` |   |
| `QPalette.Inactive` | `2` |   |
| `QPalette.Normal` | `Active` | 同义词活跃 |

```
QPalette.ColorRole
```

![Color Roles](../img/palette.png)

该ColorRole枚举定义了当前的图形用户界面中使用的不同象征意义的颜色角色。

中央角色是：

| Constant | Value | Description |
| --- | --- | --- |
| `QPalette.Window` | `10` | 一般的背景色。 |
| `QPalette.Background` | `Window` | 这个值是过时的。使用Window来代替。 |
| `QPalette.WindowText` | `0` | 一般的前景色。 |
| `QPalette.Foreground` | `WindowText` | 这个值是过时的。使用代替WindowText的。 |
| `QPalette.Base` | `9` | 大多采用作为背景色的文本输入窗口小部件，但也可以用于其他绘画 - 如组合框的背景下拉列表和工具栏的句柄。它通常是白色或其它浅色。 |
| `QPalette.AlternateBase` | `16` | 作为与交替行的颜色欣赏到备用背景色（见[QAbstractItemView.setAlternatingRowColors](qabstractitemview.html#alternatingRowColors-prop)（））。 |
| `QPalette.ToolTipBase` | `18` | 用作背景颜色[QToolTip](qtooltip.html)和[QWhatsThis](qwhatsthis.html)。工具提示使用的颜色不活动组[QPalette](qpalette.html)，因为工具提示未激活的窗口。 |
| `QPalette.ToolTipText` | `19` | 作为前景色[QToolTip](qtooltip.html)和[QWhatsThis](qwhatsthis.html)。工具提示使用的颜色不活动组[QPalette](qpalette.html)，因为工具提示未激活的窗口。 |
| `QPalette.Text` | `6` | 所使用的前景色`Base`。这通常是一样的`WindowText`，在这种情况下，它必须提供良好的对比度`Window`和`Base`。 |
| `QPalette.Button` | `1` | 一般按钮的背景颜色。这样的背景可以从不同的`Window`因为有些款式需要不同的背景颜色的按钮。 |
| `QPalette.ButtonText` | `8` | 与使用的前景色`Button`颜色。 |
| `QPalette.BrightText` | `7` | 文本颜色是从非常不同`WindowText`，并与对比以及如`Dark`。通常用于需要绘制文本的地方`Text` or `WindowText`将得到较差的对比度，例如在压制的按钮。请注意，文本颜色，可用于东西不仅仅是文字等;文字颜色_usually_用于文本，但它是相当普遍使用的文字颜色角色的线条，图标等 |

有大多用于三维斜角和阴影效果一些色彩的角色。所有这些通常是衍生自`Window`以及在依赖于该关系的方式使用。例如，按钮依赖于它，使斜面看起来有吸引力，和Motif滚动条依赖于`Mid`是从稍微不同的`Window`。

| Constant | Value | Description |
| --- | --- | --- |
| `QPalette.Light` | `2` | 比打火机`Button`颜色。 |
| `QPalette.Midlight` | `3` | 之间`Button`和`Light`。 |
| `QPalette.Dark` | `4` | 比较深`Button`。 |
| `QPalette.Mid` | `5` | 之间`Button`和`Dark`。 |
| `QPalette.Shadow` | `11` | 一个非常暗的颜色。默认情况下，阴影颜色[Qt.black](qt.html#GlobalColor-enum)。 |

选定的（标记）的项目有两个作用：

| Constant | Value | Description |
| --- | --- | --- |
| `QPalette.Highlight` | `12` | 颜色以指示所选项目或当前项目。默认情况下，突出显示颜色[Qt.darkBlue](qt.html#GlobalColor-enum)。 |
| `QPalette.HighlightedText` | `13` | 与对比的文字颜色`Highlight`。默认情况下，突出显示的文本颜色为[Qt.white](qt.html#GlobalColor-enum)。 |

有相关的超链接两种颜色的作用：

| Constant | Value | Description |
| --- | --- | --- |
| `QPalette.Link` | `14` | 用于未访问过的超链接的文本颜色。默认情况下，链接颜色是[Qt.blue](qt.html#GlobalColor-enum)。 |
| `QPalette.LinkVisited` | `15` | 用于已访问的超链接的文本颜色。默认情况下， linkvisited颜色[Qt.magenta](qt.html#GlobalColor-enum)。 |

请注意，我们不使用`Link`和`LinkVisited`呈现在Qt的富文本时，那角色，我们建议您使用CSS和[QTextDocument.setDefaultStyleSheet](qtextdocument.html#defaultStyleSheet-prop)（ ）函数来改变链接的外观。例如：

```
     [QTextBrowser](qtextbrowser.html) browser;
     [QColor](qcolor.html) linkColor([Qt](qt.html).red);
     [QString](qstring.html) sheet = [QString](qstring.html).fromLatin1("a { text-decoration: underline; color: %1 }").arg(linkColor.name());
     browser.document()->setDefaultStyleSheet(sheet);

```

| Constant | Value | Description |
| --- | --- | --- |
| `QPalette.NoRole` | `17` | 没有作用;此特殊的作用通常被用来表示一个作用还没有被分配。 |

* * *

## Method Documentation

```
QPalette.__init__ (self)
```

构造一个使用应用程序的默认调色板调色板对象。

**See also** [QApplication.setPalette](qapplication.html#setPalette)（）和[QApplication.palette](qapplication.html#palette)（ ） 。

```
QPalette.__init__ (self, QColor button)
```

构造一个调色板从_button_颜色。其他颜色的自动计算，在此基础上的色彩。`Window`将按钮的颜色为好。

```
QPalette.__init__ (self, Qt.GlobalColor button)
```

构造一个调色板从_button_颜色。其他颜色的自动计算，在此基础上的色彩。`Window`将按钮的颜色为好。

```
QPalette.__init__ (self, QColor button, QColor background)
```

构造一个调色板从_button_颜色和_window_。其他颜色的自动计算，根据这些颜色。

```
QPalette.__init__ (self, QBrush foreground, QBrush button, QBrush light, QBrush dark, QBrush mid, QBrush text, QBrush bright_text, QBrush base, QBrush background)
```

构造一个调色板。您可以通过其中的画笔，像素图或纯颜色_windowText_，_button_，_light_，_dark_，_mid_，_text_，_bright_text_，_base_和_window_。

**See also** [QBrush](qbrush.html)。

```
QPalette.__init__ (self, QColor foreground, QColor background, QColor light, QColor dark, QColor mid, QColor text, QColor base)
```

```
QPalette.__init__ (self, QPalette palette)
```

```
QPalette.__init__ (self, QVariant variant)
```

构造的副本_p_。

这个构造函数是快的感谢[implicit sharing](index.htm)。

```
QBrush QPalette.alternateBase (self)
```

[

返回当前颜色组的备用基地刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.background (self)
```

[](qbrush.html)

```
QBrush QPalette.base (self)
```

[

返回当前颜色组的基本刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.brightText (self)
```

[

返回当前颜色组的光明前景文本刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.brush (self, ColorGroup cg, ColorRole cr)
```

[

返回刷中指定的颜色_group_中，用于给定的颜色_role_。

](qbrush.html)

[**See also**](qbrush.html) [color](qpalette.html#color)（ ）[setBrush](qpalette.html#setBrush)（）和[ColorRole](qpalette.html#ColorRole-enum)。

```
QBrush QPalette.brush (self, ColorRole cr)
```

[

这是一个重载函数。

](qbrush.html)

[返回该已被设置为给定的彩色的画笔_role_在当前的](qbrush.html)[ColorGroup](qpalette.html#ColorGroup-enum)。

**See also** [color](qpalette.html#color)（ ）[setBrush](qpalette.html#setBrush)（）和[ColorRole](qpalette.html#ColorRole-enum)。

```
QBrush QPalette.button (self)
```

[

返回当前颜色组的按钮刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.buttonText (self)
```

[

返回当前颜色组的按钮文本前景刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
int QPalette.cacheKey (self)
```

返回一个数字，用于标识此内容[QPalette](qpalette.html)对象。不同[QPalette](qpalette.html)对象可以具有相同的密钥，如果它们指的是相同的内容。

该cacheKey （ ）会改变，当调色板被改变。

```
QColor QPalette.color (self, ColorGroup cg, ColorRole cr)
```

[

返回颜色中指定的颜色_group_中，用于给定的颜色_role_。

](qcolor.html)

[**See also**](qcolor.html) [brush](qpalette.html#brush)（ ）[setColor](qpalette.html#setColor)（）和[ColorRole](qpalette.html#ColorRole-enum)。

```
QColor QPalette.color (self, ColorRole cr)
```

[

这是一个重载函数。

](qcolor.html)

[返回该已被设置为给定的颜色的颜色_role_在当前的](qcolor.html)[ColorGroup](qpalette.html#ColorGroup-enum)。

**See also** [brush](qpalette.html#brush)（）和[ColorRole](qpalette.html#ColorRole-enum)。

```
ColorGroup QPalette.currentColorGroup (self)
```

[

返回调色板的当前颜色组。

](qpalette.html#ColorGroup-enum)

[**See also**](qpalette.html#ColorGroup-enum) [setCurrentColorGroup](qpalette.html#setCurrentColorGroup)（ ） 。

```
QBrush QPalette.dark (self)
```

[

返回当前颜色组的暗刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.foreground (self)
```

[](qbrush.html)

```
QBrush QPalette.highlight (self)
```

[

返回当前颜色组的重头戏刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.highlightedText (self)
```

[

返回当前颜色组的高亮文本刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
bool QPalette.isBrushSet (self, ColorGroup cg, ColorRole cr)
```

返回True如果[ColorGroup](qpalette.html#ColorGroup-enum) _cg_和[ColorRole](qpalette.html#ColorRole-enum) _cr_已经在此之前的调色板设置，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [setBrush](qpalette.html#setBrush)（ ） 。

```
bool QPalette.isCopyOf (self, QPalette p)
```

返回True如果这个调色板，_p_是彼此的副本，即其中一人被创建为其他既不其后修改的副本，否则返回False 。这比平等更严格的。

**See also** [operator=](qpalette.html#operator-eq)（）和[operator==](qpalette.html#operator-eq-eq)（ ） 。

```
bool QPalette.isEqual (self, ColorGroup cr1, ColorGroup cr2)
```

返回True （通常很快） ，如果色组_cg1_等于_cg2_否则返回False 。

```
QBrush QPalette.light (self)
```

[

返回当前颜色组的光刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.link (self)
```

[

返回当前颜色组的未访问过的链接文字笔刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.linkVisited (self)
```

[

返回当前颜色组的访问链接文本刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.mid (self)
```

[

返回当前颜色组的中间刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.midlight (self)
```

[

返回当前颜色组的midlight刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QPalette QPalette.resolve (self, QPalette)
```

[](qpalette.html)

[返回一个新的](qpalette.html)[QPalette](qpalette.html)具有从属性复制_other_。

```
int QPalette.resolve (self)
```

```
QPalette.resolve (self, int mask)
```

```
int QPalette.serialNumber (self)
```

```
QPalette.setBrush (self, ColorGroup cg, ColorRole cr, QBrush brush)
```

设置刷子对于给定的颜色_role_到指定的_brush_在调色板中的所有组。

**See also** [brush](qpalette.html#brush)（ ）[setColor](qpalette.html#setColor)（）和[ColorRole](qpalette.html#ColorRole-enum)。

```
QPalette.setBrush (self, ColorRole acr, QBrush abrush)
```

这是一个重载函数。

设置刷子中指定的颜色_group_中，用于给定的颜色_role_，以_brush_。

**See also** [brush](qpalette.html#brush)（ ）[setColor](qpalette.html#setColor)（）和[ColorRole](qpalette.html#ColorRole-enum)。

```
QPalette.setColor (self, ColorGroup acg, ColorRole acr, QColor acolor)
```

设置颜色中指定的颜色_group_中，用于给定的颜色_role_到指定的固_color_。

**See also** [setBrush](qpalette.html#setBrush)（ ）[color](qpalette.html#color)（）和[ColorRole](qpalette.html#ColorRole-enum)。

```
QPalette.setColor (self, ColorRole acr, QColor acolor)
```

这是一个重载函数。

设置用于给定的颜色的颜色_role_，所有的颜色组，到指定的固_color_。

**See also** [brush](qpalette.html#brush)（ ）[setColor](qpalette.html#setColor)（）和[ColorRole](qpalette.html#ColorRole-enum)。

```
QPalette.setColorGroup (self, ColorGroup cr, QBrush foreground, QBrush button, QBrush light, QBrush dark, QBrush mid, QBrush text, QBrush bright_text, QBrush base, QBrush background)
```

设置的组_cg_。您可以通过其中的画笔，像素图或纯颜色_windowText_，_button_，_light_，_dark_，_mid_，_text_，_bright_text_，_base_和_window_。

**See also** [QBrush](qbrush.html)。

```
QPalette.setCurrentColorGroup (self, ColorGroup cg)
```

调色板的当前颜色组设置为_cg_。

**See also** [currentColorGroup](qpalette.html#currentColorGroup)（ ） 。

```
QBrush QPalette.shadow (self)
```

[

返回当前颜色组的眼影刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.text (self)
```

[

返回当前颜色组的文本前景刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.toolTipBase (self)
```

[](qbrush.html)

[返回当前颜色组的刀尖基地刷。这个刷子是由](qbrush.html)[QToolTip](qtooltip.html)和[QWhatsThis](qwhatsthis.html)。

**Note:**工具提示使用的颜色不活动组[QPalette](qpalette.html)，因为工具提示未激活的窗口。

此功能被引入Qt的4.4 。

**See also** [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.toolTipText (self)
```

[](qbrush.html)

[返回当前颜色组的工具提示文本刷。这个刷子是由](qbrush.html)[QToolTip](qtooltip.html)和[QWhatsThis](qwhatsthis.html)。

**Note:**工具提示使用的颜色不活动组[QPalette](qpalette.html)，因为工具提示未激活的窗口。

此功能被引入Qt的4.4 。

**See also** [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.window (self)
```

[

返回当前颜色组的窗口（一般背景）刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
QBrush QPalette.windowText (self)
```

[

返回当前颜色组的窗口文本（一般前台）刷。

](qbrush.html)

[**See also**](qbrush.html) [ColorRole](qpalette.html#ColorRole-enum)和[brush](qpalette.html#brush)（ ） 。

```
bool QPalette.__eq__ (self, QPalette p)
```

```
bool QPalette.__ne__ (self, QPalette p)
```