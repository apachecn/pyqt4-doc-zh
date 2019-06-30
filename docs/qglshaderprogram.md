# QGLShaderProgram Class Reference

## [[QtOpenGL](index.htm) module]

该QGLShaderProgram类允许的OpenGL着色器程序链接和使用。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QGLContext context, QObject parent = None)`
*   `bool addShader (self, QGLShader shader)`
*   `bool addShaderFromSourceCode (self, QGLShader.ShaderType type, QByteArray source)`
*   `bool addShaderFromSourceCode (self, QGLShader.ShaderType type, QString source)`
*   `bool addShaderFromSourceFile (self, QGLShader.ShaderType type, QString fileName)`
*   `int attributeLocation (self, QByteArray name)`
*   `int attributeLocation (self, QString name)`
*   `bool bind (self)`
*   `bindAttributeLocation (self, QByteArray name, int location)`
*   `bindAttributeLocation (self, QString name, int location)`
*   `disableAttributeArray (self, int location)`
*   `disableAttributeArray (self, str name)`
*   `enableAttributeArray (self, int location)`
*   `enableAttributeArray (self, str name)`
*   `int geometryInputType (self)`
*   `int geometryOutputType (self)`
*   `int geometryOutputVertexCount (self)`
*   `bool isLinked (self)`
*   `bool link (self)`
*   `QString log (self)`
*   `int programId (self)`
*   `release (self)`
*   `removeAllShaders (self)`
*   `removeShader (self, QGLShader shader)`
*   `setAttributeArray (self, int location, sequence values)`
*   `setAttributeArray (self, str name, sequence values)`
*   `setAttributeBuffer (self, int location, int type, int offset, int tupleSize, int stride = 0)`
*   `setAttributeBuffer (self, str name, int type, int offset, int tupleSize, int stride = 0)`
*   `setAttributeValue (self, int location, float value)`
*   `setAttributeValue (self, int location, float x, float y)`
*   `setAttributeValue (self, int location, float x, float y, float z)`
*   `setAttributeValue (self, int location, float x, float y, float z, float w)`
*   `setAttributeValue (self, int location, QVector2D value)`
*   `setAttributeValue (self, int location, QVector3D value)`
*   `setAttributeValue (self, int location, QVector4D value)`
*   `setAttributeValue (self, int location, QColor value)`
*   `setAttributeValue (self, str name, float value)`
*   `setAttributeValue (self, str name, float x, float y)`
*   `setAttributeValue (self, str name, float x, float y, float z)`
*   `setAttributeValue (self, str name, float x, float y, float z, float w)`
*   `setAttributeValue (self, str name, QVector2D value)`
*   `setAttributeValue (self, str name, QVector3D value)`
*   `setAttributeValue (self, str name, QVector4D value)`
*   `setAttributeValue (self, str name, QColor value)`
*   `setGeometryInputType (self, int inputType)`
*   `setGeometryOutputType (self, int outputType)`
*   `setGeometryOutputVertexCount (self, int count)`
*   `setUniformValue (self, int location, int value)`
*   `setUniformValue (self, int location, float value)`
*   `setUniformValue (self, int location, float x, float y)`
*   `setUniformValue (self, int location, float x, float y, float z)`
*   `setUniformValue (self, int location, float x, float y, float z, float w)`
*   `setUniformValue (self, int location, QVector2D value)`
*   `setUniformValue (self, int location, QVector3D value)`
*   `setUniformValue (self, int location, QVector4D value)`
*   `setUniformValue (self, int location, QColor color)`
*   `setUniformValue (self, int location, QPoint point)`
*   `setUniformValue (self, int location, QPointF point)`
*   `setUniformValue (self, int location, QSize size)`
*   `setUniformValue (self, int location, QSizeF size)`
*   `setUniformValue (self, int location, QMatrix2x2 value)`
*   `setUniformValue (self, int location, QMatrix2x3 value)`
*   `setUniformValue (self, int location, QMatrix2x4 value)`
*   `setUniformValue (self, int location, QMatrix3x2 value)`
*   `setUniformValue (self, int location, QMatrix3x3 value)`
*   `setUniformValue (self, int location, QMatrix3x4 value)`
*   `setUniformValue (self, int location, QMatrix4x2 value)`
*   `setUniformValue (self, int location, QMatrix4x3 value)`
*   `setUniformValue (self, int location, QMatrix4x4 value)`
*   `setUniformValue (self, int location, QTransform value)`
*   `setUniformValue (self, str name, int value)`
*   `setUniformValue (self, str name, float value)`
*   `setUniformValue (self, str name, float x, float y)`
*   `setUniformValue (self, str name, float x, float y, float z)`
*   `setUniformValue (self, str name, float x, float y, float z, float w)`
*   `setUniformValue (self, str name, QVector2D value)`
*   `setUniformValue (self, str name, QVector3D value)`
*   `setUniformValue (self, str name, QVector4D value)`
*   `setUniformValue (self, str name, QColor color)`
*   `setUniformValue (self, str name, QPoint point)`
*   `setUniformValue (self, str name, QPointF point)`
*   `setUniformValue (self, str name, QSize size)`
*   `setUniformValue (self, str name, QSizeF size)`
*   `setUniformValue (self, str name, QMatrix2x2 value)`
*   `setUniformValue (self, str name, QMatrix2x3 value)`
*   `setUniformValue (self, str name, QMatrix2x4 value)`
*   `setUniformValue (self, str name, QMatrix3x2 value)`
*   `setUniformValue (self, str name, QMatrix3x3 value)`
*   `setUniformValue (self, str name, QMatrix3x4 value)`
*   `setUniformValue (self, str name, QMatrix4x2 value)`
*   `setUniformValue (self, str name, QMatrix4x3 value)`
*   `setUniformValue (self, str name, QMatrix4x4 value)`
*   `setUniformValue (self, str name, QTransform value)`
*   `setUniformValueArray (self, int location, sequence values)`
*   `setUniformValueArray (self, str name, sequence values)`
*   `list-of-QGLShader shaders (self)`
*   `int uniformLocation (self, QByteArray name)`
*   `int uniformLocation (self, QString name)`

### Static Methods

*   `bool hasOpenGLShaderPrograms (QGLContext context = None)`

* * *

## Detailed Description

该QGLShaderProgram类允许的OpenGL着色器程序链接和使用。

### Introduction

此类支持写在OpenGL着色语言（ GLSL ）和OpenGL的/ ES着色语言（ GLSL / ES）着色器程序。

[QGLShader](qglshader.html)和QGLShaderProgram庇护程序员从编译和连接顶点和片段着色器的详细信息。

下面的示例创建使用附带的源顶点着色器程序`code`。一旦编译和链接，着色器程序是在当前激活[QGLContext](qglcontext.html)通过调用[QGLShaderProgram.bind](qglshaderprogram.html#bind)（）：

```
 [QGLShader](qglshader.html) shader([QGLShader](qglshader.html).Vertex);
 shader.compileSourceCode(code);

 QGLShaderProgram program(context);
 program.addShader(shader);
 program.link();

 program.bind();

