---
title: PdfSaveOptions.CreateNoteHyperlinks
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. Ana metin öyküsündeki dipnot/sonnot referanslarının etkin köprülere dönüştürülüp dönüştürülmeyeceğini belirtir. Tıklandığında köprü ilgili dipnota/sonnota götürür. Varsayılandıryanlış .
type: docs
weight: 40
url: /tr/net/aspose.words.saving/pdfsaveoptions/createnotehyperlinks/
---
## PdfSaveOptions.CreateNoteHyperlinks property

Ana metin öyküsündeki dipnot/sonnot referanslarının etkin köprülere dönüştürülüp dönüştürülmeyeceğini belirtir. Tıklandığında köprü ilgili dipnota/sonnota götürür. Varsayılandır`yanlış` .

```csharp
public bool CreateNoteHyperlinks { get; set; }
```

### Örnekler

Dipnotların ve son notların nasıl köprü işlevi göreceğini gösterir.

```csharp
Document doc = new Document(MyDir + "Footnotes and endnotes.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions options = new PdfSaveOptions();

// Tüm dipnot/sonnot sembollerini döndürmek için "CreateNoteHyperlinks" özelliğini "true" olarak ayarlayın
// metinde, tıklandığında bizi ilgili dipnotlarına/son notlarına götüren bağlantılar gibi davranır.
// "CreateNoteHyperlinks" özelliğini, dipnot/sonnot sembollerinin hiçbir şeye bağlanmasını önlemek için "false" olarak ayarlayın.
options.CreateNoteHyperlinks = createNoteHyperlinks;

doc.Save(ArtifactsDir + "PdfSaveOptions.NoteHyperlinks.pdf", options);
```

### Ayrıca bakınız

* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


