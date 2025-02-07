---
title: TxtLoadOptions.DetectNumberingWithWhitespaces
second_title: Справочник по API Aspose.Words для .NET
description: TxtLoadOptions свойство. Позволяет указать как распознаются нумерованные элементы списка при импорте документа из формата обычного текста. Значение по умолчанию  true.
type: docs
weight: 20
url: /ru/net/aspose.words.loading/txtloadoptions/detectnumberingwithwhitespaces/
---
## TxtLoadOptions.DetectNumberingWithWhitespaces property

Позволяет указать, как распознаются нумерованные элементы списка при импорте документа из формата обычного текста. Значение по умолчанию — true.

```csharp
public bool DetectNumberingWithWhitespaces { get; set; }
```

### Примечания

Если для этой опции установлено значение false, алгоритм распознавания списков обнаруживает абзацы списка, когда номера списка заканчиваются на либо точкой, либо правой квадратной скобкой, либо символами маркера (такими как «•», «*», «-» или «o»).

Если для этой опции установлено значение true, пробелы также используются в качестве разделителей номеров списка: алгоритм распознавания списка для нумерации в арабском стиле (1., 1.1.2.) использует как пробелы, так и символы точки ("".").

### Примеры

Показывает, как обнаруживать списки при загрузке текстовых документов.

```csharp
// Создаем текстовый документ в виде строки с четырьмя отдельными частями, которые мы можем интерпретировать как списки,
// с разными разделителями. После загрузки документа с открытым текстом в объект «Документ»
// Aspose.Words всегда обнаружит первые три списка и добавит объект «Список»
// для каждого свойства документа "Списки".
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";

// Создаем объект "TxtLoadOptions", который мы можем передать конструктору документа
// чтобы изменить способ загрузки документа с открытым текстом.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Установите для свойства "DetectNumberingWithWhitespaces" значение "true", чтобы обнаруживать пронумерованные элементы
// с разделителями-пробелами, такими как четвертый список в нашем документе, as lists.
// Это также может ложно определить абзацы, начинающиеся с цифр, как списки.
// Установите для свойства "DetectNumberingWithWhitespaces" значение "false"
// чтобы не создавать списки из нумерованных элементов с разделителями-пробелами.
loadOptions.DetectNumberingWithWhitespaces = detectNumberingWithWhitespaces;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

if (detectNumberingWithWhitespaces)
{
    Assert.AreEqual(4, doc.Lists.Count);
    Assert.True(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
else
{
    Assert.AreEqual(3, doc.Lists.Count);
    Assert.False(doc.FirstSection.Body.Paragraphs.Any(p => p.GetText().Contains("Fourth list") && ((Paragraph)p).IsListItem));
}
```

### Смотрите также

* class [TxtLoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../txtloadoptions/)
* сборка [Aspose.Words](../../../)


