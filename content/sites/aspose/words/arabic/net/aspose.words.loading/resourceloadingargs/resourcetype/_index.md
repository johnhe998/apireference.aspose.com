---
title: ResourceLoadingArgs.ResourceType
second_title: Aspose.Words لمراجع .NET API
description: ResourceLoadingArgs ملكية. نوع المورد .
type: docs
weight: 20
url: /ar/net/aspose.words.loading/resourceloadingargs/resourcetype/
---
## ResourceLoadingArgs.ResourceType property

نوع المورد .

```csharp
public ResourceType ResourceType { get; }
```

### أمثلة

يوضح كيفية تخصيص عملية تحميل الموارد الخارجية في مستند.

```csharp
{
    Document doc = new Document();
    doc.ResourceLoadingCallback = new ImageNameHandler();

    DocumentBuilder builder = new DocumentBuilder(doc);

    // عادةً ما يتم إدراج الصور باستخدام URI أو مصفوفة بايت.
    // كل مثيل لتحميل المورد سوف يستدعي طريقة ResourceLoading لرد الاتصال.
    builder.InsertImage("Google logo");
    builder.InsertImage("Aspose logo");
    builder.InsertImage("Watermark");

    Assert.AreEqual(3, doc.GetChildNodes(NodeType.Shape, true).Count);

    doc.Save(ArtifactsDir + "DocumentBase.ResourceLoadingCallback.docx");

/// <summary>
/// يسمح لنا بتحميل الصور في مستند باستخدام اختصارات محددة مسبقًا ، بدلاً من URIs.
/// سيؤدي هذا إلى فصل منطق تحميل الصورة عن باقي إنشاء المستند.
/// </summary>
private class ImageNameHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(ResourceLoadingArgs args)
    {
        // إذا واجهت رد النداء هذا أحد اختصارات الصور أثناء تحميل الصورة ،
        // سيطبق منطقًا فريدًا لكل اختصار محدد بدلاً من معاملته على أنه URI.
        if (args.ResourceType == ResourceType.Image)
            switch (args.OriginalUri)
            {
                case "Google logo":
                    using (WebClient webClient = new WebClient())
                    {
                        args.SetData(webClient.DownloadData("http://www.google.com/images/logos/ps_logo2.png ")) ;
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

### أنظر أيضا

* enum [ResourceType](../../resourcetype/)
* class [ResourceLoadingArgs](../)
* مساحة الاسم [Aspose.Words.Loading](../../resourceloadingargs/)
* المجسم [Aspose.Words](../../../)


