# QWebInspector Class Reference

## [[QtWebKit](index.htm) module]

该QWebInspector类允许的安置和控制[QWebPage](qwebpage.html)的检查。检查员可以显示网页的层次结构，它的加载数据和它的各个元素的当前状态。它主要是用于Web开发人员。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `closeEvent (self, QCloseEvent event)`
*   `bool event (self, QEvent)`
*   `hideEvent (self, QHideEvent event)`
*   `QWebPage page (self)`
*   `resizeEvent (self, QResizeEvent event)`
*   `setPage (self, QWebPage page)`
*   `showEvent (self, QShowEvent event)`
*   `QSize sizeHint (self)`

* * *

## Detailed Description

该QWebInspector类允许的安置和控制[QWebPage](qwebpage.html)的检查。检查员可以显示网页的层次结构，它的加载数据和它的各个元素的当前状态。它主要是用于Web开发人员。

该[QWebPage](qwebpage.html)要被检查，必须使用指定的[setPage](qwebinspector.html#setPage)（）方法。

一个典型的使用QWebInspector的如下：

```
     // ...
     [QWebPage](qwebpage.html) *page = new [QWebPage](qwebpage.html);
     // ...

     QWebInspector *inspector = new QWebInspector;
     inspector->setPage(page);

```

一个QWebInspector可取得明显的以编程方式使用[setVisible](qwidget.html#visible-prop)（） ，或者通过附加的用户[QWebPage](qwebpage.html)的上下文菜单。

**Note:**如果A QWebInspector会显示一个空白窗口小部件：

*   [page](qwebinspector.html#page)() is null
*   [QWebSettings.DeveloperExtrasEnabled](qwebsettings.html#WebAttribute-enum) is false

### Resources

这个类的作用主要是作为一个容器和一个控制器的检查。最需要的检查器中的资源都是由相关的资[QWebPage](qwebpage.html)并且被分配在第一时间是：

*   an element is inspected
*   the QWebInspector is shown.

### Inspector configuration persistence

检查员允许用户通过其用户界面配置一些选项（如资源跟踪​​“始终启用”选项） 。这些设置将自动被持久化[QtWebKit](index.htm)只有当你的应用程序以前称为[QCoreApplication.setOrganizationName](qcoreapplication.html#organizationName-prop)（）和[QCoreApplication.setApplicationName](qcoreapplication.html#applicationName-prop)（ ） 。看[QSettings](qsettings.html)的默认构造函数文档为什么这是必要的解释。

* * *

## Method Documentation

```
QWebInspector.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个未绑定[QWebInspector](qwebinspector.html)同_parent_作为其母公司。

```
QWebInspector.closeEvent (self, QCloseEvent event)
```

从重新实现[QWidget.closeEvent](qwidget.html#closeEvent)（ ） 。

```
bool QWebInspector.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QWebInspector.hideEvent (self, QHideEvent event)
```

从重新实现[QWidget.hideEvent](qwidget.html#hideEvent)（ ） 。

```
QWebPage QWebInspector.page (self)
```

[](qwebpage.html)

[返回视察](qwebpage.html)[QWebPage](qwebpage.html)。如果没有网页，目前相关的，则返回一个空指针。

**See also** [setPage](qwebinspector.html#setPage)（ ） 。

```
QWebInspector.resizeEvent (self, QResizeEvent event)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QWebInspector.setPage (self, QWebPage page)
```

这个检查绑定到[QWebPage](qwebpage.html)要被检查。

**Notes:**

*   There can only be one [QWebInspector](qwebinspector.html) associated with a [QWebPage](qwebpage.html) and vice versa.
*   Calling this method with a null _page_ will break the current association, if any.
*   If _page_ is already associated to another [QWebInspector](qwebinspector.html), the association will be replaced and the previous [QWebInspector](qwebinspector.html) will become unbound

**See also** [page](qwebinspector.html#page)（ ） 。

```
QWebInspector.showEvent (self, QShowEvent event)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QSize QWebInspector.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。