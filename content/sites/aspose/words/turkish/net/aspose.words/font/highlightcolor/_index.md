---
title: Font.HighlightColor
second_title: Aspose.Words for .NET API Referansı
description: Font mülk. Vurgu işaretçi rengini alır veya ayarlar.
type: docs
weight: 150
url: /tr/net/aspose.words/font/highlightcolor/
---
## Font.HighlightColor property

Vurgu (işaretçi) rengini alır veya ayarlar.

```csharp
public Color HighlightColor { get; set; }
```

### Örnekler

Font özelliğini kullanarak bir metin akışının nasıl biçimlendirileceğini gösterir.

```csharp
Document doc = new Document();
Run run = new Run(doc, "Hello world!");

Aspose.Words.Font font = run.Font;
font.Name = "Courier New";
font.Size = 36;
font.HighlightColor = Color.Yellow;

doc.FirstSection.Body.FirstParagraph.AppendChild(run);
doc.Save(ArtifactsDir + "Font.CreateFormattedRun.docx");
```

### Ayrıca bakınız

* class [Font](../)
* ad alanı [Aspose.Words](../../font/)
* toplantı [Aspose.Words](../../../)


