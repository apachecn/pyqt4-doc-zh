# QDesignerFormWindowManagerInterface Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerFormWindowManagerInterface类允许你操作的窗口形式在Qt Designer中收集和控制的Qt Designer的表格编辑操作。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QAction actionAdjustSize (self)`
*   `QAction actionBreakLayout (self)`
*   `QAction actionCopy (self)`
*   `QAction actionCut (self)`
*   `QAction actionDelete (self)`
*   `QAction actionFormLayout (self)`
*   `QAction actionGridLayout (self)`
*   `QAction actionHorizontalLayout (self)`
*   `QAction actionLower (self)`
*   `QAction actionPaste (self)`
*   `QAction actionRaise (self)`
*   `QAction actionRedo (self)`
*   `QAction actionSelectAll (self)`
*   `QAction actionSimplifyLayout (self)`
*   `QAction actionSplitHorizontal (self)`
*   `QAction actionSplitVertical (self)`
*   `QAction actionUndo (self)`
*   `QAction actionVerticalLayout (self)`
*   `QDesignerFormWindowInterface activeFormWindow (self)`
*   `addFormWindow (self, QDesignerFormWindowInterface formWindow)`
*   `QDesignerFormEditorInterface core (self)`
*   `QDesignerFormWindowInterface createFormWindow (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `QDesignerFormWindowInterface formWindow (self, int index)`
*   `int formWindowCount (self)`
*   `removeFormWindow (self, QDesignerFormWindowInterface formWindow)`
*   `setActiveFormWindow (self, QDesignerFormWindowInterface formWindow)`

### Qt Signals

*   `void activeFormWindowChanged (QDesignerFormWindowInterface *)`
*   `void formWindowAdded (QDesignerFormWindowInterface *)`
*   `void formWindowRemoved (QDesignerFormWindowInterface *)`

* * *

## Detailed Description

该QDesignerFormWindowManagerInterface类允许你操作的窗口形式在Qt Designer中收集和控制的Qt Designer的表格编辑操作。

QDesignerFormWindowManagerInterface不打算直接实例化。_Qt Designer_使用表单窗口管理器来控制各种形式的窗口在其工作区。你可以检索界面_Qt Designer_的使用构成了窗口管理器[QDesignerFormEditorInterface.formWindowManager](qdesignerformeditorinterface.html#formWindowManager)（）函数。例如：

```
         QDesignerFormWindowManagerInterface *manager = 0;
         [QDesignerFormWindowInterface](qdesignerformwindowinterface.html) *formWindow = 0;

         manager = formEditor->formWindowManager();
         formWindow = manager->formWindow(0);

         manager->setActiveFormWindow(formWindow);

```

当实现一个自定义的widget插件，一个指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。您必须在子类[QDesignerCustomWidgetInterface](qdesignercustomwidgetinterface.html)为你的插件暴露在Qt Designer中。

表格窗口管理器界面提供了[createFormWindow](qdesignerformwindowmanagerinterface.html#createFormWindow)（ ）函数，使您能够创建一个新的窗体窗口，您可以添加到窗体的窗口，该管理器维护的收集，使用[addFormWindow](qdesignerformwindowmanagerinterface.html#addFormWindow)（）槽。它也提供了[formWindowCount](qdesignerformwindowmanagerinterface.html#formWindowCount)（ ）函数返回当前经理人的控制之下形式的窗口的数量，[formWindow](qdesignerformwindowmanagerinterface.html#formWindow)（）函数返回与给定的索引相关联的形式的窗口，并且[activeFormWindow](qdesignerformwindowmanagerinterface.html#activeFormWindow)（ ）函数返回当前选定窗体窗口。该[removeFormWindow](qdesignerformwindowmanagerinterface.html#removeFormWindow)（ ）插槽可让您减少表格的窗口管理器必须保持数，以及[setActiveFormWindow](qdesignerformwindowmanagerinterface.html#setActiveFormWindow)（）槽允许您更改窗体窗口焦点_Qt Designer_的工作空间。

此外， QDesignerFormWindowManagerInterface包含的函数的集合，使您能够干预和控制_Qt Designer_的表单编辑操作。所有这些函数返回原来的动作，从而有可能进一步干预后传播的功能。

最后，该接口提供了当表单窗口被加入其中发射三种信号，当当前选择的窗口形式的变化时，或者当一个窗口的形式被除去，分别。所有的信号进行有问题的窗口形式作为其参数。

* * *

## Method Documentation

```
QDesignerFormWindowManagerInterface.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个接口与给定的_parent_表单窗口管理器。

