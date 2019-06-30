# QTemporaryFile Class Reference

## [[QtCore](index.htm) module]

该QTemporaryFile类是一个操作上的临时文件的I / O设备。[More...](#details)

继承[QFile](qfile.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString templateName)`
*   `__init__ (self, QObject parent)`
*   `__init__ (self, QString templateName, QObject parent)`
*   `bool autoRemove (self)`
*   `QAbstractFileEngine fileEngine (self)`
*   `QString fileName (self)`
*   `QString fileTemplate (self)`
*   `bool open (self)`
*   `bool open (self, QIODevice.OpenMode flags)`
*   `setAutoRemove (self, bool b)`
*   `setFileTemplate (self, QString name)`

### Static Methods

*   `QTemporaryFile createLocalFile (QString fileName)`
*   `QTemporaryFile createLocalFile (QFile file)`

* * *

## Detailed Description

该QTemporaryFile类是一个操作上的临时文件的I / O设备。

QTemporaryFile是用来安全地创建唯一的临时文件。文件本身是通过调用创建[open](qtemporaryfile.html#open)（ ） 。临时文件的名称是保证是唯一的（即，你保证不会复盖现有文件） ，文件随后将在销毁QTemporaryFile对象的删除。这是一种避免数据损坏的存储在临时文件数据应用的重要技术。文件名可以是自动生成的，或基于模板，这是传递给QTemporaryFile的构造函数创建的。

例如：

```
     // Within a function/method...

     QTemporaryFile file;
     if (file.open()) {
         // file.fileName() returns the unique file name
     }

     // The QTemporaryFile destructor removes the temporary file
     // as it goes out of scope.

```

调用后重新打开QTemporaryFile[close](qfile.html#close)（）是安全的。为只要QTemporaryFile对象本身不被破坏，该唯一的临时文件将存在和保持开放内部由QTemporaryFile 。

临时文件的文件名可以通过调用被发现[fileName](qtemporaryfile.html#fileName)（ ） 。请注意，这仅仅是定义在第一次打开该文件后，在此之前，函数返回一个空字符串。

临时文件将有名称的一些静态的一部分，计算为独特的某一部分。默认文件名`qt_temp`将被放置到临时路径所返回[QDir.tempPath](qdir.html#tempPath)（ ） 。如果你指定你自己的文件名，相对文件路径将不会被放置在临时目录默认，但相对于当前的工作目录。

指定的文件名可以包含以下模板`XXXXXX`（ 6大写的“X”字符） ，将通过文件名的自动生成的部分被替换。注意，模板是区分大小写的。如果模板中不存在的文件名， QTemporaryFile生成的一部分追加到给定的文件名。

* * *

## Method Documentation

```
QTemporaryFile.__init__ (self)
```

构造一个[QTemporaryFile](qtemporaryfile.html)在[QDir.tempPath](qdir.html#tempPath)（ ） ，使用文件模板“ qt_temp.XXXXXX ” 。该文件存储在系统的临时目录。

**See also** [setFileTemplate](qtemporaryfile.html#setFileTemplate)（）和[QDir.tempPath](qdir.html#tempPath)（ ） 。

```
QTemporaryFile.__init__ (self, QString templateName)
```

构造一个[QTemporaryFile](qtemporaryfile.html)用的模板的文件名_templateName_。一旦打开临时文件，这将被用来创建一个唯一的文件名。

如果_templateName_不包含XXXXXX，它会自动被追加并作为文件名的动态部分。

If _templateName_是一个相对路径，该路径将是相对于当前工作目录。您可以使用[QDir.tempPath](qdir.html#tempPath)（ ）构造_templateName_如果你想使用系统的临时目录。

**See also** [open](qtemporaryfile.html#open)（）和[fileTemplate](qtemporaryfile.html#fileTemplate)（ ） 。

```
QTemporaryFile.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QTemporaryFile](qtemporaryfile.html)（用给定的_parent_）在[QDir.tempPath](qdir.html#tempPath)（ ） ，使用文件模板“ qt_temp.XXXXXX ” 。

**See also** [setFileTemplate](qtemporaryfile.html#setFileTemplate)（ ） 。

```
QTemporaryFile.__init__ (self, QString templateName, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QTemporaryFile](qtemporaryfile.html)用的模板的文件名_templateName_和指定的_parent_。一旦打开临时文件，这将被用来创建一个唯一的文件名。

如果_templateName_不包含XXXXXX，它会自动被追加并作为文件名的动态部分。

If _templateName_是一个相对路径，该路径将是相对于当前工作目录。您可以使用[QDir.tempPath](qdir.html#tempPath)（ ）构造_templateName_如果你想使用系统的临时目录。

**See also** [open](qtemporaryfile.html#open)（）和[fileTemplate](qtemporaryfile.html#fileTemplate)（ ） 。

```
bool QTemporaryFile.autoRemove (self)
```

返回True如果[QTemporaryFile](qtemporaryfile.html)处于自动删除模式。自动删除模式会自动从磁盘损坏后删除的文件名。这使得它非常容易地创建您的[QTemporaryFile](qtemporaryfile.html)在堆栈中的对象，用数据填充它，从中读取，终于在函数返回后会自己自动清理。

自动删除默认为开启。

**See also** [setAutoRemove](qtemporaryfile.html#setAutoRemove)（）和[remove](qfile.html#remove)（ ） 。

```
QTemporaryFile QTemporaryFile.createLocalFile (QString fileName)
```

[

If _file_是不是在本地磁盘上，一个临时文件在本地磁盘上创建的，_file_复制到本地临时文件，和一个指向临时本地文件返回。如果_file_已经在本地磁盘上，一个副本则不会创建并返回0 。

](qtemporaryfile.html)

```
QTemporaryFile QTemporaryFile.createLocalFile (QFile file)
```

[

这是一个重载函数。

](qtemporaryfile.html)

[工程对给定的_fileName_而不是现有的](qtemporaryfile.html)[QFile](qfile.html)对象。

```
QAbstractFileEngine QTemporaryFile.fileEngine (self)
```

[

```
QString QTemporaryFile.fileName (self)
```

](qabstractfileengine.html)

[返回完整的唯一文件名的支持](qabstractfileengine.html)[QTemporaryFile](qtemporaryfile.html)对象。这个字符串是前空[QTemporaryFile](qtemporaryfile.html)被打开，之后它将包含[fileTemplate](qtemporaryfile.html#fileTemplate)（ ）加上额外的字符以使其唯一。

**See also** [fileTemplate](qtemporaryfile.html#fileTemplate)（ ） 。

```
QString QTemporaryFile.fileTemplate (self)
```

返回集合文件模板。默认的文件模板将被称为qt_temp并放置在[QDir.tempPath](qdir.html#tempPath)（ ） 。

**See also** [setFileTemplate](qtemporaryfile.html#setFileTemplate)（ ） 。

```
bool QTemporaryFile.open (self)
```

A [QTemporaryFile](qtemporaryfile.html)将始终打开[QIODevice.ReadWrite](qiodevice.html#OpenModeFlag-enum)模式，这可以方便地访问文件中的数据。这个函数将返回成功后，真实，且设置[fileName](qtemporaryfile.html#fileName)（ ）所使用的唯一的文件名。

**See also** [fileName](qtemporaryfile.html#fileName)（ ） 。

```
bool QTemporaryFile.open (self, QIODevice.OpenMode flags)
```

从重新实现[QIODevice.open](qiodevice.html#open)（ ） 。

创建临时文件一个唯一的文件名，并打开它。你可以通过调用后得到的唯一的名称[fileName](qtemporaryfile.html#fileName)（ ） 。该文件是保证已经建立了这个功能（即，它以前从未存在） 。

```
QTemporaryFile.setAutoRemove (self, bool b)
```

设置[QTemporaryFile](qtemporaryfile.html)进入自动删除模式下，如果_b_是真实的。

自动删除默认为开启。

**See also** [autoRemove](qtemporaryfile.html#autoRemove)（）和[remove](qfile.html#remove)（ ） 。

```
QTemporaryFile.setFileTemplate (self, QString name)
```

设置文件名的静态部分，以_name_。如果文件模板中XXXXXX将被自动替换为文件名的独特之处，否则结束的文件名会自动根据指定的静态部分来确定。

If _name_包含相对文件路径，该路径将是相对于当前工作目录。您可以使用[QDir.tempPath](qdir.html#tempPath)（ ）构造_name_如果你想使用系统的临时目录。

**See also** [fileTemplate](qtemporaryfile.html#fileTemplate)（ ） 。