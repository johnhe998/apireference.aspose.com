---
title: PageSetup.LineNumberCountBy
second_title: Aspose.Words for .NET API Referansı
description: PageSetup mülk. Satır numaraları için sayısal artışı döndürür veya ayarlar.
type: docs
weight: 210
url: /tr/net/aspose.words/pagesetup/linenumbercountby/
---
## PageSetup.LineNumberCountBy property

Satır numaraları için sayısal artışı döndürür veya ayarlar.

```csharp
public int LineNumberCountBy { get; set; }
```

### Örnekler

Bir bölüm için satır numaralandırmanın nasıl etkinleştirileceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bölümün metin satırlarının solundaki sayıları görüntülemek için bölümün PageSetup nesnesini kullanabiliriz.
// Bu, List nesnesiyle aynı davranıştır,
// ancak tüm bölümü kapsar ve metni hiçbir şekilde değiştirmez.
// Bölümümüz her yeni sayfada numaralandırmayı 1'den yeniden başlatacak ve numarayı gösterecek,
// 3'ün katı ise, satırın solunda 50pt.
PageSetup pageSetup = builder.PageSetup;
pageSetup.LineStartingNumber = 1;
pageSetup.LineNumberCountBy = 3;
pageSetup.LineNumberRestartMode = LineNumberRestartMode.RestartPage;
pageSetup.LineNumberDistanceFromText = 50.0d;

for (int i = 1; i <= 25; i++)
    builder.Writeln($"Line {i}.");

// Satır sayacı, "SuppressLineNumbers" bayrağı "true" olarak ayarlanmış herhangi bir paragrafı atlayacaktır.
// Bu paragraf 3'ün katı olan 15. satırdadır ve bu nedenle normalde bir satır numarası görüntüler.
// Bölümün satır sayacı da bu satırı yok sayar, sonraki satırı 15. satır olarak kabul eder,
// ve o noktadan itibaren saymaya devam edin.
doc.FirstSection.Body.Paragraphs[14].ParagraphFormat.SuppressLineNumbers = true;

doc.Save(ArtifactsDir + "PageSetup.LineNumbers.docx");
```

### Ayrıca bakınız

* class [PageSetup](../)
* ad alanı [Aspose.Words](../../pagesetup/)
* toplantı [Aspose.Words](../../../)


