---
title: FieldListNum.ListName
second_title: Справочник по API Aspose.Words для .NET
description: FieldListNum свойство. Получает или задает имя определения абстрактной нумерации используемого для нумерации.
type: docs
weight: 40
url: /ru/net/aspose.words.fields/fieldlistnum/listname/
---
## FieldListNum.ListName property

Получает или задает имя определения абстрактной нумерации, используемого для нумерации.

```csharp
public string ListName { get; set; }
```

### Примеры

Показывает, как нумеровать абзацы с полями LISTNUM.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// В полях LISTNUM отображается число, которое увеличивается в каждом поле LISTNUM.
// Эти поля также имеют различные параметры, которые позволяют нам использовать их для эмуляции нумерованных списков.
FieldListNum field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);

// По умолчанию списки начинают считать с 1, но мы можем установить для этого числа другое значение, например 0.
// В этом поле будет отображаться «0)».
field.StartingNumber = "0";
builder.Writeln("Paragraph 1");

Assert.AreEqual(" LISTNUM  \\s 0", field.GetFieldCode());

 // Поля LISTNUM поддерживают отдельные счетчики для каждого уровня списка.
// Вставка поля LISTNUM в тот же абзац, что и другое поле LISTNUM
// увеличивает уровень списка вместо количества.
// Следующее поле продолжит счет, который мы начали выше, и отобразит значение «1» на уровне списка 1.
builder.InsertField(FieldType.FieldListNum, true);

// Это поле начнет отсчет на уровне списка 2. Оно будет отображать значение «1».
builder.InsertField(FieldType.FieldListNum, true);

// Это поле начнет отсчет на уровне списка 3. Оно будет отображать значение «1».
// Разные уровни списка имеют разное форматирование,
// таким образом, эти поля вместе будут отображать значение "1)a)i)".
builder.InsertField(FieldType.FieldListNum, true);
builder.Writeln("Paragraph 2");

// Следующее поле LISTNUM, которое мы вставляем, продолжит подсчет на уровне списка
// что предыдущее поле LISTNUM было включено.
// Мы можем использовать свойство "ListLevel" для перехода на другой уровень списка.
// Если бы это поле LISTNUM оставалось на уровне списка 3, оно отображало бы "ii)",
// но поскольку мы переместили его на уровень списка 2, он продолжает считать на этом уровне и отображает "b)".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListLevel = "2";
builder.Writeln("Paragraph 3");

Assert.AreEqual(" LISTNUM  \\l 2", field.GetFieldCode());

// Мы можем установить свойство ListName, чтобы заставить поле эмулировать другой тип поля AUTONUM.
// "NumberDefault" эмулирует AUTONUM, "OutlineDefault" эмулирует AUTONUMOUT,
// и «LegalDefault» эмулирует поля AUTONUMLGL.
// Имя списка "OutlineDefault" с 1 в качестве начального номера приведет к отображению "I.".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.StartingNumber = "1";
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 4");

Assert.IsTrue(field.HasListName);
Assert.AreEqual(" LISTNUM  OutlineDefault \\s 1", field.GetFieldCode());

// Имя списка не переносится из предыдущего поля, поэтому нам нужно будет устанавливать его для каждого нового поля.
// Это поле продолжает счет с другим именем списка и отображает «II.».
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 5");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.LISTNUM.docx");
```

### Смотрите также

* class [FieldListNum](../)
* пространство имен [Aspose.Words.Fields](../../fieldlistnum/)
* сборка [Aspose.Words](../../../)


