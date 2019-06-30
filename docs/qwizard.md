# QWizard Class Reference

## [[QtGui](index.htm) module]

该QWizard类提供了一个向导框架。[More...](#details)

继承[QDialog](qdialog.html)。

### Types

*   `enum WizardButton { BackButton, NextButton, CommitButton, FinishButton, ..., Stretch }`
*   `enum WizardOption { IndependentPages, IgnoreSubTitles, ExtendedWatermarkPixmap, NoDefaultButton, ..., HaveCustomButton3 }`
*   `class **[WizardOptions](index.htm)**`
*   `enum WizardPixmap { WatermarkPixmap, LogoPixmap, BannerPixmap, BackgroundPixmap }`
*   `enum WizardStyle { ClassicStyle, ModernStyle, MacStyle, AeroStyle }`

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `int addPage (self, QWizardPage page)`
*   `back (self)`
*   `QAbstractButton button (self, WizardButton which)`
*   `QString buttonText (self, WizardButton which)`
*   `cleanupPage (self, int id)`
*   `int currentId (self)`
*   `QWizardPage currentPage (self)`
*   `done (self, int result)`
*   `bool event (self, QEvent event)`
*   `QVariant field (self, QString name)`
*   `bool hasVisitedPage (self, int id)`
*   `initializePage (self, int id)`
*   `next (self)`
*   `int nextId (self)`
*   `WizardOptions options (self)`
*   `QWizardPage page (self, int id)`
*   `list-of-int pageIds (self)`
*   `paintEvent (self, QPaintEvent event)`
*   `QPixmap pixmap (self, WizardPixmap which)`
*   `removePage (self, int id)`
*   `resizeEvent (self, QResizeEvent event)`
*   `restart (self)`
*   `setButton (self, WizardButton which, QAbstractButton button)`
*   `setButtonLayout (self, list-of-QWizard.WizardButton layout)`
*   `setButtonText (self, WizardButton which, QString text)`
*   `setDefaultProperty (self, str className, str property, str changedSignal)`
*   `setField (self, QString name, QVariant value)`
*   `setOption (self, WizardOption option, bool on = True)`
*   `setOptions (self, WizardOptions options)`
*   `setPage (self, int id, QWizardPage page)`
*   `setPixmap (self, WizardPixmap which, QPixmap pixmap)`
*   `setSideWidget (self, QWidget widget)`
*   `setStartId (self, int id)`
*   `setSubTitleFormat (self, Qt.TextFormat format)`
*   `setTitleFormat (self, Qt.TextFormat format)`
*   `setVisible (self, bool visible)`
*   `setWizardStyle (self, WizardStyle style)`
*   `QWidget sideWidget (self)`
*   `QSize sizeHint (self)`
*   `int startId (self)`
*   `Qt.TextFormat subTitleFormat (self)`
*   `bool testOption (self, WizardOption option)`
*   `Qt.TextFormat titleFormat (self)`
*   `bool validateCurrentPage (self)`
*   `list-of-int visitedPages (self)`
*   `WizardStyle wizardStyle (self)`

### Qt Signals

*   `void currentIdChanged (int)`
*   `void customButtonClicked (int)`
*   `void helpRequested ()`
*   `void pageAdded (int)`
*   `void pageRemoved (int)`

* * *

## Detailed Description

该QWizard类提供了一个向导框架。

一个向导（也称为Mac OS X上的助手）是一种特殊类型的输入对话框，它包含的页面顺序。一个向导的目的是通过一步一个工艺步骤引导用户。奇才是复杂或罕见的任务，用户可能会发现很难学到有用的。

QWizard继承[QDialog](qdialog.html)并表示一个向导。每个页面都是一个[QWizardPage](qwizardpage.html)（一[QWidget](qwidget.html)子类） 。要创建自己的向导，你可以直接使用这些类，或者你可以继承他们进行更多的控制。

主题：

### A Trivial Example

下面的例子演示了如何创建向导页面，并将其添加到向导。对于更高级的示例，请参见[Class Wizard](index.htm)和[License Wizard](index.htm)。

```
 [QWizardPage](qwizardpage.html) *createIntroPage()
 {
     [QWizardPage](qwizardpage.html) *page = new [QWizardPage](qwizardpage.html);
     page->setTitle("Introduction");

     [QLabel](qlabel.html) *label = new [QLabel](qlabel.html)("This wizard will help you register your copy "
                                "of Super Product Two.");
     label->setWordWrap(true);

     [QVBoxLayout](qvboxlayout.html) *layout = new [QVBoxLayout](qvboxlayout.html);
     layout->addWidget(label);
     page->setLayout(layout);

     return page;
 }

 [QWizardPage](qwizardpage.html) *createRegistrationPage()
 {
     ...
 }

 [QWizardPage](qwizardpage.html) *createConclusionPage()
 {
     ...
 }

 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html) app(argc, argv);

     [QString](qstring.html) translatorFileName = QLatin1String("qt_");
     translatorFileName += [QLocale](qlocale.html).system().name();
     [QTranslator](qtranslator.html) *translator = new [QTranslator](qtranslator.html)(&app);
     if (translator->load(translatorFileName, [QLibraryInfo](qlibraryinfo.html).location([QLibraryInfo](qlibraryinfo.html).TranslationsPath)))
         app.installTranslator(translator);

     QWizard wizard;
     wizard.addPage(createIntroPage());
     wizard.addPage(createRegistrationPage());
     wizard.addPage(createConclusionPage());

     wizard.setWindowTitle("Trivial Wizard");
 #ifdef Q_OS_SYMBIAN
     wizard.showMaximized();
 #else
     wizard.show();
 #endif

     return app.exec();
 }

```

### Wizard Look and Feel

QWizard支持四个精灵的样子：

*   [ClassicStyle](qwizard.html#WizardStyle-enum)
*   [ModernStyle](qwizard.html#WizardStyle-enum)
*   [MacStyle](qwizard.html#WizardStyle-enum)
*   [AeroStyle](qwizard.html#WizardStyle-enum)

你可以明确地设置一下使用使用[setWizardStyle](qwizard.html#wizardStyle-prop)（ ） （例如，如果你想同样的外观在所有平台） 。

| [ClassicStyle](qwizard.html#WizardStyle-enum) | [ModernStyle](qwizard.html#WizardStyle-enum) | [MacStyle](qwizard.html#WizardStyle-enum) | [AeroStyle](qwizard.html#WizardStyle-enum) |
| --- | --- | --- | --- |
| ![](../img/qtwizard-classic1.png) | ![](../img/qtwizard-modern1.png) | ![](../img/qtwizard-mac1.png) | ![](../img/qtwizard-aero1.png) |
| ![](../img/qtwizard-classic2.png) | ![](../img/qtwizard-modern2.png) | ![](../img/qtwizard-mac2.png) | ![](../img/qtwizard-aero2.png) |

注意：[AeroStyle](qwizard.html#WizardStyle-enum)只有在Windows Vista系统上的alpha合成启用效果。[ModernStyle](qwizard.html#WizardStyle-enum)作为当不满足这个条件的后备。

除了精灵的风格，也有控制精灵的外观和感觉的几个选项。这些可以使用设置[setOption](qwizard.html#setOption)（）或[setOptions](qwizard.html#options-prop)（ ） 。例如，[HaveHelpButton](qwizard.html#WizardOption-enum)让QWizard秀一**Help**连同其他向导按钮按钮。

使用的向导按钮的顺序，你甚至可以更改为任意顺序[setButtonLayout](qwizard.html#setButtonLayout)（ ），您最多可以添加三个自定义按钮（例如，**Print**按钮）按钮行。这是通过调用实现[setButton](qwizard.html#setButton)（）或[setButtonText](qwizard.html#setButtonText)（ ）与[CustomButton1](qwizard.html#WizardButton-enum)，[CustomButton2](qwizard.html#WizardButton-enum)或[CustomButton3](qwizard.html#WizardButton-enum)设置按钮，并且通过使[HaveCustomButton1](qwizard.html#WizardOption-enum)，[HaveCustomButton2](qwizard.html#WizardOption-enum)或[HaveCustomButton3](qwizard.html#WizardOption-enum)选项。每当用户点击自定义按钮，[customButtonClicked](qwizard.html#customButtonClicked)（）被发射。例如：

```
         wizard()->setButtonText(QWizard.CustomButton1, tr("&Print"));
         wizard()->setOption(QWizard.HaveCustomButton1, true);
         connect(wizard(), SIGNAL(customButtonClicked(int)),
                 this, SLOT(printButtonClicked()));

```

### Elements of a Wizard Page

向导包括一个序列的[QWizardPage](qwizardpage.html)秒。在任何时间，仅示出一个页面。一个页面具有以下属性：

*   A [title](qwizardpage.html#title-prop).
*   A [subTitle](qwizardpage.html#subTitle-prop).
*   A set of pixmaps, which may or may not be honored, depending on the wizard's style:
    *   [WatermarkPixmap](qwizard.html#WizardPixmap-enum) (used by [ClassicStyle](qwizard.html#WizardStyle-enum) and [ModernStyle](qwizard.html#WizardStyle-enum))
    *   [BannerPixmap](qwizard.html#WizardPixmap-enum) (used by [ModernStyle](qwizard.html#WizardStyle-enum))
    *   [LogoPixmap](qwizard.html#WizardPixmap-enum) (used by [ClassicStyle](qwizard.html#WizardStyle-enum) and [ModernStyle](qwizard.html#WizardStyle-enum))
    *   [BackgroundPixmap](qwizard.html#WizardPixmap-enum) (used by [MacStyle](qwizard.html#WizardStyle-enum))

图中初级讲座展示QWizard如何呈现这些属性，假设他们都是现在和[ModernStyle](qwizard.html#WizardStyle-enum)用于：

![](../img/qtwizard-nonmacpage.png)

当[subTitle](qwizardpage.html#subTitle-prop)被设置， QWizard在报头中显示它，在这种情况下，它也使用了[BannerPixmap](qwizard.html#WizardPixmap-enum)和[LogoPixmap](qwizard.html#WizardPixmap-enum)装饰头。该[WatermarkPixmap](qwizard.html#WizardPixmap-enum)被显示在左侧，头下方。在底部，有一排按钮允许用户浏览页面。

页面本身（的[QWizardPage](qwizardpage.html)插件）佔据的标题，水印，按钮行之间的区域。典型地，该网页是[QWizardPage](qwizardpage.html)在其上[QGridLayout](qgridlayout.html)安装，使用标准子部件（[QLabel](qlabel.html)秒，[QLineEdit](qlineedit.html)秒，等等）。

如果精灵的风格[MacStyle](qwizard.html#WizardStyle-enum)，页面看起来完全不同：

![](../img/qtwizard-macpage.png)

水印，旗帜，徽像素图是由忽略[MacStyle](qwizard.html#WizardStyle-enum)。如果[BackgroundPixmap](qwizard.html#WizardPixmap-enum)被设置，它被用作背景为向导，否则，一个默认的“助手”的图像被使用。

标题和副标题都是通过调用设置[QWizardPage.setTitle](qwizardpage.html#title-prop)（）和[QWizardPage.setSubTitle](qwizardpage.html#subTitle-prop)（ ）上的个人网页。他们可能是纯文本或HTML （见[titleFormat](qwizard.html#titleFormat-prop)和[subTitleFormat](qwizard.html#subTitleFormat-prop)） 。该像素图就可以设置全局使用的整个向导[setPixmap](qwizard.html#setPixmap)（ ） ，或在每个页面的基础上使用[QWizardPage.setPixmap](qwizardpage.html#setPixmap)（ ） 。

### Registering and Using Fields

在许多向导页面的内容可能会影响后面的页的字段的缺省值。为了便于页面之间进行通信， QWizard支持一个“场”的机制，允许您注册一个字段（例如，[QLineEdit](qlineedit.html)）上的一个页面，访问任何网页它的价值。它也可以指定必填字段（即，必须在用户之前被填充字段可以前进到下一个页面） 。

要注册一个字段，调用[QWizardPage.registerField](qwizardpage.html#registerField)（）字段。例如：

```
 ClassInfoPage.ClassInfoPage([QWidget](qwidget.html) *parent)
     : [QWizardPage](qwizardpage.html)(parent)
 {
     ...
     classNameLabel = new [QLabel](qlabel.html)(tr("&Class name:"));
     classNameLineEdit = new [QLineEdit](qlineedit.html);
     classNameLabel->setBuddy(classNameLineEdit);

     baseClassLabel = new [QLabel](qlabel.html)(tr("B&ase class:"));
     baseClassLineEdit = new [QLineEdit](qlineedit.html);
     baseClassLabel->setBuddy(baseClassLineEdit);

     qobjectMacroCheckBox = new [QCheckBox](qcheckbox.html)(tr("Generate Q_OBJECT &macro"));

     registerField("className*", classNameLineEdit);
     registerField("baseClass", baseClassLineEdit);
     registerField("qobjectMacro", qobjectMacroCheckBox);
     ...
 }

```

上面的代码注册三个字段，`className`，`baseClass`和`qobjectMacro`，这是三个子控件相关联。星号（`*`）旁`className`表示必填字段。

任何页面的字段是从什么页面访问。例如：

```
 void OutputFilesPage.initializePage()
 {
     [QString](qstring.html) className = field("className").toString();
     headerLineEdit->setText(className.toLower() + ".h");
     implementationLineEdit->setText(className.toLower() + ".cpp");
     outputDirLineEdit->setText([QDir](qdir.html).convertSeparators([QDir](qdir.html).tempPath()));
 }

```

在这里，我们称之为[QWizardPage.field](qwizardpage.html#field)（ ）来访问的内容`className`字段（这是在所定义的`ClassInfoPage`） ，并用它来初始化`OuputFilePage`。该字段的内容返回为一个[QVariant](qvariant.html)。

当我们使用创建一个字段[QWizardPage.registerField](qwizardpage.html#registerField)（ ） ，我们通过一个唯一的字段名和窗口小部件。我们还可以提供一个Qt的属性名字和一个“改变”信号（即所发射的属性发生变化时的信号）作为第三和第四个参数，但是，这是没有必要的最常见的Qt部件，如[QLineEdit](qlineedit.html)，[QCheckBox](qcheckbox.html)和[QComboBox](qcombobox.html)，因为QWizard知道查找哪些属性。

如果一个星号（`*`）追加到名字的时候该物业登记，该字段是_mandatory field_。当一个页面有必填字段中，**Next**和/或**Finish**按钮被激活，只有当所有必填字段被填充。

考虑现场“装” ， QWizard简单地检查该字段的当前值不等于原来的值（它有值时，[initializePage](qwizard.html#initializePage)（ ）被调用） 。为[QLineEdit](qlineedit.html)和[QAbstractSpinBox](qabstractspinbox.html)子类， QWizard还检查[hasAcceptableInput()](qlineedit.html#acceptableInput-prop)返回True ，兑现任何验证或面具。

是提供了方便QWizard的强制性场机制。一个更强大的（但也比较麻烦），另一种方法是重新实现[QWizardPage.isComplete](qwizardpage.html#isComplete)（）和以发射[QWizardPage.completeChanged](qwizardpage.html#completeChanged)（ ）信号时的页面变得完整或不完整。

的启用/禁用状态**Next**和/或**Finish**按钮是向所述用户输入执行验证的一种方法。另一种方式是重新实现[validateCurrentPage](qwizard.html#validateCurrentPage)（ ）（或[QWizardPage.validatePage](qwizardpage.html#validatePage)（））来执行一些最后一分钟的验证（并且显示一个错误信息，如果用户输入了不完整的或无效的信息）。如果函数返回True，则下一个页面显示（或向导完成），否则，在当前页面熬夜。

### Creating Linear Wizards

大多数向导具有线性结构，第1页其次是第2页，依此类推直到最后一页。该[Class Wizard](index.htm)例子是这样的精灵。随着QWizard ，线性精灵是通过实例的创建[QWizardPage](qwizardpage.html)s和利用它们插入[addPage](qwizard.html#addPage)（ ） 。默认情况下，页面都显示在它们被添加的顺序。例如：

```
 ClassWizard.ClassWizard([QWidget](qwidget.html) *parent)
     : QWizard(parent)
 {
     addPage(new IntroPage);
     addPage(new ClassInfoPage);
     addPage(new CodeStylePage);
     addPage(new OutputFilesPage);
     addPage(new ConclusionPage);
     ...
 }

```

当一个网页是关于要显示， QWizard电话[initializePage](qwizard.html#initializePage)（ ） （这反过来又调用[QWizardPage.initializePage](qwizardpage.html#initializePage)（））来使用默认值填充页面。默认情况下，此功能不执行任何操作，但它可以被重新实现来初始化基于其它网页的田地页面的内容（见[example above](#initialize-page)） 。

如果用户按下**Back**，[cleanupPage](qwizard.html#cleanupPage)（）被调用（这反过来又调用[QWizardPage.cleanupPage](qwizardpage.html#cleanupPage)（））。默认实现重置页面的栏位为原始值（他们之前所拥有的价值观[initializePage](qwizard.html#initializePage)（ ）被调用） 。如果你想要的**Back**按钮是无损，并保持用户输入的值，只需启用[IndependentPages](qwizard.html#WizardOption-enum)选项。

### Creating Non-Linear Wizards

一些向导是更复杂的，因为它们允许基于由用户所提供的信息不同的遍历路径。该[License Wizard](index.htm)举例说明这一点。它提供了五个向导页，具体取决于哪个选项被选中，用户可以到达不同的页面。

![](../img/licensewizard-flow.png)

在复杂的向导，页面识别标识。这些ID通常定义使用一个枚举。例如：

```
 class LicenseWizard : public QWizard
 {
     ...
     enum { Page_Intro, Page_Evaluate, Page_Register, Page_Details,
            Page_Conclusion };
     ...
 };

```

该页面使用插入[setPage](qwizard.html#setPage)（ ） ，它接受一个ID和一个实例[QWizardPage](qwizardpage.html)（子类或） ：

```
 LicenseWizard.LicenseWizard([QWidget](qwidget.html) *parent)
     : QWizard(parent)
 {
     setPage(Page_Intro, new IntroPage);
     setPage(Page_Evaluate, new EvaluatePage);
     setPage(Page_Register, new RegisterPage);
     setPage(Page_Details, new DetailsPage);
     setPage(Page_Conclusion, new ConclusionPage);
     ...
 }

```

默认情况下，页面中显示递增的ID顺序。提供一个动态的顺序取决于用户选择的选项，我们必须重新实现[QWizardPage.nextId](qwizardpage.html#nextId)（ ） 。例如：

```
 int IntroPage.nextId() const
 {
     if (evaluateRadioButton->isChecked()) {
         return LicenseWizard.Page_Evaluate;
     } else {
         return LicenseWizard.Page_Register;
     }
 }

 int EvaluatePage.nextId() const
 {
     return LicenseWizard.Page_Conclusion;
 }

 int RegisterPage.nextId() const
 {
     if (upgradeKeyLineEdit->text().isEmpty()) {
         return LicenseWizard.Page_Details;
     } else {
         return LicenseWizard.Page_Conclusion;
     }
 }

 int DetailsPage.nextId() const
 {
     return LicenseWizard.Page_Conclusion;
 }

 int ConclusionPage.nextId() const
 {
     return -1;
 }

```

这也将有可能把所有的逻辑在一个地方，在一个[QWizard.nextId](qwizard.html#nextId)（ ）重新实现。例如：

```
 int LicenseWizard.nextId() const
 {
     switch (currentId()) {
     case Page_Intro:
         if (field("intro.evaluate").toBool()) {
             return Page_Evaluate;
         } else {
             return Page_Register;
         }
     case Page_Evaluate:
         return Page_Conclusion;
     case Page_Register:
         if (field("register.upgradeKey").toString().isEmpty()) {
             return Page_Details;
         } else {
             return Page_Conclusion;
         }
     case Page_Details:
         return Page_Conclusion;
     case Page_Conclusion:
     default:
         return -1;
     }
 }

```

开始在另一个页面比页面具有最低的ID ，调用[setStartId](qwizard.html#startId-prop)（ ） 。

要测试一个网页是否已被访问，则调用[hasVisitedPage](qwizard.html#hasVisitedPage)（ ） 。例如：

```
 void ConclusionPage.initializePage()
 {
     [QString](qstring.html) licenseText;

     if (wizard()->hasVisitedPage(LicenseWizard.Page_Evaluate)) {
         licenseText = tr("<u>Evaluation License Agreement:</u> "
                          "You can use this software for 30 days and make one "
                          "backup, but you are not allowed to distribute it.");
     } else if (wizard()->hasVisitedPage(LicenseWizard.Page_Details)) {
         licenseText = tr("<u>First-Time License Agreement:</u> "
                          "You can use this software subject to the license "
                          "you will receive by email.");
     } else {
         licenseText = tr("<u>Upgrade License Agreement:</u> "
                          "This software is licensed under the terms of your "
                          "current license.");
     }
     bottomLabel->setText(licenseText);
 }

```

* * *

## Type Documentation

```
QWizard.WizardButton
```

此枚举指定一个向导按钮。

| Constant | Value | Description |
| --- | --- | --- |
| `QWizard.BackButton` | `0` | 该**Back**按钮（**Go Back**在Mac OS X ） |
| `QWizard.NextButton` | `1` | 该**Next**按钮（**Continue**在Mac OS X ） |
| `QWizard.CommitButton` | `2` | 该**Commit**钮 |
| `QWizard.FinishButton` | `3` | 该**Finish**按钮（**Done**在Mac OS X ） |
| `QWizard.CancelButton` | `4` | 该**Cancel**按钮（参见[NoCancelButton](qwizard.html#WizardOption-enum)） |
| `QWizard.HelpButton` | `5` | 该**Help**按钮（参见[HaveHelpButton](qwizard.html#WizardOption-enum)） |
| `QWizard.CustomButton1` | `6` | 第一个用户自定义按钮（参见[HaveCustomButton1](qwizard.html#WizardOption-enum)） |
| `QWizard.CustomButton2` | `7` | 第二个用户自定义按钮（也见[HaveCustomButton2](qwizard.html#WizardOption-enum)） |
| `QWizard.CustomButton3` | `8` | 第三个用户自定义按钮（也见[HaveCustomButton3](qwizard.html#WizardOption-enum)） |

当调用下面的值才有用[setButtonLayout](qwizard.html#setButtonLayout)（）：

| Constant | Value | Description |
| --- | --- | --- |
| `QWizard.Stretch` | `9` | 的水平伸展的按钮布局 |

**See also** [setButton](qwizard.html#setButton)（ ）[setButtonText](qwizard.html#setButtonText)（ ）[setButtonLayout](qwizard.html#setButtonLayout)（）和[customButtonClicked](qwizard.html#customButtonClicked)（ ） 。

```
QWizard.WizardOption
```

此枚举指定影响精灵的外观和感觉的各种选项。

| Constant | Value | Description |
| --- | --- | --- |
| `QWizard.IndependentPages` | `0x00000001` | 页面是相互独立的（即，它们不会相互派生值）。 |
| `QWizard.IgnoreSubTitles` | `0x00000002` | 不显示任何字幕，即使它们被设置。 |
| `QWizard.ExtendedWatermarkPixmap` | `0x00000004` | 任何延长[WatermarkPixmap](qwizard.html#WizardPixmap-enum)一路下跌到窗口的边缘。 |
| `QWizard.NoDefaultButton` | `0x00000008` | 不要使**Next** or **Finish**按钮对话框的[default button](qpushbutton.html#default-prop)。 |
| `QWizard.NoBackButtonOnStartPage` | `0x00000010` | 不显示**Back**在开始页面上按钮。 |
| `QWizard.NoBackButtonOnLastPage` | `0x00000020` | 不显示**Back**在最后一页按钮。 |
| `QWizard.DisabledBackButtonOnLastPage` | `0x00000040` | 关闭**Back**在最后一页按钮。 |
| `QWizard.HaveNextButtonOnLastPage` | `0x00000080` | 显示（禁用）**Next**在最后一页按钮。 |
| `QWizard.HaveFinishButtonOnEarlyPages` | `0x00000100` | 显示（禁用）**Finish**在非最后几页按钮。 |
| `QWizard.NoCancelButton` | `0x00000200` | 不显示**Cancel**按钮。 |
| `QWizard.CancelButtonOnLeft` | `0x00000400` | 把**Cancel**上的左按钮**Back**（而不是右侧**Finish** or **Next**） 。 |
| `QWizard.HaveHelpButton` | `0x00000800` | 显示**Help**按钮。 |
| `QWizard.HelpButtonOnRight` | `0x00001000` | 把**Help**上的按键布局（而不是在最左侧）最右边的按钮。 |
| `QWizard.HaveCustomButton1` | `0x00002000` | 显示的第一个用户自定义按钮（[CustomButton1](qwizard.html#WizardButton-enum)） 。 |
| `QWizard.HaveCustomButton2` | `0x00004000` | 显示第二个用户自定义按钮（[CustomButton2](qwizard.html#WizardButton-enum)） 。 |
| `QWizard.HaveCustomButton3` | `0x00008000` | 显示第三个用户自定义按钮（[CustomButton3](qwizard.html#WizardButton-enum)） 。 |

该WizardOptions类型是一个typedef为[QFlags](index.htm)\u003cWizardOption\u003e 。它存储WizardOption值的或组合。

**See also** [setOptions](qwizard.html#options-prop)（ ）[setOption](qwizard.html#setOption)（）和[testOption](qwizard.html#testOption)（ ） 。

```
QWizard.WizardPixmap
```

该枚举指定可以与一个页面相关联的像素图。

| Constant | Value | Description |
| --- | --- | --- |
| `QWizard.WatermarkPixmap` | `0` | 上一个左侧的高像素图[ClassicStyle](qwizard.html#WizardStyle-enum) or [ModernStyle](qwizard.html#WizardStyle-enum)页面 |
| `QWizard.LogoPixmap` | `1` | 右侧的小像素图[ClassicStyle](qwizard.html#WizardStyle-enum) or [ModernStyle](qwizard.html#WizardStyle-enum)页头 |
| `QWizard.BannerPixmap` | `2` | 佔据的背景像素图[ModernStyle](qwizard.html#WizardStyle-enum)页头 |
| `QWizard.BackgroundPixmap` | `3` | 佔据的背景像素图[MacStyle](qwizard.html#WizardStyle-enum)巫师 |

**See also** [setPixmap](qwizard.html#setPixmap)（ ）[QWizardPage.setPixmap](qwizardpage.html#setPixmap)（）和[Elements of a Wizard Page](qwizard.html#elements-of-a-wizard-page)。

```
QWizard.WizardStyle
```

此枚举指定所支持的不同的外观[QWizard](qwizard.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QWizard.ClassicStyle` | `0` | 经典的Windows外观 |
| `QWizard.ModernStyle` | `1` | 现代的Windows外观 |
| `QWizard.MacStyle` | `2` | 的Mac OS X的外观 |
| `QWizard.AeroStyle` | `3` | Windows Aero的外观 |

**See also** [setWizardStyle](qwizard.html#wizardStyle-prop)（ ）[WizardOption](qwizard.html#WizardOption-enum)和[Wizard Look and Feel](qwizard.html#wizard-look-and-feel)。

* * *

## Method Documentation

```
QWizard.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个向导给定的_parent_和窗口_flags_。

**See also** [parent](qobject.html#parent)（）和[windowFlags](qwidget.html#windowFlags-prop)（ ） 。

```
int QWizard.addPage (self, QWizardPage page)
```

该_page_说法有它的所有权转移给Qt的。

将给定_page_精灵，并返回该页面的ID 。

该ID是保证比任何其他大的ID[QWizard](qwizard.html)到目前为止。

**See also** [setPage](qwizard.html#setPage)（ ）[page](qwizard.html#page)（）和[pageAdded](qwizard.html#pageAdded)（ ） 。

```
QWizard.back (self)
```

这种方法也是一个Qt槽与C + +的签名`void back()`。

返回到前一个页面。

这相当于按下**Back**按钮。

**See also** [next](qwizard.html#next)（ ）[accept](qdialog.html#accept)（ ）[reject](qdialog.html#reject)（）和[restart](qwizard.html#restart)（ ） 。

```
QAbstractButton QWizard.button (self, WizardButton which)
```

[

返回对应于角色的按钮_which_。

](qabstractbutton.html)

[**See also**](qabstractbutton.html) [setButton](qwizard.html#setButton)（）和[setButtonText](qwizard.html#setButtonText)（ ） 。

```
QString QWizard.buttonText (self, WizardButton which)
```

按钮返回文本_which_。

如果使用的是文本有奔集[setButtonText](qwizard.html#setButtonText)（ ） ，则返回该文本。

默认情况下，按钮上的文本取决于[wizardStyle](qwizard.html#wizardStyle-prop)。例如，在Mac OS X中，**Next**按钮被称为**Continue**。

**See also** [button](qwizard.html#button)（ ）[setButton](qwizard.html#setButton)（ ）[setButtonText](qwizard.html#setButtonText)（ ）[QWizardPage.buttonText](qwizardpage.html#buttonText)（）和[QWizardPage.setButtonText](qwizardpage.html#setButtonText)（ ） 。

```
QWizard.cleanupPage (self, int id)
```

这个虚函数被调用[QWizard](qwizard.html)清理页面_id_用户通过点击它离开之前**Back**（除非[QWizard.IndependentPages](qwizard.html#WizardOption-enum)选项设置） 。

默认实现调用[QWizardPage.cleanupPage](qwizardpage.html#cleanupPage)（ ）页（_id_） 。

**See also** [QWizardPage.cleanupPage](qwizardpage.html#cleanupPage)（）和[initializePage](qwizard.html#initializePage)（ ） 。

```
int QWizard.currentId (self)
```

```
QWizardPage QWizard.currentPage (self)
```

[

返回一个指针，指向当前页面，或者0，如果没有当前页面（例如，向导会显示之前） 。

](qwizardpage.html)

[这等同于调用页面（](qwizardpage.html)[currentId](qwizard.html#currentId-prop)（））。

**See also** [page](qwizard.html#page)（ ）[currentId](qwizard.html#currentId-prop)（）和[restart](qwizard.html#restart)（ ） 。

```
QWizard.done (self, int result)
```

从重新实现[QDialog.done](qdialog.html#done)（ ） 。

```
bool QWizard.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QVariant QWizard.field (self, QString name)
```

返回字段的所谓的值_name_。

此功能可用于访问向导的任何页面上的字段。

**See also** [QWizardPage.registerField](qwizardpage.html#registerField)（ ）[QWizardPage.field](qwizardpage.html#field)（）和[setField](qwizard.html#setField)（ ） 。

```
bool QWizard.hasVisitedPage (self, int id)
```

如果页面历史记录中包含页面，则返回True_id_否则，返回False 。

Pressing **Back**当前页面标记为“未访问”了。

**See also** [visitedPages](qwizard.html#visitedPages)（ ） 。

```
QWizard.initializePage (self, int id)
```

这个虚函数被调用[QWizard](qwizard.html)准备一页_id_它表明无论是作为一个结果之前[QWizard.restart](qwizard.html#restart)（）被调用时，或者当用户点击的结果**Next**。 （然而，如果[QWizard.IndependentPages](qwizard.html#WizardOption-enum)选项设置，此功能只在第一次调用的页面显示。 ）

通过重新实现这个功能，可以确保基于前几页信息页面的栏已正确初始化。

默认实现调用[QWizardPage.initializePage](qwizardpage.html#initializePage)（ ）页（_id_） 。

**See also** [QWizardPage.initializePage](qwizardpage.html#initializePage)（）和[cleanupPage](qwizard.html#cleanupPage)（ ） 。

```
QWizard.next (self)
```

这种方法也是一个Qt槽与C + +的签名`void next()`。

前进到下一个页面。

这相当于按下**Next** or **Commit**按钮。

**See also** [nextId](qwizard.html#nextId)（ ）[back](qwizard.html#back)（ ）[accept](qdialog.html#accept)（ ）[reject](qdialog.html#reject)（）和[restart](qwizard.html#restart)（ ） 。

```
int QWizard.nextId (self)
```

这个虚函数被调用[QWizard](qwizard.html)找出当用户点击显示哪些页面**Next**按钮。

返回值是下一个页面的ID ，或-1，如果没有页面如下。

默认实现调用[QWizardPage.nextId](qwizardpage.html#nextId)（）对[currentPage](qwizard.html#currentPage)（ ） 。

通过重新实现此功能，您可以指定一个动态的页面顺序。

**See also** [QWizardPage.nextId](qwizardpage.html#nextId)（）和[currentPage](qwizard.html#currentPage)（ ） 。

```
WizardOptions QWizard.options (self)
```

[](index.htm)

```
QWizardPage QWizard.page (self, int id)
```

[

用给定的返回页面_id_或0，如果不存在这样的页面。

](qwizardpage.html)

[**See also**](qwizardpage.html) [addPage](qwizard.html#addPage)（）和[setPage](qwizard.html#setPage)（ ） 。

```
list-of-int QWizard.pageIds (self)
```

返回页ID的列表。

此功能被引入Qt的4.5 。

```
QWizard.paintEvent (self, QPaintEvent event)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QPixmap QWizard.pixmap (self, WizardPixmap which)
```

[

返回角色像素图组_which_。

](qpixmap.html)

[默认情况下，设置唯一的像素图是](qpixmap.html)[BackgroundPixmap](qwizard.html#WizardPixmap-enum)在Mac OS X。

**See also** [setPixmap](qwizard.html#setPixmap)（ ）[QWizardPage.pixmap](qwizardpage.html#pixmap)（）和[Elements of a Wizard Page](qwizard.html#elements-of-a-wizard-page)。

```
QWizard.removePage (self, int id)
```

删除的页面与给定_id_。[cleanupPage](qwizard.html#cleanupPage)（）将在必要时调用。

**Note:**删除页面可能影响的价值[startId](qwizard.html#startId-prop)属性。

此功能被引入Qt的4.5 。

**See also** [addPage](qwizard.html#addPage)（ ）[setPage](qwizard.html#setPage)（ ）[pageRemoved](qwizard.html#pageRemoved)（）和[startId](qwizard.html#startId-prop)（ ） 。

```
QWizard.resizeEvent (self, QResizeEvent event)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QWizard.restart (self)
```

这种方法也是一个Qt槽与C + +的签名`void restart()`。

重新启动向导在开始页面。这个函数被自动调用该向导显示时。

**See also** [startId](qwizard.html#startId-prop)（ ） 。

```
QWizard.setButton (self, WizardButton which, QAbstractButton button)
```

该_button_说法有它的所有权转移给Qt的。

设置对应的角色按钮_which_至_button_。

要添加额外的按钮向导（例如，一**Print**钮），一个方法是调用SET按钮（ ）与[CustomButton1](qwizard.html#WizardButton-enum)至[CustomButton3](qwizard.html#WizardButton-enum)，并使用make可见的按钮[HaveCustomButton1](qwizard.html#WizardOption-enum)至[HaveCustomButton3](qwizard.html#WizardOption-enum)选项。

**See also** [button](qwizard.html#button)（ ）[setButtonText](qwizard.html#setButtonText)（ ）[setButtonLayout](qwizard.html#setButtonLayout)（）和[options](qwizard.html#options-prop)。

```
QWizard.setButtonLayout (self, list-of-QWizard.WizardButton layout)
```

设置在该按钮所显示的顺序_layout_，其中_layout_是的列表[WizardButton](qwizard.html#WizardButton-enum)秒。

默认的布局取决于选项（例如，是否[HelpButtonOnRight](qwizard.html#WizardOption-enum)）被设置。如果你需要比更多的控制按钮的布局你可以调用这个函数是什么[options](qwizard.html#options-prop)已经提供。

您可以使用指定的布局横向延伸[Stretch](qwizard.html#WizardButton-enum)。

例如：

```
 MyWizard.MyWizard([QWidget](qwidget.html) *parent)
     : [QWizard](qwizard.html)(parent)
 {
     ...
     [QList](index.htm)<[QWizard](qwizard.html).WizardButton> layout;
     layout << [QWizard](qwizard.html).Stretch << [QWizard](qwizard.html).BackButton << [QWizard](qwizard.html).CancelButton
            << [QWizard](qwizard.html).NextButton << [QWizard](qwizard.html).FinishButton;
     setButtonLayout(layout);
     ...
 }

```

**See also** [setButton](qwizard.html#setButton)（ ）[setButtonText](qwizard.html#setButtonText)（）和[setOptions](qwizard.html#options-prop)（ ） 。

```
QWizard.setButtonText (self, WizardButton which, QString text)
```

按钮设置文本_which_要_text_。

默认情况下，按钮上的文本取决于[wizardStyle](qwizard.html#wizardStyle-prop)。例如，在Mac OS X中，**Next**按钮被称为**Continue**。

要添加额外的按钮向导（例如，一**Print**钮），一个方法是调用setButtonText （ ）与[CustomButton1](qwizard.html#WizardButton-enum)，[CustomButton2](qwizard.html#WizardButton-enum)或[CustomButton3](qwizard.html#WizardButton-enum)设定自己的文字，并使用make可见的按钮[HaveCustomButton1](qwizard.html#WizardOption-enum)，[HaveCustomButton2](qwizard.html#WizardOption-enum)和/或[HaveCustomButton3](qwizard.html#WizardOption-enum)选项。

在每个页面的基础上使用按钮的文本也可以设置[QWizardPage.setButtonText](qwizardpage.html#setButtonText)（ ） 。

**See also** [buttonText](qwizard.html#buttonText)（ ）[setButton](qwizard.html#setButton)（ ）[button](qwizard.html#button)（ ）[setButtonLayout](qwizard.html#setButtonLayout)（ ）[setOptions](qwizard.html#options-prop)（）和[QWizardPage.setButtonText](qwizardpage.html#setButtonText)（ ） 。

```
QWizard.setDefaultProperty (self, str className, str property, str changedSignal)
```

设置为默认属性_className_要_property_和相关联的变化信号是_changedSignal_。

默认属性时使用的一个实例_className_（它的一个子类或）传递给[QWizardPage.registerField](qwizardpage.html#registerField)（ ），并指定属性。

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

**See also** [QWizardPage.registerField](qwizardpage.html#registerField)（ ） 。

```
QWizard.setField (self, QString name, QVariant value)
```

设置字段中称为值_name_至_value_。

此功能可用于在向导的任何页面上设置的字段。

**See also** [QWizardPage.registerField](qwizardpage.html#registerField)（ ）[QWizardPage.setField](qwizardpage.html#setField)（）和[field](qwizard.html#field)（ ） 。

```
QWizard.setOption (self, WizardOption option, bool on = True)
```

设置给定_option_被启用，如果_on_是真的，否则，清除给定的_option_。

**See also** [options](qwizard.html#options-prop)，[testOption](qwizard.html#testOption)（）和[setWizardStyle](qwizard.html#wizardStyle-prop)（ ） 。

```
QWizard.setOptions (self, WizardOptions options)
```

```
QWizard.setPage (self, int id, QWizardPage page)
```

该_page_说法有它的所有权转移给Qt的。

将给定_page_与给定的精灵_id_。

**Note:**添加页面可能影响的价值[startId](qwizard.html#startId-prop)在财产的情况下它是没有显式设置。

**See also** [addPage](qwizard.html#addPage)（ ）[page](qwizard.html#page)（）和[pageAdded](qwizard.html#pageAdded)（ ） 。

```
QWizard.setPixmap (self, WizardPixmap which, QPixmap pixmap)
```

设置像素图的作用_which_至_pixmap_。

该像素图所使用的[QWizard](qwizard.html)显示一个页面时。其中像素图实际使用依赖于[wizard style](qwizard.html#wizard-look-and-feel)。

像素图，也可以使用一个特定的页面设置[QWizardPage.setPixmap](qwizardpage.html#setPixmap)（ ） 。

**See also** [pixmap](qwizard.html#pixmap)（ ）[QWizardPage.setPixmap](qwizardpage.html#setPixmap)（）和[Elements of a Wizard Page](qwizard.html#elements-of-a-wizard-page)。

```
QWizard.setSideWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置给定_widget_要显示在该向导的左侧。对于使用样式[WatermarkPixmap](qwizard.html#WizardPixmap-enum)（[ClassicStyle](qwizard.html#WizardStyle-enum)和[ModernStyle](qwizard.html#WizardStyle-enum)）侧部件上显示水印的顶部，对于其它样式或不设置水印当侧部件上显示该向导的左侧。

传递0表示无副作用小部件。

当_widget_是不是0精灵reparents它。

任何以前的侧部件被隐藏。

您可致电setSideWidget （ ）使用相同的部件在不同的时间。

这里设置的所有部件将由向导时，它被摧毁，除非你单独reparent小部件设置一些对方部件（或0 ）后删除。

默认情况下，无副作用小部件存在。

此功能被引入Qt的4.7 。

**See also** [sideWidget](qwizard.html#sideWidget)（ ） 。

```
QWizard.setStartId (self, int id)
```

```
QWizard.setSubTitleFormat (self, Qt.TextFormat format)
```

```
QWizard.setTitleFormat (self, Qt.TextFormat format)
```

```
QWizard.setVisible (self, bool visible)
```

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

```
QWizard.setWizardStyle (self, WizardStyle style)
```

```
QWidget QWizard.sideWidget (self)
```

[

返回在向导或0的左侧的小部件。

默认情况下，无副作用小部件存在。

此功能被引入Qt的4.7 。

](qwidget.html)

[**See also**](qwidget.html) [setSideWidget](qwizard.html#setSideWidget)（ ） 。

```
QSize QWizard.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
int QWizard.startId (self)
```

```
Qt.TextFormat QWizard.subTitleFormat (self)
```

[

```
bool QWizard.testOption (self, WizardOption option)
```

返回True如果给定的_option_被启用，否则返回False 。

](qt.html#TextFormat-enum)

[**See also**](qt.html#TextFormat-enum) [options](qwizard.html#options-prop)，[setOption](qwizard.html#setOption)（）和[setWizardStyle](qwizard.html#wizardStyle-prop)（ ） 。

```
Qt.TextFormat QWizard.titleFormat (self)
```

[

```
bool QWizard.validateCurrentPage (self)
```

](qt.html#TextFormat-enum)

[这个虚函数被调用](qt.html#TextFormat-enum)[QWizard](qwizard.html)当用户点击**Next** or **Finish**执行一些最后一分钟的验证。如果返回True，则下一个页面显示（或向导完成），否则，在当前页面熬夜。

默认实现调用[QWizardPage.validatePage](qwizardpage.html#validatePage)（）对[currentPage](qwizard.html#currentPage)（ ） 。

如果可能的话，它通常是更好的风格禁用**Next** or **Finish**按钮（通过指定[mandatory fields](qwizard.html#mandatory-fields)或通过重新实现[QWizardPage.isComplete](qwizardpage.html#isComplete)（ ） ），而不是重新实现validateCurrentPage （ ） 。

**See also** [QWizardPage.validatePage](qwizardpage.html#validatePage)（）和[currentPage](qwizard.html#currentPage)（ ） 。

```
list-of-int QWizard.visitedPages (self)
```

返回浏览过的网页的ID列表，在其中的网页被访问的顺序。

Pressing **Back**当前页面标记为“未访问”了。

**See also** [hasVisitedPage](qwizard.html#hasVisitedPage)（ ） 。

```
WizardStyle QWizard.wizardStyle (self)
```

[

* * *

## Qt Signal Documentation

```
void currentIdChanged (int)
```

这是该信号的默认超载。

这个信号被发射时，当前页面的变化，与新的当前_id_。

](qwizard.html#WizardStyle-enum)

[**See also**](qwizard.html#WizardStyle-enum) [currentId](qwizard.html#currentId-prop)（）和[currentPage](qwizard.html#currentPage)（ ） 。

```
void customButtonClicked (int)
```

这是该信号的默认超载。

当用户点击自定义按钮这个信号被发射。_which_可以[CustomButton1](qwizard.html#WizardButton-enum)，[CustomButton2](qwizard.html#WizardButton-enum)或[CustomButton3](qwizard.html#WizardButton-enum)。

默认情况下，显示没有自定义按钮。通话[setOption](qwizard.html#setOption)（ ）与[HaveCustomButton1](qwizard.html#WizardOption-enum)，[HaveCustomButton2](qwizard.html#WizardOption-enum)或[HaveCustomButton3](qwizard.html#WizardOption-enum)有一个，并使用[setButtonText](qwizard.html#setButtonText)（）或[setButton](qwizard.html#setButton)（）来配置它。

**See also** [helpRequested](qwizard.html#helpRequested)（ ） 。

```
void helpRequested ()
```

This is the default overload of this signal.

当用户点击这个信号被发射的**Help**按钮。

缺省情况下，**Help**显示按钮。调用的SetOption （[HaveHelpButton](qwizard.html#WizardOption-enum)，真）有一个。

例如：

```
 LicenseWizard.LicenseWizard([QWidget](qwidget.html) *parent)
     : [QWizard](qwizard.html)(parent)
 {
     ...
     setOption(HaveHelpButton, true);
     connect(this, SIGNAL(helpRequested()), this, SLOT(showHelp()));
     ...
 }

 void LicenseWizard.showHelp()
 {
     static [QString](qstring.html) lastHelpMessage;

     [QString](qstring.html) message;

     switch (currentId()) {
     case Page_Intro:
         message = tr("The decision you make here will affect which page you "
                      "get to see next.");
         break;
     ...
     default:
         message = tr("This help is likely not to be of any help.");
     }

     [QMessageBox](qmessagebox.html).information(this, tr("License Wizard Help"), message);

 }

```

**See also** [customButtonClicked](qwizard.html#customButtonClicked)（ ） 。

```
void pageAdded (int)
```

这是该信号的默认超载。

每当一个页面被添加到向导这个信号被发射。在页面的_id_作为参数传递。

此功能被引入Qt的4.7 。

**See also** [addPage](qwizard.html#addPage)（ ）[setPage](qwizard.html#setPage)（）和[startId](qwizard.html#startId-prop)（ ） 。

```
void pageRemoved (int)
```

这是该信号的默认超载。

每当一个页面被从向导删除这个信号被发射。在页面的_id_作为参数传递。

此功能被引入Qt的4.7 。

**See also** [removePage](qwizard.html#removePage)（）和[startId](qwizard.html#startId-prop)（ ） 。