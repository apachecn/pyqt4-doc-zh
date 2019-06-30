# QWebPage Class Reference

## [[QtWebKit](index.htm) module]

该QWebPage类提供了一个对象来查看和编辑网页文件。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `class **[ChooseMultipleFilesExtensionOption](index.htm)**`
*   `class **[ChooseMultipleFilesExtensionReturn](index.htm)**`
*   `enum ErrorDomain { QtNetwork, Http, WebKit }`
*   `class **[ErrorPageExtensionOption](index.htm)**`
*   `class **[ErrorPageExtensionReturn](index.htm)**`
*   `enum Extension { ChooseMultipleFilesExtension, ErrorPageExtension }`
*   `class **[ExtensionOption](index.htm)**`
*   `class **[ExtensionReturn](index.htm)**`
*   `enum Feature { Notifications, Geolocation }`
*   `enum FindFlag { FindBackward, FindCaseSensitively, FindWrapsAroundDocument, HighlightAllOccurrences }`
*   `class **[FindFlags](index.htm)**`
*   `enum LinkDelegationPolicy { DontDelegateLinks, DelegateExternalLinks, DelegateAllLinks }`
*   `enum NavigationType { NavigationTypeLinkClicked, NavigationTypeFormSubmitted, NavigationTypeBackOrForward, NavigationTypeReload, NavigationTypeFormResubmitted, NavigationTypeOther }`
*   `enum PermissionPolicy { PermissionUnknown, PermissionGrantedByUser, PermissionDeniedByUser }`
*   `class **[ViewportAttributes](index.htm)**`
*   `enum WebAction { NoWebAction, OpenLink, OpenLinkInNewWindow, OpenFrameInNewWindow, ..., CopyImageUrlToClipboard }`
*   `enum WebWindowType { WebBrowserWindow, WebModalDialog }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool acceptNavigationRequest (self, QWebFrame frame, QNetworkRequest request, NavigationType type)`
*   `QAction action (self, WebAction action)`
*   `int bytesReceived (self)`
*   `QString chooseFile (self, QWebFrame originatingFrame, QString oldFile)`
*   `QObject createPlugin (self, QString classid, QUrl url, QStringList paramNames, QStringList paramValues)`
*   `QMenu createStandardContextMenu (self)`
*   `QWebPage createWindow (self, WebWindowType type)`
*   `QWebFrame currentFrame (self)`
*   `bool event (self, QEvent)`
*   `bool extension (self, Extension extension, ExtensionOption option = None, ExtensionReturn output = None)`
*   `bool findText (self, QString subString, FindFlags options = 0)`
*   `bool focusNextPrevChild (self, bool next)`
*   `bool forwardUnsupportedContent (self)`
*   `QWebFrame frameAt (self, QPoint pos)`
*   `bool hasSelection (self)`
*   `QWebHistory history (self)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery property)`
*   `bool isContentEditable (self)`
*   `bool isModified (self)`
*   `javaScriptAlert (self, QWebFrame originatingFrame, QString msg)`
*   `bool javaScriptConfirm (self, QWebFrame originatingFrame, QString msg)`
*   `javaScriptConsoleMessage (self, QString message, int lineNumber, QString sourceID)`
*   `(bool, QString result) javaScriptPrompt (self, QWebFrame originatingFrame, QString msg, QString defaultValue)`
*   `bool javaScriptPrompt (self, QWebFrame originatingFrame, QString msg, QString defaultValue, QString result)`
*   `LinkDelegationPolicy linkDelegationPolicy (self)`
*   `QWebFrame mainFrame (self)`
*   `QNetworkAccessManager networkAccessManager (self)`
*   `QPalette palette (self)`
*   `QWebPluginFactory pluginFactory (self)`
*   `QSize preferredContentsSize (self)`
*   `QString selectedHtml (self)`
*   `QString selectedText (self)`
*   `setActualVisibleContentRect (self, QRect rect)`
*   `setContentEditable (self, bool editable)`
*   `setFeaturePermission (self, QWebFrame frame, Feature feature, PermissionPolicy policy)`
*   `setForwardUnsupportedContent (self, bool forward)`
*   `setLinkDelegationPolicy (self, LinkDelegationPolicy policy)`
*   `setNetworkAccessManager (self, QNetworkAccessManager manager)`
*   `setPalette (self, QPalette palette)`
*   `setPluginFactory (self, QWebPluginFactory factory)`
*   `setPreferredContentsSize (self, QSize size)`
*   `QWebSettings settings (self)`
*   `setView (self, QWidget view)`
*   `setViewportSize (self, QSize size)`
*   `bool shouldInterruptJavaScript (self)`
*   `QStringList supportedContentTypes (self)`
*   `bool supportsContentType (self, QString mimeType)`
*   `bool supportsExtension (self, Extension extension)`
*   `bool swallowContextMenuEvent (self, QContextMenuEvent event)`
*   `int totalBytes (self)`
*   `triggerAction (self, WebAction action, bool checked = False)`
*   `QUndoStack undoStack (self)`
*   `updatePositionDependentActions (self, QPoint pos)`
*   `QString userAgentForUrl (self, QUrl url)`
*   `QWidget view (self)`
*   `ViewportAttributes viewportAttributesForSize (self, QSize availableSize)`
*   `QSize viewportSize (self)`

### Qt Signals

*   `void applicationCacheQuotaExceeded (QWebSecurityOrigin *,quint64)`
*   `void contentsChanged ()`
*   `void databaseQuotaExceeded (QWebFrame *,QString)`
*   `void downloadRequested (const QNetworkRequest&)`
*   `void featurePermissionRequestCanceled (QWebFrame *,QWebPage::Feature)`
*   `void featurePermissionRequested (QWebFrame *,QWebPage::Feature)`
*   `void frameCreated (QWebFrame *)`
*   `void geometryChangeRequested (const QRect&)`
*   `void linkClicked (const QUrl&)`
*   `void linkHovered (const QString&,const QString&,const QString&)`
*   `void loadFinished (bool)`
*   `void loadProgress (int)`
*   `void loadStarted ()`
*   `void menuBarVisibilityChangeRequested (bool)`
*   `void microFocusChanged ()`
*   `void printRequested (QWebFrame *)`
*   `void repaintRequested (const QRect&)`
*   `void restoreFrameStateRequested (QWebFrame *)`
*   `void saveFrameStateRequested (QWebFrame *,QWebHistoryItem *)`
*   `void scrollRequested (int,int,const QRect&)`
*   `void selectionChanged ()`
*   `void statusBarMessage (const QString&)`
*   `void statusBarVisibilityChangeRequested (bool)`
*   `void toolBarVisibilityChangeRequested (bool)`
*   `void unsupportedContent (QNetworkReply *)`
*   `void viewportChangeRequested ()`
*   `void windowCloseRequested ()`

