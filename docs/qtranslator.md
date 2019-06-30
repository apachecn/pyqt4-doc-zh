# QTranslator Class Reference

## [[QtCore](index.htm) module]

该QTranslator这样类提供了文本输出的国际化支持。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool isEmpty (self)`
*   `bool load (self, QString fileName, QString directory = QString(), QString searchDelimiters = QString(), QString suffix = QString())`
*   `bool load (self, QLocale locale, QString fileName, QString prefix = QString(), QString directory = QString(), QString suffix = QString())`
*   `bool loadFromData (self, str data)`
*   `QString translate (self, str context, str sourceText, str disambiguation = None)`
*   `QString translate (self, str context, str sourceText, str comment, int n)`

* * *

## Detailed Description

该QTranslator这样类提供了文本输出的国际化支持。

这个类的一个对象包含了一组从源语言翻译成目标语言的。 QTranslator这样提供的功能来查找在翻译文件翻译。使用创建翻译文件[Qt Linguist](index.htm#qt-linguist)。

最常见的用途QTranslator这样的是：它使用加载翻译文件，安装[QApplication.installTranslator](qcoreapplication.html#installTranslator)（） ，并通过用它[QObject.tr](qobject.html#tr)（ ） 。这里的`main()`从功能上[Hello tr()](index.htm)例如：

```
 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html) app(argc, argv);

     QTranslator translator;
     translator.load("hellotr_la");
     app.installTranslator(&translator);

     [QPushButton](qpushbutton.html) hello([QPushButton](qpushbutton.html).tr("Hello world!"));
     hello.resize(100, 30);

     hello.show();
     return app.exec();
 }

```

需要注意的是，译者必须创建_before_应用程序的窗口小部件。

大多数应用程序都不需要做任何事情都要有这个类。这个类提供的其他功能是对翻译文件的工作应用中非常有用。

### Looking up Translations

它可以利用查找翻译[translate](qtranslator.html#translate)（ ） （如[tr](qobject.html#tr)（）和[QApplication.translate](qcoreapplication.html#translate)（ ）一样） 。该[translate](qtranslator.html#translate)（ ）函数需要三个参数：

*   The _context_ - usually the class name for the [tr](qobject.html#tr)() caller.
*   The _source text_ - usually the argument to [tr](qobject.html#tr)().
*   The _disambiguation_ - an optional string that helps disambiguate different uses of the same text in the same context.

例如，在一个对话框“取消”可能具有“ Anuluj ”时，程序在波兰的运行（在这种情况下，源文本将是“取消” ） 。上下文将（通常）是对话框的类名;有一般会是没有意见，而翻译的文本将是“ Anuluj ” 。

但它并不总是那么简单。打印机对话框中的设定进行双面打印和装订的西班牙语版本可能会同时需要“ Activado ”和“ Activada ”作为翻译为“​​已启用” 。在这种情况下，源文本将在这两种情况下“启用” ，并在上下文将是对话框的类名，但是这两个项目将有disambiguations如“双面打印”为1与“结合”，为其他。消歧使译者选择适当的性别为西班牙语版本，使Qt的翻译来区分。

### Using Multiple Translations

多个翻译文件可以安装在一个应用程序。翻译是在它们被安装在其相反的顺序搜索的，所以最近安装的翻译文件中搜索翻译第一和最早的翻译文件最后搜索。搜索一旦被发现包含匹配的字符串翻译停止。

这种机制使得它可以为特定的翻译被“选中”或优先于他人，只需通过它传递给从应用程序卸载翻译[QApplication.removeTranslator](qcoreapplication.html#removeTranslator)（ ）函数，并重新安装[QApplication.installTranslator](qcoreapplication.html#installTranslator)（ ） 。那么这将是第一次翻译要查找的字符串匹配。

* * *

## Method Documentation

```
QTranslator.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空消息文件对象的父_parent_未连接到任何文件。

```
bool QTranslator.isEmpty (self)
```

返回True如果翻译为空，否则返回False 。此功能适用于剥离和未移除的翻译文件。

```
bool QTranslator.load (self, QString fileName, QString directory = QString(), QString searchDelimiters = QString(), QString suffix = QString())
```

负载_filename_+_suffix_（ “ QM ”如果_suffix_未指定） ，其可以是绝对文件名或相对于_directory_。返回True如果加载成功的翻译，否则返回False 。

