---
title: Enum HtmlOfficeMathOutputMode
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.HtmlOfficeMathOutputMode تعداد. يحدد كيفية قيام Aspose.Words بتصدير OfficeMath إلى HTML و MHTML و EPUB.
type: docs
weight: 4840
url: /ar/net/aspose.words.saving/htmlofficemathoutputmode/
---
## HtmlOfficeMathOutputMode enumeration

يحدد كيفية قيام Aspose.Words بتصدير OfficeMath إلى HTML و MHTML و EPUB.

```csharp
public enum HtmlOfficeMathOutputMode
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Image | `0` | يتم تحويل OfficeMath إلى HTML كصورة محددة بواسطة علامة &lt;img&gt; . |
| MathML | `1` | يتم تحويل OfficeMath إلى HTML باستخدام MathML. |
| Text | `2` | يتم تحويل OfficeMath إلى HTML كتسلسل عمليات التشغيل المحددة بواسطة علامات &lt;span&gt; . |

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

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


