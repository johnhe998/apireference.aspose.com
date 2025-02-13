---
title: XamlFlowSaveOptions.ImagesFolderAlias
second_title: Справочник по API Aspose.Words для .NET
description: XamlFlowSaveOptions свойство. Указывает имя папки используемой для создания URI изображений записываемых в документ XAML. По умолчанию  пустая строка.
type: docs
weight: 40
url: /ru/net/aspose.words.saving/xamlflowsaveoptions/imagesfolderalias/
---
## XamlFlowSaveOptions.ImagesFolderAlias property

Указывает имя папки, используемой для создания URI изображений, записываемых в документ XAML. По умолчанию — пустая строка.

```csharp
public string ImagesFolderAlias { get; set; }
```

### Примечания

Когда вы сохраняете[`Document`](../../../aspose.words/document/) в формате XAML Aspose.Words необходимо сохранить все изображения , встроенные в документ, как отдельные файлы.[`ImagesFolder`](../imagesfolder/) позволяет указать, где изображения будут сохранены и`ImagesFolderAlias` позволяет указать, как будут создаваться URI изображения.

Если`ImagesFolderAlias` не является пустой строкой, то URI изображения, записанный в XAML, будетImagesFolderAlias + &lt;имя файла изображения&gt;.

Если`ImagesFolderAlias` является пустой строкой, то URI изображения, записанный в XAML, будетПапка изображений + &lt;имя файла изображения&gt;.

Если`ImagesFolderAlias` установлен в '.' (точка), то имя файла изображения будет записано в XAML без указания пути независимо от других параметров.

### Примеры

Показывает, как распечатать имена файлов связанных изображений, созданных при преобразовании документа в потоковую форму .xaml.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ImageUriPrinter callback = new ImageUriPrinter(ArtifactsDir + "XamlFlowImageFolderAlias");

    // Создаем объект «XamlFlowSaveOptions», который мы можем передать методу «Сохранить» документа
    // чтобы изменить способ сохранения документа в формате сохранения XAML.
    XamlFlowSaveOptions options = new XamlFlowSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFlow, options.SaveFormat);

    // Используйте свойство «ImagesFolder», чтобы назначить папку в локальной файловой системе, в которую
    // Aspose.Words сохранит все связанные изображения документа.
    options.ImagesFolder = ArtifactsDir + "XamlFlowImageFolder";

    // Используйте свойство "ImagesFolderAlias", чтобы использовать эту папку
    // при построении URI изображения вместо имени папки с изображениями.
    options.ImagesFolderAlias = ArtifactsDir + "XamlFlowImageFolderAlias";

    options.ImageSavingCallback = callback;

    // Папка, указанная в «ImagesFolderAlias», должна содержать ресурсы вместо «ImagesFolder».
    // Мы должны убедиться, что папка существует, прежде чем потоки обратного вызова смогут поместить в нее свои ресурсы.
    Directory.CreateDirectory(options.ImagesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFlowSaveOptions.ImageFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine($"{callback.ImagesFolderAlias}/{resource}");

/// <summary>
/// Подсчитывает и печатает имена файлов изображений, в то время как их родительский документ преобразуется в потоковую форму .xaml.
/// </summary>
private class ImageUriPrinter : IImageSavingCallback
{
    public ImageUriPrinter(string imagesFolderAlias)
    {
        ImagesFolderAlias = imagesFolderAlias;
        Resources = new List<string>();
    }

    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        Resources.Add(args.ImageFileName);

        // Если бы мы указали псевдоним папки с изображениями, нам также понадобился бы
        // чтобы перенаправить каждый поток, чтобы поместить его изображение в папку псевдонима.
        args.ImageStream = new FileStream($"{ImagesFolderAlias}/{args.ImageFileName}", FileMode.Create);
        args.KeepImageStreamOpen = false;
    }

    public string ImagesFolderAlias { get; }
    public List<string> Resources { get; }
}
```

### Смотрите также

* class [XamlFlowSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../xamlflowsaveoptions/)
* сборка [Aspose.Words](../../../)


