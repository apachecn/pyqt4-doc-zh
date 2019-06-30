# QDBus Class Reference

## [[QtDBus](index.htm) module]

该QDBus命名空间包含了整个二手其他标识符[QtDBus](index.htm)库。[More...](#details)

### Types

*   `enum CallMode { NoBlock, Block, BlockWithGui, AutoDetect }`

* * *

## Detailed Description

该QDBus命名空间包含了整个二手其他标识符[QtDBus](index.htm)库。

* * *

## Type Documentation

```
QDBus.CallMode
```

这个枚举描述放置一个函数调用的各种方法。有效的模式是：

| Constant | Value | Description |
| --- | --- | --- |
| `QDBus.NoBlock` | `0` | 发出呼叫，但不为等待答复（答复的内容将被丢弃） 。 |
| `QDBus.Block` | `1` | 不要使用一个事件循环等待一个答复，而是阻止网络操作，同时等待。这意味着用户界面可能不会更新，直到函数返回。 |
| `QDBus.BlockWithGui` | `2` | 使用Qt的事件循环，等待答复。这意味着，用户界面将保持响应（处理输入事件） ，但它也意味着其他事件可能发生，象信号传递和其他D-Bus的方法调用。 |
| `QDBus.AutoDetect` | `3` | 自动检测，如果被调用的函数有一个答复。 |

当使用BlockWithGui ，应用程序必须重入任何功能齐备。