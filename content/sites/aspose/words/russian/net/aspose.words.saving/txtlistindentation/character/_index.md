---
title: TxtListIndentation.Character
second_title: Справочник по API Aspose.Words для .NET
description: TxtListIndentation свойство. Получает или задает какой символ использовать для отступа уровней списка. Значение по умолчанию  0 что означает отсутствие отступа.
type: docs
weight: 20
url: /ru/net/aspose.words.saving/txtlistindentation/character/
---
## TxtListIndentation.Character property

Получает или задает, какой символ использовать для отступа уровней списка. Значение по умолчанию — '\0', что означает отсутствие отступа.

```csharp
public char Character { get; set; }
```

### Примеры

Показывает, как настроить отступ списка при сохранении документа в виде открытого текста.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создаем список с тремя уровнями отступов.
builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.ListFormat.ListIndent();
builder.Writeln("Item 2");
builder.ListFormat.ListIndent(); 
builder.Write("Item 3");

// Создаем объект "TxtSaveOptions", который мы можем передать в метод "Сохранить" документа
// чтобы изменить способ сохранения документа в виде открытого текста.
TxtSaveOptions txtSaveOptions = new TxtSaveOptions();

// Установите свойство «Персонаж», чтобы назначить символ для использования
// для заполнения, имитирующего отступ списка в открытом тексте.
txtSaveOptions.ListIndentation.Character = ' ';

// Установите свойство "Count", чтобы указать количество раз
// для размещения символа заполнения для каждого уровня отступа списка.
txtSaveOptions.ListIndentation.Count = 3;

doc.Save(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt", txtSaveOptions);

string docText = File.ReadAllText(ArtifactsDir + "TxtSaveOptions.TxtListIndentation.txt");

Assert.AreEqual("1. Item 1\r\n" +
                "   a. Item 2\r\n" +
                "      i. Item 3\r\n", docText);
```

### Смотрите также

* class [TxtListIndentation](../)
* пространство имен [Aspose.Words.Saving](../../txtlistindentation/)
* сборка [Aspose.Words](../../../)


