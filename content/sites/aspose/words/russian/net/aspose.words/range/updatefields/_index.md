---
title: Range.UpdateFields
second_title: Справочник по API Aspose.Words для .NET
description: Range метод. Обновляет значения полей документа в этом диапазоне.
type: docs
weight: 110
url: /ru/net/aspose.words/range/updatefields/
---
## Range.UpdateFields method

Обновляет значения полей документа в этом диапазоне.

```csharp
public void UpdateFields()
```

### Примечания

Когда вы открываете, изменяете и затем сохраняете документ, Aspose.Words не обновляет поля автоматически, а сохраняет их нетронутыми. правильные (вычисленные) значения полей появляются в сохраненном документе.

Нет необходимости обновлять поля после выполнения слияния, потому что слияние является своего рода полем update и автоматически обновляет все поля в документе.

Этот метод не обновляет все типы полей. Подробный список поддерживаемых типов полей см. в Руководстве программиста.

Этот метод не обновляет поля, связанные с алгоритмами макета страницы (например, PAGE, PAGES, PAGEREF). Поля, связанные с макетом страницы, обновляются при отображении документа или вызове[`UpdatePageLayout`](../../document/updatepagelayout/).

Чтобы обновить поля во всем документе, используйте[`UpdateFields`](../../document/updatefields/).

### Примеры

Показывает, как обновить все поля в диапазоне.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" DOCPROPERTY Category");
builder.InsertBreak(BreakType.SectionBreakEvenPage);
builder.InsertField(" DOCPROPERTY Category");

// Вышеупомянутые поля DOCPROPERTY будут отображать значение этого встроенного свойства документа.
doc.BuiltInDocumentProperties.Category = "MyCategory";

// Если мы обновляем значение свойства документа, нам потребуется обновить все поля DOCPROPERTY, чтобы отобразить его.
Assert.AreEqual(string.Empty, doc.Range.Fields[0].Result);
Assert.AreEqual(string.Empty, doc.Range.Fields[1].Result);

// Обновить все поля, находящиеся в диапазоне первого раздела.
doc.FirstSection.Range.UpdateFields();

Assert.AreEqual("MyCategory", doc.Range.Fields[0].Result);
Assert.AreEqual(string.Empty, doc.Range.Fields[1].Result);
```

### Смотрите также

* class [Range](../)
* пространство имен [Aspose.Words](../../range/)
* сборка [Aspose.Words](../../../)


