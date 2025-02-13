---
title: ThumbnailGeneratingOptions.GenerateFromFirstPage
second_title: Aspose.Words لمراجع .NET API
description: ThumbnailGeneratingOptions ملكية. يحدد ما إذا كان سيتم إنشاء مصغر من الصفحة الأولى من المستند أو الصورة الأولى.
type: docs
weight: 20
url: /ar/net/aspose.words.rendering/thumbnailgeneratingoptions/generatefromfirstpage/
---
## ThumbnailGeneratingOptions.GenerateFromFirstPage property

يحدد ما إذا كان سيتم إنشاء مصغر من الصفحة الأولى من المستند أو الصورة الأولى.

```csharp
public bool GenerateFromFirstPage { get; set; }
```

### ملاحظات

الافتراضي هو`حقيقي` ، مما يعني أنه سيتم إنشاء الصورة المصغرة من الصفحة الأولى من المستند . إذا كانت القيمة`خاطئة` ولا توجد صورة في المستند ، سيتم إنشاء الصورة المصغرة من الصفحة الأولى من المستند.

### أمثلة

يوضح كيفية تحديث الصورة المصغرة للمستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.InsertImage(ImageDir + "Logo.jpg");

// هناك طريقتان لتعيين صورة مصغرة عند حفظ مستند إلى .epub.
// 1 - استخدم الصفحة الأولى للمستند:
doc.UpdateThumbnail();
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstPage.epub");

// 2 - استخدم أول صورة موجودة في المستند:
ThumbnailGeneratingOptions options = new ThumbnailGeneratingOptions();
options.ThumbnailSize = new Size(400, 400);
options.GenerateFromFirstPage = false;

doc.UpdateThumbnail(options);
doc.Save(ArtifactsDir + "Document.UpdateThumbnail.FirstImage.epub");
```

### أنظر أيضا

* class [ThumbnailGeneratingOptions](../)
* مساحة الاسم [Aspose.Words.Rendering](../../thumbnailgeneratingoptions/)
* المجسم [Aspose.Words](../../../)


