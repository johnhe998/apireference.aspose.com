---
title: HtmlFixedSaveOptions.ExportFormFields
second_title: Aspose.Words لمراجع .NET API
description: HtmlFixedSaveOptions ملكية. الحصول على أو تعيين إشارة إلى ما إذا كان يتم تصدير حقول النموذج كعناصر تفاعلية كعلامة إدخال بدلاً من تحويلها إلى نص أو رسومات.
type: docs
weight: 80
url: /ar/net/aspose.words.saving/htmlfixedsaveoptions/exportformfields/
---
## HtmlFixedSaveOptions.ExportFormFields property

الحصول على أو تعيين إشارة إلى ما إذا كان يتم تصدير حقول النموذج كعناصر تفاعلية (كعلامة "إدخال") بدلاً من تحويلها إلى نص أو رسومات.

```csharp
public bool ExportFormFields { get; set; }
```

### أمثلة

يوضح كيفية تصدير حقول النموذج إلى Html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertCheckBox("CheckBox", false, 15);

// عندما نقوم بتصدير مستند يحتوي على حقول نموذج إلى .html ،
// هناك طريقتان يمكن من خلالهما لـ Aspose.Words تصدير حقول النموذج.
// سيؤدي تعيين علامة "ExportFormFields" على "true" إلى تصديرها ككائنات تفاعلية.
// تعيين هذه العلامة على "خطأ" سيعرض حقول النموذج كنص عادي.
// سيؤدي ذلك إلى تجميدها بقيمتها الحالية ، ومنع قارئ مستند HTML الخاص بنا
// من القدرة على التفاعل معهم.
HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    ExportFormFields = exportFormFields
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.ExportFormFields.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.ExportFormFields.html");

if (exportFormFields)
{
    Assert.True(Regex.Match(outDocContents,
        "<a name=\"CheckBox\" style=\"left:0pt; top:0pt;\"></a>" +
        "<input style=\"position:absolute; left:0pt; top:0pt;\" type=\"checkbox\" name=\"CheckBox\" />").Success);
}
else
{
    Assert.True(Regex.Match(outDocContents, 
        "<a name=\"CheckBox\" style=\"left:0pt; top:0pt;\"></a>" +
        "<div class=\"awdiv\" style=\"left:0.8pt; top:0.8pt; width:14.25pt; height:14.25pt; border:solid 0.75pt #000000;\"").Success);
}
```

### أنظر أيضا

* class [HtmlFixedSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* المجسم [Aspose.Words](../../../)


