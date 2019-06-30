# QSettings Class Reference

## [[QtCore](index.htm) module]

该QSettings类提供持久的与平台无关的应用程序设置。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum Format { NativeFormat, IniFormat, InvalidFormat }`
*   `enum Scope { UserScope, SystemScope }`
*   `enum Status { NoError, AccessError, FormatError }`

### Methods

*   `__init__ (self, QString organization, QString application = QString(), QObject parent = None)`
*   `__init__ (self, Scope scope, QString organization, QString application = QString(), QObject parent = None)`
*   `__init__ (self, Format format, Scope scope, QString organization, QString application = QString(), QObject parent = None)`
*   `__init__ (self, QString fileName, Format format, QObject parent = None)`
*   `__init__ (self, QObject parent = None)`
*   `QStringList allKeys (self)`
*   `QString applicationName (self)`
*   `beginGroup (self, QString prefix)`
*   `int beginReadArray (self, QString prefix)`
*   `beginWriteArray (self, QString prefix, int size = -1)`
*   `QStringList childGroups (self)`
*   `QStringList childKeys (self)`
*   `clear (self)`
*   `bool contains (self, QString key)`
*   `endArray (self)`
*   `endGroup (self)`
*   `bool event (self, QEvent event)`
*   `bool fallbacksEnabled (self)`
*   `QString fileName (self)`
*   `Format format (self)`
*   `QString group (self)`
*   `QTextCodec iniCodec (self)`
*   `bool isWritable (self)`
*   `QString organizationName (self)`
*   `remove (self, QString key)`
*   `Scope scope (self)`
*   `setArrayIndex (self, int i)`
*   `setFallbacksEnabled (self, bool b)`
*   `setIniCodec (self, QTextCodec codec)`
*   `setIniCodec (self, str codecName)`
*   `setValue (self, QString key, QVariant value)`
*   `Status status (self)`
*   `sync (self)`
*   `object value (self, QString key, QVariant defaultValue = QVariant(), object type = None)`

### Static Methods

*   `Format defaultFormat ()`
*   `setDefaultFormat (Format format)`
*   `setPath (Format format, Scope scope, QString path)`
*   `setSystemIniPath (QString dir)`
*   `setUserIniPath (QString dir)`

* * *

## Detailed Description

该QSettings类提供持久的与平台无关的应用程序设置。

用户通常期望的应用程序记住它的跨会话设置（窗口大小和位置，期权等） 。这些信息通常存储在Windows系统注册表，并在Mac OS X上在Unix系统中，在没有一个标准的XML文件的偏好，许多应用程序（包括KDE应用程序）使用INI的文本文件。

QSettings是围绕这些技术的抽象，使您能够保存和恢复应用程序设置在一个便携的方式。它也支持[custom storage formats](qsettings.html#registerFormat)。

QSettings的API是基于[QVariant](qvariant.html)，让您节省最大的价值为基础的类型，如[QString](qstring.html)，[QRect](qrect.html)和[QImage](qimage.html)，用最小的努力。

如果你需要的是一种非持久性记忆体为基础的结构，可以考虑使用[QMap](index.htm)\u003c[QString](qstring.html)，[QVariant](qvariant.html)\u003e代替。

### Basic Usage

当创建一个QSettings对象，你必须通过你的公司或组织的名称以及您的应用程序的名称。例如，如果您的产品被称为少年阿虎和您的公司被称为MySoft ，你会兴建QSettings对象，如下所示：

```
     QSettings settings("MySoft", "Star Runner");

```

QSettings对象可以（即使用创建无论是在栈或堆`new`） 。构建和销毁QSettings对象是非常快的。

如果您使用的许多地方在你的应用程序QSettings ，您可能希望使用指定的组织名称和应用程序名称[QCoreApplication.setOrganizationName](qcoreapplication.html#organizationName-prop)（）和[QCoreApplication.setApplicationName](qcoreapplication.html#applicationName-prop)（ ） ，然后使用默认的构造函数QSettings ：

```
     [QCoreApplication](qcoreapplication.html).setOrganizationName("MySoft");
     [QCoreApplication](qcoreapplication.html).setOrganizationDomain("mysoft.com");
     [QCoreApplication](qcoreapplication.html).setApplicationName("Star Runner");
     ...
     QSettings settings;

```

（在这里，我们也可以指定组织的互联网域名，当互联网域名设置，它是用来代替组织名称在Mac OS X ，因为Mac OS X的应用程序通常使用Internet域名来标识自己。如果没有域设置，假的域是从组织名称派生的。见[Platform-Specific Notes](#platform-specific-notes)下面的详细信息。 ）

QSettings存储设置。每个设置由一个[QString](qstring.html)它指定该设置的名称（在_key_）和一个[QVariant](qvariant.html)存储与该键相关联的数据。写一个设置，使用[setValue](qsettings.html#setValue)（ ） 。例如：

```
     settings.setValue("editor/wrapMargin", 68);

```

如果已经存在具有相同键的设置，现有的值会被新值复盖。为了提高效率，更改可能不会立即保存到永久存储。 （您可以随时拨打[sync](qsettings.html#sync)（ ）提交更改。 ）

您可以使用得到一个设定的值返回[value](qsettings.html#value)（）：

```
     int margin = settings.value("editor/wrapMargin").toInt();

```

如果没有具有指定名称的设置， QSettings返回null[QVariant](qvariant.html)（可以转换为整数0）。你可以通过传递第二个参数指定另一个缺省值[value](qsettings.html#value)（）：

```
     int margin = settings.value("editor/wrapMargin", 80).toInt();

```

为了测试是否一个给定的键存在，调用[contains](qsettings.html#contains)（ ） 。要删除一个键，呼叫相关的设置[remove](qsettings.html#remove)（ ） 。要获得所有键的列表，请致电[allKeys](qsettings.html#allKeys)（ ） 。要移除所有的键，通话[clear](qsettings.html#clear)（ ） 。

### QVariant and GUI Types

因为[QVariant](qvariant.html)是部分[QtCore](index.htm)库，它不能提供转换功能以数据类型，例如[QColor](qcolor.html)，[QImage](qimage.html)和[QPixmap](qpixmap.html)，它们是部分[QtGui](index.htm)。换句话说，没有`toColor()`，`toImage()`或`toPixmap()`在功能[QVariant](qvariant.html)。

相反，你可以使用[QVariant.value](qvariant.html#value)（）或[qVariantValue](index.htm#qVariantValue)（ ）模板函数。例如：

```
 QSettings settings("MySoft", "Star Runner");
 [QColor](qcolor.html) color = settings.value("DataPump/bgcolor").value<[QColor](qcolor.html)>();

```

逆变换（例如，从[QColor](qcolor.html)至[QVariant](qvariant.html)）是自动对所支持的所有数据类型[QVariant](qvariant.html)包括GUI相关的类：

```
 QSettings settings("MySoft", "Star Runner");
 [QColor](qcolor.html) color = palette().background().color();
 settings.setValue("DataPump/bgcolor", color);

