---
title: ResourceSavingArgs.ResourceFileUri
second_title: Aspose.Words لمراجع .NET API
description: ResourceSavingArgs ملكية. الحصول على أو تعيين معرف المورد الموحد URI المستخدم للإشارة إلى ملف المورد من المستند.
type: docs
weight: 40
url: /ar/net/aspose.words.saving/resourcesavingargs/resourcefileuri/
---
## ResourceSavingArgs.ResourceFileUri property

الحصول على أو تعيين معرف المورد الموحد (URI) المستخدم للإشارة إلى ملف المورد من المستند.

```csharp
public string ResourceFileUri { get; set; }
```

### ملاحظات

تتيح لك هذه الخاصية تغيير URIs لملفات الموارد التي تم تصديرها إلى مستندات HTML أو SVG للصفحة الثابتة.

ينشئ Aspose.Words تلقائيًا عنوان URI لكل ملف مورد أثناء التصدير إلى تنسيق HTML أو SVG للصفحة الثابتة. ملفات الموارد المرجعية التي تم إنشاؤها بواسطة Aspose.Words ملفات الموارد المرجعية التي تم إنشاؤها. ومع ذلك ، يمكن أن تكون URIs غير صحيحة إذا كان سيتم نقل ملفات الموارد إلى موقع آخر أو إذا تم حفظ ملفات الموارد في الدفق.

عند إطلاق الحدث ، تحتوي هذه الخاصية على URI الذي تم إنشاؤه بواسطة Aspose.Words . يمكنك تغيير قيمة هذه الخاصية لتوفير URI مخصص لملف المورد.

[`ResourcesFolder`](../../htmlfixedsaveoptions/resourcesfolder/)[`ResourcesFolder`](../../svgsaveoptions/resourcesfolder/)[`ResourcesFolderAlias`](../../htmlfixedsaveoptions/resourcesfolderalias/)[`ResourcesFolderAlias`](../../svgsaveoptions/resourcesfolderalias/)

### أمثلة

يوضح كيفية استخدام رد الاتصال لتتبع الموارد الخارجية التي تم إنشاؤها أثناء تحويل مستند إلى HTML.

```csharp
public void ResourceSavingCallback()
{
    Document doc = new Document(MyDir + "Bullet points with alternative font.docx");

    FontSavingCallback callback = new FontSavingCallback();

    HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
    {
        ResourceSavingCallback = callback
    };

    doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.UsingMachineFonts.html", saveOptions);

    Console.WriteLine(callback.GetText());
}

private class FontSavingCallback : IResourceSavingCallback
{
    /// <summary>
    /// يتم الاستدعاء عندما يحفظ Aspose.Words موردًا خارجيًا لصفحة ثابتة HTML أو SVG.
    /// </summary>
    public void ResourceSaving(ResourceSavingArgs args)
    {
        mText.AppendLine($"Original document URI:\t{args.Document.OriginalFileName}");
        mText.AppendLine($"Resource being saved:\t{args.ResourceFileName}");
        mText.AppendLine($"Full uri after saving:\t{args.ResourceFileUri}\n");
    }

    public string GetText()
    {
        return mText.ToString();
    }

    private readonly StringBuilder mText = new StringBuilder();
}
```

### أنظر أيضا

* class [ResourceSavingArgs](../)
* مساحة الاسم [Aspose.Words.Saving](../../resourcesavingargs/)
* المجسم [Aspose.Words](../../../)


