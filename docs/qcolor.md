# QColor Class Reference

## [[QtGui](index.htm) module]

的而QColor类提供基于RGB ， HSV或CMYK值的颜色。[More...](#details)

### Types

*   `enum Spec { Invalid, Rgb, Hsv, Cmyk, Hsl }`

### Methods

*   `__init__ (self, Qt.GlobalColor color)`
*   `__init__ (self, int rgb)`
*   `__init__ (self, QVariant variant)`
*   `__init__ (self)`
*   `__init__ (self, int r, int g, int b, int alpha = 255)`
*   `__init__ (self, QString aname)`
*   `__init__ (self, QColor acolor)`
*   `int alpha (self)`
*   `float alphaF (self)`
*   `int black (self)`
*   `float blackF (self)`
*   `int blue (self)`
*   `float blueF (self)`
*   `QColor convertTo (self, Spec colorSpec)`
*   `int cyan (self)`
*   `float cyanF (self)`
*   `QColor dark (self, int factor = 200)`
*   `QColor darker (self, int factor = 200)`
*   `(int c, int m, int y, int k, int alpha) getCmyk (self)`
*   `(float c, float m, float y, float k, float alpha) getCmykF (self)`
*   `(int h, int s, int l, int alpha) getHsl (self)`
*   `(float h, float s, float l, float alpha) getHslF (self)`
*   `(int h, int s, int v, int alpha) getHsv (self)`
*   `(float h, float s, float v, float alpha) getHsvF (self)`
*   `(int r, int g, int b, int alpha) getRgb (self)`
*   `(float r, float g, float b, float alpha) getRgbF (self)`
*   `int green (self)`
*   `float greenF (self)`
*   `int hslHue (self)`
*   `float hslHueF (self)`
*   `int hslSaturation (self)`
*   `float hslSaturationF (self)`
*   `int hsvHue (self)`
*   `float hsvHueF (self)`
*   `int hsvSaturation (self)`
*   `float hsvSaturationF (self)`
*   `int hue (self)`
*   `float hueF (self)`
*   `bool isValid (self)`
*   `QColor light (self, int factor = 150)`
*   `QColor lighter (self, int factor = 150)`
*   `int lightness (self)`
*   `float lightnessF (self)`
*   `int magenta (self)`
*   `float magentaF (self)`
*   `QString name (self)`
*   `int red (self)`
*   `float redF (self)`
*   `int rgb (self)`
*   `int rgba (self)`
*   `int saturation (self)`
*   `float saturationF (self)`
*   `setAlpha (self, int alpha)`
*   `setAlphaF (self, float alpha)`
*   `setBlue (self, int blue)`
*   `setBlueF (self, float blue)`
*   `setCmyk (self, int c, int m, int y, int k, int alpha = 255)`
*   `setCmykF (self, float c, float m, float y, float k, float alpha = 1)`
*   `setGreen (self, int green)`
*   `setGreenF (self, float green)`
*   `setHsl (self, int h, int s, int l, int alpha = 255)`
*   `setHslF (self, float h, float s, float l, float alpha = 1)`
*   `setHsv (self, int h, int s, int v, int alpha = 255)`
*   `setHsvF (self, float h, float s, float v, float alpha = 1)`
*   `setNamedColor (self, QString name)`
*   `setRed (self, int red)`
*   `setRedF (self, float red)`
*   `setRgb (self, int r, int g, int b, int alpha = 255)`
*   `setRgb (self, int rgb)`
*   `setRgba (self, int rgba)`
*   `setRgbF (self, float r, float g, float b, float alpha = 1)`
*   `Spec spec (self)`
*   `QColor toCmyk (self)`
*   `QColor toHsl (self)`
*   `QColor toHsv (self)`
*   `QColor toRgb (self)`
*   `int value (self)`
*   `float valueF (self)`
*   `int yellow (self)`
*   `float yellowF (self)`

### Static Methods

*   `bool allowX11ColorNames ()`
*   `QStringList colorNames ()`
*   `QColor fromCmyk (int c, int m, int y, int k, int alpha = 255)`
*   `QColor fromCmykF (float c, float m, float y, float k, float alpha = 1)`
*   `QColor fromHsl (int h, int s, int l, int alpha = 255)`
*   `QColor fromHslF (float h, float s, float l, float alpha = 1)`
*   `QColor fromHsv (int h, int s, int v, int alpha = 255)`
*   `QColor fromHsvF (float h, float s, float v, float alpha = 1)`
*   `QColor fromRgb (int rgb)`
*   `QColor fromRgb (int r, int g, int b, int alpha = 255)`
*   `QColor fromRgba (int rgba)`
*   `QColor fromRgbF (float r, float g, float b, float alpha = 1)`
*   `bool isValidColor (QString name)`
*   `setAllowX11ColorNames (bool enabled)`

### Special Methods

*   `bool __eq__ (self, QColor c)`
*   `bool __ne__ (self, QColor c)`

* * *

## Detailed Description

这个类可以醃制。

A [Qt.GlobalColor](qt.html#GlobalColor-enum)可用于每当一个[QColor](qcolor.html)预计。

的而QColor类提供基于RGB ， HSV或CMYK值的颜色。

颜色是在RGB（红色，绿色和蓝色）分量方面通常指定的，但它也可能在HSV （色调，饱和度和值）和CMYK方面指定（青色，洋红色，黄色和黑色）组件。在另外一个颜色可以使用颜色名称来指定。颜色名称可以是任何的SVG 1.0颜色名称。

| RGB | HSV | CMYK |
| --- | --- | --- |
| ![](../img/qcolor-rgb.png) | ![](../img/qcolor-hsv.png) | ![](../img/qcolor-cmyk.png) |

基于RGB值，而QColor构造函数创建的颜色。要创建基于两种HSV或CMYK值而QColor ，使用[toHsv](qcolor.html#toHsv)（）和[toCmyk](qcolor.html#toCmyk)（ ）分别为功能。这些函数返回使用所需格式的颜色的副本。除了静态[fromRgb](qcolor.html#fromRgb)（ ）[fromHsv](qcolor.html#fromHsv)（）和[fromCmyk](qcolor.html#fromCmyk)（ ）函数从指定的值来创建颜色。可替换地，颜色可以被转换为任何使用三种格式的[convertTo](qcolor.html#convertTo)（）函数（返回所需格式的彩色复印件） ，或任何[setRgb](qcolor.html#setRgb)（ ）[setHsv](qcolor.html#setHsv)（）和[setCmyk](qcolor.html#setCmyk)（ ）函数改变_this_颜色的格式。该[spec](qcolor.html#spec)（ ）函数告诉的颜色是如何规定的。

颜色可以通过传递一个RGB字符串（如“ ＃ 112233 ” ） ，或颜色名称（如“蓝” ） ，到被设置[setNamedColor](qcolor.html#setNamedColor)（）函数。颜色名称取自SVG 1.0颜色名称。该[name](qcolor.html#name)（ ）函数返回的格式为“＃RRGGBB ”颜色的名字。颜色也可以通过使用设置[setRgb](qcolor.html#setRgb)（ ）[setHsv](qcolor.html#setHsv)（）和[setCmyk](qcolor.html#setCmyk)（ ） 。为了得到一个较亮或较暗的颜色使用[lighter](qcolor.html#lighter)（）和[darker](qcolor.html#darker)（ ）分别为功能。

该[isValid](qcolor.html#isValid)（ ）函数表示而QColor是否是合法的。例如， RGB颜色与RGB值超出范围是违法的。出于性能原因，而QColor大多无视非法的颜色，因为这个原因，使用了无效的颜色的结果是不确定的。

色分量可分别被检索，例如，使用[red](qcolor.html#red)（ ）[hue](qcolor.html#hue)（）和[cyan](qcolor.html#cyan)（ ） 。也可以使用检索一气呵成的颜色分量的值的[getRgb](qcolor.html#getRgb)（ ）[getHsv](qcolor.html#getHsv)（）和[getCmyk](qcolor.html#getCmyk)（）函数。使用RGB颜色模型中，颜色分量，另外可以与访问[rgb](qcolor.html#rgb)（ ） 。

有几个相关的非会员：[QRgb](qcolor.html#QRgb-typedef)是typdef为一个unsigned int表示的RGB值三元（ R， G，B ） 。请注意，它也可以容纳的alpha通道的值（有关详细信息，请参阅[Alpha-Blended Drawing](#alpha-blended-drawing)节）。该[qRed](index.htm#qRed)（ ）[qBlue](index.htm#qBlue)（）和[qGreen](index.htm#qGreen)（ ）函数返回给定的相应组件[QRgb](qcolor.html#QRgb-typedef)值，而[qRgb](index.htm#qRgb)（）和[qRgba](index.htm#qRgba)（ ）函数创建并返回[QRgb](qcolor.html#QRgb-typedef)根据给定的元件值三元组。最后，该[qAlpha](index.htm#qAlpha)（ ）函数返回所提供的alpha分量[QRgb](qcolor.html#QRgb-typedef)和[qGray](index.htm#qGray)（）函数计算并返回基于给定值的灰度值。

而QColor是平台和设备无关。该[QColormap](index.htm)类的颜色映射到硬件。

有关油画一般的详细信息，请参阅[Paint System](index.htm)文档。

### Integer vs. Floating Point Precision

而QColor支持浮点精度，并提供所有的颜色分量函数的浮点版本，例如：[getRgbF](qcolor.html#getRgbF)（ ）[hueF](qcolor.html#hueF)（）和[fromCmykF](qcolor.html#fromCmykF)（ ） 。注意，由于该部件在使用16位整数存储，有可能是使用例如设置的值之间的微小偏差，[setRgbF](qcolor.html#setRgbF)（）和由返回的值[getRgbF](qcolor.html#getRgbF)（ ）函数由于四舍五入。

而整数根据功能需要在0-255范围内的值（除[hue](qcolor.html#hue)（），它必须在0-359范围内的值） ，浮点函数接受的范围值0.0 - 1.0 。

### Alpha-Blended Drawing

而QColor还支持alpha混合大纲和灌装。颜色的Alpha通道指定了透明效果， 0表示完全透明的颜色，而255表示完全不透明的颜色。例如：

```
 // Specify semi-transparent red
 painter.setBrush(QColor(255, 0, 0, 127));
 painter.drawRect(0, 0, width()/2, height());

 // Specify semi-transparent blue
 painter.setBrush(QColor(0, 0, 255, 127));
 painter.drawRect(0, 0, width(), height()/2);

```

上面的代码将产生以下输出：

![](../img/alphafill.png)

Alpha混合绘图支持在Windows，Mac OS X和在具有在X渲染扩展安装X11系统。

颜色的Alpha通道可以检索和使用设置[alpha](qcolor.html#alpha)（）和[setAlpha](qcolor.html#setAlpha)如果（）函数的值是一个整数，并[alphaF](qcolor.html#alphaF)（）和[setAlphaF](qcolor.html#setAlphaF)（ ）如果它的值是QREAL （双） 。默认情况下， alpha通道被设置为255 （不透明） 。检索和设置_all_RGB颜色组件（包括Alpha通道）一气呵成，使用[rgba](qcolor.html#rgba)（）和[setRgba](qcolor.html#setRgba)（）函数。

### Predefined Colors

有由所描述的20预定QColors[Qt.GlobalColor](qt.html#GlobalColor-enum)枚举，包括黑色，白色，小学和中学的颜色，颜色较深的版本的这些颜色和三种深浅灰色的。而QColor还认识了各种颜色的名称;静[colorNames](qcolor.html#colorNames)（ ）函数返回一个[QStringList](qstringlist.html)颜色的名称而QColor知道。

![Qt Colors](../img/qt-colors.png)

此外，该[Qt.color0](qt.html#GlobalColor-enum)，[Qt.color1](qt.html#GlobalColor-enum)和[Qt.transparent](qt.html#GlobalColor-enum)颜色用于特殊用途。

[Qt.color0](qt.html#GlobalColor-enum)（零像素值），并[Qt.color1](qt.html#GlobalColor-enum)（非零像素值）是特殊的颜色用于QBitmaps绘制。与绘画[Qt.color0](qt.html#GlobalColor-enum)设置位图位为0（透明的，也就是说，背景） ，并用绘画[Qt.color1](qt.html#GlobalColor-enum)设置比特为1（不透明，即，前景） 。

[Qt.transparent](qt.html#GlobalColor-enum)用于指示一个透明像素。当用该值画，像素值将被使用适合于所使用的底层像素格式。

### The HSV Color Model

RGB模式是面向硬件。其代表性接近大多数显示器显示。与此相反， HSV表示的方式更适合于人的感知颜色的颜色。例如，关系“强于”，“比暗” ，和“相反的”容易地表达在HSV但更难于RGB来表示。

单纯疱疹病毒，如RGB ，有三个组成部分：

*   H, for hue, is in the range 0 to 359 if the color is chromatic (not gray), or meaningless if it is gray. It represents degrees on the color wheel familiar to most people. Red is 0 (degrees), green is 120, and blue is 240.

    ![](../img/qcolor-hue.png)

*   S, for saturation, is in the range 0 to 255, and the bigger it is, the stronger the color is. Grayish colors have saturation near 0; very strong colors have saturation near 255.

    ![](../img/qcolor-saturation.png)

*   V, for value, is in the range 0 to 255 and represents lightness or brightness of the color. 0 is black; 255 is as far from black as possible.

    ![](../img/qcolor-value.png)

下面是一些例子：纯红色是H = 0 ， S = 255 ，V = 255 ;暗红色，稍走向洋红色，可为H = 350 （相当于-10 ） ， S = 255 ，V = 180 ;一个浅灰色的淡红色可配H约0 （比如350-359或0-10） ，S 50-100 ，和S = 255 。

Qt的返回无彩色-1的色调值。如果你传递一个色调值过大， Qt的强制它进入范围。顺化360或720被视为0 ;色相540被视为180 。

除了标准的HSV模型， Qt提供了一个alpha通道，以功能[alpha-blended drawing](#alpha-blended-drawing)。

### The HSL Color Model

HSL类似于单纯疱疹病毒。而不是从HSV值参数， HSL具有亮度参数。亮度参数去从黑色到颜色，从颜色为白色。如果你在晚上的黑色或暗灰色到外面去。在一天其丰富多彩的，但如果你看一下在一个真正强大的光的事情，他们要白洗了。

### The CMYK Color Model

而RGB和HSV颜色模型用于显示在电脑萤幕上， CMYK模型是用在印刷机和一些硬拷贝设备的四色印刷工艺。

CMYK四部分组成，全部在范围0-255 ：青色（C ） ，品红（M ） ，黄色（Y）和黑色（K ） 。青色，品红色和黄色的被称为减色; CMYK颜色模型由开始的白色表面，然后通过应用适当的部件中减去颜色产生的颜色。同时结合青色，品红色和黄色给人的色黑，减去一个或多个将产生的任何其他颜色。当在不同的百分比相结合，这三种颜色可以创造颜色的整个频谱。

将100 ％的青色，品红和黄色_does_产生黑色，但结果并不理想，因为它浪费墨水，增加了干燥时间，并且在打印时给出了一个泥泞的颜色。出于这个原因，黑是专业的印刷加提供了坚实的黑色调，因此称为“四色” 。

除了标准的CMYK模型， Qt提供了一个alpha通道，以功能[alpha-blended drawing](#alpha-blended-drawing)。

* * *

## Type Documentation

```
QColor.Spec
```

指定颜色的类型，可以是RGB ， HSV ， CMYK或HSL 。

| Constant | Value |
| --- | --- |
| `QColor.Rgb` | `1` |
| `QColor.Hsv` | `2` |
| `QColor.Cmyk` | `3` |
| `QColor.Hsl` | `4` |
| `QColor.Invalid` | `0` |

**See also** [spec](qcolor.html#spec)（）和[convertTo](qcolor.html#convertTo)（ ） 。

* * *

## Method Documentation

```
QColor.__init__ (self, Qt.GlobalColor color)
```

构建了一个无效的颜色的RGB值（0，0 ，0）。无效的颜色是没有正确设置为底层窗口系统的颜色。

无效的颜色的Alpha值是不确定的。

**See also** [isValid](qcolor.html#isValid)（ ） 。

```
QColor.__init__ (self, int rgb)
```

构造一个具有RGB值的颜色_r_，_g_，_b_和的alpha通道（透明度）值_a_。

颜色是左无效的，如果任何参数是无效的。

**See also** [setRgba](qcolor.html#setRgba)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor.__init__ (self, QVariant variant)
```

构造一个颜色的值_color_。 alpha组件将被忽略并设置为固体。

**See also** [fromRgb](qcolor.html#fromRgb)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor.__init__ (self)
```

构造一个命名的颜色以同样的方式为[setNamedColor](qcolor.html#setNamedColor)（）用给定的_name_。

颜色是左无效的，如果_name_不能被解析。

**See also** [setNamedColor](qcolor.html#setNamedColor)（ ）[name](qcolor.html#name)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor.__init__ (self, int r, int g, int b, int alpha = 255)
```

构造一个命名的颜色以同样的方式为[setNamedColor](qcolor.html#setNamedColor)（）用给定的_name_。

颜色是左无效的，如果_name_不能被解析。

**See also** [setNamedColor](qcolor.html#setNamedColor)（ ）[name](qcolor.html#name)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor.__init__ (self, QString aname)
```

构造一个颜色，是副本_color_。

**See also** [isValid](qcolor.html#isValid)（ ） 。

```
QColor.__init__ (self, QColor acolor)
```

```
bool QColor.allowX11ColorNames ()
```

返回True如果[setNamedColor](qcolor.html#setNamedColor)（ ）是允许查找颜色的X11颜色数据库。默认情况下，这个函数返回False 。

**Note:**此功能仅可在X11平台上。

**See also** [setAllowX11ColorNames](qcolor.html#setAllowX11ColorNames)（ ） 。

```
int QColor.alpha (self)
```

返回此颜色的Alpha颜色分量。

**See also** [setAlpha](qcolor.html#setAlpha)（ ）[alphaF](qcolor.html#alphaF)（）和[Alpha-Blended Drawing](qcolor.html#alpha-blended-drawing)。

```
float QColor.alphaF (self)
```

返回此颜色的Alpha颜色分量。

**See also** [setAlphaF](qcolor.html#setAlphaF)（ ）[alpha](qcolor.html#alpha)（）和[Alpha-Blended Drawing](qcolor.html#alpha-blended-drawing)。

```
int QColor.black (self)
```

返回该颜色的黑色成分。

**See also** [blackF](qcolor.html#blackF)（ ）[getCmyk](qcolor.html#getCmyk)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
float QColor.blackF (self)
```

返回该颜色的黑色成分。

**See also** [black](qcolor.html#black)（ ）[getCmykF](qcolor.html#getCmykF)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
int QColor.blue (self)
```

返回该颜色的蓝色分量。

**See also** [setBlue](qcolor.html#setBlue)（ ）[blueF](qcolor.html#blueF)（）和[getRgb](qcolor.html#getRgb)（ ） 。

```
float QColor.blueF (self)
```

返回该颜色的蓝色分量。

**See also** [setBlueF](qcolor.html#setBlueF)（ ）[blue](qcolor.html#blue)（）和[getRgbF](qcolor.html#getRgbF)（ ） 。

```
QStringList QColor.colorNames ()
```

返回[QStringList](qstringlist.html)包含颜色名称的Qt知道。

**See also** [Predefined Colors](qcolor.html#predefined-colors)。

```
QColor QColor.convertTo (self, Spec colorSpec)
```

[

创建副本_this_颜色在由指定的格式_colorSpec_。

](qcolor.html)

[**See also**](qcolor.html) [spec](qcolor.html#spec)（ ）[toCmyk](qcolor.html#toCmyk)（ ）[toHsv](qcolor.html#toHsv)（ ）[toRgb](qcolor.html#toRgb)（）和[isValid](qcolor.html#isValid)（ ） 。

```
int QColor.cyan (self)
```

返回该颜色的青色成分。

**See also** [cyanF](qcolor.html#cyanF)（ ）[getCmyk](qcolor.html#getCmyk)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
float QColor.cyanF (self)
```

返回该颜色的青色成分。

**See also** [cyan](qcolor.html#cyan)（ ）[getCmykF](qcolor.html#getCmykF)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
QColor QColor.dark (self, int factor = 200)
```

[](qcolor.html)

```
QColor QColor.darker (self, int factor = 200)
```

[

返回一个暗（或亮）色，但不改变这个对象。

](qcolor.html)

[如果_factor_大于100时，这个函数返回一个较深的颜色。环境_factor_到300返回具有三分之一的亮度的颜色。如果_factor_小于100 ，则返回的颜色很浅，但我们建议使用](qcolor.html)[lighter](qcolor.html#lighter)（）函数，用于这一目的。如果_factor_为0或负数，则返回值是不确定的。

该功能可将当前的RGB颜色转换到HSV ，通过划分值（V ）组件_factor_和颜色转换回RGB 。

此功能被引入Qt的4.3 。

**See also** [lighter](qcolor.html#lighter)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor QColor.fromCmyk (int c, int m, int y, int k, int alpha = 255)
```

[](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从给定的CMYK色彩值构造：_c_（青色） ，_m_（品红色），_y_（黄色），_k_（黑色），并_a_（ α-信道，即，透明性） 。

所有的值必须在0-255范围内。

**See also** [toCmyk](qcolor.html#toCmyk)（ ）[fromCmykF](qcolor.html#fromCmykF)（ ）[isValid](qcolor.html#isValid)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
QColor QColor.fromCmykF (float c, float m, float y, float k, float alpha = 1)
```

[

这是一个重载函数。

](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从给定的CMYK色彩值构造：_c_（青色） ，_m_（品红色），_y_（黄色），_k_（黑色），并_a_（ α-信道，即，透明性） 。

所有的值必须在0.0-1.0范围内。

**See also** [toCmyk](qcolor.html#toCmyk)（ ）[fromCmyk](qcolor.html#fromCmyk)（ ）[isValid](qcolor.html#isValid)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
QColor QColor.fromHsl (int h, int s, int l, int alpha = 255)
```

[](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从HSV颜色值组成，_h_（色调） ，_s_（饱和度） ，_l_（亮度），和_a_（ α-信道，即，透明性） 。

价值_s_，_l_和_a_都必须在0-255范围内;价值_h_必须在0-359的范围。

此功能被引入Qt的4.6 。

**See also** [toHsl](qcolor.html#toHsl)（ ）[fromHslF](qcolor.html#fromHslF)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor QColor.fromHslF (float h, float s, float l, float alpha = 1)
```

[

这是一个重载函数。

](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从HSV颜色值组成，_h_（色调） ，_s_（饱和度） ，_l_（亮度），和_a_（ α-信道，即，透明性） 。

所有的值必须在0.0-1.0范围内。

此功能被引入Qt的4.6 。

**See also** [toHsl](qcolor.html#toHsl)（ ）[fromHsl](qcolor.html#fromHsl)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor QColor.fromHsv (int h, int s, int v, int alpha = 255)
```

[](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从HSV颜色值组成，_h_（色调） ，_s_（饱和度） ，_v_（值），_a_（ α-信道，即，透明性） 。

价值_s_，_v_和_a_都必须在0-255范围内;价值_h_必须在0-359的范围。

**See also** [toHsv](qcolor.html#toHsv)（ ）[fromHsvF](qcolor.html#fromHsvF)（ ）[isValid](qcolor.html#isValid)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
QColor QColor.fromHsvF (float h, float s, float v, float alpha = 1)
```

[

这是一个重载函数。

](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从HSV颜色值组成，_h_（色调） ，_s_（饱和度） ，_v_（值），_a_（ α-信道，即，透明性） 。

所有的值必须在0.0-1.0范围内。

**See also** [toHsv](qcolor.html#toHsv)（ ）[fromHsv](qcolor.html#fromHsv)（ ）[isValid](qcolor.html#isValid)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
QColor QColor.fromRgb (int rgb)
```

[](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从给定的构造[QRgb](qcolor.html#QRgb-typedef)值_rgb_。

的alpha分量_rgb_被忽略（即，它会自动设置为255 ） ，使用[fromRgba](qcolor.html#fromRgba)（）函数，包括由给定指定的alpha通道[QRgb](qcolor.html#QRgb-typedef)值。

**See also** [fromRgba](qcolor.html#fromRgba)（ ）[fromRgbF](qcolor.html#fromRgbF)（ ）[toRgb](qcolor.html#toRgb)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor QColor.fromRgb (int r, int g, int b, int alpha = 255)
```

[](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从RGB颜色值构造，_r_（红色），_g_（绿色） ，_b_（蓝色），并_a_（ α-信道，即，透明性） 。

所有的值必须在0-255范围内。

**See also** [toRgb](qcolor.html#toRgb)（ ）[fromRgbF](qcolor.html#fromRgbF)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor QColor.fromRgba (int rgba)
```

[](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从给定的构造[QRgb](qcolor.html#QRgb-typedef)值_rgba_。

不同的是[fromRgb](qcolor.html#fromRgb)（）函数，由给定的指定的alpha通道[QRgb](qcolor.html#QRgb-typedef)值被包括在内。

**See also** [fromRgb](qcolor.html#fromRgb)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor QColor.fromRgbF (float r, float g, float b, float alpha = 1)
```

[](qcolor.html)

[静态方便函数返回一个](qcolor.html)[QColor](qcolor.html)从RGB颜色值构造，_r_（红色），_g_（绿色） ，_b_（蓝色），并_a_（ α-信道，即，透明性） 。

所有的值必须在0.0-1.0范围内。

**See also** [fromRgb](qcolor.html#fromRgb)（ ）[toRgb](qcolor.html#toRgb)（）和[isValid](qcolor.html#isValid)（ ） 。

```
(int c, int m, int y, int k, int alpha) QColor.getCmyk (self)
```

设置指向的内容_c_，_m_，_y_，_k_和_a_，青色，品红色，色彩的CMYK值的黄色，黑色，和alpha通道（透明度）的组件。

这些成分可以单独使用检索到的[cyan](qcolor.html#cyan)（ ）[magenta](qcolor.html#magenta)（ ）[yellow](qcolor.html#yellow)（ ）[black](qcolor.html#black)（）和[alpha](qcolor.html#alpha)（）函数。

**See also** [setCmyk](qcolor.html#setCmyk)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
(float c, float m, float y, float k, float alpha) QColor.getCmykF (self)
```

设置指向的内容_c_，_m_，_y_，_k_和_a_，青色，品红色，色彩的CMYK值的黄色，黑色，和alpha通道（透明度）的组件。

这些成分可以单独使用检索到的[cyanF](qcolor.html#cyanF)（ ）[magentaF](qcolor.html#magentaF)（ ）[yellowF](qcolor.html#yellowF)（ ）[blackF](qcolor.html#blackF)（）和[alphaF](qcolor.html#alphaF)（）函数。

**See also** [setCmykF](qcolor.html#setCmykF)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
(int h, int s, int l, int alpha) QColor.getHsl (self)
```

设置指向的内容_h_，_s_，_l_和_a_，对颜色的HSL值的色相，饱和度，明度，和alpha通道（透明度）的组件。

这些组件可以检索单独使用hueHsl （） ， saturationHsl （） ，[lightness](qcolor.html#lightness)（）和[alpha](qcolor.html#alpha)（）函数。

此功能被引入Qt的4.6 。

**See also** [setHsl](qcolor.html#setHsl)（ ） 。

```
(float h, float s, float l, float alpha) QColor.getHslF (self)
```

设置指向的内容_h_，_s_，_l_和_a_，对颜色的HSL值的色相，饱和度，明度，和alpha通道（透明度）的组件。

这些组件可以检索单独使用hueHslF （） ， saturationHslF （） ，[lightnessF](qcolor.html#lightnessF)（）和[alphaF](qcolor.html#alphaF)（）函数。

此功能被引入Qt的4.6 。

**See also** [setHsl](qcolor.html#setHsl)（ ） 。

```
(int h, int s, int v, int alpha) QColor.getHsv (self)
```

设置指向的内容_h_，_s_，_v_和_a_，对颜色的HSV值的色相，饱和度，值和alpha通道（透明度）的组件。

这些成分可以单独使用检索到的[hue](qcolor.html#hue)（ ）[saturation](qcolor.html#saturation)（ ）[value](qcolor.html#value)（）和[alpha](qcolor.html#alpha)（）函数。

**See also** [setHsv](qcolor.html#setHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
(float h, float s, float v, float alpha) QColor.getHsvF (self)
```

设置指向的内容_h_，_s_，_v_和_a_，对颜色的HSV值的色相，饱和度，值和alpha通道（透明度）的组件。

这些成分可以单独使用检索到的[hueF](qcolor.html#hueF)（ ）[saturationF](qcolor.html#saturationF)（ ）[valueF](qcolor.html#valueF)（）和[alphaF](qcolor.html#alphaF)（）函数。

**See also** [setHsv](qcolor.html#setHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
(int r, int g, int b, int alpha) QColor.getRgb (self)
```

设置指向的内容_r_，_g_，_b_和_a_，以红，绿，蓝和alpha通道（透明度）的颜色的RGB值的组件。

这些成分可以单独使用检索到的[red](qcolor.html#red)（ ）[green](qcolor.html#green)（ ）[blue](qcolor.html#blue)（）和[alpha](qcolor.html#alpha)（）函数。

**See also** [rgb](qcolor.html#rgb)（）和[setRgb](qcolor.html#setRgb)（ ） 。

```
(float r, float g, float b, float alpha) QColor.getRgbF (self)
```

设置指向的内容_r_，_g_，_b_和_a_，以红，绿，蓝和alpha通道（透明度）的颜色的RGB值的组件。

这些成分可以单独使用检索到的[redF](qcolor.html#redF)（ ）[greenF](qcolor.html#greenF)（ ）[blueF](qcolor.html#blueF)（）和[alphaF](qcolor.html#alphaF)（）函数。

**See also** [rgb](qcolor.html#rgb)（）和[setRgb](qcolor.html#setRgb)（ ） 。

```
int QColor.green (self)
```

返回该颜色的绿色分量。

**See also** [setGreen](qcolor.html#setGreen)（ ）[greenF](qcolor.html#greenF)（）和[getRgb](qcolor.html#getRgb)（ ） 。

```
float QColor.greenF (self)
```

返回该颜色的绿色分量。

**See also** [setGreenF](qcolor.html#setGreenF)（ ）[green](qcolor.html#green)（）和[getRgbF](qcolor.html#getRgbF)（ ） 。

```
int QColor.hslHue (self)
```

返回该颜色的色调色彩分量。

此功能被引入Qt的4.6 。

**See also** [getHslF](qcolor.html#getHslF)（）和[getHsl](qcolor.html#getHsl)（ ） 。

```
float QColor.hslHueF (self)
```

返回该颜色的色调色彩分量。

此功能被引入Qt的4.6 。

**See also** [hue](qcolor.html#hue)（）和[getHslF](qcolor.html#getHslF)（ ） 。

```
int QColor.hslSaturation (self)
```

返回该颜色的饱和度色彩分量。

此功能被引入Qt的4.6 。

**See also** [saturationF](qcolor.html#saturationF)（ ）[getHsv](qcolor.html#getHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
float QColor.hslSaturationF (self)
```

返回该颜色的饱和度色彩分量。

此功能被引入Qt的4.6 。

**See also** [saturationF](qcolor.html#saturationF)（）和[getHslF](qcolor.html#getHslF)（ ） 。

```
int QColor.hsvHue (self)
```

返回该颜色的色调色彩分量。

**See also** [hueF](qcolor.html#hueF)（ ）[getHsv](qcolor.html#getHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
float QColor.hsvHueF (self)
```

返回该颜色的色调色彩分量。

**See also** [hue](qcolor.html#hue)（ ）[getHsvF](qcolor.html#getHsvF)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
int QColor.hsvSaturation (self)
```

返回该颜色的饱和度色彩分量。

**See also** [saturationF](qcolor.html#saturationF)（ ）[getHsv](qcolor.html#getHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
float QColor.hsvSaturationF (self)
```

返回该颜色的饱和度色彩分量。

**See also** [saturation](qcolor.html#saturation)（ ）[getHsvF](qcolor.html#getHsvF)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
int QColor.hue (self)
```

返回该颜色的色调色彩分量。

颜色是隐式转换到HSV 。

**See also** [hsvHue](qcolor.html#hsvHue)（ ）[hueF](qcolor.html#hueF)（ ）[getHsv](qcolor.html#getHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
float QColor.hueF (self)
```

返回该颜色的色调色彩分量。

颜色是隐式转换到HSV 。

**See also** [hsvHueF](qcolor.html#hsvHueF)（ ）[hue](qcolor.html#hue)（ ）[getHsvF](qcolor.html#getHsvF)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
bool QColor.isValid (self)
```

返回True如果颜色是有效的，否则返回False 。

```
bool QColor.isValidColor (QString name)
```

返回True如果_name_是有效的颜色名称和可用于构造一个有效的[QColor](qcolor.html)对象，否则返回False 。

它使用在所使用的算法相同[setNamedColor](qcolor.html#setNamedColor)（ ） 。

此功能被引入Qt的4.7 。

**See also** [setNamedColor](qcolor.html#setNamedColor)（ ） 。

```
QColor QColor.light (self, int factor = 150)
```

[](qcolor.html)

```
QColor QColor.lighter (self, int factor = 150)
```

[

返回一个打火机（或较暗）的颜色，但不改变这个对象。

](qcolor.html)

[如果_factor_大于100时，这个函数返回一个较浅的颜色。环境_factor_150返回一个颜色是亮50 ％ 。如果_factor_小于100 ，则返回颜色比较深，但我们建议使用](qcolor.html)[darker](qcolor.html#darker)（）函数，用于这一目的。如果_factor_为0或负数，则返回值是不确定的。

该功能可将当前的RGB颜色转换到HSV ，通过乘以值（V ）组件_factor_和颜色转换回RGB 。

此功能被引入Qt的4.3 。

**See also** [darker](qcolor.html#darker)（）和[isValid](qcolor.html#isValid)（ ） 。

```
int QColor.lightness (self)
```

返回该颜色的明度色彩分量。

此功能被引入Qt的4.6 。

**See also** [lightnessF](qcolor.html#lightnessF)() and [getHsl](qcolor.html#getHsl)().

```
float QColor.lightnessF (self)
```

返回该颜色的明度色彩分量。

此功能被引入Qt的4.6 。

**See also** [value](qcolor.html#value)（）和[getHslF](qcolor.html#getHslF)（ ） 。

```
int QColor.magenta (self)
```

返回该颜色的品红色分量。

**See also** [magentaF](qcolor.html#magentaF)（ ）[getCmyk](qcolor.html#getCmyk)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
float QColor.magentaF (self)
```

返回该颜色的品红色分量。

**See also** [magenta](qcolor.html#magenta)（ ）[getCmykF](qcolor.html#getCmykF)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
QString QColor.name (self)
```

返回格式为“ ＃ RRGGBB ”颜色的名称，即一个“＃”字符后跟三个两位十六进制数字。

**See also** [setNamedColor](qcolor.html#setNamedColor)（ ） 。

```
int QColor.red (self)
```

返回该颜色的红色分量。

**See also** [setRed](qcolor.html#setRed)（ ）[redF](qcolor.html#redF)（）和[getRgb](qcolor.html#getRgb)（ ） 。

```
float QColor.redF (self)
```

返回该颜色的红色分量。

**See also** [setRedF](qcolor.html#setRedF)（ ）[red](qcolor.html#red)（）和[getRgbF](qcolor.html#getRgbF)（ ） 。

```
int QColor.rgb (self)
```

返回的颜色的RGB值。 Alpha值是不透明的。

**See also** [setRgb](qcolor.html#setRgb)（ ）[getRgb](qcolor.html#getRgb)（）和[rgba](qcolor.html#rgba)（ ） 。

```
int QColor.rgba (self)
```

返回RGB值的颜色，包括其阿尔法。

对于无效的颜色，返回的颜色的Alpha值是不确定的。

**See also** [setRgba](qcolor.html#setRgba)（）和[rgb](qcolor.html#rgb)（ ） 。

```
int QColor.saturation (self)
```

返回该颜色的饱和度色彩分量。

颜色是隐式转换到HSV 。

**See also** [hsvSaturation](qcolor.html#hsvSaturation)（ ）[saturationF](qcolor.html#saturationF)（ ）[getHsv](qcolor.html#getHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
float QColor.saturationF (self)
```

返回该颜色的饱和度色彩分量。

颜色是隐式转换到HSV 。

**See also** [hsvSaturationF](qcolor.html#hsvSaturationF)（ ）[saturation](qcolor.html#saturation)（ ）[getHsvF](qcolor.html#getHsvF)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
QColor.setAllowX11ColorNames (bool enabled)
```

允许[setNamedColor](qcolor.html#setNamedColor)（ ）来查找颜色的X11颜色数据库，如果_enabled_。默认情况下，[setNamedColor](qcolor.html#setNamedColor)（ ）不_not_查找颜色的X11颜色数据库。

**Note:**此功能仅可在X11平台上。

**See also** [setNamedColor](qcolor.html#setNamedColor)（）和[allowX11ColorNames](qcolor.html#allowX11ColorNames)（ ） 。

```
QColor.setAlpha (self, int alpha)
```

设置此颜色的alpha来_alpha_。整数阿尔法被指定在0-255范围内。

**See also** [alpha](qcolor.html#alpha)（ ）[alphaF](qcolor.html#alphaF)（）和[Alpha-Blended Drawing](qcolor.html#alpha-blended-drawing)。

```
QColor.setAlphaF (self, float alpha)
```

设置此颜色的alpha来_alpha_。 QREAL阿尔法被指定在0.0-1.0范围内。

**See also** [alphaF](qcolor.html#alphaF)（ ）[alpha](qcolor.html#alpha)（）和[Alpha-Blended Drawing](qcolor.html#alpha-blended-drawing)。

```
QColor.setBlue (self, int blue)
```

设置该颜色的蓝色分量到_blue_。整数组件0-255范围内指定。

**See also** [blue](qcolor.html#blue)（ ）[blueF](qcolor.html#blueF)（）和[setRgb](qcolor.html#setRgb)（ ） 。

```
QColor.setBlueF (self, float blue)
```

设置该颜色的蓝色分量到_blue_。浮子组件在0.0-1.0范围指定。

**See also** [blueF](qcolor.html#blueF)（ ）[blue](qcolor.html#blue)（）和[setRgbF](qcolor.html#setRgbF)（ ） 。

```
QColor.setCmyk (self, int c, int m, int y, int k, int alpha = 255)
```

设置颜色为CMYK值，_c_（青色） ，_m_（品红色），_y_（黄色），_k_（黑色），并_a_（ α-信道，即，透明性） 。

所有的值必须在0-255范围内。

**See also** [getCmyk](qcolor.html#getCmyk)（ ）[setCmykF](qcolor.html#setCmykF)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
QColor.setCmykF (self, float c, float m, float y, float k, float alpha = 1)
```

这是一个重载函数。

设置颜色为CMYK值，_c_（青色） ，_m_（品红色），_y_（黄色），_k_（黑色），并_a_（ α-信道，即，透明性） 。

所有的值必须在0.0-1.0范围内。

**See also** [getCmykF](qcolor.html#getCmykF)（ ）[setCmyk](qcolor.html#setCmyk)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
QColor.setGreen (self, int green)
```

设置这个颜色的绿色分量来_green_。整数组件0-255范围内指定。

**See also** [green](qcolor.html#green)（ ）[greenF](qcolor.html#greenF)（）和[setRgb](qcolor.html#setRgb)（ ） 。

```
QColor.setGreenF (self, float green)
```

设置这个颜色的绿色分量来_green_。浮子组件在0.0-1.0范围指定。

**See also** [greenF](qcolor.html#greenF)（ ）[green](qcolor.html#green)（）和[setRgbF](qcolor.html#setRgbF)（ ） 。

```
QColor.setHsl (self, int h, int s, int l, int alpha = 255)
```

设置一个HSL颜色值;_h_是色调_s_是饱和，_l_是轻和_a_是HSL颜色的alpha分量。

饱和度，值和alpha通道的值必须在0-255范围内，色调值必须大于-1 。

此功能被引入Qt的4.6 。

**See also** [getHsl](qcolor.html#getHsl)（）和[setHslF](qcolor.html#setHslF)（ ） 。

```
QColor.setHslF (self, float h, float s, float l, float alpha = 1)
```

设置一个HSL颜色明度;_h_是色调_s_是饱和，_l_是轻和_a_是HSL颜色的alpha分量。

所有的值必须在0.0-1.0范围内。

此功能被引入Qt的4.6 。

**See also** [getHslF](qcolor.html#getHslF)（）和[setHsl](qcolor.html#setHsl)（ ） 。

```
QColor.setHsv (self, int h, int s, int v, int alpha = 255)
```

设置HSV颜色值;_h_是色调_s_是饱和，_v_是值和_a_是HSV颜色的alpha分量。

饱和度，值和alpha通道的值必须在0-255范围内，色调值必须大于-1 。

**See also** [hsv](index.htm#hsv)（ ）[getHsv](qcolor.html#getHsv)（ ）[setHsvF](qcolor.html#setHsvF)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
QColor.setHsvF (self, float h, float s, float v, float alpha = 1)
```

设置HSV颜色值;_h_是色调_s_是饱和，_v_是值和_a_是HSV颜色的alpha分量。

所有的值必须在0.0-1.0范围内。

**See also** [getHsvF](qcolor.html#getHsvF)（ ）[setHsv](qcolor.html#setHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
QColor.setNamedColor (self, QString name)
```

设置该RGB值[QColor](qcolor.html)至_name_，这可能是在这些格式之一：

*   #RGB (each of R, G, and B is a single hex digit)
*   #RRGGBB
*   #RRRGGGBBB
*   #RRRRGGGGBBBB
*   A name from the list of colors defined in the list of [SVG color keyword names](http://www.w3.org/TR/SVG/types.html#ColorKeywords) provided by the World Wide Web Consortium; for example, "steelblue" or "gainsboro". These color names work on all platforms. Note that these color names are _not_ the same as defined by the [Qt.GlobalColor](qt.html#GlobalColor-enum) enums, e.g. "green" and [Qt.green](qt.html#GlobalColor-enum) does not refer to the same color.
*   `transparent` - representing the absence of a color.
*   _X11 only_: If [allowX11ColorNames](qcolor.html#allowX11ColorNames)() returns true, any valid X11 color name. See the documentation for `XParseColor()` for information about valid X11 color names.

颜色是无效的，如果_name_不能被解析。

**See also** [QColor](qcolor.html#QColor)（ ）[name](qcolor.html#name)（ ）[isValid](qcolor.html#isValid)（）和[allowX11ColorNames](qcolor.html#allowX11ColorNames)（ ） 。

```
QColor.setRed (self, int red)
```

设置这个颜色的红色分量_red_。整数组件0-255范围内指定。

**See also** [red](qcolor.html#red)（ ）[redF](qcolor.html#redF)（）和[setRgb](qcolor.html#setRgb)（ ） 。

```
QColor.setRedF (self, float red)
```

设置这个颜色的红色分量_red_。浮子组件在0.0-1.0范围指定。

**See also** [redF](qcolor.html#redF)（ ）[red](qcolor.html#red)（）和[setRgbF](qcolor.html#setRgbF)（ ） 。

```
QColor.setRgb (self, int r, int g, int b, int alpha = 255)
```

设置的RGB值，以_r_，_g_，_b_和α值，以_a_。

所有的值必须在0-255范围内。

**See also** [rgb](qcolor.html#rgb)（ ）[getRgb](qcolor.html#getRgb)（）和[setRgbF](qcolor.html#setRgbF)（ ） 。

```
QColor.setRgb (self, int rgb)
```

这是一个重载函数。

设置的RGB值，以_rgb_。 alpha值设置为不透明的。

```
QColor.setRgba (self, int rgba)
```

设置的RGB值，以_rgba_，包括其阿尔法。

**See also** [rgba](qcolor.html#rgba)（）和[rgb](qcolor.html#rgb)（ ） 。

```
QColor.setRgbF (self, float r, float g, float b, float alpha = 1)
```

设置此颜色的颜色通道_r_（红色），_g_（绿色） ，_b_（蓝色）和_a_（α，透明度） 。

所有的值必须在0.0-1.0范围内。

**See also** [rgb](qcolor.html#rgb)（ ）[getRgbF](qcolor.html#getRgbF)（）和[setRgb](qcolor.html#setRgb)（ ） 。

```
Spec QColor.spec (self)
```

[

返回的颜色是如何规定的。

](qcolor.html#Spec-enum)

[**See also**](qcolor.html#Spec-enum) [Spec](qcolor.html#Spec-enum)和[convertTo](qcolor.html#convertTo)（ ） 。

```
QColor QColor.toCmyk (self)
```

[](qcolor.html)

[创建并返回一个CMYK](qcolor.html)[QColor](qcolor.html)在此基础上的色彩。

**See also** [fromCmyk](qcolor.html#fromCmyk)（ ）[convertTo](qcolor.html#convertTo)（ ）[isValid](qcolor.html#isValid)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
QColor QColor.toHsl (self)
```

[](qcolor.html)

[创建并返回一个HSL](qcolor.html)[QColor](qcolor.html)在此基础上的色彩。

**See also** [fromHsl](qcolor.html#fromHsl)（ ）[convertTo](qcolor.html#convertTo)（）和[isValid](qcolor.html#isValid)（ ） 。

```
QColor QColor.toHsv (self)
```

[](qcolor.html)

[创建并返回一个单纯疱疹病毒](qcolor.html)[QColor](qcolor.html)在此基础上的色彩。

**See also** [fromHsv](qcolor.html#fromHsv)（ ）[convertTo](qcolor.html#convertTo)（ ）[isValid](qcolor.html#isValid)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
QColor QColor.toRgb (self)
```

[](qcolor.html)

[创建并返回一个RGB](qcolor.html)[QColor](qcolor.html)在此基础上的色彩。

**See also** [fromRgb](qcolor.html#fromRgb)（ ）[convertTo](qcolor.html#convertTo)（）和[isValid](qcolor.html#isValid)（ ） 。

```
int QColor.value (self)
```

返回此颜色值的颜色分量。

**See also** [valueF](qcolor.html#valueF)（ ）[getHsv](qcolor.html#getHsv)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
float QColor.valueF (self)
```

返回此颜色值的颜色分量。

**See also** [value](qcolor.html#value)（ ）[getHsvF](qcolor.html#getHsvF)（）和[The HSV Color Model](qcolor.html#the-hsv-color-model)。

```
int QColor.yellow (self)
```

返回该颜色的黄色成分。

**See also** [yellowF](qcolor.html#yellowF)（ ）[getCmyk](qcolor.html#getCmyk)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
float QColor.yellowF (self)
```

返回该颜色的黄色成分。

**See also** [yellow](qcolor.html#yellow)（ ）[getCmykF](qcolor.html#getCmykF)（）和[The CMYK Color Model](qcolor.html#the-cmyk-color-model)。

```
bool QColor.__eq__ (self, QColor c)
```

```
bool QColor.__ne__ (self, QColor c)
```