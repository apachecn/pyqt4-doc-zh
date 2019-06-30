# QDeclarativeEngine Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeEngine类提供了实例QML组件的环境。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum ObjectOwnership { CppOwnership, JavaScriptOwnership }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `addImageProvider (self, QString id, QDeclarativeImageProvider)`
*   `addImportPath (self, QString dir)`
*   `addPluginPath (self, QString dir)`
*   `QUrl baseUrl (self)`
*   `clearComponentCache (self)`
*   `QDeclarativeImageProvider imageProvider (self, QString id)`
*   `QStringList importPathList (self)`
*   `(bool, QString errorString) importPlugin (self, QString filePath, QString uri)`
*   `QNetworkAccessManager networkAccessManager (self)`
*   `QDeclarativeNetworkAccessManagerFactory networkAccessManagerFactory (self)`
*   `QString offlineStoragePath (self)`
*   `bool outputWarningsToStandardError (self)`
*   `QStringList pluginPathList (self)`
*   `removeImageProvider (self, QString id)`
*   `QDeclarativeContext rootContext (self)`
*   `setBaseUrl (self, QUrl)`
*   `setImportPathList (self, QStringList paths)`
*   `setNetworkAccessManagerFactory (self, QDeclarativeNetworkAccessManagerFactory)`
*   `setOfflineStoragePath (self, QString dir)`
*   `setOutputWarningsToStandardError (self, bool)`
*   `setPluginPathList (self, QStringList paths)`

### Static Methods

*   `QDeclarativeContext contextForObject (QObject)`
*   `ObjectOwnership objectOwnership (QObject)`
*   `setContextForObject (QObject, QDeclarativeContext)`
*   `setObjectOwnership (QObject, ObjectOwnership)`

### Qt Signals

*   `void quit ()`
*   `void warnings (const QList&lt;QDeclarativeError&gt;&)`

* * *

## Detailed Description

该QDeclarativeEngine类提供了实例QML组件的环境。

每个QML组件实例化的[QDeclarativeContext](qdeclarativecontext.html)。[QDeclarativeContext](qdeclarativecontext.html)的是将数据传递到QML组件是必不可少的。在QML中，上下文是分级排列并且这个层次是由QDeclarativeEngine管理。

在此之前创建的任何QML组件，应用程序必须创建一个QDeclarativeEngine来访问一个QML上下文。下面的示例显示了如何创建一个简单的文本项。

```
 QDeclarativeEngine engine;
 [QDeclarativeComponent](qdeclarativecomponent.html) component(&engine);
 component.setData("import QtQuick 1.0\nText { text: \"Hello world!\" }", [QUrl](qurl.html)());
 [QDeclarativeItem](qdeclarativeitem.html) *item = qobject_cast<[QDeclarativeItem](qdeclarativeitem.html) *>(component.create());

 //add item to view, etc
 ...

```

