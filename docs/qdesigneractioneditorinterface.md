# QDesignerActionEditorInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerActionEditorInterface类允许您更改的Qt Designer的动作编辑器的焦点。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent, Qt.WindowFlags flags = 0)`
*   `QDesignerFormEditorInterface core (self)`
*   `manageAction (self, QAction action)`
*   `setFormWindow (self, QDesignerFormWindowInterface formWindow)`
*   `unmanageAction (self, QAction action)`

* * *

## Detailed Description

该QDesignerActionEditorInterface类允许您更改的Qt Designer的动作编辑器的焦点。

该QDesignerActionEditorInterface类不适合直接实例化。你可以检索界面_Qt Designer_使用的动作编辑器[QDesignerFormEditorInterface.actionEditor](qdesignerformeditorinterface.html#actionEditor)（）函数。

您可以使用控制，也可在动作编辑器的窗口，它的行动[manageAction](qdesigneractioneditorinterface.html#manageAction)（）和[unmanageAction](qdesigneractioneditorinterface.html#unmanageAction)（）函数。是受管理的动作_Qt Designer_在动作编辑器可用，而一个非讬管的操作将被忽略。

QDesignerActionEditorInterface还提供了[core](qdesigneractioneditorinterface.html#core)（ ）函数，你可以用它来检索指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象，并且[setFormWindow](qdesigneractioneditorinterface.html#setFormWindow)（ ）函数，使您可以更改当前选定窗体窗口。

* * *

## Method Documentation

```
QDesignerActionEditorInterface.__init__ (self, QWidget parent, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个动作编辑器界面与给定_parent_和在指定的窗口_flags_。

```
QDesignerFormEditorInterface QDesignerActionEditorInterface.core (self)
```

[](qdesignerformeditorinterface.html)

[返回一个指针_Qt Designer_目前的](qdesignerformeditorinterface.html)[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象。

```
QDesignerActionEditorInterface.manageAction (self, QAction action)
```

这种方法是抽象的，应在任何子类中重新实现。

指示_Qt Designer_管理规定_action_。是受管理的动作_Qt Designer_可在动作编辑器。

**See also** [unmanageAction](qdesigneractioneditorinterface.html#unmanageAction)（ ） 。

```
QDesignerActionEditorInterface.setFormWindow (self, QDesignerFormWindowInterface formWindow)
```

这种方法也是一个Qt槽与C + +的签名`void setFormWindow(QDesignerFormWindowInterface *)`。

这种方法是抽象的，应在任何子类中重新实现。

设置当前选定的表格窗口_formWindow_。

```
QDesignerActionEditorInterface.unmanageAction (self, QAction action)
```

这种方法是抽象的，应在任何子类中重新实现。

指示_Qt Designer_忽略指定的_action_。非讬管的动作是不是在动作编辑器。

**See also** [manageAction](qdesigneractioneditorinterface.html#manageAction)（ ） 。