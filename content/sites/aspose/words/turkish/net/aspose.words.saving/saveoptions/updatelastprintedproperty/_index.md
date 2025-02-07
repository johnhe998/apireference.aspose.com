---
title: SaveOptions.UpdateLastPrintedProperty
second_title: Aspose.Words for .NET API Referansı
description: SaveOptions mülk. olup olmadığını belirleyen bir değer alır veya ayarlar.LastPrinted özellik kaydedilmeden önce güncellenir.
type: docs
weight: 180
url: /tr/net/aspose.words.saving/saveoptions/updatelastprintedproperty/
---
## SaveOptions.UpdateLastPrintedProperty property

olup olmadığını belirleyen bir değer alır veya ayarlar.[`LastPrinted`](../../../aspose.words.properties/builtindocumentproperties/lastprinted/) özellik kaydedilmeden önce güncellenir.

```csharp
public bool UpdateLastPrintedProperty { get; set; }
```

### Örnekler

Kaydederken bir belgenin "CreatedTime" özelliğinin nasıl güncelleneceğini gösterir.

```csharp
Document doc = new Document();
doc.BuiltInDocumentProperties.CreatedTime = new DateTime(2019, 12, 20);

// Bu bayrak, yerleşik bir özellik olan oluşturulan zamanın güncellenip güncellenmediğini belirler.
// Öyleyse, belgenin en son kaydetme işleminin tarihi
// parametre olarak geçirilen bu SaveOptions nesnesi ile oluşturulan zaman olarak kullanılır.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.UpdateCreatedTimeProperty = isUpdateCreatedTimeProperty;

doc.Save(ArtifactsDir + "DocSaveOptions.UpdateCreatedTimeProperty.docx", saveOptions);

// Kaydedilen belgeyi açın, ardından özelliğin değerini doğrulayın.
doc = new Document(ArtifactsDir + "DocSaveOptions.UpdateCreatedTimeProperty.docx");

Assert.AreNotEqual(isUpdateCreatedTimeProperty, new DateTime(2019, 12, 20) == doc.BuiltInDocumentProperties.CreatedTime);
```

Kaydederken bir belgenin "Son yazdırılan" özelliğinin nasıl güncelleneceğini gösterir.

```csharp
Document doc = new Document();
doc.BuiltInDocumentProperties.LastPrinted = new DateTime(2019, 12, 20);

// Bu bayrak, yerleşik bir özellik olan son basılan tarihin güncellenip güncellenmediğini belirler.
// Öyleyse, belgenin en son kaydetme işleminin tarihi
// parametre olarak geçirilen bu SaveOptions nesnesi ile yazdırma tarihi olarak kullanılır.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.UpdateLastPrintedProperty = isUpdateLastPrintedProperty;

// Microsoft Word 2003'te bu özellik Dosya -> Özellikler -> İstatistikler -> Basılı.
// Ayrıca PRINTDATE alanı kullanılarak belgenin gövdesinde de görüntülenebilir.
doc.Save(ArtifactsDir + "DocSaveOptions.UpdateLastPrintedProperty.doc", saveOptions);

// Kaydedilen belgeyi açın, ardından özelliğin değerini doğrulayın.
doc = new Document(ArtifactsDir + "DocSaveOptions.UpdateLastPrintedProperty.doc");

Assert.AreNotEqual(isUpdateLastPrintedProperty, new DateTime(2019, 12, 20) == doc.BuiltInDocumentProperties.LastPrinted);
```

### Ayrıca bakınız

* class [SaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../saveoptions/)
* toplantı [Aspose.Words](../../../)


