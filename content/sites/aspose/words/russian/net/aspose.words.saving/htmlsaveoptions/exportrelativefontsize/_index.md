---
title: HtmlSaveOptions.ExportRelativeFontSize
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает должны ли размеры шрифта выводиться в относительных единицах при сохранении в HTML MHTML или EPUB. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 240
url: /ru/net/aspose.words.saving/htmlsaveoptions/exportrelativefontsize/
---
## HtmlSaveOptions.ExportRelativeFontSize property

Указывает, должны ли размеры шрифта выводиться в относительных единицах при сохранении в HTML, MHTML или EPUB. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool ExportRelativeFontSize { get; set; }
```

### Примечания

Во многих существующих документах (HTML, IDPF EPUB) размеры шрифтов указаны в относительных единицах. Это позволяет приложениям настраивать размер текста при просмотре/обработке документов. Например, Microsoft Internet Explorer имеет подменю «Вид-&gt;Размер текста», Adobe Digital Editions имеет две кнопки: Увеличить/Уменьшить размер текста. Если вы ожидаете, что эта функция будет работать, установите`ExportRelativeFontSize` собственность на`истинный` .

Модель документа Aspose Words содержит и работает только с единицами абсолютного размера шрифта. Относительные единицы требуют дополнительной логики для пересчета от некоторого начального (стандартного) размера. Размер шрифта **Обычный** стиль документа принят за стандартный. Например, если **Обычный** имеет шрифт 12pt, а некоторый текст имеет размер 18pt, тогда он будет выводиться как **1,5 см.** к HTML.

Когда этот параметр включен, элементы документа, кроме текста, по-прежнему будут иметь абсолютные размеры. Также некоторые атрибуты, связанные с текстом , могут быть выражены абсолютно. В частности, межстрочный интервал, указанный в правиле «точно» , может привести к нежелательным результатам при масштабировании текста. Таким образом, исходные документы должны быть правильно оформлены и протестированы при экспорте с`ExportRelativeFontSize` установлен в`истинный`.

### Примеры

Показывает, как использовать относительные размеры шрифта при сохранении в .html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Default font size, ");
builder.Font.Size = 24;
builder.Writeln("2x default font size,");
builder.Font.Size = 96;
builder.Write("8x default font size");

// Когда мы сохраняем документ в HTML, мы можем передать объект SaveOptions
// чтобы определить, использовать ли относительный или абсолютный размер шрифта.
// Установите для флага «ExportRelativeFontSize» значение «true», чтобы объявить размеры шрифта
 // используя единицу измерения "em", которая является коэффициентом, умножающим текущий размер шрифта.
// Установите для флага «ExportRelativeFontSize» значение «false», чтобы объявить размеры шрифта
// с использованием единицы измерения "pt", которая представляет собой абсолютный размер шрифта в пунктах.
HtmlSaveOptions options = new HtmlSaveOptions { ExportRelativeFontSize = exportRelativeFontSize };

doc.Save(ArtifactsDir + "HtmlSaveOptions.RelativeFontSize.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.RelativeFontSize.html");

if (exportRelativeFontSize)
{
    Assert.True(outDocContents.Contains(
        "<body style=\"font-family:'Times New Roman'\">" +
            "<div>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                    "<span>Default font size, </span>" +
                "</p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt; font-size:2em\">" +
                    "<span>2x default font size,</span>" +
                "</p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt; font-size:8em\">" +
                    "<span>8x default font size</span>" +
                "</p>" +
            "</div>" +
        "</body>"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<body style=\"font-family:'Times New Roman'; font-size:12pt\">" +
            "<div>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
                    "<span>Default font size, </span>" +
                "</p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt; font-size:24pt\">" +
                    "<span>2x default font size,</span>" +
                "</p>" +
                "<p style=\"margin-top:0pt; margin-bottom:0pt; font-size:96pt\">" +
                    "<span>8x default font size</span>" +
                "</p>" +
            "</div>" +
        "</body>"));
}
```

### Смотрите также

* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


