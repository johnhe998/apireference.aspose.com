---
title: SvgSaveOptions.ExportEmbeddedImages
second_title: Aspose.Words for .NET API Referansı
description: SvgSaveOptions mülk. Görüntülerin SVG belgesine base64 olarak gömülmesinin gerekip gerekmediği belirtilir. Bu bayrağın ayarlanması çıktı SVG dosyasının boyutunu önemli ölçüde artırabilir.
type: docs
weight: 20
url: /tr/net/aspose.words.saving/svgsaveoptions/exportembeddedimages/
---
## SvgSaveOptions.ExportEmbeddedImages property

Görüntülerin SVG belgesine base64 olarak gömülmesinin gerekip gerekmediği belirtilir. Bu bayrağın ayarlanması, çıktı SVG dosyasının boyutunu önemli ölçüde artırabilir.

```csharp
public bool ExportEmbeddedImages { get; set; }
```

### Örnekler

Bir belgeyi .svg'ye dönüştürürken oluşturulan bağlantılı kaynakların URI'lerinin nasıl değiştirileceğini ve yazdırılacağını gösterir.

```csharp
public void SvgResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");

    SvgSaveOptions options = new SvgSaveOptions
    {
        SaveFormat = SaveFormat.Svg,
        ExportEmbeddedImages = false,
        ResourcesFolder = ArtifactsDir + "SvgResourceFolder",
        ResourcesFolderAlias = ArtifactsDir + "SvgResourceFolderAlias",
        ShowPageBorder = false,

        ResourceSavingCallback = new ResourceUriPrinter()
    };

    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "SvgSaveOptions.SvgResourceFolder.svg", options);
}

/// <summary>
/// .svg'ye dönüştürüldükçe içerdiği kaynakların URI'lerini sayar ve yazdırır.
/// </summary>
private class ResourceUriPrinter : IResourceSavingCallback
{
    void IResourceSavingCallback.ResourceSaving(ResourceSavingArgs args)
    {
        Console.WriteLine($"Resource #{++mSavedResourceCount} \"{args.ResourceFileName}\"");
        Console.WriteLine("\t" + args.ResourceFileUri);
    }

    private int mSavedResourceCount;
}
```

### Ayrıca bakınız

* class [SvgSaveOptions](../)
* ad alanı [Aspose.Words.Saving](../../svgsaveoptions/)
* toplantı [Aspose.Words](../../../)


