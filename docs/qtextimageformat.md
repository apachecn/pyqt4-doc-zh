# QTextImageFormat Class Reference

## [[QtGui](index.htm) module]

The QTextImageFormat class provides formatting information for images in a [QTextDocument](qtextdocument.html). [More...](#details)

继承[QTextCharFormat](qtextcharformat.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextImageFormat)`
*   `float height (self)`
*   `bool isValid (self)`
*   `QString name (self)`
*   `setHeight (self, float aheight)`
*   `setName (self, QString aname)`
*   `setWidth (self, float awidth)`
*   `float width (self)`

* * *

## Detailed Description

该QTextImageFormat类提供的格式设置信息的图像[QTextDocument](qtextdocument.html)。

内嵌图像是由一个对象替换字符（ 0xFFFC以Unicode ），其中有一个相关的QTextImageFormat表示。图像格式指定一个名字[setName](qtextimageformat.html#setName)（） ，用于定位该图像。使用指定的矩形的大小，图像将被佔用[setWidth](qtextimageformat.html#setWidth)（）和[setHeight](qtextimageformat.html#setHeight)（ ） 。

图像可以在为其Qt的图像读取任何格式提供的，因此SVG图形可以包括一起PNG，TIFF等位图格式。

* * *

## Method Documentation

```
QTextImageFormat.__init__ (self)
```

创建一个新的图像格式的对象。

```
QTextImageFormat.__init__ (self, QTextImageFormat)
```

```
float QTextImageFormat.height (self)
```

返回由图像所佔据的矩形的高度。

**See also** [width](qtextimageformat.html#width)（）和[setHeight](qtextimageformat.html#setHeight)（ ） 。

```
bool QTextImageFormat.isValid (self)
```

返回True如果图像格式是有效的，否则返回False 。

```
QString QTextImageFormat.name (self)
```

返回图像的名称。这个名字是指在应用程序的资源文件中的条目。

**See also** [setName](qtextimageformat.html#setName)（ ） 。

```
QTextImageFormat.setHeight (self, float aheight)
```

设置_height_由图像所佔据的矩形。

**See also** [height](qtextimageformat.html#height)（）和[setWidth](qtextimageformat.html#setWidth)（ ） 。

```
QTextImageFormat.setName (self, QString aname)
```

设置_name_的图像。该_name_用来定位图像中的应用程序的资源。

**See also** [name](qtextimageformat.html#name)（ ） 。

```
QTextImageFormat.setWidth (self, float awidth)
```

设置_width_由图像所佔据的矩形。

**See also** [width](qtextimageformat.html#width)（）和[setHeight](qtextimageformat.html#setHeight)（ ） 。

```
float QTextImageFormat.width (self)
```

返回由图像所佔据的矩形的宽度。

**See also** [height](qtextimageformat.html#height)（）和[setWidth](qtextimageformat.html#setWidth)（ ） 。