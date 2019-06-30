# QDesignerObjectInspectorInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerObjectInspectorInterface类允许你改变的Qt Designer的对象检查的重点。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent, Qt.WindowFlags flags = 0)`
*   `QDesignerFormEditorInterface core (self)`
*   `setFormWindow (self, QDesignerFormWindowInterface formWindow)`

* * *

## Detailed Description

该QDesignerObjectInspectorInterface类允许你改变的Qt Designer的对象检查的重点。

您可以使用QDesignerObjectInspectorInterface改变当前窗体窗口的选择。例如，实现一个自定义的widget插件时：

```
         QDesignerObjectInspectorInterface *objectInspector = 0;
         objectInspector = formEditor->objectInspector();

         [QDesignerFormWindowManagerInterface](qdesignerformwindowmanagerinterface.html) *manager = 0;
         manager = formEditor->formWindowManager();

         objectInspector->setFormWindow(manager->formWindow(0));

```

该QDesignerObjectInspectorInterface类不适合直接实例化。你可以检索界面_Qt Designer_使用的对象检查器[QDesignerFormEditorInterface.objectInspector](qdesignerformeditorinterface.html#objectInspector)（）函数。一个指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。当实现一个自定义的widget插件，你必须在子类[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)暴露你的插件_Qt Designer_。

该接口提供了[core](qdesignerobjectinspectorinterface.html#core)（ ）函数，你可以用它来检索指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象，并且[setFormWindow](qdesignerobjectinspectorinterface.html#setFormWindow)（ ）函数，使您可以更改当前窗体窗口的选择。

* * *

## Method Documentation

```
QDesignerObjectInspectorInterface.__init__ (self, QWidget parent, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个对象检查接口与给定的_parent_和在指定的窗口_flags_。

```
QDesignerFormEditorInterface QDesignerObjectInspectorInterface.core (self)
```

[](qdesignerformeditorinterface.html)

[返回一个指针_Qt Designer_目前的](qdesignerformeditorinterface.html)[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象。

```
QDesignerObjectInspectorInterface.setFormWindow (self, QDesignerFormWindowInterface formWindow)
```

这种方法也是一个Qt槽与C + +的签名`void setFormWindow(QDesignerFormWindowInterface *)`。

这种方法是抽象的，应在任何子类中重新实现。

设置当前选定的表格窗口_formWindow_。