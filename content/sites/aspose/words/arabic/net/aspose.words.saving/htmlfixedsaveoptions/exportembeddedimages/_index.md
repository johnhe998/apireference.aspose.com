---
title: HtmlFixedSaveOptions.ExportEmbeddedImages
second_title: Aspose.Words لمراجع .NET API
description: HtmlFixedSaveOptions ملكية. يحدد ما إذا كان يجب تضمين الصور في مستند Html بتنسيق Base64 . ملاحظة يمكن أن يؤدي إعداد هذه العلامة إلى زيادة حجم ملف Html الناتج بشكل كبير.
type: docs
weight: 60
url: /ar/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedimages/
---
## HtmlFixedSaveOptions.ExportEmbeddedImages property

يحدد ما إذا كان يجب تضمين الصور في مستند Html بتنسيق Base64 . ملاحظة يمكن أن يؤدي إعداد هذه العلامة إلى زيادة حجم ملف Html الناتج بشكل كبير.

```csharp
public bool ExportEmbeddedImages { get; set; }
```

### أمثلة

يوضح كيفية تحديد مكان تخزين الصور عند تصدير مستند إلى Html.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// عندما نقوم بتصدير مستند يحتوي على صور مضمنة إلى .html ،
// Aspose.Words يمكن أن تضع الصور في موقعين محتملين.
// سيؤدي تعيين علامة "ExportEmbeddedImages" على "true" إلى تخزين البيانات الأولية
// لجميع الصور داخل مستند HTML الناتج ، في السمة "src" في < image > العلامات.
// سيؤدي تعيين هذه العلامة إلى "خطأ" إلى إنشاء ملف صورة في نظام الملفات المحلي لكل صورة ،
// وتخزين كل هذه الملفات في مجلد منفصل.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedImages = exportImages
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedImages.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedImages.html");

if (exportImages)
{
    Assert.False(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedImages/image001.jpeg"));
    Assert.True(Regex.Match(outDocContents,
        "<img class=\"awimg\" style=\"left:0pt; top:0pt; width:493.1pt; height:300.55pt;\" src=\".+\" />").Success);
}
else
{
    Assert.True(File.Exists(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedImages/image001.jpeg"));
    Assert.True(Regex.Match(outDocContents,
        "<img class=\"awimg\" style=\"left:0pt; top:0pt; width:493.1pt; height:300.55pt;\" " +
        "src=\"HtmlFixedSaveOptions[.]ExportEmbeddedImages/image001[.]jpeg\" />").Success);
}
```

### أنظر أيضا

* class [HtmlFixedSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* المجسم [Aspose.Words](../../../)


