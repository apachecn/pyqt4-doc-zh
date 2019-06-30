# QGraphicsItemAnimation Class Reference

## [[QtGui](index.htm) module]

该QGraphicsItemAnimation类提供了简单的动画支持[QGraphicsItem](qgraphicsitem.html)。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `afterAnimationStep (self, float step)`
*   `beforeAnimationStep (self, float step)`
*   `clear (self)`
*   `float horizontalScaleAt (self, float step)`
*   `float horizontalShearAt (self, float step)`
*   `QGraphicsItem item (self)`
*   `QMatrix matrixAt (self, float step)`
*   `QPointF posAt (self, float step)`
*   `list-of-tuple-of-float-QPointF posList (self)`
*   `reset (self)`
*   `float rotationAt (self, float step)`
*   `list-of-tuple-of-float-float rotationList (self)`
*   `list-of-tuple-of-float-QPointF scaleList (self)`
*   `setItem (self, QGraphicsItem item)`
*   `setPosAt (self, float step, QPointF pos)`
*   `setRotationAt (self, float step, float angle)`
*   `setScaleAt (self, float step, float sx, float sy)`
*   `setShearAt (self, float step, float sh, float sv)`
*   `setStep (self, float x)`
*   `setTimeLine (self, QTimeLine timeLine)`
*   `setTranslationAt (self, float step, float dx, float dy)`
*   `list-of-tuple-of-float-QPointF shearList (self)`
*   `QTimeLine timeLine (self)`
*   `list-of-tuple-of-float-QPointF translationList (self)`
*   `float verticalScaleAt (self, float step)`
*   `float verticalShearAt (self, float step)`
*   `float xTranslationAt (self, float step)`
*   `float yTranslationAt (self, float step)`

* * *

## Detailed Description

该QGraphicsItemAnimation类提供了简单的动画支持[QGraphicsItem](qgraphicsitem.html)。

该QGraphicsItemAnimation类一个动画[QGraphicsItem](qgraphicsitem.html)。您可以在指定的步骤安排变更项目的变换矩阵。该QGraphicsItemAnimation类具有电流步长值。当这个值改变安排在该步骤的转换执行。动画的当前步骤设置与`setStep()`功能。

QGraphicsItemAnimation会做一个简单的线性插值最邻近的预定变化的计算矩阵。例如，如果你设置为值0.0和1.0的项目的位置，动画会显示该项目活动在这些位置之间的直线。同样是真实的缩放和旋转。

