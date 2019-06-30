# QX11Info Class Reference

## [[QtGui](index.htm) module]

该QX11Info类提供有关X显示配置信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QX11Info other)`
*   `int cells (self)`
*   `int colormap (self)`
*   `bool defaultColormap (self)`
*   `bool defaultVisual (self)`
*   `int depth (self)`
*   `int screen (self)`
*   `sip.voidptr visual (self)`

### Static Methods

*   `int appCells (int screen = -1)`
*   `str appClass ()`
*   `int appColormap (int screen = -1)`
*   `bool appDefaultColormap (int screen = -1)`
*   `bool appDefaultVisual (int screen = -1)`
*   `int appDepth (int screen = -1)`
*   `int appDpiX (int screen = -1)`
*   `int appDpiY (int screen = -1)`
*   `int appRootWindow (int screen = -1)`
*   `int appScreen ()`
*   `int appTime ()`
*   `int appUserTime ()`
*   `sip.voidptr appVisual (int screen = -1)`
*   `Display display ()`
*   `bool isCompositingManagerRunning ()`
*   `setAppDpiX (int screen, int dpi)`
*   `setAppDpiY (int screen, int dpi)`
*   `setAppTime (int time)`
*   `setAppUserTime (int time)`

* * *

## Detailed Description

该QX11Info类提供有关X显示配置信息。

这个类提供了两个API ：一组非静态函数，提供有关特定部件或像素图的信息，和一组静态函数提供的默认信息的应用程序。

**Warning:**这个类仅适用于X11 。对于一个可移植的方式，使用查询每个屏幕信息[QDesktopWidget](qdesktopwidget.html)。

* * *

## Method Documentation

```
QX11Info.__init__ (self)
```

构造一个空[QX11Info](qx11info.html)对象。

```
QX11Info.__init__ (self, QX11Info other)
```

构造的副本_other_。

```
int QX11Info.appCells (int screen = -1)
```

返回在给定的应用程序所使用的细胞数_screen_。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [cells](qx11info.html#cells)（ ） 。

```
str QX11Info.appClass ()
```

返回X11的应用程序类。

**See also** [display](qx11info.html#display)（ ） 。

```
int QX11Info.appColormap (int screen = -1)
```

返回给定的句柄应用程序的彩色地图_screen_。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [colormap](qx11info.html#colormap)（）和[defaultColormap](qx11info.html#defaultColormap)（ ） 。

```
bool QX11Info.appDefaultColormap (int screen = -1)
```

如果应用程序有一个默认的彩色地图上给定的，则返回True_screen_否则返回False 。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

```
bool QX11Info.appDefaultVisual (int screen = -1)
```

如果应用程序有一个默认的视觉上给定的，则返回True_screen_否则返回False 。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

```
int QX11Info.appDepth (int screen = -1)
```

返回在给定的应用程序所使用的颜色深度（每个像素的位数）_screen_。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [depth](qx11info.html#depth)（ ） 。

```
int QX11Info.appDpiX (int screen = -1)
```

返回给定的水平分辨率_screen_以每英寸的点数表示。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [setAppDpiX](qx11info.html#setAppDpiX)（）和[appDpiY](qx11info.html#appDpiY)（ ） 。

```
int QX11Info.appDpiY (int screen = -1)
```

返回给定的垂直分辨率_screen_以每英寸的点数表示。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [setAppDpiY](qx11info.html#setAppDpiY)（）和[appDpiX](qx11info.html#appDpiX)（ ） 。

```
int QX11Info.appRootWindow (int screen = -1)
```

返回给定的句柄应用程序根窗口_screen_。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [QApplication.desktop](qapplication.html#desktop)（ ） 。

```
int QX11Info.appScreen ()
```

返回正在显示的应用程序，其中该屏幕的数量。

**See also** [display](qx11info.html#display)（）和[screen](qx11info.html#screen)（ ） 。

```
int QX11Info.appTime ()
```

返回X11的时间。

**See also** [setAppTime](qx11info.html#setAppTime)（）和[appUserTime](qx11info.html#appUserTime)（ ） 。

```
int QX11Info.appUserTime ()
```

返回X11的用户时间。

**See also** [setAppUserTime](qx11info.html#setAppUserTime)（）和[appTime](qx11info.html#appTime)（ ） 。

```
sip.voidptr QX11Info.appVisual (int screen = -1)
```

返回当前视觉所使用的应用程序在给定的_screen_。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [visual](qx11info.html#visual)（）和[defaultVisual](qx11info.html#defaultVisual)（ ） 。

```
int QX11Info.cells (self)
```

返回单元的数目。

**See also** [appCells](qx11info.html#appCells)（ ） 。

```
int QX11Info.colormap (self)
```

返回的句柄彩色地图。

**See also** [defaultColormap](qx11info.html#defaultColormap)（ ） 。

```
bool QX11Info.defaultColormap (self)
```

返回True如果有一个默认的彩色地图，否则返回False 。

**See also** [colormap](qx11info.html#colormap)（ ） 。

```
bool QX11Info.defaultVisual (self)
```

返回True如果有一个默认的视觉享受;否则返回False。

**See also** [visual](qx11info.html#visual)（）和[appVisual](qx11info.html#appVisual)（ ） 。

```
int QX11Info.depth (self)
```

返回X显示的色彩深度（每像素位数） 。

**See also** [appDepth](qx11info.html#appDepth)（ ） 。

```
Display QX11Info.display ()
```

返回默认显示为应用程序。

**See also** [appScreen](qx11info.html#appScreen)（ ） 。

```
bool QX11Info.isCompositingManagerRunning ()
```

返回True如果有一个合成器上运行。

此功能被引入Qt的4.4 。

```
int QX11Info.screen (self)
```

把屏幕返回当前正在使用的数量。

返回值是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [appScreen](qx11info.html#appScreen)（ ） 。

```
QX11Info.setAppDpiX (int screen, int dpi)
```

设定的给定的水平分辨率_screen_以通过指定每英寸的点数_xdpi_。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [appDpiX](qx11info.html#appDpiX)（）和[setAppDpiY](qx11info.html#setAppDpiY)（ ） 。

```
QX11Info.setAppDpiY (int screen, int dpi)
```

设定的给定的垂直分辨率_screen_以通过指定每英寸的点数_ydpi_。

该_screen_参数是一个X屏幕号。请注意，如果用户的系统使用的Xinerama （相对于传统的X11多屏幕） ，只有一个X屏幕。使用[QDesktopWidget](qdesktopwidget.html)查询有关的Xinerama屏幕上的信息。

**See also** [appDpiY](qx11info.html#appDpiY)（）和[setAppDpiX](qx11info.html#setAppDpiX)（ ） 。

```
QX11Info.setAppTime (int time)
```

设置X11的时间由指定的值_time_。

**See also** [appTime](qx11info.html#appTime)（）和[setAppUserTime](qx11info.html#setAppUserTime)（ ） 。

```
QX11Info.setAppUserTime (int time)
```

设置所指定的X11用户时间_time_。

**See also** [appUserTime](qx11info.html#appUserTime)（）和[setAppTime](qx11info.html#setAppTime)（ ） 。

```
sip.voidptr QX11Info.visual (self)
```

返回当前视觉。

**See also** [appVisual](qx11info.html#appVisual)（）和[defaultVisual](qx11info.html#defaultVisual)（ ） 。