---
title: FieldIndex.UseYomi
second_title: Справочник по API Aspose.Words для .NET
description: FieldIndex свойство. Получает или задает следует ли включить использование текста yomi для элементов указателя.
type: docs
weight: 170
url: /ru/net/aspose.words.fields/fieldindex/useyomi/
---
## FieldIndex.UseYomi property

Получает или задает, следует ли включить использование текста yomi для элементов указателя.

```csharp
public bool UseYomi { get; set; }
```

### Примеры

Показывает, как фонетически сортировать записи поля ИНДЕКС.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создать поле INDEX, которое будет отображать запись для каждого поля XE, найденного в документе.
// Каждая запись будет отображать значение свойства Text поля XE с левой стороны,
// и номер страницы, содержащей поле XE справа.
// Запись INDEX соберет все поля XE с совпадающими значениями в свойстве "Текст"
// в одну запись вместо создания записи для каждого поля XE.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// Таблица INDEX автоматически сортирует записи по значениям их свойств Text в алфавитном порядке.
// Настроить таблицу INDEX для фонетической сортировки записей с использованием вместо этого хираганы.
index.UseYomi = sortEntriesUsingYomi;

if (sortEntriesUsingYomi)
    Assert.AreEqual(" INDEX  \\y", index.GetFieldCode());
else
    Assert.AreEqual(" INDEX ", index.GetFieldCode());

// Вставьте 4 поля XE, которые будут отображаться как записи в таблице содержания поля INDEX.
// Свойство "Текст" может содержать написание слова в кандзи, произношение которого может быть двусмысленным,
// в то время как версия слова "Ёми" будет произноситься точно так же, как произносится с использованием хираганы.
// Если мы настроим наше поле ИНДЕКС на использование Yomi, оно отсортирует эти записи
// по значению их свойств Yomi, а не по их значениям Text.
builder.InsertBreak(BreakType.PageBreak);
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "愛子";
indexEntry.Yomi = "あ";

Assert.AreEqual(" XE  愛子 \\y あ", indexEntry.GetFieldCode());

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "明美";
indexEntry.Yomi = "あ";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "恵美";
indexEntry.Yomi = "え";

builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "愛美";
indexEntry.Yomi = "え";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Yomi.docx");
```

### Смотрите также

* class [FieldIndex](../)
* пространство имен [Aspose.Words.Fields](../../fieldindex/)
* сборка [Aspose.Words](../../../)