```

### Writing portable shaders

着色器程序可能是因为不同的标准顶点属性和统一的变量支持水平难以跨越的OpenGL实现重用。特别是， GLSL / ES缺乏一切都存在于桌面OpenGL系统的标准变量：`gl_Vertex`，`gl_Normal`，`gl_Color`，等等。桌面OpenGL缺少可变预选赛`highp`，`mediump`和`lowp`。

该QGLShaderProgram类使得编写可移植着色器更容易的前缀与桌面OpenGL以下行的所有着色器程序的过程：

```
 #define highp
 #define mediump
 #define lowp

```

这使得它可以运行在桌面系统最GLSL / ES着色器程序。程序员应该限制自己只是功能，是目前在GLSL / ES ，避免标准的变量名只能在桌面上。

### Simple shader example

```
 program.addShaderFromSourceCode([QGLShader](qglshader.html).Vertex,
     "attribute highp vec4 vertex;\n"
     "uniform highp mat4 matrix;\n"
     "void main(void)\n"
     "{\n"
     "   gl_Position = matrix * vertex;\n"
     "}");
 program.addShaderFromSourceCode([QGLShader](qglshader.html).Fragment,
     "uniform mediump vec4 color;\n"
     "void main(void)\n"
     "{\n"
     "   gl_FragColor = color;\n"
     "}");
 program.link();
 program.bind();

 int vertexLocation = program.attributeLocation("vertex");
 int matrixLocation = program.uniformLocation("matrix");
 int colorLocation = program.uniformLocation("color");

