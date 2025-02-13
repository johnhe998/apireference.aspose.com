---
title: HtmlSaveOptions.ExportXhtmlTransitional
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает следует ли записывать объявление DOCTYPE при сохранении в HTML или MHTML. Когдаистинный  записывает объявление DOCTYPE в документ перед корневым элементом. Значение по умолчаниюЛОЖЬ. При сохранении в EPUB или HTML5 Html5  всегда записывается объявление DOCTYPE .
type: docs
weight: 290
url: /ru/net/aspose.words.saving/htmlsaveoptions/exportxhtmltransitional/
---
## HtmlSaveOptions.ExportXhtmlTransitional property

Указывает, следует ли записывать объявление DOCTYPE при сохранении в HTML или MHTML. Когда`истинный` , записывает объявление DOCTYPE в документ перед корневым элементом. Значение по умолчанию:`ЛОЖЬ`. При сохранении в EPUB или HTML5 (Html5 ) всегда записывается объявление DOCTYPE .

```csharp
public bool ExportXhtmlTransitional { get; set; }
```

### Примечания

Aspose.Words всегда пишет правильно сформированный HTML, независимо от этой настройки.

Когда`истинный`, начало выходного HTML-документа будет выглядеть так:

Aspose.Words стремится выводить XHTML в соответствии со спецификацией XHTML 1.0 Transitional, , но вывод не всегда будет проверяться на соответствие DTD. Некоторые структуры внутри документа Microsoft Word трудно или невозможно сопоставить с документом, который будет проверяться на соответствие схеме XHTML. Например, XHTML не допускает вложенных списков (UL не может быть вложен в другой элемент UL), но в документе Microsoft Word многоуровневые списки встречаются довольно часто.

```csharp
<?xml version="1.0" encoding="utf-8" standalone="no" ?>
<!DOCTYPE html 
      PUBLIC "-//W3C//DTD XHTML 1.0 Переходный//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
```

### Примеры

Показывает, как отображать заголовок DOCTYPE при преобразовании документов в переходный стандарт Xhtml 1.0.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    HtmlVersion = HtmlVersion.Xhtml,
    ExportXhtmlTransitional = showDoctypeDeclaration,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html", options);

// Наш документ будет содержать заголовок объявления DOCTYPE, только если мы установили флаг "ExportXhtmlTransitional" в значение "true".
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html");

if (showDoctypeDeclaration)
    Assert.True(outDocContents.Contains(
        "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"no\"?>\r\n" +
        "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Transitional//EN\" \"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd\">\r\n" +
        "<html xmlns=\"http://www.w3.org/1999/xhtml\">"));
else
    Assert.True(outDocContents.Contains("<html>"));
```

### Смотрите также

* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


