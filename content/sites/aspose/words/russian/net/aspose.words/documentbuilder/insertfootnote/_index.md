---
title: DocumentBuilder.InsertFootnote
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder метод. Вставляет сноску или концевую сноску в документ.
type: docs
weight: 310
url: /ru/net/aspose.words/documentbuilder/insertfootnote/
---
## InsertFootnote(FootnoteType, string) {#insertfootnote}

Вставляет сноску или концевую сноску в документ.

```csharp
public Footnote InsertFootnote(FootnoteType footnoteType, string footnoteText)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| footnoteType | FootnoteType | Указывает, вставлять ли сноску или концевую сноску. |
| footnoteText | String | Задает текст сноски. |

### Возвращаемое значение

Возвращает только что созданный объект сноски.

### Примеры

Показывает, как ссылаться на текст со сноской и концевой сноской.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставляем некоторый текст и помечаем его сноской со свойством IsAuto, для которого по умолчанию установлено значение «true»,
// поэтому маркер, видимый в основном тексте, будет автоматически пронумерован как «1»,
// и сноска появится внизу страницы.
builder.Write("This text will be referenced by a footnote.");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote comment regarding referenced text.");

// Вставьте дополнительный текст и отметьте его концевой сноской с пользовательской контрольной меткой,
// который будет использоваться вместо числа "2" и установить для "IsAuto" значение false.
builder.Write("This text will be referenced by an endnote.");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote comment regarding referenced text.", "CustomMark");

// Сноски всегда появляются внизу текста, на который они ссылаются,
// поэтому этот разрыв страницы не повлияет на сноску.
// С другой стороны, концевые сноски всегда находятся в конце документа
// чтобы этот разрыв страницы переместил концевую сноску на следующую страницу.
builder.InsertBreak(BreakType.PageBreak);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertFootnote.docx");
```

### Смотрите также

* class [Footnote](../../../aspose.words.notes/footnote/)
* enum [FootnoteType](../../../aspose.words.notes/footnotetype/)
* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)

---

## InsertFootnote(FootnoteType, string, string) {#insertfootnote_1}

Вставляет сноску или концевую сноску в документ.

```csharp
public Footnote InsertFootnote(FootnoteType footnoteType, string footnoteText, string referenceMark)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| footnoteType | FootnoteType | Указывает, вставлять ли сноску или концевую сноску. |
| footnoteText | String | Задает текст сноски. |
| referenceMark | String | Указывает пользовательскую метку сноски. |

### Возвращаемое значение

Возвращает только что созданный объект сноски.

### Примеры

Показывает, как ссылаться на текст со сноской и концевой сноской.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставляем некоторый текст и помечаем его сноской со свойством IsAuto, для которого по умолчанию установлено значение «true»,
// поэтому маркер, видимый в основном тексте, будет автоматически пронумерован как «1»,
// и сноска появится внизу страницы.
builder.Write("This text will be referenced by a footnote.");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote comment regarding referenced text.");

// Вставьте дополнительный текст и отметьте его концевой сноской с пользовательской контрольной меткой,
// который будет использоваться вместо числа "2" и установить для "IsAuto" значение false.
builder.Write("This text will be referenced by an endnote.");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote comment regarding referenced text.", "CustomMark");

// Сноски всегда появляются внизу текста, на который они ссылаются,
// поэтому этот разрыв страницы не повлияет на сноску.
// С другой стороны, концевые сноски всегда находятся в конце документа
// чтобы этот разрыв страницы переместил концевую сноску на следующую страницу.
builder.InsertBreak(BreakType.PageBreak);

doc.Save(ArtifactsDir + "DocumentBuilder.InsertFootnote.docx");
```

### Смотрите также

* class [Footnote](../../../aspose.words.notes/footnote/)
* enum [FootnoteType](../../../aspose.words.notes/footnotetype/)
* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


