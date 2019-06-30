# QIcon Class Reference

## [[QtGui](index.htm) module]

该QIcon则类提供了在不同的模式和状态可缩放图标。[More...](#details)

### Types

*   `enum Mode { Normal, Disabled, Active, Selected }`
*   `enum State { On, Off }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPixmap pixmap)`
*   `__init__ (self, QIcon other)`
*   `__init__ (self, QString fileName)`
*   `__init__ (self, QIconEngine engine)`
*   `__init__ (self, QIconEngineV2 engine)`
*   `__init__ (self, QVariant variant)`
*   `QSize actualSize (self, QSize size, Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `addFile (self, QString fileName, QSize size = QSize(), Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `addPixmap (self, QPixmap pixmap, Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `list-of-QSize availableSizes (self, Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `int cacheKey (self)`
*   `bool isDetached (self)`
*   `bool isNull (self)`
*   `QString name (self)`
*   `paint (self, QPainter painter, QRect rect, Qt.Alignment alignment = Qt.AlignCenter, Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `paint (self, QPainter painter, int x, int y, int w, int h, Qt.Alignment alignment = Qt.AlignCenter, Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `QPixmap pixmap (self, QSize size, Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `QPixmap pixmap (self, int w, int h, Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `QPixmap pixmap (self, int extent, Mode mode = QIcon.Normal, State state = QIcon.Off)`
*   `int serialNumber (self)`
*   `swap (self, QIcon other)`

### Static Methods

*   `QIcon fromTheme (QString name, QIcon fallback = QIcon())`
*   `bool hasThemeIcon (QString name)`
*   `setThemeName (QString path)`
*   `setThemeSearchPaths (QStringList searchpath)`
*   `QString themeName ()`
*   `QStringList themeSearchPaths ()`

* * *

## Detailed Description

该QIcon则类提供了在不同的模式和状态可缩放图标。

一个QIcon则可以生成一组像素图的它被赋予较小的，更大的，积极的，和残疾人像素图。这样的像素图所使用的Qt控件显示代表一个特定动作的图标。

最简单的使用QIcon则是创建一个从[QPixmap](qpixmap.html)文件或资源，然后使用它，可以让Qt的制定所有必需的图标样式和大小。例如：

```
 [QToolButton](qtoolbutton.html) *button = new [QToolButton](qtoolbutton.html);
 button->setIcon(QIcon("open.xpm"));

```

要撤消QIcon则，只需在其位置空图标：

```
 button->setIcon(QIcon());

```

使用[QImageReader.supportedImageFormats](qimagereader.html#supportedImageFormats)（）和[QImageWriter.supportedImageFormats](qimagewriter.html#supportedImageFormats)（ ）函数来获取支持的文件格式的完整列表。

当您使用像素图（撷取像素图[QSize](qsize.html)，模式，状态） ，且没有像素映射为这个给定的大小，模式和状态已经被添加以[addFile](qicon.html#addFile)（）或[addPixmap](qicon.html#addPixmap)（），然后QIcon则将会产生1的飞行。该像素图的产生发生在一个[QIconEngineV2](qiconenginev2.html)。默认引擎秤像素映射下来，如果需要，但再也没有起来，并使用当前样式来计算伤残外观。通过使用自定义图标的引擎，您可以自定义生成图标的每一个方面。同[QIconEnginePluginV2](index.htm)它可以注册不同的图标引擎不同的文件后缀，从而有可能为第三方提供额外的图标引擎包括那些使用Qt 。

**Note:**由于Qt 4.2中，支持SVG图标引擎包括在内。

### Making Classes that Use QIcon

如果你自己写的小工具，有一个选项来设置一个小像素映射，可以考虑允许QIcon则到该像素图进行设置。 Qt的类[QToolButton](qtoolbutton.html)是这样的一个部件的一个例子。

提供一种方法来设置QIcon则，当你绘制图标，选择任何像素图是适合你的部件的当前状态。例如：

```
 void MyWidget.drawIcon([QPainter](qpainter.html) *painter, [QPoint](qpoint.html) pos)
 {
     [QPixmap](qpixmap.html) pixmap = icon.pixmap([QSize](qsize.html)(22, 22),
                                    isEnabled() ? QIcon.Normal
                                                : QIcon.Disabled,
                                    isChecked() ? QIcon.On
                                                : QIcon.Off);
     painter->drawPixmap(pos, pixmap);
 }

```

您可能也使的使用`Active`模式，或许让你的widget`Active`当鼠标悬停在小部件（见[QWidget.enterEvent](qwidget.html#enterEvent)（ ） ） ，同时按下鼠标时以待释放，这将激活该功能，或当它是当前选定的项目。如果小部件可以切换，在“开”模式可能被用来绘制不同的图标。

![QIcon](../img/icon.png)

* * *

## Type Documentation

```
QIcon.Mode
```

该枚举类型描述了其中一个像素图的目的是要使用的模式。当前定义的模式有：

| Constant | Value | Description |
| --- | --- | --- |
| `QIcon.Normal` | `0` | 显示的像素图，当用户不与图标交互的，而是由图标表示的功能是可用的。 |
| `QIcon.Disabled` | `1` | 显示像素映射时由图标表示的功能不可用。 |
| `QIcon.Active` | `2` | 显示像素映射时由图标表示的功能是提供用户与交互图标，例如，移动鼠标，或单击它。 |
| `QIcon.Selected` | `3` | 显示像素映射时由图标表示该项目被选中。 |

```
QIcon.State
```

该枚举描述了其中一个像素图的目的是要使用的状态。该_state_可以是：

| Constant | Value | Description |
| --- | --- | --- |
| `QIcon.Off` | `1` | 显示像素图时，部件是在“关”的状态 |
| `QIcon.On` | `0` | 显示像素图时，部件是在一个“开”状态 |

* * *

## Method Documentation

```
QIcon.__init__ (self)
```

构造一个空的图标。

```
QIcon.__init__ (self, QPixmap pixmap)
```

从构造一个图标_pixmap_。

```
QIcon.__init__ (self, QIcon other)
```

构造的副本_other_。这是非常快的。

```
QIcon.__init__ (self, QString fileName)
```

构造一个图标从文件中给定的_fileName_。该文件将被按需加载。

If _fileName_包含相对路径（例如，文件名只）的相关文件，必须找到相对于运行时的工作目录。

文件名可以是指在磁盘上或对应用程序的嵌入资源之一实际的文件。请参阅[Resource System](index.htm)概述有关如何嵌入在应用程序的可执行映像和其他资源文件的详细信息。

使用[QImageReader.supportedImageFormats](qimagereader.html#supportedImageFormats)（）和[QImageWriter.supportedImageFormats](qimagewriter.html#supportedImageFormats)（ ）函数来获取支持的文件格式的完整列表。

```
QIcon.__init__ (self, QIconEngine engine)
```

该_engine_说法有它的所有权转移给Qt的。

创建一个具有特定图标的图标_engine_。图标采用了发动机的所有权。

```
QIcon.__init__ (self, QIconEngineV2 engine)
```

该_engine_说法有它的所有权转移给Qt的。

创建一个具有特定图标的图标_engine_。图标采用了发动机的所有权。

```
QIcon.__init__ (self, QVariant variant)
```

```
QSize QIcon.actualSize (self, QSize size, Mode mode = QIcon.Normal, State state = QIcon.Off)
```

[

返回图标的实际大小为所请求的_size_，_mode_和_state_。其结果可能会小于要求的，但从来没有较大。

](qsize.html)

[**See also**](qsize.html) [pixmap](qicon.html#pixmap)（）和[paint](qicon.html#paint)（ ） 。

```
QIcon.addFile (self, QString fileName, QSize size = QSize(), Mode mode = QIcon.Normal, State state = QIcon.Off)
```

增加了一个图像从文件用给定的_fileName_的图标，作为一个专业化的_size_，_mode_和_state_。该文件将被按需加载。注：自定义图标引擎可以自由地忽略额外添加的像素图。

If _fileName_包含相对路径（例如，文件名只）的相关文件，必须找到相对于运行时的工作目录。

文件名可以是指在磁盘上或对应用程序的嵌入资源之一实际的文件。请参阅[Resource System](index.htm)概述有关如何嵌入在应用程序的可执行映像和其他资源文件的详细信息。

使用[QImageReader.supportedImageFormats](qimagereader.html#supportedImageFormats)（）和[QImageWriter.supportedImageFormats](qimagewriter.html#supportedImageFormats)（ ）函数来获取支持的文件格式的完整列表。

注意：当您添加一个非空的文件名到[QIcon](qicon.html)，图标变为非空，即使该文件不存在或指向一个损坏的文件。

**See also** [addPixmap](qicon.html#addPixmap)（ ） 。

```
QIcon.addPixmap (self, QPixmap pixmap, Mode mode = QIcon.Normal, State state = QIcon.Off)
```

添加_pixmap_的图标，作为一个专业化的_mode_和_state_。

自定义图标的引擎可以自由地忽略额外添加的像素图。

**See also** [addFile](qicon.html#addFile)（ ） 。

```
list-of-QSize QIcon.availableSizes (self, Mode mode = QIcon.Normal, State state = QIcon.Off)
```

返回可用图标大小的列表指定_mode_和_state_。

此功能被引入Qt的4.5 。

```
int QIcon.cacheKey (self)
```

返回一个数字，用于标识此内容[QIcon](qicon.html)对象。不同[QIcon](qicon.html)对象可以具有相同的密钥，如果它们指的是相同的内容。

该cacheKey （ ）会改变时，该图标是通过改变[addPixmap](qicon.html#addPixmap)（）或[addFile](qicon.html#addFile)（ ） 。

缓存键是最有用与缓存结合使用。

此功能被引入Qt的4.3 。

**See also** [QPixmap.cacheKey](qpixmap.html#cacheKey)（ ） 。

```
QIcon QIcon.fromTheme (QString name, QIcon fallback = QIcon())
```

[](qicon.html)

[返回](qicon.html)[QIcon](qicon.html)对应_name_在当前的图标主题。如果没有这样的图标在当前主题中找到_fallback_返回来代替。

Freedesktop的图标规格及命名规范的最新版本可以在这里获得：

*   [http://standards.freedesktop.org/icon-theme-spec/icon-theme-spec-latest.html](http://standards.freedesktop.org/icon-theme-spec/icon-theme-spec-latest.html)
*   [http://standards.freedesktop.org/icon-naming-spec/icon-naming-spec-latest.html](http://standards.freedesktop.org/icon-naming-spec/icon-naming-spec-latest.html)

来从当前的图标主题的图标：

```
     [QIcon](qicon.html) undoicon = [QIcon](qicon.html).fromTheme("edit-undo");

```

或者，如果你想提供一个保证回退不支持主题图标的平台，您可以使用第二个参数：

```
     [QIcon](qicon.html) undoicon = [QIcon](qicon.html).fromTheme("edit-undo", [QIcon](qicon.html)(":/undo.png"));

```

**Note:**默认情况下，只有X11将支持主题图标。为了使用在Mac和Windows主题图标，你将不得不捆绑一个兼容的主题之一，您[themeSearchPaths](qicon.html#themeSearchPaths)（ ），并设置适当的[themeName](qicon.html#themeName)（ ） 。

此功能被引入Qt的4.6 。

**See also** [themeName](qicon.html#themeName)（ ）[setThemeName](qicon.html#setThemeName)（）和[themeSearchPaths](qicon.html#themeSearchPaths)（ ） 。

```
bool QIcon.hasThemeIcon (QString name)
```

返回True如果有一个图标供_name_在当前的图标主题，否则返回False 。

此功能被引入Qt的4.6 。

**See also** [themeSearchPaths](qicon.html#themeSearchPaths)（ ）[fromTheme](qicon.html#fromTheme)（）和[setThemeName](qicon.html#setThemeName)（ ） 。

```
bool QIcon.isDetached (self)
```

```
bool QIcon.isNull (self)
```

返回True如果该图标为空，否则返回False 。

图标是空的，如果它既不具有像素图，也不是一个文件名。

注意：即使是一个非空的图标可能无法建立有效像素映射，如。如果文件不存在或无法读取。

```
QString QIcon.name (self)
```

返回（如果可用）来创建图标，名称。

根据创建图标的方式，它可能有一个相关的名称。这是用于与创建的图标的情况下[fromTheme](qicon.html#fromTheme)（）或图标用[QIconEngine](qiconengine.html)支撑[QIconEngineV2.IconNameHook](qiconenginev2.html#IconEngineHook-enum)。

此功能被引入Qt的4.7 。

**See also** [fromTheme](qicon.html#fromTheme)（）和[QIconEngine](qiconengine.html)。

```
QIcon.paint (self, QPainter painter, QRect rect, Qt.Alignment alignment = Qt.AlignCenter, Mode mode = QIcon.Normal, State state = QIcon.Off)
```

使用_painter_绘制图标与指定的_alignment_，需要_mode_和_state_成长方形_rect_。

**See also** [actualSize](qicon.html#actualSize)（）和[pixmap](qicon.html#pixmap)（ ） 。

```
QIcon.paint (self, QPainter painter, int x, int y, int w, int h, Qt.Alignment alignment = Qt.AlignCenter, Mode mode = QIcon.Normal, State state = QIcon.Off)
```

这是一个重载函数。

绘制图标进入矩形[QRect](qrect.html)（_x_，_y_，_w_，_h_） 。

```
QPixmap QIcon.pixmap (self, QSize size, Mode mode = QIcon.Normal, State state = QIcon.Off)
```

[

返回一个像素图的要求_size_，_mode_和_state_，生成1如果必要的。像素图可能小于要求的，但从来没有较大。

](qpixmap.html)

[**See also**](qpixmap.html) [setPixmap](index.htm#setPixmap)（ ）[actualSize](qicon.html#actualSize)（）和[paint](qicon.html#paint)（ ） 。

```
QPixmap QIcon.pixmap (self, int w, int h, Mode mode = QIcon.Normal, State state = QIcon.Off)
```

[](qpixmap.html)

```
QPixmap QIcon.pixmap (self, int extent, Mode mode = QIcon.Normal, State state = QIcon.Off)
```

[

```
int QIcon.serialNumber (self)
```

```
QIcon.setThemeName (QString path)
```

设置当前的图标主题_name_。

该_name_应该对应于包含描述它的内容的index.theme文件中的themeSearchPath目录名（ ） 。

此功能被引入Qt的4.6 。

](qpixmap.html)

[**See also**](qpixmap.html) [themeSearchPaths](qicon.html#themeSearchPaths)（）和[themeName](qicon.html#themeName)（ ） 。

```
QIcon.setThemeSearchPaths (QStringList searchpath)
```

设置为图标主题的搜索路径_paths_。

此功能被引入Qt的4.6 。

**See also** [themeSearchPaths](qicon.html#themeSearchPaths)（ ）[fromTheme](qicon.html#fromTheme)（）和[setThemeName](qicon.html#setThemeName)（ ） 。

```
QIcon.swap (self, QIcon other)
```

交换图标_other_与此图标。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QString QIcon.themeName ()
```

返回当前的图标主题的名称。

在X11上，当前图标主题取决于您的桌面设置。在其他平台上它不是默认设置。

此功能被引入Qt的4.6 。

**See also** [setThemeName](qicon.html#setThemeName)（ ）[themeSearchPaths](qicon.html#themeSearchPaths)（ ）[fromTheme](qicon.html#fromTheme)（）和[hasThemeIcon](qicon.html#hasThemeIcon)（ ） 。

```
QStringList QIcon.themeSearchPaths ()
```

返回图标主题的搜索路径。

默认值将取决于平台：

在X11 ，搜索路径将如果有使用XDG_DATA_DIRS环境变量。

默认情况下，所有的平台都会有资源目录`:\icons`作为后备。您可以使用“ RCC项目” ，以从你的图标主题的资源文件。

此功能被引入Qt的4.6 。

**See also** [setThemeSearchPaths](qicon.html#setThemeSearchPaths)（ ）[fromTheme](qicon.html#fromTheme)（）和[setThemeName](qicon.html#setThemeName)（ ） 。