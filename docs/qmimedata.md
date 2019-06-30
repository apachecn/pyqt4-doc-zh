# QMimeData Class Reference

## [[QtCore](index.htm) module]

该QMimeData类提供一个容器，用于数据记录有关它的MIME类型的信息。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self)`
*   `clear (self)`
*   `QVariant colorData (self)`
*   `QByteArray data (self, QString mimetype)`
*   `QStringList formats (self)`
*   `bool hasColor (self)`
*   `bool hasFormat (self, QString mimetype)`
*   `bool hasHtml (self)`
*   `bool hasImage (self)`
*   `bool hasText (self)`
*   `bool hasUrls (self)`
*   `QString html (self)`
*   `QVariant imageData (self)`
*   `removeFormat (self, QString mimetype)`
*   `QVariant retrieveData (self, QString mimetype, Type preferredType)`
*   `setColorData (self, QVariant color)`
*   `setData (self, QString mimetype, QByteArray data)`
*   `setHtml (self, QString html)`
*   `setImageData (self, QVariant image)`
*   `setText (self, QString text)`
*   `setUrls (self, list-of-QUrl urls)`
*   `QString text (self)`
*   `list-of-QUrl urls (self)`

* * *

## Detailed Description

该QMimeData类提供一个容器，用于数据记录有关它的MIME类型的信息。

QMimeData是用来描述可以存储在信息[clipboard](qclipboard.html)，并经由传输[drag and drop](index.htm)机制。 QMimeData对象，它们与相应的MIME类型保存数据关联起来，以确保信息可以在应用程序之间进行安全转移，并在同一应用程序内各地复制。

通常使用创建QMimeData对象`new`并供给到[QDrag](qdrag.html) or [QClipboard](qclipboard.html)对象。这是为了让Qt的管理他们所使用的内存。

单个QMimeData对象可以使用几种不同的格式的同时存储相同的数据。该[formats](qmimedata.html#formats)（ ）函数返回按优先顺序排列的可用格式的列表。该[data](qmimedata.html#data)（ ）函数返回一个MIME类型相关联的原始数据，并[setData](qmimedata.html#setData)（）允许您设置一个MIME类型的数据。

对于最常见的MIME类型， QMimeData提供方便的功能来访问数据：

| Tester | Getter | Setter | MIME Types |
| --- | --- | --- | --- |
| [hasText](qmimedata.html#hasText)() | [text](qmimedata.html#text)() | [setText](qmimedata.html#setText)() | `text/plain` |
| [hasHtml](qmimedata.html#hasHtml)() | [html](qmimedata.html#html)() | [setHtml](qmimedata.html#setHtml)() | `text/html` |
| [hasUrls](qmimedata.html#hasUrls)() | [urls](qmimedata.html#urls)() | [setUrls](qmimedata.html#setUrls)() | `text/uri-list` |
| [hasImage](qmimedata.html#hasImage)() | [imageData](qmimedata.html#imageData)() | [setImageData](qmimedata.html#setImageData)() | `image/` * |
| [hasColor](qmimedata.html#hasColor)() | [colorData](qmimedata.html#colorData)() | [setColorData](qmimedata.html#setColorData)() | `application/x-color` |

例如，如果你写一个接受URL的小工具拖拽，你最终会编写这样的代码：

```
 void MyWidget.dragEnterEvent([QDragEnterEvent](qdragenterevent.html) *event)
 {
     if (event->mimeData()->hasUrls())
         event->acceptProposedAction();
 }

 void MyWidget.dropEvent([QDropEvent](qdropevent.html) *event)
 {
     if (event->mimeData()->hasUrls()) {
         foreach ([QUrl](qurl.html) url, event->mimeData()->urls()) {
             ...
         }
     }
 }