```
QAction QDesignerFormWindowManagerInterface.actionAdjustSize (self)
```

[

允许你进行干预和控制_Qt Designer_的“调整大小”的行动。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionBreakLayout (self)
```

[

允许你进行干预和控制_Qt Designer_的“破布局”动作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionCopy (self)
```

[

允许你进行干预和控制_Qt Designer_的“复制”操作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionCut (self)
```

[

允许你进行干预和控制_Qt Designer_的“切”的动作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionDelete (self)
```

[

允许你进行干预和控制_Qt Designer_的“删除”操作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionFormLayout (self)
```

[

允许你进行干预和控制_Qt Designer_的“窗体布局”动作。该函数返回原来的动作。

FormWindowManagerPrivateMap * fwmpm = g_FormWindowManagerPrivateMap （）;

此功能被引入Qt的4.4 。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionGridLayout (self)
```

[

允许你进行干预和控制，为在表单窗口网格布局的要求_Qt Designer_的工作空间。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionHorizontalLayout (self)
```

[

允许你进行干预和控制，为在表单窗口水平布局的要求_Qt Designer_的工作空间。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionLower (self)
```

[

允许你进行干预和控制降低窗体窗口的作用_Qt Designer_的工作空间。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionPaste (self)
```

[

允许你进行干预和控制_Qt Designer_的“粘贴”操作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionRaise (self)
```

[

允许你进行干预和控制在一个窗口的形式筹集的作用_Qt Designer_的工作空间。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionRedo (self)
```

[

允许你进行干预和控制_Qt Designer_的“重做”操作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionSelectAll (self)
```

[

允许你进行干预和控制_Qt Designer_的“全选”操作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionSimplifyLayout (self)
```

[

允许你进行干预和控制_Qt Designer_的“简化布局”动作。该函数返回原来的动作。

此功能被引入Qt的4.4 。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionSplitHorizontal (self)
```

[

允许你进行干预和控制_Qt Designer_的“水平分割”的行动。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionSplitVertical (self)
```

[

允许你进行干预和控制_Qt Designer_的“垂直拆分”操作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionUndo (self)
```

[

允许你进行干预和控制_Qt Designer_的“撤消”操作。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QAction QDesignerFormWindowManagerInterface.actionVerticalLayout (self)
```

[

允许你进行干预和控制，为在表单窗口的垂直布局的要求_Qt Designer_的工作空间。该函数返回原来的动作。

](qaction.html)

[**See also**](qaction.html) [QAction](qaction.html)。

```
QDesignerFormWindowInterface QDesignerFormWindowManagerInterface.activeFormWindow (self)
```

[

返回当前活动窗体的窗口_Qt Designer_的工作空间。

](qdesignerformwindowinterface.html)

[**See also**](qdesignerformwindowinterface.html) [setActiveFormWindow](qdesignerformwindowmanagerinterface.html#setActiveFormWindow)（）和[removeFormWindow](qdesignerformwindowmanagerinterface.html#removeFormWindow)（ ） 。

```
QDesignerFormWindowManagerInterface.addFormWindow (self, QDesignerFormWindowInterface formWindow)
```

这种方法也是一个Qt槽与C + +的签名`void addFormWindow(QDesignerFormWindowInterface *)`。

将给定_formWindow_在窗口的集合，_Qt Designer_的形式的窗口管理器维护。

**See also** [formWindowAdded](qdesignerformwindowmanagerinterface.html#formWindowAdded)（ ） 。

```
QDesignerFormEditorInterface QDesignerFormWindowManagerInterface.core (self)
```

[](qdesignerformeditorinterface.html)

[返回一个指针_Qt Designer_目前的](qdesignerformeditorinterface.html)[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象。

```
QDesignerFormWindowInterface QDesignerFormWindowManagerInterface.createFormWindow (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个窗体窗口与给定_parent_和给定的窗口_flags_。

](qdesignerformwindowinterface.html)

[**See also**](qdesignerformwindowinterface.html) [addFormWindow](qdesignerformwindowmanagerinterface.html#addFormWindow)（ ） 。

```
QDesignerFormWindowInterface QDesignerFormWindowManagerInterface.formWindow (self, int index)
```

[

返回窗口的形式在给定的_index_。

](qdesignerformwindowinterface.html)

[**See also**](qdesignerformwindowinterface.html) [setActiveFormWindow](qdesignerformwindowmanagerinterface.html#setActiveFormWindow)（）和[removeFormWindow](qdesignerformwindowmanagerinterface.html#removeFormWindow)（ ） 。

```
int QDesignerFormWindowManagerInterface.formWindowCount (self)
```

返回的维护形式的窗口数量_Qt Designer_的形成窗口管理器。

```
QDesignerFormWindowManagerInterface.removeFormWindow (self, QDesignerFormWindowInterface formWindow)
```

这种方法也是一个Qt槽与C + +的签名`void removeFormWindow(QDesignerFormWindowInterface *)`。

删除给定的_formWindow_从窗户的集合，_Qt Designer_的形式的窗口管理器维护。

**See also** [formWindow](qdesignerformwindowmanagerinterface.html#formWindow)（）和[formWindowRemoved](qdesignerformwindowmanagerinterface.html#formWindowRemoved)（ ） 。

```
QDesignerFormWindowManagerInterface.setActiveFormWindow (self, QDesignerFormWindowInterface formWindow)
```

这种方法也是一个Qt槽与C + +的签名`void setActiveFormWindow(QDesignerFormWindowInterface *)`。

设置给定_formWindow_要在当前活动窗体的窗口_Qt Designer_的工作空间。

**See also** [activeFormWindow](qdesignerformwindowmanagerinterface.html#activeFormWindow)（）和[activeFormWindowChanged](qdesignerformwindowmanagerinterface.html#activeFormWindowChanged)（ ） 。

* * *

## Qt Signal Documentation

```
void activeFormWindowChanged (QDesignerFormWindowInterface *)
```

这是该信号的默认超载。

这个信号被发射时，在当前激活的形式窗口的内容_Qt Designer_工作空间的改变。一个指针，指向当前活动_formWindow_被作为参数传递。

**See also** [activeFormWindow](qdesignerformwindowmanagerinterface.html#activeFormWindow)（ ） 。

```
void formWindowAdded (QDesignerFormWindowInterface *)
```

这是该信号的默认超载。

当一个新的窗体窗口被添加到窗口的集合，这个信号被发射的_Qt Designer_的形式的窗口管理器维护。一个指向新_formWindow_被作为参数传递。

**See also** [addFormWindow](qdesignerformwindowmanagerinterface.html#addFormWindow)（）和[setActiveFormWindow](qdesignerformwindowmanagerinterface.html#setActiveFormWindow)（ ） 。

```
void formWindowRemoved (QDesignerFormWindowInterface *)
```

这是该信号的默认超载。

当一个表单窗口从窗口的集合中移除这个信号被发射的_Qt Designer_的形式的窗口管理器维护。一个指针，指向被删除_formWindow_被作为参数传递。

**See also** [removeFormWindow](qdesignerformwindowmanagerinterface.html#removeFormWindow)（ ） 。