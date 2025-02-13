---
title: PdfSaveOptions.UseCoreFonts
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. الحصول على قيمة أو تعيينها لتحديد ما إذا كان سيتم استبدال خطوط TrueType Arial و Times New Roman و Courier New و Symbol بخطوط PDF Type 1 الأساسية.
type: docs
weight: 280
url: /ar/net/aspose.words.saving/pdfsaveoptions/usecorefonts/
---
## PdfSaveOptions.UseCoreFonts property

الحصول على قيمة أو تعيينها لتحديد ما إذا كان سيتم استبدال خطوط TrueType Arial و Times New Roman و Courier New و Symbol بخطوط PDF Type 1 الأساسية.

```csharp
public bool UseCoreFonts { get; set; }
```

### ملاحظات

النظام الأساسي`خاطئة` . عندما يتم تعيين هذه القيمة على`حقيقي` تم استبدال خطوط Arial و Times New Roman و Courier New و Symbol في مستند PDF بخط Core Type 1 المقابل.

يجب أن تكون خطوط PDF الأساسية ، أو مقاييس الخط الخاصة بها وخطوط الاستبدال المناسبة ، متاحة لأي تطبيق عارض PDF.

يعمل هذا الإعداد فقط مع النص في ترميز ANSI (Windows-1252). سيتم كتابة النص غير ANSI بخط تروتايب مضمن بغض النظر عن هذا الإعداد.

يتطلب التوافق مع PDF / A و PDF / UA دمج كل الخطوط.`خاطئة` سيتم استخدام القيمة تلقائيًا عند الحفظ في PDF / A و PDF / UA.

لا يتم دعم الخطوط الأساسية عند الحفظ بتنسيق PDF 2.0.`خاطئة`سيتم استخدام القيمة تلقائيًا عند الحفظ إلى PDF 2.0.

هذا الخيار له أولوية أعلى إذن[`FontEmbeddingMode`](../fontembeddingmode/) اختيار.

### أمثلة

يوضح كيفية تمكين / تعطيل استبدال خط PDF Type 1.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Courier New";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// اضبط خاصية "UseCoreFonts" على "true" لاستبدال بعض الخطوط ،
// بما في ذلك الخطين في وثيقتنا ، مع ما يعادلهما من PDF Type 1.
// اضبط خاصية "UseCoreFonts" على "false" لعدم تطبيق خطوط PDF Type 1.
options.UseCoreFonts = useCoreFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf", options);

if (useCoreFonts)
    Assert.That(3000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
else
    Assert.That(30000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedCoreFonts.pdf").Length));
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


