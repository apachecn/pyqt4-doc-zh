# QGraphicsTransform Class Reference

## [[QtGui](index.htm) module]

该QGraphicsTransform类是对QGraphicsItems建设先进变换的抽象基类。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QGraphicsRotation](qgraphicsrotation.html)和[QGraphicsScale](qgraphicsscale.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `applyTo (self, QMatrix4x4 matrix)`
*   `update (self)`

* * *

## Detailed Description

该QGraphicsTransform类是对QGraphicsItems建设先进变换的抽象基类。

作为替代QGraphicsItem.transform ， QGraphicsTransform允许您创建和控制，可以独立使用专门的属性进行配置先进的转换。

[QGraphicsItem](qgraphicsitem.html)可以让你任意数量的QGraphicsTransform实例分配给一个[QGraphicsItem](qgraphicsitem.html)。每个QGraphicsTransform是为了，一次一个应用，该[QGraphicsItem](qgraphicsitem.html)它赋值。

QGraphicsTransform是用于动画特别有用。而[QGraphicsItem.setTransform](qgraphicsitem.html#setTransform)（）让你指定的任何直接转化为一个项目，没有直接的方法（两种状态，分别用于该项目具有不同的任意变换分配之间转换时如）两种不同的转换之间进行插值。使用QGraphicsTransform可以插各独立转化​​的属性值。然后将得到的操作被组合成一个单一的变换被应用到[QGraphicsItem](qgraphicsitem.html)。

转换使用的是计算在真实的三维空间[QMatrix4x4](qmatrix4x4.html)。当该变换被应用到一个[QGraphicsItem](qgraphicsitem.html)时，将投射返回到2D[QTransform](qtransform.html)。当多个QGraphicsTransform对象被施加到一个[QGraphicsItem](qgraphicsitem.html)，所有的变革都计算在真正的3D空间中，与投影回2D只有最后QGraphicsTransform应用后发生。唯一的例外是[QGraphicsRotation](qgraphicsrotation.html)，突出回2D之后每次旋转以保持围绕X的立体效果和Y轴。

如果你想创建自己的配置的转变，您可以创建QGraphicsTransform的子类（或任何或现有的子类） ，并重新实现纯虚[applyTo](qgraphicstransform.html#applyTo)（ ）函数，它接受一个指向[QMatrix4x4](qmatrix4x4.html)。每个操作你想申请应当公开为属性（例如， customTransform - \u003e setVerticalShear （ 2.5 ） ） 。里面你重新实现[applyTo](qgraphicstransform.html#applyTo)（ ） ，你可以修改所提供的变换分别。

QGraphicsTransform可以一起使用[QGraphicsItem.setTransform](qgraphicsitem.html#setTransform)（ ）[QGraphicsItem.setRotation](qgraphicsitem.html#setRotation)（）和[QGraphicsItem.setScale](qgraphicsitem.html#setScale)（ ） 。

* * *

## Method Documentation

```
QGraphicsTransform.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QGraphicsTransform](qgraphicstransform.html)用给定的_parent_。

```
QGraphicsTransform.applyTo (self, QMatrix4x4 matrix)
```

这种方法是抽象的，应在任何子类中重新实现。

这个纯虚方法在派生类中被重新实现。

它适用于这种转型_matrix_。

**See also** [QGraphicsItem.transform](qgraphicsitem.html#transform)（）和[QMatrix4x4.toTransform](qmatrix4x4.html#toTransform)（ ） 。

```
QGraphicsTransform.update (self)
```

这种方法也是一个Qt槽与C + +的签名`void update()`。

通知此转换操作已改变其参数，这样的方式[applyTo](qgraphicstransform.html#applyTo)（ ）会返回不同的结果比以前。

当实施你自己的自定义图形的变换，你必须在每次调用这个函数，你改变一个参数，让[QGraphicsItem](qgraphicsitem.html)知道它的变换需要被更新。

**See also** [applyTo](qgraphicstransform.html#applyTo)（ ） 。