# QFileDialog Class Reference

## [[QtGui](index.htm) module]

该QFileDialog中的类提供了一个对话框，让用户选择文件或目录。[More...](#details)

继承[QDialog](qdialog.html)。

### Types

*   `enum AcceptMode { AcceptOpen, AcceptSave }`
*   `enum DialogLabel { LookIn, FileName, FileType, Accept, Reject }`
*   `enum FileMode { AnyFile, ExistingFile, Directory, ExistingFiles, DirectoryOnly }`
*   `enum Option { ShowDirsOnly, DontResolveSymlinks, DontConfirmOverwrite, DontUseSheet, ..., HideNameFilterDetails }`
*   `class **[Options](index.htm)**`
*   `enum ViewMode { Detail, List }`

### Methods

*   `__init__ (self, QWidget parent, Qt.WindowFlags f)`
*   `__init__ (self, QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString())`
*   `accept (self)`
*   `AcceptMode acceptMode (self)`
*   `changeEvent (self, QEvent e)`
*   `bool confirmOverwrite (self)`
*   `QString defaultSuffix (self)`
*   `QDir directory (self)`
*   `done (self, int result)`
*   `FileMode fileMode (self)`
*   `QDir.Filters filter (self)`
*   `QStringList filters (self)`
*   `QStringList history (self)`
*   `QFileIconProvider iconProvider (self)`
*   `bool isNameFilterDetailsVisible (self)`
*   `bool isReadOnly (self)`
*   `QAbstractItemDelegate itemDelegate (self)`
*   `QString labelText (self, DialogLabel label)`
*   `QStringList nameFilters (self)`
*   `open (self)`
*   `open (self, QObject receiver, SLOT()SLOT() member)`
*   `open (self, callable receiver)`
*   `Options options (self)`
*   `QAbstractProxyModel proxyModel (self)`
*   `bool resolveSymlinks (self)`
*   `bool restoreState (self, QByteArray state)`
*   `QByteArray saveState (self)`
*   `QStringList selectedFiles (self)`
*   `QString selectedFilter (self)`
*   `QString selectedNameFilter (self)`
*   `selectFile (self, QString filename)`
*   `selectFilter (self, QString filter)`
*   `selectNameFilter (self, QString filter)`
*   `setAcceptMode (self, AcceptMode mode)`
*   `setConfirmOverwrite (self, bool enabled)`
*   `setDefaultSuffix (self, QString suffix)`
*   `setDirectory (self, QString directory)`
*   `setDirectory (self, QDir adirectory)`
*   `setFileMode (self, FileMode mode)`
*   `setFilter (self, QString filter)`
*   `setFilter (self, QDir.Filters filters)`
*   `setFilters (self, QStringList filters)`
*   `setHistory (self, QStringList paths)`
*   `setIconProvider (self, QFileIconProvider provider)`
*   `setItemDelegate (self, QAbstractItemDelegate delegate)`
*   `setLabelText (self, DialogLabel label, QString text)`
*   `setNameFilter (self, QString filter)`
*   `setNameFilterDetailsVisible (self, bool enabled)`
*   `setNameFilters (self, QStringList filters)`
*   `setOption (self, Option option, bool on = True)`
*   `setOptions (self, Options options)`
*   `setProxyModel (self, QAbstractProxyModel model)`
*   `setReadOnly (self, bool enabled)`
*   `setResolveSymlinks (self, bool enabled)`
*   `setSidebarUrls (self, list-of-QUrl urls)`
*   `setViewMode (self, ViewMode mode)`
*   `setVisible (self, bool visible)`
*   `list-of-QUrl sidebarUrls (self)`
*   `bool testOption (self, Option option)`
*   `ViewMode viewMode (self)`

### Static Methods

*   `QString getExistingDirectory (QWidget parent = None, QString caption = QString(), QString directory = QString(), Options options = QFileDialog.ShowDirsOnly)`
*   `QString getOpenFileName (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), Options options = 0)`
*   `QString getOpenFileName (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString selectedFilter = None, Options options = 0)`
*   `(QString, QString) getOpenFileNameAndFilter (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString initialFilter = QString(), Options options = 0)`
*   `QStringList getOpenFileNames (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), Options options = 0)`
*   `QStringList getOpenFileNames (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString selectedFilter = None, Options options = 0)`
*   `(QString, QString) getOpenFileNamesAndFilter (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString initialFilter = QString(), Options options = 0)`
*   `QString getSaveFileName (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), Options options = 0)`
*   `QString getSaveFileName (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString selectedFilter = None, Options options = 0)`
*   `(QString, QString) getSaveFileNameAndFilter (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString initialFilter = QString(), Options options = 0)`

### Qt Signals

*   `void currentChanged (const QString&)`
*   `void directoryEntered (const QString&)`
*   `void fileSelected (const QString&)`
*   `void filesSelected (const QStringList&)`
*   `void filterSelected (const QString&)`

* * *

## Detailed Description

该QFileDialog中的类提供了一个对话框，让用户选择文件或目录。

在QFileDialog中类使用户可以遍历文件系统，以选择一个或多个文件或目录。

创建一个QFileDialog中最简单的方法是使用静态函数。在Windows，Mac OS X ， KDE和GNOME ，这些静态函数将调用本地文件对话框时可能的。

```
 fileName = QFileDialog.getOpenFileName(this,
     tr("Open Image"), "/home/jana", tr("Image Files (*.png *.jpg *.bmp)"));

```

在上面的例子中，一个模态QFileDialog中使用静态函数创建。该对话框最初显示“ /首页/贾纳”目录中的内容，并显示文件匹配字符串中给定的模式“图像文件（ * 。 PNG ，JPG等图片。 BMP ） ” 。文件对话框的父被设置为_this_和窗口标题设置为“打开图像” 。

如果你想使用多个过滤器，分离与每一个_two_分号。例如：

```
 "Images (*.png *.xpm *.jpg);;Text files (*.txt);;XML files (*.xml)"

```

你可以创建自己的QFileDialog中不使用静态函数。通过调用[setFileMode](qfiledialog.html#fileMode-prop)（ ） ，您可以指定哪些用户必须在对话框中进行选择：

```
 QFileDialog dialog(this);
 dialog.setFileMode(QFileDialog.AnyFile);

```

在上面的例子中，文件对话框的模式被设置为[AnyFile](qfiledialog.html#FileMode-enum)的，这意味着用户可以选择任何文件，甚至指定不存在的文件。这种模式是建立一个“另存为”文件对话框是有用的。使用[ExistingFile](qfiledialog.html#FileMode-enum)如果用户必须选择一个现有的文件，或[Directory](qfiledialog.html#FileMode-enum)如果只有一个目录可能被选中。请参阅[QFileDialog.FileMode](qfiledialog.html#FileMode-enum)枚举类型的模式的完整列表。

该[fileMode](qfiledialog.html#fileMode-prop)属性包含操作对话框的模式，这表示，预计选择什么类型的对象的用户。使用[setNameFilter](qfiledialog.html#setNameFilter)（ ）来设置对话框的文件过滤器。例如：

```
 dialog.setNameFilter(tr("Images (*.png *.xpm *.jpg)"));

```

在上面的例子中，过滤器被设置为`"Images (*.png *.xpm *.jpg)"`，这意味着只有与扩展名的文件`png`，`xpm`或`jpg`将被显示在QFileDialog中进行。您可以通过使用应用多种滤镜[setNameFilters](qfiledialog.html#setNameFilters)（ ） 。使用[selectNameFilter](qfiledialog.html#selectNameFilter)（）来选择你给的文件对话框的缺省过滤器的过滤器之一。

文件对话框有两种视图模式：[List](qfiledialog.html#ViewMode-enum)和[Detail](qfiledialog.html#ViewMode-enum)。[List](qfiledialog.html#ViewMode-enum)介绍了当前目录中的内容作为文件名和目录名的列表。[Detail](qfiledialog.html#ViewMode-enum)还显示文件和目录名的列表，但提供了额外的信息，并排的名字，如文件大小和修改日期。与设定的模式[setViewMode](qfiledialog.html#viewMode-prop)（）：

```
 dialog.setViewMode(QFileDialog.Detail);

```

创建自己的文件对话框时，你将需要使用的最后一个重要的功能是[selectedFiles](qfiledialog.html#selectedFiles)（ ） 。

```
 [QStringList](qstringlist.html) fileNames;
 if (dialog.exec())
     fileNames = dialog.selectedFiles();

```

在上面的示例中，创建并显示一个模式文件对话框。如果用户单击OK（确定） ，他们所选择的文件放在`fileName`。

对话框的工作目录可以被设置[setDirectory](qfiledialog.html#setDirectory)（ ） 。在当前目录下的每个文件可以使用被选择的[selectFile](qfiledialog.html#selectFile)（）函数。

该[Standard Dialogs](index.htm)示例显示了如何使用QFileDialog中以及其他内置Qt对话框。

* * *

## Type Documentation

```
QFileDialog.AcceptMode
```

| Constant | Value |
| --- | --- |
| `QFileDialog.AcceptOpen` | `0` |
| `QFileDialog.AcceptSave` | `1` |

```
QFileDialog.DialogLabel
```

| Constant | Value |
| --- | --- |
| `QFileDialog.LookIn` | `0` |
| `QFileDialog.FileName` | `1` |
| `QFileDialog.FileType` | `2` |
| `QFileDialog.Accept` | `3` |
| `QFileDialog.Reject` | `4` |

```
QFileDialog.FileMode
```

此枚举用于指示哪些用户可以在文件对话框中选择，即如果用户单击OK（确定）对话框将返回什么。

| Constant | Value | Description |
| --- | --- | --- |
| `QFileDialog.AnyFile` | `0` | 一个文件的文件名，无论是否存在。 |
| `QFileDialog.ExistingFile` | `1` | 现有的单个文件的名称。 |
| `QFileDialog.Directory` | `2` | 一个目录的名称。这两个文件和目录都显示出来。 |
| `QFileDialog.ExistingFiles` | `3` | 零个或多个现有文件的名称。 |

这个值是过时的，因为Qt的4.5 ：

| Constant | Value | Description |
| --- | --- | --- |
| `QFileDialog.DirectoryOnly` | `4` | 使用`Directory`和的SetOption （[ShowDirsOnly](qfiledialog.html#Option-enum)，真正的）来代替。 |

**See also** [setFileMode](qfiledialog.html#fileMode-prop)（ ） 。

```
QFileDialog.Option
```

| Constant | Value | Description |
| --- | --- | --- |
| `QFileDialog.ShowDirsOnly` | `0x00000001` | 只显示在文件对话框的目录。默认情况下这两个文件和目录都显示。 （只适用于[Directory](qfiledialog.html#FileMode-enum)文件模式。 ） |
| `QFileDialog.DontResolveSymlinks` | `0x00000002` | 不解决符号链接的文件对话框。默认情况下符号链接都解决了。 |
| `QFileDialog.DontConfirmOverwrite` | `0x00000004` | 不要求确认如果选择现有文件。默认情况下请求确认。 |
| `QFileDialog.DontUseNativeDialog` | `0x00000010` | 不要使用本地文件对话框。默认情况下，使用本地文件对话框，除非你用的子类[QFileDialog](qfiledialog.html)包含[Q_OBJECT](qobject.html#Q_OBJECT)宏。 |
| `QFileDialog.ReadOnly` | `0x00000020` | 表明该模型是只读的。 |
| `QFileDialog.HideNameFilterDetails` | `0x00000040` | 表示如果文件名过滤器的细节被隐藏与否。 |
| `QFileDialog.DontUseSheet` | `0x00000008` | 在Qt的早期版本中，静态函数会默认创建一个表，如果静态函数被赋予了父母。这不再支持和不执行任何操作在Qt的4.5 ，静态函数将永远是一个应用程序的模态对话框。如果你想使用表，使用[QFileDialog.open](qfiledialog.html#open)（ ）来代替。 |

该选项类型是一个typedef为[QFlags](index.htm)\u003cOPTION\u003e 。它存储选项值的一个或组合。

```
QFileDialog.ViewMode
```

这个枚举变量描述文件对话框的视图模式，即什么有关每个文件的信息将被显示。

| Constant | Value | Description |
| --- | --- | --- |
| `QFileDialog.Detail` | `0` | 显示一个图标，名称，详细目录中的每个项目。 |
| `QFileDialog.List` | `1` | 只显示目录中的图标，并为每个项目的名称。 |

**See also** [setViewMode](qfiledialog.html#viewMode-prop)（ ） 。

* * *

## Method Documentation

```
QFileDialog.__init__ (self, QWidget parent, Qt.WindowFlags f)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个文件对话框给定的_parent_和widget_flags_。

```
QFileDialog.__init__ (self, QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString())
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个文件对话框给定的_parent_和_caption_最初显示指定的内容_directory_。该目录中的内容被过滤所示的对话框中之前，使用的过滤器通过指定一个分号分隔的列表_filter_。

```
QFileDialog.accept (self)
```

从重新实现[QDialog.accept](qdialog.html#accept)（ ） 。

```
AcceptMode QFileDialog.acceptMode (self)
```

[

```
QFileDialog.changeEvent (self, QEvent e)
```

](qfiledialog.html#AcceptMode-enum)

[从重新实现](qfiledialog.html#AcceptMode-enum)[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
bool QFileDialog.confirmOverwrite (self)
```

```
QString QFileDialog.defaultSuffix (self)
```

```
QDir QFileDialog.directory (self)
```

[

返回目录当前显示在对话框中。

](qdir.html)

[**See also**](qdir.html) [setDirectory](qfiledialog.html#setDirectory)（ ） 。

```
QFileDialog.done (self, int result)
```

从重新实现[QDialog.done](qdialog.html#done)（ ） 。

```
FileMode QFileDialog.fileMode (self)
```

[](qfiledialog.html#FileMode-enum)

```
QDir.Filters QFileDialog.filter (self)
```

[

返回显示的是文件时所使用的过滤器。

此功能被引入Qt的4.4 。

](index.htm)

[**See also**](index.htm) [setFilter](qfiledialog.html#setFilter)（ ） 。

```
QStringList QFileDialog.filters (self)
```

```
QString QFileDialog.getExistingDirectory (QWidget parent = None, QString caption = QString(), QString directory = QString(), Options options = QFileDialog.ShowDirsOnly)
```

这是一个方便的静态函数将返回由用户选择一个已存在的目录。

```
 [QString](qstring.html) dir = [QFileDialog](qfiledialog.html).getExistingDirectory(this, tr("Open Directory"),
                                                 "/home",
                                                 [QFileDialog](qfiledialog.html).ShowDirsOnly
                                                 | [QFileDialog](qfiledialog.html).DontResolveSymlinks);

```

这个函数创建具有给定一个模式文件对话框_parent_小工具。如果_parent_不为0时，将显示该对话框居中在父窗口部件。

对话框的工作目录设置为_dir_和标题设置为_caption_。无论这些可能是在这种情况下，当前目录和默认的标题将分别使用一个空字符串。

该_options_参数包含有关如何运行对话框中的各种选项，请参阅[QFileDialog.Option](qfiledialog.html#Option-enum)枚举就可以传递标志的更多信息。为确保本地文件对话框，[ShowDirsOnly](qfiledialog.html#Option-enum)必须设置。

在Windows，Mac OS X和Symbian ^ 3系统，这个静态函数将使用本地文件对话框，而不是一个[QFileDialog](qfiledialog.html)。在Windows CE上，如果设备没有本地文件对话框中，[QFileDialog](qfiledialog.html)将被使用。

上UNIX/X11 ，文件对话框的正常行为是解决并按照符号链接。例如，如果`/usr/tmp`是一个符号链接`/var/tmp`，文件对话框将变为`/var/tmp`进入后`/usr/tmp`。如果_options_包括[DontResolveSymlinks](qfiledialog.html#Option-enum)，文件对话框将把符号连接作为常规目录。

在Windows的对话框会打滑阻塞模式的事件循环，不会派遣任何QTimers ，如果_parent_是不是0，那么它将使该对话框下方父的标题栏。

在Symbian ^ 3_options_参数仅用于定义如果使用本地文件对话框。

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QFileDialog](qfiledialog.html)构造函数。

**See also** [getOpenFileName](qfiledialog.html#getOpenFileName)（ ）[getOpenFileNames](qfiledialog.html#getOpenFileNames)（）和[getSaveFileName](qfiledialog.html#getSaveFileName)（ ） 。

```
QString QFileDialog.getOpenFileName (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), Options options = 0)
```

这是一个方便的静态函数，返回由用户选择一个已存在的文件。如果用户按下Cancel ，则返回一个空字符串。

```
 [QString](qstring.html) fileName = [QFileDialog](qfiledialog.html).getOpenFileName(this, tr("Open File"),
                                                 "/home",
                                                 tr("Images (*.png *.xpm *.jpg)"));

```

用给定的函数创建一个样式文件对话框_parent_小工具。如果_parent_不为0时，将显示该对话框居中在父窗口部件。

文件对话框的工作目录将被设置为_dir_。如果_dir_包括一个文件名，该文件将被选中。只有匹配给定的文件_filter_示。选定的过滤器设置为_selectedFilter_。参数_dir_，_selectedFilter_和_filter_可能是空字符串。如果你想多个过滤器，将它们分开，以'; “; ，例如：

```
 "Images (*.png *.xpm *.jpg);;Text files (*.txt);;XML files (*.xml)"

```

该_options_参数包含有关如何运行对话框中的各种选项，请参阅[QFileDialog.Option](qfiledialog.html#Option-enum)枚举就可以传递标志的更多信息。

该对话框的标题设置为_caption_。如果_caption_不指定，那么默认的标题将被使用。

在Windows，Mac OS X和Symbian ^ 3系统，这个静态函数将使用本地文件对话框，而不是一个[QFileDialog](qfiledialog.html)。

在Windows的对话框会打滑阻塞模式的事件循环，不会派遣任何QTimers ，如果_parent_是不是0，那么它将使该对话框下方父的标题栏。

上UNIX/X11 ，文件对话框的正常行为是解决并按照符号链接。例如，如果`/usr/tmp`是一个符号链接`/var/tmp`，文件对话框将变为`/var/tmp`进入后`/usr/tmp`。如果_options_包括[DontResolveSymlinks](qfiledialog.html#Option-enum)，文件对话框将把符号连接作为常规目录。

在Symbian ^ 3的参数_selectedFilter_已经没有任何意义和_options_参数仅用于定义如果使用本地文件对话框。

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QFileDialog](qfiledialog.html)构造函数。

**See also** [getOpenFileNames](qfiledialog.html#getOpenFileNames)（ ）[getSaveFileName](qfiledialog.html#getSaveFileName)（）和[getExistingDirectory](qfiledialog.html#getExistingDirectory)（ ） 。

```
QString QFileDialog.getOpenFileName (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString selectedFilter = None, Options options = 0)
```

```
(QString, QString) QFileDialog.getOpenFileNameAndFilter (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString initialFilter = QString(), Options options = 0)
```

```
QStringList QFileDialog.getOpenFileNames (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), Options options = 0)
```

这是一个方便的静态函数，将返回一个或多个由用户选择现有的文件。

```
 [QStringList](qstringlist.html) files = [QFileDialog](qfiledialog.html).getOpenFileNames(
                         this,
                         "Select one or more files to open",
                         "/home",
                         "Images (*.png *.xpm *.jpg)");

```

这个函数创建具有给定一个模式文件对话框_parent_小工具。如果_parent_不为0时，将显示该对话框居中在父窗口部件。

文件对话框的工作目录将被设置为_dir_。如果_dir_包括一个文件名，该文件将被选中。该过滤器被设置为_filter_使只显示那些匹配过滤文件。选定的过滤器设置为_selectedFilter_。参数_dir_，_selectedFilter_和_filter_可能是空字符串。如果你需要多个过滤器，将它们分开，以'; “; ，例如：

```
 "Images (*.png *.xpm *.jpg);;Text files (*.txt);;XML files (*.xml)"

```

该对话框的标题设置为_caption_。如果_caption_不指定，那么默认的标题将被使用。

在Windows，Mac OS X和Symbian ^ 3系统，这个静态函数将使用本地文件对话框，而不是一个[QFileDialog](qfiledialog.html)。

在Windows的对话框会打滑阻塞模式的事件循环，不会派遣任何QTimers ，如果_parent_是不是0，那么它将使该对话框下方父的标题栏。

上UNIX/X11 ，文件对话框的正常行为是解决并按照符号链接。例如，如果`/usr/tmp`是一个符号链接`/var/tmp`，文件对话框将变为`/var/tmp`进入后`/usr/tmp`。该_options_参数包含有关如何运行对话框中的各种选项，请参阅[QFileDialog.Option](qfiledialog.html#Option-enum)枚举就可以传递标志的更多信息。

**Note:**如果你想遍历文件的列表，你应该遍历一个副本。例如：

```
 [QStringList](qstringlist.html) list = files;
 [QStringList](qstringlist.html).Iterator it = list.begin();
 while(it != list.end()) {
     myProcessing(*it);
     ++it;
 }

```

在Symbian ^ 3的参数_selectedFilter_已经没有任何意义和_options_参数仅用于定义如果使用本地文件对话框。在Symbian ^ 3 ，这个函数只能返回一个文件名。

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QFileDialog](qfiledialog.html)构造函数。

**See also** [getOpenFileName](qfiledialog.html#getOpenFileName)（ ）[getSaveFileName](qfiledialog.html#getSaveFileName)（）和[getExistingDirectory](qfiledialog.html#getExistingDirectory)（ ） 。

```
QStringList QFileDialog.getOpenFileNames (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString selectedFilter = None, Options options = 0)
```

```
(QString, QString) QFileDialog.getOpenFileNamesAndFilter (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString initialFilter = QString(), Options options = 0)
```

```
QString QFileDialog.getSaveFileName (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), Options options = 0)
```

这是一个方便的静态函数将返回由用户选择的文件名。该文件没有存在。

它创建具有给定一个模式文件对话框_parent_小工具。如果_parent_不为0时，将显示该对话框居中在父窗口部件。

```
 [QString](qstring.html) fileName = [QFileDialog](qfiledialog.html).getSaveFileName(this, tr("Save File"),
                            "/home/jana/untitled.png",
                            tr("Images (*.png *.xpm *.jpg)"));

```

文件对话框的工作目录将被设置为_dir_。如果_dir_包括一个文件名，该文件将被选中。只有文件的匹配_filter_示。选定的过滤器设置为_selectedFilter_。参数_dir_，_selectedFilter_和_filter_可能是空字符串。多个过滤器之间用“ ; ”; 。例如：

```
 "Images (*.png *.xpm *.jpg);;Text files (*.txt);;XML files (*.xml)"

```

该_options_参数包含有关如何运行对话框中的各种选项，请参阅[QFileDialog.Option](qfiledialog.html#Option-enum)枚举就可以传递标志的更多信息。

默认的过滤器可以通过设置选择_selectedFilter_到所需的值。

该对话框的标题设置为_caption_。如果_caption_没有被指定，默认字幕将被使用。

在Windows，Mac OS X和Symbian ^ 3系统，这个静态函数将使用本地文件对话框，而不是一个[QFileDialog](qfiledialog.html)。

在Windows的对话框会打滑阻塞模式的事件循环，不会派遣任何QTimers ，如果_parent_是不是0，那么它将使该对话框下方父的标题栏。在Mac OS X ，其本地文件对话框，滤波器参数将被忽略。

上UNIX/X11 ，文件对话框的正常行为是解决并按照符号链接。例如，如果`/usr/tmp`是一个符号链接`/var/tmp`，文件对话框将变为`/var/tmp`进入后`/usr/tmp`。如果_options_包括[DontResolveSymlinks](qfiledialog.html#Option-enum)文件对话框将把符号连接作为常规目录。

在Symbian ^ 3的参数_filter_和_selectedFilter_没有任何意义。该_options_参数仅用于定义如果使用本地文件对话框。

**Warning:**不要删除_parent_在该对话框的执行。如果你想这样做，你应该用一个自己创建的对话框[QFileDialog](qfiledialog.html)构造函数。

**See also** [getOpenFileName](qfiledialog.html#getOpenFileName)（ ）[getOpenFileNames](qfiledialog.html#getOpenFileNames)（）和[getExistingDirectory](qfiledialog.html#getExistingDirectory)（ ） 。

```
QString QFileDialog.getSaveFileName (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString selectedFilter = None, Options options = 0)
```

```
(QString, QString) QFileDialog.getSaveFileNameAndFilter (QWidget parent = None, QString caption = QString(), QString directory = QString(), QString filter = QString(), QString initialFilter = QString(), Options options = 0)
```

```
QStringList QFileDialog.history (self)
```

返回的FileDialog的浏览历史记录作为路径的列表。

**See also** [setHistory](qfiledialog.html#setHistory)（ ） 。

```
QFileIconProvider QFileDialog.iconProvider (self)
```

[

返回所使用的文件对话框的图标提供商。

](qfileiconprovider.html)

[**See also**](qfileiconprovider.html) [setIconProvider](qfiledialog.html#setIconProvider)（ ） 。

```
bool QFileDialog.isNameFilterDetailsVisible (self)
```

```
bool QFileDialog.isReadOnly (self)
```

```
QAbstractItemDelegate QFileDialog.itemDelegate (self)
```

[

返回用于呈现在文件对话框的意见项目的项目委讬。

](qabstractitemdelegate.html)

[**See also**](qabstractitemdelegate.html) [setItemDelegate](qfiledialog.html#setItemDelegate)（ ） 。

```
QString QFileDialog.labelText (self, DialogLabel label)
```

返回在指定的文件对话框上显示的文本_label_。

**See also** [setLabelText](qfiledialog.html#setLabelText)（ ） 。

```
QStringList QFileDialog.nameFilters (self)
```

返回文件类型过滤器，在操作这个文件对话框。

此功能被引入Qt的4.4 。

**See also** [setNameFilters](qfiledialog.html#setNameFilters)（ ） 。

```
QFileDialog.open (self)
```

这是一个重载函数。

此功能连接它的信号之一，由指定的插槽_receiver_和_member_。特定信号取决于是[filesSelected](qfiledialog.html#filesSelected)（）如果[fileMode](qfiledialog.html#fileMode-prop) is [ExistingFiles](qfiledialog.html#FileMode-enum)和[fileSelected](qfiledialog.html#fileSelected)（）如果[fileMode](qfiledialog.html#fileMode-prop)是其他任何东西。

该信号会从插槽中断开时，关闭对话框。

此功能被引入Qt的4.5 。

```
QFileDialog.open (self, QObject receiver, SLOT()SLOT() member)
```

```
QFileDialog.open (self, callable receiver)
```

```
Options QFileDialog.options (self)
```

[](index.htm)

```
QAbstractProxyModel QFileDialog.proxyModel (self)
```

[

返回所使用的文件对话框的代理模型。默认情况下没有代理设置。

](qabstractproxymodel.html)

[**See also**](qabstractproxymodel.html) [setProxyModel](qfiledialog.html#setProxyModel)（ ） 。

```
bool QFileDialog.resolveSymlinks (self)
```

```
bool QFileDialog.restoreState (self, QByteArray state)
```

恢复对话框的布局，历史和当前目录到_state_规定。

通常，这是配合使用[QSettings](qsettings.html)从过去的会话还原大小。

如果有错误，则返回False

此功能被引入Qt的4.3 。

```
QByteArray QFileDialog.saveState (self)
```

[

保存对话框的布局，历史和当前目录的状态。

](qbytearray.html)

[通常，这是配合使用](qbytearray.html)[QSettings](qsettings.html)要记住的大小为今后的会议。版本号码被存储作为数据的一部分。

此功能被引入Qt的4.3 。

```
QStringList QFileDialog.selectedFiles (self)
```

返回包含在对话框中选定的文件的绝对路径的字符串列表。如果没有文件被选中，或模式是不[ExistingFiles](qfiledialog.html#FileMode-enum) or [ExistingFile](qfiledialog.html#FileMode-enum)， selectedFiles （）包含在视口中当前路径。

**See also** [selectedNameFilter](qfiledialog.html#selectedNameFilter)（）和[selectFile](qfiledialog.html#selectFile)（ ） 。

```
QString QFileDialog.selectedFilter (self)
```

```
QString QFileDialog.selectedNameFilter (self)
```

返回用户在文件对话框中选择过滤器。

此功能被引入Qt的4.4 。

**See also** [selectedFiles](qfiledialog.html#selectedFiles)（ ） 。

```
QFileDialog.selectFile (self, QString filename)
```

选择给定的_filename_在文件对话框。

**See also** [selectedFiles](qfiledialog.html#selectedFiles)（ ） 。

```
QFileDialog.selectFilter (self, QString filter)
```

```
QFileDialog.selectNameFilter (self, QString filter)
```

设置当前文件类型_filter_。多个过滤器可以被传递_filter_用分号或空格分隔。

此功能被引入Qt的4.4 。

**See also** [setNameFilter](qfiledialog.html#setNameFilter)（ ）[setNameFilters](qfiledialog.html#setNameFilters)（）和[selectedNameFilter](qfiledialog.html#selectedNameFilter)（ ） 。

```
QFileDialog.setAcceptMode (self, AcceptMode mode)
```

```
QFileDialog.setConfirmOverwrite (self, bool enabled)
```

```
QFileDialog.setDefaultSuffix (self, QString suffix)
```

```
QFileDialog.setDirectory (self, QString directory)
```

设置文件对话框的电流_directory_。

**See also** [directory](qfiledialog.html#directory)（ ） 。

```
QFileDialog.setDirectory (self, QDir adirectory)
```

这是一个重载函数。

```
QFileDialog.setFileMode (self, FileMode mode)
```

```
QFileDialog.setFilter (self, QString filter)
```

设置模型使用的过滤器_filters_。该过滤器是用于指定类型的文件应该被显示。

此功能被引入Qt的4.4 。

**See also** [filter](qfiledialog.html#filter)（ ） 。

```
QFileDialog.setFilter (self, QDir.Filters filters)
```

```
QFileDialog.setFilters (self, QStringList filters)
```

```
QFileDialog.setHistory (self, QStringList paths)
```

设置文件对话框的浏览历史记录包含给定_paths_。

**See also** [history](qfiledialog.html#history)（ ） 。

```
QFileDialog.setIconProvider (self, QFileIconProvider provider)
```

设置使用的文件对话框，以指定的图标提供商_provider_。

**See also** [iconProvider](qfiledialog.html#iconProvider)（ ） 。

```
QFileDialog.setItemDelegate (self, QAbstractItemDelegate delegate)
```

设置用于渲染的意见项目在文件对话框中给定的项目代表_delegate_。

**Warning:**你不应该共享视图之间的委讬的同一实例。否则会导致不正确或不直观的编辑行为，因为在一个给定的委讬每个视图可能会收到[closeEditor()](qabstractitemdelegate.html#closeEditor)信号，并试图访问，修改或关闭一个已经被关闭的编辑器。

注意，所用的模型是[QFileSystemModel](qfilesystemmodel.html)。它具有自定义项目角色的数据，这是由所描述的[Roles](qfilesystemmodel.html#Roles-enum)枚举。您可以使用[QFileIconProvider](qfileiconprovider.html)如果只想自定义图标。

**See also** [itemDelegate](qfiledialog.html#itemDelegate)（ ）[setIconProvider](qfiledialog.html#setIconProvider)（）和[QFileSystemModel](qfilesystemmodel.html)。

```
QFileDialog.setLabelText (self, DialogLabel label, QString text)
```

设置_text_在所指定的文件对话框显示_label_。

**See also** [labelText](qfiledialog.html#labelText)（ ） 。

```
QFileDialog.setNameFilter (self, QString filter)
```

设置在文件对话框中使用的过滤器给定_filter_。

If _filter_包含一对含有一个或多个括号中的**anything*something**，用空格隔开，那么只有包含在括号内的文字被用作过滤器。这意味着，这些电话都是等价的：

```
 dialog.setNameFilter("All C++ files (*.cpp *.cc *.C *.cxx *.c++)");
 dialog.setNameFilter("*.cpp *.cc *.C *.cxx *.c++");

```

此功能被引入Qt的4.4 。

**See also** [setNameFilters](qfiledialog.html#setNameFilters)（ ） 。

```
QFileDialog.setNameFilterDetailsVisible (self, bool enabled)
```

```
QFileDialog.setNameFilters (self, QStringList filters)
```

设置_filters_在文件对话框中使用。

```
 [QStringList](qstringlist.html) filters;
 filters << "Image files (*.png *.xpm *.jpg)"
         << "Text files (*.txt)"
         << "Any files (*)";

 [QFileDialog](qfiledialog.html) dialog(this);
 dialog.setNameFilters(filters);
 dialog.exec_();

```

此功能被引入Qt的4.4 。

**See also** [nameFilters](qfiledialog.html#nameFilters)（ ） 。

```
QFileDialog.setOption (self, Option option, bool on = True)
```

设置给定_option_被启用，如果_on_是真的，否则，清除给定的_option_。

此功能被引入Qt的4.5 。

**See also** [options](qfiledialog.html#options-prop)和[testOption](qfiledialog.html#testOption)（ ） 。

```
QFileDialog.setOptions (self, Options options)
```

```
QFileDialog.setProxyModel (self, QAbstractProxyModel model)
```

该_model_说法有它的所有权转移给Qt的。

该模型提出的意见设置为给定_proxyModel_。如果您要修改的基础模型，这非常有用，例如，添加列，过滤数据或添加驱动器。

任何现有的代理模型将被删除，但不会被删除。文件对话框将采取的所有权_proxyModel_。

此功能被引入Qt的4.3 。

**See also** [proxyModel](qfiledialog.html#proxyModel)（ ） 。

```
QFileDialog.setReadOnly (self, bool enabled)
```

```
QFileDialog.setResolveSymlinks (self, bool enabled)
```

```
QFileDialog.setSidebarUrls (self, list-of-QUrl urls)
```

设置_urls_位于侧边栏的。

例如：

```
     [QList](index.htm)<[QUrl](qurl.html)> urls;
     urls << [QUrl](qurl.html).fromLocalFile("/home/gvatteka/dev/qt-45")
          << [QUrl](qurl.html).fromLocalFile([QDesktopServices](qdesktopservices.html).storageLocation([QDesktopServices](qdesktopservices.html).MusicLocation));

     [QFileDialog](qfiledialog.html) dialog;
     dialog.setSidebarUrls(urls);
     dialog.setFileMode([QFileDialog](qfiledialog.html).AnyFile);
     if(dialog.exec()) {
         // ...
     }

```

文件对话框就会看起来像这样：

![](../img/filedialogurls.png)

此功能被引入Qt的4.3 。

**See also** [sidebarUrls](qfiledialog.html#sidebarUrls)（ ） 。

```
QFileDialog.setViewMode (self, ViewMode mode)
```

```
QFileDialog.setVisible (self, bool visible)
```

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

```
list-of-QUrl QFileDialog.sidebarUrls (self)
```

返回的URL是目前在侧边栏的列表

此功能被引入Qt的4.3 。

**See also** [setSidebarUrls](qfiledialog.html#setSidebarUrls)（ ） 。

```
bool QFileDialog.testOption (self, Option option)
```

返回True如果给定的_option_被启用，否则返回False 。

此功能被引入Qt的4.5 。

**See also** [options](qfiledialog.html#options-prop)和[setOption](qfiledialog.html#setOption)（ ） 。

```
ViewMode QFileDialog.viewMode (self)
```

[

* * *

## Qt Signal Documentation

```
void currentChanged (const QString&)
```

这是该信号的默认超载。

如果当前文件的变化，这个信号被发射的新的文件名作为_path_参数。

](qfiledialog.html#ViewMode-enum)

[**See also**](qfiledialog.html#ViewMode-enum) [filesSelected](qfiledialog.html#filesSelected)（ ） 。

```
void directoryEntered (const QString&)
```

这是该信号的默认超载。

当用户输入这个信号被发射的_directory_。

此功能被引入Qt的4.3 。

```
void fileSelected (const QString&)
```

这是该信号的默认超载。

当选择的变化和对话框被接受，这个信号被发射的（可能为空）选中_file_。

**See also** [currentChanged](qfiledialog.html#currentChanged)（）和[QDialog.Accepted](qdialog.html#DialogCode-enum)。

```
void filesSelected (const QStringList&)
```

这是该信号的默认超载。

当选择的变化和对话框被接受，这个信号被发射用的（可能为空）名单_selected_文件。

**See also** [currentChanged](qfiledialog.html#currentChanged)（）和[QDialog.Accepted](qdialog.html#DialogCode-enum)。

```
void filterSelected (const QString&)
```

这是该信号的默认超载。

当用户选择这个信号被发射的_filter_。

此功能被引入Qt的4.3 。