---
title: FontSavingArgs.FontFileName
second_title: Aspose.Words لمراجع .NET API
description: FontSavingArgs ملكية. الحصول على أو تحديد اسم الملف بدون مسار حيث سيتم حفظ الخط فيه.
type: docs
weight: 40
url: /ar/net/aspose.words.saving/fontsavingargs/fontfilename/
---
## FontSavingArgs.FontFileName property

الحصول على أو تحديد اسم الملف (بدون مسار) حيث سيتم حفظ الخط فيه.

```csharp
public string FontFileName { get; set; }
```

### ملاحظات

تتيح لك هذه الخاصية إعادة تعريف كيفية إنشاء أسماء ملفات الخطوط أثناء التصدير إلى HTML.

عند إطلاق الحدث ، تحتوي هذه الخاصية على اسم الملف الذي تم إنشاؤه بواسطة Aspose.Words . يمكنك تغيير قيمة هذه الخاصية لحفظ الخط في ملف مختلف . لاحظ أن أسماء الملفات يجب أن تكون فريدة.

يقوم Aspose.Words تلقائيًا بإنشاء اسم ملف فريد لكل خط مضمن عند تصدير إلى تنسيق HTML. تعتمد كيفية إنشاء اسم ملف الخط على ما إذا كنت ستحفظ المستند إلى ملف أو إلى دفق.

عند حفظ مستند إلى ملف ، يبدو اسم ملف الخط الذي تم إنشاؤه مثل &lt;اسم الملف الأساسي للمستند&gt;. &lt;اسم الملف الأصلي&gt; &lt;لاحقة اختيارية&gt;. &lt;امتداد&gt;.

عند حفظ مستند إلى دفق ، يبدو اسم ملف الخط الذي تم إنشاؤه مثل Aspose.Words. &lt;document GU&gt;. &lt;original file name&gt; &lt;Optional Optional&gt;. &lt;extension&gt;.

`FontFileName` يجب أن يحتوي على اسم الملف فقط بدون المسار. Aspose. تحدد الكلمات مسار الحفظ باستخدام اسم ملف المستند ، the[`FontsFolder`](../../htmlsaveoptions/fontsfolder/) و [`FontsFolderAlias`](../../htmlsaveoptions/fontsfolderalias/) الخصائص.

### أمثلة

يوضح كيفية تحديد منطق مخصص لتصدير الخطوط عند الحفظ بتنسيق HTML.

```csharp
{
    Document doc = new Document(MyDir + "Rendering.docx");

    // تكوين كائن SaveOptions لتصدير الخطوط إلى ملفات منفصلة.
    // تعيين رد اتصال يعالج حفظ الخط بطريقة مخصصة.
    HtmlSaveOptions options = new HtmlSaveOptions
    {
        ExportFontResources = true,
        FontSavingCallback = new HandleFontSaving()
    };

    // ستصدر رد النداء ملفات .ttf وحفظها بجانب المستند الناتج.
    doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveExportedFonts.html", options);

    foreach (string fontFilename in Array.FindAll(Directory.GetFiles(ArtifactsDir), s => s.EndsWith(".ttf")))
    {
        Console.WriteLine(fontFilename);
    }

/// <summary>
/// يطبع معلومات حول الخطوط المصدرة ويحفظها في نفس مجلد النظام المحلي مثل إخراجها .html.
/// </summary>
public class HandleFontSaving : IFontSavingCallback
{
    void IFontSavingCallback.FontSaving(FontSavingArgs args)
    {
        Console.Write($"Font:\t{args.FontFamilyName}");
        if (args.Bold) Console.Write(", bold");
        if (args.Italic) Console.Write(", italic");
        Console.WriteLine($"\nSource:\t{args.OriginalFileName}, {args.OriginalFileSize} bytes\n");

        // يمكننا أيضًا الوصول إلى المستند المصدر من هنا.
        Assert.True(args.Document.OriginalFileName.EndsWith("Rendering.docx"));

        Assert.True(args.IsExportNeeded);
        Assert.True(args.IsSubsettingNeeded);

        // هناك طريقتان لحفظ الخط الذي تم تصديره.
        // 1 - احفظه في موقع نظام ملفات محلي:
        args.FontFileName = args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last();

        // 2 - احفظه في دفق:
        args.FontStream =
            new FileStream(ArtifactsDir + args.OriginalFileName.Split(Path.DirectorySeparatorChar).Last(), FileMode.Create);
        Assert.False(args.KeepFontStreamOpen);
    }
}
```

### أنظر أيضا

* class [FontSavingArgs](../)
* مساحة الاسم [Aspose.Words.Saving](../../fontsavingargs/)
* المجسم [Aspose.Words](../../../)


