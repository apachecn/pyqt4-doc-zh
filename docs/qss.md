*   ## [项目列表](#)

| [Qt样式单参考](#__RefHeading__8571_1947317750) |
| [可进行样式设置的部件列表](#__RefHeading__8573_1947317750) |
| [属性列表](#__RefHeading__8575_1947317750) |
| [图标列表](#__RefHeading__8577_1947317750) |
| [属性类型列表](#__RefHeading__8579_1947317750) |
| [伪状态列表](#__RefHeading__8581_1947317750) |
| [子控件列表](#__RefHeading__8583_1947317750) |

请在py文件进行调用

[Home](index.html) · [All Classes](index.htm) · [Modules](index.htm)  · [QSS HELP](qss.html)  · [QSS 案例](qtqss.html) · [VER007 HOME](HTTP://VER007.COM)

# Qt4.7文档翻译：Qt样式单参考,Qt Style Sheets Reference

## 
<colgroup><col width="152"> <col width="591"></colgroup> 
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |

 [属性类型](#list-of-property-types) 来进行赋值。除非另外有说明，否则以下的属性对所有部件都有用。带有星号*的属性是Qt 特有的，在CSS2 或CSS3 中没有等价属性。

<colgroup><col width="168"> <col width="68"> <col width="507"></colgroup> 
| 属性 | 类型 | 说明 |
| alternate-background-color | [Brush](#brush) | 在 [QAbstractItemView](qabstractitemview.html)子类中使用的交替背景色。如果这個属性没有设置的话，那么默认值就是为调色板（palette）的AlternateBase角色（role）设置的值。示例：QTreeView {alternate-background-color: blue;background: yellow;}参考 [background](#background-prop)和 [selection-background-color](#selection-background-color-prop)。 |
| background | [Background](#background) | 用来设置背景的省写（Shorthand）方式。等价于设置background-color、background-image、background-repeat和／或background-position。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QDialog](qdialog.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)、 [QToolTip](qtooltip.html)和普通的 [QWidget](qwidget.html)支持。示例：QTextEdit { background: yellow }通常，有必要设置一個类似Qt::BrushStyle中的样式的填充模式。你可以为Qt::SolidPattern、Qt::RadialGradientPattern、Qt::LinearGradientPattern和Qt::ConicalGradientPattern使用背景色（background-color）属性。其它模式也可以很简单地通过创建一個包含那种模式的背景图片的方式来实现。示例：QLabel {background-image: url(dense6pattern.png);background-repeat: repeat-xy;}参考 [background-origin](#background-origin-prop)、[selection-background-](#selection-background-color-prop) [color](#selection-background-color-prop)、 [background-clip](#background-clip-prop)、 [background-attachment](#background-attachment-prop)和 [alternate-background-color](#alternate-background-color-prop)。 |
| background- color | [Brush](#brush) | 为这個部件使用的背景颜色。示例：QLabel { background-color: yellow }QLineEdit { background-color: rgb(255, 0, 0) } |
| background-image | [Url](#url) | 为这個部件使用的背景图片。图片的半透明部分会露出背景颜色（background-color）。示例：QFrame { background-image: url(:/../img/hydro.png) } |
| background-repeat | [Repeat](#repeat) | 在填充background-origin矩形的过程中，背景图片是否要重要，以及如何重复。如果没有设置的话，则背景图片在两个方向上都重复（repeat）。示例：QFrame {background: white url(:/../img/ring.png);background-repeat: repeat-y;background-position: left;} |
| background-position | [Alignment](#alignment) | 背景图片在background-origin矩形中的对齐方式。没有设置的话，则对齐方式是top left（左上）。Example:QFrame {background: url(:/../img/footer.png);background-position: bottom left;} |
| background-attachment | [Attachment](#attachment) | 确定在一個 [QAbstractScrollArea](qabstractscrollarea.html)中的背景图片是否会随视口（viewport）滚动。默认情况下，背景图片会随视口滚动。示例：QTextEdit {background-image: url("leaves.png");background-attachment: fixed;}参考 [background](#background-prop)。 |
| background-clip | [Origin](#origin) | 在部件的矩形区域中绘制背景（background）的区域。这個属性指定的是background-color和background-image在其中被修剪（clipped）的矩形区域。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QDialog](qdialog.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)、 [QToolTip](qtooltip.html)和普通的 [QWidget](qwidget.html)支持。如果这個属性没有设置的话，则默认值是border。示例：QFrame {background-image: url(:/../img/header.png);background-position: top left;background-origin: content;background-clip: padding;}参考 [background](#background-prop)、 [background-origin](#background-origin-prop)和盒状模型（The Box Model）。 |
| background-origin | [Origin](#origin) | 部件的背景矩形区域，与background-position和background-image结合使用。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QDialog](qdialog.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)、 [QToolTip](qtooltip.html)和普通的 [QWidget](qwidget.html)支持。如果这個属性没有设置的话，则默认值是padding。示例：QFrame {background-image: url(:/../img/header.png);background-position: top left;background-origin: content;}参考 [background](#background-prop)和盒状模型。 |
| border | [Border](#border) | 用来设置部件的边框的省写方式。等价于设置border-color、border-style和／或border-width。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)、 [QToolTip](qtooltip.html)和普通 [QWidget](qwidget.html)支持。示例：QLineEdit { border: 1px solid white } |
| border-top | [Border](#border) | 用来设置部件的顶部边框的省写方式。等价于设置border-top-color、border-top-style和／或border-top-width。 |
| border-right | [Border](#border) | 用来设置部件的右侧边框的省写方式。等价于设置border-right-color、border-right-style和／或border-right-width。 |
| border-bottom | [Border](#border) | 用来设置部件的底部边框的省写方式。等价于设置border-bottom-color、border-bottom-style和／或border-bottom-width。 |
| border-left | [Border](#border) | 用来设置部件的左侧边框的省写方式。等价于设置border-left-color、border-left-style和／或border-left-width。 |
| border-color | [Box Colors](#box-colors) | 边框的所有边的颜色。等价于指定border-top-color、border-right-color、border-bottom-color和border-left-color。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)、 [QToolTip](qtooltip.html)和普通 [QWidget](qwidget.html)支持。如果这個属性没有指定，则默认是 [color](#color-prop)（也就是说，部件的前景色）。示例：QLineEdit {border-width: 1px;border-style: solid;border-color: white;}参考 [border-style](#border-style-prop)、 [border-width](#border-width-prop)、 [border-image](#border-image-prop)和盒状模型。 |
| border-top-color | [Brush](#brush) | 边框的顶部边线的颜色。 |
| border-right-color | [Brush](#brush) | 边框的右侧边线的颜色。 |
| border-bottom-color | [Brush](#brush) | 边框的底部边线的颜色。 |
| border-left-color | [Brush](#brush) | 边框的左侧边线的颜色。 |
| border-image | [Border Image](#border-image) | 用来填充边框的图片。图片被切成9块，并且在必要的时候还会被拉伸（stretched）。参考 [Border Image](#border-image)以了解细节。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。参考 [border-color](#border-color-prop)、 [border-style](#border-style-prop)、 [border-width](#border-width-prop)和盒状模型。 |
| border-radius | [Radius](#radius) | 边框的边角的半径。等价于指定border-top-left-radius、border-top-right-radius、border-bottom-right-radius和border-bottom-left-radius。边框半径（border-radius）会修剪（clips）这個元素的背景（ [background](#background-prop)）。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。如果这個属性没有指定的话，那么它的默认值是0。示例：QLineEdit {border-width: 1px;border-style: solid;border-radius: 4px;}参考 [border-width](#border-width-prop)和盒状模型。 |
| border-top-left-radius | [Radius](#radius) | 边框的左上角的半径。 |
| border-top-right-radius | [Radius](#radius) | 边框的右上角的半径。 |
| border-bottom-right-radius | [Radius](#radius) | 边框的右下角的半径。将这個属性设置成正数的值就会产生圆角。 |
| border-bottom-left-radius | [Radius](#radius) | 边框的左下角的半径。将这個属性设置成正数的值就会产生圆角。 |
| border-style | [Border Style](#border-style) | 边框的所有边线的风格。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。如果这個属性没有指定，则默认值是无（none）。示例：QLineEdit {border-width: 1px;border-style: solid;border-color: blue;}参考 [border-color](#border-color-prop)、 [border-style](#border-style-prop)、 [border-image](#border-image-prop)和盒状模型。 |
| border-top- style | [Border ](#border-style)[Style](#border-style) | 边框的顶部边线的风格。 |
| border-right-style | [Border Style](#border-style) | 边框的右侧边线的风格。 |
| border-bottom-style | [Border Style](#border-style) | 边框的底部边线的风格。 |
| border-left-style | [Border Style](#border-style) | 边框的左侧边线的风格。 |
| border-width | [Box Lengths](#box-lengths) | 边框的宽度。等价于设置border-top-width、border-right-width、border-bottom-width和border-left-width。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。示例：QLineEdit {border-width: 2px;border-style: solid;border-color: darkblue;}参考 [border-color](#border-color-prop)、 [border-radius](#border-radius-prop)、 [border-style](#border-style-prop)、 [border-image](#border-image-prop)和盒状模型。 |
| border-top-width | [Length](#length) | 边框的顶部边线的宽度。 |
| border-right-width | [Length](#length) | 边框的右侧边线的宽度。 |
| border-bottom-width | [Length](#length) | 边框的底部边线的宽度。 |
| border-left-width | [Length](#length) | 边框的左侧边线的宽度。 |
| bottom | [Length](#length) | 如果 [position](#position-prop)（位置）是relative（相对的）（默认值），则将一个子控件（ [subcontrol](#subcontrols)）向上移动一定的位置；在那种情况下，指定bottom:  y等价于指定 [top](#top-prop) : - y。如果 [position](#position-prop)是absolute（绝对的），则bottom属性指定的是这个子控件的底部边线相对于亲代（parent）部件的底部边线的位置（参考 [subcontrol-origin](#subcontrol-origin-prop)）。示例：QSpinBox::down-button { bottom: 2px }参考 [left](#left-prop)、 [right](#right-prop)和 [top](#top-prop)。 |
| button-layout | [Number](#number) | 在一個 [QDialogButtonBox](qdialogbuttonbox.html)或 [QMessageBox](qmessagebox.html)中的按钮的布局。可选值是0 (WinLayout)、1 (MacLayout)、2 (KdeLayout)和3 (GnomeLayout)。如果这個属性没有指定的话，则默认值是由当前风格中的SH_DialogButtonLayout风格提示来确定的。示例：* { button-layout: 2 } |
| color | [Brush](#brush) | 用来渲染文字的颜色。所有支持（respect）QWidget::palette的部件都支持这個属性。如果这個属性没有设置的话，则默认值是为这個部件的调色板设置的QWidget::foregroundRole 的值（通常是黑色）。示例：QPushButton { color: red }参考 [background](#background-prop)和 [selection-color](#selection-color-prop)。 |
| dialogbuttonbox-buttons-have-icons | [Boolean](#boolean) | [QDialogButtonBox](qdialogbuttonbox.html)中的按钮是否要显示图标。如果这個属性设置为1，则 [QDialogButtonBox](qdialogbuttonbox.html)中的按钮显示图标；如果设置为0，则不显示图标。参考[List of Icons](#list-of-icons) （图标列表）小节以了解如何设置图标。QDialogButtonBox { dialogbuttonbox-buttons-have-icons: 1; }注意：定义咯这個属性的样式必须在 [QDialogButtonBox](qdialogbuttonbox.html)被创建之前就应用；也就是说妳必须将样式应用到它的亲代部件或者直接应用到程序本身。 |
| font | [Font](#font) | 用来设置文字的字体的省写方式。等价于设置font-family、font-size、font-style和／或font-weight。所有支持QWidget::font的部件都支持这個属性。如果没有设置，则默认值是QWidget::font。示例：QCheckBox { font: bold italic large "Times New Roman" } |
| font-family | String | 字体族（family）。示例：QCheckBox { font-family: "New Century Schoolbook" } |
| font-size | [Font Size](#font-size) | 字体大小。在这個版本的Qt 中，只支持pt 和px 单位。示例：QTextEdit { font-size: 12px } |
| font-style | [Font](#font-style) [Style](#font-style) | 字体风格。示例：QTextEdit { font-style: italic } |
| font-weight | [Font Weight](#font-weight) | 字体的重量（weight）。 |
| gridline-color* | [Color](#color) | 在 [QTableView](qtableview.html)中的网格线的颜色。如果没有设置的话，则默认值是当前风格中为SH_Table_GridLineColor样式提示指定的值。示例：* { gridline-color: gray } |
| height | [Length](#length) | 一個子控件（ [subcontrol](#subcontrols)）（在某些情况下，是部件）的高度。如果这個属性没有设置，则默认值取决于子控件／部件本身及当前的风格。警告：除非另有说明，否则这个属性对部件无效。如果妳想要某個部件拥有固定的高度，则将 [min-height](#min-width-prop)和 [max-height](#max-width-prop)设置成同一個值。示例：QSpinBox::down-button { height: 10px }参考 [width](#width-prop)。 |
| icon-size | [Length](#length) | 某個部件中的图标的宽度和高度。以下部件的图标尺寸可使用这個属性来设置。

*   • [QCheckBox](qcheckbox.html)

*   • [QListView](qlistview.html)

*   • [QPushButton](qpushbutton.html)

*   • [QRadioButton](qradiobutton.html)

*   • [QTabBar](qtabbar.html)

*   • [QToolBar](qtoolbar.html)

*   • [QToolBox](qtoolbox.html)

*   • [QTreeView](qtreeview.html)

 |
| image* | [Url](#url)+ | 被绘制到一個子控件（ [subcontrol](#subcontrols)）的内容区域的图片。image（图片）属性接受一组 [Url](#url)（统一资源定位器）或一個svg（可缩放矢量图）。实际绘制的图片是由与 [QIcon](qicon.html)相同的算法来确定的，（也就是说）图片绝不会被放大但必要的时候一定会缩小。如果指定咯一個svg，则图片会缩放到内容区域的大小。在子控件上设置图片会隐式地设置那個子控件的宽度和高度（除非图片是一個SVG）。在Qt 4.3 和以后的版本中，可使用 [image-position](#image-position-prop)来指定图片在矩形区域中的对齐方式。这個属性是只为子控件（ [subcontrol](#subcontrols)）设计的--我们不在其它元素中支持它。警告：需要有[QIcon](qicon.html) SVG 插件才能渲染SVG 图片。示例：/* 隐式地将down-button 的大小设置成spindown.png 的大小 */QSpinBox::down-button { image: url(:/../img/spindown.png) } |
| image-position | [alignme](#alignment) [nt](#alignment) | 在Qt 4.3 及以后的版本中，图片的位置可使用相对定位和绝对定位来设置。 |
| left | [Length](#length) | 如果 [position](#position-prop)（位置）是relative（相对的）（默认值），则将某個 [subcontrol](#subcontrols)（子控件）向右移动一定距离。如果 [position](#position-prop)是absolute（绝对的），则left属性指定的是这個子控件的左边线与亲代部件的左边线的相对位置（参考 [subcontrol-origin](#subcontrol-origin-prop)）。如果没有设置，则默认值是0。示例：QSpinBox::down-button { left: 2px }参考 [right](#right-prop)、 [top](#top-prop)和 [bottom](#bottom-prop)。 |
| lineedit-password-character* | [Number](#number) | 以Unicode（统一码）指定的 [QLineEdit](qlineedit.html)密码字符。如果这個属性没有设置，则默认值是由当前风格中的SH_LineEdit_PasswordCharacter样式提示确定的。示例：* { lineedit-password-character: 9679 } |
| margin | [Box Lengths](#box-lengths) | 部件的边距（margins）。等价于指定margin-top、margin-right、margin-bottom和margin-left。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。如果没有设置的话，默认为0。示例：QLineEdit { margin: 2px }参考 [padding](#padding-prop)、 [spacing](#spacing-prop)和盒状模型。 |
| margin-top | [Length](#length) | 部件的顶部边距。 |
| margin-right | [Length](#length) | 部件的右侧边距。 |
| margin-bottom | [Length](#length) | 部件的底部边距。 |
| margin-left | [Length](#length) | 部件的左侧边距。 |
| max-height | [Length](#length) | 这個部件或者其子控件的最大高度。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSizeGrip](qsizegrip.html)、 [QSpinBox](qspinbox.html)、 [QSplitter](qsplitter.html)、 [QStatusBar](qstatusbar.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。这個值是相对于盒状模型中的内容区域的。示例：QSpinBox { max-height: 24px }参考 [max-width](#max-width-prop)。 |
| max-width | [Length](#length) | 这個部件或者其子控件的最大宽度。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSizeGrip](qsizegrip.html)、 [QSpinBox](qspinbox.html)、 [QSplitter](qsplitter.html)、 [QStatusBar](qstatusbar.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。这個值是相对于盒状模型中的内容区域的。示例：QComboBox { max-width: 72px }参考 [max-height](#max-height-prop)。 |
| messagebox-text-interaction-flags* | [Number](#number) | 在消息框中的文字的交互行为。可能取的值取决于Qt::TextInteractionFlags。如果属性没有设置的话，则默认值是由当前风格中的SH_MessageBox_TextInteractionFlags样式提示确定的。示例：QMessageBox { messagebox-text-interaction-flags: 5 } |
| min-height | [Length](#length) | 这個部件或者其子控件的最小高度。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSizeGrip](qsizegrip.html)、 [QSpinBox](qspinbox.html)、 [QSplitter](qsplitter.html)、 [QStatusBar](qstatusbar.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。如果这個属性没有指定的话，则最小高度是基于这個部件的内容和样式来继承的。这個值是相对于盒状模型中的内容区域的。示例：QComboBox { min-height: 24px }参考 [min-width](#min-width-prop)。 |
| min-width | [Length](#length) | 这個部件或者其子控件的最小宽度。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、[Q](qlineedit.html) [LineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSizeGrip](qsizegrip.html)、 [QSpinBox](qspinbox.html)、 [QSplitter](qsplitter.html)、 [QStatusBar](qstatusbar.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。如果这個属性没有指定的话，则最小宽度是基于这個部件的内容和样式来继承的。这個值是相对于盒状模型中的内容区域的。示例：QComboBox { min-width: 72px }参考 [min-height](#min-height-prop)。 |
| opacity* | [Number](#number) | 某個部件的透明度。取值范围从0 (透明)到255 (不透明)。当前只被工具提示（ [tooltips](qtooltip.html)）支持。如果这個属性没有设置，则默认值由当前风格中的SH_ToolTipLabel_Opacity样式提示确定。示例：QToolTip { opacity: 223 } |
| padding | [Box](#box-lengths) [Lengths](#box-lengths) | 这個部件的填充宽度（padding）。等价于设置padding-top、padding-right、padding-bottom和padding-left。这個属性被 [QAbstractItemView](qabstractitemview.html)子类、 [QAbstractSpinBox](qabstractspinbox.html)子类、 [QCheckBox](qcheckbox.html)、 [QComboBox](qcombobox.html)、 [QFrame](qframe.html)、 [QGroupBox](qgroupbox.html)、 [QLabel](qlabel.html)、 [QLineEdit](qlineedit.html)、 [QMenu](qmenu.html)、 [QMenuBar](qmenubar.html)、 [QPushButton](qpushbutton.html)、 [QRadioButton](qradiobutton.html)、 [QSplitter](qsplitter.html)、 [QTextEdit](qtextedit.html)和 [QToolTip](qtooltip.html)支持。如果没有设置的话，默认为0。示例：QLineEdit { padding: 3px }参考 [margin](#margin-prop)、 [spacing](#spacing-prop)和盒状模型。 |
| padding-top | [Length](#length) | 这個部件的顶部填充距离。 |
| padding-right | [Length](#length) | 这個部件的右侧填充距离。 |
| padding-bottom | [Length](#length) | 这個部件的底部填充距离。 |
| padding-left | [Length](#length) | 这個部件的左侧填充距离。 |
| paint-alternating-row-colors-for-empty-area | bool | [QTreeView](qtreeview.html)是否要为空白区域（没有条目的区域）绘制交替行颜色 |
| position | relative
&#124; absolute | 用 [left](#left-prop)、 [right](#right-prop)、 [top](#top-prop)和 [bottom](#bottom-prop)指定的偏移值是相对的还是绝对的坐标。如果没有设置，则默认值是relative。 |
| right | [Length](#length) | 如果 [position](#position-prop)（位置）是relative（相对的）（默认值），则将某個 [subcontrol](#subcontrols)（子控件）向左移动一定距离；在那种情况下，指定right:  x就等价于指定 [left](#left-prop) : - x。如果 [position](#position-prop)是absolute（绝对的），则right属性指定的是这個子控件的右边线相对于亲代部件的右边线的位置（参考 [subcontrol-origin](#subcontrol-origin-prop)）。示例：QSpinBox::down-button { right: 2px }参考 [left](#left-prop)、 [top](#top-prop)和 [bottom](#bottom-prop)。 |
| selection-background-color* | [Brush](#brush) | 选中的文字或条目的背景。所有支持QWidget::palette并且显示选中文字的部件都支持这個属性。如果没有设置，则默认值是为调色板的Highlight角色设置的值。示例：QTextEdit { selection-background-color: darkblue }参考 [selection-color](#selection-color-prop)和 [background](#background-prop)。 |
| selection-color* | [Brush](#brush) | 选中的文字或条目的前景。所有支持QWidget::palette并且显示选中文字的部件都支持这個属性。如果没有设置，则默认值是为调色板的HighlightedText角色设置的值。示例：QTextEdit { selection-color: white }参考 [selection-background-color](#selection-background-color-prop)和 [color](#color-prop)。 |
| show-decoration-selected* | [Boolean](#boolean) | 控制的是在一個 [QListView](qlistview.html)中的选中区域是要覆盖整个行还是只覆盖文字的区域。如果没有设置，则默认值是由当前风格中的SH_ItemView_ShowDecorationSelected样式提示确定的。示例：* { show-decoration-selected: 1 } |
| spacing* | [Length](#length) | 这個部件内部的间隔（spacing）。这個属性被 [QCheckBox](qcheckbox.html)、可选中的 [QGroupBox](qgroupbox.html)、 [QMenuBar](qmenubar.html)和 [QRadioButton](qradiobutton.html)支持。如果没有指定，则默认值取决于部件本身及当前风格。示例：QMenuBar { spacing: 10 }参考 [padding](#padding-prop)和 [margin](#margin-prop)。 |
| subcontrol-origin* | [Origin](#origin) | 这個 [subcontrol](#subcontrols)（子控件）在亲代元素中的根源（origin）矩形。如果没有指定，则默认值为padding。示例：QSpinBox::up-button {image: url(:/../img/spinup.png);subcontrol-origin: content;subcontrol-position: right top;}参考 [subcontrol-position](#subcontrol-position-prop)。 |
| subcontrol-position* | [Alignment](#alignment) | 这個子控件（ [subcontrol](#subcontrols)）在由 [subcontrol-origin](#subcontrol-origin-prop)确定的根源矩形中的对齐方式。如果没有设置的话，则默认值取决于子控件本身。示例：QSpinBox::down-button {image: url(:/../img/spindown.png);subcontrol-origin: padding;subcontrol-position: right bottom;}参考 [subcontrol-origin](#subcontrol-origin-prop)。 |
| text-align | [Alignment](#alignment) | 文字和图标在这個部件的内容中的对齐方式。如果没有设置的话，则默认值取决于原生（native）风格。示例：QPushButton {text-align: left;}当前只有 [QPushButton](qpushbutton.html)和 [QProgressBar](qprogressbar.html)支持这個属性。 |
| text-decoration | none
underline
overline
line-through | 附加的文字效果 |
| top | [Length](#length) | 如果 [position](#position-prop)是relative（相对的）（默认值），则将一個 [subcontrol](#subcontrols)（子控件）向下移动指定距离。如果 [position](#position-prop)是absolute（绝对的），则top属性指定的是这個子控件的顶部边线相对于亲代部件的顶部边线的位置（参考 [subcontrol-origin](#subcontrol-origin-prop)）。如果没有设置的话，则默认值是0。示例：QSpinBox::up-button { top: 2px }参考 [left](#left-prop)、 [right](#right-prop)和 [bottom](#bottom-prop)。 |
| width | [Length](#length) | 一個 [subcontrol](#subcontrols)（子控件）（或者在某些情况下会是部件）的宽度。如果没有设置的话，则默认值取决于子控件／部件本身及当前的风格。警告：除非另外说明，否则这個属性对于部件无效。如果妳想让某個部件具有固定的宽度，则将 [min-width](#min-width-prop)和 [max-width](#max-width-prop)设置成相同的值。示例：QSpinBox::up-button { width: 12px }参考 [height](#height-prop)。 |

 [Icon](#icon) 。

注意，要想让 [QDialogButtonBox](qdialogbuttonbox.html) 中的按钮里出现图标的话，妳需要将dialogbuttonbox-buttons-have-icons 属性设置成true（真）。并且，要对图标的尺寸进行自定义的话，则使用icon-size 属性。

<colgroup><col width="329"> <col width="414"></colgroup> 
| 名字 | QStyle::StandardPixmap |
| backward-icon | QStyle::SP_ArrowBack |
| cd-icon | QStyle::SP_DriveCDIcon |
| computer-icon | QStyle::SP_ComputerIcon |
| desktop-icon | QStyle::SP_DesktopIcon |
| dialog-apply-icon | QStyle::SP_DialogApplyButton |
| dialog-cancel-icon | QStyle::SP_DialogCancelButton |
| dialog-close-icon | QStyle::SP_DialogCloseButton |
| dialog-discard-icon | QStyle::SP_DialogDiscardButton |
| dialog-help-icon | QStyle::SP_DialogHelpButton |
| dialog-no-icon | QStyle::SP_DialogNoButton |
| dialog-ok-icon | QStyle::SP_DialogOkButton |
| dialog-open-icon | QStyle::SP_DialogOpenButton |
| dialog-reset-icon | QStyle::SP_DialogResetButton |
| dialog-save-icon | QStyle::SP_DialogSaveButton |
| dialog-yes-icon | QStyle::SP_DialogYesButton |
| directory-closed-icon | QStyle::SP_DirClosedIcon |
| directory-icon | QStyle::SP_DirIcon |
| directory-link-icon | QStyle::SP_DirLinkIcon |
| directory-open-icon | QStyle::SP_DirOpenIcon |
| dockwidget-close-icon | QStyle::SP_DockWidgetCloseButton |
| downarrow-icon | QStyle::SP_ArrowDown |
| dvd-icon | QStyle::SP_DriveDVDIcon |
| file-icon | QStyle::SP_FileIcon |
| file-link-icon | QStyle::SP_FileLinkIcon |
| filedialog-contentsview-icon | QStyle::SP_FileDialogContentsView |
| filedialog-detailedview-icon | QStyle::SP_FileDialogDetailedView |
| filedialog-end-icon | QStyle::SP_FileDialogEnd |
| filedialog-infoview-icon | QStyle::SP_FileDialogInfoView |
| filedialog-listview-icon | QStyle::SP_FileDialogListView |
| filedialog-new-directory-icon | QStyle::SP_FileDialogNewFolder |
| filedialog-parent-directory-icon | QStyle::SP_FileDialogToParent |
| filedialog-start-icon | QStyle::SP_FileDialogStart |
| floppy-icon | QStyle::SP_DriveFDIcon |
| forward-icon | QStyle::SP_ArrowForward |
| harddisk-icon | QStyle::SP_DriveHDIcon |
| home-icon | QStyle::SP_DirHomeIcon |
| leftarrow-icon | QStyle::SP_ArrowLeft |
| messagebox-critical-icon | QStyle::SP_MessageBoxCritical |
| messagebox-information-icon | QStyle::SP_MessageBoxInformation |
| messagebox-question-icon | QStyle::SP_MessageBoxQuestion |
| messagebox-warning-icon | QStyle::SP_MessageBoxWarning |
| network-icon | QStyle::SP_DriveNetIcon |
| rightarrow-icon | QStyle::SP_ArrowRight |
| titlebar-contexthelp-icon | QStyle::SP_TitleBarContextHelpButton |
| titlebar-maximize-icon | QStyle::SP_TitleBarMaxButton |
| titlebar-menu-icon | QStyle::SP_TitleBarMenuButton |
| titlebar-minimize-icon | QStyle::SP_TitleBarMinButton |
| titlebar-normal-icon | QStyle::SP_TitleBarNormalButton |
| titlebar-shade-icon | QStyle::SP_TitleBarShadeButton |
| titlebar-unshade-icon | QStyle::SP_TitleBarUnshadeButton |
| trash-icon | QStyle::SP_TrashIcon |
| uparrow-icon | QStyle::SP_ArrowUp |

<colgroup><col width="106"> <col width="199"> <col width="433"></colgroup> 
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |

<colgroup><col width="210"> <col width="533"></colgroup> 
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |