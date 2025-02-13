---
title: StructuredDocumentTag.BuildingBlockCategory
second_title: Справочник по API Aspose.Words для .NET
description: StructuredDocumentTag свойство. Указывает категорию стандартного блока для этого СДТ node. Не может быть нулевым.
type: docs
weight: 30
url: /ru/net/aspose.words.markup/structureddocumenttag/buildingblockcategory/
---
## StructuredDocumentTag.BuildingBlockCategory property

Указывает категорию стандартного блока для этого **СДТ** node. Не может быть нулевым.

```csharp
public string BuildingBlockCategory { get; set; }
```

### Примечания

Доступ к этому свойству будет работать только дляBuildingBlockGallery и DocPartObj Типы СДТ. Он доступен только для чтения **СДТ**типа части документа.

Для всех других типов SDT будет иметь место исключение.

### Примеры

Показывает, как вставить тег структурированного документа в качестве стандартного блока и задать его категорию и галерею.

```csharp
Document doc = new Document();

StructuredDocumentTag buildingBlockSdt =
    new StructuredDocumentTag(doc, SdtType.BuildingBlockGallery, MarkupLevel.Block)
    {
        BuildingBlockCategory = "Built-in",
        BuildingBlockGallery = "Table of Contents"
    };

doc.FirstSection.Body.AppendChild(buildingBlockSdt);

doc.Save(ArtifactsDir + "StructuredDocumentTag.BuildingBlockCategories.docx");
```

### Смотрите также

* class [StructuredDocumentTag](../)
* пространство имен [Aspose.Words.Markup](../../structureddocumenttag/)
* сборка [Aspose.Words](../../../)


