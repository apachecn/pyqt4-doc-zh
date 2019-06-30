# QDesignerFormEditorInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerFormEditorInterface类允许您访问Qt设计器的各个组成部分。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QDesignerActionEditorInterface actionEditor (self)`
*   `QExtensionManager extensionManager (self)`
*   `QDesignerFormWindowManagerInterface formWindowManager (self)`
*   `QDesignerObjectInspectorInterface objectInspector (self)`
*   `QDesignerPropertyEditorInterface propertyEditor (self)`
*   `setActionEditor (self, QDesignerActionEditorInterface actionEditor)`
*   `setObjectInspector (self, QDesignerObjectInspectorInterface objectInspector)`
*   `setPropertyEditor (self, QDesignerPropertyEditorInterface propertyEditor)`
*   `setWidgetBox (self, QDesignerWidgetBoxInterface widgetBox)`
*   `QWidget topLevel (self)`
*   `QDesignerWidgetBoxInterface widgetBox (self)`

* * *

## Detailed Description

该QDesignerFormEditorInterface类允许您访问Qt设计器的各个组成部分。

_Qt Designer_目前的QDesignerFormEditorInterface对象掌握所有的信息_Qt Designer_的组件：动作编辑器，在Object Inspector ，属性编辑器，在窗口小部件中，并扩展和形式的窗口管理器。 QDesignerFormEditorInterface包含的函数的集合，它提供的接口对所有这些组件。它们通常用于查询（和操作）的各个组件。例如：

```
         [QDesignerObjectInspectorInterface](qdesignerobjectinspectorinterface.html) *objectInspector = 0;
         objectInspector = formEditor->objectInspector();

         [QDesignerFormWindowManagerInterface](qdesignerformwindowmanagerinterface.html) *manager = 0;
         manager = formEditor->formWindowManager();

         objectInspector->setFormWindow(manager->formWindow(0));

```

QDesignerFormEditorInterface不打算直接实例化。一个指向_Qt Designer_目前的QDesignerFormEditorInterface对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。当实现一个自定义的widget插件，你必须在子类[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)暴露你的插件_Qt Designer_。

QDesignerFormEditorInterface还提供了功能，可以设置动作编辑器，属性编辑器，对象观察器和小工具盒。如果你想提供自己的自定义组件这些都是唯一有用的。

如果设计师是嵌入在另一个程序中，一个人能提供自己的设置管理。管理者所使用的部件_Qt Designer_存储/检索持久的配置设置。默认管理器的用途[QSettings](qsettings.html)作为后端。

最后， QDesignerFormEditorInterface提供[topLevel](qdesignerformeditorinterface.html#topLevel)（ ）函数返回_Qt Designer_的顶级窗口部件。

* * *

## Method Documentation

```
QDesignerFormEditorInterface.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)与给定对象_parent_。

```
QDesignerActionEditorInterface QDesignerFormEditorInterface.actionEditor (self)
```

[

返回一个接口_Qt Designer_的动作编辑器。

](qdesigneractioneditorinterface.html)

[**See also**](qdesigneractioneditorinterface.html) [setActionEditor](qdesignerformeditorinterface.html#setActionEditor)（ ） 。

```
QExtensionManager QDesignerFormEditorInterface.extensionManager (self)
```

[

返回一个接口_Qt Designer_的扩展管理器。

](qextensionmanager.html)

```
QDesignerFormWindowManagerInterface QDesignerFormEditorInterface.formWindowManager (self)
```

[

返回一个接口_Qt Designer_的形成窗口管理器。

](qdesignerformwindowmanagerinterface.html)

```
QDesignerObjectInspectorInterface QDesignerFormEditorInterface.objectInspector (self)
```

[

返回一个接口_Qt Designer_的对象检查。

](qdesignerobjectinspectorinterface.html)

[**See also**](qdesignerobjectinspectorinterface.html) [setObjectInspector](qdesignerformeditorinterface.html#setObjectInspector)（ ） 。

```
QDesignerPropertyEditorInterface QDesignerFormEditorInterface.propertyEditor (self)
```

[

返回一个接口_Qt Designer_的属性编辑器。

](qdesignerpropertyeditorinterface.html)

[**See also**](qdesignerpropertyeditorinterface.html) [setPropertyEditor](qdesignerformeditorinterface.html#setPropertyEditor)（ ） 。

```
QDesignerFormEditorInterface.setActionEditor (self, QDesignerActionEditorInterface actionEditor)
```

Sets _Qt Designer_的动作编辑器中指定的_actionEditor_。

**See also** [actionEditor](qdesignerformeditorinterface.html#actionEditor)（ ） 。

```
QDesignerFormEditorInterface.setObjectInspector (self, QDesignerObjectInspectorInterface objectInspector)
```

Sets _Qt Designer_被指定的对象检查_objectInspector_。

**See also** [objectInspector](qdesignerformeditorinterface.html#objectInspector)（ ） 。

```
QDesignerFormEditorInterface.setPropertyEditor (self, QDesignerPropertyEditorInterface propertyEditor)
```

Sets _Qt Designer_的属性编辑器中指定的_propertyEditor_。

**See also** [propertyEditor](qdesignerformeditorinterface.html#propertyEditor)（ ） 。

```
QDesignerFormEditorInterface.setWidgetBox (self, QDesignerWidgetBoxInterface widgetBox)
```

Sets _Qt Designer_的小工具框指定_widgetBox_。

**See also** [widgetBox](qdesignerformeditorinterface.html#widgetBox)（ ） 。

```
QWidget QDesignerFormEditorInterface.topLevel (self)
```

[

Returns _Qt Designer_的顶级窗口部件。

](qwidget.html)

```
QDesignerWidgetBoxInterface QDesignerFormEditorInterface.widgetBox (self)
```

[

返回一个接口_Qt Designer_的小工具盒。

](qdesignerwidgetboxinterface.html)

[**See also**](qdesignerwidgetboxinterface.html) [setWidgetBox](qdesignerformeditorinterface.html#setWidgetBox)（ ） 。