```

有了上面的着色器程序活跃，我们可以得出一个绿色三角形如下：

```
 static GLfloat const triangleVertices[] = {
     60.0f,  10.0f,  0.0f,
     110.0f, 110.0f, 0.0f,
     10.0f,  110.0f, 0.0f
 };

 [QColor](qcolor.html) color(0, 255, 0, 255);

 QMatrix4x4 pmvMatrix;
 pmvMatrix.ortho(rect());

 program.enableAttributeArray(vertexLocation);
 program.setAttributeArray(vertexLocation, triangleVertices, 3);
 program.setUniformValue(matrixLocation, pmvMatrix);
 program.setUniformValue(colorLocation, color);

 glDrawArrays(GL_TRIANGLES, 0, 3);

 program.disableAttributeArray(vertexLocation);

```

### Binary shaders and programs

二进制着色器可以使用指定`glShaderBinary()`从返回值[QGLShader.shaderId](qglshader.html#shaderId)（ ） 。该[QGLShader](qglshader.html)实例包含二进制然后可以加入到着色器程序以[addShader](qglshaderprogram.html#addShader)（）和以通常的方式联系在一起[link](qglshaderprogram.html#link)（ ） 。

二进制程序可以使用指定`glProgramBinaryOES()`从返回值[programId](qglshaderprogram.html#programId)（ ） 。然后，应用程序应调用[link](qglshaderprogram.html#link)（），它会注意到，该方案已经指定和链接，让其他操作要在着色器程序进行。

* * *

## Method Documentation

```
QGLShaderProgram.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的着色器程序并将其附加到_parent_。该计划将是无效的，直到[addShader](qglshaderprogram.html#addShader)（）被调用。

在着色器程序将与当前相关联[QGLContext](qglcontext.html)。

**See also** [addShader](qglshaderprogram.html#addShader)（ ） 。

```
QGLShaderProgram.__init__ (self, QGLContext context, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的着色器程序并将其附加到_parent_。该计划将是无效的，直到[addShader](qglshaderprogram.html#addShader)（）被调用。

该着色器程序将与关联_context_。

**See also** [addShader](qglshaderprogram.html#addShader)（ ） 。

```
bool QGLShaderProgram.addShader (self, QGLShader shader)
```

增加了一个编译_shader_该着色器程序。返回True如果着色器可以添加，否则返回False。

所有权_shader_对象保持与来电者。它不会被删除时，这[QGLShaderProgram](qglshaderprogram.html)实例被删除。这允许调用者相同的着色器添加到多个着色器程序。

**See also** [addShaderFromSourceCode](qglshaderprogram.html#addShaderFromSourceCode)（ ）[addShaderFromSourceFile](qglshaderprogram.html#addShaderFromSourceFile)（ ）[removeShader](qglshaderprogram.html#removeShader)（ ）[link](qglshaderprogram.html#link)（）和[removeAllShaders](qglshaderprogram.html#removeAllShaders)（ ） 。

```
bool QGLShaderProgram.addShaderFromSourceCode (self, QGLShader.ShaderType type, QByteArray source)
```

编译_source_作为指定的着色器_type_并将其添加到该着色器程序。返回True如果编译成功，否则返回False。编译错误和警告将透过提供[log](qglshaderprogram.html#log)（ ） 。

该功能的目的是成为一个捷径可以快速添加顶点和片段着色器的着色器程序，而无需创建一个实例[QGLShader](qglshader.html)第一。

**See also** [addShader](qglshaderprogram.html#addShader)（ ）[addShaderFromSourceFile](qglshaderprogram.html#addShaderFromSourceFile)（ ）[removeShader](qglshaderprogram.html#removeShader)（ ）[link](qglshaderprogram.html#link)（ ）[log](qglshaderprogram.html#log)（）和[removeAllShaders](qglshaderprogram.html#removeAllShaders)（ ） 。

```
bool QGLShaderProgram.addShaderFromSourceCode (self, QGLShader.ShaderType type, QString source)
```

这是一个重载函数。

编译_source_作为指定的着色器_type_并将其添加到该着色器程序。返回True如果编译成功，否则返回False。编译错误和警告将透过提供[log](qglshaderprogram.html#log)（ ） 。

该功能的目的是成为一个捷径可以快速添加顶点和片段着色器的着色器程序，而无需创建一个实例[QGLShader](qglshader.html)第一。

**See also** [addShader](qglshaderprogram.html#addShader)（ ）[addShaderFromSourceFile](qglshaderprogram.html#addShaderFromSourceFile)（ ）[removeShader](qglshaderprogram.html#removeShader)（ ）[link](qglshaderprogram.html#link)（ ）[log](qglshaderprogram.html#log)（）和[removeAllShaders](qglshaderprogram.html#removeAllShaders)（ ） 。

```
bool QGLShaderProgram.addShaderFromSourceFile (self, QGLShader.ShaderType type, QString fileName)
```

编译的内容_fileName_作为指定的着色器_type_并将其添加到该着色器程序。返回True如果编译成功，否则返回False。编译错误和警告将透过提供[log](qglshaderprogram.html#log)（ ） 。

该功能的目的是成为一个捷径可以快速添加顶点和片段着色器的着色器程序，而无需创建一个实例[QGLShader](qglshader.html)第一。

**See also** [addShader](qglshaderprogram.html#addShader)（）和[addShaderFromSourceCode](qglshaderprogram.html#addShaderFromSourceCode)（ ） 。

```
int QGLShaderProgram.attributeLocation (self, QByteArray name)
```

返回属性的位置_name_在此着色器程序的参数列表。返回-1，如果_name_是不是这个着色器程序的有效属性。

**See also** [uniformLocation](qglshaderprogram.html#uniformLocation)（）和[bindAttributeLocation](qglshaderprogram.html#bindAttributeLocation)（ ） 。

```
int QGLShaderProgram.attributeLocation (self, QString name)
```

这是一个重载函数。

返回属性的位置_name_在此着色器程序的参数列表。返回-1，如果_name_是不是这个着色器程序的有效属性。

**See also** [uniformLocation](qglshaderprogram.html#uniformLocation)（）和[bindAttributeLocation](qglshaderprogram.html#bindAttributeLocation)（ ） 。

```
bool QGLShaderProgram.bind (self)
```

此着色器程序绑定到活动[QGLContext](qglcontext.html)并使其成为当前着色器程序。所有以前绑定的着色器程序被释放。这等同于调用`glUseProgram()`上[programId](qglshaderprogram.html#programId)（ ） 。返回True如果该程序已成功绑定，否则为False 。如果着色器程序还没有被链接，或者它需要被重新链接，该函数将调用[link](qglshaderprogram.html#link)（ ） 。

**See also** [link](qglshaderprogram.html#link)（）和[release](qglshaderprogram.html#release)（ ） 。

```
QGLShaderProgram.bindAttributeLocation (self, QByteArray name, int location)
```

绑定属性_name_到指定的_location_。此功能可调用的程序已被证实与之前或之后。还没有当程序被链接被明确约束的任何属性将被自动分配位置。

当这个函数被调用的程序被连接后，该程序将需要重新链接至使更改生效。

**See also** [attributeLocation](qglshaderprogram.html#attributeLocation)（ ） 。

```
QGLShaderProgram.bindAttributeLocation (self, QString name, int location)
```

这是一个重载函数。

绑定属性_name_到指定的_location_。此功能可调用的程序已被证实与之前或之后。还没有当程序被链接被明确约束的任何属性将被自动分配位置。

当这个函数被调用的程序被连接后，该程序将需要重新链接至使更改生效。

**See also** [attributeLocation](qglshaderprogram.html#attributeLocation)（ ） 。

```
QGLShaderProgram.disableAttributeArray (self, int location)
```

禁用顶点数组_location_在由以前调用启用此着色器程序[enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（ ） 。

**See also** [enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（ ）[setAttributeArray](qglshaderprogram.html#setAttributeArray)（ ）[setAttributeValue](qglshaderprogram.html#setAttributeValue)（）和[setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.disableAttributeArray (self, str name)
```

这是一个重载函数。

禁用顶点数组称为_name_在由以前调用启用此着色器程序[enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（ ） 。

**See also** [enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（ ）[setAttributeArray](qglshaderprogram.html#setAttributeArray)（ ）[setAttributeValue](qglshaderprogram.html#setAttributeValue)（）和[setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.enableAttributeArray (self, int location)
```

启用顶点数组_location_在这个shader程序，以便通过设置的值[setAttributeArray](qglshaderprogram.html#setAttributeArray)（ ）上_location_将用于由所述着色器程序。

**See also** [disableAttributeArray](qglshaderprogram.html#disableAttributeArray)（ ）[setAttributeArray](qglshaderprogram.html#setAttributeArray)（ ）[setAttributeValue](qglshaderprogram.html#setAttributeValue)（）和[setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.enableAttributeArray (self, str name)
```

这是一个重载函数。

使顶点数组称为_name_在这个shader程序，以便通过设置的值[setAttributeArray](qglshaderprogram.html#setAttributeArray)（ ）上_name_将用于由所述着色器程序。

**See also** [disableAttributeArray](qglshaderprogram.html#disableAttributeArray)（ ）[setAttributeArray](qglshaderprogram.html#setAttributeArray)（ ）[setAttributeValue](qglshaderprogram.html#setAttributeValue)（）和[setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
int QGLShaderProgram.geometryInputType (self)
```

返回几何着色器输入类型，如果活跃。

此参数将在下次程序连动效应。

此功能被引入Qt的4.7 。

**See also** [setGeometryInputType](qglshaderprogram.html#setGeometryInputType)（ ） 。

```
int QGLShaderProgram.geometryOutputType (self)
```

返回几何着色器输出类型，如果活跃。

此参数将在下次程序连动效应。

此功能被引入Qt的4.7 。

**See also** [setGeometryOutputType](qglshaderprogram.html#setGeometryOutputType)（ ） 。

```
int QGLShaderProgram.geometryOutputVertexCount (self)
```

返回顶点的当前几何着色器程序会产生，如果活跃的最大数目。

此参数生效ntext的时间程序链接。

此功能被引入Qt的4.7 。

**See also** [setGeometryOutputVertexCount](qglshaderprogram.html#setGeometryOutputVertexCount)（ ） 。

```
bool QGLShaderProgram.hasOpenGLShaderPrograms (QGLContext context = None)
```

否则返回False ，如果写在OpenGL着色语言（ GLSL ）着色器程序在该系统上都支持，则返回True 。

该_context_用于解析GLSL的扩展。如果_context_为null，则[QGLContext.currentContext](qglcontext.html#currentContext)（ ）被使用。

```
bool QGLShaderProgram.isLinked (self)
```

返回True如果着色器程序已被链接，否则为False 。

**See also** [link](qglshaderprogram.html#link)（ ） 。

```
bool QGLShaderProgram.link (self)
```

链接在一起，加入到这个计划与着色器[addShader](qglshaderprogram.html#addShader)（ ） 。返回True如果链接成功，否则返回False。如果链接失败，错误消息可以检索与[log](qglshaderprogram.html#log)（ ） 。

子类可以重载这个函数来初始化属性和统一的变量在特定着色器程序中使用。

如果着色器程序已经联系在一起，再调用这个函数将迫使它重新链接。

**See also** [addShader](qglshaderprogram.html#addShader)（）和[log](qglshaderprogram.html#log)（ ） 。

```
QString QGLShaderProgram.log (self)
```

在过去的返回所发生的错误和警告[link](qglshaderprogram.html#link)（）或[addShader](qglshaderprogram.html#addShader)（ ）和显式指定的源代码。

**See also** [link](qglshaderprogram.html#link)（ ） 。

```
int QGLShaderProgram.programId (self)
```

返回与此着色器程序相关联的OpenGL的标识符。

**See also** [QGLShader.shaderId](qglshader.html#shaderId)（ ） 。

```
QGLShaderProgram.release (self)
```

释放从当前活动的着色器程序[QGLContext](qglcontext.html)。这等同于调用`glUseProgram(0)`。

**See also** [bind](qglshaderprogram.html#bind)（ ） 。

```
QGLShaderProgram.removeAllShaders (self)
```

删除所有被添加到这个程序，以前的着色器。该[QGLShader](qglshader.html)如果他们在外部构造为着色器对象将不会被删除。[QGLShader](qglshader.html)这是由内部构造的对象[QGLShaderProgram](qglshaderprogram.html)将被删除。

**See also** [addShader](qglshaderprogram.html#addShader)（）和[removeShader](qglshaderprogram.html#removeShader)（ ） 。

```
QGLShaderProgram.removeShader (self, QGLShader shader)
```

移除_shader_从这个着色器程序。对象不会被删除。

**See also** [addShader](qglshaderprogram.html#addShader)（ ）[link](qglshaderprogram.html#link)（）和[removeAllShaders](qglshaderprogram.html#removeAllShaders)（ ） 。

```
QGLShaderProgram.setAttributeArray (self, int location, sequence values)
```

设置顶点数组_values_在上面的属性_location_在此着色器程序。该_tupleSize_表示每个顶点组件（4 1，2 ，3，或）的数量，以及_stride_表示顶点之间的字节数。默认_stride_零值表示该顶点被致密地填充_values_。

该阵列会变得活跃时[enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（ ）被调用的_location_。否则，使用指定的值[setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ）为_location_将被使用。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ）[setUniformValue](qglshaderprogram.html#setUniformValue)（ ）[enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（）和[disableAttributeArray](qglshaderprogram.html#disableAttributeArray)（ ） 。

```
QGLShaderProgram.setAttributeArray (self, str name, sequence values)
```

设置二维顶点数组_values_在上面的属性_location_在此着色器程序。该_stride_表示顶点之间的字节数。默认_stride_零值表示该顶点被致密地填充_values_。

该阵列会变得活跃时[enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（ ）被调用的_location_。否则，使用指定的值[setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ）为_location_将被使用。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ）[setUniformValue](qglshaderprogram.html#setUniformValue)（ ）[enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（）和[disableAttributeArray](qglshaderprogram.html#disableAttributeArray)（ ） 。

```
QGLShaderProgram.setAttributeBuffer (self, int location, int type, int offset, int tupleSize, int stride = 0)
```

设置在顶点属性值中的一个阵列_location_在此着色器程序，起始于一个特定的_offset_在当前绑定的顶点缓冲。该_stride_表示顶点之间的字节数。默认_stride_零值表示该顶点被密集的值的数组中。

该_type_表示元素的顶点值阵列中的类型，通常`GL_FLOAT`，`GL_UNSIGNED_BYTE`等。_tupleSize_表示每个顶点部件的数量：1，2 ，3，或4 。

该阵列会变得活跃时[enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（ ）被调用的_location_。否则，使用指定的值[setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ）为_location_将被使用。

此功能被引入Qt的4.7 。

**See also** [setAttributeArray](qglshaderprogram.html#setAttributeArray)（ ） 。

```
QGLShaderProgram.setAttributeBuffer (self, str name, int type, int offset, int tupleSize, int stride = 0)
```

这是一个重载函数。

设置在顶点属性值的数组，称为_name_在此着色器程序，起始于一个特定的_offset_在当前绑定的顶点缓冲。该_stride_表示顶点之间的字节数。默认_stride_零值表示该顶点被密集的值的数组中。

该_type_表示元素的顶点值阵列中的类型，通常`GL_FLOAT`，`GL_UNSIGNED_BYTE`等。_tupleSize_表示每个顶点部件的数量：1，2 ，3，或4 。

该阵列会变得活跃时[enableAttributeArray](qglshaderprogram.html#enableAttributeArray)（ ）被调用的_name_。否则，使用指定的值[setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ）为_name_将被使用。

此功能被引入Qt的4.7 。

**See also** [setAttributeArray](qglshaderprogram.html#setAttributeArray)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, int location, float value)
```

在设置该属性_location_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, int location, float x, float y)
```

在设置该属性_location_在目前情况下，以二维矢量（_x_，_y_） 。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, int location, float x, float y, float z)
```

在设置该属性_location_在当前上下文中的三维矢量（_x_，_y_，_z_） 。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, int location, float x, float y, float z, float w)
```

在设置该属性_location_在目前情况下的4D向量（_x_，_y_，_z_，_w_） 。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, int location, QVector2D value)
```

在设置该属性_location_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, int location, QVector3D value)
```

在设置该属性_location_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, int location, QVector4D value)
```

在设置该属性_location_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, int location, QColor value)
```

在设置该属性_location_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, str name, float value)
```

在设置该属性_location_在当前上下文中的内容_values_，其中包含_columns_元素，每个元素包括_rows_元素。该_rows_值应为1，2， 3，或4 。这个功能通常是用来设置矩阵值和列向量。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, str name, float x, float y)
```

这是一个重载函数。

所谓设置该属性_name_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, str name, float x, float y, float z)
```

这是一个重载函数。

所谓设置该属性_name_在目前情况下，以二维矢量（_x_，_y_） 。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, str name, float x, float y, float z, float w)
```

这是一个重载函数。

所谓设置该属性_name_在当前上下文中的三维矢量（_x_，_y_，_z_） 。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, str name, QVector2D value)
```

这是一个重载函数。

所谓设置该属性_name_在目前情况下的4D向量（_x_，_y_，_z_，_w_） 。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, str name, QVector3D value)
```

这是一个重载函数。

所谓设置该属性_name_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, str name, QVector4D value)
```

