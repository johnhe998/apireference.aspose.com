---
title: Font.LocaleId
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Получает или задает идентификатор локали язык отформатированных символов.
type: docs
weight: 200
url: /ru/net/aspose.words/font/localeid/
---
## Font.LocaleId property

Получает или задает идентификатор локали (язык) отформатированных символов.

```csharp
public int LocaleId { get; set; }
```

### Примечания

Список идентификаторов локалей см. на странице https://msdn.microsoft.com/en-us/library/cc233965.aspx .

### Примеры

Показывает, как установить языковой стандарт текста, который мы добавляем с помощью конструктора документов.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Если мы установим язык шрифта на английский и вставим немного русского текста,
// средство проверки орфографии для английской локали не распознает текст и обнаружит его как орфографическую ошибку.
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;
builder.Writeln("Привет!");

// Установите соответствующий языковой стандарт для текста, который мы собираемся добавить, чтобы применить соответствующую проверку орфографии.
builder.Font.LocaleId = new CultureInfo("ru-RU", false).LCID;
builder.Writeln("Привет!");

doc.Save(ArtifactsDir + "Font.LocaleId.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


