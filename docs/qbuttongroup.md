# QButtonGroup Class Reference

## [[QtGui](index.htm) module]

该QButtonGroup类提供一个容器来组织按钮控件组。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `addButton (self, QAbstractButton)`
*   `addButton (self, QAbstractButton, int id)`
*   `QAbstractButton button (self, int id)`
*   `list-of-QAbstractButton buttons (self)`
*   `QAbstractButton checkedButton (self)`
*   `int checkedId (self)`
*   `bool exclusive (self)`
*   `int id (self, QAbstractButton button)`
*   `removeButton (self, QAbstractButton)`
*   `setExclusive (self, bool)`
*   `setId (self, QAbstractButton button, int id)`

### Qt Signals

*   `void buttonClicked (QAbstractButton *)`
*   `void buttonClicked (int)`
*   `void buttonPressed (QAbstractButton *)`
*   `void buttonPressed (int)`
*   `void buttonReleased (QAbstractButton *)`
*   `void buttonReleased (int)`

* * *

## Detailed Description

该QButtonGroup类提供一个容器来组织按钮控件组。

QButtonGroup提供了一个抽象的容器，其中按钮控件可以放置。它不提供此容器的可视化表示（见[QGroupBox](qgroupbox.html)对于一个容器控件） ，而是管理组中每个按钮的状态。

