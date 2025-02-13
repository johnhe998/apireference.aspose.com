---
title: Font.ClearFormatting
second_title: Aspose.Words لمراجع .NET API
description: Font طريقة. إعادة التعيين إلى تنسيق الخط الافتراضي.
type: docs
weight: 550
url: /ar/net/aspose.words/font/clearformatting/
---
## Font.ClearFormatting method

إعادة التعيين إلى تنسيق الخط الافتراضي.

```csharp
public void ClearFormatting()
```

### ملاحظات

يزيل كل تنسيقات الخط المحددة صراحةً على الكائن الذي منه  **الخط** لذا سيتم توريث تنسيق الخط من الأصل المناسب.

### أمثلة

يوضح كيفية إدراج حقل ارتباط تشعبي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("For more information, please visit the ");

// أدخل ارتباطًا تشعبيًا وقم بتأكيده بتنسيق مخصص.
// سيكون الارتباط التشعبي عبارة عن نص قابل للنقر عليه والذي سينقلنا إلى الموقع المحدد في عنوان URL.
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;
builder.InsertHyperlink("Google website", "https://www.google.com "، خطأ) ;
builder.Font.ClearFormatting();
builder.Writeln(".");

// Ctrl + النقر على الرابط الأيسر في النص في Microsoft Word سينقلنا إلى عنوان URL عبر نافذة متصفح ويب جديدة.
doc.Save(ArtifactsDir + "DocumentBuilder.InsertHyperlink.docx");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


