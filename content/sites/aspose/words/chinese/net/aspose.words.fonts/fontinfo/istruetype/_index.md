---
title: FontInfo.IsTrueType
second_title: Aspose.Words for .NET API 参考
description: FontInfo 财产. 表示此字体是 TrueType 或 OpenType 字体而不是光栅或矢量字体 默认为 true
type: docs
weight: 40
url: /zh/net/aspose.words.fonts/fontinfo/istruetype/
---
## FontInfo.IsTrueType property

表示此字体是 TrueType 或 OpenType 字体，而不是光栅或矢量字体。 默认为 true。

```csharp
public bool IsTrueType { get; set; }
```

### 例子

显示如何打印文档中存在的字体的详细信息。

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// 打印文档中所有使用和未使用的字体。
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

### 也可以看看

* class [FontInfo](../)
* 命名空间 [Aspose.Words.Fonts](../../fontinfo/)
* 部件 [Aspose.Words](../../../)


