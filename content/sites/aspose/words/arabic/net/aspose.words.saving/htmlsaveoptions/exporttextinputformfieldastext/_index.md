---
title: HtmlSaveOptions.ExportTextInputFormFieldAsText
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يتحكم في كيفية حفظ حقول نموذج إدخال النص في HTML أو MHTML. القيمة الافتراضية هيخاطئة .
type: docs
weight: 270
url: /ar/net/aspose.words.saving/htmlsaveoptions/exporttextinputformfieldastext/
---
## HtmlSaveOptions.ExportTextInputFormFieldAsText property

يتحكم في كيفية حفظ حقول نموذج إدخال النص في HTML أو MHTML. القيمة الافتراضية هي`خاطئة` .

```csharp
public bool ExportTextInputFormFieldAsText { get; set; }
```

### ملاحظات

عند الضبط على`حقيقي` ، تصدير حقول نموذج إدخال النص كنص عادي. متى`خاطئة`، يقوم بتصدير حقول نموذج إدخال نص Word كعناصر INPUT في HTML.

عند التصدير إلى EPUB ، يتم دائمًا حفظ حقول نموذج إدخال النص كنص بسبب لمتطلبات هذا التنسيق.

### أمثلة

يوضح كيفية تحديد مجلد لتخزين الصور المرتبطة بعد الحفظ في .html.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

string imagesDir = Path.Combine(ArtifactsDir, "SaveHtmlWithOptions");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

// تعيين خيار لتصدير حقول النموذج كنص عادي بدلاً من عناصر إدخال HTML.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true, 
    ImagesFolder = imagesDir
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.SaveHtmlWithOptions.html", options);
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