这是通常使用的类与[QTimeLine](qtimeline.html)。时间轴的[valueChanged()](qtimeline.html#valueChanged)信号，然后连接到`setStep()`插槽。例如，您可以设置旋转的项目通过调用`setRotationAt()`针对不同的步长值。动画时间轴设定与[setTimeLine](qgraphicsitemanimation.html#setTimeLine)（）函数。

一个例子动画时间轴如下：

```
     [QGraphicsItem](qgraphicsitem.html) *ball = new [QGraphicsEllipseItem](qgraphicsellipseitem.html)(0, 0, 20, 20);

     [QTimeLine](qtimeline.html) *timer = new [QTimeLine](qtimeline.html)(5000);
     timer->setFrameRange(0, 100);

     QGraphicsItemAnimation *animation = new QGraphicsItemAnimation;
     animation->setItem(ball);
     animation->setTimeLine(timer);

     for (int i = 0; i < 200; ++i)
         animation->setPosAt(i / 200.0, [QPointF](qpointf.html)(i, i));

     [QGraphicsScene](qgraphicsscene.html) *scene = new [QGraphicsScene](qgraphicsscene.html)();
     scene->setSceneRect(0, 0, 250, 250);
     scene->addItem(ball);

     [QGraphicsView](qgraphicsview.html) *view = new [QGraphicsView](qgraphicsview.html)(scene);
     view->show();

     timer->start();

```

注意，步骤在于在0.0和1.0之间。可能有必要使用[setUpdateInterval()](qtimeline.html#updateInterval-prop)。默认的更新间隔为40毫秒。当一个预定的改造不能被删除，所以安排在同一步骤同一种（例如，旋转）的几个转变，不推荐。

* * *

## Method Documentation

```
QGraphicsItemAnimation.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个动画对象与给定_parent_。

```
QGraphicsItemAnimation.afterAnimationStep (self, float step)
```

这个方法是在需要一个新的台阶已经发生之后执行额外的代码子类重写。动画_step_提供了一种用于使用的情况下的操作取决于它的值。

```
QGraphicsItemAnimation.beforeAnimationStep (self, float step)
```

这个方法是由子类需要执行额外的代码了新的一步发生之前被复盖。动画_step_提供了一种用于使用的情况下的操作取决于它的值。

```
QGraphicsItemAnimation.clear (self)
```

清除用于动画预定转换，但保留的项目和时间安排。

```
float QGraphicsItemAnimation.horizontalScaleAt (self, float step)
```

返回水平规模的项目在指定的_step_值。

**See also** [setScaleAt](qgraphicsitemanimation.html#setScaleAt)（ ） 。

```
float QGraphicsItemAnimation.horizontalShearAt (self, float step)
```

返回水平剪切的项目在指定的_step_值。

**See also** [setShearAt](qgraphicsitemanimation.html#setShearAt)（ ） 。

```
QGraphicsItem QGraphicsItemAnimation.item (self)
```

[

返回动画对象所操作的项目。

](qgraphicsitem.html)

[**See also**](qgraphicsitem.html) [setItem](qgraphicsitemanimation.html#setItem)（ ） 。

```
QMatrix QGraphicsItemAnimation.matrixAt (self, float step)
```

[

返回用于改造项目在指定的矩阵_step_值。

](qmatrix.html)

```
QPointF QGraphicsItemAnimation.posAt (self, float step)
```

[

返回在给定项目的位置_step_值。

](qpointf.html)

[**See also**](qpointf.html) [setPosAt](qgraphicsitemanimation.html#setPosAt)（ ） 。

```
list-of-tuple-of-float-QPointF QGraphicsItemAnimation.posList (self)
```

返回所有显式地插入位置。

**See also** [posAt](qgraphicsitemanimation.html#posAt)（）和[setPosAt](qgraphicsitemanimation.html#setPosAt)（ ） 。

```
QGraphicsItemAnimation.reset (self)
```

这种方法也是一个Qt槽与C + +的签名`void reset()`。

```
float QGraphicsItemAnimation.rotationAt (self, float step)
```

返回在该项目旋转指定的角度_step_值。

**See also** [setRotationAt](qgraphicsitemanimation.html#setRotationAt)（ ） 。

```
list-of-tuple-of-float-float QGraphicsItemAnimation.rotationList (self)
```

返回所有显式地插入旋转。

**See also** [rotationAt](qgraphicsitemanimation.html#rotationAt)（）和[setRotationAt](qgraphicsitemanimation.html#setRotationAt)（ ） 。

```
list-of-tuple-of-float-QPointF QGraphicsItemAnimation.scaleList (self)
```

返回所有显式地插入尺度。

**See also** [verticalScaleAt](qgraphicsitemanimation.html#verticalScaleAt)（ ）[horizontalScaleAt](qgraphicsitemanimation.html#horizontalScaleAt)（）和[setScaleAt](qgraphicsitemanimation.html#setScaleAt)（ ） 。

```
QGraphicsItemAnimation.setItem (self, QGraphicsItem item)
```

设置指定_item_在动画中使用。

**See also** [item](qgraphicsitemanimation.html#item)（ ） 。

```
QGraphicsItemAnimation.setPosAt (self, float step, QPointF pos)
```

设置在给定项目的位置_step_值到_point_规定。

**See also** [posAt](qgraphicsitemanimation.html#posAt)（ ） 。

```
QGraphicsItemAnimation.setRotationAt (self, float step, float angle)
```

设置项的旋转在给定的_step_值到_angle_规定。

**See also** [rotationAt](qgraphicsitemanimation.html#rotationAt)（ ） 。

```
QGraphicsItemAnimation.setScaleAt (self, float step, float sx, float sy)
```

设置项的比例在给定的_step_重视使用由指定的水平和垂直缩放因子_sx_和_sy_。

**See also** [verticalScaleAt](qgraphicsitemanimation.html#verticalScaleAt)（）和[horizontalScaleAt](qgraphicsitemanimation.html#horizontalScaleAt)（ ） 。

```
QGraphicsItemAnimation.setShearAt (self, float step, float sh, float sv)
```

设置项的剪切在给定的_step_值通过使用指定的水平和垂直切变的因素_sh_和_sv_。

**See also** [verticalShearAt](qgraphicsitemanimation.html#verticalShearAt)（）和[horizontalShearAt](qgraphicsitemanimation.html#horizontalShearAt)（ ） 。

```
QGraphicsItemAnimation.setStep (self, float x)
```

这种方法也是一个Qt槽与C + +的签名`void setStep(qreal)`。

设置当前_step_价值为动画，引起预定在该步骤中要进行的变换。

```
QGraphicsItemAnimation.setTimeLine (self, QTimeLine timeLine)
```

设置用来控制动画的速度时间轴对象_timeLine_规定。

**See also** [timeLine](qgraphicsitemanimation.html#timeLine)（ ） 。

```
QGraphicsItemAnimation.setTranslationAt (self, float step, float dx, float dy)
```

设置项的翻译在给定的_step_值使用由指定的水平和垂直坐标_dx_和_dy_。

**See also** [xTranslationAt](qgraphicsitemanimation.html#xTranslationAt)（）和[yTranslationAt](qgraphicsitemanimation.html#yTranslationAt)（ ） 。

```
list-of-tuple-of-float-QPointF QGraphicsItemAnimation.shearList (self)
```

返回所有显式地插入剪。

**See also** [verticalShearAt](qgraphicsitemanimation.html#verticalShearAt)（ ）[horizontalShearAt](qgraphicsitemanimation.html#horizontalShearAt)（）和[setShearAt](qgraphicsitemanimation.html#setShearAt)（ ） 。

```
QTimeLine QGraphicsItemAnimation.timeLine (self)
```

[

返回用于控制在该动画的发生率在时间轴对象。

](qtimeline.html)

[**See also**](qtimeline.html) [setTimeLine](qgraphicsitemanimation.html#setTimeLine)（ ） 。

```
list-of-tuple-of-float-QPointF QGraphicsItemAnimation.translationList (self)
```

返回所有显式地插入翻译。

**See also** [xTranslationAt](qgraphicsitemanimation.html#xTranslationAt)（ ）[yTranslationAt](qgraphicsitemanimation.html#yTranslationAt)（）和[setTranslationAt](qgraphicsitemanimation.html#setTranslationAt)（ ） 。

```
float QGraphicsItemAnimation.verticalScaleAt (self, float step)
```

返回该项目的垂直刻度在指定_step_值。

**See also** [setScaleAt](qgraphicsitemanimation.html#setScaleAt)（ ） 。

```
float QGraphicsItemAnimation.verticalShearAt (self, float step)
```

返回该项目的垂直切变在指定_step_值。

**See also** [setShearAt](qgraphicsitemanimation.html#setShearAt)（ ） 。

```
float QGraphicsItemAnimation.xTranslationAt (self, float step)
```

返回该项目的翻译水平在指定的_step_值。

**See also** [setTranslationAt](qgraphicsitemanimation.html#setTranslationAt)（ ） 。

```
float QGraphicsItemAnimation.yTranslationAt (self, float step)
```

返回的项的竖直平移在指定_step_值。

**See also** [setTranslationAt](qgraphicsitemanimation.html#setTranslationAt)（ ） 。