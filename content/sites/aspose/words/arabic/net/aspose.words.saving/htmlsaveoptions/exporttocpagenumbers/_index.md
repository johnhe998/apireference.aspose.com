---
title: HtmlSaveOptions.ExportTocPageNumbers
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد ما إذا كان سيتم كتابة أرقام الصفحات في جدول المحتويات عند حفظ HTML و MHTML و EPUB. القيمة الافتراضية هيخاطئة .
type: docs
weight: 280
url: /ar/net/aspose.words.saving/htmlsaveoptions/exporttocpagenumbers/
---
## HtmlSaveOptions.ExportTocPageNumbers property

يحدد ما إذا كان سيتم كتابة أرقام الصفحات في جدول المحتويات عند حفظ HTML و MHTML و EPUB. القيمة الافتراضية هي`خاطئة` .

```csharp
public bool ExportTocPageNumbers { get; set; }
```

### أمثلة

يوضح كيفية عرض أرقام الصفحات عند حفظ مستند مع جدول محتويات في .html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل جدول محتويات ، ثم املأ المستند بالفقرات المنسقة باستخدام "عنوان"
// النمط الذي سيختاره جدول المحتويات كمدخلات. سيعرض كل إدخال فقرة العنوان على اليسار ،
// ورقم الصفحة الذي يحتوي على العنوان الموجود على اليمين.
FieldToc fieldToc = (FieldToc)builder.InsertField(FieldType.FieldTOC, true);

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 1"];
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 1");
builder.Writeln("Entry 2");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 3");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Entry 4");
fieldToc.UpdatePageNumbers();
doc.UpdateFields();

// لا تحتوي مستندات HTML على صفحات. إذا حفظنا هذا المستند بتنسيق HTML ،
// لن يكون لأرقام الصفحات التي يعرضها جدول المحتويات لدينا أي معنى.
// عندما نحفظ المستند إلى HTML ، يمكننا تمرير كائن SaveOptions لحذف أرقام الصفحات هذه من جدول المحتويات.
// إذا قمنا بتعيين علامة "ExportTocPageNumbers" على "true" ،
// سيعرض كل إدخال في جدول المحتويات العنوان ، والفاصل ، ورقم الصفحة ، مع الحفاظ على مظهره في Microsoft Word.
// إذا قمنا بتعيين علامة "ExportTocPageNumbers" على "خطأ" ،
// ستحذف عملية الحفظ كلاً من الفاصل ورقم الصفحة وتترك عنوان كل إدخال كما هو.
HtmlSaveOptions options = new HtmlSaveOptions { ExportTocPageNumbers = exportTocPageNumbers };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportTocPageNumbers.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportTocPageNumbers.html");

if (exportTocPageNumbers)
{
    Assert.True(outDocContents.Contains(
        "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
        "<span>Entry 1</span>" +
        "<span style=\"width:428.14pt; font-family:'Lucida Console'; font-size:10pt; display:inline-block; -aw-font-family:'Times New Roman'; " +
        "-aw-tabstop-align:right; -aw-tabstop-leader:dots; -aw-tabstop-pos:469.8pt\">.......................................................................</span>" +
        "<span>2</span>" +
        "</p>"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
        "<span>Entry 1</span>" +
        "</p>"));
}
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


