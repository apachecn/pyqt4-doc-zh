# QExtensionFactory Class Reference

## [[QtDesigner](index.htm) module]

该QExtensionFactory类允许你创建一个工厂，是能够使Qt Designer中自定义扩展的实例。[More...](#details)

继承[QObject](qobject.html)和[QAbstractExtensionFactory](qabstractextensionfactory.html)。

### Methods

*   `__init__ (self, QExtensionManager parent = None)`
*   `QObject createExtension (self, QObject object, QString iid, QObject parent)`
*   `QObject extension (self, QObject object, QString iid)`
*   `QExtensionManager extensionManager (self)`

* * *

## Detailed Description

该QExtensionFactory类允许你创建一个工厂，是能够使Qt Designer中自定义扩展的实例。

In _Qt Designer_未创建的扩展，直到你需要它们。出于这个原因，实现自定义扩展时，您还必须创建一个QExtensionFactory ，即一个类，它能够让你的扩展的一个实例，并使用它注册_Qt Designer_的[extension manager](qextensionmanager.html)。

该[QExtensionManager](qextensionmanager.html)类提供了扩展的管理设施， Qt Designer中。当一个扩展是必需的， Qt设计的[extension manager](qextensionmanager.html)将通过其所有已注册的工厂运行要求[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）对每一直到第一个是能够创造一个请求扩展选定对象，被发现。这家工厂将使这个扩展的实例。

有四种类型的可在Qt Designer中的扩展：[QDesignerContainerExtension](qdesignercontainerextension.html)，[QDesignerMemberSheetExtension](qdesignermembersheetextension.html)，[QDesignerPropertySheetExtension](qdesignerpropertysheetextension.html)和[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)。 Qt设计器的行为是一样的具有多页的容器，一个成员表，属性表或任务菜单中的延期申请是否相关。

您可以创建一个新的QExtensionFactory和重新实现[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（）函数。例如：

```
         [QObject](qobject.html) *ANewExtensionFactory.createExtension([QObject](qobject.html) *object,
                 const [QString](qstring.html) &iid, [QObject](qobject.html) *parent) const
         {
             if (iid != Q_TYPEID([QDesignerContainerExtension](qdesignercontainerextension.html)))
                 return 0;

             if (MyCustomWidget *widget = qobject_cast<MyCustomWidget*>
                    (object))
                 return new MyContainerExtension(widget, parent);

             return 0;
         }

```

或者您可以使用现有的工厂，扩大[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）函数，使工厂能够创建您的扩展也是如此。例如：

```
         [QObject](qobject.html) *AGeneralExtensionFactory.createExtension([QObject](qobject.html) *object,
                 const [QString](qstring.html) &iid, [QObject](qobject.html) *parent) const
         {
             MyCustomWidget *widget = qobject_cast<MyCustomWidget*>(object);

             if (widget && (iid == Q_TYPEID([QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)))) {
                 return new MyTaskMenuExtension(widget, parent);

             } else if (widget && (iid == Q_TYPEID([QDesignerContainerExtension](qdesignercontainerextension.html)))) {
                 return new MyContainerExtension(widget, parent);

             } else {
                 return 0;
             }
         }

```

对于使用QExtensionFactory类的完整示例，请参见[Task Menu Extension example](index.htm)。该示例显示了如何创建一个自定义的widget插件Qt Designer中，以及如何使用[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)类的自定义项添加到Qt Designer中的任务菜单。

* * *

## Method Documentation

```
QExtensionFactory.__init__ (self, QExtensionManager parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个扩展工厂给定的_parent_。

```
QObject QExtensionFactory.createExtension (self, QObject object, QString iid, QObject parent)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建由指定的延伸_iid_对于给定的_object_。扩展对象为指定的子创建_parent_。

](qobject.html)

[**See also**](qobject.html) [extension](qextensionfactory.html#extension)（ ） 。

```
QObject QExtensionFactory.extension (self, QObject object, QString iid)
```

[](qobject.html)

[从重新实现](qobject.html)[QAbstractExtensionFactory.extension](qabstractextensionfactory.html#extension)（ ） 。

返回由指定的扩展名_iid_对于给定的_object_。

**See also** [createExtension](qextensionfactory.html#createExtension)（ ） 。

```
QExtensionManager QExtensionFactory.extensionManager (self)
```

[

返回扩展工厂的扩展管理器。

](qextensionmanager.html)