---
title: HtmlSaveOptions.ExportTextInputFormFieldAsText
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Управляет сохранением полей формы ввода текста в формате HTML или MHTML. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 270
url: /ru/net/aspose.words.saving/htmlsaveoptions/exporttextinputformfieldastext/
---
## HtmlSaveOptions.ExportTextInputFormFieldAsText property

Управляет сохранением полей формы ввода текста в формате HTML или MHTML. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool ExportTextInputFormFieldAsText { get; set; }
```

### Примечания

При установке на`истинный` , экспортирует поля формы ввода текста как обычный текст. Когда`ЛОЖЬ`, экспортирует поля формы ввода текста Word как элементы INPUT в HTML.

При экспорте в EPUB поля формы ввода текста всегда сохраняются как текст из-за требований этого формата.

### Примеры

Показывает, как указать папку для хранения связанных изображений после сохранения в формате .html.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

string imagesDir = Path.Combine(ArtifactsDir, "SaveHtmlWithOptions");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

// Установите параметр для экспорта полей формы в виде простого текста вместо элементов ввода HTML.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true, 
    ImagesFolder = imagesDir
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveHtmlWithOptions.html", options);
```

### Смотрите также

* class [HtmlSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../htmlsaveoptions/)
* сборка [Aspose.Words](../../../)


