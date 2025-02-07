---
title: TxtSaveOptions.AddBidiMarks
second_title: Справочник по API Aspose.Words для .NET
description: TxtSaveOptions свойство. Указывает следует ли добавлять двунаправленные метки перед каждым запуском BiDi при экспорте в формате обычного текста.
type: docs
weight: 20
url: /ru/net/aspose.words.saving/txtsaveoptions/addbidimarks/
---
## TxtSaveOptions.AddBidiMarks property

Указывает, следует ли добавлять двунаправленные метки перед каждым запуском BiDi при экспорте в формате обычного текста.

Значение по умолчанию **ЛОЖЬ**.

```csharp
public bool AddBidiMarks { get; set; }
```

### Примеры

Показывает, как вставить символ Unicode «ПРИМЕЧАНИЕ СПРАВА НАЛЕВО» (U+200F) перед каждым двунаправленным выполнением в тексте.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");

// Создаем объект "TxtSaveOptions", который мы можем передать в метод "Сохранить" документа
// чтобы изменить способ сохранения документа в виде открытого текста.
TxtSaveOptions saveOptions = new TxtSaveOptions { Encoding = System.Text.Encoding.Unicode};

// Установите для свойства "AddBidiMarks" значение "true", чтобы добавлять метки перед запуском
// с текстом справа налево для обозначения факта.
// Установите для свойства "AddBidiMarks" значение "false", чтобы писать все слева направо
// и справа налево выполняются одинаково, ничего не указывая, что есть что.
saveOptions.AddBidiMarks = addBidiMarks;

doc.Save(ArtifactsDir + "TxtSaveOptions.AddBidiMarks.txt", saveOptions);

string docText = System.Text.Encoding.Unicode.GetString(File.ReadAllBytes(ArtifactsDir + "TxtSaveOptions.AddBidiMarks.txt"));

if (addBidiMarks)
{
    Assert.AreEqual("\uFEFFHello world!‎\r\nשלום עולם!‏\r\nمرحبا بالعالم!‏\r\n\r\n", docText);
    Assert.True(docText.Contains("\u200f"));
}
else
{
    Assert.AreEqual("\uFEFFHello world!\r\nשלום עולם!\r\nمرحبا بالعالم!\r\n\r\n", docText);
    Assert.False(docText.Contains("\u200f"));
}
```

### Смотрите также

* class [TxtSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../txtsaveoptions/)
* сборка [Aspose.Words](../../../)


