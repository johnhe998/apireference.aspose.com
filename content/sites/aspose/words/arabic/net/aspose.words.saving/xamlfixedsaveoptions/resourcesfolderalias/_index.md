---
title: XamlFixedSaveOptions.ResourcesFolderAlias
second_title: Aspose.Words لمراجع .NET API
description: XamlFixedSaveOptions ملكية. يحدد اسم المجلد المستخدم في إنشاء عناوين URI للصورة مكتوبة في مستند Xaml بصفحة ثابتة. الافتراضي هولا شيء .
type: docs
weight: 40
url: /ar/net/aspose.words.saving/xamlfixedsaveoptions/resourcesfolderalias/
---
## XamlFixedSaveOptions.ResourcesFolderAlias property

يحدد اسم المجلد المستخدم في إنشاء عناوين URI للصورة مكتوبة في مستند Xaml بصفحة ثابتة. الافتراضي هو`لا شيء` .

```csharp
public string ResourcesFolderAlias { get; set; }
```

### ملاحظات

عندما تقوم بحفظ ملف[`Document`](../../../aspose.words/document/) بتنسيق Xaml بصفحة ثابتة ، يحتاج Aspose.Words إلى حفظ جميع صور المضمنة في المستند كملفات مستقلة.[`ResourcesFolder`](../resourcesfolder/) يسمح لك بتحديد مكان حفظ الصور و`ResourcesFolderAlias` يسمح بتحديد كيفية إنشاء عناوين URI للصورة.

### أمثلة

يوضح كيفية طباعة URIs للموارد المرتبطة التي تم إنشاؤها أثناء تحويل مستند إلى نموذج ثابت .xaml.

```csharp
public void ResourceFolder()
{
    Document doc = new Document(MyDir + "Rendering.docx");
    ResourceUriPrinter callback = new ResourceUriPrinter();

    // قم بإنشاء كائن "XamlFixedSaveOptions" ، والذي يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
    // لتعديل كيفية حفظ المستند بتنسيق حفظ XAML.
    XamlFixedSaveOptions options = new XamlFixedSaveOptions();

    Assert.AreEqual(SaveFormat.XamlFixed, options.SaveFormat);

    // استخدم خاصية "ResourcesFolder" لتعيين مجلد في نظام الملفات المحلي فيه
    // Aspose.Words ستحفظ جميع الموارد المرتبطة بالمستند ، مثل الصور والخطوط.
    options.ResourcesFolder = ArtifactsDir + "XamlFixedResourceFolder";

    // استخدم خاصية "ResourcesFolderAlias" لاستخدام هذا المجلد
    // عند إنشاء عناوين URI للصورة بدلاً من اسم مجلد الموارد.
    options.ResourcesFolderAlias = ArtifactsDir + "XamlFixedFolderAlias";

    options.ResourceSavingCallback = callback;

    // سيحتاج المجلد المحدد بواسطة "ResourcesFolderAlias" إلى احتواء الموارد بدلاً من "ResourcesFolder".
    // يجب أن نتأكد من وجود المجلد قبل أن تتمكن تدفقات رد الاتصال من وضع مواردها فيه.
    Directory.CreateDirectory(options.ResourcesFolderAlias);

    doc.Save(ArtifactsDir + "XamlFixedSaveOptions.ResourceFolder.xaml", options);

    foreach (string resource in callback.Resources)
        Console.WriteLine(resource);
}

/// <summary>
/// يحسب ويطبع URIs للموارد التي تم إنشاؤها أثناء التحويل إلى .xaml ثابت.
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

        // إذا حددنا اسمًا مستعارًا لمجلد الموارد ، فسنحتاج أيضًا
        // لإعادة توجيه كل دفق لوضع مورده في مجلد الاسم المستعار.
        args.ResourceStream = new FileStream(args.ResourceFileUri, FileMode.Create);
        args.KeepResourceStreamOpen = false;
    }

    public List<string> Resources { get; }
}
```

### أنظر أيضا

* class [XamlFixedSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../xamlfixedsaveoptions/)
* المجسم [Aspose.Words](../../../)


