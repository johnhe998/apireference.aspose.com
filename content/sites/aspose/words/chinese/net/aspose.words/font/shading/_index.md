---
title: Font.Shading
second_title: Aspose.Words for .NET API 参考
description: Font 财产. 返回一个 Shading 对象该对象引用字体的着色格式
type: docs
weight: 320
url: /zh/net/aspose.words/font/shading/
---
## Font.Shading property

返回一个 Shading 对象，该对象引用字体的着色格式。

```csharp
public Shading Shading { get; }
```

### 例子

展示如何将底纹应用到由文档构建器创建的文本。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Color = Color.White;

// 一种使使用我们的白色字体颜色创建的文本可见的方法
// 是应用背景阴影效果。
Shading shading = builder.Font.Shading;
shading.Texture = TextureIndex.TextureDiagonalUp;
shading.BackgroundPatternColor = Color.OrangeRed;
shading.ForegroundPatternColor = Color.DarkBlue;

builder.Writeln("White text on an orange background with a two-tone texture.");

doc.Save(ArtifactsDir + "Font.Shading.docx");
```

### 也可以看看

* class [Shading](../../shading/)
* class [Font](../)
* 命名空间 [Aspose.Words](../../font/)
* 部件 [Aspose.Words](../../../)


