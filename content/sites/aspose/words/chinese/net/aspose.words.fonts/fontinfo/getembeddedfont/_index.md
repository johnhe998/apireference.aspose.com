---
title: FontInfo.GetEmbeddedFont
second_title: Aspose.Words for .NET API 参考
description: FontInfo 方法. 获取特定的嵌入字体文件
type: docs
weight: 80
url: /zh/net/aspose.words.fonts/fontinfo/getembeddedfont/
---
## FontInfo.GetEmbeddedFont method

获取特定的嵌入字体文件。

```csharp
public byte[] GetEmbeddedFont(EmbeddedFontFormat format, EmbeddedFontStyle style)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| format | EmbeddedFontFormat | 指定要检索的字体格式。 |
| style | EmbeddedFontStyle | 指定要检索的字体样式。 |

### 返回值

退货`无效的`如果未嵌入指定的字体。

### 例子

演示如何从文档中提取嵌入字体，并将其保存到本地文件系统。

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfo embeddedFont = doc.FontInfos["Alte DIN 1451 Mittelschrift"];
byte[] embeddedFontBytes = embeddedFont.GetEmbeddedFont(EmbeddedFontFormat.OpenType, EmbeddedFontStyle.Regular);
File.WriteAllBytes(ArtifactsDir + "Alte DIN 1451 Mittelschrift.ttf", embeddedFontBytes);

// 嵌入的字体格式可能与.doc等其他格式不同。
// 在提取字体之前，我们需要知道正确的格式。
doc = new Document(MyDir + "Embedded font.doc");

Assert.IsNull(doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFont(EmbeddedFontFormat.OpenType, EmbeddedFontStyle.Regular));
Assert.IsNotNull(doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFont(EmbeddedFontFormat.EmbeddedOpenType, EmbeddedFontStyle.Regular));

// 此外，我们可以将来自 .doc 文档的嵌入式 OpenType 格式转换为 OpenType。
embeddedFontBytes = doc.FontInfos["Alte DIN 1451 Mittelschrift"].GetEmbeddedFontAsOpenType(EmbeddedFontStyle.Regular);

File.WriteAllBytes(ArtifactsDir + "Alte DIN 1451 Mittelschrift.otf", embeddedFontBytes);
```

### 也可以看看

* enum [EmbeddedFontFormat](../../embeddedfontformat/)
* enum [EmbeddedFontStyle](../../embeddedfontstyle/)
* class [FontInfo](../)
* 命名空间 [Aspose.Words.Fonts](../../fontinfo/)
* 部件 [Aspose.Words](../../../)


