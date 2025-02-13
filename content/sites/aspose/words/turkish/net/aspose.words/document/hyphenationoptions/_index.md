---
title: Document.HyphenationOptions
second_title: Aspose.Words for .NET API Referansı
description: Document mülk. Belge tireleme seçeneklerine erişim sağlar.
type: docs
weight: 210
url: /tr/net/aspose.words/document/hyphenationoptions/
---
## Document.HyphenationOptions property

Belge tireleme seçeneklerine erişim sağlar.

```csharp
public HyphenationOptions HyphenationOptions { get; }
```

### Örnekler

Otomatik tirelemenin nasıl yapılandırılacağını gösterir.

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

### Ayrıca bakınız

* class [HyphenationOptions](../../../aspose.words.settings/hyphenationoptions/)
* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