这是一个重载函数。

所谓设置该属性_name_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setAttributeValue (self, str name, QColor value)
```

这是一个重载函数。

所谓设置该属性_name_在目前情况下，以_value_。

**See also** [setUniformValue](qglshaderprogram.html#setUniformValue)（ ） 。

```
QGLShaderProgram.setGeometryInputType (self, int inputType)
```

设定从输入型_inputType_。

此参数将在下次程序连动效应。

**See also** [geometryInputType](qglshaderprogram.html#geometryInputType)（ ） 。

```
QGLShaderProgram.setGeometryOutputType (self, int outputType)
```

从几何着色器设置输出类型，如果活跃，_outputType_。

此参数将在下次程序连动效应。

此功能被引入Qt的4.7 。

**See also** [geometryOutputType](qglshaderprogram.html#geometryOutputType)（ ） 。

```
QGLShaderProgram.setGeometryOutputVertexCount (self, int count)
```

设置顶点的当前几何着色器程序会产生，如果活跃，最大数量_count_。

此参数将在下次程序连动效应。

此功能被引入Qt的4.7 。

**See also** [geometryOutputVertexCount](qglshaderprogram.html#geometryOutputVertexCount)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, int value)
```

设置在匀变速_location_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, float value)
```

设置在匀变速_location_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, float x, float y)
```

