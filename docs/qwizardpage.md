# QWizardPage Class Reference

## [[QtGui](index.htm) module]

该QWizardPage类是向导页面的基类。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `QString buttonText (self, QWizard.WizardButton which)`
*   `cleanupPage (self)`
*   `QVariant field (self, QString name)`
*   `initializePage (self)`
*   `bool isCommitPage (self)`
*   `bool isComplete (self)`
*   `bool isFinalPage (self)`
*   `int nextId (self)`
*   `QPixmap pixmap (self, QWizard.WizardPixmap which)`
*   `registerField (self, QString name, QWidget widget, str property = None, signal changedSignal = 0)`
*   `registerField (self, QString name, QWidget widget, str property = None, SIGNAL() changedSignal = 0)`
*   `setButtonText (self, QWizard.WizardButton which, QString text)`
*   `setCommitPage (self, bool commitPage)`
*   `setField (self, QString name, QVariant value)`
*   `setFinalPage (self, bool finalPage)`
*   `setPixmap (self, QWizard.WizardPixmap which, QPixmap pixmap)`
*   `setSubTitle (self, QString subTitle)`
*   `setTitle (self, QString title)`
*   `QString subTitle (self)`
*   `QString title (self)`
*   `bool validatePage (self)`
*   `QWizard wizard (self)`

### Qt Signals

*   `void completeChanged ()`

* * *

## Detailed Description

该QWizardPage类是向导页面的基类。

[QWizard](qwizard.html)代表一个向导。每个页面都是一个QWizardPage 。当您创建自己的向导，您可以直接使用QWizardPage ，或者你可以继承它进行更多的控制。

