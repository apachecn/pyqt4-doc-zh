# QHelpEngineCore Class Reference

## [[QtHelp](index.htm) module]

该QHelpEngineCore类提供了帮助系统的核心功能。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QHelpEngine](qhelpengine.html)。

### Methods

*   `__init__ (self, QString collectionFile, QObject parent = None)`
*   `bool addCustomFilter (self, QString filterName, QStringList attributes)`
*   `bool autoSaveFilter (self)`
*   `QString collectionFile (self)`
*   `bool copyCollectionFile (self, QString fileName)`
*   `QString currentFilter (self)`
*   `QStringList customFilters (self)`
*   `QVariant customValue (self, QString key, QVariant defaultValue = QVariant())`
*   `QString documentationFileName (self, QString namespaceName)`
*   `QString error (self)`
*   `QByteArray fileData (self, QUrl url)`
*   `list-of-QUrl files (self, QString namespaceName, QStringList filterAttributes, QString extensionFilter = QString())`
*   `QStringList filterAttributes (self)`
*   `QStringList filterAttributes (self, QString filterName)`
*   `list-of-QStringList filterAttributeSets (self, QString namespaceName)`
*   `QUrl findFile (self, QUrl url)`
*   `dict-of-QString-QUrl linksForIdentifier (self, QString id)`
*   `bool registerDocumentation (self, QString documentationFileName)`
*   `QStringList registeredDocumentations (self)`
*   `bool removeCustomFilter (self, QString filterName)`
*   `bool removeCustomValue (self, QString key)`
*   `setAutoSaveFilter (self, bool save)`
*   `setCollectionFile (self, QString fileName)`
*   `setCurrentFilter (self, QString filterName)`
*   `bool setCustomValue (self, QString key, QVariant value)`
*   `bool setupData (self)`
*   `bool unregisterDocumentation (self, QString namespaceName)`

### Static Methods

*   `QVariant metaData (QString documentationFileName, QString name)`
*   `QString namespaceName (QString documentationFileName)`

### Qt Signals

*   `void currentFilterChanged (const QString&)`
*   `void setupFinished ()`
*   `void setupStarted ()`
*   `void warning (const QString&)`

* * *

## Detailed Description

该QHelpEngineCore类提供了帮助系统的核心功能。

