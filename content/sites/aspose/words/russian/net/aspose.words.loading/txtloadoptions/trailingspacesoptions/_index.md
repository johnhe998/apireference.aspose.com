---
title: TxtLoadOptions.TrailingSpacesOptions
second_title: Справочник по API Aspose.Words для .NET
description: TxtLoadOptions свойство. Получает или задает предпочтительный вариант обработки завершающего пробела. Значение по умолчаниюTrim .
type: docs
weight: 50
url: /ru/net/aspose.words.loading/txtloadoptions/trailingspacesoptions/
---
## TxtLoadOptions.TrailingSpacesOptions property

Получает или задает предпочтительный вариант обработки завершающего пробела. Значение по умолчанию:Trim .

```csharp
public TxtTrailingSpacesOptions TrailingSpacesOptions { get; set; }
```

### Примеры

Показывает, как обрезать пробелы при загрузке текстовых документов.

```csharp
string textDoc = "      Line 1 \n" +
                 "    Line 2   \n" +
                 " Line 3       ";

// Создаем объект "TxtLoadOptions", который мы можем передать конструктору документа
// чтобы изменить способ загрузки документа с открытым текстом.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Установите для свойства "LeadingSpacesOptions" значение "TxtLeadingSpacesOptions.Preserve"
// для сохранения всех пробелов в начале каждой строки.
// Установите для свойства "LeadingSpacesOptions" значение "TxtLeadingSpacesOptions.ConvertToIndent"
// чтобы удалить все пробельные символы в начале каждой строки,
// и затем применяем к абзацу отступ первой строки слева, чтобы имитировать эффект пробелов.
// Установите для свойства "LeadingSpacesOptions" значение "TxtLeadingSpacesOptions.Trim"
// чтобы удалить все пробельные символы в начале каждой строки.
loadOptions.LeadingSpacesOptions = txtLeadingSpacesOptions;

// Установите для свойства "TrailingSpacesOptions" значение "TxtTrailingSpacesOptions.Preserve"
// для сохранения всех пробелов в конце каждой строки. 
// Установите для свойства "TrailingSpacesOptions" значение "TxtTrailingSpacesOptions.Trim", чтобы 
// удалить все пробельные символы в конце каждой строки.
loadOptions.TrailingSpacesOptions = txtTrailingSpacesOptions;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

switch (txtLeadingSpacesOptions)
{
    case TxtLeadingSpacesOptions.ConvertToIndent:
        Assert.AreEqual(37.8d, paragraphs[0].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(25.2d, paragraphs[1].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(6.3d, paragraphs[2].ParagraphFormat.FirstLineIndent);

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
    case TxtLeadingSpacesOptions.Preserve:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("      Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("    Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith(" Line 3"));
        break;
    case TxtLeadingSpacesOptions.Trim:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
}

switch (txtTrailingSpacesOptions)
{
    case TxtTrailingSpacesOptions.Preserve:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1 \r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2   \r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3       \f"));
        break;
    case TxtTrailingSpacesOptions.Trim:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1\r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2\r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3\f"));
        break;
}
```

### Смотрите также

* enum [TxtTrailingSpacesOptions](../../txttrailingspacesoptions/)
* class [TxtLoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../txtloadoptions/)
* сборка [Aspose.Words](../../../)