```

有三种方法用于在QMimeData对象存储自定义数据：

1.  自定义数据可以直接存储在一个QMimeData对象作为[QByteArray](qbytearray.html) using [setData](qmimedata.html#setData)（ ） 。例如：

    ```
     [QByteArray](qbytearray.html) csvData = ...;

     QMimeData *mimeData = new QMimeData;
     mimeData-&gt;setData("text/csv", csvData);

    ```

2.  我们可以继承QMimeData和重新实现[hasFormat](qmimedata.html#hasFormat)（ ）[formats](qmimedata.html#formats)（）和[retrieveData](qmimedata.html#retrieveData)（ ） 。
3.  如果发生在一个单一的应用程序中的拖放操作，我们可以继承QMimeData ，并在其中添加额外的数据，并使用[qobject_cast](qobject.html#qobject_cast)（ ）在接收器的放置事件处理程序。例如：

    ```
     void MyWidget.dropEvent([QDropEvent](qdropevent.html) *event)
     {
         const MyMimeData *myData =
                 qobject_cast&lt;const MyMimeData *&gt;(event-&gt;mimeData());
         if (myData) {
             // access myData's data directly (not through QMimeData's API)
         }
     }

    ```

### Platform-Specific MIME Types

在Windows上，[formats](qmimedata.html#formats)（ ）也将返回的MIME数据可自定义格式，使用`x-qt-windows-mime`亚型，表明它们代表了非标准格式的数据。该格式将采取以下形式：

```
 application/x-qt-windows-mime;value="<custom type>"

```

下面是自定义MIME类型的示例：

```
 application/x-qt-windows-mime;value="FileGroupDescriptor"
 application/x-qt-windows-mime;value="FileContents"

```

该`value`声明的每个格式的描述，其中的数据被编码的方式。

在Windows上， MIME格式并不总是直接映射到剪贴板格式。 Qt提供[QWindowsMime](index.htm)映射的剪贴板格式，打开标准的MIME格式。类似地，[QMacPasteboardMime](index.htm)MIME映射到Mac的口味。

* * *

## Method Documentation

```
QMimeData.__init__ (self)
```

构造一个新的MIME数据对象中没有任何数据。

```
QMimeData.clear (self)
```

删除所有在该对象的MIME类型和数据条目。

```
QVariant QMimeData.colorData (self)
```

返回一个颜色，如果存储在所述对象数据代表颜色（MIME类型`application/x-color`） ，否则返回一个空的变体。

A [QVariant](qvariant.html)被使用，因为[QMimeData](qmimedata.html)属于[QtCore](index.htm)库，而[QColor](qcolor.html)属于[QtGui](index.htm)。若要转换[QVariant](qvariant.html)到[QColor](qcolor.html)，只需使用[qvariant_cast](qvariant.html#qvariant_cast)（ ） 。例如：

```
 if (event->mimeData()->hasColor()) {
     [QColor](qcolor.html) color = qvariant_cast<[QColor](qcolor.html)>(event->mimeData()->colorData());
     ...
 }

