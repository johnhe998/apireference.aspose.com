---
title: FieldSeq.ResetHeadingLevel
second_title: Справочник по API Aspose.Words для .NET
description: FieldSeq свойство. Получает или задает целое число представляющее уровень заголовка на который сбрасывается порядковый номер. Возвращает 1 если номер отсутствует.
type: docs
weight: 40
url: /ru/net/aspose.words.fields/fieldseq/resetheadinglevel/
---
## FieldSeq.ResetHeadingLevel property

Получает или задает целое число, представляющее уровень заголовка, на который сбрасывается порядковый номер. Возвращает -1, если номер отсутствует.

```csharp
public string ResetHeadingLevel { get; set; }
```

### Примеры

Показывает создание нумерации с использованием полей SEQ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// В полях SEQ отображается счетчик, который увеличивается в каждом поле SEQ.
// Эти поля также поддерживают отдельные счетчики для каждой уникальной именованной последовательности
// определяется свойством "SequenceIdentifier" поля SEQ.
// Вставьте поле SEQ, которое будет отображать текущее значение счетчика «MySequence»,
// после использования свойства "ResetNumber", чтобы установить его в 100.
builder.Write("#");
FieldSeq fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.ResetNumber = "100";
fieldSeq.Update();

Assert.AreEqual(" SEQ  MySequence \\r 100", fieldSeq.GetFieldCode());
Assert.AreEqual("100", fieldSeq.Result);

// Показать следующее число в этой последовательности с другим полем SEQ.
builder.Write(", #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.Update();

Assert.AreEqual("101", fieldSeq.Result);

// Вставить заголовок уровня 1.
builder.InsertBreak(BreakType.ParagraphBreak);
builder.ParagraphFormat.Style = doc.Styles["Heading 1"];
builder.Writeln("This level 1 heading will reset MySequence to 1");
builder.ParagraphFormat.Style = doc.Styles["Normal"];

// Вставьте другое поле SEQ из той же последовательности и настройте его для сброса счетчика в каждом заголовке с 1.
builder.Write("\n#");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.ResetHeadingLevel = "1";
fieldSeq.Update();

// Приведенный выше заголовок является заголовком уровня 1, поэтому счетчик для этой последовательности сбрасывается на 1.
Assert.AreEqual(" SEQ  MySequence \\s 1", fieldSeq.GetFieldCode());
Assert.AreEqual("1", fieldSeq.Result);

// Переход к следующему номеру этой последовательности.
builder.Write(", #");
fieldSeq = (FieldSeq)builder.InsertField(FieldType.FieldSequence, true);
fieldSeq.SequenceIdentifier = "MySequence";
fieldSeq.InsertNextNumber = true;
fieldSeq.Update();

Assert.AreEqual(" SEQ  MySequence \\n", fieldSeq.GetFieldCode());
Assert.AreEqual("2", fieldSeq.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.SEQ.ResetNumbering.docx");
```

### Смотрите также

* class [FieldSeq](../)
* пространство имен [Aspose.Words.Fields](../../fieldseq/)
* сборка [Aspose.Words](../../../)


