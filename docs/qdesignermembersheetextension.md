# QDesignerMemberSheetExtension Class Reference

## [[QtDesigner](index.htm) module]

该QDesignerMemberSheetExtension类允许你操纵它使用Qt Designer的模式进行编辑信号和槽组态连接时显示一个窗口部件的成员函数。[More...](#details)

通过继承[QPyDesignerMemberSheetExtension](qpydesignermembersheetextension.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDesignerMemberSheetExtension)`
*   `int count (self)`
*   `QString declaredInClass (self, int index)`
*   `int indexOf (self, QString name)`
*   `bool inheritedFromWidget (self, int index)`
*   `bool isSignal (self, int index)`
*   `bool isSlot (self, int index)`
*   `bool isVisible (self, int index)`
*   `QString memberGroup (self, int index)`
*   `QString memberName (self, int index)`
*   `list-of-QByteArray parameterNames (self, int index)`
*   `list-of-QByteArray parameterTypes (self, int index)`
*   `setMemberGroup (self, int index, QString group)`
*   `setVisible (self, int index, bool b)`
*   `QString signature (self, int index)`

### Special Methods

*   `__len__ (self)`

* * *

## Detailed Description

该QDesignerMemberSheetExtension类允许你操纵它使用Qt Designer的模式进行编辑信号和槽组态连接时显示一个窗口部件的成员函数。

QDesignerMemberSheetExtension是通常用于查询控件的成员函数，并操控成员函数'出现在函数的集合_Qt Designer_的信号和槽的编辑模式。例如：

```
 QDesignerMemberSheetExtension *memberSheet  = 0;
 [QExtensionManager](qextensionmanager.html) manager = formEditor->extensionManager();

 memberSheet = qt_extension<QDesignerMemberSheetExtension*>(manager, widget);
 int index = memberSheet->indexOf(setEchoMode);
 memberSheet->setVisible(index, false);

 delete memberSheet;

```

当实现一个自定义的widget插件，一个指向_Qt Designer_目前的[QDesignerFormEditorInterface](qdesignerformeditorinterface.html)对象（`formEditor`在上面的例子）是由提供[QDesignerCustomWidgetInterface.initialize](qdesignercustomwidgetinterface.html#initialize)（ ）函数的参数。

成员表（以及任何其他扩展名） ，可以通过查询检索_Qt Designer_使用的扩展管理器[qt_extension](qextensionmanager.html#qt_extension)（）函数。当你要释放的扩展，你只需要删除的指针。

所有部件都使用默认成员表_Qt Designer_的信号和槽的编辑模式与Widget的成员函数。但QDesignerMemberSheetExtension还提供了用于创建自定义成员表扩展的接口。

**Warning:** _Qt Designer_使用QDesignerMemberSheetExtension便于信号和槽的编辑模式。当被要求2的部件之间的连接，_Qt Designer_将查询窗口小部件'成员表扩展。如果某个部件有一个实现的成员表的扩展，这个扩展将复盖默认成员表。

要创建成员表的扩展，你的扩展类必须继承自两个[QObject](qobject.html)和QDesignerMemberSheetExtension 。然后，因为我们正在实现一个接口，我们必须确保它是由已知的元对象系统中使用[Q_INTERFACES](qobject.html#Q_INTERFACES)（）宏：

```
 class MyMemberSheetExtension : public [QObject](qobject.html),
         public QDesignerMemberSheetExtension
 {
     Q_OBJECT
     Q_INTERFACES(QDesignerMemberSheetExtension)

 public:
     ...
 }

```

这使_Qt Designer_使用[qobject_cast](qobject.html#qobject_cast)（）来查询只是用一个接口支持[QObject](qobject.html)指针。

In _Qt Designer_未创建的扩展，直到你需要它们。出于这个原因，实施部件片扩展时，您还必须创建一个[QExtensionFactory](qextensionfactory.html)，即一个类，它能够让你的扩展的一个实例，并使用它注册_Qt Designer_的[extension manager](qextensionmanager.html)。

当一个部件的材料片扩展是必需的，_Qt Designer_的[extension manager](qextensionmanager.html)将通过其所有已注册的工厂运行要求[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）对每一直到第一个即能创建成员表扩展的小部件，被发现。这家工厂将使这个扩展的实例。如果没有找到这样的工厂，_Qt Designer_将使用默认的成员表。

有扩展的四个可用的类型_Qt Designer_：[QDesignerContainerExtension](qdesignercontainerextension.html)， QDesignerMemberSheetExtension ，[QDesignerPropertySheetExtension](qdesignerpropertysheetextension.html)和[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)。_Qt Designer_的行为是一样的具有多页的容器，一个成员表，属性表或任务菜单中的延期申请是否相关。

该[QExtensionFactory](qextensionfactory.html)类提供了一个标准的扩展工厂，并且也可以用作用于定义扩展工厂的接口。您可以创建一个新的[QExtensionFactory](qextensionfactory.html)并重新实现[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（）函数。例如：

```
 [QObject](qobject.html) *ANewExtensionFactory.createExtension([QObject](qobject.html) *object,
         const [QString](qstring.html) &iid, [QObject](qobject.html) *parent) const
 {
     if (iid != Q_TYPEID(QDesignerMemberSheetExtension))
         return 0;

     if (MyCustomWidget *widget = qobject_cast<MyCustomWidget*>
            (object))
         return new MyMemberSheetExtension(widget, parent);

     return 0;
 }

```

或者您可以使用现有的工厂，扩大[QExtensionFactory.createExtension](qextensionfactory.html#createExtension)（ ）函数，使工厂能够创建成员表扩展为好。例如：

```
 [QObject](qobject.html) *AGeneralExtensionFactory.createExtension([QObject](qobject.html) *object,
         const [QString](qstring.html) &iid, [QObject](qobject.html) *parent) const
 {
     MyCustomWidget *widget = qobject_cast<MyCustomWidget*>(object);

     if (widget && (iid == Q_TYPEID([QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)))) {
         return new MyTaskMenuExtension(widget, parent);

     } else if (widget && (iid == Q_TYPEID(QDesignerMemberSheetExtension))) {
         return new MyMemberSheetExtension(widget, parent);

     } else {
         return 0;
     }
 }

```

对于使用扩展类的完整示例，请参见[Task Menu Extension example](index.htm)。该示例显示了如何创建一个自定义的widget插件Qt Designer中，以及如何使用[QDesignerTaskMenuExtension](qdesignertaskmenuextension.html)类的自定义项添加到_Qt Designer_的任务菜单。

* * *

## Method Documentation

```
QDesignerMemberSheetExtension.__init__ (self)
```

```
QDesignerMemberSheetExtension.__init__ (self, QDesignerMemberSheetExtension)
```

```
int QDesignerMemberSheetExtension.count (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的成员函数分机的号码。

```
QString QDesignerMemberSheetExtension.declaredInClass (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回类，其中的成员函数在给定的名称_index_声明。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（ ） 。

```
int QDesignerMemberSheetExtension.indexOf (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

返回该成员函数通过给定的指定的索引_name_。

**See also** [memberName](qdesignermembersheetextension.html#memberName)（ ） 。

```
bool QDesignerMemberSheetExtension.inheritedFromWidget (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果给定的成员函数_index_从继承[QWidget](qwidget.html)，否则为False 。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（ ） 。

```
bool QDesignerMemberSheetExtension.isSignal (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果给定的成员函数_index_是一个信号，否则为False 。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（ ） 。

```
bool QDesignerMemberSheetExtension.isSlot (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果给定的成员函数_index_是一个插槽，否则为False 。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（ ） 。

```
bool QDesignerMemberSheetExtension.isVisible (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果给定的成员函数_index_在可见_Qt Designer_的信号和槽的编辑器，否则为False 。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（）和[setVisible](qdesignermembersheetextension.html#setVisible)（ ） 。

```
QString QDesignerMemberSheetExtension.memberGroup (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回函数与给定指定的成员组的名称_index_。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（）和[setMemberGroup](qdesignermembersheetextension.html#setMemberGroup)（ ） 。

```
QString QDesignerMemberSheetExtension.memberName (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回该成员函数的名称与给定_index_。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（ ） 。

```
list-of-QByteArray QDesignerMemberSheetExtension.parameterNames (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回该成员函数的参数名称与给定_index_作为[QByteArray](qbytearray.html)列表。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（）和[parameterTypes](qdesignermembersheetextension.html#parameterTypes)（ ） 。

```
list-of-QByteArray QDesignerMemberSheetExtension.parameterTypes (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回该成员函数的参数类型与给定_index_作为[QByteArray](qbytearray.html)列表。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（）和[parameterNames](qdesignermembersheetextension.html#parameterNames)（ ） 。

```
QDesignerMemberSheetExtension.setMemberGroup (self, int index, QString group)
```

这种方法是抽象的，应在任何子类中重新实现。

设置成员函数的成员组给定的_index_，以_group_。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（）和[memberGroup](qdesignermembersheetextension.html#memberGroup)（ ） 。

```
QDesignerMemberSheetExtension.setVisible (self, int index, bool b)
```

这种方法是抽象的，应在任何子类中重新实现。

If _visible_诚然，与成员函数在给定_index_在可见_Qt Designer_的信号和槽的编辑模式，否则该成员函数被隐藏。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（）和[isVisible](qdesignermembersheetextension.html#isVisible)（ ） 。

```
QString QDesignerMemberSheetExtension.signature (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回该成员函数的签名与给定_index_。

**See also** [indexOf](qdesignermembersheetextension.html#indexOf)（ ） 。

```
 QDesignerMemberSheetExtension.__len__ (self)
```