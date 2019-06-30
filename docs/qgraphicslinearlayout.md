# QGraphicsLinearLayout Class Reference

## [[QtGui](index.htm) module]

该QGraphicsLinearLayout类提供了在图形视图管理部件的水平或垂直布局。[More...](#details)

继承[QGraphicsLayout](qgraphicslayout.html)。

### Methods

*   `__init__ (self, QGraphicsLayoutItem parent = None)`
*   `__init__ (self, Qt.Orientation orientation, QGraphicsLayoutItem parent = None)`
*   `addItem (self, QGraphicsLayoutItem item)`
*   `addStretch (self, int stretch = 1)`
*   `Qt.Alignment alignment (self, QGraphicsLayoutItem item)`
*   `int count (self)`
*   `insertItem (self, int index, QGraphicsLayoutItem item)`
*   `insertStretch (self, int index, int stretch = 1)`
*   `invalidate (self)`
*   `QGraphicsLayoutItem itemAt (self, int index)`
*   `float itemSpacing (self, int index)`
*   `Qt.Orientation orientation (self)`
*   `removeAt (self, int index)`
*   `removeItem (self, QGraphicsLayoutItem item)`
*   `setAlignment (self, QGraphicsLayoutItem item, Qt.Alignment alignment)`
*   `setGeometry (self, QRectF rect)`
*   `setItemSpacing (self, int index, float spacing)`
*   `setOrientation (self, Qt.Orientation orientation)`
*   `setSpacing (self, float spacing)`
*   `setStretchFactor (self, QGraphicsLayoutItem item, int stretch)`
*   `QSizeF sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())`
*   `float spacing (self)`
*   `int stretchFactor (self, QGraphicsLayoutItem item)`

* * *

## Detailed Description

该QGraphicsLinearLayout类提供了在图形视图管理部件的水平或垂直布局。

的默认方向的线性布局[Qt.Horizontal](qt.html#Orientation-enum)。你可以通过调用选择垂直方向或者[setOrientation](qgraphicslinearlayout.html#setOrientation)（），或者通过使[Qt.Vertical](qt.html#Orientation-enum)到QGraphicsLinearLayout的构造函数。

使用QGraphicsLinearLayout最常用的方法是通过调用构造一个对象在堆中，没有父母，添加控件和布局[addItem](qgraphicslinearlayout.html#addItem)（） ，最后是布局呼叫分配给一个小部件[QGraphicsWidget.setLayout](qgraphicswidget.html#layout-prop)（ ） 。

```
 [QGraphicsScene](qgraphicsscene.html) scene;
 [QGraphicsWidget](qgraphicswidget.html) *textEdit = scene.addWidget(new [QTextEdit](qtextedit.html));
 [QGraphicsWidget](qgraphicswidget.html) *pushButton = scene.addWidget(new [QPushButton](qpushbutton.html));

 QGraphicsLinearLayout *layout = new QGraphicsLinearLayout;
 layout->addItem(textEdit);
 layout->addItem(pushButton);

 [QGraphicsWidget](qgraphicswidget.html) *form = new [QGraphicsWidget](qgraphicswidget.html);
 form->setLayout(layout);
 scene.addItem(form);

```

您可以添加小部件，布局，延伸（[addStretch](qgraphicslinearlayout.html#addStretch)（ ）[insertStretch](qgraphicslinearlayout.html#insertStretch)（）或[setStretchFactor](qgraphicslinearlayout.html#setStretchFactor)（）），和间隔（[setItemSpacing](qgraphicslinearlayout.html#setItemSpacing)（ ）），以线性布局。布局需要的物品的所有权。在某些情况下，当项目的布局也继承自[QGraphicsItem](qgraphicsitem.html)（如[QGraphicsWidget](qgraphicswidget.html)）会有因为布局项目属于两个层次的所有权所有权的模糊性。看到的文档[QGraphicsLayoutItem.setOwnedByLayout](qgraphicslayoutitem.html#setOwnedByLayout)（ ）如何处理这个问题。你可以通过调用访问布局每个项目[count](qgraphicslinearlayout.html#count)（）和[itemAt](qgraphicslinearlayout.html#itemAt)（ ） 。调用[removeAt](qgraphicslinearlayout.html#removeAt)（）或[removeItem](qgraphicslinearlayout.html#removeItem)（ ）会从布局中删除某个项目，而不破坏它。

### Size Hints and Size Policies in QGraphicsLinearLayout

QGraphicsLinearLayout尊重每个项目的大小提示和大小政策，并在布局包含了更多的空间比中的项目可以填写，每个项目是根据该项目的布局的对齐方式排列。你可以通过调用设置每个项目的对齐方式[setAlignment](qgraphicslinearlayout.html#setAlignment)（ ） ，并通过调用检查对齐任何项目[alignment](qgraphicslinearlayout.html#alignment)（ ） 。默认情况下，项目是一致的左上角。

### Spacing within QGraphicsLinearLayout

项目之间的布局分配一些空间。空间的实际大小取决于管理widget的当前样式，但共同的间距为4 。您也可以设定自己的间距致电[setSpacing](qgraphicslinearlayout.html#setSpacing)（ ） ，并通过调用获取当前的间距值[spacing](qgraphicslinearlayout.html#spacing)（ ） 。如果要配置单独的间距为你的项目，你可以调用[setItemSpacing](qgraphicslinearlayout.html#setItemSpacing)（ ） 。

### Stretch Factor in QGraphicsLinearLayout

您可以指定一个拉伸因子在每个项目控制多少空间，它会得到比其他项目。默认情况下，布置成线性布置两个相同的部件将具有相同的大小，但是如果第一部件具有1的拉伸系数和所述第二部件具有2的拉伸系数，所述第一部件将获取可用的三分之一空间中，而第二个将得到的2/3 。

QGraphicsLinearLayout计算大小加起来的所有项目的拉伸系数，然后相应地将所述可用空间的分配。默认拉伸系数为0的所有项目;因数为0表示该项目没有任何定义的伸展系数，有效，这是一样的拉伸系数设置为1 。上的伸长率只适用于在可用空间中的布局（以下其方向）的长度方向。如果你想控制的项目的水平和垂直拉伸两种，您可以使用[QGraphicsGridLayout](qgraphicsgridlayout.html)代替。

### QGraphicsLinearLayout Compared to Other Layouts

QGraphicsLinearLayout是非常相似的[QVBoxLayout](qvboxlayout.html)和[QHBoxLayout](qhboxlayout.html)的，但在对比这些类，它是用来管理[QGraphicsWidget](qgraphicswidget.html)和[QGraphicsLayout](qgraphicslayout.html)而不是[QWidget](qwidget.html)和[QLayout](qlayout.html)。

* * *

## Method Documentation

```
QGraphicsLinearLayout.__init__ (self, QGraphicsLayoutItem parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsLinearLayout](qgraphicslinearlayout.html)例如使用[Qt.Horizontal](qt.html#Orientation-enum)方向。_parent_被传递给[QGraphicsLayout](qgraphicslayout.html)的构造。

```
QGraphicsLinearLayout.__init__ (self, Qt.Orientation orientation, QGraphicsLayoutItem parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsLinearLayout](qgraphicslinearlayout.html)实例。您可以通过_orientation_对于布局，无论是水平或垂直，并_parent_被传递给[QGraphicsLayout](qgraphicslayout.html)的构造。

```
QGraphicsLinearLayout.addItem (self, QGraphicsLayoutItem item)
```

该_item_说法有它的所有权转移给Qt的。

这个方便的功能等同于调用InsertItem将（-1 ，_item_） 。

```
QGraphicsLinearLayout.addStretch (self, int stretch = 1)
```

这个方便的功能等同于调用insertStretch （-1 ，_stretch_） 。

```
Qt.Alignment QGraphicsLinearLayout.alignment (self, QGraphicsLayoutItem item)
```

[](index.htm)

[返回对齐_item_。默认的对齐方式是](index.htm)[Qt.AlignTop](qt.html#AlignmentFlag-enum)|[Qt.AlignLeft](qt.html#AlignmentFlag-enum)。

对齐决定如何该项目的情况下那里的布局腾出更多可用空间比小部件可以佔据的位置分配给它的空间内。

**See also** [setAlignment](qgraphicslinearlayout.html#setAlignment)（ ） 。

```
int QGraphicsLinearLayout.count (self)
```

从重新实现[QGraphicsLayout.count](qgraphicslayout.html#count)（ ） 。

```
QGraphicsLinearLayout.insertItem (self, int index, QGraphicsLayoutItem item)
```

该_item_说法有它的所有权转移给Qt的。

Inserts _item_在进入布局_index_，或者说是目前在任何项目之前，_index_。

**See also** [addItem](qgraphicslinearlayout.html#addItem)（ ）[itemAt](qgraphicslinearlayout.html#itemAt)（ ）[insertStretch](qgraphicslinearlayout.html#insertStretch)（）和[setItemSpacing](qgraphicslinearlayout.html#setItemSpacing)（ ） 。

```
QGraphicsLinearLayout.insertStretch (self, int index, int stretch = 1)
```

插入一片_stretch_在_index_，或者说是目前在任何项目之前，_index_。

**See also** [addStretch](qgraphicslinearlayout.html#addStretch)（ ）[setStretchFactor](qgraphicslinearlayout.html#setStretchFactor)（ ）[setItemSpacing](qgraphicslinearlayout.html#setItemSpacing)（）和[insertItem](qgraphicslinearlayout.html#insertItem)（ ） 。

```
QGraphicsLinearLayout.invalidate (self)
```

从重新实现[QGraphicsLayout.invalidate](qgraphicslayout.html#invalidate)（ ） 。

```
QGraphicsLayoutItem QGraphicsLinearLayout.itemAt (self, int index)
```

[](qgraphicslayoutitem.html)

[从重新实现](qgraphicslayoutitem.html)[QGraphicsLayout.itemAt](qgraphicslayout.html#itemAt)（ ） 。

当从0迭代和时，它会返回在视觉排列顺序选择项目。

```
float QGraphicsLinearLayout.itemSpacing (self, int index)
```

项目后返回的间距在_index_。

**See also** [setItemSpacing](qgraphicslinearlayout.html#setItemSpacing)（ ） 。

```
Qt.Orientation QGraphicsLinearLayout.orientation (self)
```

[

返回布局方向。

](qt.html#Orientation-enum)

[**See also**](qt.html#Orientation-enum) [setOrientation](qgraphicslinearlayout.html#setOrientation)（ ） 。

```
QGraphicsLinearLayout.removeAt (self, int index)
```

从重新实现[QGraphicsLayout.removeAt](qgraphicslayout.html#removeAt)（ ） 。

在删除的项目_index_不破坏它。该项目的所有权转移给调用者。

**See also** [removeItem](qgraphicslinearlayout.html#removeItem)（）和[insertItem](qgraphicslinearlayout.html#insertItem)（ ） 。

```
QGraphicsLinearLayout.removeItem (self, QGraphicsLayoutItem item)
```

该_item_争论

移除_item_从而不破坏它的布局。所有权_item_传送到呼叫者。

**See also** [removeAt](qgraphicslinearlayout.html#removeAt)（）和[insertItem](qgraphicslinearlayout.html#insertItem)（ ） 。

```
QGraphicsLinearLayout.setAlignment (self, QGraphicsLayoutItem item, Qt.Alignment alignment)
```

设置的对齐方式_item_至_alignment_。如果_item_的排列变化，布局会自动失效。

**See also** [alignment](qgraphicslinearlayout.html#alignment)（）和[invalidate](qgraphicslinearlayout.html#invalidate)（ ） 。

```
QGraphicsLinearLayout.setGeometry (self, QRectF rect)
```

从重新实现[QGraphicsLayoutItem.setGeometry](qgraphicslayoutitem.html#setGeometry)（ ） 。

```
QGraphicsLinearLayout.setItemSpacing (self, int index, float spacing)
```

在项目建成后的间距_index_至_spacing_。

**See also** [itemSpacing](qgraphicslinearlayout.html#itemSpacing)（ ） 。

```
QGraphicsLinearLayout.setOrientation (self, Qt.Orientation orientation)
```

改变布局方向，以_orientation_。更改布局方向的布局将自动失效。

**See also** [orientation](qgraphicslinearlayout.html#orientation)（ ） 。

```
QGraphicsLinearLayout.setSpacing (self, float spacing)
```

设置布局的间距_spacing_。间距是指件之间的垂直距离和水平距离。

**See also** [spacing](qgraphicslinearlayout.html#spacing)（ ）[setItemSpacing](qgraphicslinearlayout.html#setItemSpacing)（ ）[setStretchFactor](qgraphicslinearlayout.html#setStretchFactor)（）和[QGraphicsGridLayout.setSpacing](qgraphicsgridlayout.html#setSpacing)（ ） 。

```
QGraphicsLinearLayout.setStretchFactor (self, QGraphicsLayoutItem item, int stretch)
```

设置为拉伸因子_item_至_stretch_。如果项目的伸展系数的变化，这个功能将使布局失效。

Setting _stretch_到0删除从产品上的伸长率，和实际上等同于设置_stretch_为1。

**See also** [stretchFactor](qgraphicslinearlayout.html#stretchFactor)（ ） 。

```
QSizeF QGraphicsLinearLayout.sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())
```

[](qsizef.html)

[从重新实现](qsizef.html)[QGraphicsLayoutItem.sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
float QGraphicsLinearLayout.spacing (self)
```

返回布局的间距。间距是指件之间的垂直距离和水平距离。

**See also** [setSpacing](qgraphicslinearlayout.html#setSpacing)（ ） 。

```
int QGraphicsLinearLayout.stretchFactor (self, QGraphicsLayoutItem item)
```

返回的拉伸因子_item_。默认拉伸系数为0 ，这意味着该项目已没有分配的拉伸因子。

**See also** [setStretchFactor](qgraphicslinearlayout.html#setStretchFactor)（ ） 。