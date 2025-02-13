---
title: PdfSaveOptions.AdditionalTextPositioning
second_title: Aspose.Words for .NET API Referansı
description: PdfSaveOptions mülk. Ek metin konumlandırma operatörleri yazıp yazmayacağını belirten bir bayrak.
type: docs
weight: 20
url: /tr/net/aspose.words.saving/pdfsaveoptions/additionaltextpositioning/
---
## PdfSaveOptions.AdditionalTextPositioning property

Ek metin konumlandırma operatörleri yazıp yazmayacağını belirten bir bayrak.

```csharp
public bool AdditionalTextPositioning { get; set; }
```

### Notlar

Eğer`doğru` , ek metin konumlandırma operatörleri çıktı PDF'sine yazılır. Bu, bazı yazıcılarda hatalı metin konumlandırmayla ilgili sorunlarının üstesinden gelmeye yardımcı olabilir. Dezavantajı artan PDF belge boyutudur.

Varsayılan değer`yanlış`.

### Örnekler

Ek metin konumlandırma operatörlerinin nasıl yazılacağını gösterin.

```csharp
Document doc = new Document(MyDir + "Text positioning operators.docx");

// Belgenin "Kaydet" yöntemine aktarabileceğimiz bir "PdfSaveOptions" nesnesi oluşturun
// bu yöntemin belgeyi .PDF'ye dönüştürme şeklini değiştirmek için.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    TextCompression = PdfTextCompression.None,

    // Yanlış düzeltmeyi denemek için "AdditionalTextPositioning" özelliğini "true" olarak ayarlayın
    // Çıktı PDF'sinde eleman konumlandırma, varsa, artan dosya boyutu pahasına.
    // Belgeyi her zamanki gibi işlemek için "AdditionalTextPositioning" özelliğini "false" olarak ayarlayın.
    AdditionalTextPositioning = applyAdditionalTextPositioning
};

doc.Save(ArtifactsDir + "PdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

### Ayrıca bakınız

* class [PdfSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../pdfsaveoptions/)
* toplantı [Aspose.Words](../../../)


