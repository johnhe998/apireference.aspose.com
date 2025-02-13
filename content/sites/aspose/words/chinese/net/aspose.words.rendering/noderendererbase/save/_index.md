---
title: NodeRendererBase.Save
second_title: Aspose.Words for .NET API 参考
description: NodeRendererBase 方法. 将形状渲染成图像并保存到文件中
type: docs
weight: 90
url: /zh/net/aspose.words.rendering/noderendererbase/save/
---
## Save(string, ImageSaveOptions) {#save_1}

将形状渲染成图像并保存到文件中。

```csharp
public void Save(string fileName, ImageSaveOptions saveOptions)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| fileName | String | 图像文件的名称。如果具有指定名称的文件已存在，则覆盖现有文件。 |
| saveOptions | ImageSaveOptions | 指定控制如何渲染和保存形状的选项。可以为空。 |

### 例子

演示如何将 Office Math 对象呈现到本地文件系统中的图像文件中。

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// 创建一个“ImageSaveOptions”对象传递给节点渲染器的“Save”方法进行修改
// 它如何将 OfficeMath 节点呈现为图像。
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// 将“Scale”属性设置为 5，以将对象渲染为其原始大小的五倍。
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### 也可以看看

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* 命名空间 [Aspose.Words.Rendering](../../noderendererbase/)
* 部件 [Aspose.Words](../../../)

---

## Save(Stream, ImageSaveOptions) {#save}

将形状渲染成图像并保存到流中。

```csharp
public void Save(Stream stream, ImageSaveOptions saveOptions)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| stream | Stream | 保存形状图像的流。 |
| saveOptions | ImageSaveOptions | 指定控制如何渲染和保存形状的选项。可以为null。 如果为null，图像将保存为PNG格式。 |

### 例子

演示如何使用形状渲染器将形状导出到本地文件系统中的文件。

```csharp
Document doc = new Document(MyDir + "Various shapes.docx");
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(7, shapes.Length);

// 文档中有 7 个形状，包括一组形状和 2 个子形状。
// 我们会将每个形状渲染到本地文件系统中的一个图像文件中
// 同时忽略组形状，因为它们没有外观。
// 这将产生 6 个图像文件。
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>())
{
    ShapeRenderer renderer = shape.GetShapeRenderer();
    ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
    renderer.Save(ArtifactsDir + $"Shape.RenderAllShapes.{shape.Name}.png", options);
}
```

### 也可以看看

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* 命名空间 [Aspose.Words.Rendering](../../noderendererbase/)
* 部件 [Aspose.Words](../../../)


