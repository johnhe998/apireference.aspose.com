---
title: HtmlFixedSaveOptions.SaveFontFaceCssSeparately
second_title: Aspose.Words لمراجع .NET API
description: HtmlFixedSaveOptions ملكية. تشير العلامة إلى ما إذا كان يجب وضع قواعد CSS  fontface في ملف منفصل fontFaces.css عندما يتم حفظ مستند مع ورقة أنماط خارجية أي عندماExportEmbeddedCss هوخاطئة  . القيمة الافتراضية هيخاطئة  جميع قواعد CSS مكتوبة في ملف واحد styles.css .
type: docs
weight: 160
url: /ar/net/aspose.words.saving/htmlfixedsaveoptions/savefontfacecssseparately/
---
## HtmlFixedSaveOptions.SaveFontFaceCssSeparately property

تشير العلامة إلى ما إذا كان يجب وضع قواعد CSS "@ font-face" في ملف منفصل "fontFaces.css" عندما يتم حفظ مستند مع ورقة أنماط خارجية (أي عندما[`ExportEmbeddedCss`](../exportembeddedcss/) هو`خاطئة` ) . القيمة الافتراضية هي`خاطئة` ، جميع قواعد CSS مكتوبة في ملف واحد "styles.css" .

```csharp
public bool SaveFontFaceCssSeparately { get; set; }
```

### ملاحظات

تعيين هذه الخاصية على`حقيقي` يستعيد السلوك القديم (ملفات منفصلة) للتوافق مع الكود القديم.

### أمثلة

يوضح كيفية وضع CSS في ملف منفصل وإضافة بادئة لجميع أسماء فئات CSS الخاصة به.

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");

HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions
{
    CssClassNamesPrefix = "myprefix",
    SaveFontFaceCssSeparately = true
};

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.AddCssClassNamesPrefix.html", htmlFixedSaveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.AddCssClassNamesPrefix.html");

Assert.True(Regex.Match(outDocContents,
    "<div class=\"myprefixdiv myprefixpage\" style=\"width:595[.]3pt; height:841[.]9pt;\">" +
    "<div class=\"myprefixdiv\" style=\"left:85[.]05pt; top:36pt; clip:rect[(]0pt,510[.]25pt,74[.]95pt,-85.05pt[)];\">" +
    "<span class=\"myprefixspan myprefixtext001\" style=\"font-size:11pt; left:294[.]73pt; top:0[.]36pt; line-height:12[.]29pt;\">").Success);

outDocContents = File.ReadAllText(ArtifactsDir + "HtmlFixedSaveOptions.AddCssClassNamesPrefix/styles.css");

Assert.True(Regex.Match(outDocContents,
    ".myprefixdiv { position:absolute; } " +
    ".myprefixspan { position:absolute; white-space:pre; color:#000000; font-size:12pt; }").Success);
```

### أنظر أيضا

* class [HtmlFixedSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* المجسم [Aspose.Words](../../../)


