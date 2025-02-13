---
title: XamlFixedSaveOptions.SaveFormat
second_title: Справочник по API Aspose.Words для .NET
description: XamlFixedSaveOptions свойство. Определяет формат в котором документ будет сохранен если используется этот объект параметров сохранения.XamlFixed .
type: docs
weight: 50
url: /ru/net/aspose.words.saving/xamlfixedsaveoptions/saveformat/
---
## XamlFixedSaveOptions.SaveFormat property

Определяет формат, в котором документ будет сохранен, если используется этот объект параметров сохранения.XamlFixed .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### Примеры

Показывает, как распечатать URI связанных ресурсов, созданных при преобразовании документа в XAML фиксированной формы.

```csharp
public void ResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");
    ResourceUriPrinter callback = new ResourceUriPrinter();

    // Создаем объект "XamlFixedSaveOptions", который мы можем передать методу "Сохранить" документа
    // чтобы изменить способ сохранения документа в формате сохранения XAML.
    XamlFixedSaveOptions options = new XamlFixedSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFixed, options.SaveFormat);

    // Используйте свойство "ResourcesFolder", чтобы назначить папку в локальной файловой системе, в которую
    // Aspose.Words сохранит все связанные ресурсы документа, такие как изображения и шрифты.
    options.ResourcesFolder = ArtifactsDir + "XamlFixedResourceFolder";

    // Используйте свойство "ResourcesFolderAlias", чтобы использовать эту папку
    // при построении URI изображения вместо имени папки ресурсов.
    options.ResourcesFolderAlias = ArtifactsDir + "XamlFixedFolderAlias";

    options.ResourceSavingCallback = callback;

    // Папка, указанная в «ResourcesFolderAlias», должна содержать ресурсы вместо «ResourcesFolder».
    // Мы должны убедиться, что папка существует, прежде чем потоки обратного вызова смогут поместить в нее свои ресурсы.
    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFixedSaveOptions.ResourceFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine(resource);
}

/// <summary>
/// Подсчитывает и печатает URI ресурсов, созданных во время преобразования в фиксированный .xaml.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    public ResourceUriPrinter()
    {
        Resources = new List<string>();
    }

    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Resources.Add($"Resource \"{args.ResourceFileName}\"\n\t{args.ResourceFileUri}");

        // Если бы мы указали псевдоним папки ресурсов, нам также понадобился бы
        // чтобы перенаправить каждый поток, чтобы поместить его ресурс в папку псевдонима.
        args.ResourceStream = new FileStream(args.ResourceFileUri, FileMode.Create);
        args.KeepResourceStreamOpen = false;
    }

    public List<string> Resources { get; }
}
```

### Смотрите также

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [XamlFixedSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../xamlfixedsaveoptions/)
* сборка [Aspose.Words](../../../)


