---
title: ImportFormatOptions.IgnoreTextBoxes
second_title: Справочник по API Aspose.Words для .NET
description: ImportFormatOptions свойство. Получает или задает логическое значение указывающее что исходное форматирование содержимого текстовых полей игнорируется  еслиKeepSourceFormatting используется режим. Значение по умолчаниюистинный .
type: docs
weight: 40
url: /ru/net/aspose.words/importformatoptions/ignoretextboxes/
---
## ImportFormatOptions.IgnoreTextBoxes property

Получает или задает логическое значение, указывающее, что исходное форматирование содержимого текстовых полей игнорируется , еслиKeepSourceFormatting используется режим. Значение по умолчанию:`истинный` .

```csharp
public bool IgnoreTextBoxes { get; set; }
```

### Примеры

Показывает, как управлять форматированием текстового поля при добавлении документа.

```csharp
// Создаем документ, в который будут вставлены узлы из другого документа.
Document dstDoc = new Document();
DocumentBuilder builder = new DocumentBuilder(dstDoc);

builder.Writeln("Hello world!");

// Создадим еще один документ с текстовым полем, которое мы импортируем в первый документ.
Document srcDoc = new Document();
builder = new DocumentBuilder(srcDoc);

Shape textBox = builder.InsertShape(ShapeType.TextBox, 300, 100);
builder.MoveTo(textBox.FirstParagraph);
builder.ParagraphFormat.Style.Font.Name = "Courier New";
builder.ParagraphFormat.Style.Font.Size = 24;
builder.Write("Textbox contents");

// Установите флаг, чтобы указать, очищать или сохранять форматирование текстового поля
// при импорте их в другие документы.
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.IgnoreTextBoxes = ignoreTextBoxes;

// Импортируем текстовое поле из исходного документа в целевой документ,
// и затем проверяем, сохранили ли мы стиль его текстового содержимого.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
Shape importedTextBox = (Shape)importer.ImportNode(textBox, true);
dstDoc.FirstSection.Body.Paragraphs[1].AppendChild(importedTextBox);

if (ignoreTextBoxes)
{
    Assert.AreEqual(12.0d, importedTextBox.FirstParagraph.Runs[0].Font.Size);
    Assert.AreEqual("Times New Roman", importedTextBox.FirstParagraph.Runs[0].Font.Name);
}
else
{
    Assert.AreEqual(24.0d, importedTextBox.FirstParagraph.Runs[0].Font.Size);
    Assert.AreEqual("Courier New", importedTextBox.FirstParagraph.Runs[0].Font.Name);
}

dstDoc.Save(ArtifactsDir + "DocumentBuilder.IgnoreTextBoxes.docx");
```

### Смотрите также

* class [ImportFormatOptions](../)
* пространство имен [Aspose.Words](../../importformatoptions/)
* сборка [Aspose.Words](../../../)


