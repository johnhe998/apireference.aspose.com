---
title: HyphenationOptions.HyphenationZone
second_title: Aspose.Words for .NET API 参考
description: HyphenationOptions 财产. 获取或设置距离右边距不希望连字的点的 1/20 的距离 此属性的默认值为 3600.25 英寸
type: docs
weight: 50
url: /zh/net/aspose.words.settings/hyphenationoptions/hyphenationzone/
---
## HyphenationOptions.HyphenationZone property

获取或设置距离右边距不希望连字的点的 1/20 的距离。 此属性的默认值为 360（0.25 英寸）。

```csharp
public int HyphenationZone { get; set; }
```

### 例子

显示如何配置自动断字。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 24;
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.HyphenationOptions.AutoHyphenation = true;
doc.HyphenationOptions.ConsecutiveHyphenLimit = 2;
doc.HyphenationOptions.HyphenationZone = 720;
doc.HyphenationOptions.HyphenateCaps = true;

doc.Save(ArtifactsDir + "Document.HyphenationOptions.docx");
```

### 也可以看看

* class [HyphenationOptions](../)
* 命名空间 [Aspose.Words.Settings](../../hyphenationoptions/)
* 部件 [Aspose.Words](../../../)


