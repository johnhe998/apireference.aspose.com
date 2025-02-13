---
title: StructuredDocumentTag.DateStorageFormat
second_title: Справочник по API Aspose.Words для .NET
description: StructuredDocumentTag свойство. Получает/устанавливает формат в котором дата для SDT даты сохраняется когда СДТ привязан к узлу XML в хранилище данных документа. Значение по умолчаниюDateTime
type: docs
weight: 110
url: /ru/net/aspose.words.markup/structureddocumenttag/datestorageformat/
---
## StructuredDocumentTag.DateStorageFormat property

Получает/устанавливает формат, в котором дата для SDT даты сохраняется, когда **СДТ** привязан к узлу XML в хранилище данных документа. Значение по умолчанию:DateTime

```csharp
public SdtDateStorageFormat DateStorageFormat { get; set; }
```

### Примечания

Доступ к этому свойству будет работать только дляDate Тип SDT.

Для всех других типов SDT будет иметь место исключение.

### Примеры

Показывает, как предложить пользователю ввести дату с тегом структурированного документа.

```csharp
Document doc = new Document();

// Вставьте структурированный тег документа, предлагающий пользователю ввести дату.
// В Microsoft Word этот элемент известен как «элемент управления содержимым средства выбора даты».
// Когда мы нажимаем на стрелку справа от этого тега в Microsoft Word,
// мы увидим всплывающее окно в виде кликабельного календаря.
// Мы можем использовать это всплывающее окно для выбора даты, которую будет отображать тег.
StructuredDocumentTag sdtDate = new StructuredDocumentTag(doc, SdtType.Date, MarkupLevel.Inline);

// Отображение даты в соответствии с арабским языком Саудовской Аравии.
sdtDate.DateDisplayLocale = CultureInfo.GetCultureInfo("ar-SA").LCID;

// Установите формат, в котором будет отображаться дата.
sdtDate.DateDisplayFormat = "dd MMMM, yyyy";
sdtDate.DateStorageFormat = SdtDateStorageFormat.DateTime;

// Отображение даты по календарю Хиджры.
sdtDate.CalendarType = SdtCalendarType.Hijri;

// Прежде чем пользователь выберет дату в Microsoft Word, тег будет отображать текст «Нажмите здесь, чтобы ввести дату».
// В соответствии с календарем тега установите свойство «FullDate», чтобы тег отображал дату по умолчанию.
sdtDate.FullDate = new DateTime(1440, 10, 20);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(sdtDate);

doc.Save(ArtifactsDir + "StructuredDocumentTag.Date.docx");
```

### Смотрите также

* enum [SdtDateStorageFormat](../../sdtdatestorageformat/)
* class [StructuredDocumentTag](../)
* пространство имен [Aspose.Words.Markup](../../structureddocumenttag/)
* сборка [Aspose.Words](../../../)


