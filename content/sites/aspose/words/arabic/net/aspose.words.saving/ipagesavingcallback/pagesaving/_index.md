---
title: IPageSavingCallback.PageSaving
second_title: Aspose.Words لمراجع .NET API
description: IPageSavingCallback طريقة. يتم الاستدعاء عند قيام Aspose.Words بحفظ صفحة منفصلة بتنسيقات صفحات ثابتة.
type: docs
weight: 10
url: /ar/net/aspose.words.saving/ipagesavingcallback/pagesaving/
---
## IPageSavingCallback.PageSaving method

يتم الاستدعاء عند قيام Aspose.Words بحفظ صفحة منفصلة بتنسيقات صفحات ثابتة.

```csharp
public void PageSaving(PageSavingArgs args)
```

### أمثلة

يوضح كيفية استخدام رد نداء لحفظ مستند إلى صفحة HTML بصفحة.

```csharp
public void PageFileNames()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("Page 1.");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 2.");
    builder.InsertImage(ImageDir + "Logo.jpg");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 3.");

    // قم بإنشاء كائن "HtmlFixedSaveOptions" ، والذي يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
    // لتعديل كيفية تحويل المستند إلى HTML.
    HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions();

    // سنحفظ كل صفحة في هذا المستند في ملف HTML منفصل في نظام الملفات المحلي.
    // تعيين رد اتصال يسمح لنا بتسمية كل مستند HTML ناتج.
    htmlFixedSaveOptions.PageSavingCallback = new CustomFileNamePageSavingCallback();

    doc.Save(ArtifactsDir + "SavingCallback.PageFileNames.html", htmlFixedSaveOptions);

    string[] filePaths = Directory.GetFiles(ArtifactsDir).Where(
        s => s.StartsWith(ArtifactsDir + "SavingCallback.PageFileNames.Page_")).OrderBy(s => s).ToArray();

    Assert.AreEqual(3, filePaths.Length);
}

/// <summary>
/// يحفظ كل الصفحات في ملف ودليل محدد بداخله.
/// </summary>
private class CustomFileNamePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        string outFileName = $"{ArtifactsDir}SavingCallback.PageFileNames.Page_{args.PageIndex}.html";

        // فيما يلي طريقتان لتحديد مكان حفظ Aspose.Words كل صفحة من المستند.
        // 1 - حدد اسم ملف لملف صفحة الإخراج:
        args.PageFileName = outFileName;

        // 2 - إنشاء دفق مخصص لملف صفحة الإخراج:
        args.PageStream = new FileStream(outFileName, FileMode.Create);

        Assert.False(args.KeepPageStreamOpen);
    }
}
```

### أنظر أيضا

* class [PageSavingArgs](../../pagesavingargs/)
* interface [IPageSavingCallback](../)
* مساحة الاسم [Aspose.Words.Saving](../../ipagesavingcallback/)
* المجسم [Aspose.Words](../../../)


