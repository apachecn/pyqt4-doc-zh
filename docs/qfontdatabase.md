# QFontDatabase Class Reference

## [[QtGui](index.htm) module]

该QFontDatabase类提供有关在底层窗口系统中可用的字体信息。[More...](#details)

### Types

*   `enum WritingSystem { Any, Latin, Greek, Cyrillic, ..., Nko }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QFontDatabase)`
*   `bool bold (self, QString family, QString style)`
*   `QStringList families (self, WritingSystem writingSystem = QFontDatabase.Any)`
*   `QFont font (self, QString family, QString style, int pointSize)`
*   `bool isBitmapScalable (self, QString family, QString style = QString())`
*   `bool isFixedPitch (self, QString family, QString style = QString())`
*   `bool isScalable (self, QString family, QString style = QString())`
*   `bool isSmoothlyScalable (self, QString family, QString style = QString())`
*   `bool italic (self, QString family, QString style)`
*   `list-of-int pointSizes (self, QString family, QString style = QString())`
*   `list-of-int smoothSizes (self, QString family, QString style)`
*   `QStringList styles (self, QString family)`
*   `QString styleString (self, QFont font)`
*   `QString styleString (self, QFontInfo fontInfo)`
*   `int weight (self, QString family, QString style)`
*   `list-of-QFontDatabase.WritingSystem writingSystems (self)`
*   `list-of-QFontDatabase.WritingSystem writingSystems (self, QString family)`

### Static Methods

*   `int addApplicationFont (QString fileName)`
*   `int addApplicationFontFromData (QByteArray fontData)`
*   `QStringList applicationFontFamilies (int id)`
*   `bool removeAllApplicationFonts ()`
*   `bool removeApplicationFont (int id)`
*   `list-of-int standardSizes ()`
*   `bool supportsThreadedFontRendering ()`
*   `QString writingSystemName (WritingSystem writingSystem)`
*   `QString writingSystemSample (WritingSystem writingSystem)`

* * *

## Detailed Description

该QFontDatabase类提供有关在底层窗口系统中可用的字体信息。

这个类最常见的用途是在数据库中查询字体的列表[families](qfontdatabase.html#families)（）和用于[pointSizes](qfontdatabase.html#pointSizes)（）和[styles](qfontdatabase.html#styles)（ ），可为每个家庭。一种替代[pointSizes](qfontdatabase.html#pointSizes)（）是[smoothSizes](qfontdatabase.html#smoothSizes)（ ）返回的大小在其中一个给定的系列和样式看起来有吸引力。

如果字体家族可从两个或两个以上的代工厂代工名称包含在家庭名称，例如： “黑体[点击]”和“黑体[ Cronyx ]” 。当您指定一个家庭，你可以使用旧的复姓“代工家庭”的形式或方括号内的“家庭[铸造]”格式，例如： “ Cronyx -黑体”或“宋体[ Cronyx ]” 。如果家里有一个铸造它使用括号内的格式总是返回，这与返回的值的情况下[families](qfontdatabase.html#families)（ ） 。

该[font](qfontdatabase.html#font)（ ）函数返回一个[QFont](qfont.html)给一个家庭，样式和点大小。

一个家庭和样式的组合可以进行检查，看它是否是[italic](qfontdatabase.html#italic)（）或[bold](qfontdatabase.html#bold)（ ） ，并检索其[weight](qfontdatabase.html#weight)（ ） 。同样，我们可以调用[isBitmapScalable](qfontdatabase.html#isBitmapScalable)（ ）[isSmoothlyScalable](qfontdatabase.html#isSmoothlyScalable)（ ）[isScalable](qfontdatabase.html#isScalable)（）和[isFixedPitch](qfontdatabase.html#isFixedPitch)（ ） 。

使用[styleString](qfontdatabase.html#styleString)（）来获取一个样式的文本版本。

该QFontDatabase类还支持一些静态的功能，例如，[standardSizes](qfontdatabase.html#standardSizes)（ ） 。您可以使用检索书写系统的描述[writingSystemName](qfontdatabase.html#writingSystemName)（ ） ，和一个在书写系统的字符样本[writingSystemSample](qfontdatabase.html#writingSystemSample)（ ） 。

例如：

```
     QFontDatabase database;
     [QTreeWidget](qtreewidget.html) fontTree;
     fontTree.setColumnCount(2);
     fontTree.setHeaderLabels([QStringList](qstringlist.html)() << "Font" << "Smooth Sizes");

     foreach (const [QString](qstring.html) &family, database.families()) {
         [QTreeWidgetItem](qtreewidgetitem.html) *familyItem = new [QTreeWidgetItem](qtreewidgetitem.html)(&fontTree);
         familyItem->setText(0, family);

         foreach (const [QString](qstring.html) &style, database.styles(family)) {
             [QTreeWidgetItem](qtreewidgetitem.html) *styleItem = new [QTreeWidgetItem](qtreewidgetitem.html)(familyItem);
             styleItem->setText(0, style);

             [QString](qstring.html) sizes;
             foreach (int points, database.smoothSizes(family, style))
                 sizes += [QString](qstring.html).number(points) + " ";

             styleItem->setText(1, sizes.trimmed());
         }
     }

```

此示例获取字体系列，样式为每个家庭的名单，以及可用于家庭和风格的各种组合的点尺寸列表中，在树视图中显示此信息。

* * *

## Type Documentation

```
QFontDatabase.WritingSystem
```

| Constant | Value | Description |
| --- | --- | --- |
| `QFontDatabase.Any` | `0` |   |
| `QFontDatabase.Latin` | `1` |   |
| `QFontDatabase.Greek` | `2` |   |
| `QFontDatabase.Cyrillic` | `3` |   |
| `QFontDatabase.Armenian` | `4` |   |
| `QFontDatabase.Hebrew` | `5` |   |
| `QFontDatabase.Arabic` | `6` |   |
| `QFontDatabase.Syriac` | `7` |   |
| `QFontDatabase.Thaana` | `8` |   |
| `QFontDatabase.Devanagari` | `9` |   |
| `QFontDatabase.Bengali` | `10` |   |
| `QFontDatabase.Gurmukhi` | `11` |   |
| `QFontDatabase.Gujarati` | `12` |   |
| `QFontDatabase.Oriya` | `13` |   |
| `QFontDatabase.Tamil` | `14` |   |
| `QFontDatabase.Telugu` | `15` |   |
| `QFontDatabase.Kannada` | `16` |   |
| `QFontDatabase.Malayalam` | `17` |   |
| `QFontDatabase.Sinhala` | `18` |   |
| `QFontDatabase.Thai` | `19` |   |
| `QFontDatabase.Lao` | `20` |   |
| `QFontDatabase.Tibetan` | `21` |   |
| `QFontDatabase.Myanmar` | `22` |   |
| `QFontDatabase.Georgian` | `23` |   |
| `QFontDatabase.Khmer` | `24` |   |
| `QFontDatabase.SimplifiedChinese` | `25` |   |
| `QFontDatabase.TraditionalChinese` | `26` |   |
| `QFontDatabase.Japanese` | `27` |   |
| `QFontDatabase.Korean` | `28` |   |
| `QFontDatabase.Vietnamese` | `29` |   |
| `QFontDatabase.Symbol` | `30` |   |
| `QFontDatabase.Other` | `Symbol` | （同符号） |
| `QFontDatabase.Ogham` | ？ |   |
| `QFontDatabase.Runic` | ？ |   |
| `QFontDatabase.Nko` | ？ |   |

* * *

## Method Documentation

```
QFontDatabase.__init__ (self)
```

创建字体数据库对象。

```
QFontDatabase.__init__ (self, QFontDatabase)
```

```
int QFontDatabase.addApplicationFont (QString fileName)
```

从指定的文件加载字体_fileName_并使得它的应用程序可用。一个ID被返回的，可用于与再除去字体[removeApplicationFont](qfontdatabase.html#removeApplicationFont)（）或检索包含在字体族名称的列表。

该函数返回-1，如果无法加载的字体。

目前只有TrueType字体， TrueType字体的集合，和OpenType字体的支持。

**Note:**增加对UNIX/X11平台上的应用程序的字体而不fontconfig的目前不支持。

**Note:**在Symbian ，字体系列名称被截断为20个字符的长度。

这个函数中引入了Qt 4.2中。

**See also** [addApplicationFontFromData](qfontdatabase.html#addApplicationFontFromData)（ ）[applicationFontFamilies](qfontdatabase.html#applicationFontFamilies)（）和[removeApplicationFont](qfontdatabase.html#removeApplicationFont)（ ） 。

```
int QFontDatabase.addApplicationFontFromData (QByteArray fontData)
```

加载从指定的二进制数据的字体_fontData_并使得它的应用程序可用。一个ID被返回的，可用于与再除去字体[removeApplicationFont](qfontdatabase.html#removeApplicationFont)（）或检索包含在字体族名称的列表。

该函数返回-1，如果无法加载的字体。

目前，只有TrueType字体和TrueType字体集合的支持。

**Note:**增加对UNIX/X11平台上的应用程序的字体而不fontconfig的目前不支持。

**Note:**在Symbian ，字体系列名称被截断为20个字符的长度。

这个函数中引入了Qt 4.2中。

**See also** [addApplicationFont](qfontdatabase.html#addApplicationFont)（ ）[applicationFontFamilies](qfontdatabase.html#applicationFontFamilies)（）和[removeApplicationFont](qfontdatabase.html#removeApplicationFont)（ ） 。

```
QStringList QFontDatabase.applicationFontFamilies (int id)
```

返回字体系列的确定给定应用程序的字体列表_id_。

这个函数中引入了Qt 4.2中。

**See also** [addApplicationFont](qfontdatabase.html#addApplicationFont)（）和[addApplicationFontFromData](qfontdatabase.html#addApplicationFontFromData)（ ） 。

```
bool QFontDatabase.bold (self, QString family, QString style)
```

返回True如果有家庭的字体_family_和风格_style_是大胆的，否则返回False 。

**See also** [italic](qfontdatabase.html#italic)（）和[weight](qfontdatabase.html#weight)（ ） 。

```
QStringList QFontDatabase.families (self, WritingSystem writingSystem = QFontDatabase.Any)
```

返回其支持的可用字体家族的排序列表_writingSystem_。

如果一个家庭中存在几个代工厂，该字体返回的名称的形式为“家庭[铸造]” 。例如：“时代[点击]” ， “时代[ Cronyx ]” ， “帕拉天奴” 。

**See also** [writingSystems](qfontdatabase.html#writingSystems)（ ） 。

```
QFont QFontDatabase.font (self, QString family, QString style, int pointSize)
```

[](qfont.html)

[返回](qfont.html)[QFont](qfont.html)对象有家庭_family_，式_style_和点大小_pointSize_。如果可以创建没有匹配的字体，一[QFont](qfont.html)使用该应用程序的默认字体对象被返回。

```
bool QFontDatabase.isBitmapScalable (self, QString family, QString style = QString())
```

返回True如果有家庭的字体_family_和风格_style_是一个可扩展的位图字体，否则返回False 。缩放的位图字体，通常会产生不吸引人几乎不可读的结果，因为该字体的像素进行缩放。如果您需要缩放位图字体，最好是将其扩展到返回的固定尺寸之一[smoothSizes](qfontdatabase.html#smoothSizes)（ ） 。

**See also** [isScalable](qfontdatabase.html#isScalable)（）和[isSmoothlyScalable](qfontdatabase.html#isSmoothlyScalable)（ ） 。

```
bool QFontDatabase.isFixedPitch (self, QString family, QString style = QString())
```

返回True如果有家庭的字体_family_和风格_style_是固定摊位，否则返回False 。

```
bool QFontDatabase.isScalable (self, QString family, QString style = QString())
```

返回True如果有家庭的字体_family_和风格_style_具有可扩展性，否则返回False 。

**See also** [isBitmapScalable](qfontdatabase.html#isBitmapScalable)（）和[isSmoothlyScalable](qfontdatabase.html#isSmoothlyScalable)（ ） 。

```
bool QFontDatabase.isSmoothlyScalable (self, QString family, QString style = QString())
```

返回True如果有家庭的字体_family_和风格_style_为顺利扩展性，否则返回False 。如果这个函数返回True ，它的安全扩展该字体到任何尺寸，结果总是看起来有吸引力。

**See also** [isScalable](qfontdatabase.html#isScalable)（）和[isBitmapScalable](qfontdatabase.html#isBitmapScalable)（ ） 。

```
bool QFontDatabase.italic (self, QString family, QString style)
```

返回True如果有家庭的字体_family_和风格_style_是斜体，否则返回False 。

**See also** [weight](qfontdatabase.html#weight)（）和[bold](qfontdatabase.html#bold)（ ） 。

```
list-of-int QFontDatabase.pointSizes (self, QString family, QString style = QString())
```

返回点尺寸的可用于与所述给定字体的列表_family_和_style_。该列表可能是空的。

**See also** [smoothSizes](qfontdatabase.html#smoothSizes)（）和[standardSizes](qfontdatabase.html#standardSizes)（ ） 。

```
bool QFontDatabase.removeAllApplicationFonts ()
```

删除所有应用程序的本地字体先前添加的使用[addApplicationFont](qfontdatabase.html#addApplicationFont)（）和[addApplicationFontFromData](qfontdatabase.html#addApplicationFontFromData)（ ） 。

返回True如果字体卸载成功，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [removeApplicationFont](qfontdatabase.html#removeApplicationFont)（ ）[addApplicationFont](qfontdatabase.html#addApplicationFont)（）和[addApplicationFontFromData](qfontdatabase.html#addApplicationFontFromData)（ ） 。

```
bool QFontDatabase.removeApplicationFont (int id)
```

删除确定以前加载的应用程序字体_id_。返回True如果字体卸载成功，否则返回False 。

这个函数中引入了Qt 4.2中。

**See also** [removeAllApplicationFonts](qfontdatabase.html#removeAllApplicationFonts)（ ）[addApplicationFont](qfontdatabase.html#addApplicationFont)（）和[addApplicationFontFromData](qfontdatabase.html#addApplicationFontFromData)（ ） 。

```
list-of-int QFontDatabase.smoothSizes (self, QString family, QString style)
```

返回一个字体的磅值与给定_family_和_style_这将看起来有吸引力。该列表可能是空的。对于非可缩放字体和位图可缩放字体，这个功能相当于[pointSizes](qfontdatabase.html#pointSizes)（ ） 。

**See also** [pointSizes](qfontdatabase.html#pointSizes)（）和[standardSizes](qfontdatabase.html#standardSizes)（ ） 。

```
list-of-int QFontDatabase.standardSizes ()
```

返回标准字体大小的列表。

**See also** [smoothSizes](qfontdatabase.html#smoothSizes)（）和[pointSizes](qfontdatabase.html#pointSizes)（ ） 。

```
QStringList QFontDatabase.styles (self, QString family)
```

返回的款式可供字体系列列表_family_。一些示例风格： “轻” ， “轻斜体” ， “粗体” ， “斜” ， “黛咪” 。该列表可能是空的。

**See also** [families](qfontdatabase.html#families)（ ） 。

```
QString QFontDatabase.styleString (self, QFont font)
```

返回描述的风格字符串_font_。例如， “粗斜体” ， “粗体” ， “斜体”或“正常” 。一个空字符串可以被返回。

```
QString QFontDatabase.styleString (self, QFontInfo fontInfo)
```

返回描述的风格字符串_fontInfo_。例如， “粗斜体” ， “粗体” ， “斜体”或“正常” 。一个空字符串可以被返回。

```
bool QFontDatabase.supportsThreadedFontRendering ()
```

如果字体渲染支持GUI线程，否则为False以外，则返回True 。换句话说，假返回值意味着所有[QPainter.drawText](qpainter.html#drawText)（ ） GUI线程之外调用不会产生可读的输出。

此功能被引入Qt的4.4 。

**See also** [Painting In Threads](index.htm#painting-in-threads)。

```
int QFontDatabase.weight (self, QString family, QString style)
```

返回具有家族字体的粗细_family_和风格_style_。如果没有这样的家庭和样式的组合，则返回-1 。

**See also** [italic](qfontdatabase.html#italic)（）和[bold](qfontdatabase.html#bold)（ ） 。

```
QString QFontDatabase.writingSystemName (WritingSystem writingSystem)
```

返回名称_writingSystem_（例如，用于显示在对话框的用户）。

```
list-of-QFontDatabase.WritingSystem QFontDatabase.writingSystems (self)
```

返回可用的书写系统的排序列表。这是从有关系统上所有已安装的字体的信息生成列表。

**See also** [families](qfontdatabase.html#families)（ ） 。

```
list-of-QFontDatabase.WritingSystem QFontDatabase.writingSystems (self, QString family)
```

返回书写系统由给定的字体支持的排序列表_family_。

**See also** [families](qfontdatabase.html#families)（ ） 。

```
QString QFontDatabase.writingSystemSample (WritingSystem writingSystem)
```

返回一个字符串，从样品字符_writingSystem_。