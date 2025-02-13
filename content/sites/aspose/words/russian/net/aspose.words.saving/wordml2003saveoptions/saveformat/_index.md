---
title: WordML2003SaveOptions.SaveFormat
second_title: Справочник по API Aspose.Words для .NET
description: WordML2003SaveOptions свойство. Определяет формат в котором документ будет сохранен если используется этот объект параметров сохранения.WordML .
type: docs
weight: 20
url: /ru/net/aspose.words.saving/wordml2003saveoptions/saveformat/
---
## WordML2003SaveOptions.SaveFormat property

Определяет формат, в котором документ будет сохранен, если используется этот объект параметров сохранения.WordML .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Примеры

Показывает, как управлять необработанным содержимым выходного документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Создаем объект "WordML2003SaveOptions" для передачи в метод "Сохранить" документа
// чтобы изменить способ сохранения документа в формате сохранения WordML.
WordML2003SaveOptions options = new WordML2003SaveOptions();

Assert.AreEqual(SaveFormat.WordML, options.SaveFormat);

// Установите для свойства "PrettyFormat" значение "true", чтобы применить отступ символа табуляции и
// новые строки, чтобы облегчить чтение необработанного содержимого выходного документа.
// Установите для свойства "PrettyFormat" значение "false", чтобы сохранить необработанное содержимое документа в одном непрерывном теле текста.
options.PrettyFormat = prettyFormat;

doc.Save(ArtifactsDir + "WordML2003SaveOptions.PrettyFormat.xml", options);

string fileContents = File.ReadAllText(ArtifactsDir + "WordML2003SaveOptions.PrettyFormat.xml");

if (prettyFormat)
    Assert.True(fileContents.Contains(
        "<o:DocumentProperties>\r\n\t\t" +
            "<o:Revision>1</o:Revision>\r\n\t\t" +
            "<o:TotalTime>0</o:TotalTime>\r\n\t\t" +
            "<o:Pages>1</o:Pages>\r\n\t\t" +
            "<o:Words>0</o:Words>\r\n\t\t" +
            "<o:Characters>0</o:Characters>\r\n\t\t" +
            "<o:Lines>1</o:Lines>\r\n\t\t" +
            "<o:Paragraphs>1</o:Paragraphs>\r\n\t\t" +
            "<o:CharactersWithSpaces>0</o:CharactersWithSpaces>\r\n\t\t" +
            "<o:Version>11.5606</o:Version>\r\n\t" +
        "</o:DocumentProperties>"));
else
    Assert.True(fileContents.Contains(
        "<o:DocumentProperties><o:Revision>1</o:Revision><o:TotalTime>0</o:TotalTime><o:Pages>1</o:Pages>" +
        "<o:Words>0</o:Words><o:Characters>0</o:Characters><o:Lines>1</o:Lines><o:Paragraphs>1</o:Paragraphs>" +
        "<o:CharactersWithSpaces>0</o:CharactersWithSpaces><o:Version>11.5606</o:Version></o:DocumentProperties>"));
```

### Смотрите также

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [WordML2003SaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../wordml2003saveoptions/)
* сборка [Aspose.Words](../../../)


