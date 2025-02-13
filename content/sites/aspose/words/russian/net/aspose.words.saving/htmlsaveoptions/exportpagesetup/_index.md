---
title: HtmlSaveOptions.ExportPageSetup
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает экспортируются ли параметры страницы в формат HTML MHTML или EPUB. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 230
url: /ru/net/aspose.words.saving/htmlsaveoptions/exportpagesetup/
---
## HtmlSaveOptions.ExportPageSetup property

Указывает, экспортируются ли параметры страницы в формат HTML, MHTML или EPUB. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool ExportPageSetup { get; set; }
```

### Примечания

Каждый[`Section`](../../../aspose.words/section/) в модели документа Aspose.Words предоставляет информацию о настройке страницы через[`PageSetup`](../../../aspose.words/pagesetup/) учебный класс. Когда вы экспортируете документ в формат HTML, вам может понадобиться сохранить эту информацию для дальнейшего использования. В частности, настройка страницы может быть важна для рендеринга на постраничный носитель (печать) или последующего преобразования в исходные форматы файлов Microsoft Word (DOCX, DOC, RTF, WML).

В большинстве случаев HTML предназначен для просмотра в браузерах, где не выполняется пагинация. Таким образом, эта функция feature по умолчанию неактивна.

### Примеры

Показывает, как принять решение о сохранении структуры раздела/информации о настройке страницы при сохранении в формате HTML.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TopMargin = 36.0;
pageSetup.BottomMargin = 36.0;
pageSetup.PaperSize = PaperSize.A5;

// При сохранении документа в HTML мы можем передать объект SaveOptions
// для принятия решения о сохранении или отказе от настроек настройки страницы.
// Если мы установим для флага «ExportPageSetup» значение «true», выходной HTML-документ будет содержать нашу конфигурацию настройки страницы.
// Если мы установим для флага «ExportPageSetup» значение «false», операция сохранения отменит наши настройки настройки страницы
// для первого раздела, и оба раздела будут выглядеть одинаково.
HtmlSaveOptions options = new HtmlSaveOptions { ExportPageSetup = exportPageSetup };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportPageSetup.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportPageSetup.html");

if (exportPageSetup)
{
    Assert.True(outDocContents.Contains(
        "<style type=\"text/css\">" +
            "@page Section1 { size:419.55pt 595.3pt; margin:36pt 70.85pt }" +
            "@page Section2 { size:612pt 792pt; margin:70.85pt }" +
            "div.Section1 { page:Section1 }div.Section2 { page:Section2 }" +
        "</style>"));

    Assert.True(outDocContents.Contains(
        "<div class=\"Section1\">" +
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<span>Section 1</span>" +
            "</p>" +
        "</div>"));
}
else
{
    Assert.False(outDocContents.Contains("style type=\"text/css\">"));

    Assert.True(outDocContents.Contains(
        "<div>" +
            "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                "<span>Section 1</span>" +
            "</p>" +
        "</div>"));
}
```

### Смотрите также

* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