之前的帮助引擎可以被使用，它必须通过调用初始化[setupData](qhelpenginecore.html#setupData)（ ） 。在安装过程中的信号的开头[setupStarted](qhelpenginecore.html#setupStarted)（）被发射。从这点上，直到该信号[setupFinished](qhelpenginecore.html#setupFinished)（ ）被发射，是在一个不确定的意义不可用状态的帮助数据。

核心帮助引擎可用于执行不同的任务。通过调用[linksForIdentifier](qhelpenginecore.html#linksForIdentifier)（ ）的引擎返回的URL中指定帮助系统内的文件位置。实际的文件数据可以通过调用retrived[fileData](qhelpenginecore.html#fileData)（ ） 。相反，在这个类中的所有其他功能，[linksForIdentifier](qhelpenginecore.html#linksForIdentifier)（ ）取决于当前设置的自定义过滤器。根据不同的过滤器，该函数可能返回不同的点击率。

每一个帮助引擎可以包含任意数量的自定义过滤器。自定义过滤器是由一个名称来定义，并设置过滤器的属性，并可以通过调用被添加到帮助引擎[addCustomFilter](qhelpenginecore.html#addCustomFilter)（ ） 。类似的，它是通过调用删除[removeCustomFilter](qhelpenginecore.html#removeCustomFilter)（ ） 。[customFilters](qhelpenginecore.html#customFilters)（ ）返回所有定义的过滤器。

帮助引擎还提供了一个持续性的方式媲美ini文件或Windows注册表项设置和读取的值的可能性。欲了解更多信息，请参阅的setValue （ ）或（）的值。

这个类不提供任何GUI组件或功能的指标或内容。如果您需要这些使用的一个[QHelpEngine](qhelpengine.html)代替。

当创建一个自定义帮助观众观众可以通过写其中可能包含不同的关键字被用于配置帮助引擎的自定义集合文件中进行配置。这些关键字和值和它们的含义可以在帮助信息中找到 [creating a custom help collection file](index.htm#creating-a-custom-help-collection-file)助理。

* * *

## Method Documentation

```
QHelpEngineCore.__init__ (self, QString collectionFile, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的核心引擎的帮助用_parent_。帮助引擎使用存储在信息_collectionFile_提供帮助。如果集合文件还不存在，它会被创建。

```
bool QHelpEngineCore.addCustomFilter (self, QString filterName, QStringList attributes)
```

添加新的自定义过滤器_filterName_。该过滤器的属性被指定_attributes_。如果过滤器已经存在，它的属性设置将被替换。该函数返回True如果操作成功，否则返回False 。

**See also** [customFilters](qhelpenginecore.html#customFilters)（）和[removeCustomFilter](qhelpenginecore.html#removeCustomFilter)（ ） 。

```
bool QHelpEngineCore.autoSaveFilter (self)
```

```
QString QHelpEngineCore.collectionFile (self)
```

```
bool QHelpEngineCore.copyCollectionFile (self, QString fileName)
```

创建文件_fileName_如果成功，将文件从当前集合文件到新创建的文件中的所有内容，并返回True，否则返回False 。

在复制过程可确保文件引用的Qt收集文件（`.qch`）文件也会相应更新。

```
QString QHelpEngineCore.currentFilter (self)
```

```
QStringList QHelpEngineCore.customFilters (self)
```

返回自定义过滤器的列表。

**See also** [addCustomFilter](qhelpenginecore.html#addCustomFilter)（）和[removeCustomFilter](qhelpenginecore.html#removeCustomFilter)（ ） 。

```
QVariant QHelpEngineCore.customValue (self, QString key, QVariant defaultValue = QVariant())
```

返回赋予的价值_key_。如果请求的键不存在，则指定_defaultValue_返回。

**See also** [setCustomValue](qhelpenginecore.html#setCustomValue)（）和[removeCustomValue](qhelpenginecore.html#removeCustomValue)（ ） 。

```
QString QHelpEngineCore.documentationFileName (self, QString namespaceName)
```

返回Qt的压缩帮助文件确定的绝对文件名（ 。 QCH ）_namespaceName_。如果没有注册与指定的命名空间的Qt压缩帮助文件，则返回一个空字符串。

**See also** [namespaceName](qhelpenginecore.html#namespaceName)（ ） 。

```
QString QHelpEngineCore.error (self)
```

返回上次发生错误的描述。

```
QByteArray QHelpEngineCore.fileData (self, QUrl url)
```

[](qbytearray.html)

[返回文件所指定的数据_url_。如果文件不存在，空](qbytearray.html)[QByteArray](qbytearray.html)返回。

**See also** [findFile](qhelpenginecore.html#findFile)（ ） 。

```
list-of-QUrl QHelpEngineCore.files (self, QString namespaceName, QStringList filterAttributes, QString extensionFilter = QString())
```

返回文件包含了Qt压缩帮助文件中的列表_namespaceName_。该文件可以被过滤_filterAttributes_以及由它们的扩展名_extensionFilter_（例如，“ HTML” ） 。

```
QStringList QHelpEngineCore.filterAttributes (self)
```

返回所有定义的过滤器属性列表。

```
QStringList QHelpEngineCore.filterAttributes (self, QString filterName)
```

返回过滤器属性所使用的自定义过滤器列表_filterName_。

```
list-of-QStringList QHelpEngineCore.filterAttributeSets (self, QString namespaceName)
```

返回过滤器的属性为Qt的压缩帮助文件中定义与给定的命名空间中的不同的过滤器部分的列表_namespaceName_。

```
QUrl QHelpEngineCore.findFile (self, QUrl url)
```

[

返回一个无效的URL ，如果该文件_url_无法找到。如果该文件存在，则返回无论是同一个URL或一个不同的URL ，如果该文件位于这是通过一个共同的虚拟文件夹合并不同的命名空间。

```
dict-of-QString-QUrl QHelpEngineCore.linksForIdentifier (self, QString id)
```

返回命中发现了一个地图_id_。一击中的包含文件的标题和URL所在的关键字的位置。其结果取决于当前的过滤器，这意味着只有注册为当前过滤器的关键字将被退回。

```
QVariant QHelpEngineCore.metaData (QString documentationFileName, QString name)
```

返回的元数据Qt的压缩帮助文件_documentationFileName_。如果没有可用的无数据_name_，一个无效的QVariant （ ）返回。元数据是指创建Qt的压缩帮助文件时，不能在以后修改。通用元数据包括例如文档的作者。

```
QString QHelpEngineCore.namespaceName (QString documentationFileName)
```

返回由指定Qt的压缩帮助文件中定义的命名空间名称（ QCH ）其_documentationFileName_。如果该文件是无效的，则返回一个空字符串。

](qurl.html)

[**See also**](qurl.html) [documentationFileName](qhelpenginecore.html#documentationFileName)（ ） 。

```
bool QHelpEngineCore.registerDocumentation (self, QString documentationFileName)
```

寄存器文件中包含了Qt压缩的帮助文件（ 。 QCH ）_documentationFileName_。一个压缩的帮助文件，其命名空间唯一标识，只能注册一次。返回True ，如果注册成功，否则为False。

**See also** [unregisterDocumentation](qhelpenginecore.html#unregisterDocumentation)（）和[error](qhelpenginecore.html#error)（ ） 。

```
QStringList QHelpEngineCore.registeredDocumentations (self)
```

返回当前集合文件的所有已注册的Qt压缩帮助文件的列表。返回的名称是注册的Qt压缩的帮助文件（。 QCH ）的命名空间。

```
bool QHelpEngineCore.removeCustomFilter (self, QString filterName)
```

返回True如果过滤器_filterName_成功移除，否则为False 。

**See also** [addCustomFilter](qhelpenginecore.html#addCustomFilter)（）和[customFilters](qhelpenginecore.html#customFilters)（ ） 。

```
bool QHelpEngineCore.removeCustomValue (self, QString key)
```

移除_key_从集合文件中的设置部分。如果该值被删除成功，否则为False ，则返回True 。

**See also** [customValue](qhelpenginecore.html#customValue)（）和[setCustomValue](qhelpenginecore.html#setCustomValue)（ ） 。

```
QHelpEngineCore.setAutoSaveFilter (self, bool save)
```

```
QHelpEngineCore.setCollectionFile (self, QString fileName)
```

```
QHelpEngineCore.setCurrentFilter (self, QString filterName)
```

```
bool QHelpEngineCore.setCustomValue (self, QString key, QVariant value)
```

保存_value_下_key_。如果键已经存在，则该值将被复盖。返回True如果该值已成功保存，否则为False 。

**See also** [customValue](qhelpenginecore.html#customValue)（）和[removeCustomValue](qhelpenginecore.html#removeCustomValue)（ ） 。

```
bool QHelpEngineCore.setupData (self)
```

设置了帮助发动机通过处理发现在收集文件并返回True，如果成功的信息，否则返回False 。

通过调用函数时，帮助引擎是被迫立即初始化。大部分的时间，这个功能并没有被显式调用，因为它依赖于正确设置了帮助发动机getter函数做自己。

**Note:** `qsqlite4.dll`需要部署的应用程序加载的帮助集合时帮助系统使用sqlite的驱动程序。

```
bool QHelpEngineCore.unregisterDocumentation (self, QString namespaceName)
```

注销确定其Qt的压缩的帮助文件（ 。 QCH ）_namespaceName_从帮助集合。成功时返回TRUE ，否则返回False 。

**See also** [registerDocumentation](qhelpenginecore.html#registerDocumentation)（）和[error](qhelpenginecore.html#error)（ ） 。

* * *

## Qt Signal Documentation

```
void currentFilterChanged (const QString&)
```

这是该信号的默认超载。

当电流过滤器改变为这个信号被发射_newFilter_。

```
void setupFinished ()
```

这是该信号的默认超载。

当设置完成后这个信号被发射。

```
void setupStarted ()
```

这是该信号的默认超载。

当安装程序启动这个信号被发射。

```
void warning (const QString&)
```

这是该信号的默认超载。

当一个非关键性错误发生时，这个信号被发射。警告消息存储在_msg_。