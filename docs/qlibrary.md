# QLibrary Class Reference

## [[QtCore](index.htm) module]

该QLibrary类加载共享库在运行时。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum LoadHint { ResolveAllSymbolsHint, ExportExternalSymbolsHint, LoadArchiveMemberHint }`
*   `class **[LoadHints](index.htm)**`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QString fileName, QObject parent = None)`
*   `__init__ (self, QString fileName, int verNum, QObject parent = None)`
*   `__init__ (self, QString fileName, QString version, QObject parent = None)`
*   `QString errorString (self)`
*   `QString fileName (self)`
*   `bool isLoaded (self)`
*   `bool load (self)`
*   `LoadHints loadHints (self)`
*   `sip.voidptr resolve (self, str symbol)`
*   `setFileName (self, QString fileName)`
*   `setFileNameAndVersion (self, QString fileName, int verNum)`
*   `setFileNameAndVersion (self, QString fileName, QString version)`
*   `setLoadHints (self, LoadHints hints)`
*   `bool unload (self)`

### Static Methods

*   `bool isLibrary (QString fileName)`
*   `sip.voidptr resolve (QString fileName, str symbol)`
*   `sip.voidptr resolve (QString fileName, int verNum, str symbol)`
*   `sip.voidptr resolve (QString fileName, QString version, str symbol)`

* * *

## Detailed Description

该QLibrary类加载共享库在运行时。

