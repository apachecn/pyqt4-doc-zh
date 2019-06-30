# QExtensionManager Class Reference

## [[QtDesigner](index.htm) module]

该QExtensionManager类提供扩展的管理设施， Qt Designer中。[More...](#details)

继承[QObject](qobject.html)和[QAbstractExtensionManager](qabstractextensionmanager.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QObject extension (self, QObject object, QString iid)`
*   `registerExtensions (self, QAbstractExtensionFactory factory, QString iid = QString())`
*   `unregisterExtensions (self, QAbstractExtensionFactory factory, QString iid = QString())`

* * *

## Detailed Description

该QExtensionManager类提供扩展的管理设施， Qt Designer中。

In _Qt Designer_未创建的扩展，直到你需要它们。出于这个原因，实施一个扩展时，您还必须创建一个[QExtensionFactory](qextensionfactory.html)，即一个类，它能够让你的扩展的一个实例，并使用它注册_Qt Designer_的扩展管理器。

的延伸工厂登记通常在做[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数：

```
         void MyPlugin.initialize([QDesignerFormEditorInterface](qdesignerformeditorinterface.html) *formEditor)
         {
             if (initialized)
                 return;

             QExtensionManager *manager = formEditor->extensionManager();
             Q_ASSERT(manager != 0);

             manager->registerExtensions(new MyExtensionFactory(manager),
                                         Q_TYPEID([QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)));

             initialized = true;
         }

```

该QExtensionManager不打算直接实例化。你可以检索界面_Qt Designer_使用的扩展管理器[QDesignerFormEditorInterface.extensionManager](qdesignerformeditorinterface.html#extensionManager)（）函数。一个指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。当实现一个自定义的widget插件，你必须在子类[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)暴露你的插件_Qt Designer_。

然后，当一个扩展是必需的，_Qt Designer_的扩展管理器将通过其所有已注册的工厂运行要求[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）对每一直到第一个能够创建请求的扩展选定对象，被发现。这家工厂将使这个扩展的实例。

有扩展的四个可用的类型_Qt Designer_：[QDesignerContainerExtension](qdesignercontainerextension.html)，[QDesignerMemberSheetExtension](qdesignermembersheetextension.html)，[QDesignerPropertySheetExtension](qdesignerpropertysheetextension.html)和[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)。_Qt Designer_的行为是相同的同一个容器中，构件表，属性表或任务菜单所需的分机是否相关联。

对于使用QExtensionManager类的完整示例，请参见[Task Menu Extension example](index.htm)。该示例显示了如何创建一个自定义的widget插件Qt Designer中，以及如何使用[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)类的自定义项添加到_Qt Designer_的任务菜单。

* * *

## Method Documentation

```
QExtensionManager.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个扩展管理器给定的_parent_。

```
QObject QExtensionManager.extension (self, QObject object, QString iid)
```

[](qobject.html)

[从重新实现](qobject.html)[QAbstractExtensionManager.extension](qabstractextensionmanager.html#extension)（ ） 。

返回由指定的扩展名_iid_，对于给定的_object_。

```
QExtensionManager.registerExtensions (self, QAbstractExtensionFactory factory, QString iid = QString())
```

从重新实现[QAbstractExtensionManager.registerExtensions](qabstractextensionmanager.html#registerExtensions)（ ） 。

注册由给定指定的扩展名_factory_和扩展标识符_iid_。

```
QExtensionManager.unregisterExtensions (self, QAbstractExtensionFactory factory, QString iid = QString())
```

从重新实现[QAbstractExtensionManager.unregisterExtensions](qabstractextensionmanager.html#unregisterExtensions)（ ） 。

注销由给定指定的扩展名_factory_和扩展标识符_iid_。