```

自定义类型使用登记[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（）和[qRegisterMetaTypeStreamOperators](qmetatype.html#qRegisterMetaTypeStreamOperators)（）可以使用QSettings被存储。

### Section and Key Syntax

设置键可以包含任何Unicode字符。 Windows注册表和INI文件使用不区分大小写键，而在Mac OS X中的碳Preferences API使用区分大小写键。为了避免可移植性问题，请遵循这些简单的规则：

1.  总是使用相同的情况下，指的是同一个键。例如，如果你指的是键“文本字体”在一个地方在你的代码，不称其为“文本字体”别的地方。
2.  避免将除的情况下相同的键名。例如，如果您有一个名为键“[MainWindow](index.htm#mainwindow)“不要试图去拯救另一个关键是”主窗口“ 。
3.  不要在节或键名称中使用斜线（' / '和' \ '）;反斜杠字符用于分隔子键（见下文） 。在windows '\'被QSettings转换为'/' ，这使得它们是相同的。

您可以使用形成的“/”字符作为分隔符，类似于Unix的文件路径分级密钥。例如：

```
     settings.setValue("mainwindow/size", win->size());
     settings.setValue("mainwindow/fullScreen", win->isFullScreen());
     settings.setValue("outputpanel/visible", panel->isVisible());

```

如果你想保存或恢复具有相同前缀的许多设置，您可以使用指定的前缀[beginGroup](qsettings.html#beginGroup)（ ）和呼叫[endGroup](qsettings.html#endGroup)（）结尾。下面是同样的例子了，但使用组机制这个时候：

```
     settings.beginGroup("mainwindow");
     settings.setValue("size", win->size());
     settings.setValue("fullScreen", win->isFullScreen());
     settings.endGroup();

     settings.beginGroup("outputpanel");
     settings.setValue("visible", panel->isVisible());
     settings.endGroup();

```

如果一组设置使用[beginGroup](qsettings.html#beginGroup)（ ） ，大部分功能的行为从而改变了。组可以递归集。

除了团体， QSettings还支持“数组”的概念。看[beginReadArray](qsettings.html#beginReadArray)（）和[beginWriteArray](qsettings.html#beginWriteArray)（ ）了解详情。

### Fallback Mechanism

让我们假设你已经创建了一个QSettings对象与该组织名称MySoft和应用程序的名称少年阿虎。当你看到一个值，最多四个地点中搜索的顺序：

1.  对于少年阿虎应用程序的用户特定位置
2.  用于通过MySoft所有应用程序的用户特定位置
3.  对于少年阿虎应用系统范围的位置
4.  由MySoft所有应用系统范围的位置

（见[Platform-Specific Notes](#platform-specific-notes)下面关于这些地点是在Qt所支持的不同平台的信息。 ）

如果一个密钥不能在第一位置被发现，搜索继续在第二的位置，并依此类推。这使您能够存储系统范围或组织范围内设置，并复盖它们基于每个用户或每个应用程序的基础。要关闭此机制，调用setFallbacksEnabled （假） 。

虽然可用于读取来自所有四个位置的键，仅在第一个文件（手头的应用程序的用户特定位置）是用于写访问。要写入的任何其他文件，省略了应用程序的名称和/或指定[QSettings.SystemScope](qsettings.html#Scope-enum)（相对于[QSettings.UserScope](qsettings.html#Scope-enum)，默认值） 。

让我们用一个例子来看看：

```
     QSettings obj1("MySoft", "Star Runner");
     QSettings obj2("MySoft");
     QSettings obj3(QSettings.SystemScope, "MySoft", "Star Runner");
     QSettings obj4(QSettings.SystemScope, "MySoft");

```

下表总结了QSettings对象的访问哪个位置。 “**X**“表示该位置是相关联的主力位置的QSettings对象，并同时用于阅读和写作， ”O“是指阅读时的位置作为后备。

| Locations | `obj1` | `obj2` | `obj3` | `obj4` |
| --- | --- | --- | --- | --- |
| 1\. User, Application | **X** |  |  |  |
| 2\. User, Organization | o | **X** |  |  |
| 3\. System, Application | o |  | **X** |  |
| 4\. System, Organization | o | o | o | **X** |

这种机制的好处在于，它可以在Qt所支持的所有平台，并且它还是给你一个很大的灵活性，而不需要你指定的任何文件名或注册表路径。

如果你想使用在所有平台上，而不是原生API INI文件，你可以传递[QSettings.IniFormat](qsettings.html#Format-enum)作为第一个参数传递给QSettings的构造函数，其次是范围，组织名称和应用程序名称：

```
     QSettings settings(QSettings.IniFormat, QSettings.UserScope,
                        "MySoft", "Star Runner");

```

该[Settings Editor](index.htm)例如，您可以尝试不同的设置位置，并作为默认选择开启或关闭。

### Restoring the State of a GUI Application

QSettings通常被用来存储一个图形用户界面的应用程序的状态。下面的例子演示了如何使用QSettings来保存和恢复应用程序的主窗口的几何形状。

```
 void MainWindow.writeSettings()
 {
     QSettings settings("Moose Soft", "Clipper");

     settings.beginGroup("MainWindow");
     settings.setValue("size", size());
     settings.setValue("pos", pos());
     settings.endGroup();
 }

 void MainWindow.readSettings()
 {
     QSettings settings("Moose Soft", "Clipper");

     settings.beginGroup("MainWindow");
     resize(settings.value("size", [QSize](qsize.html)(400, 400)).toSize());
     move(settings.value("pos", [QPoint](qpoint.html)(200, 200)).toPoint());
     settings.endGroup();
 }

```

See [Window Geometry](index.htm#window-geometry)关于为什么它是最好打电话讨论[QWidget.resize](qwidget.html#size-prop)（）和[QWidget.move](qwidget.html#pos-prop)（ ），而不是[QWidget.setGeometry](qwidget.html#geometry-prop)（ ）来还原窗口的几何形状。

该`readSettings()`和`writeSettings()`功能必须从主窗口的构造函数和close事件处理程序中调用如下：

```
 MainWindow.MainWindow()
 {
     ...
     readSettings();
 }

 void MainWindow.closeEvent([QCloseEvent](qcloseevent.html) *event)
 {
     if (userReallyWantsToQuit()) {
         writeSettings();
         event->accept();
     } else {
         event->ignore();
     }
 }