一个[exclusive](qbuttongroup.html#exclusive-prop)按钮组关闭所有可复（切换）按钮，除了被点击的之一。默认情况下，一个按钮组是独占的。在一个按钮组中的按钮通常是可复[QPushButton](qpushbutton.html)的，[QCheckBox](qcheckbox.html)ES （通常用于非排他性按钮组） ，或[QRadioButton](qradiobutton.html)秒。如果你创建一个专属按钮组，你应该确保该组中的一个按钮初步检查，否则，本集团将首先在没有任何按键被选中的状态。

按钮添加到组[addButton](qbuttongroup.html#addButton)（ ） 。它可以从组中删除[removeButton](qbuttongroup.html#removeButton)（ ） 。如果该组是独占的，目前检查按钮，可作为[checkedButton](qbuttongroup.html#checkedButton)（ ） 。如果点击一个按钮[buttonClicked](qbuttongroup.html#buttonClicked)（）信号被发射。对于独家组可检查的按钮，这意味着被选中的按钮。组中的按钮列表是由返回[buttons](qbuttongroup.html#buttons)（ ） 。

此外， QButtonGroup可以整数和按钮之间进行映射。您可以指定一个整数ID的按钮[setId](qbuttongroup.html#setId)（ ），并与检索[id](qbuttongroup.html#id)（ ） 。当前选中按钮的ID可与[checkedId](qbuttongroup.html#checkedId)（ ） ，并有一个重载信号[buttonClicked](qbuttongroup.html#buttonClicked)（），它发射的按钮的ID。这个id`-1`由QButtonGroup保留的意思是“没有这样的按钮” 。映射机制的目的是简化枚举值中的用户接口的表示。

* * *

## Method Documentation

```
QButtonGroup.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的空按钮组给定的_parent_。

**See also** [addButton](qbuttongroup.html#addButton)（）和[setExclusive](qbuttongroup.html#exclusive-prop)（ ） 。

```
QButtonGroup.addButton (self, QAbstractButton)
```

将给定_button_以本集团内部的按钮列表的末尾。一个ID将这个被分配到按钮[QButtonGroup](qbuttongroup.html)。自动分配的ID都保证是负的，从-2 。如果您还指定自己的ID，请使用正确的价值观，以避免冲突。

**See also** [removeButton](qbuttongroup.html#removeButton)（）和[buttons](qbuttongroup.html#buttons)（ ） 。

```
QButtonGroup.addButton (self, QAbstractButton, int id)
```

将给定_button_在按钮组中，与给定_id_。建议在分配唯一积极的IDS 。

**See also** [removeButton](qbuttongroup.html#removeButton)（）和[buttons](qbuttongroup.html#buttons)（ ） 。

```
QAbstractButton QButtonGroup.button (self, int id)
```

[

返回按钮具有指定_id_，或者0，如果没有这样的按钮存在。

这个函数是Qt 4.1中引入。

```
list-of-QAbstractButton QButtonGroup.buttons (self)
```

返回该组的按钮列表。这可能是空的。

](qabstractbutton.html)

[**See also**](qabstractbutton.html) [addButton](qbuttongroup.html#addButton)（）和[removeButton](qbuttongroup.html#removeButton)（ ） 。

```
QAbstractButton QButtonGroup.checkedButton (self)
```

[

返回按钮组的检查按钮，或者0，如果没有按钮被选中。

](qabstractbutton.html)

[**See also**](qabstractbutton.html) [buttonClicked](qbuttongroup.html#buttonClicked)（ ） 。

```
int QButtonGroup.checkedId (self)
```

返回的的ID[checkedButton](qbuttongroup.html#checkedButton)（ ） ，或-1，如果检查没有按钮。

这个函数是Qt 4.1中引入。

**See also** [setId](qbuttongroup.html#setId)（ ） 。

```
bool QButtonGroup.exclusive (self)
```

```
int QButtonGroup.id (self, QAbstractButton button)
```

返回的ID所指定_button_，或-1，如果没有这样的按钮存在。

这个函数是Qt 4.1中引入。

**See also** [setId](qbuttongroup.html#setId)（ ） 。

```
QButtonGroup.removeButton (self, QAbstractButton)
```

删除给定的_button_从按钮组。

**See also** [addButton](qbuttongroup.html#addButton)（）和[buttons](qbuttongroup.html#buttons)（ ） 。

```
QButtonGroup.setExclusive (self, bool)
```

```
QButtonGroup.setId (self, QAbstractButton button, int id)
```

设置_id_为指定的_button_。需要注意的是_id_不能为-1。

这个函数是Qt 4.1中引入。

**See also** [id](qbuttongroup.html#id)（ ） 。

* * *

## Qt Signal Documentation

```
void buttonClicked (QAbstractButton *)
```

这是该信号的默认超载。

这个信号被发射给定的时_button_被点击。当它第一次按下一个按钮被点击，然后释放，当它的快捷键键入，或编程时[QAbstractButton.click](qabstractbutton.html#click)（）或[QAbstractButton.animateClick](qabstractbutton.html#animateClick)（）被调用。

**See also** [checkedButton](qbuttongroup.html#checkedButton)（）和[QAbstractButton.clicked](qabstractbutton.html#clicked)（ ） 。

```
void buttonClicked (int)
```

这个信号被发射时，在给定的一个按钮_id_被点击。

**See also** [checkedButton](qbuttongroup.html#checkedButton)（）和[QAbstractButton.clicked](qabstractbutton.html#clicked)（ ） 。

```
void buttonPressed (QAbstractButton *)
```

这是该信号的默认超载。

这个信号被发射给定的时_button_被按下。

这个函数中引入了Qt 4.2中。

**See also** [QAbstractButton.pressed](qabstractbutton.html#pressed)（ ） 。

```
void buttonPressed (int)
```

这个信号被发射时，在给定的一个按钮_id_被按下。

这个函数中引入了Qt 4.2中。

**See also** [QAbstractButton.pressed](qabstractbutton.html#pressed)（ ） 。

```
void buttonReleased (QAbstractButton *)
```

这是该信号的默认超载。

这个信号被发射给定的时_button_被释放。

这个函数中引入了Qt 4.2中。

**See also** [QAbstractButton.released](qabstractbutton.html#released)（ ） 。

```
void buttonReleased (int)
```

这个信号被发射时，在给定的一个按钮_id_被释放。

这个函数中引入了Qt 4.2中。

**See also** [QAbstractButton.released](qabstractbutton.html#released)（ ） 。