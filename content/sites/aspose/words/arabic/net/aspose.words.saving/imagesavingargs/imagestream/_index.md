---
title: ImageSavingArgs.ImageStream
second_title: Aspose.Words لمراجع .NET API
description: ImageSavingArgs ملكية. يسمح بتحديد التدفق حيث سيتم حفظ الصورة فيه.
type: docs
weight: 40
url: /ar/net/aspose.words.saving/imagesavingargs/imagestream/
---
## ImageSavingArgs.ImageStream property

يسمح بتحديد التدفق حيث سيتم حفظ الصورة فيه.

```csharp
public Stream ImageStream { get; set; }
```

### ملاحظات

تتيح لك هذه الخاصية حفظ الصور في التدفقات بدلاً من الملفات أثناء HTML.

النظام الأساسي`لا شيء` . عندما تكون هذه الخاصية`لا شيء` ، سيتم حفظ الصورة في ملف محدد في[`ImageFileName`](../imagefilename/) منشأه.

استخدام[`IImageSavingCallback`](../../iimagesavingcallback/) لا يمكنك استبدال صورة واحدة بـ بأخرى. الغرض منه هو فقط التحكم في الموقع حيث يتم حفظ الصور.

### أمثلة

يوضح كيفية إشراك رد اتصال حفظ الصورة في عملية تحويل HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // عندما نحفظ المستند إلى HTML ، يمكننا تمرير كائن SaveOptions لتعيين رد اتصال
    // لتخصيص عملية حفظ الصورة.
    HtmlSaveOptions options = new HtmlSaveOptions();
    options.ImageSavingCallback = new ImageShapePrinter();

    doc.Save(ArtifactsDir + "HtmlSaveOptions.ImageSavingCallback.html", options);
}

/// <summary>
/// يطبع خصائص كل صورة حيث أن عملية الحفظ تحفظها في ملف صورة في نظام الملفات المحلي
/// أثناء تصدير مستند إلى HTML.
/// </summary>
private class ImageShapePrinter : IImageSavingCallback
{
    void IImageSavingCallback.ImageSaving(ImageSavingArgs args)
    {
        args.KeepImageStreamOpen = false;
        Assert.True(args.IsImageAvailable);

        Console.WriteLine($"{args.Document.OriginalFileName.Split('\\').Last()} Image #{++mImageCount}");

        LayoutCollector layoutCollector = new LayoutCollector(args.Document);

        Console.WriteLine($"\tOn page:\t{layoutCollector.GetStartPageIndex(args.CurrentShape)}");
        Console.WriteLine($"\tDimensions:\t{args.CurrentShape.Bounds}");
        Console.WriteLine($"\tAlignment:\t{args.CurrentShape.VerticalAlignment}");
        Console.WriteLine($"\tWrap type:\t{args.CurrentShape.WrapType}");
        Console.WriteLine($"Output filename:\t{args.ImageFileName}\n");
    }

    private int mImageCount;
}
```

### أنظر أيضا

* class [ImageSavingArgs](../)
* مساحة الاسم [Aspose.Words.Saving](../../imagesavingargs/)
* المجسم [Aspose.Words](../../../)


