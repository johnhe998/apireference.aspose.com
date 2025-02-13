---
title: Font.Emboss
second_title: Aspose.Words for .NET API 参考
description: Font 财产. 如果字体格式为浮雕则为真
type: docs
weight: 100
url: /zh/net/aspose.words/font/emboss/
---
## Font.Emboss property

如果字体格式为浮雕则为真。

```csharp
public bool Emboss { get; set; }
```

### 例子

展示如何对文本应用雕刻/浮雕效果。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 36;
builder.Font.Color = Color.LightBlue;

// 下面是使用阴影为文本应用类似 3D 效果的两种方法。
// 1 - 雕刻文字，使其看起来像字母沉入页面：
builder.Font.Engrave = true;

builder.Writeln("This text is engraved.");

// 2 - 浮雕文本使其看起来像从页面中弹出的字母：
builder.Font.Engrave = false;
builder.Font.Emboss = true;

builder.Writeln("This text is embossed.");

doc.Save(ArtifactsDir + "Font.EngraveEmboss.docx");
```

### 也可以看看

* class [Font](../)
* 命名空间 [Aspose.Words](../../font/)
* 部件 [Aspose.Words](../../../)