在这种情况下，文本项目将在发动机的创建[root context](qdeclarativeengine.html#rootContext)。

* * *

## Type Documentation

```
QDeclarativeEngine.ObjectOwnership
```

所有权控制QML是否自动销毁[QObject](qobject.html)当对象被垃圾由JavaScript引擎收集。这两种所有制的选项有：

| Constant | Value | Description |
| --- | --- | --- |
| `QDeclarativeEngine.CppOwnership` | `0` | 对象是由C + +代码拥有，永远不会被QML被删除。 JavaScript的destroy（）方法不能与CppOwnership对象使用。此选项类似于[QScriptEngine.QtOwnership](qscriptengine.html#ValueOwnership-enum)。 |
| `QDeclarativeEngine.JavaScriptOwnership` | `1` | 该目的是通过JavaScript的拥有。当对象被返回到QML作为一个方法调用或属性访问的返回值， QML会删除该对象，如果有它没有剩馀的JavaScript引用和它有没有[QObject.parent](qobject.html#parent)（ ） 。此选项类似于[QScriptEngine.ScriptOwnership](qscriptengine.html#ValueOwnership-enum)。 |

一般的应用程序并不需要显式设置对象的所有权。 QML使用启发式设置默认对象所有权。默认情况下，是通过QML创建一个对象有JavaScriptOwnership 。唯一的例外是通过调用QDeclarativeCompnent.create （创建的根对象）或[QDeclarativeComponent.beginCreate](qdeclarativecomponent.html#beginCreate)（），它在默认情况下已经CppOwnership 。这些根级对象的所有权被视为已转移到C + +调用者。

通过QML不能创建对象具有CppOwnership默认。唯一的例外是一个C + +方法调用返回的对象。这些对象的所有权被传递给JavaScript 。

调用[setObjectOwnership](qdeclarativeengine.html#setObjectOwnership)（ ）复盖使用QML默认所有权启发式。

* * *

## Method Documentation

```
QDeclarativeEngine.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的[QDeclarativeEngine](qdeclarativeengine.html)用给定的_parent_。

```
QDeclarativeEngine.addImageProvider (self, QString id, QDeclarativeImageProvider)
```

设置_provider_用于经由所请求的图像_image_： URL方案，与主机_providerId_。该[QDeclarativeEngine](qdeclarativeengine.html)采取所有权_provider_。

图片提供者能为像素图和螺纹图像请求支持。请参阅[QDeclarativeImageProvider](qdeclarativeimageprovider.html)文件中有关实施和使用图像提供商的详细信息。

所有所需的图像提供商应该被添加到发动机的任何QML源之前文件被加载。

**See also** [removeImageProvider](qdeclarativeengine.html#removeImageProvider)（ ） 。

```
QDeclarativeEngine.addImportPath (self, QString dir)
```

添加_path_因为那里的搜索引擎在一个基于URL的目录结构安装的模块目录。该_path_可以是本地文件系统的目录或URL。

新添加的_path_将首先在[importPathList](qdeclarativeengine.html#importPathList)（ ） 。

**See also** [setImportPathList](qdeclarativeengine.html#setImportPathList)（）和[QML Modules](index.htm#qml-modules)。

```
QDeclarativeEngine.addPluginPath (self, QString dir)
```

添加_path_因为此时发动机搜索的导入模块本地插件（在引用的目录`qmldir`文件） 。

默认情况下，列表中只包含`.`即在该目录中的引擎的搜索`qmldir`文件本身。

新添加的_path_将首先在[pluginPathList](qdeclarativeengine.html#pluginPathList)（ ） 。

**See also** [setPluginPathList](qdeclarativeengine.html#setPluginPathList)（ ） 。

```
QUrl QDeclarativeEngine.baseUrl (self)
```

[](qurl.html)

[返回的基础URL为这个引擎。基本URL仅用于解决组件时的相对URL被传递给](qurl.html)[QDeclarativeComponent](qdeclarativecomponent.html)构造函数。

如果基URL尚未显式设置，则此方法返回应用程序的当前工作目录。

**See also** [setBaseUrl](qdeclarativeengine.html#setBaseUrl)（ ） 。

```
QDeclarativeEngine.clearComponentCache (self)
```

清除发动机的内部部件缓存。

通常情况下，[QDeclarativeEngine](qdeclarativeengine.html)缓存从QML文件中加载的组件。这种方法清除该缓存，并强制组件重新加载。

```
QDeclarativeContext QDeclarativeEngine.contextForObject (QObject)
```

[](qdeclarativecontext.html)

[返回](qdeclarativecontext.html)[QDeclarativeContext](qdeclarativecontext.html)为_object_，或者0，如果没有上下文已定。

当[QDeclarativeEngine](qdeclarativeengine.html)实例化一个[QObject](qobject.html)时，上下文被自动设置。

**See also** [setContextForObject](qdeclarativeengine.html#setContextForObject)（ ） 。

```
QDeclarativeImageProvider QDeclarativeEngine.imageProvider (self, QString id)
```

[](qdeclarativeimageprovider.html)

[返回](qdeclarativeimageprovider.html)[QDeclarativeImageProvider](qdeclarativeimageprovider.html)对于设置_providerId_。

```
QStringList QDeclarativeEngine.importPathList (self)
```

返回将搜索引擎在一个基于URL的目录结构安装的模块的目录列表。

例如，如果`/opt/MyApp/lib/imports`在路径中，然后QML的进口`com.mycompany.Feature`会导致[QDeclarativeEngine](qdeclarativeengine.html)看在`/opt/MyApp/lib/imports/com/mycompany/Feature/`对于由该模块提供的组件。一`qmldir`文件是必需的，用于定义类型映射版本，并可能宣告扩展插件。

默认情况下，该列表包含应用程序的可执行文件的目录，在指定路径`QML_IMPORT_PATH`环境变量，以及内置的`ImportsPath`从[QLibraryInfo](qlibraryinfo.html)。

**See also** [addImportPath](qdeclarativeengine.html#addImportPath)（）和[setImportPathList](qdeclarativeengine.html#setImportPathList)（ ） 。

```
(bool, QString errorString) QDeclarativeEngine.importPlugin (self, QString filePath, QString uri)
```

进口评为插件_filePath_与_uri_提供。返回True如果插件被成功导入，否则返回False 。

如果失败，如果非空， *_errorString_将被设置为描述失败的消息。

该插件必须是Qt的插件，它实现了[QDeclarativeExtensionPlugin](qdeclarativeextensionplugin.html)接口。

```
QNetworkAccessManager QDeclarativeEngine.networkAccessManager (self)
```

[](qnetworkaccessmanager.html)

[返回一个共同的](qnetworkaccessmanager.html)[QNetworkAccessManager](qnetworkaccessmanager.html)它可以用来由本机实例化的任何QML元素。

如果[QDeclarativeNetworkAccessManagerFactory](qdeclarativenetworkaccessmanagerfactory.html)已被设置和一[QNetworkAccessManager](qnetworkaccessmanager.html)尚未建立，则[QDeclarativeNetworkAccessManagerFactory](qdeclarativenetworkaccessmanagerfactory.html)将被用来创建[QNetworkAccessManager](qnetworkaccessmanager.html)否则返回[QNetworkAccessManager](qnetworkaccessmanager.html)不会有任何代理或缓存设置。

**See also** [setNetworkAccessManagerFactory](qdeclarativeengine.html#setNetworkAccessManagerFactory)（ ） 。

```
QDeclarativeNetworkAccessManagerFactory QDeclarativeEngine.networkAccessManagerFactory (self)
```

[](qdeclarativenetworkaccessmanagerfactory.html)

[返回当前](qdeclarativenetworkaccessmanagerfactory.html)[QDeclarativeNetworkAccessManagerFactory](qdeclarativenetworkaccessmanagerfactory.html)。

**See also** [setNetworkAccessManagerFactory](qdeclarativeengine.html#setNetworkAccessManagerFactory)（ ） 。

```
ObjectOwnership QDeclarativeEngine.objectOwnership (QObject)
```

[

返回的所有权_object_。

](qdeclarativeengine.html#ObjectOwnership-enum)

[**See also**](qdeclarativeengine.html#ObjectOwnership-enum) [setObjectOwnership](qdeclarativeengine.html#setObjectOwnership)（ ） 。

```
QString QDeclarativeEngine.offlineStoragePath (self)
```

```
bool QDeclarativeEngine.outputWarningsToStandardError (self)
```

返回True如果警告信息将被输出到stderr除了由正在发射[warnings](qdeclarativeengine.html#warnings)（ ）信号，否则为False 。

默认值是True 。

**See also** [setOutputWarningsToStandardError](qdeclarativeengine.html#setOutputWarningsToStandardError)（ ） 。

```
QStringList QDeclarativeEngine.pluginPathList (self)
```

返回目录所在的搜索引擎为进口原生模块插件（在引用的列表`qmldir`文件） 。

默认情况下，列表中只包含`.`即在该目录中的引擎的搜索`qmldir`文件本身。

**See also** [addPluginPath](qdeclarativeengine.html#addPluginPath)（）和[setPluginPathList](qdeclarativeengine.html#setPluginPathList)（ ） 。

```
QDeclarativeEngine.removeImageProvider (self, QString id)
```

移除[QDeclarativeImageProvider](qdeclarativeimageprovider.html)为_providerId_。

返回，如果它被发现的提供者，否则返回0 。

**See also** [addImageProvider](qdeclarativeengine.html#addImageProvider)（ ） 。

```
QDeclarativeContext QDeclarativeEngine.rootContext (self)
```

[

返回引擎的根上下文。

](qdeclarativecontext.html)

[根上下文是由自动创建](qdeclarativecontext.html)[QDeclarativeEngine](qdeclarativeengine.html)。数据应提供给由发动机实例化所有的QML组件实例应该放在根上下文。

额外的数据应该只提供给组件实例的一个子集应该被添加到子上下文父到根上下文。

```
QDeclarativeEngine.setBaseUrl (self, QUrl)
```

设置这台发动机的基础URL_url_。

**See also** [baseUrl](qdeclarativeengine.html#baseUrl)（ ） 。

```
QDeclarativeEngine.setContextForObject (QObject, QDeclarativeContext)
```

设置[QDeclarativeContext](qdeclarativecontext.html)为_object_至_context_。如果_object_已经有一个上下文，则输出警告，但上下文不被改变。

当[QDeclarativeEngine](qdeclarativeengine.html)实例化一个[QObject](qobject.html)时，上下文被自动设置。

**See also** [contextForObject](qdeclarativeengine.html#contextForObject)（ ） 。

```
QDeclarativeEngine.setImportPathList (self, QStringList paths)
```

Sets _paths_因为那里的搜索引擎在一个基于URL的目录结构安装的模块的目录列表。

默认情况下，该列表包含应用程序的可执行文件的目录，在指定路径`QML_IMPORT_PATH`环境变量，以及内置的`ImportsPath`从[QLibraryInfo](qlibraryinfo.html)。

**See also** [importPathList](qdeclarativeengine.html#importPathList)（）和[addImportPath](qdeclarativeengine.html#addImportPath)（ ） 。

```
QDeclarativeEngine.setNetworkAccessManagerFactory (self, QDeclarativeNetworkAccessManagerFactory)
```

设置_factory_用于创建[QNetworkAccessManager](qnetworkaccessmanager.html)（S ） 。

[QNetworkAccessManager](qnetworkaccessmanager.html)用于通过QML所有网络访问。通过实现工厂能够创建自定义[QNetworkAccessManager](qnetworkaccessmanager.html)有专门的缓存，代理和cookie支持。

工厂必须执行引擎之前进行设置。

**See also** [networkAccessManagerFactory](qdeclarativeengine.html#networkAccessManagerFactory)（ ） 。

```
QDeclarativeEngine.setObjectOwnership (QObject, ObjectOwnership)
```

设置_ownership_的_object_。

**See also** [objectOwnership](qdeclarativeengine.html#objectOwnership)（ ） 。

```
QDeclarativeEngine.setOfflineStoragePath (self, QString dir)
```

```
QDeclarativeEngine.setOutputWarningsToStandardError (self, bool)
```

设置是否警告信息将被输出到stderr到_enabled_。

If _enabled_诚然，通过QML产生的任何警告信息将被输出到标准错误，并发射[warnings](qdeclarativeengine.html#warnings)（）信号。如果_enabled_是假的，对[warnings](qdeclarativeengine.html#warnings)（）信号将被发射。这允许应用程序来处理报警输出自己。

默认值是True 。

**See also** [outputWarningsToStandardError](qdeclarativeengine.html#outputWarningsToStandardError)（ ） 。

```
QDeclarativeEngine.setPluginPathList (self, QStringList paths)
```

设置目录所在的引擎搜索的导入模块本地插件（在引用的列表`qmldir`文件）_paths_。

默认情况下，列表中只包含`.`即在该目录中的引擎的搜索`qmldir`文件本身。

**See also** [pluginPathList](qdeclarativeengine.html#pluginPathList)（）和[addPluginPath](qdeclarativeengine.html#addPluginPath)（ ） 。

* * *

## Qt Signal Documentation

```
void quit ()
```

这是该信号的默认超载。

这个信号被发射时，由发动机加载的QML想退出。

```
void warnings (const QList<QDeclarativeError>&)
```

这是该信号的默认超载。

这个信号被发射时_warnings_通过QML生成的消息。