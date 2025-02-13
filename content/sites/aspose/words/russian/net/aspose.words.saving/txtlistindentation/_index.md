---
title: Class TxtListIndentation
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.TxtListIndentation сорт. Определяет отступ уровней списка при экспорте документа вText формат.
type: docs
weight: 5370
url: /ru/net/aspose.words.saving/txtlistindentation/
---
## TxtListIndentation class

Определяет отступ уровней списка при экспорте документа вText формат.

```csharp
public class TxtListIndentation
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [TxtListIndentation](txtlistindentation/)() | Конструктор по умолчанию. |

## Характеристики

| Имя | Описание |
| --- | --- |
| [Character](../../aspose.words.saving/txtlistindentation/character/) { get; set; } | Получает или задает, какой символ использовать для отступа уровней списка. Значение по умолчанию — '\0', что означает отсутствие отступа. |
| [Count](../../aspose.words.saving/txtlistindentation/count/) { get; set; } | Получает или устанавливает количество[`Character`](./character/) для использования в качестве отступа на один уровень списка. Значение по умолчанию равно 0, что означает отсутствие отступа. |

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

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


