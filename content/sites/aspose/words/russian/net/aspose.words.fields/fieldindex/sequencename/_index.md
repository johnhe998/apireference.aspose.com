---
title: FieldIndex.SequenceName
second_title: Справочник по API Aspose.Words для .NET
description: FieldIndex свойство. Получает или задает имя последовательности номер которой включен в номер страницы.
type: docs
weight: 150
url: /ru/net/aspose.words.fields/fieldindex/sequencename/
---
## FieldIndex.SequenceName property

Получает или задает имя последовательности, номер которой включен в номер страницы.

```csharp
public string SequenceName { get; set; }
```

### Примеры

Показывает, как разделить документ на части, объединив поля ИНДЕКС и ПОСЛЕДОВАТЕЛЬНОСТЬ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создать поле INDEX, которое будет отображать запись для каждого поля XE, найденного в документе.
// Каждая запись будет отображать значение свойства Text поля XE с левой стороны,
// и номер страницы, содержащей поле XE справа.
// Если поля XE имеют одинаковое значение в свойстве «Текст»,
// поле ИНДЕКС сгруппирует их в одну запись.
FieldIndex index = (FieldIndex)builder.InsertField(FieldType.FieldIndex, true);

// В свойстве SequenceName укажите имя последовательности полей SEQ. Каждая запись в этом поле ИНДЕКС теперь также будет отображать
// номер подсчета последовательности в расположении поля XE, которое создало эту запись.
index.SequenceName = "MySequence";

// Установите текст, который будет окружать последовательность и номера страниц, чтобы объяснить их значение пользователю.
// Запись, созданная с этой конфигурацией, будет отображать что-то вроде «MySequence at 1 on page 1» под своим номером страницы.
// PageNumberSeparator и SequenceSeparator не могут быть длиннее 15 символов.
index.PageNumberSeparator = "\tMySequence at ";
index.SequenceSeparator = " on page ";
Assert.IsTrue(index.HasSequenceName);

Assert.AreEqual(" INDEX  \\s MySequence \\e \"\tMySequence at \" \\d \" on page \"", index.GetFieldCode());

// В полях SEQ отображается счетчик, который увеличивается в каждом поле SEQ.
// Эти поля также поддерживают отдельные счетчики для каждой уникальной именованной последовательности
// определяется свойством "SequenceIdentifier" поля SEQ.
// Вставляем поле SEQ, которое перемещает последовательность «MySequence» на 1.
// Это поле ничем не отличается от обычного текста документа. Он не будет отображаться в таблице содержания поля INDEX.
builder.InsertBreak(BreakType.PageBreak);
FieldSeq sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

Assert.AreEqual(" SEQ  MySequence", sequenceField.GetFieldCode());

// Вставьте поле XE, которое создаст запись в поле INDEX.
// Так как "MySequence" находится на 1, а это поле XE на странице 2, вместе с пользовательскими разделителями, которые мы определили выше,
// запись ИНДЕКС этого поля будет отображать «Кот» слева и «Моя последовательность в 1 на странице 2» справа.
FieldXE indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

Assert.AreEqual(" XE  Cat", indexEntry.GetFieldCode());

// Вставьте разрыв страницы и используйте поля SEQ для продвижения "MySequence" до 3.
builder.InsertBreak(BreakType.PageBreak);
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";
sequenceField = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
sequenceField.SequenceIdentifier = "MySequence";

// Вставьте поле XE с тем же свойством Text, что и выше.
// Запись INDEX сгруппирует поля XE с соответствующими значениями в свойстве "Текст"
// в одну запись вместо создания записи для каждого поля XE.
// Так как мы находимся на странице 2 с "MySequence" на 3, ", 3 на странице 3" будет добавлено к той же записи INDEX, что и выше.
// Часть номера страницы этой записи INDEX теперь будет отображать «MySequence at 1 on page 2, 3 on page 3».
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Cat";

// Вставьте поле XE с новым и уникальным значением свойства Text.
// Это добавит новую запись с MySequence в 3 на странице 4.
builder.InsertBreak(BreakType.PageBreak);
indexEntry = (FieldXE)builder.InsertField(FieldType.FieldIndexEntry, true);
indexEntry.Text = "Dog";

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.INDEX.XE.Sequence.docx");
```

### Смотрите также

* class [FieldIndex](../)
* пространство имен [Aspose.Words.Fields](../../fieldindex/)
* сборка [Aspose.Words](../../../)


