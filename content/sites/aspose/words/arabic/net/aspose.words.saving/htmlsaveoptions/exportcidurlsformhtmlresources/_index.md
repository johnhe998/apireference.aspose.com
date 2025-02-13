---
title: HtmlSaveOptions.ExportCidUrlsForMhtmlResources
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد ما إذا كان سيتم استخدام عناوين URL لـ CID معرف المحتوى للإشارة إلى الموارد الصور والخطوط و CSS المضمنة في مستندات MHTML . القيمة الافتراضية هيخاطئة .
type: docs
weight: 120
url: /ar/net/aspose.words.saving/htmlsaveoptions/exportcidurlsformhtmlresources/
---
## HtmlSaveOptions.ExportCidUrlsForMhtmlResources property

يحدد ما إذا كان سيتم استخدام عناوين URL لـ CID (معرف المحتوى) للإشارة إلى الموارد (الصور والخطوط و CSS) المضمنة في مستندات MHTML . القيمة الافتراضية هي`خاطئة` .

```csharp
public bool ExportCidUrlsForMhtmlResources { get; set; }
```

### ملاحظات

يؤثر هذا الخيار فقط على المستندات التي يتم حفظها في MHTML.

بشكل افتراضي ، تتم الإشارة إلى الموارد في مستندات MHTML بواسطة اسم الملف (على سبيل المثال ، "image.png") ، والتي تتم مطابقتها مع رؤوس "موقع المحتوى" لأجزاء MIME.

يتيح هذا الخيار طريقة بديلة ، حيث تتم كتابة المراجع إلى ملفات الموارد كعناوين URL CID (معرف المحتوى) (على سبيل المثال ، "cid: image.png") وتتم مطابقتها مع رؤوس "Content-ID".

من الناحية النظرية ، يجب ألا يكون هناك فرق بين طريقتين المراجع ويجب أن يعمل أي منهما بشكل جيد في أي متصفح أو وكيل بريد. ومع ذلك ، في الممارسة العملية ، يفشل بعض الوكلاء في جلب الموارد حسب اسم الملف. إذا رفض المستعرض أو وكيل البريد تحميل الموارد المضمنة في مستند MTHML (لا يعرض الصور أو لا يقوم بتحميل أنماط CSS ) ، فحاول تصدير المستند باستخدام عناوين URL لـ CID.

### أمثلة

يوضح كيفية تمكين معرفات المحتوى لمستندات MHTML الناتجة.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// سيؤدي تعيين هذه العلامة إلى استبدال علامات "موقع المحتوى"
// مع علامات "Content-ID" لكل مورد من مستند الإدخال.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Mhtml)
{
    ExportCidUrlsForMhtmlResources = exportCidUrlsForMhtmlResources,
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ContentIdUrls.mht", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ContentIdUrls.mht");

if (exportCidUrlsForMhtmlResources)
{
    Assert.True(outDocContents.Contains("Content-ID: <document.html>"));
    Assert.True(outDocContents.Contains("<link href=3D\"cid:styles.css\" type=3D\"text/css\" rel=3D\"stylesheet\" />"));
    Assert.True(outDocContents.Contains("@font-face { font-family:'Arial Black'; font-weight:bold; src:url('cid:arib=\r\nlk.ttf') }"));
    Assert.True(outDocContents.Contains("<img src=3D\"cid:image.003.jpeg\" width=3D\"350\" height=3D\"180\" alt=3D\"\" />"));
}
else
{
    Assert.True(outDocContents.Contains("Content-Location: document.html"));
    Assert.True(outDocContents.Contains("<link href=3D\"styles.css\" type=3D\"text/css\" rel=3D\"stylesheet\" />"));
    Assert.True(outDocContents.Contains("@font-face { font-family:'Arial Black'; font-weight:bold; src:url('ariblk.t=\r\ntf') }"));
    Assert.True(outDocContents.Contains("<img src=3D\"image.003.jpeg\" width=3D\"350\" height=3D\"180\" alt=3D\"\" />"));
}
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


