---
title: HtmlFixedSaveOptions.ExportEmbeddedFonts
second_title: Aspose.Words لمراجع .NET API
description: HtmlFixedSaveOptions ملكية. يحدد ما إذا كان يجب تضمين الخطوط في مستند Html بتنسيق Base64 . ملاحظة يمكن أن يؤدي إعداد هذه العلامة إلى زيادة حجم ملف Html الناتج بشكل ملحوظ.
type: docs
weight: 50
url: /ar/net/aspose.words.saving/htmlfixedsaveoptions/exportembeddedfonts/
---
## HtmlFixedSaveOptions.ExportEmbeddedFonts property

يحدد ما إذا كان يجب تضمين الخطوط في مستند Html بتنسيق Base64 . ملاحظة يمكن أن يؤدي إعداد هذه العلامة إلى زيادة حجم ملف Html الناتج بشكل ملحوظ.

```csharp
public bool ExportEmbeddedFonts { get; set; }
```

### أمثلة

يوضح كيفية تحديد مكان تخزين الخطوط المضمنة عند تصدير مستند إلى Html.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

// عندما نقوم بتصدير مستند يحتوي على خطوط مضمنة إلى .html ،
// Aspose.Words يمكن أن تضع الخطوط في موقعين محتملين.
// سيؤدي تعيين علامة "ExportEmbeddedFonts" على "true" إلى تخزين البيانات الأولية للخطوط المضمنة داخل ورقة أنماط CSS ،
// في خاصية "url" لقاعدة "@ font-face". قد يؤدي هذا إلى إنشاء ملف ورقة أنماط CSS ضخم
// وتقليل عدد الملفات الخارجية التي سينشئها تحويل HTML هذا.
// سيؤدي تعيين هذه العلامة إلى "خطأ" إلى إنشاء ملف لكل خط.
// سترتبط ورقة أنماط CSS بكل ملف خط باستخدام خاصية "url" لقاعدة "@ font-face".
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportEmbeddedFonts = exportEmbeddedFonts
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts/styles.css");

if (exportEmbeddedFonts)
{
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], url[(].+[)] format[(]'woff'[)]; }").Success);
    Assert.AreEqual(0, Directory.GetFiles(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts").Count(f => f.EndsWith(".woff")));
}
else
{
    Assert.True(Regex.Match(outDocContents,
        "@font-face { font-family:'Arial'; font-style:normal; font-weight:normal; src:local[(]'☺'[)], url[(]'font001[.]woff'[)] format[(]'woff'[)]; }").Success);
    Assert.AreEqual(2, Directory.GetFiles(ArtifactsDir + "HtmlFixedSaveOptions.ExportEmbeddedFonts").Count(f => f.EndsWith(".woff")));
}
```

### أنظر أيضا

* class [HtmlFixedSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* المجسم [Aspose.Words](../../../)