一个QLibrary对象的一个实例在一个单一的共享对象文件操作（我们称之为“库” ，但也被称为一个“ DLL” ） 。一个QLibrary提供了一个平台无关的方式访问存储库中的功能。你可以传递一个文件名在构造函数中，或显式设置[setFileName](qlibrary.html#fileName-prop)（ ） 。当加载库时， QLibrary中的所有系统特定的库位置搜索（例如：`LD_LIBRARY_PATH`在Unix上） ，除非文件名有一个绝对路径。如果文件无法找到， QLibrary试着修改名字用不同平台特定的文件后缀，如“ 。所以”在Unix上， “ dylib的”在Mac上，或在Windows和Symbian 。“ DLL” 。这使得它可以指定只能由他们的基本名（即没有自己的后缀）标识的共享库，所以同样的代码将工作在不同的操作系统。

最重要的功能是[load](qlibrary.html#load)（ ）动态加载的库文件，[isLoaded](qlibrary.html#isLoaded)（）来检查装载是否成功，并[resolve](qlibrary.html#resolve)（ ）来解决在库中的元件。该[resolve](qlibrary.html#resolve)（ ）函数隐式地试图加载库，如果它没有被加载。 QLibrary的多个实例可以用来访问同一个物理磁带库。一旦加载，图书馆保留在内存中，直到应用程序终止。您可以尝试使用卸载库[unload](qlibrary.html#unload)（ ） ，但如果其他的实例都使用相同的库，则调用将失败，并卸载当每一个实例都调用才会发生[unload](qlibrary.html#unload)（ ） 。

一个典型的应用QLibrary是解决一个库导出的符号，来调用C函数这个符号表示。这就是所谓的相对于“隐式链接” ，这是由在构建过程中的链接步骤对链接库中的可执行文件时进行“显式链接” 。

注：在Symbian解决使用他们的名字符号仅支持如果库被构建为STDDLL 。否则序必须被使用。另外，在塞班库的路径被忽略，系统默认的库位置始终使用。

下面的代码片段加载一个库，解决了符号“ mysymbol ” ，并调用该函数，如果一切成功。如果出现问题，例如库文件不存在或者符号没有定义，函数指针将是0 ，不会被调用。

```
 QLibrary myLib("mylib");
 typedef void (*MyPrototype)();
 MyPrototype myFunction = (MyPrototype) myLib.resolve("mysymbol");
 if (myFunction)
     myFunction();

```

该符号必须导出为一个C函数的库[resolve](qlibrary.html#resolve)（ ）工作。这意味着函数必须被包裹在一个`extern "C"`如果阻塞的库编译一个C + +编译器。在Windows上，这也需要使用一个`dllexport`宏;见[resolve](qlibrary.html#resolve)（ ）对于如何做到这一点的细节。为方便起见，有一个静态的[resolve](qlibrary.html#resolve)（ ）函数，你可以使用，如果你只是想调用的库函数而不明确的加载库：

```
 typedef void (*MyPrototype)();
 MyPrototype myFunction =
         (MyPrototype) QLibrary.resolve("mylib", "mysymbol");
 if (myFunction)
     myFunction();

```

* * *

## Type Documentation

```
QLibrary.LoadHint
```

该枚举描述了可被用来改变库被加载时的处理方式的可能的提示。这些值表示当加载库如何符号解析，并使用指定的[setLoadHints](qlibrary.html#loadHints-prop)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QLibrary.ResolveAllSymbolsHint` | `0x01` | 原因在一个库中的所有符号加载时得到解决，而不是简单地当[resolve](qlibrary.html#resolve)（）被调用。 |
| `QLibrary.ExportExternalSymbolsHint` | `0x02` | 出口未解决的外部符号库中，使他们能够在其他以后加载动态加载的库来解决。 |
| `QLibrary.LoadArchiveMemberHint` | `0x04` | 允许内的存档文件中指定一个特定的目标文件库的文件名。如果这个提示，给出库的文件名包含一个路径，这是一个参考的存档文件，其次是参照归档成员。 |

该LoadHints类型是一个typedef为[QFlags](index.htm)\u003cLoadHint\u003e 。它存储载入提示值的或组合。

**See also** [loadHints](qlibrary.html#loadHints-prop)。

* * *

## Method Documentation

```
QLibrary.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个库与给定_parent_。

```
QLibrary.__init__ (self, QString fileName, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个库对象与给定_parent_可以加载指定的库_fileName_。

我们建议省略了文件的后缀_fileName_，因为[QLibrary](qlibrary.html)会自动寻找与相应的后缀的文件按照平台，如在Windows “ 。所以”在Unix上， “ 。 dylib的”在Mac OS X ，和“ DLL” 。 （见[fileName](qlibrary.html#fileName-prop)。 ）

注：在Symbian的路径部分_fileName_被忽略。

```
QLibrary.__init__ (self, QString fileName, int verNum, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个库对象与给定_parent_可以加载指定的库_fileName_和主版本号_verNum_。目前，版本号会被忽略在Windows和Symbian 。

我们建议省略了文件的后缀_fileName_，因为[QLibrary](qlibrary.html)会自动寻找与相应的后缀的文件按照平台，如在Windows “ 。所以”在Unix上， “ 。 dylib的”在Mac OS X ，和“ DLL” 。 （见[fileName](qlibrary.html#fileName-prop)。 ）

注：在Symbian的路径部分_fileName_被忽略。

```
QLibrary.__init__ (self, QString fileName, QString version, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个库对象与给定_parent_可以加载指定的库_fileName_和完整的版本号_version_。目前，版本号会被忽略在Windows和Symbian 。

我们建议省略了文件的后缀_fileName_，因为[QLibrary](qlibrary.html)会自动寻找与相应的后缀的文件按照平台，如在Windows “ 。所以”在Unix上， “ 。 dylib的”在Mac OS X ，和“ DLL” 。 （见[fileName](qlibrary.html#fileName-prop)。 ）

注：在Symbian的路径部分_fileName_被忽略。

```
QString QLibrary.errorString (self)
```

返回与上次发生错误的描述文本字符串。目前， errorString只会被设置，如果[load](qlibrary.html#load)（ ）[unload](qlibrary.html#unload)（）或[resolve](qlibrary.html#resolve)（ ）由于某种原因失败。

这个函数中引入了Qt 4.2中。

```
QString QLibrary.fileName (self)
```

```
bool QLibrary.isLibrary (QString fileName)
```

返回True如果_fileName_有一个可加载的库的有效后缀，否则返回False 。

| Platform | Valid suffixes |
| --- | --- |
| Windows | `.dll`, `.DLL` |
| Unix/Linux | `.so` |
| AIX | `.a` |
| HP-UX | `.sl`, `.so` (HP-UXi) |
| Mac OS X | `.dylib`, `.bundle`, `.so` |
| Symbian | `.dll` |

在Unix尾随版本号将被忽略。

```
bool QLibrary.isLoaded (self)
```

返回True如果库被加载，否则返回False 。

**See also** [load](qlibrary.html#load)（ ） 。

```
bool QLibrary.load (self)
```

加载库，如果已成功加载的库返回True，否则返回False 。自[resolve](qlibrary.html#resolve)（ ）解决，没有必要显式调用它的任何符号前总是调用这个函数。在某些情况下，您可能想预先加载的库，你会在这种情况下使用此功能。

**See also** [unload](qlibrary.html#unload)（ ） 。

```
LoadHints QLibrary.loadHints (self)
```

[

```
sip.voidptr QLibrary.resolve (self, str symbol)
```

返回导出符号的地址_symbol_。如有必要，该库被加载。该函数返回0，如果符号无法解析，或者无法加载库。

例如：

```
 typedef int (*AvgFunction)(int, int);

 AvgFunction avg = (AvgFunction) library->resolve("avg");
 if (avg)
     return avg(5, 8);
 else
     return -1;

```

该符号必须导出为从库中的C函数。这意味着函数必须被包裹在一个`extern "C"`如果库是编译一个C + +编译器。在Windows上，还必须明确地从使用的DLL导出函数`__declspec(dllexport)`编译器指令，例如：

```
 extern "C" MY_EXPORT int avg(int a, int b)
 {
     return (a + b) / 2;
 }

```

同`MY_EXPORT`定义为

```
 #ifdef Q_WS_WIN
 #define MY_EXPORT __declspec(dllexport)
 #else
 #define MY_EXPORT
 #endif

```

注：在Symbian解决与符号名只有当加载的库是作为STDDLL 。否则，该序数必须被使用。

```
sip.voidptr QLibrary.resolve (QString fileName, str symbol)
```

这是一个重载函数。

](index.htm)

[加载库_fileName_并返回导出符号的地址_symbol_。需要注意的是_fileName_不应该包括特定于平台的文件后缀（见](index.htm)[fileName](qlibrary.html#fileName-prop)） 。该库仍然加载，直到应用程序退出。

该函数返回0，如果符号无法解析，或者无法加载库。

注：在Symbian解决与符号名只有当加载的库是作为STDDLL 。否则，该序数必须被使用。

**See also** [resolve](qlibrary.html#resolve)（ ） 。

```
sip.voidptr QLibrary.resolve (QString fileName, int verNum, str symbol)
```

这是一个重载函数。

加载库_fileName_与主版本号_verNum_并返回导出符号的地址_symbol_。需要注意的是_fileName_不应该包括特定于平台的文件后缀（见[fileName](qlibrary.html#fileName-prop)） 。该库仍然加载，直到应用程序退出。_verNum_被忽略的Windows 。

该函数返回0，如果符号无法解析，或者无法加载库。

注：在Symbian解决与符号名只有当加载的库是作为STDDLL 。否则，该序数必须被使用。

**See also** [resolve](qlibrary.html#resolve)（ ） 。

```
sip.voidptr QLibrary.resolve (QString fileName, QString version, str symbol)
```

这是一个重载函数。

加载库_fileName_有完整的版本号_version_并返回导出符号的地址_symbol_。需要注意的是_fileName_不应该包括特定于平台的文件后缀（见[fileName](qlibrary.html#fileName-prop)） 。该库仍然加载，直到应用程序退出。_version_被忽略的Windows 。

该函数返回0，如果符号无法解析，或者无法加载库。

注：在Symbian解决与符号名只有当加载的库是作为STDDLL 。否则，该序数必须被使用。

此功能被引入Qt的4.4 。

**See also** [resolve](qlibrary.html#resolve)（ ） 。

```
QLibrary.setFileName (self, QString fileName)
```

```
QLibrary.setFileNameAndVersion (self, QString fileName, int verNum)
```

设置[fileName](qlibrary.html#fileName-prop)财产和主版本号_fileName_和_versionNumber_分别。该_versionNumber_被忽略的Windows和Symbian 。

注：在Symbian的路径部分_fileName_被忽略。

**See also** [setFileName](qlibrary.html#fileName-prop)（ ） 。

```
QLibrary.setFileNameAndVersion (self, QString fileName, QString version)
```

设置[fileName](qlibrary.html#fileName-prop)财产和完整版本号为_fileName_和_version_分别。该_version_参数被忽略在Windows和Symbian 。

注：在Symbian的路径部分_fileName_被忽略。

此功能被引入Qt的4.4 。

**See also** [setFileName](qlibrary.html#fileName-prop)（ ） 。

```
QLibrary.setLoadHints (self, LoadHints hints)
```

```
bool QLibrary.unload (self)
```

卸载库，如果库可以卸载返回True，否则返回False 。

出现这种情况自动终止应用程序，所以你通常不应需要调用这个函数。

如果其它实例[QLibrary](qlibrary.html)使用相同的库，则调用将失败，并卸载只会发生在每一个实例都调用unload （ ） 。

请注意，在Mac OS X 10.3 （ Panther）的，动态库不能被卸载。

**See also** [resolve](qlibrary.html#resolve)（）和[load](qlibrary.html#load)（ ） 。