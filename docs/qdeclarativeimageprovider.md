# QDeclarativeImageProvider Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeImageProvider类提供支持像素图和螺纹图像请求在QML的接口。[More...](#details)

### Types

*   `enum ImageType { Image, Pixmap }`

### Methods

*   `__init__ (self, ImageType type)`
*   `__init__ (self, QDeclarativeImageProvider)`
*   `ImageType imageType (self)`
*   `QImage requestImage (self, QString id, QSize size, QSize requestedSize)`
*   `QPixmap requestPixmap (self, QString id, QSize size, QSize requestedSize)`

* * *

## Detailed Description

该QDeclarativeImageProvider类提供支持像素图和螺纹图像请求在QML的接口。

QDeclarativeImageProvider是用来提供在QML应用先进的图像加载功能。它允许在QML图像是：

*   Loaded using QPixmaps rather than actual image files
*   Loaded asynchronously in a separate thread, if [imageType](qdeclarativeimageprovider.html#imageType)() is [ImageType.Image](qdeclarativeimageprovider.html#ImageType-enum)

要指定图像应该通过图像提供商加载，使用**"image:"**方案的图像的URL源，接着通过图像提供者和请求图像的标识符。例如：

```
 [Image](qdeclarativeimageprovider.html#ImageType-enum) { source: "image://myimageprovider/image.png" }

```

这指定图像应该由名为“ myimageprovider ”的形象提供商被加载，并且要加载的图像被命名为“ image.png ” 。根据已通过注册的供应商的QML引擎调用相应的图像提供商[QDeclarativeEngine.addImageProvider](qdeclarativeengine.html#addImageProvider)（ ） 。

请注意，标识符是不区分大小写的，但是URL的其馀部分将被传递与保存情况。例如，下面的代码片段仍然会指定的图像是由一个名为“ myimageprovider ”的形象提供加载，但它会要求不同的图像比上面的代码片段（ “ Image.png ”而不是“ image.png ” ） 。

```
 [Image](qdeclarativeimageprovider.html#ImageType-enum) { source: "image://MyImageProvider/Image.png" }

```

如果你想要的URL的其馀部分是不区分大小写的，你将不得不采取的是自己的形象提供商内部的照顾。

#### An example

这里有两个图像。他们的`source`值表明它们应以命名为“颜色”的图像提供者被加载，并且要加载的图像是“黄色”和“红色” ，分别是：

```
 [Column](index.htm) {
     [Image](qdeclarativeimageprovider.html#ImageType-enum) { source: "image://colors/yellow" }
     [Image](qdeclarativeimageprovider.html#ImageType-enum) { source: "image://colors/red" }
 }

```

当这些图像通过QML加载，它会寻找一个匹配的图像提供者和调用它的[requestImage](qdeclarativeimageprovider.html#requestImage)（）或[requestPixmap](qdeclarativeimageprovider.html#requestPixmap)（）方法（取决于其[imageType](qdeclarativeimageprovider.html#imageType)（））来加载图像。该方法被调用的`id`参数设置为“黄色”的第一映像，而“红色”为第二。

这里是一个图像提供商实现，可以加载由上面的QML要求的图像。此实现动态生成[QPixmap](qpixmap.html)那充满了请求的彩色图像：

```
 class ColorImageProvider : public QDeclarativeImageProvider
 {
 public:
     ColorImageProvider()
         : QDeclarativeImageProvider(QDeclarativeImageProvider.Pixmap)
     {
     }

     [QPixmap](qpixmap.html) requestPixmap(const [QString](qstring.html) &id, [QSize](qsize.html) *size, const [QSize](qsize.html) &requestedSize)
     {
         int width = 100;
         int height = 50;

         if (size)
             *size = [QSize](qsize.html)(width, height);
         [QPixmap](qpixmap.html) pixmap(requestedSize.width() > 0 ? requestedSize.width() : width,
                        requestedSize.height() > 0 ? requestedSize.height() : height);
         pixmap.fill([QColor](qcolor.html)(id).rgba());

         return pixmap;
     }
 };

```

为了使这提供商访问QML ，它注册到QML引擎与“色”的标识符：

```
 int main(int argc, char *argv[])
 {
     ...

     [QDeclarativeEngine](qdeclarativeengine.html) engine;
     engine->addImageProvider(QLatin1String("colors"), new ColorPixmapProvider);

     ...
 }

```

现在，该图像可以成功加载在QML ：

![](../img/imageprovider.png)

一个完整的例子可在Qt的[examples/declarative/cppextensions/imageprovider](index.htm)目录。请注意该示例通过一个注册的供应商[plugin](qdeclarativeextensionplugin.html)而不是注册在应用程序中`main()`功能，如上所示。

#### Asynchronous image loading

支持图片提供商[QImage](qimage.html)自动加载包括对图像的异步加载的支持。要启用异步加载的图像源，设置`asynchronous`属性为`true`的相关[Image](qdeclarativeimageprovider.html#ImageType-enum)，[BorderImage](index.htm) or [AnimatedImage](index.htm)对象。当启用此功能时，图像请求提供商是运行在一个低优先级的线程，让图像加载在后台被执行，并且减少了用户界面的性能影响。

不支持，提供图像提供商异步加载[QPixmap](qpixmap.html)而不是[QImage](qimage.html)值，像素映射只能在主线程中创建的。在这种情况下，如果[asynchronous](index.htm#asynchronous-prop)被设置为`true`，该值将被忽略和图像同步加载。

#### Image caching

由QDeclarativeImageProvider返回图像会自动缓存，类似于由QML引擎加载任何图像。当用“图像:/ / ”前缀的图像被从缓存中加载，[requestImage](qdeclarativeimageprovider.html#requestImage)（）和[requestPixmap](qdeclarativeimageprovider.html#requestPixmap)（ ）不会被调用相关图像提供商。如果图像应始终从图像提供者获取，并且不应该在所有高速缓存中，设置`cache`属性为`false`的相关[Image](qdeclarativeimageprovider.html#ImageType-enum)，[BorderImage](index.htm) or [AnimatedImage](index.htm)对象。

* * *

## Type Documentation

```
QDeclarativeImageProvider.ImageType
```

定义此图像提供商支持的图像类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QDeclarativeImageProvider.Image` | `0` | 图像提供商提供[QImage](qimage.html)图像。该[requestImage](qdeclarativeimageprovider.html#requestImage)（ ）方法会被调用所有的图像请求。 |
| `QDeclarativeImageProvider.Pixmap` | `1` | 图像提供商提供[QPixmap](qpixmap.html)图像。该[requestPixmap](qdeclarativeimageprovider.html#requestPixmap)（ ）方法会被调用所有的图像请求。 |

* * *

## Method Documentation

```
QDeclarativeImageProvider.__init__ (self, ImageType type)
```

创建一个图像提供商，将提供给定的图像_type_。

```
QDeclarativeImageProvider.__init__ (self, QDeclarativeImageProvider)
```

```
ImageType QDeclarativeImageProvider.imageType (self)
```

[

返回此提供程序支持的图像类型。

](qdeclarativeimageprovider.html#ImageType-enum)

```
QImage QDeclarativeImageProvider.requestImage (self, QString id, QSize size, QSize requestedSize)
```

[

实现此方法与返回的图像_id_。默认实现返回一个空的图像。

](qimage.html)

[该_id_是请求的图像源，以“形象： ”方案和提供商的标识去掉。例如，如果图像](qimage.html)[source](index.htm#source-prop)在“图像:/ / MYPROVIDER /图标/家” ，给定的_id_将“图标/家” 。

该_requestedSize_对应于[Image.sourceSize](index.htm#sourceSize-prop)通过图像元素要求。如果_requestedSize_是一个有效的大小，返回的图像应该是大小。

在所有情况下，_size_必须被设置到图像的原始大小。这是用于设置[width](index.htm#width-prop)和[height](index.htm#height-prop)相关的[Image](qdeclarativeimageprovider.html#ImageType-enum)如果这些值没有显式设置。

**Note:**这种方法可以被多个线程调用，因此确保该方法的实现是可重入的。

```
QPixmap QDeclarativeImageProvider.requestPixmap (self, QString id, QSize size, QSize requestedSize)
```

[

实现此方法与返回的像素图_id_。默认实现返回一个空的像素图。

](qpixmap.html)

[该_id_是请求的图像源，以“形象： ”方案和提供商的标识去掉。例如，如果图像](qpixmap.html)[source](index.htm#source-prop)在“图像:/ / MYPROVIDER /图标/家” ，给定的_id_将“图标/家” 。

该_requestedSize_对应于[Image.sourceSize](index.htm#sourceSize-prop)通过图像元素要求。如果_requestedSize_是一个有效的大小，返回的图像应该是大小。

在所有情况下，_size_必须被设置到图像的原始大小。这是用于设置[width](index.htm#width-prop)和[height](index.htm#height-prop)相关的[Image](qdeclarativeimageprovider.html#ImageType-enum)如果这些值没有显式设置。