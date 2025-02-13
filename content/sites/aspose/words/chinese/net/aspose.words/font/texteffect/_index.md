---
title: Font.TextEffect
second_title: Aspose.Words for .NET API 参考
description: Font 财产. 获取或设置字体动画效果
type: docs
weight: 450
url: /zh/net/aspose.words/font/texteffect/
---
## Font.TextEffect property

获取或设置字体动画效果。

```csharp
public TextEffect TextEffect { get; set; }
```

### 例子

展示如何将视觉效果应用于跑步。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 36;
builder.Font.TextEffect = TextEffect.SparkleText;

builder.Writeln("Text with a sparkle effect.");

// 旧版本的 Microsoft Word 仅支持字体动画效果。
doc.Save(ArtifactsDir + "Font.SparklingText.doc");
```

### 也可以看看

* enum [TextEffect](../../texteffect/)
* class [Font](../)
* 命名空间 [Aspose.Words](../../font/)
* 部件 [Aspose.Words](../../../)


