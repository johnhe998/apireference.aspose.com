---
title: PageSetup.EndnoteOptions
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Bu bölümdeki son notların numaralandırılmasını ve konumlandırılmasını kontrol eden seçenekler sunar.
type: docs
weight: 120
url: /tr/net/aspose.words/pagesetup/endnoteoptions/
---
## PageSetup.EndnoteOptions property

Bu bölümdeki son notların numaralandırılmasını ve konumlandırılmasını kontrol eden seçenekler sunar.

```csharp
public EndnoteOptions EndnoteOptions { get; }
```

### Örnekler

Bir bölümdeki dipnotları/son notları etkileyen seçeneklerin nasıl yapılandırılacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote reference text.");

// Numaralandırmayı 1'den yeniden başlatmak için ilk bölümdeki tüm dipnotları yapılandırın
// her yeni sayfada ve her sayfadaki metnin hemen altında kendilerini gösterirler.
FootnoteOptions footnoteOptions = doc.Sections[0].PageSetup.FootnoteOptions;
footnoteOptions.Position = FootnotePosition.BeneathText;
footnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
footnoteOptions.StartNumber = 1;

builder.Write(" Hello again.");
builder.InsertFootnote(FootnoteType.Footnote, "Endnote reference text.");

// Bölüm boyunca sürekli bir sayım sağlamak için ilk bölümdeki tüm son notları yapılandırın,
// 1'den başlayarak. Ayrıca, hepsini belgenin sonunda toplanmış olarak görünecek şekilde ayarlayın.
EndnoteOptions endnoteOptions = doc.Sections[0].PageSetup.EndnoteOptions;
endnoteOptions.Position = EndnotePosition.EndOfDocument;
endnoteOptions.RestartRule = FootnoteNumberingRule.Continuous;
endnoteOptions.StartNumber = 1;

doc.Save(ArtifactsDir + "PageSetup.FootnoteOptions.docx");
```

### Ayrıca bakınız

* class [EndnoteOptions](../../../aspose.words.notes/endnoteoptions/)
* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


