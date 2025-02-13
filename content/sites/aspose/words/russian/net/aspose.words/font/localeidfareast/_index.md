---
title: Font.LocaleIdFarEast
second_title: Справочник по API Aspose.Words для .NET
description: Font свойство. Получает или задает идентификатор локали язык отформатированных азиатских символов.
type: docs
weight: 220
url: /ru/net/aspose.words/font/localeidfareast/
---
## Font.LocaleIdFarEast property

Получает или задает идентификатор локали (язык) отформатированных азиатских символов.

```csharp
public int LocaleIdFarEast { get; set; }
```

### Примечания

Список идентификаторов локалей см. на странице https://msdn.microsoft.com/en-us/library/cc233965.aspx .

### Примеры

Показывает, как вставлять и форматировать текст на дальневосточном языке.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Укажите настройки шрифта, которые конструктор документов будет применять к любому вставляемому тексту.
builder.Font.Name = "Courier New";
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// Назовите эквиваленты «FarEast» для нашего шрифта и локали.
// Если компоновщик вставляет азиатские символы с этой конфигурацией шрифта, то каждый запуск, содержащий
// эти символы будут отображаться с использованием шрифта/региона "FarEast" вместо стандартного.
// Это может быть полезно, когда западный шрифт не имеет идеального представления для азиатских символов.
builder.Font.NameFarEast = "SimSun";
builder.Font.LocaleIdFarEast = new CultureInfo("zh-CN", false).LCID;

// Этот текст будет отображаться шрифтом/языком по умолчанию.
builder.Writeln("Hello world!");

// Поскольку это азиатские символы, в этом запуске будут применены наши эквиваленты шрифта/локали FarEast.
builder.Writeln("你好世界");

doc.Save(ArtifactsDir + "Font.FarEast.docx");
```

### Смотрите также

* class [Font](../)
* пространство имен [Aspose.Words](../../font/)
* сборка [Aspose.Words](../../../)


