---
title: HtmlSaveOptions.OfficeMathOutputMode
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يتحكم في كيفية تصدير كائنات OfficeMath إلى HTML أو MHTML أو EPUB. القيمة الافتراضية هيHtmlOfficeMathOutputMode.Image .
type: docs
weight: 400
url: /ar/net/aspose.words.saving/htmlsaveoptions/officemathoutputmode/
---
## HtmlSaveOptions.OfficeMathOutputMode property

يتحكم في كيفية تصدير كائنات OfficeMath إلى HTML أو MHTML أو EPUB. القيمة الافتراضية هي`HtmlOfficeMathOutputMode.Image` .

```csharp
public HtmlOfficeMathOutputMode OfficeMathOutputMode { get; set; }
```

### أمثلة

يوضح كيفية تحديد كيفية تصدير كائنات Microsoft OfficeMath إلى HTML.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

// عندما نحفظ المستند بتنسيق HTML ، يمكننا تمرير كائن SaveOptions
// لتحديد كيفية معالجة عملية الحفظ لكائنات OfficeMath.
// تعيين خاصية "OfficeMathOutputMode" على "HtmlOfficeMathOutputMode.Image"
// سيعرض كل كائن OfficeMath في صورة.
// تعيين خاصية "OfficeMathOutputMode" على "HtmlOfficeMathOutputMode.MathML"
// سيحول كل كائن OfficeMath إلى MathML.
// تعيين خاصية "OfficeMathOutputMode" على "HtmlOfficeMathOutputMode.Text"
// سيمثل كل صيغة OfficeMath باستخدام نص HTML عادي.
HtmlSaveOptions options = new HtmlSaveOptions { OfficeMathOutputMode = htmlOfficeMathOutputMode };

doc.Save(ArtifactsDir + "HtmlSaveOptions.OfficeMathOutputMode.html", options);
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.OfficeMathOutputMode.html");

switch (htmlOfficeMathOutputMode)
{
    case HtmlOfficeMathOutputMode.Image:
        Assert.True(Regex.Match(outDocContents, 
            "<p style=\"margin-top:0pt; margin-bottom:10pt\">" +
                "<img src=\"HtmlSaveOptions.OfficeMathOutputMode.001.png\" width=\"159\" height=\"19\" alt=\"\" style=\"vertical-align:middle; " +
                "-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
            "</p>").Success);
        break;
    case HtmlOfficeMathOutputMode.MathML:
        Assert.True(Regex.Match(outDocContents,
            "<p style=\"margin-top:0pt; margin-bottom:10pt; text-align:center\">" +
                "<math xmlns=\"http://www.w3.org/1998/Math/MathML\"> " +
                    "<mi>i</mi>" +
                    "<mo>[+]</mo>" +
                    "<mi>b</mi>" +
                    "<mo>-</mo>" +
                    "<mi>c</mi>" +
                    "<mo>≥</mo>" +
                    ".*" +
                "</math>" +
            "</p>").Success);
        break;
    case HtmlOfficeMathOutputMode.Text:
        Assert.True(Regex.Match(outDocContents,
            @"<p style=\""margin-top:0pt; margin-bottom:10pt; text-align:center\"">" +
                @"<span style=\""font-family:'Cambria Math'\"">i[+]b-c≥iM[+]bM-cM </span>" +
            "</p>").Success);
        break;
}
```

### أنظر أيضا

* enum [HtmlOfficeMathOutputMode](../../htmlofficemathoutputmode/)
* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


