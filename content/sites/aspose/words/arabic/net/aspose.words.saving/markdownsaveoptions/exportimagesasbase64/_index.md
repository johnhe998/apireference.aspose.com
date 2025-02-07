---
title: MarkdownSaveOptions.ExportImagesAsBase64
second_title: Aspose.Words لمراجع .NET API
description: MarkdownSaveOptions ملكية. يحدد ما إذا كانت الصور سيتم حفظها بتنسيق Base64 في ملف الإخراج. الإعداد الافتراضي هوخاطئة .
type: docs
weight: 20
url: /ar/net/aspose.words.saving/markdownsaveoptions/exportimagesasbase64/
---
## MarkdownSaveOptions.ExportImagesAsBase64 property

يحدد ما إذا كانت الصور سيتم حفظها بتنسيق Base64 في ملف الإخراج. الإعداد الافتراضي هو`خاطئة` .

```csharp
public bool ExportImagesAsBase64 { get; set; }
```

### ملاحظات

عندما يتم تعيين هذه الخاصية على`حقيقي`يتم تصدير بيانات الصور مباشرة إلى ملف **IMG** لم يتم إنشاء عناصر وملفات منفصلة.

### أمثلة

يوضح كيفية حفظ مستند .md مع الصور المضمنة بداخله.

```csharp
Document doc = new Document(MyDir + "Images.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ExportImagesAsBase64 = exportImagesAsBase64 };

doc.Save(ArtifactsDir + "MarkdownSaveOptions.ExportImagesAsBase64.md", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "MarkdownSaveOptions.ExportImagesAsBase64.md");

Assert.True(exportImagesAsBase64
    ? outDocContents.Contains("data:image/jpeg;base64")
    : outDocContents.Contains("MarkdownSaveOptions.ExportImagesAsBase64.001.jpeg"));
```

### أنظر أيضا

* class [MarkdownSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../markdownsaveoptions/)
* المجسم [Aspose.Words](../../../)


