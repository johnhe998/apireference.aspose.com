---
title: Enum ResourceLoadingAction
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Loading.ResourceLoadingAction перечисление. Задает режим загрузки ресурсов.
type: docs
weight: 3480
url: /ru/net/aspose.words.loading/resourceloadingaction/
---
## ResourceLoadingAction enumeration

Задает режим загрузки ресурсов.

```csharp
public enum ResourceLoadingAction
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Default | `0` | Aspose.Words загрузит этот ресурс как обычно. |
| Skip | `1` | Aspose.Words пропустит загрузку этого ресурса. Для изображения будет сохранена только ссылка без данных, таблица стилей CSS будет проигнорирована для формата HTML. |
| UserProvided | `2` | Aspose.Words будет использовать массив байтов, предоставленный пользователем в[`SetData`](../resourceloadingargs/setdata/) как данные ресурса. |

### Примеры

Показывает, как настроить процесс загрузки внешних ресурсов в документ.

```csharp
{
    Document doc = new Document();
    doc.ResourceLoadingCallback = new ImageNameHandler();

    DocumentBuilder builder = new DocumentBuilder(doc);

    // Изображения обычно вставляются с использованием URI или массива байтов.
    // Каждый экземпляр загрузки ресурсов будет вызывать метод ResourceLoading нашего обратного вызова.
    builder.InsertImage("Google logo");
    builder.InsertImage("Aspose logo");
    builder.InsertImage("Watermark");

    Assert.AreEqual(3, doc.GetChildNodes(NodeType.Shape, true).Count);

    doc.Save(ArtifactsDir + "DocumentBase.ResourceLoadingCallback.docx");

/// <summary>
/// Позволяет нам загружать изображения в документ, используя предопределенные сокращения, а не URI.
/// Это отделит логику загрузки изображения от остальной конструкции документа.
/// </summary>
private class ImageNameHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(ResourceLoadingArgs args)
    {
        // Если этот обратный вызов встречает одно из сокращений изображения при загрузке изображения,
        // он будет применять уникальную логику для каждого определенного сокращения вместо того, чтобы рассматривать его как URI.
        if (args.ResourceType == ResourceType.Image)
            switch (args.OriginalUri)
            {
                case "Google logo":
                    using (WebClient webClient = new WebClient())
                    {
                        args.SetData(webClient.DownloadData("http://www.google.com/images/logos/ps_logo2.png"));
                    }

                    return ResourceLoadingAction.UserProvided;

                case "Aspose logo":
                    args.SetData(File.ReadAllBytes(ImageDir + "Logo.jpg"));

                    return ResourceLoadingAction.UserProvided;

                case "Watermark":
                    args.SetData(File.ReadAllBytes(ImageDir + "Transparent background logo.png"));

                    return ResourceLoadingAction.UserProvided;
            }

        return ResourceLoadingAction.Default;
    }
}
```

### Смотрите также

* пространство имен [Aspose.Words.Loading](../../aspose.words.loading/)
* сборка [Aspose.Words](../../)