```

请参阅[Application](index.htm)例如对于使用QSettings一个自包含的例子。

### Accessing Settings from Multiple Threads or Processes Simultaneously

QSettings是[reentrant](index.htm#reentrant)。这意味着，你可以在不同的线程中同时使用不同的QSettings对象。这保证代表，即使在​​QSettings对象引用磁盘上的同一个文件（或在系统注册表中的相同条目） 。如果设置是通过一个QSettings对象修改，更改将立即可见在同一位置上运行，而且住在同一个过程中的任何其他QSettings对象。

QSettings可以安全使用来自不同的进程（可以是您的应用程序在同一时间或不同的应用程序运行完全不同的实例）来读取和写入到同一个系统中的位置。它使用的谘询文件锁定和智能融合算法，以确保数据的完整性。需要注意的是[sync](qsettings.html#sync)（ ）进口（除了写这个QSettings的变化）由其他进程的变化。

### Platform-Specific Notes

#### Locations Where Application Settings Are Stored

诚如[Fallback Mechanism](#fallback-mechanism)节中， QSettings存储设置在四个位置，这取决于设置是否用户特定的或系统范围以及是否设置是特定于应用程序或组织范围内的应用程序。为简单起见，我们假设该组织被称为MySoft和应用程序被称为少年阿虎。

在Unix系统中，如果文件格式是[NativeFormat](qsettings.html#Format-enum)，以下文件默认情况下使用：

1.  `$HOME/.config/MySoft/Star Runner.conf`（ Qt嵌入式Linux操作系统：`$HOME/Settings/MySoft/Star Runner.conf`）
2.  `$HOME/.config/MySoft.conf`（ Qt嵌入式Linux操作系统：`$HOME/Settings/MySoft.conf`）
3.  `/etc/xdg/MySoft/Star Runner.conf`
4.  `/etc/xdg/MySoft.conf`

在Mac OS X版本10.2和10.3 ，这些文件默认情况下使用：

1.  `$HOME/Library/Preferences/com.MySoft.Star Runner.plist`
2.  `$HOME/Library/Preferences/com.MySoft.plist`
3.  `/Library/Preferences/com.MySoft.Star Runner.plist`
4.  `/Library/Preferences/com.MySoft.plist`

在Windows上，[NativeFormat](qsettings.html#Format-enum)设置存储在以下注册表​​路径：

1.  `HKEY_CURRENT_USER\Software\MySoft\Star Runner`
2.  `HKEY_CURRENT_USER\Software\MySoft`
3.  `HKEY_LOCAL_MACHINE\Software\MySoft\Star Runner`
4.  `HKEY_LOCAL_MACHINE\Software\MySoft`

**Note:**在Windows上，在WOW64模式下运行32位程序，设置存储在以下注册表路径：`HKEY_LOCAL_MACHINE\Software\WOW6432node`。

如果文件格式是[IniFormat](qsettings.html#Format-enum)下列文件用于在Unix和Mac OS X ：

1.  `$HOME/.config/MySoft/Star Runner.ini`（ Qt嵌入式Linux操作系统：`$HOME/Settings/MySoft/Star Runner.ini`）
2.  `$HOME/.config/MySoft.ini`（ Qt嵌入式Linux操作系统：`$HOME/Settings/MySoft.ini`）
3.  `/etc/xdg/MySoft/Star Runner.ini`
4.  `/etc/xdg/MySoft.ini`

在Windows中，下列文件用于：

1.  `%APPDATA%\MySoft\Star Runner.ini`
2.  `%APPDATA%\MySoft.ini`
3.  `%COMMON_APPDATA%\MySoft\Star Runner.ini`
4.  `%COMMON_APPDATA%\MySoft.ini`

该`%APPDATA%`路径通常是`C:\Documents and Settings\_User Name_\Application Data`;的`%COMMON_APPDATA%`路径通常是`C:\Documents and Settings\All Users\Application Data`。

在Symbian ，用于以下两个文件[IniFormat](qsettings.html#Format-enum)和[NativeFormat](qsettings.html#Format-enum)（在这个例子中，我们假定该应用程序被安装在`e-drive`和它的安全ID是`0xECB00931`） ：

1.  `c:\data\.config\MySoft\Star Runner.conf`
2.  `c:\data\.config\MySoft.conf`
3.  `e:\private\ecb00931\MySoft\Star Runner.conf`
4.  `e:\private\ecb00931\MySoft.conf`

该[SystemScope](qsettings.html#Scope-enum)设置位置是从应用程序的安装驱动器和安全ID （ UID3 ）确定。如果应用程序是内置在ROM上，驱动器用于[SystemScope](qsettings.html#Scope-enum) is `c:`。

**Note:**塞班[SystemScope](qsettings.html#Scope-enum)设置为默认私有的应用程序和应用程序之间不共享，不像其他的环境。

为路径`.ini`和`.conf`文件可以通过改变[setPath](qsettings.html#setPath)（ ） 。在Unix和Mac OS X ，用户可以重写它们通过设置`XDG_CONFIG_HOME`环境变量，见[setPath](qsettings.html#setPath)（ ）了解详情。

#### Accessing INI and .plist Files Directly

有时候，你想访问存储在一个特定的文件或注册表路径设置。在所有的平台上，如果你想直接读取INI文件，则可以使用QSettings的构造函数接受一个文件名作为第一个参数，并通过[QSettings.IniFormat](qsettings.html#Format-enum)作为第二个参数。例如：

```
 QSettings settings("/home/petra/misc/myapp.ini",
                    QSettings.IniFormat);

```

然后，您可以使用QSettings对象来读取和写入文件中的设置。

在Mac OS X中，可以访问基于XML的`.plist`通过传递文件[QSettings.NativeFormat](qsettings.html#Format-enum)作为第二个参数。例如：

```
 QSettings settings("/Users/petra/misc/myapp.plist",
                    QSettings.NativeFormat);

```

#### Accessing the Windows Registry Directly

在Windows中， QSettings可以让你访问已写入和QSettings （或设置，支持的格式，例如，字符串数据）在系统注册表设置。这是通过构建一个QSettings对象在注册表中的路径和完成[QSettings.NativeFormat](qsettings.html#Format-enum)。

例如：

```
 QSettings settings("HKEY_CURRENT_USER\\Software\\Microsoft\\Office",
                    QSettings.NativeFormat);

```

所有出现在指定路径下的注册表项，可以读取或通过QSettings对象写像往常一样（使用正斜杠，而不是反斜杠） 。例如：

```
 settings.setValue("11.0/Outlook/Security/DontTrustInstalledFiles", 0);

```

需要注意的是反斜杠字符是，如前所述，使用QSettings来单独的子项。因此，您无法读取或写入包含斜杠或反斜杠Windows的注册表条目，您必须使用本机Windows API，如果你需要的话。

#### Accessing Common Registry Settings on Windows

在Windows上，它有可能为一键都有一个值和子项。它的默认值是使用“默认”或访问“ 。 ”代替一个子项：

```
 settings.setValue("HKEY_CURRENT_USER\\MySoft\\Star Runner\\Galaxy", "Milkyway");
 settings.setValue("HKEY_CURRENT_USER\\MySoft\\Star Runner\\Galaxy\\Sun", "OurStar");
 settings.value("HKEY_CURRENT_USER\\MySoft\\Star Runner\\Galaxy\\Default"); // returns "Milkyway"

```

在其它非Windows平台， “默认”和“ 。 ”将被视为常规的子项。

#### Securing application settings in Symbian

[UserScope](qsettings.html#Scope-enum)在Symbian的设置是可写的默认的应用程序。为了保护和访问其他应用程序篡改应用程序设置，该设置需要放置在应用程序的私有安全区域。这可以通过直接指定给私人区域中的设置存储路径来完成。下面的代码片断改变[UserScope](qsettings.html#Scope-enum)至`c:/private/ecb00931/MySoft.conf`（提供的应用程序被安装在`c-drive`和它的安全ID是`0xECB00931`：

```
 QSettings settings([QApplication](qapplication.html).applicationDirPath() + "/MySoft.conf");

