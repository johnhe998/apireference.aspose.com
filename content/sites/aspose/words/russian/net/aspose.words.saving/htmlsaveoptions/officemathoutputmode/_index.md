---
title: HtmlSaveOptions.OfficeMathOutputMode
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Управляет экспортом объектов OfficeMath в HTML MHTML или EPUB. Значение по умолчаниюHtmlOfficeMathOutputMode.Image .
type: docs
weight: 400
url: /ru/net/aspose.words.saving/htmlsaveoptions/officemathoutputmode/
---
## HtmlSaveOptions.OfficeMathOutputMode property

Управляет экспортом объектов OfficeMath в HTML, MHTML или EPUB. Значение по умолчанию:`HtmlOfficeMathOutputMode.Image` .

```csharp
public HtmlOfficeMathOutputMode OfficeMathOutputMode { get; set; }
```

### Примеры

Показывает, как указать, как экспортировать объекты Microsoft OfficeMath в HTML.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

// Когда мы сохраняем документ в HTML, мы можем передать объект SaveOptions
// чтобы определить, как операция сохранения обрабатывает объекты OfficeMath.
// Установка свойства "OfficeMathOutputMode" в "HtmlOfficeMathOutputMode.Image"
// преобразует каждый объект OfficeMath в изображение.
// Установка свойства "OfficeMathOutputMode" в "HtmlOfficeMathOutputMode.MathML"
// преобразует каждый объект OfficeMath в MathML.
// Установка свойства "OfficeMathOutputMode" в "HtmlOfficeMathOutputMode.Text"
// будет представлять каждую формулу OfficeMath с помощью обычного текста HTML.
HtmlSaveOptions options = new HtmlSaveOptions { OfficeMathOutputMode = htmlOfficeMathOutputMode };

doc.Save(ArtifactsDir + "HtmlSaveOptions.OfficeMathOutputMode.html", options);
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.OfficeMathOutputMode.html");

switch (htmlOfficeMathOutputMode)
{
    case HtmlOfficeMathOutputMode.Image:
        Assert.True(Regex.Match(outDocContents, 
            "<p style=\"margin-top:0pt; margin-bottom:10pt\">" +
                "<img src=\"HtmlSaveOptions.OfficeMathOutputMode.001.png\" width=\"159\" height=\"19\" alt=\"\" style=\"vertical-align:middle; " +
                "-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
            "</p>").Success);
        break;
    case HtmlOfficeMathOutputMode.MathML:
        Assert.True(Regex.Match(outDocContents,
            "<p style=\"margin-top:0pt; margin-bottom:10pt; text-align:center\">" +
                "<math xmlns=\"http://www.w3.org/1998/Math/MathML\">" +
                    "<mi>i</mi>" +
                    "<mo>[+]</mo>" +
                    "<mi>b</mi>" +
                    "<mo>-</mo>" +
                    "<mi>c</mi>" +
                    "<mo>≥</mo>" +
                    ".*" +
                "</math>" +
            "</p>").Success);
        break;
    case HtmlOfficeMathOutputMode.Text:
        Assert.True(Regex.Match(outDocContents,
            @"<p style=\""margin-top:0pt; margin-bottom:10pt; text-align:center\"">" +
                @"<span style=\""font-family:'Cambria Math'\"">i[+]b-c≥iM[+]bM-cM </span>" +
            "</p>").Success);
        break;
}
```

### Смотрите также

* enum [HtmlOfficeMathOutputMode](../../htmlofficemathoutputmode/)
* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


