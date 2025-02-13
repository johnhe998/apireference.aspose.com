---
title: ImportFormatOptions.MergePastedLists
second_title: Aspose.Words for .NET API Referansı
description: ImportFormatOptions mülk. Yapıştırılan listelerin çevredeki listelerle birleştirilip birleştirilmeyeceğini belirten bir boole değeri alır veya ayarlar. Varsayılan değeryanlış .
type: docs
weight: 60
url: /tr/net/aspose.words/importformatoptions/mergepastedlists/
---
## ImportFormatOptions.MergePastedLists property

Yapıştırılan listelerin çevredeki listelerle birleştirilip birleştirilmeyeceğini belirten bir boole değeri alır veya ayarlar. Varsayılan değer`yanlış` .

```csharp
public bool MergePastedLists { get; set; }
```

### Örnekler

Belgelerdeki listelerin nasıl birleştirileceğini gösterir.

```csharp
Document srcDoc = new Document(MyDir + "List item.docx");
Document dstDoc = new Document(MyDir + "List destination.docx");

ImportFormatOptions options = new ImportFormatOptions { MergePastedLists = true };

// "MergePastedLists" özelliğini "true" olarak ayarlayın, yapıştırılan listeler çevredeki listelerle birleştirilir.
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

dstDoc.Save(ArtifactsDir + "Document.MergePastedLists.docx");
```

### Ayrıca bakınız

* class [ImportFormatOptions](../)
* ad alanı [Aspose.Words](../../importformatoptions/)
* toplantı [Aspose.Words](../../../)


