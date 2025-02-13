---
title: PdfSaveOptions.Clone
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions yöntem. Bu nesnenin derin bir klonunu oluşturur.
type: docs
weight: 310
url: /tr/net/aspose.words.saving/pdfsaveoptions/clone/
---
## PdfSaveOptions.Clone method

Bu nesnenin derin bir klonunu oluşturur.

```csharp
public PdfSaveOptions Clone()
```

### Örnekler

PDF'ye kaydetmeden hemen önce bir belgedeki tüm alanların nasıl güncelleneceğini gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// SAYFA ve SAYILAR alanları ile metin ekleyin. Bu alanlar gerçek zamanlı olarak doğru değeri göstermez.
// "Field.Update()" ve "Document.UpdateFields()" gibi güncelleme yöntemlerini kullanarak bunları manuel olarak güncellememiz gerekecek.
// her seferinde doğru değerleri göstermelerine ihtiyacımız var.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Hello World!");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// Kaydetme işleminden hemen önce bir belgedeki tüm alanları güncellememek için "UpdateFields" özelliğini "false" olarak ayarlayın.
// Kaydetmeden önce tüm alanlarımızın güncel olacağını biliyorsak bu tercih edilen seçenektir.
// Tüm belgeyi yinelemek için "UpdateFields" özelliğini "true" olarak ayarlayın
// alanları ve bunları PDF olarak kaydetmeden önce güncelleyin. Bu, tüm alanların görüntülenmesini sağlayacaktır.
// PDF'deki en doğru değerler.
options.UpdateFields = updateFields;

// PdfSaveOptions nesnelerini klonlayabiliriz.
Assert.AreNotSame(options, options.Clone());

doc.Save(ArtifactsDir + "PdfSaveOptions.UpdateFields.pdf", options);
```

### Ayrıca bakınız

* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


