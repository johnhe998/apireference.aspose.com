---
title: OdtSaveOptions.MeasureUnit
second_title: Aspose.Words for .NET API Referansı
description: OdtSaveOptions mülk. Belge içeriğine uygulanacak ölçü birimlerini belirlemeye izin verir. Varsayılan değerCentimeters
type: docs
weight: 30
url: /tr/net/aspose.words.saving/odtsaveoptions/measureunit/
---
## OdtSaveOptions.MeasureUnit property

Belge içeriğine uygulanacak ölçü birimlerini belirlemeye izin verir. Varsayılan değerCentimeters

```csharp
public OdtSaveMeasureUnit MeasureUnit { get; set; }
```

### Notlar

Open Office, belgelerde uzunlukları, genişlikleri ve diğer ölçülebilir biçimlendirmeleri ve içerik özelliklerini belirtirken santimetre kullanır, MS Office ise inç kullanır.

### Örnekler

Kaydedilmiş bir ODT belgesinin stil parametrelerini tanımlamak için farklı ölçü birimlerinin nasıl kullanılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Belgeyi .odt'a aktardığımızda, belgeyi kaydetme şeklimizi değiştirmek için bir OdtSaveOptions nesnesini kullanabiliriz.
// "MeasureUnit" özelliğini "OdtSaveMeasureUnit.Santimetre" olarak ayarlayabiliriz.
// Open Office'in kullandığı metrik sistemi kullanarak stil parametreleri gibi içerikleri tanımlamak için. 
// "MeasureUnit" özelliğini "OdtSaveMeasureUnit.Inches" olarak ayarlayabiliriz.
// Microsoft Word'ün kullandığı emperyal sistemi kullanarak stil parametreleri gibi içeriği tanımlamak için.
OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = odtSaveMeasureUnit
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### Ayrıca bakınız

* enum [OdtSaveMeasureUnit](../../odtsavemeasureunit/)
* class [OdtSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../odtsaveoptions/)
* toplantı [Aspose.Words](../../../)


