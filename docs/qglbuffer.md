# QGLBuffer Class Reference

## [[QtOpenGL](index.htm) module]

该QGLBuffer类提供用于创建和管理GL缓冲区对象。[More...](#details)

### Types

*   `enum Access { ReadOnly, WriteOnly, ReadWrite }`
*   `enum Type { VertexBuffer, IndexBuffer, PixelPackBuffer, PixelUnpackBuffer }`
*   `enum UsagePattern { StreamDraw, StreamRead, StreamCopy, StaticDraw, ..., DynamicCopy }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, Type type)`
*   `__init__ (self, QGLBuffer other)`
*   `allocate (self, sip.voidptr data, int count)`
*   `allocate (self, int count)`
*   `bool bind (self)`
*   `int bufferId (self)`
*   `bool create (self)`
*   `destroy (self)`
*   `bool isCreated (self)`
*   `sip.voidptr map (self, Access access)`
*   `bool read (self, int offset, sip.voidptr data, int count)`
*   `release (self)`
*   `setUsagePattern (self, UsagePattern value)`
*   `int size (self)`
*   `Type type (self)`
*   `bool unmap (self)`
*   `UsagePattern usagePattern (self)`
*   `write (self, int offset, sip.voidptr data, int count)`

### Static Methods

*   `release (Type type)`

* * *

## Detailed Description

该QGLBuffer类提供用于创建和管理GL缓冲区对象。

缓冲对象在GL服务器创建，使客户端应用程序可避免上传顶点，索引，纹理图像数据等，他们需要每一次。

QGLBuffer对象可以被复制围绕作为参照相关GL缓冲对象：

```
 QGLBuffer buffer1(QGLBuffer.IndexBuffer);
 buffer1.create();

 QGLBuffer buffer2 = buffer1;

```

QGLBuffer进行浅拷贝时，对象被复制以这种方式，但没有实现副本上写的语义。原来的对象会受到影响每当副本被修改。

* * *

## Type Documentation

```
QGLBuffer.Access
```

这个枚举变量定义的访问模式[QGLBuffer.map](qglbuffer.html#map)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QGLBuffer.ReadOnly` | `0x88B8` | 该缓冲区将被映射为只读。 |
| `QGLBuffer.WriteOnly` | `0x88B9` | 该缓冲区将被映射为只写。 |
| `QGLBuffer.ReadWrite` | `0x88BA` | 该缓冲区将被映射为阅读和写作。 |

```
QGLBuffer.Type
```

这个枚举变量定义GL缓冲对象的创建与类型[QGLBuffer](qglbuffer.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QGLBuffer.VertexBuffer` | `0x8892` | 顶点缓冲对象指定顶点数组时使用。 |
| `QGLBuffer.IndexBuffer` | `0x8893` | 与使用索引缓冲区对象`glDrawElements()`。 |
| `QGLBuffer.PixelPackBuffer` | `0x88EB` | 自GL服务器读取像素数据的像素组缓存对象（例如，与`glReadPixels()`） 。下的OpenGL / ES不支持。 |
| `QGLBuffer.PixelUnpackBuffer` | `0x88EC` | 为像素数据写入到GL服务器（例如，以像素解包缓冲区对象`glTexImage2D()`） 。下的OpenGL / ES不支持。 |

```
QGLBuffer.UsagePattern
```

这个枚举变量定义的使用模式[QGLBuffer](qglbuffer.html)对象。

| Constant | Value | Description |
| --- | --- | --- |
| `QGLBuffer.StreamDraw` | `0x88E0` | 这些数据将被设置一次，用过几次的绘图操作。下OpenGL / ES 1.1 ，这是相同的StaticDraw 。 |
| `QGLBuffer.StreamRead` | `0x88E1` | 这些数据将被设置一次，用过几次读回数据从GL服务器。下的OpenGL / ES不支持。 |
| `QGLBuffer.StreamCopy` | `0x88E2` | 这些数据将被设置一次，用过几次读取数据从GL服务器回在进一步的绘制操作使用。下的OpenGL / ES不支持。 |
| `QGLBuffer.StaticDraw` | `0x88E4` | 这些数据将被设置一次，多次使用的绘图操作。 |
| `QGLBuffer.StaticRead` | `0x88E5` | 这些数据将被设置一次，多次使用读回数据从GL服务器。下的OpenGL / ES不支持。 |
| `QGLBuffer.StaticCopy` | `0x88E6` | 这些数据将被设置一次，多次使用，用于读取数据从GL服务器回在进一步的绘制操作使用。下的OpenGL / ES不支持。 |
| `QGLBuffer.DynamicDraw` | `0x88E8` | 该数据将被反复修改和多次使用的绘图操作。 |
| `QGLBuffer.DynamicRead` | `0x88E9` | 该数据将被反复修改和多次使用读回数据从GL服务器。下的OpenGL / ES不支持。 |
| `QGLBuffer.DynamicCopy` | `0x88EA` | 该数据将被反复修改和多次使用，用于读取数据从GL服务器回在进一步的绘制操作使用。下的OpenGL / ES不支持。 |

* * *

## Method Documentation

```
QGLBuffer.__init__ (self)
```

构造类型的一个新的缓冲区对象[QGLBuffer.VertexBuffer](qglbuffer.html#Type-enum)。

注：此构造函数只是创建[QGLBuffer](qglbuffer.html)实例。在GL服务器的实际缓冲区对象不创建，直到[create](qglbuffer.html#create)（）被调用。

**See also** [create](qglbuffer.html#create)（ ） 。

```
QGLBuffer.__init__ (self, Type type)
```

构建了一个新的缓冲区对象_type_。

注：此构造函数只是创建[QGLBuffer](qglbuffer.html)实例。在GL服务器的实际缓冲区对象不创建，直到[create](qglbuffer.html#create)（）被调用。

**See also** [create](qglbuffer.html#create)（ ） 。

```
QGLBuffer.__init__ (self, QGLBuffer other)
```

构造的浅表副本_other_。

注意：[QGLBuffer](qglbuffer.html)没有实现副本上写的语义，所以_other_将受到影响每当副本被修改。

```
QGLBuffer.allocate (self, sip.voidptr data, int count)
```

中分配_count_的空间的缓冲区中的字节，并将其初始化内容_data_。任何以前的内容将被删除。

假定[create](qglbuffer.html#create)（ ）被调用这个缓冲区，它已经绑定到当前的上下文。

**See also** [create](qglbuffer.html#create)（ ）[read](qglbuffer.html#read)（）和[write](qglbuffer.html#write)（ ） 。

```
QGLBuffer.allocate (self, int count)
```

这是一个重载函数。

中分配_count_的空间字节的缓冲区。任何以前的内容将被删除。

假定[create](qglbuffer.html#create)（ ）被调用这个缓冲区，它已经绑定到当前的上下文。

**See also** [create](qglbuffer.html#create)（）和[write](qglbuffer.html#write)（ ） 。

```
bool QGLBuffer.bind (self)
```

结合与此对象到当前的GL上下文相关联的缓冲区。如果结合是不可能的，通常是因为返回False[type](qglbuffer.html#type)（ ）不支持此GL实现。

该缓冲区必须被绑定到同一个[QGLContext](qglcontext.html)当电流[create](qglbuffer.html#create)（ ）被调用，或到另一个[QGLContext](qglcontext.html)这是分享它。否则为False将被从这个函数返回。

**See also** [release](qglbuffer.html#release)（）和[create](qglbuffer.html#create)（ ） 。

```
int QGLBuffer.bufferId (self)
```

返回与该缓冲区关联的GL标识符;如果缓冲区尚未创建为零。

**See also** [isCreated](qglbuffer.html#isCreated)（ ） 。

```
bool QGLBuffer.create (self)
```

在创建GL服务器的缓冲区对象。如果在创建对象，则返回True ，否则返回False 。

此函数必须调用当前[QGLContext](qglcontext.html)。该缓冲区将被绑定到，可以在这方面（或与它共享的任何其他情况下）才能使用。

这个函数将返回False ，如果GL实现不支持的缓冲区，或者是没有电流[QGLContext](qglcontext.html)。

**See also** [isCreated](qglbuffer.html#isCreated)（ ）[allocate](qglbuffer.html#allocate)（ ）[write](qglbuffer.html#write)（）和[destroy](qglbuffer.html#destroy)（ ） 。

```
QGLBuffer.destroy (self)
```

摧毁这个缓冲区对象，包括GL服务器所使用的存储。到缓冲区中的所有引用都将变成无效。

```
bool QGLBuffer.isCreated (self)
```

如果这个缓冲区已经建立，则返回True ，否则返回False 。

**See also** [create](qglbuffer.html#create)（）和[destroy](qglbuffer.html#destroy)（ ） 。

```
sip.voidptr QGLBuffer.map (self, Access access)
```

这个映射缓冲区的内容到应用程序的内存空间，并返回一个指向它的指针。返回null ，如果内存映射是不可能的。该_access_参数表示将要执行的访问类型。

假定[create](qglbuffer.html#create)（ ）被调用这个缓冲区，它已经绑定到当前的上下文。

此功能仅是下的OpenGL / ES的支持，如果`GL_OES_mapbuffer`扩展出现。

**See also** [unmap](qglbuffer.html#unmap)（ ）[create](qglbuffer.html#create)（）和[bind](qglbuffer.html#bind)（ ） 。

```
bool QGLBuffer.read (self, int offset, sip.voidptr data, int count)
```

读取_count_在这个缓冲区起始字节_offset_成_data_。如果不支持从缓冲区读取错误;在成功时返回真。下的OpenGL / ES不支持的缓冲区读取。

据推测，此缓冲区已被绑定到当前上下文。

**See also** [write](qglbuffer.html#write)（）和[bind](qglbuffer.html#bind)（ ） 。

```
QGLBuffer.release (self)
```

释放与从目前的GL上下文此对象关联的缓冲区。

这个函数必须被调用，使用相同的[QGLContext](qglcontext.html)电流时[bind](qglbuffer.html#bind)（ ）被调用的缓冲区。

**See also** [bind](qglbuffer.html#bind)（ ） 。

```
QGLBuffer.release (Type type)
```

释放与相关联的缓冲_type_在当前的[QGLContext](qglcontext.html)。

此功能是直接调用`glBindBuffer(type, 0)`使用时，调用者不知道哪些[QGLBuffer](qglbuffer.html)已经被绑定到上下文，但要确保它被释放。

```
 [QGLBuffer](qglbuffer.html).release([QGLBuffer](qglbuffer.html).VertexBuffer);

```

```
QGLBuffer.setUsagePattern (self, UsagePattern value)
```

设置此缓冲区对象的使用模式_value_。这个函数必须在被调用[allocate](qglbuffer.html#allocate)（）或[write](qglbuffer.html#write)（ ） 。

**See also** [usagePattern](qglbuffer.html#usagePattern)（ ）[allocate](qglbuffer.html#allocate)（）和[write](qglbuffer.html#write)（ ） 。

```
int QGLBuffer.size (self)
```

返回数据的大小在此缓冲液中，用于读取操作。返回-1，如果读取缓冲区的大小是不支持，或者缓冲尚未建立。

据推测，此缓冲区已被绑定到当前上下文。

**See also** [isCreated](qglbuffer.html#isCreated)（）和[bind](qglbuffer.html#bind)（ ） 。

```
Type QGLBuffer.type (self)
```

[

返回缓冲区的当前对象表示的类型。

```
bool QGLBuffer.unmap (self)
```

](qglbuffer.html#Type-enum)

[取消映射缓冲区它被映射到应用程序的内存空间与以前调用后](qglbuffer.html#Type-enum)[map](qglbuffer.html#map)（ ） 。返回True如果取消映射成功，否则返回False 。

据推测，此缓冲区已被绑定到当前上下文，它先前被映射到[map](qglbuffer.html#map)（ ） 。

此功能仅是下的OpenGL / ES的支持，如果`GL_OES_mapbuffer`扩展出现。

**See also** [map](qglbuffer.html#map)（ ） 。

```
UsagePattern QGLBuffer.usagePattern (self)
```

[](qglbuffer.html#UsagePattern-enum)

[返回此缓冲区对象的使用模式。缺省值是](qglbuffer.html#UsagePattern-enum)[StaticDraw](qglbuffer.html#UsagePattern-enum)。

**See also** [setUsagePattern](qglbuffer.html#setUsagePattern)（ ） 。

```
QGLBuffer.write (self, int offset, sip.voidptr data, int count)
```

替换_count_这个缓冲区的字节开始_offset_同的内容_data_。在缓冲区内的任何其他字节将保持不变。

假定[create](qglbuffer.html#create)（ ）被调用这个缓冲区，它已经绑定到当前的上下文。

**See also** [create](qglbuffer.html#create)（ ）[read](qglbuffer.html#read)（）和[allocate](qglbuffer.html#allocate)（ ） 。