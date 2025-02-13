---
title: HtmlSaveOptions.ExportXhtmlTransitional
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يحدد ما إذا كان سيتم كتابة إعلان DOCTYPE عند الحفظ بتنسيق HTML أو MHTML.حقيقي  يكتب إعلان DOCTYPE في المستند قبل عنصر الجذر. القيمة الافتراضية هيخاطئة. عند الحفظ في EPUB أو HTML5 Html5  يتم كتابة إعلان DOCTYPE دائمًا.
type: docs
weight: 290
url: /ar/net/aspose.words.saving/htmlsaveoptions/exportxhtmltransitional/
---
## HtmlSaveOptions.ExportXhtmlTransitional property

يحدد ما إذا كان سيتم كتابة إعلان DOCTYPE عند الحفظ بتنسيق HTML أو MHTML.`حقيقي` ، يكتب إعلان DOCTYPE في المستند قبل عنصر الجذر. القيمة الافتراضية هي`خاطئة`. عند الحفظ في EPUB أو HTML5 (Html5 ) يتم كتابة إعلان DOCTYPE دائمًا.

```csharp
public bool ExportXhtmlTransitional { get; set; }
```

### ملاحظات

تقوم Aspose.Words دائمًا بكتابة HTML جيد التكوين بغض النظر عن هذا الإعداد.

متي`حقيقي`، ستبدو بداية مستند إخراج HTML بالشكل التالي:

تهدف Aspose.Words إلى إخراج XHTML وفقًا لمواصفات XHTML 1.0 Transitional ، ولكن لن يتم دائمًا التحقق من صحة المخرجات مقابل DTD. من الصعب أو المستحيل تعيين بعض الهياكل داخل مستند Microsoft Word إلى مستند يتم التحقق منه مقابل مخطط XHTML. على سبيل المثال ، لا تسمح XHTML بالقوائم المتداخلة (لا يمكن دمج UL داخل عنصر UL آخر) ، ولكن في مستندات Microsoft Word ، تحدث القوائم متعددة المستويات كثيرًا.

```csharp
<?xml version="1.0" encoding="utf-8" standalone="no" ?>
<!DOCTYPE html 
      PUBLIC "-// W3C // DTD XHTML 1.0 Transitional // EN "
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml "xml: lang =" en "lang =" ar ">
```

### أمثلة

يوضح كيفية عرض عنوان DOCTYPE عند تحويل المستندات إلى معيار Xhtml 1.0 الانتقالي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");

HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    HtmlVersion = HtmlVersion.Xhtml,
    ExportXhtmlTransitional = showDoctypeDeclaration,
    PrettyFormat = true
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html", options);

// سوف تحتوي وثيقتنا على عنوان إعلان DOCTYPE فقط إذا قمنا بتعيين علامة "ExportXhtmlTransitional" على "true".
string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportXhtmlTransitional.html");

if (showDoctypeDeclaration)
    Assert.True(outDocContents.Contains(
        "<?xml version=\"1.0\" encoding=\"utf-8\" standalone=\"no\"?>\r\n" +
        "<!DOCTYPE html PUBLIC \"-// W3C // DTD XHTML 1.0 Transitional // EN \ "\" http: //www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd \ "> \ r \ n" +
        "<html xmlns=\"http://www.w3.org/1999/xhtml\"> ")) ;
else
    Assert.True(outDocContents.Contains("<html>"));
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


