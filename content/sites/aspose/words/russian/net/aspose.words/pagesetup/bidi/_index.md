---
title: PageSetup.Bidi
second_title: Справочник по API Aspose.Words для .NET
description: PageSetup свойство. Указывает что этот раздел содержит двунаправленный текст сложные сценарии.
type: docs
weight: 10
url: /ru/net/aspose.words/pagesetup/bidi/
---
## PageSetup.Bidi property

Указывает, что этот раздел содержит двунаправленный текст (сложные сценарии).

```csharp
public bool Bidi { get; set; }
```

### Примечания

При значении true столбцы в этом разделе располагаются справа налево.

### Примеры

Показывает, как установить порядок текстовых столбцов в разделе.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TextColumns.SetCount(3);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Write("Column 2.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Write("Column 3.");

// Установите для свойства "Bidi" значение "true", чтобы расположить столбцы, начиная с правой стороны страницы.
// Порядок столбцов будет соответствовать направлению текста справа налево.
// Установите для свойства "Bidi" значение "false", чтобы расположить столбцы, начиная с левой стороны страницы.
// Порядок столбцов будет соответствовать направлению текста слева направо.
pageSetup.Bidi = reverseColumns;

doc.Save(ArtifactsDir + "PageSetup.Bidi.docx");
```

### Смотрите также

* class [PageSetup](../)
* пространство имен [Aspose.Words](../../pagesetup/)
* сборка [Aspose.Words](../../../)


