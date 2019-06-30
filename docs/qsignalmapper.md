# QSignalMapper Class Reference

## [[QtCore](index.htm) module]

该QSignalMapper捆绑类的个别发件人的信号。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `map (self)`
*   `map (self, QObject sender)`
*   `QObject mapping (self, int id)`
*   `QObject mapping (self, QString text)`
*   `QObject mapping (self, QWidget widget)`
*   `QObject mapping (self, QObject object)`
*   `removeMappings (self, QObject sender)`
*   `setMapping (self, QObject sender, int id)`
*   `setMapping (self, QObject sender, QString text)`
*   `setMapping (self, QObject sender, QWidget widget)`
*   `setMapping (self, QObject sender, QObject object)`

### Qt Signals

*   `void mapped (int)`
*   `void mapped (const QString&)`
*   `void mapped (QWidget *)`
*   `void mapped (QObject *)`

* * *

## Detailed Description

该QSignalMapper捆绑类的个别发件人的信号。

此类采集一组参数的信号，并重新发射它们与整型，字符串或对应于发送该信号的插件对象的参数。

这个类支持使用特定的字符串或整数与特定对象的映射[setMapping](qsignalmapper.html#setMapping)（ ） 。的对象的信号可以被连接到[map](qsignalmapper.html#map)（）槽，将放出[mapped](qsignalmapper.html#mapped)（）信号与原信号的对象相关联的字符串或整数。映射可以在以后使用中删除[removeMappings](qsignalmapper.html#removeMappings)（ ） 。

例如：假设我们要创建一个包含一组按钮（如工具选项板）的自定义窗口小部件。一种方法是在连接各个按钮的`clicked()`信号到其自己的定制插槽，但在这个例子中，我们希望所有的按钮连接到一个单一的插槽，并通过单击的按钮，参数化的插槽。

下面是一个简单的自定义窗口小部件，有一个单一信号的定义，`clicked()`，这是发射与被点击的按钮的文本：

```
 class ButtonWidget : public [QWidget](qwidget.html)
 {
     Q_OBJECT

 public:
     ButtonWidget([QStringList](qstringlist.html) texts, [QWidget](qwidget.html) *parent = 0);

 signals:
     void clicked(const [QString](qstring.html) &text);

 private:
     QSignalMapper *signalMapper;
 };

```

我们需要实现的唯一功能是构造函数：

```
 ButtonWidget.ButtonWidget([QStringList](qstringlist.html) texts, [QWidget](qwidget.html) *parent)
     : [QWidget](qwidget.html)(parent)
 {
     signalMapper = new QSignalMapper(this);

     [QGridLayout](qgridlayout.html) *gridLayout = new [QGridLayout](qgridlayout.html);
     for (int i = 0; i < texts.size(); ++i) {
         [QPushButton](qpushbutton.html) *button = new [QPushButton](qpushbutton.html)(texts[i]);
         connect(button, SIGNAL(clicked()), signalMapper, SLOT(map()));
         signalMapper->setMapping(button, texts[i]);
         gridLayout->addWidget(button, i / 3, i % 3);
     }

     connect(signalMapper, SIGNAL(mapped(const [QString](qstring.html) &)),
             this, SIGNAL(clicked(const [QString](qstring.html) &)));

     setLayout(gridLayout);
 }

```

文本列表被传递给构造函数。信号映射器的构造和在列表中的每个文本[QPushButton](qpushbutton.html)被创建。我们连接每个按钮的`clicked()`信号到信号映射器的[map](qsignalmapper.html#map)（）槽，并从每个按钮的信号映射到该按钮的文本创建一个映射。最后，我们连接信号变换器的[mapped](qsignalmapper.html#mapped)（ ）信号到自定义widget的`clicked()`信号。当用户点击一个按钮，自定义窗口小部件会发出一个单一的`clicked()`信号，其参数是用户点击按钮的文本。

* * *

## Method Documentation

```
QSignalMapper.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSignalMapper](qsignalmapper.html)与父_parent_。

```
QSignalMapper.map (self)
```

这种方法也是一个Qt槽与C + +的签名`void map()`。

这个插槽发出的信号的基础上哪个对象发送信号给它。

```
QSignalMapper.map (self, QObject sender)
```

这种方法也是一个Qt槽与C + +的签名`void map(QObject *)`。

这个时隙发射的基础上，信号_sender_对象。

```
QObject QSignalMapper.mapping (self, int id)
```

[](qobject.html)

[返回发件人](qobject.html)[QObject](qobject.html)是与相关联的_id_。

**See also** [setMapping](qsignalmapper.html#setMapping)（ ） 。

```
QObject QSignalMapper.mapping (self, QString text)
```

[](qobject.html)

[这个函数的重载](qobject.html)[mapping](qsignalmapper.html#mapping)（ ） 。

```
QObject QSignalMapper.mapping (self, QWidget widget)
```

[](qobject.html)

[这个函数的重载](qobject.html)[mapping](qsignalmapper.html#mapping)（ ） 。

返回发件人[QObject](qobject.html)是与相关联的_widget_。

```
QObject QSignalMapper.mapping (self, QObject object)
```

[](qobject.html)

[这个函数的重载](qobject.html)[mapping](qsignalmapper.html#mapping)（ ） 。

返回发件人[QObject](qobject.html)是与相关联的_object_。

```
QSignalMapper.removeMappings (self, QObject sender)
```

删除所有映射_sender_。

这是自动完成的，当映射对象被销毁。

```
QSignalMapper.setMapping (self, QObject sender, int id)
```

添加一个映射，这样，当[map](qsignalmapper.html#map)（）被从给定的信号_sender_中，信号映射（_id_）被发射。

有可能是对每个发送至多一个整数ID 。

**See also** [mapping](qsignalmapper.html#mapping)（ ） 。

```
QSignalMapper.setMapping (self, QObject sender, QString text)
```

添加一个映射，这样，当[map](qsignalmapper.html#map)（）是从信号_sender_中，信号映射（_text_）被发射。

可能有最多一个文本为每个发件人。

```
QSignalMapper.setMapping (self, QObject sender, QWidget widget)
```

添加一个映射，这样，当[map](qsignalmapper.html#map)（）是从信号_sender_中，信号映射（_widget_）被发射。

可能有最多一个部件每个发件人。

```
QSignalMapper.setMapping (self, QObject sender, QObject object)
```

添加一个映射，这样，当[map](qsignalmapper.html#map)（）是从信号_sender_中，信号映射（_object_）被发射。

可能存在至多一个对象的每个发送者。

* * *

## Qt Signal Documentation

```
void mapped (int)
```

这是该信号的默认超载。

这个信号被发射时[map](qsignalmapper.html#map)（）从一个对象，该对象具有整数的映射集信号。对象的映射整数传入_i_。

**See also** [setMapping](qsignalmapper.html#setMapping)（ ） 。

```
void mapped (const QString&)
```

这个信号被发射时[map](qsignalmapper.html#map)（）从一个对象，它有一个字符串的映射集信号。该对象的字符串映射中传递_text_。

**See also** [setMapping](qsignalmapper.html#setMapping)（ ） 。

```
void mapped (QWidget *)
```

这个信号被发射时[map](qsignalmapper.html#map)（ ）从一个对象，它有一个小部件映射集信号。对象的映射部件被传递_widget_。

**See also** [setMapping](qsignalmapper.html#setMapping)（ ） 。

```
void mapped (QObject *)
```

这个信号被发射时[map](qsignalmapper.html#map)（）从一个对象，该对象具有对象映射集信号。由地图提供的对象被传递_object_。

**See also** [setMapping](qsignalmapper.html#setMapping)（ ） 。