# QDeclarativePropertyMap Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativePropertyMap类允许您设置，可以在QML绑定使用键 - 值对。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `clear (self, QString key)`
*   `bool contains (self, QString key)`
*   `int count (self)`
*   `insert (self, QString key, QVariant value)`
*   `bool isEmpty (self)`
*   `QStringList keys (self)`
*   `int size (self)`
*   `QVariant value (self, QString key)`

### Special Methods

*   `QVariant __getitem__ (self, QString key)`
*   `__len__ (self)`

### Qt Signals

*   `void valueChanged (const QString&,const QVariant&)`

* * *

## Detailed Description

该QDeclarativePropertyMap类允许您设置，可以在QML绑定使用键 - 值对。

QDeclarativePropertyMap提供了一个方便的方式来域数据暴露给UI层。下面的例子显示了如何声明在C + +的数据，然后访问它的QML 。

在C + +中的文件：

```
 // create our data
 QDeclarativePropertyMap ownerData;
 ownerData.insert("name", [QVariant](qvariant.html)([QString](qstring.html)("John Smith")));
 ownerData.insert("phone", [QVariant](qvariant.html)([QString](qstring.html)("555-5555")));

 // expose it to the UI layer
 [QDeclarativeView](qdeclarativeview.html) view;
 [QDeclarativeContext](qdeclarativecontext.html) *ctxt = view.rootContext();
 ctxt->setContextProperty("owner", &ownerData);

 view.setSource([QUrl](qurl.html).fromLocalFile("main.qml"));
 view.show();

```

然后，在`main.qml`：

```
 Text { text: owner.name + " " + owner.phone }

```

绑定是动态的 - 每当一个键的值被更新，什么都绑定到该密钥将更新。

为了检测在UI层做值的变化可以连接到[valueChanged](qdeclarativepropertymap.html#valueChanged)（）信号。但是请注意，[valueChanged](qdeclarativepropertymap.html#valueChanged)（）是**NOT**更改时通过调用发出的制作[insert](qdeclarativepropertymap.html#insert)（）或[clear](qdeclarativepropertymap.html#clear)（） - 它是仅当一个值被从QML更新射出。

**Note:**这是不可能的，从地图中删除键，一旦一个密钥被添加，你只能修改或清除其关联的值。

* * *

## Method Documentation

```
QDeclarativePropertyMap.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个可绑定的地图与父对象_parent_。

```
QDeclarativePropertyMap.clear (self, QString key)
```

清除值（如果有的话）与关联_key_。

```
bool QDeclarativePropertyMap.contains (self, QString key)
```

如果地图包含，则返回True_key_。

**See also** [size](qdeclarativepropertymap.html#size)（ ） 。

```
int QDeclarativePropertyMap.count (self)
```

这是一个重载函数。

同[size](qdeclarativepropertymap.html#size)（ ） 。

```
QDeclarativePropertyMap.insert (self, QString key, QVariant value)
```

设置关联的值_key_至_value_。

如果该键不存在，则会自动创建。

```
bool QDeclarativePropertyMap.isEmpty (self)
```

返回True如果映射不包含键，否则返回False 。

**See also** [size](qdeclarativepropertymap.html#size)（ ） 。

```
QStringList QDeclarativePropertyMap.keys (self)
```

返回键的列表。

已清除键仍然会出现在这个列表中，即使它们相关的值是无效的[QVariants](index.htm#qvariants)。

```
int QDeclarativePropertyMap.size (self)
```

返回键映射中的号码。

**See also** [isEmpty](qdeclarativepropertymap.html#isEmpty)（）和[count](qdeclarativepropertymap.html#count)（ ） 。

```
QVariant QDeclarativePropertyMap.value (self, QString key)
```

返回与关联的值_key_。

如果没有值被设置为这个键（或如果该值已被清除） ，无效[QVariant](qvariant.html)返回。

```
QVariant QDeclarativePropertyMap.__getitem__ (self, QString key)
```

```
 QDeclarativePropertyMap.__len__ (self)
```

* * *

## Qt Signal Documentation

```
void valueChanged (const QString&,const QVariant&)
```

这是该信号的默认超载。

这个信号被发射时在地图中的一个值被改变。_key_是对应于该键_value_已更改。

**Note:**的valueChanged （）是**NOT**更改时通过调用发出的制作[insert](qdeclarativepropertymap.html#insert)（）或[clear](qdeclarativepropertymap.html#clear)（） - 它是仅当一个值被从QML更新射出。