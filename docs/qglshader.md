# QGLShader Class Reference

## [[QtOpenGL](index.htm) module]

该QGLShader类允许的OpenGL着色器进行编译。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `class **[ShaderType](index.htm)**`
*   `enum ShaderTypeBit { Vertex, Fragment, Geometry }`

### Methods

*   `__init__ (self, ShaderType type, QObject parent = None)`
*   `__init__ (self, ShaderType type, QGLContext context, QObject parent = None)`
*   `bool compileSourceCode (self, QByteArray source)`
*   `bool compileSourceCode (self, QString source)`
*   `bool compileSourceFile (self, QString fileName)`
*   `bool isCompiled (self)`
*   `QString log (self)`
*   `int shaderId (self)`
*   `ShaderType shaderType (self)`
*   `QByteArray sourceCode (self)`

### Static Methods

*   `bool hasOpenGLShaders (ShaderType type, QGLContext context = None)`

* * *

## Detailed Description

该QGLShader类允许的OpenGL着色器进行编译。

此类支持写在OpenGL着色语言（ GLSL ）和OpenGL的/ ES着色语言（ GLSL / ES ）的着色器。

QGLShader和[QGLShaderProgram](qglshaderprogram.html)庇护程序员的编译和连接顶点和片段着色器的详细信息。

* * *

## Type Documentation

```
QGLShader.ShaderTypeBit
```

这个枚举指定的类型[QGLShader](qglshader.html)正在被创建。

| Constant | Value | Description |
| --- | --- | --- |
| `QGLShader.Vertex` | `0x0001` | 顶点着色器编写的OpenGL着色语言（ GLSL ） 。 |
| `QGLShader.Fragment` | `0x0002` | 片段着色器编写的OpenGL着色语言（ GLSL ） 。 |
| `QGLShader.Geometry` | `0x0004` | 写在OpenGL着色语言（ GLSL ），几何着色器的基础上， GL_EXT_geometry_shader4扩展。 |

该ShaderType类型是一个typedef为[QFlags](index.htm)\u003cShaderTypeBit\u003e 。它存储ShaderTypeBit值的或组合。

* * *

## Method Documentation

```
QGLShader.__init__ (self, ShaderType type, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QGLShader](qglshader.html)指定的对象_type_并重视它_parent_。如果不支持着色器程序，[QGLShaderProgram.hasOpenGLShaderPrograms](qglshaderprogram.html#hasOpenGLShaderPrograms)（ ）将返回False 。

此构造函数通常后跟调用[compileSourceCode](qglshader.html#compileSourceCode)（）或[compileSourceFile](qglshader.html#compileSourceFile)（ ） 。

着色器将与当前相关联[QGLContext](qglcontext.html)。

**See also** [compileSourceCode](qglshader.html#compileSourceCode)（）和[compileSourceFile](qglshader.html#compileSourceFile)（ ） 。

```
QGLShader.__init__ (self, ShaderType type, QGLContext context, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QGLShader](qglshader.html)指定的对象_type_并重视它_parent_。如果不支持着色器程序，然后[QGLShaderProgram.hasOpenGLShaderPrograms](qglshaderprogram.html#hasOpenGLShaderPrograms)（ ）将返回False 。

此构造函数通常后跟调用[compileSourceCode](qglshader.html#compileSourceCode)（）或[compileSourceFile](qglshader.html#compileSourceFile)（ ） 。

着色器将与相关联_context_。

**See also** [compileSourceCode](qglshader.html#compileSourceCode)（）和[compileSourceFile](qglshader.html#compileSourceFile)（ ） 。

```
bool QGLShader.compileSourceCode (self, QByteArray source)
```

设置_source_码本着色器和编译它。返回True如果源被成功编译，否则返回False。

**See also** [compileSourceFile](qglshader.html#compileSourceFile)（ ） 。

```
bool QGLShader.compileSourceCode (self, QString source)
```

这是一个重载函数。

设置_source_码本着色器和编译它。返回True如果源被成功编译，否则返回False。

**See also** [compileSourceFile](qglshader.html#compileSourceFile)（ ） 。

```
bool QGLShader.compileSourceFile (self, QString fileName)
```

设置此着色器中的内容的源代码_fileName_并编译它。返回True如果文件可以被打开，源代码编译，否则返回False。

**See also** [compileSourceCode](qglshader.html#compileSourceCode)（ ） 。

```
bool QGLShader.hasOpenGLShaders (ShaderType type, QGLContext context = None)
```

返回True如果类型的着色器程序_type_否则为False ;此系统上都支持。

该_context_用于解析GLSL的扩展。如果_context_为null，则[QGLContext.currentContext](qglcontext.html#currentContext)（ ）被使用。

此功能被引入Qt的4.7 。

```
bool QGLShader.isCompiled (self)
```

返回True如果着色器已被编译，否则为False 。

**See also** [compileSourceCode](qglshader.html#compileSourceCode)（）和[compileSourceFile](qglshader.html#compileSourceFile)（ ） 。

```
QString QGLShader.log (self)
```

返回上次编译期间发生的错误和警告。

**See also** [compileSourceCode](qglshader.html#compileSourceCode)（）和[compileSourceFile](qglshader.html#compileSourceFile)（ ） 。

```
int QGLShader.shaderId (self)
```

返回与此相关的着色器OpenGL的标识符。

**See also** [QGLShaderProgram.programId](qglshaderprogram.html#programId)（ ） 。

```
ShaderType QGLShader.shaderType (self)
```

[

返回此着色器的类型。

](index.htm)

```
QByteArray QGLShader.sourceCode (self)
```

[

返回的源代码着色器。

](qbytearray.html)

[**See also**](qbytearray.html) [compileSourceCode](qglshader.html#compileSourceCode)（ ） 。