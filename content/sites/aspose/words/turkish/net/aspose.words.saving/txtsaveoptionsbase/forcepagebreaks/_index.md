---
title: TxtSaveOptionsBase.ForcePageBreaks
second_title: Aspose.Words for .NET API Referansı
description: TxtSaveOptionsBase mülk. Dışa aktarma sırasında sayfa sonlarının korunup korunmayacağını belirtmeye izin verir.
type: docs
weight: 30
url: /tr/net/aspose.words.saving/txtsaveoptionsbase/forcepagebreaks/
---
## TxtSaveOptionsBase.ForcePageBreaks property

Dışa aktarma sırasında sayfa sonlarının korunup korunmayacağını belirtmeye izin verir.

Varsayılan değer **yanlış**.

```csharp
public bool ForcePageBreaks { get; set; }
```

### Notlar

Özellik, yalnızca bir belgeye açıkça eklenen sayfa sonlarını etkiler. MS Word'ün her sayfanın sonuna otomatik olarak eklediği sayfa sonlarıyla ilgili değildir.

### Örnekler

Bir belgeyi düz metne dışa aktarırken sayfa sonlarının korunup korunmayacağının nasıl belirleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Page 1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page 3");

// Belgenin "Kaydet" kısmına geçirebileceğimiz bir "TxtSaveOptions" nesnesi oluşturun
// belgeyi düz metne kaydetme şeklimizi değiştirme yöntemi.
TxtSaveOptions saveOptions = new TxtSaveOptions();

// Aspose.Words "Document" nesnelerinde tıpkı Microsoft Word belgelerinde olduğu gibi sayfa sonları bulunur.
// ".txt" gibi kaydetme biçimleri, sayfa sonu olmayan sürekli bir metin gövdesidir.
// Tüm sayfa sonlarını '\f' karakterleri biçiminde korumak için "ForcePageBreaks" özelliğini "true" olarak ayarlayın.
// Tüm sayfa sonlarını atmak için "ForcePageBreaks" özelliğini "false" olarak ayarlayın.
saveOptions.ForcePageBreaks = forcePageBreaks;

doc.Save(ArtifactsDir + "TxtSaveOptions.PageBreaks.txt", saveOptions);

// Sayfa sonları olan bir düz metin belgesi yüklersek,
// "Belge" nesnesi, gövdeyi sayfalara bölmek için bunları kullanır.
doc = new Document(ArtifactsDir + "TxtSaveOptions.PageBreaks.txt");

Assert.AreEqual(forcePageBreaks ? 3 : 1, doc.PageCount);
```

### Ayrıca bakınız

* class [TxtSaveOptionsBase](../)
* ad alanı [Aspose.Words.Saving](../../txtsaveoptionsbase/)
* toplantı [Aspose.Words](../../../)


