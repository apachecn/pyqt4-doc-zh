# QVariantAnimation Class Reference

## [[QtCore](index.htm) module]

该QVariantAnimation类提供了动画的抽象基类。[More...](#details)

继承[QAbstractAnimation](qabstractanimation.html)。

通过继承[QPropertyAnimation](qpropertyanimation.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QVariant currentValue (self)`
*   `int duration (self)`
*   `QEasingCurve easingCurve (self)`
*   `QVariant endValue (self)`
*   `bool event (self, QEvent event)`
*   `QVariant interpolated (self, QVariant from, QVariant to, float progress)`
*   `QVariant keyValueAt (self, float step)`
*   `list-of-tuple-of-float-QVariant keyValues (self)`
*   `setDuration (self, int msecs)`
*   `setEasingCurve (self, QEasingCurve easing)`
*   `setEndValue (self, QVariant value)`
*   `setKeyValueAt (self, float step, QVariant value)`
*   `setKeyValues (self, list-of-tuple-of-float-QVariant values)`
*   `setStartValue (self, QVariant value)`
*   `QVariant startValue (self)`
*   `updateCurrentTime (self, int)`
*   `updateCurrentValue (self, QVariant value)`
*   `updateState (self, QAbstractAnimation.State newState, QAbstractAnimation.State oldState)`

### Qt Signals

*   `void valueChanged (const QVariant&)`

* * *

## Detailed Description

该QVariantAnimation类提供了动画的抽象基类。

这个类是一部分[The Animation Framework](index.htm)。它可以作为财产和物品的动画一个基类，与共享的功能函数。

QVariantAnimation不能直接使用，因为它是一个抽象类，它有一个叫做纯虚方法[updateCurrentValue](qvariantanimation.html#updateCurrentValue)（ ） 。这个类在执行插值[QVariant](qvariant.html)秒，但保留使用插值到其子类。目前， Qt提供[QPropertyAnimation](qpropertyanimation.html)，这动画的Qt[properties](index.htm#qt-s-property-system)。请参阅[QPropertyAnimation](qpropertyanimation.html)类描述，如果您希望进行动画该等物业。

然后，您可以通过调用设置该属性开始和结束值[setStartValue](qvariantanimation.html#startValue-prop)（）和[setEndValue](qvariantanimation.html#endValue-prop)（ ） ，最后调用[start](qabstractanimation.html#start)（）来启动动画。 QVariantAnimation将插在目标对象的属性，放出[valueChanged](qvariantanimation.html#valueChanged)（ ） 。反应在电流值的变化，你必须重新实现[updateCurrentValue](qvariantanimation.html#updateCurrentValue)（ ）虚函数。

另外，也可以在位于起始和结束值之间规定的步骤来设定值。那么插值会触及这些点在指定的步骤。注意，开始和结束的值在0.0和1.0中定义的键值。

有两种方式会影响QVariantAnimation如何插值的值。你可以通过调用设置缓动曲线[setEasingCurve](qvariantanimation.html#easingCurve-prop)（ ） ，并配置持续时间通过调用[setDuration](qvariantanimation.html#duration-prop)（ ） 。您可以更改的[QVariants](index.htm#qvariants)通过创建QVariantAnimation的子类，并重新实现虚拟内插[interpolated](qvariantanimation.html#interpolated)（）函数。

子类QVariantAnimation可以是一个选择，如果你有[QVariant](qvariant.html)s表示你不希望声明为Qt的属性。但请注意，您在大多数情况下会有所改善您的声明[QVariant](qvariant.html)作为一个属性。

不是所有的[QVariant](qvariant.html)类型的支持。下面是当前支持的列表[QVariant](qvariant.html)类型：

*   [Int](qmetatype.html#Type-enum)
*   [Double](qmetatype.html#Type-enum)
*   [Float](qmetatype.html#Type-enum)
*   [QLine](qmetatype.html#Type-enum)
*   [QLineF](qmetatype.html#Type-enum)
*   [QPoint](qmetatype.html#Type-enum)
*   [QPointF](qmetatype.html#Type-enum)
*   [QSize](qmetatype.html#Type-enum)
*   [QSizeF](qmetatype.html#Type-enum)
*   [QRect](qmetatype.html#Type-enum)
*   [QRectF](qmetatype.html#Type-enum)
*   [QColor](qmetatype.html#Type-enum)

如果您需要进行插值其它不同的类型，包括自定义类型，你必须实现插值为这些自己。要做到这一点，你可以为一个给定类型注册一个插补功能。这个函数有3个参数：起始值，结束值和目前的进展。

例如：

```
 [QVariant](qvariant.html) myColorInterpolator(const [QColor](qcolor.html) &start, const [QColor](qcolor.html) &end, [qreal](index.htm#qreal-typedef) progress)
 {
     ...
     return [QColor](qcolor.html)(...);
 }
 ...
 qRegisterAnimationInterpolator<[QColor](qcolor.html)>(myColorInterpolator);

```

另一种选择是重新实现[interpolated](qvariantanimation.html#interpolated)（ ），它返回插补值进行插补值。

* * *

## Method Documentation

```
QVariantAnimation.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构建[QVariantAnimation](qvariantanimation.html)对象。_parent_被传递给[QAbstractAnimation](qabstractanimation.html)的构造。

```
QVariant QVariantAnimation.currentValue (self)
```

```
int QVariantAnimation.duration (self)
```

```
QEasingCurve QVariantAnimation.easingCurve (self)
```

[

```
QVariant QVariantAnimation.endValue (self)
```

```
bool QVariantAnimation.event (self, QEvent event)
```

](qeasingcurve.html)

[从重新实现](qeasingcurve.html)[QObject.event](qobject.html#event)（ ） 。

```
QVariant QVariantAnimation.interpolated (self, QVariant from, QVariant to, float progress)
```

这个虚函数返回变体之间的线性插值_from_和_to_在_progress_， 0和1之间，通常的值。您可以在子类中重新实现这个功能[QVariantAnimation](qvariantanimation.html)提供自己的插值算法。

需要注意的是，为了使内插至一个工作[QEasingCurve](qeasingcurve.html)返回一个值大于0小于1 （如更小或更大[QEasingCurve.InBack](qeasingcurve.html#Type-enum)），你应该确保它能够推断。如果数据类型的语义不容许外推这个功能应该处理的优雅。

你应该调用[QVariantAnimation](qvariantanimation.html)如果你想让你的类来处理已经支持Qt的类型实现此功能（见类[QVariantAnimation](qvariantanimation.html)说明支持的类型的列表） 。

**See also** [QEasingCurve](qeasingcurve.html)。

```
QVariant QVariantAnimation.keyValueAt (self, float step)
```

返回关键帧值给定的_step_。给定_step_必须是范围为0到1。如果不存在[KeyValue](qvariantanimation.html#KeyValue-typedef)为_step_，它返回一个无效的[QVariant](qvariant.html)。

**See also** [keyValues](qvariantanimation.html#keyValues)（）和[setKeyValueAt](qvariantanimation.html#setKeyValueAt)（ ） 。

```
list-of-tuple-of-float-QVariant QVariantAnimation.keyValues (self)
```

返回此动画的关键帧。

**See also** [keyValueAt](qvariantanimation.html#keyValueAt)（）和[setKeyValues](qvariantanimation.html#setKeyValues)（ ） 。

```
QVariantAnimation.setDuration (self, int msecs)
```

```
QVariantAnimation.setEasingCurve (self, QEasingCurve easing)
```

```
QVariantAnimation.setEndValue (self, QVariant value)
```

```
QVariantAnimation.setKeyValueAt (self, float step, QVariant value)
```

创建一个关键帧在给定的_step_用给定的_value_。给定_step_必须是范围为0到1。

**See also** [setKeyValues](qvariantanimation.html#setKeyValues)（）和[keyValueAt](qvariantanimation.html#keyValueAt)（ ） 。

```
QVariantAnimation.setKeyValues (self, list-of-tuple-of-float-QVariant values)
```

替换当前设置关键帧与给定_keyValues_。的关键帧的步骤必须在范围0到1。

**See also** [keyValues](qvariantanimation.html#keyValues)（）和[keyValueAt](qvariantanimation.html#keyValueAt)（ ） 。

```
QVariantAnimation.setStartValue (self, QVariant value)
```

```
QVariant QVariantAnimation.startValue (self)
```

```
QVariantAnimation.updateCurrentTime (self, int)
```

从重新实现[QAbstractAnimation.updateCurrentTime](qabstractanimation.html#updateCurrentTime)（ ） 。

```
QVariantAnimation.updateCurrentValue (self, QVariant value)
```

这种方法是抽象的，应在任何子类中重新实现。

这个纯虚函数被调用每次动画的当前值的变化。该_value_参数是新的当前值。

**See also** [currentValue](qvariantanimation.html#currentValue-prop)。

```
QVariantAnimation.updateState (self, QAbstractAnimation.State newState, QAbstractAnimation.State oldState)
```

从重新实现[QAbstractAnimation.updateState](qabstractanimation.html#updateState)（ ） 。

* * *

## Qt Signal Documentation

```
void valueChanged (const QVariant&)
```

这是该信号的默认超载。

[QVariantAnimation](qvariantanimation.html)发出这个信号时的当前_value_变化。

**See also** [currentValue](qvariantanimation.html#currentValue-prop)，[startValue](qvariantanimation.html#startValue-prop)和[endValue](qvariantanimation.html#endValue-prop)。