If _directory_没有被指定，应用程序的可执行文件的目录时（即作为[applicationDirPath()](qcoreapplication.html#applicationDirPath)） 。

这个翻译对象的以前的内容将被丢弃。

如果文件名不存在，其他的文件名尝试按以下顺序：

1.  文件名不_suffix_追加。
2.  文件名与一个字符之后的文字_search_delimiters_剥去（ “[_](index.html)“是默认的_search_delimiters_如果它是一个空字符串）和_suffix_。
3.  没有文件名剥离_suffix_追加。
4.  文件名再剥离等。

例如，在fr_CA语言环境中运行（法语加拿大）的应用程序可能调用的负载（ “ foo.fr_ca ” ， “ /选择/ foolib ” ） 。 load（）方法会然后尝试从该列表中打开的第一个现有可读的文件：

1.  `/opt/foolib/foo.fr_ca.qm`
2.  `/opt/foolib/foo.fr_ca`
3.  `/opt/foolib/foo.fr.qm`
4.  `/opt/foolib/foo.fr`
5.  `/opt/foolib/foo.qm`
6.  `/opt/foolib/foo`

```
bool QTranslator.load (self, QLocale locale, QString fileName, QString prefix = QString(), QString directory = QString(), QString suffix = QString())
```

负载_filename_+_prefix_+[ui language name](qlocale.html#uiLanguages)+_suffix_（ “ QM ”如果_suffix_未指定） ，其可以是绝对文件名或相对于_directory_。返回True如果加载成功的翻译，否则返回False 。

这个翻译对象的以前的内容将被丢弃。

如果文件名不存在，其他的文件名尝试按以下顺序：

1.  文件名不_suffix_追加。
2.  后文件与用户界面语言部分名称的“[_](index.html)“字符剥离和_suffix_。
3.  无剥离与用户界面语言部分文件名_suffix_追加。
4.  与用户界面语言部分文件名再剥离等

例如，运行在语言环境下的应用程序[ui languages](qlocale.html#uiLanguages) - “上课” ， “ FR- CA” ， “德”可以称之为负载（[QLocale.system](qlocale.html#system)（ ） ， “富” ， “ ” ， “ /选择/ foolib ” ， “ QM ” ） 。[load](qtranslator.html#load)（ ）将取代' - ' （破折号）与'[_](index.html)' （下划线）在UI语言，然后尝试从该列表中打开的第一个现有可读的文件：

1.  `/opt/foolib/foo.es.qm`
2.  `/opt/foolib/foo.es`
3.  `/opt/foolib/foo.fr_CA.qm`
4.  `/opt/foolib/foo.fr_CA`
5.  `/opt/foolib/foo.de.qm`
6.  `/opt/foolib/foo.de`
7.  `/opt/foolib/foo.fr.qm`
8.  `/opt/foolib/foo.fr`
9.  `/opt/foolib/foo.qm`
10.  `/opt/foolib/foo`。
11.  `/opt/foolib/foo`

对操作系统所在的文件系统是大小写敏感的，[QTranslator](qtranslator.html)也尝试加载区域名称的小写版本。

此功能被引入Qt的4.8 。

```
bool QTranslator.loadFromData (self, str data)
```

```
QString QTranslator.translate (self, str context, str sourceText, str disambiguation = None)
```

返回翻译的关键（_context_，_sourceText_，_disambiguation_） 。如果没有找到，还尝试（_context_，_sourceText_，“”） 。如果仍然失败，则返回一个空字符串。

如果您需要以编程方式插入翻译中的[QTranslator](qtranslator.html)这个功能可以重新实现。

**See also** [load](qtranslator.html#load)（ ） 。

```
QString QTranslator.translate (self, str context, str sourceText, str comment, int n)
```

这个函数的重载[translate](qtranslator.html#translate)（ ） 。

返回翻译的关键（_context_，_sourceText_，_disambiguation_） 。如果没有找到，还尝试（_context_，_sourceText_，“”） 。如果仍然失败，则返回一个空字符串。

If _n_是不是-1 ，它是用来选择的翻译（例如“ ％ n文件中找到”与“ ％不找到文件” ）以适当的形式。

**See also** [load](qtranslator.html#load)（ ） 。