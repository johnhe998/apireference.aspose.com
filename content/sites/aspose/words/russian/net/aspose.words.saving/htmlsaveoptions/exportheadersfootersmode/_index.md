---
title: HtmlSaveOptions.ExportHeadersFootersMode
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает как верхние и нижние колонтитулы выводятся в HTML MHTML или EPUB. Значение по умолчаниюPerSection для HTML/MHTML иNone для EPUB.
type: docs
weight: 170
url: /ru/net/aspose.words.saving/htmlsaveoptions/exportheadersfootersmode/
---
## HtmlSaveOptions.ExportHeadersFootersMode property

Указывает, как верхние и нижние колонтитулы выводятся в HTML, MHTML или EPUB. Значение по умолчанию:PerSection для HTML/MHTML иNone для EPUB.

```csharp
public ExportHeadersFootersMode ExportHeadersFootersMode { get; set; }
```

### Примечания

Трудно осмысленно выводить верхние и нижние колонтитулы в HTML, потому что HTML не разбит на страницы.

Когда это свойствоPerSection, Aspose.Words экспортирует только основные верхние и нижние колонтитулы в начале и в конце каждого раздела.

Когда он являетсяFirstSectionHeaderLastSectionFooter экспортируются только первый основной заголовок и последний основной нижний колонтитул (включая ссылку на предыдущий).

Вы можете полностью отключить экспорт верхних и нижних колонтитулов, установив для этого свойства значениеNone.

### Примеры

Показывает, как опускать верхние и нижние колонтитулы при сохранении документа в формате HTML.

```csharp
Document doc = new Document(MyDir + "Header and footer types.docx");

// Этот документ содержит верхние и нижние колонтитулы. Мы можем получить к ним доступ через коллекцию «HeadersFooters».
Assert.AreEqual("First header", doc.FirstSection.HeadersFooters[HeaderFooterType.HeaderFirst].GetText().Trim());

// Такие форматы, как .html, не разбивают документ на страницы, поэтому верхние и нижние колонтитулы не будут работать одинаково
// они будут, когда мы откроем документ в формате .docx с помощью Microsoft Word.
// Если мы преобразуем документ с верхними/нижними колонтитулами в html, преобразование ассимилирует верхние/нижние колонтитулы в основной текст.
// Мы можем использовать объект SaveOptions, чтобы опустить верхние/нижние колонтитулы при преобразовании в html.
HtmlSaveOptions saveOptions =
    new HtmlSaveOptions(SaveFormat.Html) { ExportHeadersFootersMode = ExportHeadersFootersMode.None };

doc.Save(ArtifactsDir + "HeaderFooter.ExportMode.html", saveOptions);

// Открываем наш сохраненный документ и проверяем, что он не содержит текста заголовка
doc = new Document(ArtifactsDir + "HeaderFooter.ExportMode.html");

Assert.IsFalse(doc.Range.Text.Contains("First header"));
```

### Смотрите также

* enum [ExportHeadersFootersMode](../../exportheadersfootersmode/)
* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


