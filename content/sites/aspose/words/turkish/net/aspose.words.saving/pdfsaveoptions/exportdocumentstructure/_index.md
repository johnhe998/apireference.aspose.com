---
title: PdfSaveOptions.ExportDocumentStructure
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. Belge yapısının dışa aktarılıp aktarılmayacağını belirleyen bir değer alır veya ayarlar.
type: docs
weight: 120
url: /tr/net/aspose.words.saving/pdfsaveoptions/exportdocumentstructure/
---
## PdfSaveOptions.ExportDocumentStructure property

Belge yapısının dışa aktarılıp aktarılmayacağını belirleyen bir değer alır veya ayarlar.

```csharp
public bool ExportDocumentStructure { get; set; }
```

### Notlar

Bu uyumluluk için belge yapısı gerektiğinden, PDF/A-1a, PDF/A-2a ve PDF/UA-1'e kaydederken bu değer yok sayılır.

Belge yapısının dışa aktarılmasının bellek tüketimini, özellikle de büyük belgeler için önemli ölçüde artırdığını unutmayın.

### Örnekler

Belgemizi programlı olarak yorumlamaya yardımcı olabilecek belge yapısı öğelerinin nasıl korunacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("Hello world!");
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Write(
    "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// Belge yapısını, bu tür etiketleri şu şekilde kullanılabilir hale getirmek için "ExportDocumentStructure" özelliğini "true" olarak ayarlayın.
// Artan dosya boyutu pahasına Adobe Acrobat'ın "İçerik" gezinme bölmesi.
// Belge yapısını dışa aktarmamak için "ExportDocumentStructure" özelliğini "false" olarak ayarlayın.
options.ExportDocumentStructure = exportDocumentStructure;

// Bu belgeyi kaydederken belge yapısını dışa aktardığımızı varsayalım. Bu durumda,
// Adobe Acrobat kullanarak açabilir ve başlık gibi öğeler için etiketler bulabiliriz
// ve sonraki paragraf "Görünüm" -> "Göster/Gizle" -> "Gezinme bölmeleri" -> "Etiketler".
doc.Save(ArtifactsDir + "PdfSaveOptions.ExportDocumentStructure.pdf", options);
```

### Ayrıca bakınız

* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


