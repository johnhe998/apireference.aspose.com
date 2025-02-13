---
title: HtmlSaveOptions.ImagesFolder
second_title: Справочник по API Aspose.Words для .NET
description: HtmlSaveOptions свойство. Указывает физическую папку в которой сохраняются изображения при экспорте документа в формат HTML. По умолчанию  пустая строка.
type: docs
weight: 370
url: /ru/net/aspose.words.saving/htmlsaveoptions/imagesfolder/
---
## HtmlSaveOptions.ImagesFolder property

Указывает физическую папку, в которой сохраняются изображения при экспорте документа в формат HTML. По умолчанию — пустая строка.

```csharp
public string ImagesFolder { get; set; }
```

### Примечания

Когда вы сохраняете[`Document`](../../../aspose.words/document/) в формате HTML Aspose.Words необходимо сохранить все изображения , встроенные в документ, как отдельные файлы.`ImagesFolder` позволяет указать, где изображения будут сохранены и[`ImagesFolderAlias`](../imagesfolderalias/) позволяет указать, как будут создаваться URI изображения.

Если вы сохраняете документ в файл и указываете имя файла, Aspose.Words по умолчанию сохраняет изображения в той же папке, где сохранен файл документа. Использовать`ImagesFolder` , чтобы переопределить это поведение.

Если вы сохраняете документ в поток, Aspose.Words не имеет папки для сохранения изображений, , но все равно нужно куда-то сохранять изображения. В этом случае вам необходимо указать доступную папку в`ImagesFolder` свойство или предоставить пользовательские потоки через [`ImageSavingCallback`](../imagesavingcallback/) обработчик события.

Если папка, указанная`ImagesFolder` не существует, он будет создан автоматически.

[`ResourceFolder`](../resourcefolder/) — это еще один способ указать папку, в которую следует сохранять изображения.

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