```

架构库（如Qt本身）可以使用存储配置和高速缓存设置[UserScope](qsettings.html#Scope-enum)，这是方便和可写的其他应用程序。如果应用程序是很安全的敏感或采用高平台的安全功能，它可以谨慎地也迫使框架的设置将存储在应用程序的私有目录。这可以通过改变的缺省路径进行[UserScope](qsettings.html#Scope-enum)前[QApplication](qapplication.html)创建：

```
 #include <QSettings>
 #include <QDesktopServices>
 int main(int argc, char *argv[])
 {
 #ifdef Q_OS_SYMBIAN
     // Use QDesktopServices:storageLocation as QApplication is not yet created
     QSettings.setPath(
         QSettings.NativeFormat, QSettings.UserScope,
         [QDesktopServices](qdesktopservices.html).storageLocation([QDesktopServices](qdesktopservices.html).DataLocation) + "/settings");
 #endif
     [QApplication](qapplication.html) app(argc, argv);

     ...
 }

```

请注意，这可能会影响框架库“功能，如果他们希望在应用程序之间共享的设置。

#### Changing the location of global Qt settings on Mac OS X

在Mac OS X ，全球Qt的设置（存储在`com.trolltech.plist`）存储在两种情况下应用程序设置文件：

1.  如果应用程序在Mac OS X中的沙箱运行（在Mac OS X 10.7或更高版本）或
2.  如果`Info.plist`该应用程序的文件中包含的关键`"ForAppStore"`与该值`"yes"`

在这些情况下，应用程序设置文件使用该应用程序的包标识符，它因此必须在应用程序的设置命名`Info.plist`文件中。

此功能提供方便的Qt应用程序的验收到Mac App Store的，如在存储全局的Qt设置的默认行为`com.trolltech.plist`文件不符合Mac App Store的文件系统的使用要求。有关提交Qt应用程序在Mac App Store的更多信息，请参阅 [Preparing a Qt application for Mac App Store submission](index.htm#preparing-a-qt-application-for-mac-app-store-submission)。

#### Platform Limitations

尽管QSettings试图抚平支持的不同的平台之间的差异，还存在着一些分歧，你应该知道，当移植应用程序的：

*   The Windows system registry has the following limitations: A subkey may not exceed 255 characters, an entry's value may not exceed 16,383 characters, and all the values of a key may not exceed 65,535 characters. One way to work around these limitations is to store the settings using the [IniFormat](qsettings.html#Format-enum) instead of the [NativeFormat](qsettings.html#Format-enum).
*   On Mac OS X, [allKeys](qsettings.html#allKeys)() will return some extra keys for global settings that apply to all applications. These keys can be read using [value](qsettings.html#value)() but cannot be changed, only shadowed. Calling setFallbacksEnabled(false) will hide these global settings.
*   On Mac OS X, the CFPreferences API used by QSettings expects Internet domain names rather than organization names. To provide a uniform API, QSettings derives a fake domain name from the organization name (unless the organization name already is a domain name, e.g. OpenOffice.org). The algorithm appends ".com" to the company name and replaces spaces and other illegal characters with hyphens. If you want to specify a different domain name, call [QCoreApplication.setOrganizationDomain](qcoreapplication.html#organizationDomain-prop)(), [QCoreApplication.setOrganizationName](qcoreapplication.html#organizationName-prop)(), and [QCoreApplication.setApplicationName](qcoreapplication.html#applicationName-prop)() in your `main()` function and then use the default QSettings constructor. Another solution is to use preprocessor directives, for example:

    ```
     #ifdef Q_WS_MAC
         QSettings settings("grenoullelogique.fr", "Squash");
     #else
         QSettings settings("Grenoulle Logique", "Squash");
     #endif

    ```

*   On Unix and Mac OS X systems, the advisory file locking is disabled if NFS (or AutoFS or CacheFS) is detected to work around a bug in the NFS fcntl() implementation, which hangs forever if statd or lockd aren't running. Also, the locking isn't performed when accessing `.plist` files.
*   On the BlackBerry platform, applications run in a sandbox. They are not allowed to read or write outside of this sandbox. This involves the following limitations:
    *   As there is only a single scope the scope is simply ignored.
    *   The [Fallback Mechanism](#fallback-mechanism) is not applied, i.e. only a single location is considered.
    *   It is advised against setting and using custom file paths.

* * *

## Type Documentation

```
QSettings.Format
```

该枚举类型指定使用的存储格式[QSettings](qsettings.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QSettings.NativeFormat` | `0` | Store the settings using the most appropriate storage format for the platform. On Windows, this means the system registry; on Mac OS X, this means the CFPreferences API; on Unix, this means textual configuration files in INI format. |
| `QSettings.IniFormat` | `1` | 存储在INI文件中的设置。 |
| `QSettings.InvalidFormat` | `16` | 特殊值返回的[registerFormat](qsettings.html#registerFormat)（ ） 。 |

在Unix上， NativeFormat和IniFormat意思是一样的，只是文件扩展名是不同的（`.conf`为NativeFormat ，`.ini`为IniFormat ） 。

INI文件的格式是， Qt支持所有平台上的Windows文件格式。在没有一个INI标准，我们尝试按照微软确实，但下列情况除外：

*   If you store types that [QVariant](qvariant.html) can't convert to [QString](qstring.html) (e.g., [QPoint](qpoint.html), [QRect](qrect.html), and [QSize](qsize.html)), Qt uses an `@`-based syntax to encode the type. For example:

    ```
     pos = @Point(100 100)

    ```

    为了最大限度地减少兼容性问题，任何`@`没有出现在值的第一个位置或后面没有一个Qt类型（`Point`，`Rect`，`Size`等）被视为普通字符。

*   Although backslash is a special character in INI files, most Windows applications don't escape backslashes (`\`) in file paths:

    ```
     windir = C:\Windows

    ```

    [QSettings](qsettings.html)始终将反斜杠为一个特殊字符，并提供用于读取或写入这样的条目没有API 。

*   The INI file format has severe restrictions on the syntax of a key. Qt works around this by using `%` as an escape character in keys. In addition, if you save a top-level setting (a key with no slashes in it, e.g., "someKey"), it will appear in the INI file's "General" section. To avoid overwriting other keys, if you save something using the a key such as "General/someKey", the key will be located in the "%General" section, _not_ in the "General" section.
*   Following the philosophy that we should be liberal in what we accept and conservative in what we generate, [QSettings](qsettings.html) will accept Latin-1 encoded INI files, but generate pure ASCII files, where non-ASCII values are encoded using standard INI escape sequences. To make the INI files more readable (but potentially less compatible), call [setIniCodec](qsettings.html#setIniCodec)().

**See also** [registerFormat](qsettings.html#registerFormat)（）和[setPath](qsettings.html#setPath)（ ） 。

```
QSettings.Scope
```

此枚举指定的设置是否用户特定的或同一系统的所有用户共享。

| Constant | Value | Description |
| --- | --- | --- |
| `QSettings.UserScope` | `0` | 在特定于当前用户（例如，在用户的主目录）的位置存储设置。 |
| `QSettings.SystemScope` | `1` | 在全球的位置存储设置，使在同一台机器上的所有用户访问同一组的设置。 |

**See also** [setPath](qsettings.html#setPath)（ ） 。

```
QSettings.Status
```

下面的状态值是可能的：

| Constant | Value | Description |
| --- | --- | --- |
| `QSettings.NoError` | `0` | 未发生错误。 |
| `QSettings.AccessError` | `1` | 出现访问错误（例如试图写一个只读文件） 。 |
| `QSettings.FormatError` | `2` | 发生了格式错误（例如加载一个格式错误的INI文件） 。 |

**See also** [status](qsettings.html#status)（ ） 。

* * *

## Method Documentation

```
QSettings.__init__ (self, QString organization, QString application = QString(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSettings](qsettings.html)对象，用于访问应用程序的设置，称为_application_从所谓的组织_organization_，并与家长_parent_。

例如：

```
 [QSettings](qsettings.html) settings("Moose Tech", "Facturo-Pro");

```

范围设置为[QSettings.UserScope](qsettings.html#Scope-enum)以及格式被设置为[QSettings.NativeFormat](qsettings.html#Format-enum)（即调用[setDefaultFormat](qsettings.html#setDefaultFormat)（ ）之前调用此构造函数没有效果） 。

**See also** [setDefaultFormat](qsettings.html#setDefaultFormat)（）和[Fallback Mechanism](qsettings.html#fallback-mechanism)。

```
QSettings.__init__ (self, Scope scope, QString organization, QString application = QString(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSettings](qsettings.html)对象，用于访问应用程序的设置，称为_application_从所谓的组织_organization_，并与家长_parent_。

If _scope_ is [QSettings.UserScope](qsettings.html#Scope-enum)时，[QSettings](qsettings.html)对象首先搜索用户特定的设置，它会搜索系统范围的设置作为后备之前。如果_scope_ is [QSettings.SystemScope](qsettings.html#Scope-enum)时，[QSettings](qsettings.html)对象将忽略用户特定的设置，并提供访问系统范围的设置。

存储格式被设置为[QSettings.NativeFormat](qsettings.html#Format-enum)（即调用[setDefaultFormat](qsettings.html#setDefaultFormat)（ ）之前调用此构造函数没有效果） 。

如果没有应用程序名，则该[QSettings](qsettings.html)对象将只能访问整个组织的[locations](qsettings.html#fallback-mechanism)。

**See also** [setDefaultFormat](qsettings.html#setDefaultFormat)（ ） 。

```
QSettings.__init__ (self, Format format, Scope scope, QString organization, QString application = QString(), QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSettings](qsettings.html)对象，用于访问应用程序的设置，称为_application_从所谓的组织_organization_，并与家长_parent_。

If _scope_ is [QSettings.UserScope](qsettings.html#Scope-enum)时，[QSettings](qsettings.html)对象首先搜索用户特定的设置，它会搜索系统范围的设置作为后备之前。如果_scope_ is [QSettings.SystemScope](qsettings.html#Scope-enum)时，[QSettings](qsettings.html)对象将忽略用户特定的设置，并提供访问系统范围的设置。

If _format_ is [QSettings.NativeFormat](qsettings.html#Format-enum)，本机API被用于存储设置。如果_format_ is [QSettings.IniFormat](qsettings.html#Format-enum)中， INI格式被使用。

如果没有应用程序名，则该[QSettings](qsettings.html)对象将只能访问整个组织的[locations](qsettings.html#fallback-mechanism)。

```
QSettings.__init__ (self, QString fileName, Format format, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSettings](qsettings.html)对象用于访问存储在名为该文件中的设置_fileName_，与父_parent_。如果文件不存在，则创建它。

If _format_ is [QSettings.NativeFormat](qsettings.html#Format-enum)，的意思_fileName_取决于平台。在Unix上，_fileName_是INI文件的名称。在Mac OS X ，_fileName_是一个名字`.plist`文件中。在Windows上，_fileName_是在系统注册表中的路径。

If _format_ is [QSettings.IniFormat](qsettings.html#Format-enum)，_fileName_是INI文件的名称。

**Warning:**此功能提供了方便。它的工作原理以及用于访问INI或`.plist`通过Qt的产生，但文件可能在最初由其他程序，文件，发现了一些语法失败。尤其要注意以下限制：

*   [QSettings](qsettings.html) provides no way of reading INI "path" entries, i.e., entries with unescaped slash characters. (This is because these entries are ambiguous and cannot be resolved automatically.)
*   In INI files, [QSettings](qsettings.html) uses the `@` character as a metacharacter in some contexts, to encode Qt-specific data types (e.g., `@Rect`), and might therefore misinterpret it when it occurs in pure INI files.

**See also** [fileName](qsettings.html#fileName)（ ） 。

```
QSettings.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSettings](qsettings.html)对象用于访问应用程序和组织的设置与调用先前设置[QCoreApplication.setOrganizationName](qcoreapplication.html#organizationName-prop)（ ）[QCoreApplication.setOrganizationDomain](qcoreapplication.html#organizationDomain-prop)（）和[QCoreApplication.setApplicationName](qcoreapplication.html#applicationName-prop)（ ） 。

的范围是[QSettings.UserScope](qsettings.html#Scope-enum)和格式是[defaultFormat](qsettings.html#defaultFormat)（ ） （[QSettings.NativeFormat](qsettings.html#Format-enum)默认情况下） 。使用[setDefaultFormat](qsettings.html#setDefaultFormat)（ ）调用此构造函数来改变使用此构造函数的默认格式之前。

代码

```
 [QSettings](qsettings.html) settings("Moose Soft", "Facturo-Pro");

```

相当于

```
 [QCoreApplication](qcoreapplication.html).setOrganizationName("Moose Soft");
 [QCoreApplication](qcoreapplication.html).setApplicationName("Facturo-Pro");
 [QSettings](qsettings.html) settings;

```

If [QCoreApplication.setOrganizationName](qcoreapplication.html#organizationName-prop)（）和[QCoreApplication.setApplicationName](qcoreapplication.html#applicationName-prop)（）先前没有被调用，在[QSettings](qsettings.html)对象将不能读取或写入的任何设置，并[status](qsettings.html#status)（ ）将返回[AccessError](qsettings.html#Status-enum)。

在Mac OS X中，如果两个名称和互联网域名都为组织指定的域优先于名称。在其他平台上，该名优先于域。

**See also** [QCoreApplication.setOrganizationName](qcoreapplication.html#organizationName-prop)（ ）[QCoreApplication.setOrganizationDomain](qcoreapplication.html#organizationDomain-prop)（ ）[QCoreApplication.setApplicationName](qcoreapplication.html#applicationName-prop)（）和[setDefaultFormat](qsettings.html#setDefaultFormat)（ ） 。

```
QStringList QSettings.allKeys (self)
```

返回所有键，包括子项的列表，可以使用读取的[QSettings](qsettings.html)对象。

例如：

```
 [QSettings](qsettings.html) settings;
 settings.setValue("fridge/color", [Qt](qt.html).white);
 settings.setValue("fridge/size", [QSize](qsize.html)(32, 96));
 settings.setValue("sofa", true);
 settings.setValue("tv", false);

 [QStringList](qstringlist.html) keys = settings.allKeys();
 // keys: ["fridge/color", "fridge/size", "sofa", "tv"]

```

如果一组设置使用[beginGroup](qsettings.html#beginGroup)（ ）只返回该组中的按键，没有组前缀：

```
 settings.beginGroup("fridge");
 keys = settings.allKeys();
 // keys: ["color", "size"]

```

**See also** [childGroups](qsettings.html#childGroups)（）和[childKeys](qsettings.html#childKeys)（ ） 。

```
QString QSettings.applicationName (self)
```

返回用于存储设置的应用程序的名称。

此功能被引入Qt的4.4 。

**See also** [QCoreApplication.applicationName](qcoreapplication.html#applicationName-prop)（ ）[format](qsettings.html#format)（ ）[scope](qsettings.html#scope)（）和[organizationName](qsettings.html#organizationName)（ ） 。

```
QSettings.beginGroup (self, QString prefix)
```

追加可_prefix_到当前组。

当前组会自动追加到指定所有键[QSettings](qsettings.html)。此外，查询功能，如[childGroups](qsettings.html#childGroups)（ ）[childKeys](qsettings.html#childKeys)（）和[allKeys](qsettings.html#allKeys)（ ）是基于组。缺省情况下，组设置。

组是有用的，以避免一遍又一遍相同的设置路径打字。例如：

```
 settings.beginGroup("mainwindow");
 settings.setValue("size", win->size());
 settings.setValue("fullScreen", win->isFullScreen());
 settings.endGroup();

 settings.beginGroup("outputpanel");
 settings.setValue("visible", panel->isVisible());
 settings.endGroup();

```

这将设置的三个设置值：

*   `mainwindow/size`
*   `mainwindow/fullScreen`
*   `outputpanel/visible`

Call [endGroup](qsettings.html#endGroup)（ ）到当前组复位到它是什么相应的beginGroup （ ）调用之前。组可以嵌套。

**See also** [endGroup](qsettings.html#endGroup)（）和[group](qsettings.html#group)（ ） 。

```
int QSettings.beginReadArray (self, QString prefix)
```

添加_prefix_到当前组，并开始从数组中读取。返回该数组的大小。

例如：

```
 struct Login {
     [QString](qstring.html) userName;
     [QString](qstring.html) password;
 };
 [QList](index.htm)<Login> logins;
 ...

 [QSettings](qsettings.html) settings;
 int size = settings.beginReadArray("logins");
 for (int i = 0; i < size; ++i) {
     settings.setArrayIndex(i);
     Login login;
     login.userName = settings.value("userName").toString();
     login.password = settings.value("password").toString();
     logins.append(login);
 }
 settings.endArray();

```

使用[beginWriteArray](qsettings.html#beginWriteArray)（）写在首位的数组。

**See also** [beginWriteArray](qsettings.html#beginWriteArray)（ ）[endArray](qsettings.html#endArray)（）和[setArrayIndex](qsettings.html#setArrayIndex)（ ） 。

```
QSettings.beginWriteArray (self, QString prefix, int size = -1)
```

添加_prefix_到当前组，并开始写大小的数组_size_。如果_size_为-1 （默认值） ，它会自动根据写入的条目的索引号。

如果你有一定的组键的许多事件，你可以使用数组，使您的生活更轻松。例如，让我们假设你想保存的用户名和密码的长度可变的列表。那么你可以这样写：

```
 struct Login {
     [QString](qstring.html) userName;
     [QString](qstring.html) password;
 };
 [QList](index.htm)<Login> logins;
 ...

 [QSettings](qsettings.html) settings;
 settings.beginWriteArray("logins");
 for (int i = 0; i < logins.size(); ++i) {
     settings.setArrayIndex(i);
     settings.setValue("userName", list.at(i).userName);
     settings.setValue("password", list.at(i).password);
 }
 settings.endArray();

```

生成的密钥将有形式

*   `logins/size`
*   `logins/1/userName`
*   `logins/1/password`
*   `logins/2/userName`
*   `logins/2/password`
*   `logins/3/userName`
*   `logins/3/password`
*   ...

读回一个数组，使用[beginReadArray](qsettings.html#beginReadArray)（ ） 。

**See also** [beginReadArray](qsettings.html#beginReadArray)（ ）[endArray](qsettings.html#endArray)（）和[setArrayIndex](qsettings.html#setArrayIndex)（ ） 。

```
QStringList QSettings.childGroups (self)
```

返回包含所有按键键顶层组的列表，可以使用读取的[QSettings](qsettings.html)对象。

例如：

```
 [QSettings](qsettings.html) settings;
 settings.setValue("fridge/color", [Qt](qt.html).white);
 settings.setValue("fridge/size", [QSize](qsize.html)(32, 96));
 settings.setValue("sofa", true);
 settings.setValue("tv", false);

 [QStringList](qstringlist.html) groups = settings.childGroups();
 // groups: ["fridge"]

```

如果一组设置使用[beginGroup](qsettings.html#beginGroup)（ ） ，则返回该组中的第一级按键，没有组前缀。

```
 settings.beginGroup("fridge");
 groups = settings.childGroups();
 // groups: []

```

您可以通过整个层次结构设置使用导航[childKeys](qsettings.html#childKeys)（）和childGroups （ ）递归。

**See also** [childKeys](qsettings.html#childKeys)（）和[allKeys](qsettings.html#allKeys)（ ） 。

```
QStringList QSettings.childKeys (self)
```

返回所有顶级键的列表，可以使用读取的[QSettings](qsettings.html)对象。

例如：

```
 [QSettings](qsettings.html) settings;
 settings.setValue("fridge/color", [Qt](qt.html).white);
 settings.setValue("fridge/size", [QSize](qsize.html)(32, 96));
 settings.setValue("sofa", true);
 settings.setValue("tv", false);

 [QStringList](qstringlist.html) keys = settings.childKeys();
 // keys: ["sofa", "tv"]

```

如果一组设置使用[beginGroup](qsettings.html#beginGroup)（ ） ，则返回该组中的顶级键，而不群的前缀：

```
 settings.beginGroup("fridge");
 keys = settings.childKeys();
 // keys: ["color", "size"]

```

您可以通过整个层次结构设置使用CHILDKEYS浏览（）和[childGroups](qsettings.html#childGroups)（ ）递归。

**See also** [childGroups](qsettings.html#childGroups)（）和[allKeys](qsettings.html#allKeys)（ ） 。

```
QSettings.clear (self)
```

删除所有条目关联到这个主位置[QSettings](qsettings.html)对象。

在备用位置的条目不会被删除。

如果你只是想删除当前条目[group](qsettings.html#group)（ ） ，使用删除（“” ）来代替。

**See also** [remove](qsettings.html#remove)（）和[setFallbacksEnabled](qsettings.html#setFallbacksEnabled)（ ） 。

```
bool QSettings.contains (self, QString key)
```

如果存在一个名为设置，则返回True_key_否则返回False 。

如果一组设置使用[beginGroup](qsettings.html#beginGroup)（ ）_key_被视为相对于该组。

请注意，Windows注册表和INI文件使用不区分大小写键，而在Mac OS X中的碳Preferences API使用区分大小写键。为了避免可移植性问题，请参见[Section and Key Syntax](qsettings.html#section-and-key-syntax)规则。

**See also** [value](qsettings.html#value)（）和[setValue](qsettings.html#setValue)（ ） 。

```
Format QSettings.defaultFormat ()
```

[](qsettings.html#Format-enum)

[用于存储的设置返回默认文件格式](qsettings.html#Format-enum)[QSettings](qsettings.html)（[QObject](qobject.html)* ）构造函数。如果没有默认格式设置，[QSettings.NativeFormat](qsettings.html#Format-enum)被使用。

此功能被引入Qt的4.4 。

**See also** [setDefaultFormat](qsettings.html#setDefaultFormat)（）和[format](qsettings.html#format)（ ） 。

```
QSettings.endArray (self)
```

关闭已启动使用数组[beginReadArray](qsettings.html#beginReadArray)（）或[beginWriteArray](qsettings.html#beginWriteArray)（ ） 。

**See also** [beginReadArray](qsettings.html#beginReadArray)（）和[beginWriteArray](qsettings.html#beginWriteArray)（ ） 。

```
QSettings.endGroup (self)
```

复位组，这是什么相应的前[beginGroup](qsettings.html#beginGroup)（ ）调用。

例如：

```
 settings.beginGroup("alpha");
 // settings.group() == "alpha"

 settings.beginGroup("beta");
 // settings.group() == "alpha/beta"

 settings.endGroup();
 // settings.group() == "alpha"

 settings.endGroup();
 // settings.group() == ""

```

**See also** [beginGroup](qsettings.html#beginGroup)（）和[group](qsettings.html#group)（ ） 。

```
bool QSettings.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QSettings.fallbacksEnabled (self)
```

返回True如果启用了回退，否则返回False 。

默认情况下，回退启用。

**See also** [setFallbacksEnabled](qsettings.html#setFallbacksEnabled)（ ） 。

```
QString QSettings.fileName (self)
```

返回在使用此书面设置的路径[QSettings](qsettings.html)对象被存储。

在Windows上，如果格式是[QSettings.NativeFormat](qsettings.html#Format-enum)，返回值是一个系统注册表路径，而不是文件路径。

**See also** [isWritable](qsettings.html#isWritable)（）和[format](qsettings.html#format)（ ） 。

```
Format QSettings.format (self)
```

[

返回用于存储设置的格式。

此功能被引入Qt的4.4 。

](qsettings.html#Format-enum)

[**See also**](qsettings.html#Format-enum) [defaultFormat](qsettings.html#defaultFormat)（ ）[fileName](qsettings.html#fileName)（ ）[scope](qsettings.html#scope)（ ）[organizationName](qsettings.html#organizationName)（）和[applicationName](qsettings.html#applicationName)（ ） 。

```
QString QSettings.group (self)
```

返回当前组。

**See also** [beginGroup](qsettings.html#beginGroup)（）和[endGroup](qsettings.html#endGroup)（ ） 。

```
QTextCodec QSettings.iniCodec (self)
```

[

返回用于访问INI文件的编解码器。缺省情况下，编解码器使用，所以返回空指针。

此功能被引入Qt的4.5 。

](qtextcodec.html)

[**See also**](qtextcodec.html) [setIniCodec](qsettings.html#setIniCodec)（ ） 。

```
bool QSettings.isWritable (self)
```

返回True如果设置可以使用此写入[QSettings](qsettings.html)对象，否则返回False 。

为什么isWritable （ ）也可能返回False的原因之一是，如果[QSettings](qsettings.html)运行在一个只读文件。

**Warning:**此功能是不完全可靠，因为文件权限可以随时更改。

**See also** [fileName](qsettings.html#fileName)（ ）[status](qsettings.html#status)（）和[sync](qsettings.html#sync)（ ） 。

```
QString QSettings.organizationName (self)
```

返回用于存储设置的组织名称。

此功能被引入Qt的4.4 。

**See also** [QCoreApplication.organizationName](qcoreapplication.html#organizationName-prop)（ ）[format](qsettings.html#format)（ ）[scope](qsettings.html#scope)（）和[applicationName](qsettings.html#applicationName)（ ） 。

```
QSettings.remove (self, QString key)
```

删除设置_key_和任何一个子设定_key_。

例如：

```
 [QSettings](qsettings.html) settings;
 settings.setValue("ape");
 settings.setValue("monkey", 1);
 settings.setValue("monkey/sea", 2);
 settings.setValue("monkey/doe", 4);

 settings.remove("monkey");
 [QStringList](qstringlist.html) keys = settings.allKeys();
 // keys: ["ape"]

```

请注意，如果回退的地点之一包含具有相同键的设置，该设置将调用remove （ ）后是可见的。

If _key_是一个空字符串，在目前的所有键[group](qsettings.html#group)（）被除去。例如：

```
 [QSettings](qsettings.html) settings;
 settings.setValue("ape");
 settings.setValue("monkey", 1);
 settings.setValue("monkey/sea", 2);
 settings.setValue("monkey/doe", 4);

 settings.beginGroup("monkey");
 settings.remove("");
 settings.endGroup();

 [QStringList](qstringlist.html) keys = settings.allKeys();
 // keys: ["ape"]

```

请注意，Windows注册表和INI文件使用不区分大小写键，而在Mac OS X中的碳Preferences API使用区分大小写键。为了避免可移植性问题，请参见[Section and Key Syntax](qsettings.html#section-and-key-syntax)规则。

**See also** [setValue](qsettings.html#setValue)（ ）[value](qsettings.html#value)（）和[contains](qsettings.html#contains)（ ） 。

```
Scope QSettings.scope (self)
```

[

返回用于存储设置的范围。

此功能被引入Qt的4.4 。

](qsettings.html#Scope-enum)

[**See also**](qsettings.html#Scope-enum) [format](qsettings.html#format)（ ）[organizationName](qsettings.html#organizationName)（）和[applicationName](qsettings.html#applicationName)（ ） 。

```
QSettings.setArrayIndex (self, int i)
```

当前数组的索引设置为_i_。呼叫功能，如[setValue](qsettings.html#setValue)（ ）[value](qsettings.html#value)（ ）[remove](qsettings.html#remove)（）和[contains](qsettings.html#contains)（ ）将运行在该索引处的数组项。

你必须调用[beginReadArray](qsettings.html#beginReadArray)（）或[beginWriteArray](qsettings.html#beginWriteArray)（ ）之前，你可以调用这个函数。

```
QSettings.setDefaultFormat (Format format)
```

设置默认的文件格式为给定的_format_，它被用于存储设定的[QSettings](qsettings.html)（[QObject](qobject.html)* ）构造函数。

如果没有默认格式设置，[QSettings.NativeFormat](qsettings.html#Format-enum)被使用。请参阅该文档[QSettings](qsettings.html)您正在使用，看看是否该构造函数会忽略这个功能的构造函数。

此功能被引入Qt的4.4 。

**See also** [defaultFormat](qsettings.html#defaultFormat)（）和[format](qsettings.html#format)（ ） 。

```
QSettings.setFallbacksEnabled (self, bool b)
```

套回退是否启用_b_。

默认情况下，回退启用。

**See also** [fallbacksEnabled](qsettings.html#fallbacksEnabled)（ ） 。

```
QSettings.setIniCodec (self, QTextCodec codec)
```

设置编解码器，用于访问INI文件（包括`.conf`在Unix文件）_codec_。编解码器，用于解码被从INI文件读取的数据，并用于编码被写入到文件中的任何数据。缺省情况下，编解码器用于和非ASCII字符都使用标准的INI转义序列编码。

**Warning:**该编解码器必须立即创建后设置的[QSettings](qsettings.html)对象，访问任何数据之前。

此功能被引入Qt的4.5 。

**See also** [iniCodec](qsettings.html#iniCodec)（ ） 。

```
QSettings.setIniCodec (self, str codecName)
```

这是一个重载函数。

设置编解码器，用于访问INI文件（包括`.conf`在Unix文件）复制到[QTextCodec](qtextcodec.html)对于由指定的编码_codecName_。为共同的价值观`codecName`包括“ ISO 8859 ”，“ UTF-8” ，和“UTF- 16” 。如果编码不被识别，没有任何反应。

此功能被引入Qt的4.5 。

**See also** [QTextCodec.codecForName](qtextcodec.html#codecForName)（ ） 。

```
QSettings.setPath (Format format, Scope scope, QString path)
```

设置用于存储设置为给定的路径_format_和_scope_，以_path_。该_format_可以自定义格式。

下面的表总结了默认值：

| Platform | Format | Scope | Path |
| --- | --- | --- | --- |
| Windows | [IniFormat](qsettings.html#Format-enum) | [UserScope](qsettings.html#Scope-enum) | `%APPDATA%` |
| [SystemScope](qsettings.html#Scope-enum) | `%COMMON_APPDATA%` |
| Unix | [NativeFormat](qsettings.html#Format-enum), [IniFormat](qsettings.html#Format-enum) | [UserScope](qsettings.html#Scope-enum) | `$HOME/.config` |
| [SystemScope](qsettings.html#Scope-enum) | `/etc/xdg` |
| Qt for Embedded Linux | [NativeFormat](qsettings.html#Format-enum), [IniFormat](qsettings.html#Format-enum) | [UserScope](qsettings.html#Scope-enum) | `$HOME/Settings` |
| [SystemScope](qsettings.html#Scope-enum) | `/etc/xdg` |
| Mac OS X | [IniFormat](qsettings.html#Format-enum) | [UserScope](qsettings.html#Scope-enum) | `$HOME/.config` |
| [SystemScope](qsettings.html#Scope-enum) | `/etc/xdg` |
| Symbian | [NativeFormat](qsettings.html#Format-enum), [IniFormat](qsettings.html#Format-enum) | [UserScope](qsettings.html#Scope-enum) | `c:/data/.config` |
| [SystemScope](qsettings.html#Scope-enum) | `&lt;drive&gt;/private/&lt;uid&gt;` |

默认[UserScope](qsettings.html#Scope-enum)在Unix和Mac OS X （路径`$HOME/.config`或$ HOME /设置）可以通过设置由用户复盖了`XDG_CONFIG_HOME`环境变量。默认[SystemScope](qsettings.html#Scope-enum)在Unix和Mac OS X （路径`/etc/xdg`）可以使用构建Qt库时，被复盖的`configure`脚本的`--sysconfdir`标志（见[QLibraryInfo](qlibraryinfo.html)有关详细信息） 。

设置[NativeFormat](qsettings.html#Format-enum)在Windows和Mac OS X的路径没有影响。

**Warning:**此功能不会影响现有的[QSettings](qsettings.html)对象。

这个函数是Qt 4.1中引入。

**See also** [registerFormat](qsettings.html#registerFormat)（ ） 。

```
QSettings.setSystemIniPath (QString dir)
```

```
QSettings.setUserIniPath (QString dir)
```

```
QSettings.setValue (self, QString key, QVariant value)
```

设定设定值_key_至_value_。如果_key_已经存在，原来的值将被复盖。

请注意，Windows注册表和INI文件使用不区分大小写键，而在Mac OS X中的碳Preferences API使用区分大小写键。为了避免可移植性问题，请参见[Section and Key Syntax](qsettings.html#section-and-key-syntax)规则。

例如：

```
 [QSettings](qsettings.html) settings;
 settings.setValue("interval", 30);
 settings.value("interval").toInt();     // returns 30

 settings.setValue("interval", 6.55);
 settings.value("interval").toDouble();  // returns 6.55

```

**See also** [value](qsettings.html#value)（ ）[remove](qsettings.html#remove)（）和[contains](qsettings.html#contains)（ ） 。

```
Status QSettings.status (self)
```

[](qsettings.html#Status-enum)

[返回指示会见了由的第一个错误状态码](qsettings.html#Status-enum)[QSettings](qsettings.html)或[QSettings.NoError](qsettings.html#Status-enum)如果没有发生错误。

要知道，[QSettings](qsettings.html)延迟执行某种操作。出于这个原因，你可能需要调用[sync](qsettings.html#sync)（） ，以确保存储在数据[QSettings](qsettings.html)呼叫状态（ ）之前被写入磁盘。

**See also** [sync](qsettings.html#sync)（ ） 。

```
QSettings.sync (self)
```

将任何未保存的更改永久存储，并重新载入已在此期间被修改由其他应用程序的任何设置。

此功能是从自动调用[QSettings](qsettings.html)的析构函数，并通过定期的事件循环，所以你通常不需要自己调用它。

**See also** [status](qsettings.html#status)（ ） 。

```
object QSettings.value (self, QString key, QVariant defaultValue = QVariant(), object type = None)
```

返回值用于设置_key_。如果设置不存在，返回_defaultValue_。

如果没有指定默认值，则默认[QVariant](qvariant.html)返回。

请注意，Windows注册表和INI文件使用不区分大小写键，而在Mac OS X中的碳Preferences API使用区分大小写键。为了避免可移植性问题，请参见[Section and Key Syntax](qsettings.html#section-and-key-syntax)规则。

例如：

```
 [QSettings](qsettings.html) settings;
 settings.setValue("animal/snake", 58);
 settings.value("animal/snake", 1024).toInt();   // returns 58
 settings.value("animal/zebra", 1024).toInt();   // returns 1024
 settings.value("animal/zebra").toInt();         // returns 0

```

**See also** [setValue](qsettings.html#setValue)（ ）[contains](qsettings.html#contains)（）和[remove](qsettings.html#remove)（ ） 。