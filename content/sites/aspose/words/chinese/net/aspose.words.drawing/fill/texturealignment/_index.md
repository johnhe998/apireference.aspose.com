---
title: Fill.TextureAlignment
second_title: Aspose.Words for .NET API 参考
description: Fill 财产. 获取或设置平铺纹理填充的对齐方式
type: docs
weight: 130
url: /zh/net/aspose.words.drawing/fill/texturealignment/
---
## Fill.TextureAlignment property

获取或设置平铺纹理填充的对齐方式。

```csharp
public TextureAlignment TextureAlignment { get; set; }
```

### 例子

显示如何填充和平铺形状内的纹理。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);

// 将纹理对齐应用于形状填充。
shape.Fill.PresetTextured(PresetTexture.Canvas);
shape.Fill.TextureAlignment = TextureAlignment.TopRight;

// 如果您想获得“TextureAlignment”，请使用合规性选项使用 DML 定义形状
// 文档保存后的属性。
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.TextureFill.docx", saveOptions);
```

### 也可以看看

* enum [TextureAlignment](../../texturealignment/)
* class [Fill](../)
* 命名空间 [Aspose.Words.Drawing](../../fill/)
* 部件 [Aspose.Words](../../../)


