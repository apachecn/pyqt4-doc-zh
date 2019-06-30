# QEasingCurve Class Reference

## [[QtCore](index.htm) module]

该QEasingCurve类提供​​用于控制动画的缓和曲线。[More...](#details)

### Types

*   `enum Type { Linear, InQuad, OutQuad, InOutQuad, ..., Custom }`

### Methods

*   `__init__ (self, Type type = QEasingCurve.Linear)`
*   `__init__ (self, QEasingCurve other)`
*   `float amplitude (self)`
*   `callable customType (self)`
*   `float overshoot (self)`
*   `float period (self)`
*   `setAmplitude (self, float amplitude)`
*   `setCustomType (self, callable func)`
*   `setOvershoot (self, float overshoot)`
*   `setPeriod (self, float period)`
*   `setType (self, Type type)`
*   `Type type (self)`
*   `float valueForProgress (self, float progress)`

### Special Methods

*   `bool __eq__ (self, QEasingCurve other)`
*   `bool __ne__ (self, QEasingCurve other)`

* * *

## Detailed Description

该QEasingCurve类提供​​用于控制动画的缓和曲线。

缓和曲线描述的功能，其控制0和1之间的内插的速度应如何。缓和曲线允许从一个值到另一个过渡显得更自然不是一个简单的恒定速度将允许。该QEasingCurve类通常是在与结合使用[QVariantAnimation](qvariantanimation.html)和[QPropertyAnimation](qpropertyanimation.html)类，但可以使用其本身。它通常被用来从零速度（缓和）加速插或减速到零速度（缓出） 。缓解和减轻了，也可以在同一个缓动曲线相结合。

来计算内插的速度，缓和曲线提供的功能[valueForProgress](qeasingcurve.html#valueForProgress)（ ），其中该_progress_参数指定插值的进度： 0是插值的起始值， 1为插值的终值。返回的值是插值的有效进展。如果返回值是一样的输入值的所有输入值的缓动曲线是线性曲线。这是默认行为。

例如，

```
 QEasingCurve easing(QEasingCurve.InOutQuad);

 for([qreal](index.htm#qreal-typedef) t = 0.0; t < 1.0; t+=0.1)
     qWarning() << "Effective progress" << t << " is
                << easing.valueForProgress(t); 

```

将打印0和1之间的内插的有效进展。

当使用一个[QPropertyAnimation](qpropertyanimation.html)时，相关的缓和曲线将被用于控制起始值和endValue值之间的内插的进展：

```
 [QPropertyAnimation](qpropertyanimation.html) animation;
 animation.setStartValue(0);
 animation.setEndValue(1000);
 animation.setDuration(1000);
 animation.setEasingCurve(QEasingCurve.InOutQuad);

```

设定的幅度，过冲，期间或能力取决于QEasingCurve类型。振幅接入服务提供给表现为弹簧等弹性及反弹曲线的曲线。变化的幅度变化的曲线的高度。访问期间只适用于弹性曲线和设置较高的周期减缓反弹的速度。只有具有“自食其果”的行为，如曲线[InBack](qeasingcurve.html#Type-enum)，[OutBack](qeasingcurve.html#Type-enum)，[InOutBack](qeasingcurve.html#Type-enum)和[OutInBack](qeasingcurve.html#Type-enum)有过冲的设置。这些曲线将插以外的终点，并返回到终点，作用类似于一个飞去来器。

该[Easing Curves Example](index.htm)包含QEasingCurve类型的样品并允许您更改曲线设置。

* * *

## Type Documentation

```
QEasingCurve.Type
```

缓和曲线的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QEasingCurve.Linear` | `0` | ![](../img/qeasingcurve-linear.png)
缓和曲线的线性（ t）的功能：速度是恒定的。 |
| `QEasingCurve.InQuad` | `1` | ![](../img/qeasingcurve-inquad.png)
缓和曲线二次（T ^ 2 ）功能：从零速度加速。 |
| `QEasingCurve.OutQuad` | `2` | ![](../img/qeasingcurve-outquad.png)
缓和曲线二次（T ^ 2 ）功能：减速至零速度。 |
| `QEasingCurve.InOutQuad` | `3` | ![](../img/qeasingcurve-inoutquad.png)
缓和曲线二次（T ^ 2 ）功能：加速至一半，然后再减速。 |
| `QEasingCurve.OutInQuad` | `4` | ![](../img/qeasingcurve-outinquad.png)
缓和曲线二次（T ^ 2 ）功能：减速至一半，然后再加速。 |
| `QEasingCurve.InCubic` | `5` | ![](../img/qeasingcurve-incubic.png)
缓和曲线立方（T ^ 3 ）功能：从零速度加速。 |
| `QEasingCurve.OutCubic` | `6` | ![](../img/qeasingcurve-outcubic.png)
缓和曲线立方（T ^ 3 ）功能：减速至零速度。 |
| `QEasingCurve.InOutCubic` | `7` | ![](../img/qeasingcurve-inoutcubic.png)
缓和曲线立方（T ^ 3 ）功能：加速至一半，然后再减速。 |
| `QEasingCurve.OutInCubic` | `8` | ![](../img/qeasingcurve-outincubic.png)
缓和曲线立方（T ^ 3 ）功能：减速，直到一半，然后再加速。 |
| `QEasingCurve.InQuart` | `9` | ![](../img/qeasingcurve-inquart.png)
缓和曲线四次（T ^ 4 ）功能：从零速度加速。 |
| `QEasingCurve.OutQuart` | `10` | ![](../img/qeasingcurve-outquart.png)
缓和曲线四次（T ^ 4 ）功能：减速至零速度。 |
| `QEasingCurve.InOutQuart` | `11` | ![](../img/qeasingcurve-inoutquart.png)
缓和曲线四次（T ^ 4 ）功能：加速至一半，然后再减速。 |
| `QEasingCurve.OutInQuart` | `12` | ![](../img/qeasingcurve-outinquart.png)
缓和曲线四次（T ^ 4 ）功能：减速，直到一半，然后再加速。 |
| `QEasingCurve.InQuint` | `13` | ![](../img/qeasingcurve-inquint.png)
缓和曲线五次（T ^ 5 ）宽松：从零速度加速。 |
| `QEasingCurve.OutQuint` | `14` | ![](../img/qeasingcurve-outquint.png)
缓和曲线五次（T ^ 5 ）功能：减速至零速度。 |
| `QEasingCurve.InOutQuint` | `15` | ![](../img/qeasingcurve-inoutquint.png)
缓和曲线五次（T ^ 5 ）功能：加速至一半，然后再减速。 |
| `QEasingCurve.OutInQuint` | `16` | ![](../img/qeasingcurve-outinquint.png)
缓和曲线五次（T ^ 5 ）功能：减速，直到一半，然后再加速。 |
| `QEasingCurve.InSine` | `17` | ![](../img/qeasingcurve-insine.png)
缓动曲线为正弦（罪（ t））的功能：从零速度加速。 |
| `QEasingCurve.OutSine` | `18` | ![](../img/qeasingcurve-outsine.png)
缓动曲线为正弦（罪（ t））的功能：从零速度减速。 |
| `QEasingCurve.InOutSine` | `19` | ![](../img/qeasingcurve-inoutsine.png)
缓动曲线为正弦（罪（ t））的功能：加速至一半，然后再减速。 |
| `QEasingCurve.OutInSine` | `20` | ![](../img/qeasingcurve-outinsine.png)
缓动曲线为正弦（罪（ t））的功能：减速，直到一半，然后再加速。 |
| `QEasingCurve.InExpo` | `21` | ![](../img/qeasingcurve-inexpo.png)
缓和曲线的指数（ 2 ^ t）的功能：从零速度加速。 |
| `QEasingCurve.OutExpo` | `22` | ![](../img/qeasingcurve-outexpo.png)
缓和曲线的指数（ 2 ^ t）的功能：从零速度减速。 |
| `QEasingCurve.InOutExpo` | `23` | ![](../img/qeasingcurve-inoutexpo.png)
缓和曲线的指数（ 2 ^ t）的功能：加速至一半，然后再减速。 |
| `QEasingCurve.OutInExpo` | `24` | ![](../img/qeasingcurve-outinexpo.png)
缓和曲线的指数（ 2 ^ t）的功能：减速，直到一半，然后再加速。 |
| `QEasingCurve.InCirc` | `25` | ![](../img/qeasingcurve-incirc.png)
缓和曲线的圆（ SQRT （ 1 -T ^ 2 ） ）功能：从零速度加速。 |
| `QEasingCurve.OutCirc` | `26` | ![](../img/qeasingcurve-outcirc.png)
缓和曲线的圆（ SQRT （ 1 -T ^ 2 ） ）功能：从零速度减速。 |
| `QEasingCurve.InOutCirc` | `27` | ![](../img/qeasingcurve-inoutcirc.png)
缓和曲线的圆（ SQRT （ 1 -T ^ 2 ） ）功能：加速至一半，然后再减速。 |
| `QEasingCurve.OutInCirc` | `28` | ![](../img/qeasingcurve-outincirc.png)
缓和曲线的圆（ SQRT （ 1 -T ^ 2 ） ）功能：减速至一半，然后再加速。 |
| `QEasingCurve.InElastic` | `29` | ![](../img/qeasingcurve-inelastic.png)
缓和曲线的弹性（指数衰减正弦波）功能：从零速度加速。峰值幅度可与设置_amplitude_参数和衰减的通过期间_period_参数。 |
| `QEasingCurve.OutElastic` | `30` | ![](../img/qeasingcurve-outelastic.png)
缓和曲线的弹性（指数衰减正弦波）功能：从零速度减速。峰值幅度可与设置_amplitude_参数和衰减的通过期间_period_参数。 |
| `QEasingCurve.InOutElastic` | `31` | ![](../img/qeasingcurve-inoutelastic.png)
缓和曲线的弹性（指数衰减正弦波）功能：加速至一半，然后再减速。 |
| `QEasingCurve.OutInElastic` | `32` | ![](../img/qeasingcurve-outinelastic.png)
缓和曲线的弹性（指数衰减正弦波）功能：减速至一半，然后再加速。 |
| `QEasingCurve.InBack` | `33` | ![](../img/qeasingcurve-inback.png)
缓和曲线的背（过冲三次函数： （ S +1 ） * T ^ 3 - S * T ^ 2 ）缓和：从零速度加速。 |
| `QEasingCurve.OutBack` | `34` | ![](../img/qeasingcurve-outback.png)
缓和曲线的背（过冲三次函数： （ S +1 ） * T ^ 3 - S * T ^ 2 ）缓出：减速至零速度。 |
| `QEasingCurve.InOutBack` | `35` | ![](../img/qeasingcurve-inoutback.png)
缓和曲线的背（过冲三次函数： （ S +1 ） * T ^ 3 - S * T ^ 2 ）缓解输入/输出：加速，直到一半，然后再减速。 |
| `QEasingCurve.OutInBack` | `36` | ![](../img/qeasingcurve-outinback.png)
缓和曲线的背部（立方过度宽松： （ S +1 ） * T ^ 3 - S * T ^ 2 ）缓和输出/输入：减速至一半，然后再加速。 |
| `QEasingCurve.InBounce` | `37` | ![](../img/qeasingcurve-inbounce.png)
缓和曲线反弹（指数衰减的抛物线反弹）功能：从零速度加速。 |
| `QEasingCurve.OutBounce` | `38` | ![](../img/qeasingcurve-outbounce.png)
缓和曲线反弹（指数衰减的抛物线反弹）功能：从零速度减速。 |
| `QEasingCurve.InOutBounce` | `39` | ![](../img/qeasingcurve-inoutbounce.png)
缓和曲线反弹（指数衰减的抛物线反弹）功能缓解输入/输出：加速至一半，然后再减速。 |
| `QEasingCurve.OutInBounce` | `40` | ![](../img/qeasingcurve-outinbounce.png)
缓和曲线反弹（指数衰减的抛物线反弹）函数退出宽松政策/中：减速，直到一半，然后再加速。 |
| `QEasingCurve.Custom` | `45` | 如果用户指定了一个自定义的曲线类型，这是返回[setCustomType](qeasingcurve.html#setCustomType)（ ） 。请注意，您不能打电话[setType](qeasingcurve.html#setType)（ ）与该值，但[type](qeasingcurve.html#type)（ ）可以返回它。 |

* * *

## Method Documentation

```
QEasingCurve.__init__ (self, Type type = QEasingCurve.Linear)
```

构造给定的缓动曲线_type_。

```
QEasingCurve.__init__ (self, QEasingCurve other)
```

构建副本_other_。

```
float QEasingCurve.amplitude (self)
```

返回的幅度。这并不适用于所有类型的曲线。它仅适用于弹跳和弹性曲线曲线（[type](qeasingcurve.html#type)（ ）[QEasingCurve.InBounce](qeasingcurve.html#Type-enum)，[QEasingCurve.OutBounce](qeasingcurve.html#Type-enum)，[QEasingCurve.InOutBounce](qeasingcurve.html#Type-enum)，[QEasingCurve.OutInBounce](qeasingcurve.html#Type-enum)，[QEasingCurve.InElastic](qeasingcurve.html#Type-enum)，[QEasingCurve.OutElastic](qeasingcurve.html#Type-enum)，[QEasingCurve.InOutElastic](qeasingcurve.html#Type-enum) or [QEasingCurve.OutInElastic](qeasingcurve.html#Type-enum)） 。

**See also** [setAmplitude](qeasingcurve.html#setAmplitude)（ ） 。

```
callable QEasingCurve.customType (self)
```

返回的函数指针的定义缓动曲线。如果[type](qeasingcurve.html#type)（ ）不返回[QEasingCurve.Custom](qeasingcurve.html#Type-enum)，这个函数将返回0 。

**See also** [setCustomType](qeasingcurve.html#setCustomType)（ ） 。

```
float QEasingCurve.overshoot (self)
```

返回过冲。这并不适用于所有类型的曲线。它仅适用[type](qeasingcurve.html#type)（）是[QEasingCurve.InBack](qeasingcurve.html#Type-enum)，[QEasingCurve.OutBack](qeasingcurve.html#Type-enum)，[QEasingCurve.InOutBack](qeasingcurve.html#Type-enum) or [QEasingCurve.OutInBack](qeasingcurve.html#Type-enum)。

**See also** [setOvershoot](qeasingcurve.html#setOvershoot)（ ） 。

```
float QEasingCurve.period (self)
```

返回的时间。这并不适用于所有类型的曲线。它仅适用[type](qeasingcurve.html#type)（）是[QEasingCurve.InElastic](qeasingcurve.html#Type-enum)，[QEasingCurve.OutElastic](qeasingcurve.html#Type-enum)，[QEasingCurve.InOutElastic](qeasingcurve.html#Type-enum) or [QEasingCurve.OutInElastic](qeasingcurve.html#Type-enum)。

**See also** [setPeriod](qeasingcurve.html#setPeriod)（ ） 。

```
QEasingCurve.setAmplitude (self, float amplitude)
```

设定的幅度以_amplitude_。

这将设置反弹或弹性“弹簧”效应振幅的振幅。该数字越高，则振幅为高。

**See also** [amplitude](qeasingcurve.html#amplitude)（ ） 。

```
QEasingCurve.setCustomType (self, callable func)
```

设置由用户在函数定义的自定义缓动曲线_func_。该函数的签名是QREAL myEasingFunction （ QREAL进步），其中_progress_和返回值被认为是0和1之间被归一化。 （在某些情况下的返回值可以是在那个范围外）调用此函数之后[type](qeasingcurve.html#type)（ ）将返回[QEasingCurve.Custom](qeasingcurve.html#Type-enum)。_func_不能为零。

**See also** [customType](qeasingcurve.html#customType)（）和[valueForProgress](qeasingcurve.html#valueForProgress)（ ） 。

```
QEasingCurve.setOvershoot (self, float overshoot)
```

设置超调量_overshoot_。

0不产生过冲，以及1.70158默认值会产生10％的过冲。

**See also** [overshoot](qeasingcurve.html#overshoot)（ ） 。

```
QEasingCurve.setPeriod (self, float period)
```

设置期间_period_。设置一个小的时间值将赋予曲线的高频。一个大周期将会给它一个小的频率。

**See also** [period](qeasingcurve.html#period)（ ） 。

```
QEasingCurve.setType (self, Type type)
```

设置缓和曲线的类型_type_。

**See also** [type](qeasingcurve.html#type)（ ） 。

```
Type QEasingCurve.type (self)
```

[

返回缓和曲线的类型。

](qeasingcurve.html#Type-enum)

[**See also**](qeasingcurve.html#Type-enum) [setType](qeasingcurve.html#setType)（ ） 。

```
float QEasingCurve.valueForProgress (self, float progress)
```

在返回的缓动曲线的有效进展_progress_。而_progress_必须在0和1之间，返回的有效进展可以是那些界限之外。例如，[QEasingCurve.InBack](qeasingcurve.html#Type-enum)将在函数开头返回负值。

```
bool QEasingCurve.__eq__ (self, QEasingCurve other)
```

```
bool QEasingCurve.__ne__ (self, QEasingCurve other)
```