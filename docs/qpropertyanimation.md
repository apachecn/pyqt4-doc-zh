# QPropertyAnimation Class Reference

## [[QtCore](index.htm) module]

该QPropertyAnimation类动画Qt的属性[More...](#details)

继承[QVariantAnimation](qvariantanimation.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QObject target, QByteArray propertyName, QObject parent = None)`
*   `bool event (self, QEvent event)`
*   `QByteArray propertyName (self)`
*   `setPropertyName (self, QByteArray propertyName)`
*   `setTargetObject (self, QObject target)`
*   `QObject targetObject (self)`
*   `updateCurrentValue (self, QVariant value)`
*   `updateState (self, QAbstractAnimation.State newState, QAbstractAnimation.State oldState)`

* * *

## Detailed Description

该QPropertyAnimation类动画Qt的属性

QPropertyAnimation插过[Qt properties](index.htm#qt-s-property-system)。作为属性值被存储在[QVariant](qvariant.html)s时，类继承[QVariantAnimation](qvariantanimation.html)，并支持相同的动画[variant types](qvariant.html#Type-enum)作为它的超类。

一个类声明的属性必须是一个[QObject](qobject.html)。为了能够对属性进行动画，它必须提供一个setter （这样QPropertyAnimation可以设置该属性的值） 。请注意，这使得它可以制作动画的许多Qt的部件。让我们来看一个例子：

```
 QPropertyAnimation *animation = new QPropertyAnimation(myWidget, "geometry");
 animation->setDuration(10000);
 animation->setStartValue([QRect](qrect.html)(0, 0, 100, 30));
 animation->setEndValue([QRect](qrect.html)(250, 250, 100, 30));

 animation->start();

```

属性名和[QObject](qobject.html)例如其中的属性应该是动画传递给构造函数。然后，您可以指定属性的开始和结束值。该过程是相等的，您已经实现自己的类的属性 - 只是检查与[QVariantAnimation](qvariantanimation.html)您[QVariant](qvariant.html)被支持的类型。

该[QVariantAnimation](qvariantanimation.html)类的描述解释了如何设置动画的细节。但是请注意，如果一开始未设定值，该属性将开始在它有创建QPropertyAnimation实例时的值。

QPropertyAnimation就像对自己的魅力。对于复杂的动画，例如，包含多个对象，[QAnimationGroup](qanimationgroup.html)提供。动画组是一个可以包含其他动画的动画，并且可以管理其时的动画播放。看[QParallelAnimationGroup](qparallelanimationgroup.html)的一个例子。

* * *

## Method Documentation

```
QPropertyAnimation.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构建[QPropertyAnimation](qpropertyanimation.html)对象。_parent_被传递给[QObject](qobject.html)的构造。

```
QPropertyAnimation.__init__ (self, QObject target, QByteArray propertyName, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构建[QPropertyAnimation](qpropertyanimation.html)对象。_parent_被传递给[QObject](qobject.html)的构造。动画更改属性_propertyName_上_target_。默认的持续时间为250ms 。

**See also** [targetObject](qpropertyanimation.html#targetObject-prop)和[propertyName](qpropertyanimation.html#propertyName-prop)。

```
bool QPropertyAnimation.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QByteArray QPropertyAnimation.propertyName (self)
```

[

```
QPropertyAnimation.setPropertyName (self, QByteArray propertyName)
```

```
QPropertyAnimation.setTargetObject (self, QObject target)
```

](qbytearray.html)

```
QObject QPropertyAnimation.targetObject (self)
```

[

```
QPropertyAnimation.updateCurrentValue (self, QVariant value)
```

](qobject.html)

[从重新实现](qobject.html)[QVariantAnimation.updateCurrentValue](qvariantanimation.html#updateCurrentValue)（ ） 。

这个虚函数被调用[QVariantAnimation](qvariantanimation.html)每当电流值的变化。_value_是新的，更新后的值。它更新的目标对象上的属性的当前值。

**See also** [currentValue](qvariantanimation.html#currentValue-prop)和[currentTime](qabstractanimation.html#currentTime-prop)。

```
QPropertyAnimation.updateState (self, QAbstractAnimation.State newState, QAbstractAnimation.State oldState)
```

从重新实现[QAbstractAnimation.updateState](qabstractanimation.html#updateState)（ ） 。

如果[startValue](qvariantanimation.html#startValue-prop)没有定义时，从停止到运行的动画变化的状态，当前的属性值作为动画的初始值。