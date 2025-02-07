---
title: XamlFlowSaveOptions.ImagesFolder
second_title: Aspose.Words لمراجع .NET API
description: XamlFlowSaveOptions ملكية. يحدد المجلد الفعلي حيث يتم حفظ الصور عند تصدير مستند إلى تنسيق XAML. الافتراضي هو عبارة عن سلسلة فارغة.
type: docs
weight: 30
url: /ar/net/aspose.words.saving/xamlflowsaveoptions/imagesfolder/
---
## XamlFlowSaveOptions.ImagesFolder property

يحدد المجلد الفعلي حيث يتم حفظ الصور عند تصدير مستند إلى تنسيق XAML. الافتراضي هو عبارة عن سلسلة فارغة.

```csharp
public string ImagesFolder { get; set; }
```

### ملاحظات

عندما تقوم بحفظ ملف[`Document`](../../../aspose.words/document/) بتنسيق XAML ، يحتاج Aspose.Words إلى حفظ جميع الصور المضمنة في المستند كملفات قائمة بذاتها.`ImagesFolder` يسمح لك بتحديد مكان حفظ الصور و[`ImagesFolderAlias`](../imagesfolderalias/) يسمح بتحديد كيفية إنشاء عناوين URI للصورة.

إذا قمت بحفظ مستند في ملف وقمت بتوفير اسم ملف ، Aspose.Words ، بشكل افتراضي ، يحفظ الصور في نفس المجلد حيث يتم حفظ ملف المستند. يستخدم`ImagesFolder` لتجاوز هذا السلوك.

إذا قمت بحفظ مستند في دفق ، فإن Aspose.Words ليس بها مجلد لحفظ الصور ، ولكن لا يزال بحاجة إلى حفظ الصور في مكان ما. في هذه الحالة ، تحتاج إلى تحديد مجلد يمكن الوصول إليه في ملف`ImagesFolder` الخاصية أو توفير تدفقات مخصصة عبر [`ImageSavingCallback`](../imagesavingcallback/) معالج الحدث.

### أمثلة

يوضح كيفية طباعة أسماء ملفات الصور المرتبطة التي تم إنشاؤها أثناء تحويل مستند إلى تنسيق .xaml.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    ImageUriPrinter callback = new ImageUriPrinter(ArtifactsDir + "XamlFlowImageFolderAlias");

    // قم بإنشاء كائن "XamlFlowSaveOptions" ، والذي يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
    // لتعديل كيفية حفظ المستند بتنسيق حفظ XAML.
    XamlFlowSaveOptions options = new XamlFlowSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFlow, options.SaveFormat);

    // استخدم خاصية "ImagesFolder" لتعيين مجلد في نظام الملفات المحلي فيه
    // Aspose.Words ستحفظ جميع الصور المرتبطة بالمستند.
    options.ImagesFolder = ArtifactsDir + "XamlFlowImageFolder";

    // استخدم خاصية "ImagesFolderAlias" لاستخدام هذا المجلد
    // عند إنشاء عناوين URI للصور بدلاً من اسم مجلد الصور.
    options.ImagesFolderAlias = ArtifactsDir + "XamlFlowImageFolderAlias";

    options.ImageSavingCallback = callback;

    // سيحتاج المجلد المحدد بواسطة "ImagesFolderAlias" إلى احتواء الموارد بدلاً من "ImagesFolder".
    // يجب أن نتأكد من وجود المجلد قبل أن تتمكن تدفقات رد الاتصال من وضع مواردها فيه.
    Directory.CreateDirectory(options.ImagesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFlowSaveOptions.ImageFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine($"{callback.ImagesFolderAlias}/{resource}");

/// <summary>
/// يعد ويطبع أسماء ملفات الصور أثناء تحويل المستند الأصلي إلى نموذج تدفق .xaml.
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

        // إذا حددنا اسمًا مستعارًا لمجلد الصور ، فسنحتاج أيضًا إلى
        // لإعادة توجيه كل دفق لوضع صورته في مجلد الاسم المستعار.
        args.ImageStream = new FileStream($"{ImagesFolderAlias}/{args.ImageFileName}", FileMode.Create);
        args.KeepImageStreamOpen = false;
    }

    public string ImagesFolderAlias { get; }
    public List<string> Resources { get; }
}
```

### أنظر أيضا

* class [XamlFlowSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../xamlflowsaveoptions/)
* المجسم [Aspose.Words](../../../)


