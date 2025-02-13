---
title: PdfLoadOptions.SkipPdfImages
second_title: Справочник по API Aspose.Words для .NET
description: PdfLoadOptions свойство. Получает или задает флаг указывающий следует ли пропускать изображения при загрузке документа PDF. По умолчанию  Ложь.
type: docs
weight: 40
url: /ru/net/aspose.words.loading/pdfloadoptions/skippdfimages/
---
## PdfLoadOptions.SkipPdfImages property

Получает или задает флаг, указывающий, следует ли пропускать изображения при загрузке документа PDF. По умолчанию — Ложь.

```csharp
public bool SkipPdfImages { get; set; }
```

### Примеры

Показывает, как пропускать изображения при загрузке файлов PDF.

```csharp
PdfLoadOptions options = new PdfLoadOptions();
options.SkipPdfImages = isSkipPdfImages;

Document doc = new Document(MyDir + "Images.pdf", options);
NodeCollection shapeCollection = doc.GetChildNodes(NodeType.Shape, true);

if (isSkipPdfImages)
{
    Assert.AreEqual(shapeCollection.Count, 0);
}
else
{
    Assert.AreNotEqual(shapeCollection.Count, 0);
}
```

### Смотрите также

* class [PdfLoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../pdfloadoptions/)
* сборка [Aspose.Words](../../../)


