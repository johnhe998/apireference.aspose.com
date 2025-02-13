---
title: PdfSaveOptions.EmbedFullFonts
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions ملكية. يتحكم في كيفية دمج الخطوط في مستندات PDF الناتجة.
type: docs
weight: 100
url: /ar/net/aspose.words.saving/pdfsaveoptions/embedfullfonts/
---
## PdfSaveOptions.EmbedFullFonts property

يتحكم في كيفية دمج الخطوط في مستندات PDF الناتجة.

```csharp
public bool EmbedFullFonts { get; set; }
```

### ملاحظات

النظام الأساسي`خاطئة`، مما يعني أن الخطوط قد تم دمجها قبل التضمين. يزيل Subsetting all الحروف الرسومية غير المستخدمة من الخط.

عندما يتم تعيين هذه القيمة على`حقيقي`، يتم تضمين ملف خط كامل في PDF بدون تقسيم . سينتج عن ذلك ملفات إخراج أكبر ، ولكن يمكن أن يكون خيارًا مفيدًا عندما تريد تحرير ملف PDF الناتج لاحقًا (على سبيل المثال ، إضافة المزيد من النص).

بعض الخطوط كبيرة (عدة ميغا بايت) ودمجها دون subetting سينتج عنه مستندات إخراج كبيرة.

### أمثلة

يوضح كيفية تمكين أو تعطيل الضبط الجزئي عند دمج الخطوط أثناء تقديم مستند إلى PDF.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "Arial";
builder.Writeln("Hello world!");
builder.Font.Name = "Arvo";
builder.Writeln("The quick brown fox jumps over the lazy dog.");

// تكوين مصادر الخطوط لدينا لضمان وصولنا إلى كل من الخطوط في هذا المستند.
FontSourceBase[] originalFontsSources = FontSettings.DefaultInstance.GetFontsSources();
Aspose.Words.Fonts.FolderFontSource folderFontSource = new Aspose.Words.Fonts.FolderFontSource(FontsDir, true);
FontSettings.DefaultInstance.SetFontsSources(new[] { originalFontsSources[0], folderFontSource });

FontSourceBase[] fontSources = FontSettings.DefaultInstance.GetFontsSources();
Assert.True(fontSources[0].GetAvailableFonts().Any(f => f.FullFontName == "Arial"));
Assert.True(fontSources[1].GetAvailableFonts().Any(f => f.FullFontName == "Arvo"));

// قم بإنشاء كائن "PdfSaveOptions" يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية تحويل هذه الطريقة المستند إلى PDF.
PdfSaveOptions options = new PdfSaveOptions();

// نظرًا لأن وثيقتنا تحتوي على خط مخصص ، فقد يكون التضمين في مستند الإخراج أمرًا مرغوبًا فيه.
// اضبط خاصية "EmbedFullFonts" على "true" لتضمين كل حرف رسومي لكل خط مضمن في ملف PDF الناتج.
// قد يصبح حجم المستند كبيرًا جدًا ، لكننا سنستخدم جميع الخطوط بشكل كامل إذا قمنا بتحرير ملف PDF.
// عيّن خاصية "EmbedFullFonts" على "خطأ" لتطبيق التقسيم على الخطوط ، مع حفظ الصور الرمزية فقط
// الذي يستخدمه المستند. سيكون الملف أصغر بكثير ،
// ولكن قد نحتاج إلى الوصول إلى أي خطوط مخصصة إذا قمنا بتحرير المستند.
options.EmbedFullFonts = embedFullFonts;

doc.Save(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf", options);

if (embedFullFonts)
    Assert.That(500000, Is.LessThan(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));
else
    Assert.That(25000, Is.AtLeast(new FileInfo(ArtifactsDir + "PdfSaveOptions.EmbedFullFonts.pdf").Length));

// استعادة مصادر الخط الأصلية.
FontSettings.DefaultInstance.SetFontsSources(originalFontsSources);
```

### أنظر أيضا

* class [PdfSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../pdfsaveoptions/)
* المجسم [Aspose.Words](../../../)