设置在匀变速_location_在目前情况下，以_value_。设置采样值时，此功能应该被使用。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, float x, float y, float z)
```

设置在匀变速_location_在目前情况下，以二维矢量（_x_，_y_） 。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, float x, float y, float z, float w)
```

设置在匀变速_location_在当前上下文中的三维矢量（_x_，_y_，_z_） 。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QVector2D value)
```

设置在匀变速_location_在目前情况下的4D向量（_x_，_y_，_z_，_w_） 。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QVector3D value)
```

设置在匀变速_location_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QVector4D value)
```

设置在匀变速_location_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QColor color)
```

设置在匀变速_location_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QPoint point)
```

设置在匀变速_location_在当前背景下的红色，绿色，蓝色和alpha分量_color_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QPointF point)
```

设置在匀变速_location_在当前上下文中的x和y坐标_point_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QSize size)
```

设置在匀变速_location_在当前上下文中的x和y坐标_point_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QSizeF size)
```

设置在匀变速_location_在目前情况下，以给定的宽度和高度_size_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix2x2 value)
```

设置在匀变速_location_在目前情况下，以给定的宽度和高度_size_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix2x3 value)
```

设置在匀变速_location_在目前情况下，以一个2x2的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix2x4 value)
```

设置在匀变速_location_在目前情况下，以一个2×3矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix3x2 value)
```

