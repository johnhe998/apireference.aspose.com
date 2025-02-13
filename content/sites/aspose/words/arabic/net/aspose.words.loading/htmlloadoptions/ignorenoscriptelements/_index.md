---
title: HtmlLoadOptions.IgnoreNoscriptElements
second_title: Aspose.Words لمراجع .NET API
description: HtmlLoadOptions ملكية. الحصول على أو تعيين قيمة تشير إلى تجاهل عناصر HTML noscript . القيمة الافتراضية هيخاطئة .
type: docs
weight: 40
url: /ar/net/aspose.words.loading/htmlloadoptions/ignorenoscriptelements/
---
## HtmlLoadOptions.IgnoreNoscriptElements property

الحصول على أو تعيين قيمة تشير إلى تجاهل عناصر HTML &lt;noscript&gt; . القيمة الافتراضية هي`خاطئة` .

```csharp
public bool IgnoreNoscriptElements { get; set; }
```

### ملاحظات

مثل MS Word ، لا تدعم Aspose.Words النصوص وتقوم افتراضيًا بتحميل محتوى &lt;noscript&gt; element إلى المستند الناتج. ومع ذلك ، في معظم المتصفحات ، يتم دعم البرامج النصية والمحتوى من &lt;noscript&gt; غير مرئي. تعيين هذه الخاصية إلى`حقيقي` يفرض على Aspose.Words تجاهل جميع عناصر &lt;noscript&gt; ويساعد في إنتاج مستندات تبدو أقرب إلى ما يظهر في المتصفحات .

### أمثلة

يوضح كيفية تجاهل عناصر HTML &lt;noscript&gt;.

```csharp
const string html = @"
    <html>
      <head>
        <title>NOSCRIPT</title>
          <meta http-equiv=""Content-Type"" content=""text/html; charset=utf-8"">
          <script type=""text/javascript"">
            alert(""Hello, world!"");
          </script>
      </head>
    <body>
      <noscript><p>Your browser does not support JavaScript!</p></noscript>
    </body>
    </html>";

HtmlLoadOptions htmlLoadOptions = new HtmlLoadOptions();
htmlLoadOptions.IgnoreNoscriptElements = ignoreNoscriptElements;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), htmlLoadOptions);
doc.Save(ArtifactsDir + "HtmlLoadOptions.IgnoreNoscriptElements.pdf");
```

### أنظر أيضا

* class [HtmlLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../htmlloadoptions/)
* المجسم [Aspose.Words](../../../)


