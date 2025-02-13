---
title: Document.AttachedTemplate
second_title: Aspose.Words for .NET API Referansı
description: Document mülk. Belgeye eklenen şablonun tam yolunu alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words/document/attachedtemplate/
---
## Document.AttachedTemplate property

Belgeye eklenen şablonun tam yolunu alır veya ayarlar.

```csharp
public string AttachedTemplate { get; set; }
```

### istisnalar

| istisna | şart |
| --- | --- |
| ArgumentNullException | Boş bir değere ayarlamaya çalışırsanız atar. |

### Notlar

Boş dize, belgenin Normal şablona eklendiği anlamına gelir.

### Örnekler

Ekli şablonları olmayan belgeler için varsayılan bir şablonun nasıl ayarlanacağını gösterir.

```csharp
Document doc = new Document();

// Otomatik stil güncellemeyi etkinleştir, ancak şablon belgesi ekleme.
doc.AutomaticallyUpdateStyles = true;

Assert.AreEqual(string.Empty, doc.AttachedTemplate);

// Şablon belgesi olmadığından, belgenin stil değişikliklerini izleyecek hiçbir yeri yoktu.
// Bir şablonu otomatik olarak ayarlamak için SaveOptions nesnesini kullanın
// kaydettiğimiz bir belge yoksa.
SaveOptions options = SaveOptions.CreateSaveOptions("Document.DefaultTemplate.docx");
options.DefaultTemplate = MyDir + "Business brochure.dotx";

doc.Save(ArtifactsDir + "Document.DefaultTemplate.docx", options);
```

### Ayrıca bakınız

* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


