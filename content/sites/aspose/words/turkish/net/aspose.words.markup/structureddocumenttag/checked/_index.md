---
title: StructuredDocumentTag.Checked
second_title: Aspose.Words for .NET API Referansı
description: StructuredDocumentTag mülk. Onay Kutusunun geçerli durumunu alır/ayarlar SDT . Bu özellik için varsayılan değer falsetur.
type: docs
weight: 60
url: /tr/net/aspose.words.markup/structureddocumenttag/checked/
---
## StructuredDocumentTag.Checked property

Onay Kutusunun geçerli durumunu alır/ayarlar **SDT** . Bu özellik için varsayılan değer false'tur.

```csharp
public bool Checked { get; set; }
```

### Notlar

Bu mülke erişmek yalnızcaCheckbox SDT türleri.

Diğer tüm SDT türleri için istisna oluşacaktır.

### Örnekler

Onay kutusu şeklinde yapılandırılmış bir belge etiketinin nasıl oluşturulacağını gösterin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

StructuredDocumentTag sdtCheckBox =
    new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline) {Checked = true};

// Bir onay kutusu içerik kontrolünün işaretli/işaretsiz durumunu temsil etmek için kullanılan sembolleri ayarlayabiliriz.
sdtCheckBox.SetCheckedSymbol(0x00A9, "Times New Roman");
sdtCheckBox.SetUncheckedSymbol(0x00AE, "Times New Roman");

builder.InsertNode(sdtCheckBox);

doc.Save(ArtifactsDir + "StructuredDocumentTag.CheckBox.docx");
```

### Ayrıca bakınız

* class [StructuredDocumentTag](../)
* ad alanı [Aspose.Words.Markup](../../structureddocumenttag/)
* toplantı [Aspose.Words](../../../)