设置在匀变速_location_在目前情况下，以一个2x4的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix3x3 value)
```

设置在匀变速_location_在目前情况下，以一个3x2的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix3x4 value)
```

设置在匀变速_location_在目前情况下，以一个3x3矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix4x2 value)
```

设置在匀变速_location_在目前情况下，以一个3x4的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix4x3 value)
```

设置在匀变速_location_在目前情况下，以一个4×2矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QMatrix4x4 value)
```

设置在匀变速_location_在目前情况下，以一个4x3的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, int location, QTransform value)
```

设置在匀变速_location_在目前情况下，以一个4x4矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, int value)
```

设置在匀变速_location_在目前情况下，以一个3x3变换矩阵_value_被指定为一个[QTransform](qtransform.html)值。

要设置[QTransform](qtransform.html)值作为着色器，使用一个4x4矩阵`setUniformValue(location, QMatrix4x4(value))`。

```
QGLShaderProgram.setUniformValue (self, str name, float value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, float x, float y)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, float x, float y, float z)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以_value_。设置采样值时，此功能应该被使用。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, float x, float y, float z, float w)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以二维矢量（_x_，_y_） 。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QVector2D value)
```

这是一个重载函数。

设置叫做匀变速_name_在当前上下文中的三维矢量（_x_，_y_，_z_） 。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QVector3D value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下的4D向量（_x_，_y_，_z_，_w_） 。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QVector4D value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QColor color)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QPoint point)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QPointF point)
```

