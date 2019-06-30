# QIconEngineV2 Class Reference

## [[QtGui](index.htm) module]

该QIconEngineV2类提供了一个抽象基类[QIcon](qicon.html)渲染器。[More...](#details)

继承[QIconEngine](qiconengine.html)。

### Types

*   `class **[AvailableSizesArgument](index.htm)**`
*   `enum IconEngineHook { AvailableSizesHook, IconNameHook }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIconEngineV2)`
*   `list-of-QSize availableSizes (self, QIcon.Mode mode = QIcon.Normal, QIcon.State state = QIcon.Off)`
*   `QIconEngineV2 clone (self)`
*   `QString iconName (self)`
*   `QString key (self)`
*   `bool read (self, QDataStream in)`
*   `bool write (self, QDataStream out)`

* * *

## Detailed Description

该QIconEngineV2类提供了一个抽象基类[QIcon](qicon.html)渲染器。

图标引擎呈现[QIcon](qicon.html)秒。随着图标的引擎，您可以自定义图标。 Qt提供了一个默认的引擎，使图标通过缩放图标，并提供一个残疾人的外观坚持目前的风格。

发动机是要么通过一个安装上的图标[QIcon](qicon.html)构造函数或通过[QIconEnginePluginV2](index.htm)。该插件所使用的Qt的，如果在创建图标时，一个特定的引擎没有给出。见QIconEngineV2类说明以了解如何创建图标引擎插件。

图标引擎提供的渲染功能，适用于[QIcon](qicon.html)。每个图标都有一个对应的图标引擎负责与所请求的大小，模式和状态绘制的图标。

QIconEngineV2扩展的API[QIconEngine](qiconengine.html)以允许的图标发动机内容流，并且应该使用的[QIconEngine](qiconengine.html)实施新的图标发动机。

* * *

## Type Documentation

```
QIconEngineV2.IconEngineHook
```

这些枚举值用于[virtual_hook](qiconenginev2.html#virtual_hook)（ ） ，让更多的查询引擎图标不破坏二进制兼容性。

| Constant | Value | Description |
| --- | --- | --- |
| `QIconEngineV2.AvailableSizesHook` | `1` | 允许查询中包含的像素映射为像素图的基于引擎的尺寸。该_data_的说法[virtual_hook](qiconenginev2.html#virtual_hook)（）函数是一个[AvailableSizesArgument](index.htm)指针应该充满图标的大小。工作在一个可扩展的，矢量格式条款引擎通常返回一个空列表。 |
| `QIconEngineV2.IconNameHook` | `2` | 允许使用实例化一个图标时要查询用于创建图标的名称，例如[QIcon.fromTheme](qicon.html#fromTheme)（ ） 。 |

这个枚举被引入或修改的Qt 4.5 。

**See also** [virtual_hook](qiconenginev2.html#virtual_hook)（ ） 。

* * *

## Method Documentation

```
QIconEngineV2.__init__ (self)
```

```
QIconEngineV2.__init__ (self, QIconEngineV2)
```

```
list-of-QSize QIconEngineV2.availableSizes (self, QIcon.Mode mode = QIcon.Normal, QIcon.State state = QIcon.Off)
```

返回包含在发动机的特定的所有图像的大小_mode_和_state_。

**Note:**这是一个辅助方法，并在实际工作是由完成[virtual_hook](qiconenginev2.html#virtual_hook)（ ）方法，因此这种方法取决于图标引擎的支持，并且可能无法与所有图标发动机的正常工作。

此功能被引入Qt的4.5 。

```
QIconEngineV2 QIconEngineV2.clone (self)
```

[

返回此图标引擎的一个副本。

```
QString QIconEngineV2.iconName (self)
```

返回用于（如果可用）来创建引擎，该名称。

](qiconenginev2.html)

[**Note:**这是一个辅助方法，并在实际工作是由完成](qiconenginev2.html)[virtual_hook](qiconenginev2.html#virtual_hook)（ ）方法，因此这种方法取决于图标引擎的支持，并且可能无法与所有图标发动机的正常工作。

此功能被引入Qt的4.7 。

```
QString QIconEngineV2.key (self)
```

返回标识此图标引擎的关键。

```
bool QIconEngineV2.read (self, QDataStream in)
```

读取从图标发动机内容[QDataStream](qdatastream.html) _in_。返回True如果内容被读取，否则返回False 。

[QIconEngineV2](qiconenginev2.html)的默认实现始终返回False。

```
bool QIconEngineV2.write (self, QDataStream out)
```

写这个引擎的内容到[QDataStream](qdatastream.html) _out_。返回True如果内容被写，否则返回False 。

[QIconEngineV2](qiconenginev2.html)的默认实现始终返回False。