---
title: PdfSaveOptions.PdfSaveOptions
second_title: Aspose.Words لمراجع .NET API
description: PdfSaveOptions البناء. تهيئة مثيل جديد من هذه الفئة يمكن استخدامه لحفظ مستند في Pdf التنسيق .
type: docs
weight: 10
url: /ar/net/aspose.words.saving/pdfsaveoptions/pdfsaveoptions/
---
## PdfSaveOptions constructor

تهيئة مثيل جديد من هذه الفئة يمكن استخدامه لحفظ مستند في Pdf التنسيق .

```csharp
public PdfSaveOptions()
```

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


