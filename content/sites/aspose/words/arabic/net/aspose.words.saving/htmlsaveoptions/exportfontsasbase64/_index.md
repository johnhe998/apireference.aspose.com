---
title: HtmlSaveOptions.ExportFontsAsBase64
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد ما إذا كان يجب تضمين موارد الخطوط في HTML في ترميز Base64 . الافتراضي هوخاطئة .
type: docs
weight: 160
url: /ar/net/aspose.words.saving/htmlsaveoptions/exportfontsasbase64/
---
## HtmlSaveOptions.ExportFontsAsBase64 property

يحدد ما إذا كان يجب تضمين موارد الخطوط في HTML في ترميز Base64 . الافتراضي هو`خاطئة` .

```csharp
public bool ExportFontsAsBase64 { get; set; }
```

### ملاحظات

بشكل افتراضي ، تتم كتابة الخطوط لفصل الملفات. إذا تم تعيين هذا الخيار على`حقيقي`، سيتم تضمين الخطوط في CSS للمستند بترميز Base64.

### أمثلة

يوضح كيفية تضمين الخطوط داخل مستند HTML محفوظ.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportFontsAsBase64 = true,
    CssStyleSheetType = CssStyleSheetType.Embedded,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportFontsAsBase64.html", options);
```

يوضح كيفية حفظ مستند بتنسيق .html مع صور مضمنة بداخله.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
    ExportImagesAsBase64 = exportImagesAsBase64,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportImagesAsBase64.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportImagesAsBase64.html");

Assert.True(exportImagesAsBase64
    ? outDocContents.Contains("<img src=\"data:image/png;base64")
    : outDocContents.Contains("<img src=\"HtmlSaveOptions.ExportImagesAsBase64.001.png\""));
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


