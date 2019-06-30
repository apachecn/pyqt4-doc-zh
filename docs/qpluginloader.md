# QPluginLoader Class Reference

## [[QtCore](index.htm) module]

该QPluginLoader类加载插件在运行时。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QString fileName, QObject parent = None)`
*   `QString errorString (self)`
*   `QString fileName (self)`
*   `QObject instance (self)`
*   `bool isLoaded (self)`
*   `bool load (self)`
*   `QLibrary.LoadHints loadHints (self)`
*   `setFileName (self, QString fileName)`
*   `setLoadHints (self, QLibrary.LoadHints loadHints)`
*   `bool unload (self)`

### Static Methods

*   `list-of-QObject staticInstances ()`

* * *

## Detailed Description

该QPluginLoader类加载插件在运行时。

QPluginLoader提供了访问[Qt plugin](index.htm)。一个Qt的插件存储在一个共享库（一个DLL ），并在共享库提供这些好处利用访问[QLibrary](qlibrary.html)：

*   QPluginLoader checks that a plugin is linked against the same version of Qt as the application.
*   QPluginLoader provides direct access to a root component object ([instance](qpluginloader.html#instance)()), instead of forcing you to resolve a C function manually.

一个QPluginLoader对象的一个实例运行在一个单一的共享库文件，我们称之为一个插件。它提供了一个与平台无关的方式获得在插件的功能。要指定哪些插件加载，无论是在构造函数中传递一个文件名或将其设置[setFileName](qpluginloader.html#fileName-prop)（ ） 。

最重要的功能是[load](qpluginloader.html#load)（ ）动态加载的插件文件，[isLoaded](qpluginloader.html#isLoaded)（）来检查装载是否成功，并[instance](qpluginloader.html#instance)（ ）来访问插件的根组件。该[instance](qpluginloader.html#instance)（ ）函数隐式地尝试加载该插件，如果它没有被加载。 QPluginLoader的多个实例可以被用于访问同一物理插件。

一旦加载，插件保留在内存中，直到QPluginLoader的所有实例已被卸载，或直到应用程序终止。你可以尝试使用卸载插件[unload](qpluginloader.html#unload)（ ） ，但如果QPluginLoader的其他实例都使用相同的库，则调用将失败，并卸载当每一个实例都调用才会发生[unload](qpluginloader.html#unload)（ ） 。权利之前卸载发生，根组件也将被删除。

为了加快加载和插件验证，某些被装载过程中收集的信息被缓存在持久性存储器（通过[QSettings](qsettings.html)） 。举例来说，一个负荷运算的结果（例如，成功或失败）被存储在高速缓存中，这样，后续的加载操作不尝试加载一个无效的插件。但是，如果一个插件的“最后修改”时间戳已经改变，该插件的缓存项失效，并不管值的插件重新加载缓存中的条目。缓存条目，然后更新了负载运行的新的结果。

这也意味着，时间戳必须在插件或任何依赖资源（如共享库）被更新，每次更新，因为依赖的资源可能会影响加载插件的结果。

See [How to Create Qt Plugins](index.htm)关于如何通过插件使你的应用程序扩展的信息。

请注意， QPluginLoader不能使用，如果你的应用程序是针对Qt的静态链接。在这种情况下，你也将有静态链接到插件。您可以使用[QLibrary](qlibrary.html)如果你需要在一个静态链接的应用程序加载动态库。

**Note:**在Symbian插件存根文件，必须使用时的路径插件是必要的。对于加载的插件的目的，存根可被认为具有相同的名称作为实际插件二进制文件。在实践中，他们有“ 。 QTPLUGIN ”扩展名，而不是“ DLL” ，但这种差异是由QPluginLoader透明处理和[QLibrary](qlibrary.html)避免需要特殊的Symbian处理插件，在大多数Qt应用程序。需要插件的存根，因为Symbian平台安全性拒绝所有访问在实际的插件二进制文件所在的目录。

* * *

## Method Documentation

```
QPluginLoader.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个插件加载给定的_parent_。

```
QPluginLoader.__init__ (self, QString fileName, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个插件加载给定的_parent_可以加载指定的插件_fileName_。

要加载，文件的后缀必须是一个可加载的库的有效后缀按照平台，如`.so`在Unix上， - `.dylib`在Mac OS X ，和`.dll`在Windows上。后缀可以与验证[QLibrary.isLibrary](qlibrary.html#isLibrary)（ ） 。

注：在Symbian的_fileName_必须指向插件存根文件。

**See also** [setFileName](qpluginloader.html#fileName-prop)（ ） 。

```
QString QPluginLoader.errorString (self)
```

返回与上次发生错误的描述文本字符串。

这个函数中引入了Qt 4.2中。

```
QString QPluginLoader.fileName (self)
```

```
QObject QPluginLoader.instance (self)
```

[

返回插件的根组件对象。如有必要，该插件被加载。该函数返回0，如果插件无法加载或如果根组件对象不能被实例化。

如果根组件对象被销毁，调用这个函数创建一个新的实例。

](qobject.html)

[根组件，该函数的返回，不会被删除时，](qobject.html)[QPluginLoader](qpluginloader.html)被破坏。如果你想确保根组件被删除，你应该调用[unload](qpluginloader.html#unload)（ ）只要您不必再访问核心组件。当库最后卸载，根组件将被自动删除。

该组件对象是[QObject](qobject.html)。使用[qobject_cast](qobject.html#qobject_cast)（ ）来访问您感兴趣的接口

**See also** [load](qpluginloader.html#load)（ ） 。

```
bool QPluginLoader.isLoaded (self)
```

返回True如果该插件被加载，否则返回False 。

**See also** [load](qpluginloader.html#load)（ ） 。

```
bool QPluginLoader.load (self)
```

加载插件，如果已成功加载的插件返回True，否则返回False 。自[instance](qpluginloader.html#instance)（ ）解决，没有必要显式调用它的任何符号前总是调用这个函数。在某些情况下，您可能想预先加载的插件，你会在这种情况下使用此功能。

**See also** [unload](qpluginloader.html#unload)（ ） 。

```
QLibrary.LoadHints QPluginLoader.loadHints (self)
```

[

```
QPluginLoader.setFileName (self, QString fileName)
```

```
QPluginLoader.setLoadHints (self, QLibrary.LoadHints loadHints)
```

```
list-of-QObject QPluginLoader.staticInstances ()
```

返回静态插件实例（根组件）本插件加载持有的一份名单。

```
bool QPluginLoader.unload (self)
```

卸载插件，如果插件可以卸载返回True，否则返回False 。

出现这种情况自动终止应用程序，所以你通常不应需要调用这个函数。

](index.htm)

[如果其它实例](index.htm)[QPluginLoader](qpluginloader.html)使用相同的插件，则调用将失败，并卸载只会发生在每一个实例都调用unload （ ） 。

不要试图删除根组件。而不是依赖于卸载（ ）在需要时会自动将其删除。

**See also** [instance](qpluginloader.html#instance)（）和[load](qpluginloader.html#load)（ ） 。