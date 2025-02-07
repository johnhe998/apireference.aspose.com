---
title: HtmlSaveOptions.ExportPageMargins
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает экспортируются ли поля страницы в HTML MHTML или EPUB. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 220
url: /ru/net/aspose.words.saving/htmlsaveoptions/exportpagemargins/
---
## HtmlSaveOptions.ExportPageMargins property

Указывает, экспортируются ли поля страницы в HTML, MHTML или EPUB. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool ExportPageMargins { get; set; }
```

### Примечания

Aspose.Words по умолчанию не показывает область полей страницы. Если какие-либо элементы полностью или частично обрезаны краем документа, отображаемая область может быть расширена с помощью этой опции .

### Примеры

Показывает, как отображать объекты, находящиеся за пределами границ, в выходных HTML-документах.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Используйте построитель, чтобы вставить фигуру без переноса.
Shape shape = builder.InsertShape(ShapeType.Cube, 200, 200);

shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.WrapType = WrapType.None;

// Отрицательные значения позиции фигуры могут поместить фигуру за пределы страницы.
// Если мы экспортируем это в HTML, форма будет выглядеть усеченной.
shape.Left = -150;

// При сохранении документа в HTML мы можем передать объект SaveOptions
// чтобы решить, следует ли настраивать страницу для полного отображения объектов за пределами границ.
// Если мы установим для флага «ExportPageMargins» значение «true», форма будет полностью видна в выходном HTML.
// Если мы установим флаг "ExportPageMargins" в "false",
// наш документ будет отображать усеченную форму, как мы видели бы ее в Microsoft Word.
HtmlSaveOptions options = new HtmlSaveOptions { ExportPageMargins = exportPageMargins };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportPageMargins.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportPageMargins.html");

if (exportPageMargins)
{
    Assert.True(outDocContents.Contains("<style type=\"text/css\">div.Section1 { margin:70.85pt }</style>"));
    Assert.True(outDocContents.Contains("<div class=\"Section1\"><p style=\"margin-top:0pt; margin-left:151pt; margin-bottom:0pt\">"));
}
else
{
    Assert.False(outDocContents.Contains("style type=\"text/css\">"));
    Assert.True(outDocContents.Contains("<div><p style=\"margin-top:0pt; margin-left:221.85pt; margin-bottom:0pt\">"));
}
```

### Смотрите также

* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


