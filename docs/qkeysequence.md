# QKeySequence Class Reference

## [[QtGui](index.htm) module]

该QKeySequence类封装所使用的快捷键的按键顺序。[More...](#details)

### Types

*   `enum SequenceFormat { NativeText, PortableText }`
*   `enum SequenceMatch { NoMatch, PartialMatch, ExactMatch }`
*   `enum StandardKey { UnknownKey, HelpContents, WhatsThis, Open, ..., Quit }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QKeySequence ks)`
*   `__init__ (self, QString key, SequenceFormat format)`
*   `__init__ (self, int k1, int key2 = 0, int key3 = 0, int key4 = 0)`
*   `__init__ (self, QVariant variant)`
*   `int count (self)`
*   `bool isDetached (self)`
*   `bool isEmpty (self)`
*   `SequenceMatch matches (self, QKeySequence seq)`
*   `swap (self, QKeySequence other)`
*   `QString toString (self, SequenceFormat format = QKeySequence.PortableText)`

### Static Methods

*   `QKeySequence fromString (QString str, SequenceFormat format = QKeySequence.PortableText)`
*   `list-of-QKeySequence keyBindings (StandardKey key)`
*   `QKeySequence mnemonic (QString text)`

### Special Methods

*   `bool __eq__ (self, QKeySequence other)`
*   `bool __ge__ (self, QKeySequence other)`
*   `int __getitem__ (self, int i)`
*   `bool __gt__ (self, QKeySequence other)`
*   `int __int__ (self)`
*   `bool __le__ (self, QKeySequence other)`
*   `__len__ (self)`
*   `bool __lt__ (self, QKeySequence ks)`
*   `bool __ne__ (self, QKeySequence other)`

* * *

## Detailed Description

这个类可以醃制。

[StandardKey](qkeysequence.html#StandardKey-enum)，[QString](qstring.html)或Python的int对象可随时使用[QKeySequence](qkeysequence.html)预计。

该QKeySequence类封装所使用的快捷键的按键顺序。

在其最常见的形式中，一个键序列描述了必须一起使用，以执行某些操作键的组合。密钥序列用于与[QAction](qaction.html)对象到指定键盘快捷键可以用来触发动作。

键序列可以用作键盘快捷键在三种不同的方式来构造：

*   For standard shortcuts, a [standard key](qkeysequence.html#StandardKey-enum) can be used to request the platform-specific key sequence associated with each shortcut.
*   For custom shortcuts, human-readable strings such as "Ctrl+X" can be used, and these can be translated into the appropriate shortcuts for users of different languages. Translations are made in the "[QShortcut](qshortcut.html)" context.
*   For hard-coded shortcuts, integer key codes can be specified with a combination of values defined by the [Qt.Key](qt.html#Key-enum) and [Qt.Modifier](qt.html#Modifier-enum) enum values. Each key code consists of a single [Qt.Key](qt.html#Key-enum) value and zero or more modifiers, such as [Qt.SHIFT](qt.html#Modifier-enum), [Qt.CTRL](qt.html#Modifier-enum), [Qt.ALT](qt.html#Modifier-enum) and [Qt.META](qt.html#Modifier-enum).

例如，**Ctrl P**可能用作用于打印文档的快捷方式的序列，并且可以在以下任一方式来指定：

```
 QKeySequence(QKeySequence.Print);
 QKeySequence(tr("Ctrl+P"));
 QKeySequence(tr("Ctrl+p"));
 QKeySequence([Qt](qt.html).CTRL + [Qt](qt.html).Key_P);

```

需要注意的是，对于字母，在规范字符串的情况下并不重要。在上面的例子中，用户并不需要按住**Shift**键激活用的“Ctrl + P ”指定一个快捷方式。然而，对于其他的键，使用**Shift**作为一个未指定的额外修饰键会导致混乱的键盘布局不同，所使用的那些开发者的应用程序的用户。请参阅[Keyboard Layout Issues](#keyboard-layout-issues)下面的部分获取更多细节。

优选的是，其中可以使用标准的快捷方式。当创建非标准的快捷键按键顺序，你应该使用人类可读的字符串优先于硬编码的整数值。

QKeySequence对象可以强制转换为[QString](qstring.html)取得该序列的人类可读的翻译版本。类似地，[toString](qkeysequence.html#toString)（ ）函数生成的菜单人类可读的字符串使用。在Mac OS X ，适当的符号是用来使用的Macintosh键盘上的特殊键来形容键盘快捷键。

指定硬编码键码的另一种方法是使用字符的Unicode代码点，例如， 'A'给出了相同的键顺序[Qt.Key_A](qt.html#Key-enum)。

**Note:**在Mac OS X中，提及“ Ctrl”键，[Qt.CTRL](qt.html#Modifier-enum)， Qt.Control和[Qt.ControlModifier](qt.html#KeyboardModifier-enum)对应于**Command**键在Macintosh键盘上，而凡提述“元” ，[Qt.META](qt.html#Modifier-enum)， Qt.Meta和[Qt.MetaModifier](qt.html#KeyboardModifier-enum)对应于**Control**键。在Mac OS X开发人员可以使用相同的快捷键说明在所有平台，并如预期般在Mac OS X的应用程序会自动工作

### Standard Shortcuts

QKeySequence定义了许多[standard keyboard shortcuts](qkeysequence.html#StandardKey-enum)减少设置操作在一个典型的应用程序时所需的努力的量。下表显示了通常由四个广泛使用的平台的应用程序中使用这些标准的快捷方式一些常见的键序列。请注意，在Mac OS X中，**Ctrl**值对应于**Command**键在Macintosh键盘上，并且**Meta**值对应于**Control**键。

| [StandardKey](qkeysequence.html#StandardKey-enum) | Windows | Mac OS X | KDE | GNOME | S60 |
| --- | --- | --- | --- | --- | --- |
| [HelpContents](qkeysequence.html#StandardKey-enum) | F1 | Ctrl+? | F1 | F1 | F2 |
| [WhatsThis](qkeysequence.html#StandardKey-enum) | Shift+F1 | Shift+F1 | Shift+F1 | Shift+F1 | Shift+F1 |
| Open | Ctrl+O | Ctrl+O | Ctrl+O | Ctrl+O | (none) |
| Close | Ctrl+F4, Ctrl+W | Ctrl+W, Ctrl+F4 | Ctrl+W | Ctrl+W | (none) |
| Save | Ctrl+S | Ctrl+S | Ctrl+S | Ctrl+S | (none) |
| Quit |  | Ctrl+Q | Qtrl+Q | Qtrl+Q | (none) |
| [SaveAs](qkeysequence.html#StandardKey-enum) |  | Ctrl+Shift+S |  | Ctrl+Shift+S | (none) |
| New | Ctrl+N | Ctrl+N | Ctrl+N | Ctrl+N | (none) |
| Delete | Del | Del, Meta+D | Del, Ctrl+D | Del, Ctrl+D | Del |
| Cut | Ctrl+X, Shift+Del | Ctrl+X | Ctrl+X, F20, Shift+Del | Ctrl+X, F20, Shift+Del | Ctrl+X |
| Copy | Ctrl+C, Ctrl+Ins | Ctrl+C | Ctrl+C, F16, Ctrl+Ins | Ctrl+C, F16, Ctrl+Ins | Ctrl+C |
| Paste | Ctrl+V, Shift+Ins | Ctrl+V | Ctrl+V, F18, Shift+Ins | Ctrl+V, F18, Shift+Ins | Ctrl+V |
| Preferences |  | Ctrl+, |  |  | (none) |
| Undo | Ctrl+Z, Alt+Backspace | Ctrl+Z | Ctrl+Z, F14 | Ctrl+Z, F14 | Ctrl+Z |
| Redo | Ctrl+Y, Shift+Ctrl+Z, Alt+Shift+Backspace | Ctrl+Shift+Z | Ctrl+Shift+Z | Ctrl+Shift+Z | (none) |
| Back | Alt+Left, Backspace | Ctrl+[ | Alt+Left | Alt+Left | (none) |
| Forward | Alt+Right, Shift+Backspace | Ctrl+] | Alt+Right | Alt+Right | (none) |
| Refresh | F5 | F5 | F5 | Ctrl+R, F5 | (none) |
| [ZoomIn](qkeysequence.html#StandardKey-enum) | Ctrl+Plus | Ctrl+Plus | Ctrl+Plus | Ctrl+Plus | (none) |
| [ZoomOut](qkeysequence.html#StandardKey-enum) | Ctrl+Minus | Ctrl+Minus | Ctrl+Minus | Ctrl+Minus | (none) |
| Print | Ctrl+P | Ctrl+P | Ctrl+P | Ctrl+P | (none) |
| [AddTab](qkeysequence.html#StandardKey-enum) | Ctrl+T | Ctrl+T | Ctrl+Shift+N, Ctrl+T | Ctrl+T | (none) |
| [NextChild](qkeysequence.html#StandardKey-enum) | Ctrl+Tab, Forward, Ctrl+F6 | Ctrl+}, Forward, Ctrl+Tab | Ctrl+Tab, Forward, Ctrl+Comma | Ctrl+Tab, Forward | (none) |
| [PreviousChild](qkeysequence.html#StandardKey-enum) | Ctrl+Shift+Tab, Back, Ctrl+Shift+F6 | Ctrl+{, Back, Ctrl+Shift+Tab | Ctrl+Shift+Tab, Back, Ctrl+Period | Ctrl+Shift+Tab, Back | (none) |
| Find | Ctrl+F | Ctrl+F | Ctrl+F | Ctrl+F | (none) |
| [FindNext](qkeysequence.html#StandardKey-enum) | F3, Ctrl+G | Ctrl+G | F3 | Ctrl+G, F3 | (none) |
| [FindPrevious](qkeysequence.html#StandardKey-enum) | Shift+F3, Ctrl+Shift+G | Ctrl+Shift+G | Shift+F3 | Ctrl+Shift+G, Shift+F3 | (none) |
| Replace | Ctrl+H | (none) | Ctrl+R | Ctrl+H | (none) |
| [SelectAll](qkeysequence.html#StandardKey-enum) | Ctrl+A | Ctrl+A | Ctrl+A | Ctrl+A | (none) |
| Bold | Ctrl+B | Ctrl+B | Ctrl+B | Ctrl+B | (none) |
| Italic | Ctrl+I | Ctrl+I | Ctrl+I | Ctrl+I | (none) |
| Underline | Ctrl+U | Ctrl+U | Ctrl+U | Ctrl+U | (none) |
| [MoveToNextChar](qkeysequence.html#StandardKey-enum) | Right | Right | Right | Right | Right |
| [MoveToPreviousChar](qkeysequence.html#StandardKey-enum) | Left | Left | Left | Left | Left |
| [MoveToNextWord](qkeysequence.html#StandardKey-enum) | Ctrl+Right | Alt+Right | Ctrl+Right | Ctrl+Right | Ctrl+Right |
| [MoveToPreviousWord](qkeysequence.html#StandardKey-enum) | Ctrl+Left | Alt+Left | Ctrl+Left | Ctrl+Left | Ctrl+Left |
| [MoveToNextLine](qkeysequence.html#StandardKey-enum) | Down | Down | Down | Down | Down |
| [MoveToPreviousLine](qkeysequence.html#StandardKey-enum) | Up | Up | Up | Up | Up |
| [MoveToNextPage](qkeysequence.html#StandardKey-enum) | PgDown | PgDown, Alt+PgDown, Meta+Down, Meta+PgDown | PgDown | PgDown | PgDown |
| [MoveToPreviousPage](qkeysequence.html#StandardKey-enum) | PgUp | PgUp, Alt+PgUp, Meta+Up, Meta+PgUp | PgUp | PgUp | PgUp |
| [MoveToStartOfLine](qkeysequence.html#StandardKey-enum) | Home | Ctrl+Left, Meta+Left | Home | Home | Home |
| [MoveToEndOfLine](qkeysequence.html#StandardKey-enum) | End | Ctrl+Right, Meta+Right | End | End | End |
| [MoveToStartOfBlock](qkeysequence.html#StandardKey-enum) | (none) | Alt+Up, Meta+A | (none) | (none) | (none) |
| [MoveToEndOfBlock](qkeysequence.html#StandardKey-enum) | (none) | Alt+Down, Meta+E | (none) | (none) | (none) |
| [MoveToStartOfDocument](qkeysequence.html#StandardKey-enum) | Ctrl+Home | Ctrl+Up, Home | Ctrl+Home | Ctrl+Home | Ctrl+Home |
| [MoveToEndOfDocument](qkeysequence.html#StandardKey-enum) | Ctrl+End | Ctrl+Down, End | Ctrl+End | Ctrl+End | Ctrl+End |
| [SelectNextChar](qkeysequence.html#StandardKey-enum) | Shift+Right | Shift+Right | Shift+Right | Shift+Right | Shift+Right |
| [SelectPreviousChar](qkeysequence.html#StandardKey-enum) | Shift+Left | Shift+Left | Shift+Left | Shift+Left | Shift+Left |
| [SelectNextWord](qkeysequence.html#StandardKey-enum) | Ctrl+Shift+Right | Alt+Shift+Right | Ctrl+Shift+Right | Ctrl+Shift+Right | Ctrl+Shift+Right |
| [SelectPreviousWord](qkeysequence.html#StandardKey-enum) | Ctrl+Shift+Left | Alt+Shift+Left | Ctrl+Shift+Left | Ctrl+Shift+Left | Ctrl+Shift+Left |
| [SelectNextLine](qkeysequence.html#StandardKey-enum) | Shift+Down | Shift+Down | Shift+Down | Shift+Down | Shift+Down |
| [SelectPreviousLine](qkeysequence.html#StandardKey-enum) | Shift+Up | Shift+Up | Shift+Up | Shift+Up | Shift+Up |
| [SelectNextPage](qkeysequence.html#StandardKey-enum) | Shift+PgDown | Shift+PgDown | Shift+PgDown | Shift+PgDown | Shift+PgDown |
| [SelectPreviousPage](qkeysequence.html#StandardKey-enum) | Shift+PgUp | Shift+PgUp | Shift+PgUp | Shift+PgUp | Shift+PgUp |
| [SelectStartOfLine](qkeysequence.html#StandardKey-enum) | Shift+Home | Ctrl+Shift+Left | Shift+Home | Shift+Home | Shift+Home |
| [SelectEndOfLine](qkeysequence.html#StandardKey-enum) | Shift+End | Ctrl+Shift+Right | Shift+End | Shift+End | Shift+End |
| [SelectStartOfBlock](qkeysequence.html#StandardKey-enum) | (none) | Alt+Shift+Up, Meta+Shift+A | (none) | (none) | (none) |
| [SelectEndOfBlock](qkeysequence.html#StandardKey-enum) | (none) | Alt+Shift+Down, Meta+Shift+E | (none) | (none) | (none) |
| [SelectStartOfDocument](qkeysequence.html#StandardKey-enum) | Ctrl+Shift+Home | Ctrl+Shift+Up, Shift+Home | Ctrl+Shift+Home | Ctrl+Shift+Home | Ctrl+Shift+Home |
| [SelectEndOfDocument](qkeysequence.html#StandardKey-enum) | Ctrl+Shift+End | Ctrl+Shift+Down, Shift+End | Ctrl+Shift+End | Ctrl+Shift+End | Ctrl+Shift+End |
| [DeleteStartOfWord](qkeysequence.html#StandardKey-enum) | Ctrl+Backspace | Alt+Backspace | Ctrl+Backspace | Ctrl+Backspace | (none) |
| [DeleteEndOfWord](qkeysequence.html#StandardKey-enum) | Ctrl+Del | (none) | Ctrl+Del | Ctrl+Del | (none) |
| [DeleteEndOfLine](qkeysequence.html#StandardKey-enum) | (none) | (none) | Ctrl+K | Ctrl+K | (none) |
| [InsertParagraphSeparator](qkeysequence.html#StandardKey-enum) | Enter | Enter | Enter | Enter | (none) |
| [InsertLineSeparator](qkeysequence.html#StandardKey-enum) | Shift+Enter | Meta+Enter | Shift+Enter | Shift+Enter | (none) |

需要注意的是，由于用于标准的快捷方式键顺序的平台之间的不同，你还需要在每个平台上测试你的快捷方式，以确保您不会意外分配相同的密钥序列的许多行动。

### Keyboard Layout Issues

许多关键序列规格是由基于某些类型的键盘布局，而不是选择代表一个动作的名称的第一个字母键，如开发商选择**Ctrl S**（ “ Ctrl + S键” ）或**Ctrl C**（ “ Ctrl + C键” ） 。此外，由于某些符号只能用组合键对某些键盘布局的帮助输入，用于与一种键盘布局使用按键序列可以映射到一个不同的密钥，地图无钥匙可言，或者需要额外的辅助键来用在不同的键盘布局。

例如，快捷方式，**Ctrl plus**和**Ctrl minus**，通常被用作用于图形应用缩放操作的快捷键，并且这些可以的“Ctrl + - ”指定的“Ctrl + + ”和分别。然而，这些快捷方式指定和解释的方式取决于键盘布局。挪威键盘的用户会注意到，**+**和**-**键不是键盘上相邻，但仍然能够激活两个快捷键，而不需要按下**Shift**键。然而，用户与英国的键盘需要按住**Shift**键进入**+**符号，使得快捷有效地同为“ Ctrl + Shift + = ” 。

虽然有些开发商可能会采取完全指定所有他们用自己的键盘来启动快捷方式的改性剂，这也将导致不同的键盘布局的用户意外行为。

例如，使用英国键盘的显影剂可能会决定指定“ Ctrl + Shift + =”作为密钥序列，以便创建巧合的行为以同样的方式作为快捷方式**Ctrl plus**。然而，本**=**键需要使用被访问的**Shift**挪威键盘上的按键，有效地使所需要的快捷方式**Ctrl Shift Shift =**（一个不可能的组合键） 。

其结果是，两个人可读的字符串和硬编码的密钥代码既可以是有问题的指定可以在各种不同的键盘布局中使用的键序列时使用。只有使用[standard shortcuts](qkeysequence.html#StandardKey-enum)保证了用户将能够使用该开发人员的意图的快捷方式。

尽管这样，我们就可以通过确保人类可读的字符串的使用，从而有可能为不同语言的用户作出键序列的翻译解决这个问题。这种方法会成功的用户，其键盘对他们所使用的语言是最典型布局。

### GNU Emacs Style Key Sequences

类似于使用键序列[GNU Emacs](http://www.gnu.org/software/emacs/)，允许最多四个按键代码，可以通过使用多个参数的构造函数，或者通过逗号分隔的键序列的人类可读的字符串被创建。

例如，密钥序列**Ctrl X**其次是**Ctrl C**，可以使用以下任一方式来指定：

```
 QKeySequence(tr("Ctrl+X, Ctrl+C"));
 QKeySequence([Qt](qt.html).CTRL + [Qt](qt.html).Key_X, [Qt](qt.html).CTRL + [Qt](qt.html).Key_C);

```

**Warning:** A [QApplication](qapplication.html)实例必须已建成创建QKeySequence之前，否则，你的应用程序可能会崩溃。

* * *

## Type Documentation

```
QKeySequence.SequenceFormat
```

| Constant | Value | Description |
| --- | --- | --- |
| `QKeySequence.NativeText` | `0` | 该密钥序列为平台特定的字符串。这意味着，它将会显示翻译并在Mac上它会像一个键序列从菜单栏。当你想要显示的字符串给用户这个枚举最好用。 |
| `QKeySequence.PortableText` | `1` | 键序列中给出一个“便携式”的格式，适合阅读和写入文件。在许多情况下，它看起来将类似于在Windows和X11原生文本。 |

```
QKeySequence.SequenceMatch
```

| Constant | Value | Description |
| --- | --- | --- |
| `QKeySequence.NoMatch` | `0` | 该键序列是不同的，不甚至部分匹配。 |
| `QKeySequence.PartialMatch` | `1` | 该键序列匹配部分，但也不尽相同。 |
| `QKeySequence.ExactMatch` | `2` | 密钥序列是相同的。 |

```
QKeySequence.StandardKey
```

这个枚举表示标准的键绑定。它们可以用于分配依赖于平台的键盘快捷键，一[QAction](qaction.html)。

请注意，键绑定是平台相关的。当前绑定的快捷键可以使用查询[keyBindings](qkeysequence.html#keyBindings)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QKeySequence.AddTab` | `19` | 添加新的选项卡。 |
| `QKeySequence.Back` | `13` | 导航回。 |
| `QKeySequence.Bold` | `27` | 粗体文本。 |
| `QKeySequence.Close` | `4` | 关闭文件/选项卡。 |
| `QKeySequence.Copy` | `9` | 复制。 |
| `QKeySequence.Cut` | `8` | 切。 |
| `QKeySequence.Delete` | `7` | 删除。 |
| `QKeySequence.DeleteEndOfLine` | `60` | 删除行尾。 |
| `QKeySequence.DeleteEndOfWord` | `59` | 从游标的末尾删除单词。 |
| `QKeySequence.DeleteStartOfWord` | `58` | 删除一个字到光标的开始。 |
| `QKeySequence.Find` | `22` | 查找文件。 |
| `QKeySequence.FindNext` | `23` | 查找下一个结果。 |
| `QKeySequence.FindPrevious` | `24` | 查找上一个结果。 |
| `QKeySequence.Forward` | `14` | 向前导航。 |
| `QKeySequence.HelpContents` | `1` | 打开帮助内容。 |
| `QKeySequence.InsertLineSeparator` | `62` | 插入一个新行。 |
| `QKeySequence.InsertParagraphSeparator` | `61` | 插入一个新的段落。 |
| `QKeySequence.Italic` | `28` | 斜体文本。 |
| `QKeySequence.MoveToEndOfBlock` | `41` | 移动光标到块的结尾。此快捷方式仅用于在OS X。 |
| `QKeySequence.MoveToEndOfDocument` | `43` | 将光标移动到文件末尾。 |
| `QKeySequence.MoveToEndOfLine` | `39` | 移动光标到行尾。 |
| `QKeySequence.MoveToNextChar` | `30` | 将光标移动到下一个字符。 |
| `QKeySequence.MoveToNextLine` | `34` | 将光标移动到下一行。 |
| `QKeySequence.MoveToNextPage` | `36` | 将光标移动到下一个页面。 |
| `QKeySequence.MoveToNextWord` | `32` | 将光标移动到下一个单词。 |
| `QKeySequence.MoveToPreviousChar` | `31` | 将光标移动到前一个字符。 |
| `QKeySequence.MoveToPreviousLine` | `35` | 移动光标到上一行。 |
| `QKeySequence.MoveToPreviousPage` | `37` | 将光标移动到上一个页面。 |
| `QKeySequence.MoveToPreviousWord` | `33` | 将光标移动到前一个单词。 |
| `QKeySequence.MoveToStartOfBlock` | `40` | 将光标移动到开始一个块。此快捷方式仅用于OS X。 |
| `QKeySequence.MoveToStartOfDocument` | `42` | 移动光标到启动文件。 |
| `QKeySequence.MoveToStartOfLine` | `38` | 移动光标到行首。 |
| `QKeySequence.New` | `6` | 创建新文档。 |
| `QKeySequence.NextChild` | `20` | 导航到下一个选项卡或子窗口。 |
| `QKeySequence.Open` | `3` | 打开的文档。 |
| `QKeySequence.Paste` | `10` | 粘贴。 |
| `QKeySequence.Preferences` | `64` | 打开选项对话框。 |
| `QKeySequence.PreviousChild` | `21` | 浏览上一个选项卡或子窗口。 |
| `QKeySequence.Print` | `18` | 打印文档。 |
| `QKeySequence.Quit` | `65` | 退出应用程序。 |
| `QKeySequence.Redo` | `12` | 重做。 |
| `QKeySequence.Refresh` | `15` | 刷新或重新加载当前文档。 |
| `QKeySequence.Replace` | `25` | 查找和替换。 |
| `QKeySequence.SaveAs` | `63` | 提示用户输入一个文件名后保存文件。 |
| `QKeySequence.Save` | `5` | 保存文件。 |
| `QKeySequence.SelectAll` | `26` | 选择所有文本。 |
| `QKeySequence.SelectEndOfBlock` | `55` | 扩展选择到文本块的结尾。此快捷方式仅用于OS X。 |
| `QKeySequence.SelectEndOfDocument` | `57` | 扩展选择到文件末尾。 |
| `QKeySequence.SelectEndOfLine` | `53` | 扩展选择到行尾。 |
| `QKeySequence.SelectNextChar` | `44` | 扩展选择到下一个字符。 |
| `QKeySequence.SelectNextLine` | `48` | 扩展选择到下一行。 |
| `QKeySequence.SelectNextPage` | `50` | 扩展选择到下一个页面。 |
| `QKeySequence.SelectNextWord` | `46` | 扩展选择到下一个单词。 |
| `QKeySequence.SelectPreviousChar` | `45` | 扩展选择到一个字符。 |
| `QKeySequence.SelectPreviousLine` | `49` | 扩展选择到上一行。 |
| `QKeySequence.SelectPreviousPage` | `51` | 扩展选择到上一个页面。 |
| `QKeySequence.SelectPreviousWord` | `47` | 扩展选择到上一个单词。 |
| `QKeySequence.SelectStartOfBlock` | `54` | 扩展选择到一个文本块的开始。此快捷方式仅用于OS X。 |
| `QKeySequence.SelectStartOfDocument` | `56` | 扩展选择开始文档。 |
| `QKeySequence.SelectStartOfLine` | `52` | 扩展选择到行首。 |
| `QKeySequence.Underline` | `29` | 下划线的文本。 |
| `QKeySequence.Undo` | `11` | 撤消。 |
| `QKeySequence.UnknownKey` | `0` | 未绑定的关键。 |
| `QKeySequence.WhatsThis` | `2` | 激活什么的。 |
| `QKeySequence.ZoomIn` | `16` | 放大。 |
| `QKeySequence.ZoomOut` | `17` | 缩小。 |

这个枚举被引入或修改的Qt 4.2 。

* * *

## Method Documentation

```
QKeySequence.__init__ (self)
```

构造一个空键序列。

```
QKeySequence.__init__ (self, QKeySequence ks)
```

创建从一个键序列_key_字符串。例如“ CTRL + O ”给出Ctrl + 'O' 。字符串“ Ctrl”键， “Shift”键， “ Alt”键和“元”均确认，以及他们的翻译等价于“[QShortcut](qshortcut.html)“上下文（使用[QObject.tr](qobject.html#tr)（））。

最多四个按键代码可以通过用逗号分隔输入，如： “ALT + X ， Ctrl + S键， Q” 。

_key_应该是在[NativeText](qkeysequence.html#SequenceFormat-enum)格式。

此构造方法通常用于[tr](qobject.html#tr)（ ） ，这样的快捷键可以更换的翻译：

```
 [QMenu](qmenu.html) *file = new [QMenu](qmenu.html)(this);
 file->addAction(tr("&Open..."), this, SLOT(open()),
                   [QKeySequence](qkeysequence.html)(tr("Ctrl+O", "File|Open")));

```

请注意“文件|打开”翻译注释。它是由无必要手段，但它提供了一些背景的人翻译。

```
QKeySequence.__init__ (self, QString key, SequenceFormat format)
```

创建从一个键序列_key_字符串的基础上_format_。

此功能被引入Qt的4.7 。

```
QKeySequence.__init__ (self, int k1, int key2 = 0, int key3 = 0, int key4 = 0)
```

构建了一个密钥序列具有多达4个按键_k1_，_k2_，_k3_和_k4_。

关键的代码列在[Qt.Key](qt.html#Key-enum)并且可以与改性剂相结合（见[Qt.Modifier](qt.html#Modifier-enum)）如[Qt.SHIFT](qt.html#Modifier-enum)，[Qt.CTRL](qt.html#Modifier-enum)，[Qt.ALT](qt.html#Modifier-enum)或[Qt.META](qt.html#Modifier-enum)。

```
QKeySequence.__init__ (self, QVariant variant)
```

拷贝构造函数。使得副本_keysequence_。

```
int QKeySequence.count (self)
```

返回键的键序列的数目。最大值是4 。

```
QKeySequence QKeySequence.fromString (QString str, SequenceFormat format = QKeySequence.PortableText)
```

[](qkeysequence.html)

[返回](qkeysequence.html)[QKeySequence](qkeysequence.html)从字符串_str_基于_format_。

这个函数是Qt 4.1中引入。

**See also** [toString](qkeysequence.html#toString)（ ） 。

```
bool QKeySequence.isDetached (self)
```

```
bool QKeySequence.isEmpty (self)
```

返回True如果密钥序列为空，否则返回False 。

```
list-of-QKeySequence QKeySequence.keyBindings (StandardKey key)
```

返回键绑定的列表为给定的_key_。调用此函数的结果会根据目标平台上有所不同。列表中的第一个元素表示为给定平台的主要捷径。如果结果包含一个以上的结果是，这些可以被认为是另一种快捷方式对给定相同的平台上_key_。

这个函数中引入了Qt 4.2中。

```
SequenceMatch QKeySequence.matches (self, QKeySequence seq)
```

[](qkeysequence.html#SequenceMatch-enum)

[匹配序列_seq_。回报](qkeysequence.html#SequenceMatch-enum)[ExactMatch](qkeysequence.html#SequenceMatch-enum)如果成功的话，[PartialMatch](qkeysequence.html#SequenceMatch-enum)如果_seq_不完全匹配，并[NoMatch](qkeysequence.html#SequenceMatch-enum)如果序列没有任何共同之处。回报[NoMatch](qkeysequence.html#SequenceMatch-enum)如果_seq_较短。

```
QKeySequence QKeySequence.mnemonic (QString text)
```

[

返回助记符中的快捷键序列_text_，或者一个空键序列，如果没有助记符发现。

](qkeysequence.html)

[例如，助记符（ “E ＆ XIT ” ）返回`Qt.ALT+Qt.Key_X`，助记符（ “戒菸大” ）的回报`ALT+Key_Q`和助记符（ “退出” ）返回一个空](qkeysequence.html)[QKeySequence](qkeysequence.html)。

我们提供了一个[list of common mnemonics](index.htm)英文的。在撰写本文时，微软及公开组似乎并没有发出其他语言的等价建议。

**See also** [qt_set_sequence_auto_mnemonic](index.htm#qt_set_sequence_auto_mnemonic)（ ） 。

```
QKeySequence.swap (self, QKeySequence other)
```

交换密钥序列_other_与此键序列。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QString QKeySequence.toString (self, SequenceFormat format = QKeySequence.PortableText)
```

返回键序列的字符串表示形式的基础上，_format_。

例如，该值[Qt.CTRL](qt.html#Modifier-enum)+[Qt.Key_O](qt.html#Key-enum)结果在“ CTRL + O ” 。如果密钥序列具有多个密钥代码，每一个由逗号分隔的字符串中返回，如“ Alt + X组合，按Ctrl + Y，Z ” 。琴弦， “Ctrl”键， “Shift”键，使用等换算[QObject.tr](qobject.html#tr)在（ ）中的“[QShortcut](qshortcut.html)“上下文。

如果密钥序列没有按键，则返回一个空字符串。

在Mac OS X ，返回的字符串类似于显示在菜单栏的顺序。

这个函数是Qt 4.1中引入。

**See also** [fromString](qkeysequence.html#fromString)（ ） 。

```
bool QKeySequence.__eq__ (self, QKeySequence other)
```

```
bool QKeySequence.__ge__ (self, QKeySequence other)
```

```
int QKeySequence.__getitem__ (self, int i)
```

```
bool QKeySequence.__gt__ (self, QKeySequence other)
```

```
int QKeySequence.__int__ (self)
```

```
bool QKeySequence.__le__ (self, QKeySequence other)
```

```
 QKeySequence.__len__ (self)
```

```
bool QKeySequence.__lt__ (self, QKeySequence ks)
```

```
bool QKeySequence.__ne__ (self, QKeySequence other)
```