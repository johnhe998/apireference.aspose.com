---
title: HtmlSaveOptions.ExportDropDownFormFieldAsText
second_title: Aspose.Words لمراجع .NET API
description: HtmlSaveOptions ملكية. يتحكم في كيفية حفظ حقول النموذج المنسدل في HTML أو MHTML . القيمة الافتراضية هيخاطئة .
type: docs
weight: 140
url: /ar/net/aspose.words.saving/htmlsaveoptions/exportdropdownformfieldastext/
---
## HtmlSaveOptions.ExportDropDownFormFieldAsText property

يتحكم في كيفية حفظ حقول النموذج المنسدل في HTML أو MHTML . القيمة الافتراضية هي`خاطئة` .

```csharp
public bool ExportDropDownFormFieldAsText { get; set; }
```

### ملاحظات

عند الضبط على`حقيقي` ، يقوم بتصدير حقول النموذج المنسدل كنص عادي`خاطئة`، يقوم بتصدير حقول النموذج المنسدلة كعنصر SELECT في HTML.

عند التصدير إلى EPUB ، يتم دائمًا حفظ حقول النموذج المنسدل كنص بسبب لمتطلبات هذا التنسيق.

### أمثلة

يوضح كيفية الحصول على حقول نموذج مربع التحرير والسرد المنسدل لدمجها مع نص الفقرة عند الحفظ في html.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// استخدم منشئ المستندات لإدراج مربع تحرير وسرد مع تحديد القيمة "اثنان".
builder.InsertComboBox("MyComboBox", new[] { "One", "Two", "Three" }, 1);

// تسمح لنا علامة "ExportDropDownFormFieldAsText" لكائن SaveOptions هذا
// التحكم في كيفية تعامل حفظ المستند إلى HTML مع مربعات التحرير والسرد المنسدلة.
// إعداده على "true" سيحول كل مربع تحرير وسرد إلى نص بسيط
// التي تعرض القيمة المحددة حاليًا لمربع التحرير والسرد ، مما يؤدي إلى تجميدها بشكل فعال.
// إعداده على "خطأ" سيحافظ على وظائف مربع التحرير والسرد باستخدام العلامة < select > و < الخيار >. العلامات.
HtmlSaveOptions options = new HtmlSaveOptions();
options.ExportDropDownFormFieldAsText = exportDropDownFormFieldAsText;    

doc.Save(ArtifactsDir + "HtmlSaveOptions.DropDownFormField.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.DropDownFormField.html");

if (exportDropDownFormFieldAsText)
    Assert.True(outDocContents.Contains(
        "<span>Two</span>"));
else
    Assert.True(outDocContents.Contains(
        "<select name=\"MyComboBox\">" +
            "<option>One</option>" +
            "<option selected=\"selected\">Two</option>" +
            "<option>Three</option>" +
        "</select>"));
```

### أنظر أيضا

* class [HtmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../htmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


