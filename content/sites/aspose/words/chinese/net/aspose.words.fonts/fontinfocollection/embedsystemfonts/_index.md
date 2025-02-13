---
title: FontInfoCollection.EmbedSystemFonts
second_title: Aspose.Words for .NET API 参考
description: FontInfoCollection 财产. 指定是否将系统字体嵌入到文档中 此属性的默认值为 错误的.
type: docs
weight: 20
url: /zh/net/aspose.words.fonts/fontinfocollection/embedsystemfonts/
---
## FontInfoCollection.EmbedSystemFonts property

指定是否将系统字体嵌入到文档中。 此属性的默认值为 **错误的**.

此选项仅在以下情况下有效[`EmbedTrueTypeFonts`](../embedtruetypefonts/)选项设置为 **真的**.

```csharp
public bool EmbedSystemFonts { get; set; }
```

### 评论

将此属性设置为`真的`如果用户在东亚系统 上并且想要创建一个文档，该文档可供在其系统上没有该 语言字体的其他人可读，这将非常有用。例如，日文系统上的用户可以选择在文档中嵌入 the 字体，以便日文文档在所有系统上都可读。

此选项仅适用于 DOC、DOCX 和 RTF 格式。

### 例子

显示如何使用嵌入的 TrueType 字体保存文档。

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### 也可以看看

* class [FontInfoCollection](../)
* 命名空间 [Aspose.Words.Fonts](../../fontinfocollection/)
* 部件 [Aspose.Words](../../../)