一个页面有如下属性，这是由提供[QWizard](qwizard.html)：一[title](qwizardpage.html#title-prop)，一[subTitle](qwizardpage.html#subTitle-prop)和[set of pixmaps](qwizardpage.html#setPixmap)。看[Elements of a Wizard Page](qwizard.html#elements-of-a-wizard-page)了解详情。当一个页面被（使用添加向导[QWizard.addPage](qwizard.html#addPage)（）或[QWizard.setPage](qwizard.html#setPage)（）），[wizard](qwizardpage.html#wizard)（ ）返回一个指向相关[QWizard](qwizard.html)对象。

页面提供了可重新实现以提供自定义行为五个虚拟函数：

*   [initializePage](qwizardpage.html#initializePage)() is called to initialize the page's contents when the user clicks the wizard's **Next** button. If you want to derive the page's default from what the user entered on previous pages, this is the function to reimplement.
*   [cleanupPage](qwizardpage.html#cleanupPage)() is called to reset the page's contents when the user clicks the wizard's **Back** button.
*   [validatePage](qwizardpage.html#validatePage)() validates the page when the user clicks **Next** or **Finish**. It is often used to show an error message if the user has entered incomplete or invalid information.
*   [nextId](qwizardpage.html#nextId)() returns the ID of the next page. It is useful when [creating non-linear wizards](qwizard.html#creating-non-linear-wizards), which allow different traversal paths based on the information provided by the user.
*   [isComplete](qwizardpage.html#isComplete)() is called to determine whether the **Next** and/or **Finish** button should be enabled or disabled. If you reimplement [isComplete](qwizardpage.html#isComplete)(), also make sure that [completeChanged](qwizardpage.html#completeChanged)() is emitted whenever the complete state changes.

一般情况下，**Next**按钮和**Finish**向导按钮是互斥的。如果[isFinalPage](qwizardpage.html#isFinalPage)（ ）返回True ，**Finish**可用，否则**Next**是可用的。默认情况下，[isFinalPage](qwizardpage.html#isFinalPage)（ ）为真，只有当[nextId](qwizardpage.html#nextId)（ ）返回-1 。如果你想显示**Next**和**Final**同时一个页面（让用户执行一个“早完成” ） ，调用setFinalPage （真）在该网页。对于支持早期完成向导，您可能还需要设置[HaveNextButtonOnLastPage](qwizard.html#WizardOption-enum)和[HaveFinishButtonOnEarlyPages](qwizard.html#WizardOption-enum)在该向导的选项。

在许多向导页面的内容可能会影响后面的页的字段的缺省值。为了便于页面之间进行通信，[QWizard](qwizard.html)支持["field" mechanism](qwizard.html#registering-and-using-fields)这允许您注册一个字段（例如，一[QLineEdit](qlineedit.html)）上的一个页面，访问任何网页它的价值。字段是全球整个向导，很容易让任何一个网页访问另一个页面存储的信息，而不必把所有的逻辑[QWizard](qwizard.html)或具有明确的页面了解对方。字段使用登记[registerField](qwizardpage.html#registerField)（ ），并且可以在任何时间使用访问[field](qwizardpage.html#field)（）和[setField](qwizardpage.html#setField)（ ） 。

* * *

## Method Documentation

```
QWizardPage.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个向导页中给定的_parent_。

当页面使用插入向导[QWizard.addPage](qwizard.html#addPage)（）或[QWizard.setPage](qwizard.html#setPage)（ ） ，父被自动设置为向导。

**See also** [wizard](qwizardpage.html#wizard)（ ） 。

```
QString QWizardPage.buttonText (self, QWizard.WizardButton which)
```

按钮返回文本_which_此页面上。

如果使用的是文本有奔集[setButtonText](qwizardpage.html#setButtonText)（ ） ，则返回该文本。否则，如果文本已经使用设置[QWizard.setButtonText](qwizard.html#setButtonText)（ ） ，则返回该文本。

默认情况下，按钮上的文本取决于[QWizard.wizardStyle](qwizard.html#wizardStyle-prop)。例如，在Mac OS X中，**Next**按钮被称为**Continue**。

**See also** [setButtonText](qwizardpage.html#setButtonText)（ ）[QWizard.buttonText](qwizard.html#buttonText)（）和[QWizard.setButtonText](qwizard.html#setButtonText)（ ） 。

```
QWizardPage.cleanupPage (self)
```

这个虚函数被调用[QWizard.cleanupPage](qwizard.html#cleanupPage)（）用户通过点击离开页面时**Back**（除非[QWizard.IndependentPages](qwizard.html#WizardOption-enum)选项设置） 。

默认实现重置页面的栏位为原始值（他们之前所拥有的价值观[initializePage](qwizardpage.html#initializePage)（ ）被调用） 。

**See also** [QWizard.cleanupPage](qwizard.html#cleanupPage)（ ）[initializePage](qwizardpage.html#initializePage)（）和[QWizard.IndependentPages](qwizard.html#WizardOption-enum)。

```
QVariant QWizardPage.field (self, QString name)
```

返回字段的所谓的值_name_。

此功能可用于访问向导的任何页面上的字段。这等同于调用[wizard](qwizardpage.html#wizard)（） - \u003e[field](qwizard.html#field)（_name_） 。

例如：

```
 void OutputFilesPage.initializePage()
 {
     [QString](qstring.html) className = field("className").toString();
     headerLineEdit->setText(className.toLower() + ".h");
     implementationLineEdit->setText(className.toLower() + ".cpp");
     outputDirLineEdit->setText([QDir](qdir.html).convertSeparators([QDir](qdir.html).tempPath()));
 }

```

**See also** [QWizard.field](qwizard.html#field)（ ）[setField](qwizardpage.html#setField)（）和[registerField](qwizardpage.html#registerField)（ ） 。

```
QWizardPage.initializePage (self)
```

这个虚函数被调用[QWizard.initializePage](qwizard.html#initializePage)（ ）编写的网页也显示无论是作为一个结果之前[QWizard.restart](qwizard.html#restart)（）被调用时，或者当用户点击的结果**Next**。 （然而，如果[QWizard.IndependentPages](qwizard.html#WizardOption-enum)选项设置，此功能只在第一次调用的页面显示。 ）

通过重新实现这个功能，可以确保基于前几页信息页面的栏已正确初始化。例如：

```
 void OutputFilesPage.initializePage()
 {
     [QString](qstring.html) className = field("className").toString();
     headerLineEdit->setText(className.toLower() + ".h");
     implementationLineEdit->setText(className.toLower() + ".cpp");
     outputDirLineEdit->setText([QDir](qdir.html).convertSeparators([QDir](qdir.html).tempPath()));
 }

```

默认实现不执行任何操作。

**See also** [QWizard.initializePage](qwizard.html#initializePage)（ ）[cleanupPage](qwizardpage.html#cleanupPage)（）和[QWizard.IndependentPages](qwizard.html#WizardOption-enum)。

```
bool QWizardPage.isCommitPage (self)
```

返回True如果该页面是一个提交页面，否则返回False 。

**See also** [setCommitPage](qwizardpage.html#setCommitPage)（ ） 。

```
bool QWizardPage.isComplete (self)
```

这个虚函数被调用[QWizard](qwizard.html)以确定是否**Next** or **Finish**按钮应该被启用或禁用。

默认实现返回True，如果所有[mandatory fields](qwizard.html#mandatory-fields)充满，否则返回False 。

如果重新实现此功能，请确保发射[completeChanged](qwizardpage.html#completeChanged)（ ） ，从您的实现，只要在isComplete的值（ ）变化的其馀部分。这确保了[QWizard](qwizard.html)更新其按钮的启用或禁用状态。重新实现的一个示例是可 [here](http://qt.nokia.com/doc/qq/qq22-qwizard.html#validatebeforeitstoolate)。

**See also** [completeChanged](qwizardpage.html#completeChanged)（）和[isFinalPage](qwizardpage.html#isFinalPage)（ ） 。

```
bool QWizardPage.isFinalPage (self)
```

调用此函数由[QWizard](qwizard.html)以确定是否**Finish**按钮应显示该页面与否。

默认情况下，如果没有下一个页面（即返回True ，[nextId](qwizardpage.html#nextId)（ ）返回-1 ） ，否则返回False 。

通过显式调用setFinalPage （真） ，可以让用户执行“最早完成” 。

**See also** [isComplete](qwizardpage.html#isComplete)（）和[QWizard.HaveFinishButtonOnEarlyPages](qwizard.html#WizardOption-enum)。

```
int QWizardPage.nextId (self)
```

这个虚函数被调用[QWizard.nextId](qwizard.html#nextId)（ ）来找出当用户点击显示哪些页面**Next**按钮。

返回值是下一个页面的ID ，或-1，如果没有页面如下。

默认情况下，这个函数返回的最低编号大于当前页面的ID ，或-1，如果没有这样的标识。

通过重新实现此功能，您可以指定一个动态的页面顺序。例如：

```
 int IntroPage.nextId() const
 {
     if (evaluateRadioButton->isChecked()) {
         return LicenseWizard.Page_Evaluate;
     } else {
         return LicenseWizard.Page_Register;
     }
 }

```

**See also** [QWizard.nextId](qwizard.html#nextId)（ ） 。

```
QPixmap QWizardPage.pixmap (self, QWizard.WizardPixmap which)
```

[

返回角色像素图组_which_。

](qpixmap.html)

[像素图，也可以使用整个向导设置](qpixmap.html)[QWizard.setPixmap](qwizard.html#setPixmap)（ ） ，在这种情况下，他们申请不指定像素图的所有页面。

**See also** [setPixmap](qwizardpage.html#setPixmap)（ ）[QWizard.pixmap](qwizard.html#pixmap)（）和[Elements of a Wizard Page](qwizard.html#elements-of-a-wizard-page)。

```
QWizardPage.registerField (self, QString name, QWidget widget, str property = None, signal changedSignal = 0)
```

创建一个名为场_name_用给定的相关联_property_的给定_widget_。从那时起，该属性使用变得方便[field](qwizardpage.html#field)（）和[setField](qwizardpage.html#setField)（ ） 。

字段是全球整个向导，很容易让任何一个网页访问另一个页面存储的信息，而不必把所有的逻辑[QWizard](qwizard.html)或具有明确的页面了解对方。

If _name_带星号结尾（`*`） ，该字段是必填字段。当一个页面有必填字段中，**Next**和/或**Finish**按钮被激活，只有当所有必填字段被填充。这需要_changedSignal_被指定的，告诉[QWizard](qwizard.html)重新检查的必填字段存储的值。

[QWizard](qwizard.html)知道最常见的Qt部件。对于这些（或其子类） ，你不需要指定_property_或_changedSignal_。下表列出了这些小部件：

| Widget | Property | Change Notification Signal |
| --- | --- | --- |
| [QAbstractButton](qabstractbutton.html) | bool [checked](qabstractbutton.html#checked-prop) | [toggled()](qabstractbutton.html#toggled) |
| [QAbstractSlider](qabstractslider.html) | int [value](qabstractslider.html#value-prop) | [valueChanged()](qabstractslider.html#valueChanged) |
| [QComboBox](qcombobox.html) | int [currentIndex](qcombobox.html#currentIndex-prop) | [currentIndexChanged()](qcombobox.html#currentIndexChanged) |
| [QDateTimeEdit](qdatetimeedit.html) | [QDateTime](qdatetime.html) [dateTime](qdatetimeedit.html#dateTime-prop) | [dateTimeChanged()](qdatetimeedit.html#dateTimeChanged) |
| [QLineEdit](qlineedit.html) | [QString](qstring.html) [text](qlineedit.html#text-prop) | [textChanged()](qlineedit.html#textChanged) |
| [QListWidget](qlistwidget.html) | int [currentRow](qlistwidget.html#currentRow-prop) | [currentRowChanged()](qlistwidget.html#currentRowChanged) |
| [QSpinBox](qspinbox.html) | int [value](qspinbox.html#value-prop) | [valueChanged()](qspinbox.html#valueChanged) |

您可以使用[QWizard.setDefaultProperty](qwizard.html#setDefaultProperty)（ ）将条目添加到该表或复盖现有条目。

考虑现场“装” ，[QWizard](qwizard.html)简单地检查他们的当前值不等于其原始值（它们之前所拥有的价值[initializePage](qwizardpage.html#initializePage)（ ）被调用） 。为[QLineEdit](qlineedit.html)，它还会检查[hasAcceptableInput()](qlineedit.html#acceptableInput-prop)返回True ，兑现任何验证或面具。

[QWizard](qwizard.html)提供方便的必填字段机制。它可以通过重新实现被绕过[QWizardPage.isComplete](qwizardpage.html#isComplete)（ ） 。

**See also** [field](qwizardpage.html#field)（ ）[setField](qwizardpage.html#setField)（）和[QWizard.setDefaultProperty](qwizard.html#setDefaultProperty)（ ） 。

```
QWizardPage.registerField (self, QString name, QWidget widget, str property = None, SIGNAL() changedSignal = 0)
```

```
QWizardPage.setButtonText (self, QWizard.WizardButton which, QString text)
```

按钮设置文本_which_要_text_此页面上。

默认情况下，按钮上的文本取决于[QWizard.wizardStyle](qwizard.html#wizardStyle-prop)，而是可以被重新定义为向导如使用整体[QWizard.setButtonText](qwizard.html#setButtonText)（ ） 。

**See also** [buttonText](qwizardpage.html#buttonText)（ ）[QWizard.setButtonText](qwizard.html#setButtonText)（）和[QWizard.buttonText](qwizard.html#buttonText)（ ） 。

```
QWizardPage.setCommitPage (self, bool commitPage)
```

设置这个页面是一个提交页面，如果_commitPage_为True，否则，设置它是一个正常的页面。

一个提交页面是代表它无法通过单击撤消的操作页面**Back** or **Cancel**。

A **Commit**按钮取代了**Next**提交页面上按钮。点击这个按钮简单地调用[QWizard.next](qwizard.html#next)（ ）就像点击**Next**一样。

直接提交页面中输入一个页面都有它**Back**按钮禁用。

**See also** [isCommitPage](qwizardpage.html#isCommitPage)（ ） 。

```
QWizardPage.setField (self, QString name, QVariant value)
```

设置字段中称为值_name_至_value_。

此功能可用于在向导的任何页面上设置的字段。这等同于调用[wizard](qwizardpage.html#wizard)（） - \u003e[setField(_name_, _value_)](qwizard.html#setField)。

**See also** [QWizard.setField](qwizard.html#setField)（ ）[field](qwizardpage.html#field)（）和[registerField](qwizardpage.html#registerField)（ ） 。

```
QWizardPage.setFinalPage (self, bool finalPage)
```

显式设置此页面是最终的，如果_finalPage_是真实的。

调用setFinalPage （真）后，[isFinalPage](qwizardpage.html#isFinalPage)（）返回True，并且**Finish**按钮是可见的（如果启用[isComplete](qwizardpage.html#isComplete)（ ）返回True ） 。

调用setFinalPage （假）后，[isFinalPage](qwizardpage.html#isFinalPage)（ ）返回True ，如果[nextId](qwizardpage.html#nextId)（ ）返回-1 ，否则返回False 。

**See also** [isFinalPage](qwizardpage.html#isFinalPage)（ ）[isComplete](qwizardpage.html#isComplete)（）和[QWizard.HaveFinishButtonOnEarlyPages](qwizard.html#WizardOption-enum)。

```
QWizardPage.setPixmap (self, QWizard.WizardPixmap which, QPixmap pixmap)
```

设置像素图的作用_which_至_pixmap_。

该像素图所使用的[QWizard](qwizard.html)显示一个页面时。其中像素图实际使用依赖于[wizard style](qwizard.html#wizard-look-and-feel)。

像素图，也可以使用整个向导设置[QWizard.setPixmap](qwizard.html#setPixmap)（ ） ，在这种情况下，他们申请不指定像素图的所有页面。

**See also** [pixmap](qwizardpage.html#pixmap)（ ）[QWizard.setPixmap](qwizard.html#setPixmap)（）和[Elements of a Wizard Page](qwizard.html#elements-of-a-wizard-page)。

```
QWizardPage.setSubTitle (self, QString subTitle)
```

```
QWizardPage.setTitle (self, QString title)
```

```
QString QWizardPage.subTitle (self)
```

```
QString QWizardPage.title (self)
```

```
bool QWizardPage.validatePage (self)
```

这个虚函数被调用[QWizard.validateCurrentPage](qwizard.html#validateCurrentPage)（ ）当用户点击**Next** or **Finish**执行一些最后一分钟的验证。如果返回True，则下一个页面显示（或向导完成），否则，在当前页面熬夜。

默认实现返回True 。

如果可能的话，它通常是更好的风格禁用**Next** or **Finish**按钮（通过指定[mandatory fields](qwizard.html#mandatory-fields)或者重新实现[isComplete](qwizardpage.html#isComplete)（ ） ），而不是重新实现validatePage （ ） 。

**See also** [QWizard.validateCurrentPage](qwizard.html#validateCurrentPage)（）和[isComplete](qwizardpage.html#isComplete)（ ） 。

```
QWizard QWizardPage.wizard (self)
```

[](qwizard.html)

[返回与此页面，或0相关的向导，如果这个页面没有被插入](qwizard.html)[QWizard](qwizard.html)还没有。

**See also** [QWizard.addPage](qwizard.html#addPage)（）和[QWizard.setPage](qwizard.html#setPage)（ ） 。

* * *

## Qt Signal Documentation

```
void completeChanged ()
```

这是该信号的默认超载。

这个信号被发射时的页面（即，值的完整状态[isComplete](qwizardpage.html#isComplete)（））的变化。

如果你重新实现[isComplete](qwizardpage.html#isComplete)（ ） ，一定要发出completeChanged （ ）时的值[isComplete](qwizardpage.html#isComplete)（ ）的变化，以确保[QWizard](qwizard.html)更新其按钮的启用或禁用状态。

**See also** [isComplete](qwizardpage.html#isComplete)（ ） 。