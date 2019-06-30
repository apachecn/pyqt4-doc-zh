# QDBusObjectPath Class Reference

## [[QtDBus](index.htm) module]

该QDBusObjectPath类使程序员可以识别[OBJECT_PATH](index.htm#object-paths)输入的D-Bus的类型系统提供的。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString path)`
*   `__init__ (self, QDBusObjectPath)`
*   `QString path (self)`
*   `setPath (self, QString path)`

### Special Methods

*   `bool __eq__ (self, QDBusObjectPath rhs)`
*   `bool __ge__ (self, QDBusObjectPath rhs)`
*   `int __hash__ (self)`
*   `bool __lt__ (self, QDBusObjectPath rhs)`
*   `bool __ne__ (self, QDBusObjectPath rhs)`

* * *

## Detailed Description

该QDBusObjectPath类使程序员可以识别[OBJECT_PATH](index.htm#object-paths)输入的D-Bus的类型系统提供的。

* * *

## Method Documentation

```
QDBusObjectPath.__init__ (self)
```

构造一个新对象路径。

```
QDBusObjectPath.__init__ (self, QString path)
```

根据给定的一个新的对象路径_path_。

**See also** [setPath](qdbusobjectpath.html#setPath)（ ） 。

```
QDBusObjectPath.__init__ (self, QDBusObjectPath)
```

根据给定的一个新的对象路径_path_。

```
QString QDBusObjectPath.path (self)
```

```
QDBusObjectPath.setPath (self, QString path)
```

分配给定的值_path_这个对象路径。

**See also** [path](qdbusobjectpath.html#pathx)（ ） 。

```
bool QDBusObjectPath.__eq__ (self, QDBusObjectPath rhs)
```

```
bool QDBusObjectPath.__ge__ (self, QDBusObjectPath rhs)
```

```
int QDBusObjectPath.__hash__ (self)
```

```
bool QDBusObjectPath.__lt__ (self, QDBusObjectPath rhs)
```

```
bool QDBusObjectPath.__ne__ (self, QDBusObjectPath rhs)
```