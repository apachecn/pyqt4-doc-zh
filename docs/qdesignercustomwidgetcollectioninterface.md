# QDesignerCustomWidgetCollectionInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerCustomWidgetCollectionInterface类，可以包含多个自定义部件在一个单一的库。[More...](#details)

通过继承[QPyDesignerCustomWidgetCollectionPlugin](qpydesignercustomwidgetcollectionplugin.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDesignerCustomWidgetCollectionInterface)`
*   `list-of-QDesignerCustomWidgetInterface customWidgets (self)`

* * *

## Detailed Description

该QDesignerCustomWidgetCollectionInterface类，可以包含多个自定义部件在一个单一的库。

当实现一个自定义的widget插件，你把它做成一个单独的库。如果你想包括几个自定义的widget插件在同一个库中，你必须在另外的子类QDesignerCustomWidgetCollectionInterface 。

QDesignerCustomWidgetCollectionInterface包含一个单一的函数返回集合的列表[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)对象。例如，如果你有多个自定义部件`CustomWidgetOne`，`CustomWidgetTwo`和`CustomWidgetThree`，类的定义可能看起来像这样：

```
 #include customwidgetoneinterface.h
 #include customwidgettwointerface.h
 #include customwidgetthreeinterface.h

 #include <QtDesigner/QtDesigner>
 #include <QtCore/qplugin.h>

 class MyCustomWidgets: public [QObject](qobject.html), public QDesignerCustomWidgetCollectionInterface
 {
     Q_OBJECT
     Q_INTERFACES(QDesignerCustomWidgetCollectionInterface)

 public:
     MyCustomWidgets([QObject](qobject.html) *parent = 0);

     virtual [QList](index.htm)<[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)*> customWidgets() const;

 private:
     [QList](index.htm)<[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)*> widgets;
 };

```

在类的构造函数时，将接口加入您的自定义窗口小部件，您在返回列表[customWidgets](qdesignercustomwidgetcollectioninterface.html#customWidgets)（ ）函数：

```
 MyCustomWidgets.MyCustomWidgets([QObject](qobject.html) *parent)
         : [QObject](qobject.html)(parent)
 {
     widgets.append(new CustomWidgetOneInterface(this));
     widgets.append(new CustomWidgetTwoInterface(this));
     widgets.append(new CustomWidgetThreeInterface(this));
 }

 [QList](index.htm)<[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)*> MyCustomWidgets.customWidgets() const
 {
     return widgets;
 }

 Q_EXPORT_PLUGIN2(customwidgetsplugin, MyCustomWidgets)

```

请注意，而不是使用导出的每个自定义窗口小部件插件的[Q_EXPORT_PLUGIN2](index.htm#Q_EXPORT_PLUGIN2)（）宏，你导出整个集合。该[Q_EXPORT_PLUGIN2](index.htm#Q_EXPORT_PLUGIN2)（ ）宏可确保_Qt Designer_可以访问和构建自定义部件。如果没有这个宏，是没有办法的_Qt Designer_使用它们。

* * *

## Method Documentation

```
QDesignerCustomWidgetCollectionInterface.__init__ (self)
```

```
QDesignerCustomWidgetCollectionInterface.__init__ (self, QDesignerCustomWidgetCollectionInterface)
```

```
list-of-QDesignerCustomWidgetInterface QDesignerCustomWidgetCollectionInterface.customWidgets (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回接口列表，以集合的自定义部件。