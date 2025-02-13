---
title: SaveOptions.UseHighQualityRendering
second_title: Aspose.Words لمراجع .NET API
description: SaveOptions ملكية. الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم استخدام خوارزميات عرض عالية الجودة أي بطيئة أم لا.
type: docs
weight: 220
url: /ar/net/aspose.words.saving/saveoptions/usehighqualityrendering/
---
## SaveOptions.UseHighQualityRendering property

الحصول على أو تعيين قيمة تحدد ما إذا كان سيتم استخدام خوارزميات عرض عالية الجودة (أي بطيئة) أم لا.

```csharp
public bool UseHighQualityRendering { get; set; }
```

### ملاحظات

القيمة الافتراضية هي`خاطئة` .

تُستخدم هذه الخاصية عند تصدير المستند إلى تنسيقات الصور: Tiff وPng وBmp ، Jpeg وEmf.

### أمثلة

يوضح كيفية تحسين جودة المستند الذي تم تقديمه باستخدام SaveOptions.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Size = 60;
builder.Writeln("Some text.");

SaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.Default.jpg", options);

options.UseAntiAliasing = true;
options.UseHighQualityRendering = true;

doc.Save(ArtifactsDir + "Document.ImageSaveOptions.HighQuality.jpg", options);
```

### أنظر أيضا

* class [SaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../saveoptions/)
* المجسم [Aspose.Words](../../../)


