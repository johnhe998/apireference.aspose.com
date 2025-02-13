---
title: HtmlSaveOptions.CssClassNamePrefix
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد بادئة تمت إضافتها إلى جميع أسماء فئات CSS . القيمة الافتراضية هي سلسلة فارغة ولا تحتوي أسماء فئات CSS المُنشأة على بادئة مشتركة.
type: docs
weight: 30
url: /ar/net/aspose.words.saving/htmlsaveoptions/cssclassnameprefix/
---
## HtmlSaveOptions.CssClassNamePrefix property

يحدد بادئة تمت إضافتها إلى جميع أسماء فئات CSS . القيمة الافتراضية هي سلسلة فارغة ولا تحتوي أسماء فئات CSS المُنشأة على بادئة مشتركة.

```csharp
public string CssClassNamePrefix { get; set; }
```

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentException | القيمة ليست فارغة وليست معرّف CSS صالحًا. |

### ملاحظات

إذا لم تكن هذه القيمة فارغة ، فإن جميع فئات CSS التي تم إنشاؤها بواسطة Aspose.Words ستبدأ بالبادئة المحددة.

إذا كانت القيمة ليست كذلك`لا شيء` أو فارغًا ، يجب أن يكون معرّف CSS صالحًا.

### أمثلة

يوضح كيفية حفظ مستند إلى HTML وإضافة بادئة إلى جميع أسماء فئات CSS الخاصة به.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    CssClassNamePrefix = "myprefix-"
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.CssClassNamePrefix.html", saveOptions);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.CssClassNamePrefix.html");

Assert.True(outDocContents.Contains("<p class=\"myprefix-Header\">"));
Assert.True(outDocContents.Contains("<p class=\"myprefix-Footer\">"));

outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.CssClassNamePrefix.css");

Assert.True(outDocContents.Contains(".myprefix-Footer { margin-bottom:0pt; line-height:normal; font-family:Arial; font-size:11pt }\r\n" +
                                    ".myprefix-Header { margin-bottom:0pt; line-height:normal; font-family:Arial; font-size:11pt }\r\n"));
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