* * *

## Detailed Description

该QWebPage类提供了一个对象来查看和编辑网页文件。

QWebPage持有主框架负责网页内容，设置导航的链接和行动的历史。该类可用于连同[QWebFrame](qwebframe.html)，以提供类似的功能[QWebView](qwebview.html)在一个小部件少的环境。

QWebPage的API非常相似，[QWebView](qwebview.html)，因为你仍然提供了常用的功能，如[action](qwebpage.html#action)（ ）（称为[pageAction](qwebview.html#pageAction)（ ）在[QWebView](qwebview.html)） ，[triggerAction](qwebpage.html#triggerAction)（ ）[findText](qwebpage.html#findText)（）和[settings](qwebpage.html#settings)（ ） 。更多[QWebView](qwebview.html)类似的功能可以在QWebPage的主框架中找到，通过将得到的[mainFrame](qwebpage.html#mainFrame)（）函数。例如，本[load](qwebframe.html#load)（ ）[setUrl](qwebframe.html#url-prop)（）和[setHtml](qwebframe.html#setHtml)（ ）为QWebPage功能都可以通过访问[QWebFrame](qwebframe.html)。

该[loadStarted](qwebpage.html#loadStarted)当页面开始load.The （）信号被发射[loadProgress](qwebpage.html#loadProgress)（）信号，另一方面，是每当该网页的元素完成加载，如嵌入图像，脚本等发出最后，该[loadFinished](qwebpage.html#loadFinished)（ ）信号时，页面内容完全加载，独立执行脚本或页面渲染的发射。它的参数，无论是真或假，指示加载操作是否成功。

### Using QWebPage in a Widget-less Environment

在开始之前画QWebPage对象，你需要通过调用设置视口的大小[setViewportSize](qwebpage.html#viewportSize-prop)（ ） 。然后，调用主框架的渲染功能（[QWebFrame.render](qwebframe.html#render)（））。这方面的一个例子是显示在下面的代码片段。

假设我们有一个`Thumbnail`类，如下所示：

```
 class Thumbnailer : public [QObject](qobject.html)
 {
     Q_OBJECT

 public:
     Thumbnailer(const [QUrl](qurl.html) &url);

 signals:
     void finished();

 private slots:
     void render();

 private:
     QWebPage page;

 };

```

该`Thumbnail`的构造函数接受一个_url_。我们连接我们的QWebPage对象的[loadFinished()](qwebpage.html#loadFinished)信号给我们的私人插槽，`render()`。

```
 Thumbnailer.Thumbnailer(const [QUrl](qurl.html) &url)
 {
     page.mainFrame()->load(url);
     connect(&page, SIGNAL(loadFinished(bool)),
         this, SLOT(render()));
 }

```

该`render()`函数说明我们如何使用QWebPage对象画一个缩略图。

```
 void Thumbnailer.render()
 {
     page.setViewportSize(page.mainFrame()->contentsSize());
     [QImage](qimage.html) image(page.viewportSize(), [QImage](qimage.html).Format_ARGB32);
     [QPainter](qpainter.html) painter(&image);

     page.mainFrame()->render(&painter);
     painter.end();

     [QImage](qimage.html) thumbnail = image.scaled(400, 400);
     thumbnail.save("thumbnail.png");

     emit finished();
 }

```

我们首先通过设置[viewportSize](qwebpage.html#viewportSize-prop)然后我们实例化一个[QImage](qimage.html)反对，`image`与相同尺寸的本[viewportSize](qwebpage.html#viewportSize-prop)。此图像然后作为一个参数传送`painter`。接下来，我们呈现在主框架和其子帧中的内容复制到`painter`。最后，我们保存缩放图像。

* * *

## Type Documentation

```
QWebPage.ErrorDomain
```

这个枚举描述的域[ErrorPageExtensionOption](index.htm)对象（即在发生错误的图层） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebPage.QtNetwork` | `0` | 发生在QtNetwork层中的错误;错误代码的类型是[QNetworkReply.NetworkError](qnetworkreply.html#NetworkError-enum)。 |
| `QWebPage.Http` | `1` | 发生在HTTP层中的错误;错误码是一个HTTP状态代码（见[QNetworkRequest.HttpStatusCodeAttribute](qnetworkrequest.html#Attribute-enum)） 。 |
| `QWebPage.WebKit` | `2` | 该错误是一个内部WebKit的错误。 |

这个枚举被引入或修改的Qt 4.6 。

```
QWebPage.Extension
```

该枚举描述了该页面可以支持的扩展的类型。使用这些扩展之前，您应该确认该扩展支持通过调用[supportsExtension](qwebpage.html#supportsExtension)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebPage.ChooseMultipleFilesExtension` | `0` | 无论是网页支持多文件选择。这个扩展时调用网页内容要求的一个或多个文件名，例如，作为一个“文件上传”按钮，用户点击在多个文件中允许选择一个HTML表单的结果。 |
| `QWebPage.ErrorPageExtension` | `1` | 无论何时加载失败的网页可以提供一个错误页面。 （在Qt的4.6中引入） |

**See also** [ChooseMultipleFilesExtensionOption](index.htm)，[ChooseMultipleFilesExtensionReturn](index.htm)，[ErrorPageExtensionOption](index.htm)和[ErrorPageExtensionReturn](index.htm)。

```
QWebPage.Feature
```

```
QWebPage.FindFlag
```

这个枚举说明可供的选项[findText](qwebpage.html#findText)（）函数。该选项可以是或的结果一起从下面的列表：

| Constant | Value | Description |
| --- | --- | --- |
| `QWebPage.FindBackward` | `1` | 搜索，而不是向前向后。 |
| `QWebPage.FindCaseSensitively` | `2` | 默认情况下，[findText](qwebpage.html#findText)（ ）的作品不区分大小写。指定此选项改变行为，以区分大小写的查找操作。 |
| `QWebPage.FindWrapsAroundDocument` | `4` | 品牌[findText](qwebpage.html#findText)（ ）从文件的开头重新启动，如果年底达到和文本未找到。 |
| `QWebPage.HighlightAllOccurrences` | `8` | 亮点特定字符串的所有现有出现。 （这个值被引入4.6 。 ） |

该FindFlags类型是一个typedef为[QFlags](index.htm)\u003cFindFlag\u003e 。它存储FindFlag值的或组合。

```
QWebPage.LinkDelegationPolicy
```

这个枚举变量定义代表团策略网页可以有激活链接和发光时，[linkClicked](qwebpage.html#linkClicked)（）信号。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebPage.DontDelegateLinks` | `0` | 没有链接委派。相反，[QWebPage](qwebpage.html)尝试处理他们。 |
| `QWebPage.DelegateExternalLinks` | `1` | 当激活链接指向未存储在本地文件系统或等效的文件 - 如Qt的资源系统 - 然后[linkClicked](qwebpage.html#linkClicked)（）被发射。 |
| `QWebPage.DelegateAllLinks` | `2` | 每当一个链接被激活的[linkClicked](qwebpage.html#linkClicked)（）信号被发射。 |

**See also** [QWebPage.linkDelegationPolicy](qwebpage.html#linkDelegationPolicy-prop)。

```
QWebPage.NavigationType
```

这个枚举变量描述了通过链接文件浏览时，浏览可用的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebPage.NavigationTypeLinkClicked` | `0` | 用户点击了一个集中的环节一个环节或按下回报。 |
| `QWebPage.NavigationTypeFormSubmitted` | `1` | 用户激活一个提交按钮的HTML表单。 |
| `QWebPage.NavigationTypeBackOrForward` | `2` | 导航到后退或前进史上的前面显示的文件要求。 |
| `QWebPage.NavigationTypeReload` | `3` | 用户激活重装行动。 |
| `QWebPage.NavigationTypeFormResubmitted` | `4` | HTML表单被提交第二次。 |
| `QWebPage.NavigationTypeOther` | `5` | 使用方法的导航到另一个文档上面没有列出。 |

**See also** [acceptNavigationRequest](qwebpage.html#acceptNavigationRequest)（ ） 。

```
QWebPage.PermissionPolicy
```

```
QWebPage.WebAction
```

该枚举描述，可以在网页上执行的动作的类型。

操作只在产生作用的时候都适用。行动的可用性可以通过检查来确定[isEnabled()](qaction.html#enabled-prop)在返回的行动[action](qwebpage.html#action)（ ） 。

使文字编辑，光标移动，和文本选择操作的一种方法是通过设置[contentEditable](qwebpage.html#contentEditable-prop)为True。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebPage.NoWebAction` | `-1` | 无动作被触发。 |
| `QWebPage.OpenLink` | `0` | 打开当前链接。 |
| `QWebPage.OpenLinkInNewWindow` | `1` | 在新窗口中打开当前链接。 |
| `QWebPage.OpenFrameInNewWindow` | `2` | 复制当前帧在一个新窗口。 |
| `QWebPage.DownloadLinkToDisk` | `3` | 下载当前链接到磁盘上。 |
| `QWebPage.CopyLinkToClipboard` | `4` | 复制当前链接到剪贴板。 |
| `QWebPage.OpenImageInNewWindow` | `5` | 在新窗口中打开高亮显示的图像。 |
| `QWebPage.DownloadImageToDisk` | `6` | 突出显示的图像下载到磁盘。 |
| `QWebPage.CopyImageToClipboard` | `7` | 突出显示的图像复制到剪贴板。 |
| `QWebPage.CopyImageUrlToClipboard` | `68` | 突出显示的图像的URL复制到剪贴板。 |
| `QWebPage.Back` | `8` | 导航回导航链接的历史。 |
| `QWebPage.Forward` | `9` | 向前导航的导航链接的历史。 |
| `QWebPage.Stop` | `10` | 停止加载当前页面。 |
| `QWebPage.StopScheduledPageRefresh` | `67` | 停止所有挂起的页面刷新/重定向请求。 |
| `QWebPage.Reload` | `11` | 重新载入当前页面。 |
| `QWebPage.ReloadAndBypassCache` | `53` | 重新加载当前页，但不使用任何本地缓存。 （由Qt中4.6 ） |
| `QWebPage.Cut` | `12` | 剪下当前所选复制到剪贴板中的内容。 |
| `QWebPage.Copy` | `13` | 复制当前所选复制到剪贴板中的内容。 |
| `QWebPage.Paste` | `14` | 粘贴内容来自剪贴板。 |
| `QWebPage.Undo` | `15` | 撤销上一次编辑操作。 |
| `QWebPage.Redo` | `16` | 重做上一次编辑操作。 |
| `QWebPage.MoveToNextChar` | `17` | 将光标移动到下一个字符。 |
| `QWebPage.MoveToPreviousChar` | `18` | 将光标移动到前一个字符。 |
| `QWebPage.MoveToNextWord` | `19` | 将光标移动到下一个单词。 |
| `QWebPage.MoveToPreviousWord` | `20` | 将光标移动到前一个单词。 |
| `QWebPage.MoveToNextLine` | `21` | 将光标移动到下一行。 |
| `QWebPage.MoveToPreviousLine` | `22` | 将光标移动到上一行。 |
| `QWebPage.MoveToStartOfLine` | `23` | 将光标移动到该行的开始。 |
| `QWebPage.MoveToEndOfLine` | `24` | 将光标移动到行的结尾。 |
| `QWebPage.MoveToStartOfBlock` | `25` | 将光标移动到该块的开始。 |
| `QWebPage.MoveToEndOfBlock` | `26` | 将光标移动到该块的末端。 |
| `QWebPage.MoveToStartOfDocument` | `27` | 将光标移动到文档的开头。 |
| `QWebPage.MoveToEndOfDocument` | `28` | 将光标移动到该文件的末尾。 |
| `QWebPage.SelectNextChar` | `29` | 选择下一个字符。 |
| `QWebPage.SelectPreviousChar` | `30` | 选择前一个字符。 |
| `QWebPage.SelectNextWord` | `31` | 选择下一个单词。 |
| `QWebPage.SelectPreviousWord` | `32` | 选择前一个字。 |
| `QWebPage.SelectNextLine` | `33` | 选择到下一行。 |
| `QWebPage.SelectPreviousLine` | `34` | 选择到上一行。 |
| `QWebPage.SelectStartOfLine` | `35` | 选择到行的开始。 |
| `QWebPage.SelectEndOfLine` | `36` | 选择到行的结尾。 |
| `QWebPage.SelectStartOfBlock` | `37` | 选择该块的开始。 |
| `QWebPage.SelectEndOfBlock` | `38` | 选择在块的末尾。 |
| `QWebPage.SelectStartOfDocument` | `39` | 选择到文件的开头。 |
| `QWebPage.SelectEndOfDocument` | `40` | 选择该文档的结尾。 |
| `QWebPage.DeleteStartOfWord` | `41` | 删除到单词的开头。 |
| `QWebPage.DeleteEndOfWord` | `42` | 删除该单词的末尾。 |
| `QWebPage.SetTextDirectionDefault` | `43` | 设置文本的方向为默认方向。 |
| `QWebPage.SetTextDirectionLeftToRight` | `44` | 设置文本的方向从左向右。 |
| `QWebPage.SetTextDirectionRightToLeft` | `45` | 设置文本方向从右到左。 |
| `QWebPage.ToggleBold` | `46` | 切换大胆和正常体重的格式。 |
| `QWebPage.ToggleItalic` | `47` | 切换斜体和正常风格之间的格式。 |
| `QWebPage.ToggleUnderline` | `48` | 切换下划线。 |
| `QWebPage.InspectElement` | `49` | 与当前显示的Web检查器高亮显示的HTML元素。 |
| `QWebPage.InsertParagraphSeparator` | `50` | 插入一个新的段落。 |
| `QWebPage.InsertLineSeparator` | `51` | 插入一个新行。 |
| `QWebPage.SelectAll` | `52` | 选择所有内容。 |
| `QWebPage.PasteAndMatchStyle` | `54` | 从剪贴板粘贴内容与目前的风格。 |
| `QWebPage.RemoveFormat` | `55` | 删除格式和样式。 |
| `QWebPage.ToggleStrikethrough` | `56` | 切换删除线和普通样式的格式设置。 |
| `QWebPage.ToggleSubscript` | `57` | 切换下标和基线之间的格式。 |
| `QWebPage.ToggleSuperscript` | `58` | 切换supercript和基线之间的格式。 |
| `QWebPage.InsertUnorderedList` | `59` | 切换有序列表和一个正常的块之间的选择。 |
| `QWebPage.InsertOrderedList` | `60` | 切换有序列表和一个正常的块之间的选择。 |
| `QWebPage.Indent` | `61` | 增加当前选择的格式块的一个增量的压痕。 |
| `QWebPage.Outdent` | `62` | 减少当前选定的格式块的一个增量的压痕。 |
| `QWebPage.AlignCenter` | `63` | 适用于中心对齐内容。 |
| `QWebPage.AlignJustified` | `64` | 适用于充分理由内容。 |
| `QWebPage.AlignLeft` | `65` | 适用于左对齐内容。 |
| `QWebPage.AlignRight` | `66` | 适用于右对齐内容。 |

```
QWebPage.WebWindowType
```

该枚举描述了可以通过创建窗口的类型[createWindow](qwebpage.html#createWindow)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebPage.WebBrowserWindow` | `0` | 该窗口是一个普通的Web浏览器窗口。 |
| `QWebPage.WebModalDialog` | `1` | 该窗口作为模态对话框。 |

* * *

## Method Documentation

```
QWebPage.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空[QWebPage](qwebpage.html)与父_parent_。

```
bool QWebPage.acceptNavigationRequest (self, QWebFrame frame, QNetworkRequest request, NavigationType type)
```

这个函数被调用时[WebKit](qwebpage.html#ErrorDomain-enum)请求导航_frame_由指定的资源_request_通过指定的导航类型的装置_type_。

If _frame_是一个空指针，然后导航到一个新的窗口请求。如果该请求被接受[createWindow](qwebpage.html#createWindow)（ ）将被调用。

默认实现解释页面的[linkDelegationPolicy](qwebpage.html#linkDelegationPolicy-prop)并据此发出linkClicked或返回True ，让[QWebPage](qwebpage.html)处理导航本身。

**See also** [createWindow](qwebpage.html#createWindow)（ ） 。

```
QAction QWebPage.action (self, WebAction action)
```

[](qaction.html)

[返回](qaction.html)[QAction](qaction.html)为指定的[WebAction](qwebpage.html#WebAction-enum) _action_。

该动作由资[QWebPage](qwebpage.html)但是你可以通过改变其属性自定义的外观。

[QWebPage](qwebpage.html)还采取执行行动的护理，使在触发在页面上执行相应的动作。

**See also** [triggerAction](qwebpage.html#triggerAction)（ ） 。

```
int QWebPage.bytesReceived (self)
```

返回从网络中接收到的呈现当前页面的字节数。

**See also** [totalBytes](qwebpage.html#totalBytes)（）和[loadProgress](qwebpage.html#loadProgress)（ ） 。

```
QString QWebPage.chooseFile (self, QWebFrame originatingFrame, QString oldFile)
```

当网页内容请求一个文件名，例如同时对一个HTML表单“文件上传”按钮，用户点击的结果，此函数被调用。

一个建议的文件名可以在提供_suggestedFile_。发出请求的帧被设置为_parentFrame_。

**See also** [ChooseMultipleFilesExtension](qwebpage.html#Extension-enum)。

```
QObject QWebPage.createPlugin (self, QString classid, QUrl url, QStringList paramNames, QStringList paramValues)
```

[](qobject.html)

[这个函数被调用时](qobject.html)[WebKit](qwebpage.html#ErrorDomain-enum)遇到与类型“应用程序/ x - QT-插件”一个HTML object元素。这就是所谓的值无关[QWebSettings.PluginsEnabled](qwebsettings.html#WebAttribute-enum)。该_classid_，_url_，_paramNames_和_paramValues_对应于HTML object元素属性和子元素来配置内嵌的对象。

```
QMenu QWebPage.createStandardContextMenu (self)
```

[

这个函数创建当用户点击网页上用鼠标右键其显示在标准上下文菜单。这是从默认contextMenuEvent （ ）处理函数中调用。在弹出菜单的所有权被传递给调用者。

此功能被引入Qt的4.5 。

](qmenu.html)

```
QWebPage QWebPage.createWindow (self, WebWindowType type)
```

[](qwebpage.html)

[这个函数被调用时](qwebpage.html)[WebKit](qwebpage.html#ErrorDomain-enum)要创造的赋予了新的窗口_type_，因为当一个JavaScript程序请求打开新窗口的文档的例子。

如果可以创建新窗口，新窗口的[QWebPage](qwebpage.html)返回;否则返回空指针。

如果与网页相关的视图是[QWebView](qwebview.html)对象，则默认实现请求转发到[QWebView](qwebview.html)的CreateWindow的（ ）函数，否则返回空指针。

If _type_ is [WebModalDialog](qwebpage.html#WebWindowType-enum)，应用程序必须调用setWindowModality （[Qt.ApplicationModal](qt.html#WindowModality-enum)）上的新窗口。

**Note:**在该情况下，当窗口的创建是由JavaScript的触发，除了重新实现此方法的应用程序还必须设置的JavaScriptCanOpenWindows属性[QWebSettings](qwebsettings.html)为True，以便它被调用。

**See also** [acceptNavigationRequest](qwebpage.html#acceptNavigationRequest)（）和[QWebView.createWindow](qwebview.html#createWindow)（ ） 。

```
QWebFrame QWebPage.currentFrame (self)
```

[

返回框架目前活跃。

](qwebframe.html)

[**See also**](qwebframe.html) [mainFrame](qwebpage.html#mainFrame)（）和[frameCreated](qwebpage.html#frameCreated)（ ） 。

```
bool QWebPage.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QWebPage.extension (self, Extension extension, ExtensionOption option = None, ExtensionReturn output = None)
```

这个虚函数可以在重新实现[QWebPage](qwebpage.html)子类以提供扩展的支持。该_option_参数被作为输入提供给扩展，输出结果可以被存储在_output_。

这个函数的行为由以下因素决定_extension_。该_option_和_output_值通常铸造成相应的类型（例如，[ChooseMultipleFilesExtensionOption](index.htm)和[ChooseMultipleFilesExtensionReturn](index.htm)为[ChooseMultipleFilesExtension](qwebpage.html#Extension-enum)） 。

您可以致电[supportsExtension](qwebpage.html#supportsExtension)（ ）来检查一个扩展是支持的页面。

返回True如果扩展被成功调用，否则返回False 。

**See also** [supportsExtension](qwebpage.html#supportsExtension)（）和[Extension](qwebpage.html#Extension-enum)。

```
bool QWebPage.findText (self, QString subString, FindFlags options = 0)
```

查找指定的字符串，_subString_在该页面中，使用给定的_options_。

如果[HighlightAllOccurrences](qwebpage.html#FindFlag-enum)标志传递，函数将突出存在于页面中的所有事件。所有后续调用将延长的亮点，而不是取代它，以出现新的字符串。

如果[HighlightAllOccurrences](qwebpage.html#FindFlag-enum)标志不通过，该函数将选择的发生，所有后续调用将取代目前出现的下一个。

要清除选择，只传递一个空字符串。

返回True如果_subString_结果发现，否则返回False 。

```
bool QWebPage.focusNextPrevChild (self, bool next)
```

像[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ），它侧重的下一个可获得焦点的网页元素，如果_next_为True，否则前面的元素集中。

返回True如果能找到一个新的聚焦元素，还是假的，如果它不能。

```
bool QWebPage.forwardUnsupportedContent (self)
```

```
QWebFrame QWebPage.frameAt (self, QPoint pos)
```

[

返回框架在给定点_pos_或0 ，如果没有帧在该位置。

此功能被引入Qt的4.6 。

](qwebframe.html)

[**See also**](qwebframe.html) [mainFrame](qwebpage.html#mainFrame)（）和[currentFrame](qwebpage.html#currentFrame)（ ） 。

```
bool QWebPage.hasSelection (self)
```

```
QWebHistory QWebPage.history (self)
```

[

返回一个指针，指向的导航网页视图的历史。

```
QVariant QWebPage.inputMethodQuery (self, Qt.InputMethodQuery property)
```

这种方法所使用的输入方法来查询一组页面的属性，以便能够支持复杂的输入操作方法为周围的文本和reconversions支持。

_property_指定哪些属性进行查询。

](qwebhistory.html)

[**See also**](qwebhistory.html) [QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（ ）[QInputMethodEvent](qinputmethodevent.html)和[QInputContext](qinputcontext.html)。

```
bool QWebPage.isContentEditable (self)
```

```
bool QWebPage.isModified (self)
```

```
QWebPage.javaScriptAlert (self, QWebFrame originatingFrame, QString msg)
```

这个函数被调用当一个JavaScript程序中运行_frame_调用与消息警报（ ）函数_msg_。

默认实现显示信息，_msg_，与QMessageBox.information 。

```
bool QWebPage.javaScriptConfirm (self, QWebFrame originatingFrame, QString msg)
```

这个函数被调用当一个JavaScript程序中运行_frame_该消息调用确认（ ）函数，_msg_。如果用户确认的消息，则返回True ，否则返回False 。

默认实现执行使用QMessageBox.information与查询[QMessageBox.Yes](qmessagebox.html#StandardButton-enum)和[QMessageBox.No](qmessagebox.html#StandardButton-enum)按钮。

```
QWebPage.javaScriptConsoleMessage (self, QString message, int lineNumber, QString sourceID)
```

每当一个JavaScript程序试图打印这个函数被调用_message_到web浏览器的控制台。

例如在发生计算错误的源URL可被提供_sourceID_以及_lineNumber_。

默认实现打印什么。

```
(bool, QString result) QWebPage.javaScriptPrompt (self, QWebFrame originatingFrame, QString msg, QString defaultValue)
```

这个函数被调用当一个JavaScript程序中运行_frame_尝试将提示用户输入。该方案可以提供一个可选的消息，_msg_，以及用于将输入的默认值_defaultValue_。

如果提示已取消用户的实现应该返回False ，否则结果应写入_result_而真正应该返回。如果提示没有被用户取消，实行应返回True ，结果字符串不能为空。

默认实现使用[QInputDialog.getText](qinputdialog.html#getText)（ ） 。

```
bool QWebPage.javaScriptPrompt (self, QWebFrame originatingFrame, QString msg, QString defaultValue, QString result)
```

```
LinkDelegationPolicy QWebPage.linkDelegationPolicy (self)
```

[](qwebpage.html#LinkDelegationPolicy-enum)

```
QWebFrame QWebPage.mainFrame (self)
```

[

返回该页面的主框架。

主框架可访问的子帧的层次结构，并且还需要，如果你想明确地呈现一个网页到一个给定的画家。

](qwebframe.html)

[**See also**](qwebframe.html) [currentFrame](qwebpage.html#currentFrame)（ ） 。

```
QNetworkAccessManager QWebPage.networkAccessManager (self)
```

[](qnetworkaccessmanager.html)

[返回](qnetworkaccessmanager.html)[QNetworkAccessManager](qnetworkaccessmanager.html)这是负责提供这个网络请求[QWebPage](qwebpage.html)。

**See also** [setNetworkAccessManager](qwebpage.html#setNetworkAccessManager)（ ） 。

```
QPalette QWebPage.palette (self)
```

[](qpalette.html)

```
QWebPluginFactory QWebPage.pluginFactory (self)
```

[](qwebpluginfactory.html)

[返回](qwebpluginfactory.html)[QWebPluginFactory](qwebpluginfactory.html)该负责创建插件嵌入到这个[QWebPage](qwebpage.html)。如果没有安装插件工厂则返回空指针。

**See also** [setPluginFactory](qwebpage.html#setPluginFactory)（ ） 。

```
QSize QWebPage.preferredContentsSize (self)
```

[

```
QString QWebPage.selectedHtml (self)
```

```
QString QWebPage.selectedText (self)
```

```
QWebPage.setActualVisibleContentRect (self, QRect rect)
```

```
QWebPage.setContentEditable (self, bool editable)
```

```
QWebPage.setFeaturePermission (self, QWebFrame frame, Feature feature, PermissionPolicy policy)
```

```
QWebPage.setForwardUnsupportedContent (self, bool forward)
```

```
QWebPage.setLinkDelegationPolicy (self, LinkDelegationPolicy policy)
```

```
QWebPage.setNetworkAccessManager (self, QNetworkAccessManager manager)
```

](qsize.html)

[设置](qsize.html)[QNetworkAccessManager](qnetworkaccessmanager.html) _manager_负责提供该网络的请求[QWebPage](qwebpage.html)。

**Note:**它目前不支持后更改网络访问管理器[QWebPage](qwebpage.html)已使用过它。这样做的结果是不确定的。

**See also** [networkAccessManager](qwebpage.html#networkAccessManager)（ ） 。

```
QWebPage.setPalette (self, QPalette palette)
```

```
QWebPage.setPluginFactory (self, QWebPluginFactory factory)
```

设置[QWebPluginFactory](qwebpluginfactory.html) _factory_负责创建插件嵌入到这个[QWebPage](qwebpage.html)。

注：该插件工厂仅用于本[QWebSettings.PluginsEnabled](qwebsettings.html#WebAttribute-enum)属性被启用。

**See also** [pluginFactory](qwebpage.html#pluginFactory)（ ） 。

```
QWebPage.setPreferredContentsSize (self, QSize size)
```

```
QWebSettings QWebPage.settings (self)
```

[

返回一个指向该页面的设置对象。

](qwebsettings.html)

[**See also**](qwebsettings.html) [QWebSettings.globalSettings](qwebsettings.html#globalSettings)（ ） 。

```
QWebPage.setView (self, QWidget view)
```

设置_view_与该网页相关联。

**See also** [view](qwebpage.html#view)（ ） 。

```
QWebPage.setViewportSize (self, QSize size)
```

```
bool QWebPage.shouldInterruptJavaScript (self)
```

这种方法也是一个Qt槽与C + +的签名`bool shouldInterruptJavaScript()`。

当一个JavaScript程序运行的很长一段时间调用此函数。

如果用户想停止执行JavaScript应返回True ，否则返回False 。

默认实现执行使用QMessageBox.information与查询[QMessageBox.Yes](qmessagebox.html#StandardButton-enum)和[QMessageBox.No](qmessagebox.html#StandardButton-enum)按钮。

**Warning:**因为二进制兼容性的限制，这个功能是不是虚拟的。如果你想提供自己的实现在[QWebPage](qwebpage.html)子类，重新实现shouldInterruptJavaScript （）槽在你的子类来代替。[QtWebKit](index.htm)将动态检测插槽，并调用它。

此功能被引入Qt的4.6 。

```
QStringList QWebPage.supportedContentTypes (self)
```

返回所支持的所有内容类型的列表[QWebPage](qwebpage.html)。

```
bool QWebPage.supportsContentType (self, QString mimeType)
```

返回True如果[QWebPage](qwebpage.html)可以处理给定的_mimeType_否则，返回False 。

```
bool QWebPage.supportsExtension (self, Extension extension)
```

这个虚函数返回True ，如果该网页支持_extension_否则返回False。

**See also** [extension](qwebpage.html#extension)（ ） 。

```
bool QWebPage.swallowContextMenuEvent (self, QContextMenuEvent event)
```

过滤器的上下文菜单事件，_event_通过处理程序的滚动条和自定义事件处理程序的网页。返回True如果该事件已经被处理，否则为False 。

一个网页可以通过自定义事件处理程序吞下一个上下文菜单事件，允许上下文菜单在HTML / JavaScript实现。这是由[Google Maps](http://maps.google.com/)，例如。

```
int QWebPage.totalBytes (self)
```

返回从网络中接收到的呈现当前页面的总字节数，包括额外的内容，例如嵌入的图像。

**See also** [bytesReceived](qwebpage.html#bytesReceived)（ ） 。

```
QWebPage.triggerAction (self, WebAction action, bool checked = False)
```

这个功能可以被调用来触发指定_action_。它也被称为由[QtWebKit](index.htm)如果用户通过上下文菜单项触发操作，例如。

If _action_是一个辨认的行动，那么_checked_是否动作翻转或不指定。

**See also** [action](qwebpage.html#action)（ ） 。

```
QUndoStack QWebPage.undoStack (self)
```

[

返回一个指针，用于可编辑内容的撤消堆栈。

](qundostack.html)

[**See also**](qundostack.html) [modified](qwebpage.html#modified-prop)。

```
QWebPage.updatePositionDependentActions (self, QPoint pos)
```

更新取决于位置的页面上的动作_pos_。例如，如果_pos_是在图像元素[CopyImageToClipboard](qwebpage.html#WebAction-enum)动作处于开启状态。

```
QString QWebPage.userAgentForUrl (self, QUrl url)
```

需要对HTTP请求的用户代理时，此函数被调用。您可以重新实现这个函数来动态地返回不同的用户代理的不同的URL的基础上，_url_参数。

默认实现返回以下值：

“ Mozilla/5.0 （ ％台％ ％安全％ ％子平台％ ） AppleWebKit / ％ WebKitVersion ％ （ KHTML ，像壁虎） ％ AppVersion Safari浏览器/ ％ WebKitVersion ％ ”

在移动平台，如Symbian的S60和Maemo ， “移动Safari浏览器”是用来代替“野生动物园” 。

在这个字符串中使用以下值被替换在运行时：

*   %Platform% expands to the windowing system followed by "; " if it is not Windows (e.g. "X11; ").
*   %Security% expands to "N; " if SSL is disabled.
*   %Subplatform% expands to the operating system version (e.g. "Windows NT 6.1" or "Intel Mac OS X 10.5").
*   %WebKitVersion% is the version of [WebKit](qwebpage.html#ErrorDomain-enum) the application was compiled against.
*   %AppVersion% expands to [QCoreApplication.applicationName](qcoreapplication.html#applicationName-prop)()/[QCoreApplication.applicationVersion](qcoreapplication.html#applicationVersion-prop)() if they're set; otherwise defaulting to Qt and the current Qt version.

```
QWidget QWebPage.view (self)
```

[

返回与该网页相关的视图控件。

](qwidget.html)

[**See also**](qwidget.html) [setView](qwebpage.html#setView)（ ） 。

```
ViewportAttributes QWebPage.viewportAttributesForSize (self, QSize availableSize)
```

[

计算给出了最优的视口配置_availableSize_，当用户界面组件被忽视。

配置也依赖于它是自动获得的设备的屏幕尺寸。出于测试目的的大小可以通过设置两个环境变量QTWEBKIT_DEVICE_WIDTH和QTWEBKIT_DEVICE_HEIGHT ，这需要设置两个被复盖。

](index.htm)

[该](index.htm)[ViewportAttributes](index.htm)包括像素密度比，这也将暴露在网络作者虽然 - WebKit的像素比媒体功能。这是1密度无关的像素（DPI）和物理像素之间的比率。

甲密度无关的像素相当于一个160 DPI的屏幕上的一个物理像素，所以在我们的平台假定作为基准密度。

拨码单位转换为屏幕像素是很简单的：

像素= DIP封装* （密度/ 160 ） 。

因此， 240 DPI屏幕上，1个DIP为将等于1.5物理像素。

无效的实例将在一个空的大小传递给方法的情况下返回。

**Note:**密度是从哪里页面被显示在屏幕的DPI自动获得的，但由于许多X11服务器报告错误的DPI ，可以利用来复盖它[QX11Info.setAppDpiY](qx11info.html#setAppDpiY)（ ） 。

```
QSize QWebPage.viewportSize (self)
```

[

* * *

## Qt Signal Documentation

```
void applicationCacheQuotaExceeded (QWebSecurityOrigin *,quint64)
```

这是该信号的默认超载。

这个信号被发射时网站会要求将数据存储到应用程序缓存数据库，databaseName和分配给该网站超出配额。

```
void contentsChanged ()
```

这是该信号的默认超载。

这个信号被发射时在表单元素中的文本变化以及其他可编辑的内容。

此功能被引入Qt的4.5 。

](qsize.html)

[**See also**](qsize.html) [contentEditable](qwebpage.html#contentEditable-prop)，[modified](qwebpage.html#modified-prop)，[QWebFrame.toHtml](qwebframe.html#toHtml)（）和[QWebFrame.toPlainText](qwebframe.html#toPlainText)（ ） 。

```
void databaseQuotaExceeded (QWebFrame *,QString)
```

这是该信号的默认超载。

这个信号被发射时显示在网站上_frame_在问到的数据存储到数据库中_databaseName_以及分配给该网站超出配额。

此功能被引入Qt的4.5 。

**See also** [QWebDatabase](qwebdatabase.html)。

```
void downloadRequested (const QNetworkRequest&)
```

这是该信号的默认超载。

当用户决定下载一个链接，这个信号被发射。链路以及额外的元信息的URL是包含在_request_。

**See also** [unsupportedContent](qwebpage.html#unsupportedContent)（ ） 。

```
void featurePermissionRequestCanceled (QWebFrame *,QWebPage::Feature)
```

这是该信号的默认超载。

```
void featurePermissionRequested (QWebFrame *,QWebPage::Feature)
```

这是该信号的默认超载。

```
void frameCreated (QWebFrame *)
```

这是该信号的默认超载。

每当页创建一个新的这个信号被发射_frame_。

**See also** [currentFrame](qwebpage.html#currentFrame)（ ） 。

```
void geometryChangeRequested (const QRect&)
```

这是该信号的默认超载。

这个信号被发射时的文件要在页面的位置和大小，来改变对_geom_。这可以通过JavaScript发生的例子。

```
void linkClicked (const QUrl&)
```

这是该信号的默认超载。

每当用户点击一个链接，该页面的这个信号被发射[linkDelegationPolicy](qwebpage.html#linkDelegationPolicy-prop)属性设置为处理委讬为指定的链接_url_。

默认情况下没有链接委派，并通过处理[QWebPage](qwebpage.html)代替。

**Note:**这个信号可能将不发射的点击其中的链接使用JavaScript来触发导航。

**See also** [linkHovered](qwebpage.html#linkHovered)（ ） 。

```
void linkHovered (const QString&,const QString&,const QString&)
```

这是该信号的默认超载。

当鼠标悬停在链接这个信号被发射。

_link_包含链接的url。_title_是链接元素的标题，如果它在标记中指定。_textContent_链接元素中提供的文本，例如， HTML锚点标记内的文本。

当鼠标离开链接元素的信号被发射空参数。

**See also** [linkClicked](qwebpage.html#linkClicked)（ ） 。

```
void loadFinished (bool)
```

这是该信号的默认超载。

当网页完成加载内容这个信号被发射。这个信号是脚本执行或页面渲染无关。_ok_将指示负载是否成功，或发生任何错误。

**See also** [loadStarted](qwebpage.html#loadStarted)（）和[ErrorPageExtension](qwebpage.html#Extension-enum)。

```
void loadProgress (int)
```

这是该信号的默认超载。

这个信号被发射的全球进展状态发生变化时。电流值是由所提供_progress_和秤从0到100 ，这是默认范围[QProgressBar](qprogressbar.html)。它积累的所有子帧的变化。

**See also** [bytesReceived](qwebpage.html#bytesReceived)（ ） 。

```
void loadStarted ()
```

这是该信号的默认超载。

当一个页面开始加载内容这个信号被发射。

**See also** [loadFinished](qwebpage.html#loadFinished)（ ） 。

```
void menuBarVisibilityChangeRequested (bool)
```

这是该信号的默认超载。

每当菜单栏的Web浏览器窗口的可见性承载这个信号被发射[QWebPage](qwebpage.html)应改为_visible_。

```
void microFocusChanged ()
```

这是该信号的默认超载。

这个信号被发射时的光标，例如在一个可编辑的表单元素的位置变化。它是用来通知输入方法有关新的屏幕上的位置，其中用户能够输入文字。此信号通常是连接到[QWidget.updateMicroFocus](qwidget.html#updateMicroFocus)（）槽。

```
void printRequested (QWebFrame *)
```

这是该信号的默认超载。

每当页面请求的Web浏览器来打印这个信号被发射_frame_例如，通过JavaScript的`window.print()`打电话。

**See also** [QWebFrame.print](qwebframe.html#print)（）和[QPrintPreviewDialog](qprintpreviewdialog.html)。

```
void repaintRequested (const QRect&)
```

这是该信号的默认超载。

这个信号被发射时这[QWebPage](qwebpage.html)应该被更新。渲染时，它的一个非常有用[QWebPage](qwebpage.html)没有[QWebView](qwebview.html) or [QGraphicsWebView](qgraphicswebview.html)。_dirtyRect_包含需要被更新的区域。粉刷[QWebPage](qwebpage.html)得到[mainFrame](qwebpage.html#mainFrame)（ ）并调用渲染（[QPainter](qpainter.html)* ，常量[QRegion](qregion.html)＆）方法与_dirtyRect_作为第二个参数。

**See also** [mainFrame](qwebpage.html#mainFrame)（）和[view](qwebpage.html#view)（ ） 。

```
void restoreFrameStateRequested (QWebFrame *)
```

这是该信号的默认超载。

这个信号被发射时的负荷_frame_完成后，应用程序现在可以相应地更新其状态。

此功能被引入Qt的4.5 。

```
void saveFrameStateRequested (QWebFrame *,QWebHistoryItem *)
```

这是该信号的默认超载。

在导航页面的历史前不久这个信号被发射_frame_导航回在记录时被改变，例如。

提供[QWebHistoryItem](qwebhistoryitem.html)，_item_持有该帧的改变之前的历史记录条目。

一个潜在的用例这个信号是存储自定义数据的[QWebHistoryItem](qwebhistoryitem.html)相关联的帧，利用[QWebHistoryItem.setUserData](qwebhistoryitem.html#setUserData)（ ） 。

此功能被引入Qt的4.5 。

```
void scrollRequested (int,int,const QRect&)
```

这是该信号的默认超载。

每当含量由下式给出这个信号被发射_rectToScroll_需要滚动_dx_和_dy_向下，没有视图设置。

**See also** [view](qwebpage.html#view)().

```
void selectionChanged ()
```

这是该信号的默认超载。

这个信号被发射时的选择发生变化，以交互方式或编程方式（如通过调用[triggerAction](qwebpage.html#triggerAction)（）与选择操作）。

**See also** [selectedText](qwebpage.html#selectedText-prop)（ ） 。

```
void statusBarMessage (const QString&)
```

这是该信号的默认超载。

这个信号被发射时，状态栏_text_由页改变。

```
void statusBarVisibilityChangeRequested (bool)
```

这是该信号的默认超载。

每当状态栏的Web浏览器窗口的可见性承载这个信号被发射[QWebPage](qwebpage.html)应改为_visible_。

```
void toolBarVisibilityChangeRequested (bool)
```

这是该信号的默认超载。

每当工具栏上的Web浏览器窗口的可见性承载这个信号被发射[QWebPage](qwebpage.html)应改为_visible_。

```
void unsupportedContent (QNetworkReply *)
```

这是该信号的默认超载。

这个信号被发射时[WebKit](qwebpage.html#ErrorDomain-enum)无法处理用户导航到或Web服务器的响应包括与'附件'指令一个“内容处置”标题中的链接。如果“内容处置”存在于_reply_， web服务器，指示客户端应提示用户不管内容类型来保存内容。请参见RFC 2616 19.5.1节有关内容处置的细节。

在信号发射时间的元数据[QNetworkReply](qnetworkreply.html) _reply_是可用的。

**Note:**在接收时隙是负责删除[QNetworkReply](qnetworkreply.html) _reply_。

**Note:**此信号仅当发射[forwardUnsupportedContent](qwebpage.html#forwardUnsupportedContent-prop)属性设置为True。

**See also** [downloadRequested](qwebpage.html#downloadRequested)（ ） 。

```
void viewportChangeRequested ()
```

这是该信号的默认超载。

页面作者可以通过使用viewport meta标籤提供的提供的值。关于这方面的更多信息可以在这里找到 [Safari Reference Library: Using the Viewport Meta Tag](http://developer.apple.com/safari/library/documentation/appleapplications/reference/safariwebcontent/usingtheviewport/usingtheviewport.html)。

此功能被引入Qt的4.8 。

**See also** [QWebPage.ViewportAttributes](index.htm)，[setPreferredContentsSize](qwebpage.html#preferredContentsSize-prop)（）和[QGraphicsWebView.setScale](qgraphicsitem.html#setScale)（ ） 。

```
void windowCloseRequested ()
```

这是该信号的默认超载。

每当页面请求的Web浏览器窗口，通过JavaScript的关闭，例如这个信号被发射`window.close()`打电话。