```

**See also** [hasColor](qmimedata.html#hasColor)（ ）[setColorData](qmimedata.html#setColorData)（）和[data](qmimedata.html#data)（ ） 。

```
QByteArray QMimeData.data (self, QString mimetype)
```

[

返回存储在该对象中由指定的MIME类型所描述的格式的数据_mimeType_。

](qbytearray.html)

[**See also**](qbytearray.html) [setData](qmimedata.html#setData)（ ） 。

```
QStringList QMimeData.formats (self)
```

返回由对象所支持的格式列表。这是MIME类型的量，对象可以返回合适的数据的列表。在列表中的格式是一个优先顺序。

对于数据的最常见的类型，你可以调用高级功能[hasText](qmimedata.html#hasText)（ ）[hasHtml](qmimedata.html#hasHtml)（ ）[hasUrls](qmimedata.html#hasUrls)（ ）[hasImage](qmimedata.html#hasImage)（）和[hasColor](qmimedata.html#hasColor)（ ）来代替。

**See also** [hasFormat](qmimedata.html#hasFormat)（ ）[setData](qmimedata.html#setData)（）和[data](qmimedata.html#data)（ ） 。

```
bool QMimeData.hasColor (self)
```

返回True如果对象可以返回一个颜色（ MIME类型`application/x-color`），否则返回False 。

**See also** [setColorData](qmimedata.html#setColorData)（ ）[colorData](qmimedata.html#colorData)（）和[hasFormat](qmimedata.html#hasFormat)（ ） 。

```
bool QMimeData.hasFormat (self, QString mimetype)
```

返回True如果对象可以返回的数据由指定的MIME类型_mimeType_否则返回False 。

对于数据的最常见的类型，你可以调用高级功能[hasText](qmimedata.html#hasText)（ ）[hasHtml](qmimedata.html#hasHtml)（ ）[hasUrls](qmimedata.html#hasUrls)（ ）[hasImage](qmimedata.html#hasImage)（）和[hasColor](qmimedata.html#hasColor)（ ）来代替。

**See also** [formats](qmimedata.html#formats)（ ）[setData](qmimedata.html#setData)（）和[data](qmimedata.html#data)（ ） 。

```
bool QMimeData.hasHtml (self)
```

返回True如果对象可以返回的HTML （ MIME类型`text/html`），否则返回False 。

**See also** [setHtml](qmimedata.html#setHtml)（ ）[html](qmimedata.html#html)（）和[hasFormat](qmimedata.html#hasFormat)（ ） 。

```
bool QMimeData.hasImage (self)
```

返回True如果对象可以返回一个图像，否则返回False 。

**See also** [setImageData](qmimedata.html#setImageData)（ ）[imageData](qmimedata.html#imageData)（）和[hasFormat](qmimedata.html#hasFormat)（ ） 。

```
bool QMimeData.hasText (self)
```

返回True如果对象可以返回纯文本（ MIME类型`text/plain`），否则返回False 。

**See also** [setText](qmimedata.html#setText)（ ）[text](qmimedata.html#text)（ ）[hasHtml](qmimedata.html#hasHtml)（）和[hasFormat](qmimedata.html#hasFormat)（ ） 。

```
bool QMimeData.hasUrls (self)
```

返回True如果对象可以返回的URL列表，否则返回False 。

网址对应的MIME类型`text/uri-list`。

**See also** [setUrls](qmimedata.html#setUrls)（ ）[urls](qmimedata.html#urls)（）和[hasFormat](qmimedata.html#hasFormat)（ ） 。

```
QString QMimeData.html (self)
```

返回一个字符串，如果存储在对象中的数据是HTML （ MIME类型`text/html`） ，否则返回一个空字符串。

**See also** [setHtml](qmimedata.html#setHtml)（ ）[hasHtml](qmimedata.html#hasHtml)（）和[setData](qmimedata.html#setData)（ ） 。

```
QVariant QMimeData.imageData (self)
```

返回[QVariant](qvariant.html)存储[QImage](qimage.html)如果该对象可以返回一个图像，否则返回一个空的变体。

A [QVariant](qvariant.html)被使用，因为[QMimeData](qmimedata.html)属于[QtCore](index.htm)库，而[QImage](qimage.html)属于[QtGui](index.htm)。若要转换[QVariant](qvariant.html)到[QImage](qimage.html)，只需使用[qvariant_cast](qvariant.html#qvariant_cast)（ ） 。例如：

```
 if (event->mimeData()->hasImage()) {
     [QImage](qimage.html) image = qvariant_cast<[QImage](qimage.html)>(event->mimeData()->imageData());
     ...
 }

