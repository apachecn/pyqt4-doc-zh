# QElapsedTimer Class Reference

## [[QtCore](index.htm) module]

该QElapsedTimer类提供了一种快速的方法来计算经过的时间。[More...](#details)

### Types

*   `enum ClockType { SystemTime, MonotonicClock, TickCounter, MachAbsoluteTime, PerformanceCounter }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QElapsedTimer)`
*   `int elapsed (self)`
*   `bool hasExpired (self, int timeout)`
*   `invalidate (self)`
*   `bool isValid (self)`
*   `int msecsSinceReference (self)`
*   `int msecsTo (self, QElapsedTimer other)`
*   `int nsecsElapsed (self)`
*   `int restart (self)`
*   `int secsTo (self, QElapsedTimer other)`
*   `start (self)`

### Static Methods

*   `ClockType clockType ()`
*   `bool isMonotonic ()`

### Special Methods

*   `bool __eq__ (self, QElapsedTimer other)`
*   `bool __ge__ (self, QElapsedTimer v2)`
*   `bool __lt__ (self, QElapsedTimer v2)`
*   `bool __ne__ (self, QElapsedTimer other)`

* * *

## Detailed Description

该QElapsedTimer类提供了一种快速的方法来计算经过的时间。

该QElapsedTimer类通常用于快速计算多少时间两个事件之间经过。它的API是类似的[QTime](qtime.html)，使被使用，可以很容易的移植到新类的代码。

然而，不像[QTime](qtime.html)， QElapsedTimer尝试尽可能使用单调的时钟。这意味着它不可能QElapsedTimer对象转换为人类可读的时间。

典型用例的类是确定多少时间是如何度过在一个缓慢的操作。这种情况下最简单的例子是用于调试目的，如下面的例子：

```
     QElapsedTimer timer;
     timer.start();

     slowOperation1();

     qDebug() << "The slow operation took" << timer.elapsed() << "milliseconds";

```

在这个例子中，定时器是由一个呼叫开始[start](qelapsedtimer.html#start)（）和定时器计时是由计算[elapsed](qelapsedtimer.html#elapsed)（）函数。

所经过的时间，也可用于重新计算可用于其它操作所需的时间，之后，第一个是完整的。当执行必须在一定的时间内完成，这是有用的，但需要几个步骤。该`waitFor`在类型的功能[QIODevice](qiodevice.html)和它的子类是需要这样的好例子。在这种情况下，代码可能如下：

```
 void executeSlowOperations(int timeout)
 {
     QElapsedTimer timer;
     timer.start();
     slowOperation1();

     int remainingTime = timeout - timer.elapsed();
     if (remainingTime > 0)
         slowOperation2(remainingTime);
 }

```

另一个用例是执行某种操作的具体时间片。为此， QElapsedTimer提供[hasExpired](qelapsedtimer.html#hasExpired)（）的便利功能，它可以被用于确定是否一个特定的毫秒已经过去了：

```
 void executeOperationsForTime(int ms)
 {
     QElapsedTimer timer;
     timer.start();

     while (!timer.hasExpired(ms))
         slowOperation1();
 }

```

### Reference clocks

QElapsedTimer将使用该平台的单调参考时钟在所有支持它的平台上（见[QElapsedTimer.isMonotonic](qelapsedtimer.html#isMonotonic)（））。这具有额外的好处， QElapsedTimer不受时间的调整，如在用户校正的时间。也不像[QTime](qtime.html)， QElapsedTimer是免疫的变化时区设置，如日光节约时间。

另一方面，这意味着QElapsedTimer值只能与使用相同的参考其他值进行比较。这是尤其如此，如果因为参考的时间是从QElapsedTimer对象（摘录[QElapsedTimer.msecsSinceReference](qelapsedtimer.html#msecsSinceReference)（ ） ）和序列化。这些值不应该在网络上交换或保存到磁盘上，因为没有告诉计算机节点接收的数据是否是相同的一个始发它，或者如果它已经重新启动。

它是，但是，可以在同一台机器上运行的其他进程，条件是它们也使用相同的参考时钟交换价值。 QElapsedTimer将始终使用同一个时钟，因此它的安全与来自另一个进程的值来在同一台机器进行比较。如果比较其他的API产生的值，你应该检查所使用的时钟是相同的QElapsedTimer （见[QElapsedTimer.clockType](qelapsedtimer.html#clockType)（））。

#### 32-bit overflows

一些该QElapsedTimer有一个有限的范围和击球的上限（通常为32位）后可能溢出的时钟。 QElapsedTimer处理这个溢出问题，并提出了一致的时机。然而，由于提取从QElapsedTimer参考时间时，在同一机器两个不同的过程可能有不同的理解的多少时间实际上已经过去了。

在其上的信息时钟类型可能会溢出，以及如何修复这个问题将随着时钟类型的记录。

* * *

## Type Documentation

```
QElapsedTimer.ClockType
```

这个枚举包含了不同的时钟类型[QElapsedTimer](qelapsedtimer.html)可以使用。

[QElapsedTimer](qelapsedtimer.html)将始终使用相同的时钟类型在特定的机器，所以这个值的程序的生命周期内不会改变。它被设置成使得[QElapsedTimer](qelapsedtimer.html)可以与其它非Qt的实现中使用，以保证该相同的参考时钟被使用。

| Constant | Value | Description |
| --- | --- | --- |
| `QElapsedTimer.SystemTime` | `0` | 人类可读的系统时间。这个时钟是不是单调的。 |
| `QElapsedTimer.MonotonicClock` | `1` | 该系统的单调时钟，通常是在Unix系统中找到。这个时钟是单调的，并且不会溢出。 |
| `QElapsedTimer.TickCounter` | `2` | 该系统的时钟计数器，在Windows和Symbian系统中使用。这个时钟可能会溢出。 |
| `QElapsedTimer.MachAbsoluteTime` | `3` | 在Mach内核的绝对时间（ Mac OS X中） 。这个时钟是单调的，并且不会溢出。 |
| `QElapsedTimer.PerformanceCounter` | `4` | Windows提供的高分辨率性能计数器。这个时钟是单调的，并且不会溢出。 |

##### SystemTime

系统时间时钟是纯粹的实时性，自1970年1月1日在0:00 UTC毫秒表示。它等价于C和POSIX的返回值`time`功能，以毫秒为单位加入。这个时钟类型目前只用在不支持单调时钟Unix系统（见下文）。

这是唯一的非单调时钟[QElapsedTimer](qelapsedtimer.html)可以使用。

##### MonotonicClock

这是系统的单调时钟，因为任意一个点过去以毫秒为单位。这种类型的时钟是用在哪些支持POSIX的单调时钟（ Unix系统`_POSIX_MONOTONIC_CLOCK`） 。

这个时钟不会溢出。

##### TickCounter

滴答计数器的时钟类型是基于系统的或处理器的时钟计数器，乘以一个刻度的持续时间。这个时钟类型用于在Windows和Symbian平台。如果高精度的性能计数器，可以在Windows上，`PerformanceCounter`时钟类型来代替。

该TickCounter时钟类型是可能会溢出的唯一时钟类型。 Windows Vista和Windows Server 2008中支持扩展的64位时钟计数器，它允许避免溢出。

在Windows系统中，时钟后2 ^ 32毫秒，这相当于大约49.7天溢出。这意味着，由于基准时间两个过程的推算可能是由不同的2 ^ 32毫秒的倍数。当比较这些值，它的建议，高32位的毫秒计数的被屏蔽掉。

在Symbian系统中，溢出发生后2 ^ 32的刻度，这期间可以从平台的HAL使用恒定HAL.ENanoTickPeriod获得的。在比较过程之间的值，有必要由蜱的持续时间来划分值和屏蔽掉的高32位。

##### MachAbsoluteTime

这个时钟类型是基于马赫内核，如在Mac OS X发现这个时钟类型是从MonotonicClock单独列示，因为Mac OS X是还涉及了UNIX系统，并且可以支持一个POSIX单调时钟值呈现不同的绝对时间从马赫绝对时间。

这个时钟是单调的，并且不会溢出。

##### PerformanceCounter

这个时钟使用Windows功能`QueryPerformanceCounter`和`QueryPerformanceFrequency`访问系统的高精度性能计数器。由于在所有的系统上，此计数器可能不可用，[QElapsedTimer](qelapsedtimer.html)将回落至`TickCounter`时钟自动地，如果该时钟不能使用。

这个时钟是单调的，并且不会溢出。

**See also** [clockType](qelapsedtimer.html#clockType)（）和[isMonotonic](qelapsedtimer.html#isMonotonic)（ ） 。

* * *

## Method Documentation

```
QElapsedTimer.__init__ (self)
```

```
QElapsedTimer.__init__ (self, QElapsedTimer)
```

```
ClockType QElapsedTimer.clockType ()
```

[](qelapsedtimer.html#ClockType-enum)

[返回时钟类型，这](qelapsedtimer.html#ClockType-enum)[QElapsedTimer](qelapsedtimer.html)实现使用。

**See also** [isMonotonic](qelapsedtimer.html#isMonotonic)（ ） 。

```
int QElapsedTimer.elapsed (self)
```

返回的毫秒数，因为这[QElapsedTimer](qelapsedtimer.html)上次启动。在调用此函数[QElapsedTimer](qelapsedtimer.html)这被认定无效，将导致不确定的结果。

**See also** [start](qelapsedtimer.html#start)（ ）[restart](qelapsedtimer.html#restart)（ ）[hasExpired](qelapsedtimer.html#hasExpired)（）和[invalidate](qelapsedtimer.html#invalidate)（ ） 。

```
bool QElapsedTimer.hasExpired (self, int timeout)
```

返回True如果[QElapsedTimer](qelapsedtimer.html)已经过期了_timeout_毫秒（即，多于_timeout_毫秒已经过去了） 。价值_timeout_可以是-1 ，表明该计时器未到期，在这种情况下，该功能将始终返回False 。

**See also** [elapsed](qelapsedtimer.html#elapsed)（ ） 。

```
QElapsedTimer.invalidate (self)
```

这个商标[QElapsedTimer](qelapsedtimer.html)对象为无效。

一个无效的对象可以进行检查[isValid](qelapsedtimer.html#isValid)（ ） 。定时器的计算距今无效数据是不确定的，可能会产生奇特的效果。

**See also** [isValid](qelapsedtimer.html#isValid)（ ）[start](qelapsedtimer.html#start)（）和[restart](qelapsedtimer.html#restart)（ ） 。

```
bool QElapsedTimer.isMonotonic ()
```

返回True如果这是一个单调的时钟，否则返回False。看到在不同的时钟类型，了解哪些是单调的信息。

**See also** [clockType](qelapsedtimer.html#clockType)（）和[QElapsedTimer.ClockType](qelapsedtimer.html#ClockType-enum)。

```
bool QElapsedTimer.isValid (self)
```

返回False，如果这个对象是无效通过调用[invalidate](qelapsedtimer.html#invalidate)（） ，并没有被自启动。

**See also** [invalidate](qelapsedtimer.html#invalidate)（ ）[start](qelapsedtimer.html#start)（）和[restart](qelapsedtimer.html#restart)（ ） 。

```
int QElapsedTimer.msecsSinceReference (self)
```

返回毫秒的最后一次这样的数[QElapsedTimer](qelapsedtimer.html)对象开始，其参考时钟的开始。

这个数字通常是任意的所有时钟的除外[QElapsedTimer.SystemTime](qelapsedtimer.html#ClockType-enum)时钟。对于时钟类型，这个数字是毫秒自1970年1月1日在0:00 UTC的数量（即，它是表示以毫秒为单位的Unix时间） 。

**See also** [clockType](qelapsedtimer.html#clockType)（）和[elapsed](qelapsedtimer.html#elapsed)（ ） 。

```
int QElapsedTimer.msecsTo (self, QElapsedTimer other)
```

返回毫秒这之间的数[QElapsedTimer](qelapsedtimer.html)和_other_。如果_other_这个对象之前开始，返回值将是积极的。如果是起步较晚，返回值将是负数。

返回值是不确定的，如果这个对象或_other_已失效。

**See also** [secsTo](qelapsedtimer.html#secsTo)（）和[elapsed](qelapsedtimer.html#elapsed)（ ） 。

```
int QElapsedTimer.nsecsElapsed (self)
```

返回纳秒数，因为这[QElapsedTimer](qelapsedtimer.html)上次启动。在调用此函数[QElapsedTimer](qelapsedtimer.html)这被认定无效，将导致不确定的结果。

在不提供纳秒分辨率的平台，返回的值将是现有的最佳估计。

此功能被引入Qt的4.8 。

**See also** [start](qelapsedtimer.html#start)（ ）[restart](qelapsedtimer.html#restart)（ ）[hasExpired](qelapsedtimer.html#hasExpired)（）和[invalidate](qelapsedtimer.html#invalidate)（ ） 。

```
int QElapsedTimer.restart (self)
```

重新启动定时器，并返回自上一次开始所经过的时间。此函数等同于获得的经过时间以[elapsed](qelapsedtimer.html#elapsed)（ ） ，然后重新启动定时器[start](qelapsedtimer.html#start)（） ，但它这样做在一个单一的操作中，避免了需要获得时钟值的两倍。

下面的例子演示了如何使用这个功能来校准参数，以一个缓慢的操作（例如，迭代次数），因此这种操作至少需要250毫秒：

```
     [QElapsedTimer](qelapsedtimer.html) timer;

     int count = 1;
     timer.start();
     do {
         count *= 2;
         slowOperation2(count);
     } while (timer.restart() < 250);

     return count;

```

**See also** [start](qelapsedtimer.html#start)（ ）[invalidate](qelapsedtimer.html#invalidate)（）和[elapsed](qelapsedtimer.html#elapsed)（ ） 。

```
int QElapsedTimer.secsTo (self, QElapsedTimer other)
```

返回秒这之间的数[QElapsedTimer](qelapsedtimer.html)和_other_。如果_other_这个对象之前开始，返回值将是积极的。如果是起步较晚，返回值将是负数。

返回值是不确定的，如果这个对象或_other_已失效。

**See also** [msecsTo](qelapsedtimer.html#msecsTo)（）和[elapsed](qelapsedtimer.html#elapsed)（ ） 。

```
QElapsedTimer.start (self)
```

启动此定时器。一旦开始，一个计时器的值可以与被检查[elapsed](qelapsedtimer.html#elapsed)（）或[msecsSinceReference](qelapsedtimer.html#msecsSinceReference)（ ） 。

通常情况下，一个定时器被启动只是一个冗长的操作，如前：

```
     [QElapsedTimer](qelapsedtimer.html) timer;
     timer.start();

     slowOperation1();

     qDebug() << "The slow operation took" << timer.elapsed() << "milliseconds";

```

此外，启动定时器使它再次有效。

**See also** [restart](qelapsedtimer.html#restart)（ ）[invalidate](qelapsedtimer.html#invalidate)（）和[elapsed](qelapsedtimer.html#elapsed)（ ） 。

```
bool QElapsedTimer.__eq__ (self, QElapsedTimer other)
```

```
bool QElapsedTimer.__ge__ (self, QElapsedTimer v2)
```

```
bool QElapsedTimer.__lt__ (self, QElapsedTimer v2)
```

```
bool QElapsedTimer.__ne__ (self, QElapsedTimer other)
```