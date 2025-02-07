---
title: FieldQuote.Text
second_title: Справочник по API Aspose.Words для .NET
description: FieldQuote свойство. Получает или задает текст для извлечения.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldquote/text/
---
## FieldQuote.Text property

Получает или задает текст для извлечения.

```csharp
public string Text { get; set; }
```

### Примеры

Показывает использование поля ЦИТАТА.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте поле QUOTE, которое будет отображать значение его свойства Text.
FieldQuote field = (FieldQuote)builder.InsertField(FieldType.FieldQuote, true);
field.Text = "\"Quoted text\"";

Assert.AreEqual(" QUOTE  \"\\\"Quoted text\\\"\"", field.GetFieldCode());

// Вставляем поле ЦИТАТА и вкладываем в него поле ДАТА.
// Поля ДАТА обновляют свое значение до текущей даты каждый раз, когда мы открываем документ с помощью Microsoft Word.
// Такое вложение поля DATE внутрь поля QUOTE заморозит его значение
// до даты создания документа.
builder.Write("\nDocument creation date: ");
field = (FieldQuote)builder.InsertField(FieldType.FieldQuote, true);
builder.MoveTo(field.Separator);
builder.InsertField(FieldType.FieldDate, true);

Assert.AreEqual(" QUOTE \u0013 DATE \u0014" + DateTime.Now.Date.ToShortDateString() + "\u0015", field.GetFieldCode());

// Обновляем все поля, чтобы отображались правильные результаты.
doc.UpdateFields();

Assert.AreEqual("\"Quoted text\"", doc.Range.Fields[0].Result);

doc.Save(ArtifactsDir + "Field.QUOTE.docx");
```

### Смотрите также

* class [FieldQuote](../)
* пространство имен [Aspose.Words.Fields](../../fieldquote/)
* сборка [Aspose.Words](../../../)


