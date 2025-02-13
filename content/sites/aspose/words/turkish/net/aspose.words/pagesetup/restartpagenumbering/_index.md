---
title: PageSetup.RestartPageNumbering
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Doğru sayfa numaralandırma bölümün başında yeniden başlarsa.
type: docs
weight: 350
url: /tr/net/aspose.words/pagesetup/restartpagenumbering/
---
## PageSetup.RestartPageNumbering property

**Doğru** sayfa numaralandırma bölümün başında yeniden başlarsa.

```csharp
public bool RestartPageNumbering { get; set; }
```

### Notlar

olarak ayarlanırsa **yanlış** , **Sayfa Numaralandırmayı Yeniden Başlat**özellik the öğesini geçersiz kılar[`PageStartingNumber`](../pagestartingnumber/) özellik, böylece sayfa numaralandırma önceki bölümden devam edebilir.

### Örnekler

Bir bölümde sayfa numaralandırmanın nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1, page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Section 1, page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Section 1, page 3.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Writeln("Section 2, page 1.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Section 2, page 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Section 2, page 3.");

// Belge oluşturucuyu ilk bölümün birincil başlığına taşıyın,
// o bölümdeki her sayfanın görüntüleneceği.
builder.MoveToSection(0);
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Geçerli sayfanın numarasını gösterecek bir SAYFA alanı ekleyin.
builder.Write("Page ");
builder.InsertField("PAGE", "");

// Bölümü, SAYFA alanlarının gösterdiği sayfa sayısının 5'ten başlamasını sağlayacak şekilde yapılandırın.
// Ayrıca, tüm SAYFA alanlarını, büyük Romen rakamları kullanarak sayfa numaralarını gösterecek şekilde yapılandırın.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.RestartPageNumbering = true;
pageSetup.PageStartingNumber = 5;
pageSetup.PageNumberStyle = NumberStyle.UppercaseRoman;

// İkinci bölüm için başka bir SAYFA alanıyla başka bir birincil başlık oluşturun.
builder.MoveToSection(1);
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write(" - ");
builder.InsertField("PAGE", "");
builder.Write(" - ");

// SAYFA alanlarının gösterdiği sayfa sayısının 10'dan başlaması için bölümü yapılandırın.
// Ayrıca, tüm SAYFA alanlarını Arapça sayıları kullanarak sayfa numaralarını gösterecek şekilde yapılandırın.
pageSetup = doc.Sections[1].PageSetup;
pageSetup.PageStartingNumber = 10;
pageSetup.RestartPageNumbering = true;
pageSetup.PageNumberStyle = NumberStyle.Arabic;

doc.Save(ArtifactsDir + "PageSetup.PageNumbering.docx");
```

### Ayrıca bakınız

* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


