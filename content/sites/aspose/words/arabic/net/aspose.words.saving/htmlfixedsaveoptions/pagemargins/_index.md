---
title: HtmlFixedSaveOptions.PageMargins
second_title: Aspose.Words لمراجع .NET API
description: HtmlFixedSaveOptions ملكية. يحدد الهوامش حول الصفحات في مستند HTML. تقاس قيمة الهوامش بالنقاط ويجب أن تكون مساوية لـ 0 أو أكبر منها . القيمة الافتراضية هي 10 نقاط .
type: docs
weight: 120
url: /ar/net/aspose.words.saving/htmlfixedsaveoptions/pagemargins/
---
## HtmlFixedSaveOptions.PageMargins property

يحدد الهوامش حول الصفحات في مستند HTML. تقاس قيمة الهوامش بالنقاط ويجب أن تكون مساوية لـ 0 أو أكبر منها . القيمة الافتراضية هي 10 نقاط .

```csharp
public double PageMargins { get; set; }
```

### ملاحظات

يعتمد على قيمة[`PageHorizontalAlignment`](../pagehorizontalalignment/) منشأه:

* يحدد هوامش الصفحة العلوية والسفلية واليسرى إذا كانت القيمةLeft .
* يحدد هوامش الصفحة العلوية والسفلية واليمنى إذا كانت القيمةRight .
* يحدد هوامش الصفحة العلوية والسفلية إذا كانت القيمةCenter .

### أمثلة

يوضح كيفية ضبط هوامش الصفحة عند حفظ مستند بتنسيق HTML.

```csharp
Document doc = new Document(MyDir + "Document.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions
{
    PageMargins = 15
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.PageMargins.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.PageMargins/styles.css");

Assert.True(Regex.Match(outDocContents,
    "[.]awpage { position:relative; border:solid 1pt black; margin:15pt auto 15pt auto; overflow:hidden; }").Success);
```

### أنظر أيضا

* class [HtmlFixedSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* المجسم [Aspose.Words](../../../)