```

**See also** [setImageData](qmimedata.html#setImageData)（）和[hasImage](qmimedata.html#hasImage)（ ） 。

```
QMimeData.removeFormat (self, QString mimetype)
```

删除数据条目_mimeType_在该对象。

此功能被引入Qt的4.4 。

```
QVariant QMimeData.retrieveData (self, QString mimetype, Type preferredType)
```

返回一个变量与给定的_type_包含的数据由指定的MIME类型_mimeType_。如果对象不支持的MIME类型或特定变量类型，则返回一个空的变体来代替。

调用此函数由一般[data](qmimedata.html#data)（ ） getter和通过便捷的getter （[text](qmimedata.html#text)（ ）[html](qmimedata.html#html)（ ）[urls](qmimedata.html#urls)（ ）[imageData](qmimedata.html#imageData)（）和[colorData](qmimedata.html#colorData)（））。您可以重新实现它，如果你想使用一个自定义的数据结构，而不是一个（存储数据[QByteArray](qbytearray.html)，这是[setData](qmimedata.html#setData)（ ）提供） 。那么你就还需要重新实现[hasFormat](qmimedata.html#hasFormat)（）和[formats](qmimedata.html#formats)（ ） 。

**See also** [data](qmimedata.html#data)（ ） 。

```
QMimeData.setColorData (self, QVariant color)
```

在对象的颜色数据设置为给定_color_。

颜色对应的MIME类型`application/x-color`。

**See also** [colorData](qmimedata.html#colorData)（ ）[hasColor](qmimedata.html#hasColor)（）和[setData](qmimedata.html#setData)（ ） 。

```
QMimeData.setData (self, QString mimetype, QByteArray data)
```

设置与由下式给出的MIME类型相关联的数据_mimeType_到指定的_data_。

对于数据的最常见的类型，你可以调用高级功能[setText](qmimedata.html#setText)（ ）[setHtml](qmimedata.html#setHtml)（ ）[setUrls](qmimedata.html#setUrls)（ ）[setImageData](qmimedata.html#setImageData)（）和[setColorData](qmimedata.html#setColorData)（ ）来代替。

请注意，如果你想使用自定义数据类型中的项目视图拖放操作，您必须注册为一个Qt[meta type](qmetatype.html)使用[Q_DECLARE_METATYPE](qmetatype.html#Q_DECLARE_METATYPE)（）宏，并实现流运算符吧。流运营商然后必须与所登记的[qRegisterMetaTypeStreamOperators](qmetatype.html#qRegisterMetaTypeStreamOperators)（）函数。

**See also** [data](qmimedata.html#data)（ ）[hasFormat](qmimedata.html#hasFormat)（ ）[QMetaType](qmetatype.html)和[qRegisterMetaTypeStreamOperators](qmetatype.html#qRegisterMetaTypeStreamOperators)（ ） 。

```
QMimeData.setHtml (self, QString html)
```

Sets _html_作为HTML （ MIME类型`text/html`）用于表示数据。

**See also** [html](qmimedata.html#html)（ ）[hasHtml](qmimedata.html#hasHtml)（ ）[setText](qmimedata.html#setText)（）和[setData](qmimedata.html#setData)（ ） 。

```
QMimeData.setImageData (self, QVariant image)
```

在对象中的数据设置为给定_image_。

A [QVariant](qvariant.html)被使用，因为[QMimeData](qmimedata.html)属于[QtCore](index.htm)库，而[QImage](qimage.html)属于[QtGui](index.htm)。从转换[QImage](qimage.html)至[QVariant](qvariant.html)是隐式的。例如：

```
 mimeData->setImageData([QImage](qimage.html)("beautifulfjord.png"));

```

**See also** [imageData](qmimedata.html#imageData)（ ）[hasImage](qmimedata.html#hasImage)（）和[setData](qmimedata.html#setData)（ ） 。

```
QMimeData.setText (self, QString text)
```

Sets _text_作为纯文本（ MIME类型`text/plain`）用于表示数据。

**See also** [text](qmimedata.html#text)（ ）[hasText](qmimedata.html#hasText)（ ）[setHtml](qmimedata.html#setHtml)（）和[setData](qmimedata.html#setData)（ ） 。

```
QMimeData.setUrls (self, list-of-QUrl urls)
```

设置存储在MIME数据对象通过那些指定的URL_urls_。

网址对应的MIME类型`text/uri-list`。

**See also** [urls](qmimedata.html#urls)（ ）[hasUrls](qmimedata.html#hasUrls)（）和[setData](qmimedata.html#setData)（ ） 。

```
QString QMimeData.text (self)
```

返回一个纯文本（ MIME类型`text/plain`的数据）表示。

**See also** [setText](qmimedata.html#setText)（ ）[hasText](qmimedata.html#hasText)（ ）[html](qmimedata.html#html)（）和[data](qmimedata.html#data)（ ） 。

```
list-of-QUrl QMimeData.urls (self)
```

返回包含MIME数据对象中的URL列表。

网址对应的MIME类型`text/uri-list`。

**See also** [setUrls](qmimedata.html#setUrls)（ ）[hasUrls](qmimedata.html#hasUrls)（）和[data](qmimedata.html#data)（ ） 。