# QSysInfo Class Reference

## [[QtCore](index.htm) module]

该QSysInfo类提供有关系统的信息。[More...](#details)

### Types

*   `enum Endian { BigEndian, LittleEndian, ByteOrder }`
*   `enum Sizes { WordSize }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSysInfo)`

* * *

## Detailed Description

该QSysInfo类提供有关系统的信息。

*   [WordSize](qsysinfo.html#Sizes-enum) specifies the size of a pointer for the platform on which the application is compiled.
*   [ByteOrder](qsysinfo.html#Endian-enum) specifies whether the platform is big-endian or little-endian.
*   [WindowsVersion](qsysinfo.html#WindowsVersion-var) specifies the version of the Windows operating system on which the application is run (Windows only)
*   [MacintoshVersion](qsysinfo.html#MacintoshVersion-var) specifies the version of the Macintosh operating system on which the application is run (Mac only).

一些常量只在某些平台上定义的。您可以使用预处理器符号[Q_WS_WIN](index.htm#Q_WS_WIN)和[Q_WS_MAC](index.htm#Q_WS_MAC)要测试该应用程序的Windows或Mac下编译。

* * *

## Type Documentation

```
QSysInfo.Endian
```

| Constant | Value | Description |
| --- | --- | --- |
| `QSysInfo.BigEndian` | `0` | big-endian字节顺序（也称为网络字节顺序） |
| `QSysInfo.LittleEndian` | `1` | little-endian字节顺序 |
| `QSysInfo.ByteOrder` | `&lt;platform-dependent&gt;` | 等于大尾端或LittleEndian ，取决于该平台的字节顺序。 |

```
QSysInfo.Sizes
```

此枚举提供有关数据结构所使用的底层架构的大小平台特定的信息。

| Constant | Value | Description |
| --- | --- | --- |
| `QSysInfo.WordSize` | `( sizeof( void * ) &lt;&lt;3 )` | 在指针上编译应用程序平台（ 32或64 ）的位的大小。 |

* * *

## Method Documentation

```
QSysInfo.__init__ (self)
```

```
QSysInfo.__init__ (self, QSysInfo)
```