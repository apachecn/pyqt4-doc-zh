# QGLColormap Class Reference

## [[QtOpenGL](index.htm) module]

该QGLColormap类用于安装自定义色彩映射成[QGLWidget](qglwidget.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QGLColormap)`
*   `detach (self)`
*   `QColor entryColor (self, int idx)`
*   `int entryRgb (self, int idx)`
*   `int find (self, int color)`
*   `int findNearest (self, int color)`
*   `int handle (self)`
*   `bool isEmpty (self)`
*   `setEntries (self, list-of-int colors, int base = 0)`
*   `setEntry (self, int idx, int color)`
*   `setEntry (self, int idx, QColor color)`
*   `setHandle (self, int ahandle)`
*   `int size (self)`

* * *

## Detailed Description

该QGLColormap类用于安装自定义色彩映射成[QGLWidget](qglwidget.html)。

QGLColormap提供了指定和安装索引颜色表的一个平台独立的方式[QGLWidget](qglwidget.html)。在使用OpenGL的颜色索引模式QGLColormap是特别有用的。

在X11下你必须使用支持无论是X服务器`PseudoColor` or `DirectColor`视觉类。如果你的X server目前只提供了一个`GrayScale`，`TrueColor`，`StaticColor` or `StaticGray`视觉，你将无法分配colorcells写作。如果是这样的话，试试你的X服务器设置为8位模式。那么它应该为你提供至少一个`PseudoColor`视觉。请注意，您可能会遇到颜色映射闪烁，如果你的X服务器在8位模式下运行。

该[size](qglcolormap.html#size)颜色表的（ ）总是被设置为256色。请注意，在Windows下，你也可以在子控件安装的colormaps 。

这个类的使用[implicit sharing](index.htm)作为存储器和速度的优化。

使用示例：

```
 #include <QApplication>
 #include <QGLColormap>

 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html) app(argc, argv);

     MySuperGLWidget widget;     // a QGLWidget in color-index mode
     QGLColormap colormap;

     // This will fill the colormap with colors ranging from
     // black to white.
     const int size = 256;
     for (int i = 0; i < size; ++i)
         colormap.setEntry(i, qRgb(i, i, i));

     widget.setColormap(colormap);
     widget.show();
     return app.exec();
 }

```

* * *

## Method Documentation

```
QGLColormap.__init__ (self)
```

构建[QGLColormap](qglcolormap.html)。

```
QGLColormap.__init__ (self, QGLColormap)
```

构造的浅表副本_map_。

```
QGLColormap.detach (self)
```

```
QColor QGLColormap.entryColor (self, int idx)
```

[](qcolor.html)

[返回](qcolor.html)[QRgb](qcolor.html#QRgb-typedef)与指数colorcell值_idx_。

```
int QGLColormap.entryRgb (self, int idx)
```

返回[QRgb](qcolor.html#QRgb-typedef)与指数colorcell值_idx_。

```
int QGLColormap.find (self, int color)
```

返回的颜色的索引_color_。如果_color_未在地图上，则返回-1。

```
int QGLColormap.findNearest (self, int color)
```

返回最匹配颜色的颜色的索引_color_。

```
int QGLColormap.handle (self)
```

```
bool QGLColormap.isEmpty (self)
```

返回True如果颜色表为空或不使用由[QGLWidget](qglwidget.html)否则返回False 。

未设置任何颜色值的颜色表被认为是空的。由于历史原因，一个色图，有颜色值设置，但它不使用由[QGLWidget](qglwidget.html)也被认为是空的。

比较[size](qglcolormap.html#size)（ ）与零，以确定该颜色表是空的，无论它是在使用中由一[QGLWidget](qglwidget.html)或没有。

**See also** [size](qglcolormap.html#size)（ ） 。

```
QGLColormap.setEntries (self, list-of-int colors, int base = 0)
```

在此颜色映射设定单元的阵列。_count_是应该被设置的颜色的数量，_colors_是颜色的数组，并_base_是的起始索引。在所述第一元件_colors_设置在_base_在颜色表。

```
QGLColormap.setEntry (self, int idx, int color)
```

设置单元格的索引_idx_colormap中的颜色_color_。

```
QGLColormap.setEntry (self, int idx, QColor color)
```

这是一个重载函数。

索引设置单元格_idx_colormap中的颜色_color_。

```
QGLColormap.setHandle (self, int ahandle)
```

```
int QGLColormap.size (self)
```

返回colorcells的颜色表的数量。