这是一个重载函数。

设置叫做匀变速_name_在当前背景下的红色，绿色，蓝色和alpha分量_color_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QSize size)
```

这是一个重载函数。

设置与统一的变量相关联_name_在当前上下文中的x和y坐标_point_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QSizeF size)
```

这是一个重载函数。

设置与统一的变量相关联_name_在当前上下文中的x和y坐标_point_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix2x2 value)
```

这是一个重载函数。

设置与统一的变量相关联_name_在目前情况下，以给定的宽度和高度_size_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix2x3 value)
```

这是一个重载函数。

设置与统一的变量相关联_name_在目前情况下，以给定的宽度和高度_size_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix2x4 value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以一个2x2的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix3x2 value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以一个2×3矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix3x3 value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以一个2x4的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)().

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix3x4 value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以一个3x2的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix4x2 value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以一个3x3矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix4x3 value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以一个3x4的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QMatrix4x4 value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以一个4×2矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValue (self, str name, QTransform value)
```

这是一个重载函数。

设置叫做匀变速_name_在目前情况下，以一个4x3的矩阵_value_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValueArray (self, int location, sequence values)
```

设置统一的变量数组_location_在目前情况下对_count_元素_values_。每个元素都有_tupleSize_组件。该_tupleSize_必须是1， 2，3，或4。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
QGLShaderProgram.setUniformValueArray (self, str name, sequence values)
```

设置统一的变量数组_location_在目前情况下对_count_元素_values_。

**See also** [setAttributeValue](qglshaderprogram.html#setAttributeValue)（ ） 。

```
list-of-QGLShader QGLShaderProgram.shaders (self)
```

返回已被添加到该着色器程序中所有着色器的使用列表[addShader](qglshaderprogram.html#addShader)（ ） 。

**See also** [addShader](qglshaderprogram.html#addShader)（）和[removeShader](qglshaderprogram.html#removeShader)（ ） 。

```
int QGLShaderProgram.uniformLocation (self, QByteArray name)
```

返回均匀的变量的位置_name_在此着色器程序的参数列表。返回-1，如果_name_是不是这个着色器程序一个有效的统一变量。

**See also** [attributeLocation](qglshaderprogram.html#attributeLocation)（ ） 。

```
int QGLShaderProgram.uniformLocation (self, QString name)
```

这是一个重载函数。

返回均匀的变量的位置_name_在此着色器程序的参数列表。返回-1，如果_name_是不是这个着色器程序一个有效的统一变量。

**See also** [attributeLocation](qglshaderprogram.html#attributeLocation)（ ） 。