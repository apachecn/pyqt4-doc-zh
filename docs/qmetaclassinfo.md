# QMetaClassInfo Class Reference

## [[QtCore](index.htm) module]

该QMetaClassInfo类提供有关类的附加信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QMetaClassInfo)`
*   `str name (self)`
*   `str value (self)`

* * *

## Detailed Description

该QMetaClassInfo类提供有关类的附加信息。

类信息的项目是简单的_name_ - _value_正在使用指定的对[Q_CLASSINFO](qobject.html#Q_CLASSINFO)（）中的源代码。该信息可以使用检索[name](qmetaclassinfo.html#name)（）和[value](qmetaclassinfo.html#value)（ ） 。例如：

```
 class MyClass
 {
     Q_OBJECT
     Q_CLASSINFO("author", "Sabrina Schweinsteiger")
     Q_CLASSINFO("url", "http://doc.moosesoft.co.uk/1.0/")

 public:
     ...
 };

```

这种机制是免费为您在您的Qt应用程序使用。 Qt不使用它的任何类。

* * *

## Method Documentation

```
QMetaClassInfo.__init__ (self)
```

```
QMetaClassInfo.__init__ (self, QMetaClassInfo)
```

```
str QMetaClassInfo.name (self)
```

返回此项目的名称。

**See also** [value](qmetaclassinfo.html#value)（ ） 。

```
str QMetaClassInfo.value (self)
```

返回此项目的值。

**See also** [name](qmetaclassinfo.html#name)（ ） 。