---
title: FindReplaceOptions.IgnoreFieldCodes
second_title: Aspose.Words لمراجع .NET API
description: FindReplaceOptions ملكية. الحصول على أو تعيين قيمة منطقية تشير إما إلى تجاهل النص داخل رموز الحقول . القيمة الافتراضية هيخاطئة .
type: docs
weight: 70
url: /ar/net/aspose.words.replacing/findreplaceoptions/ignorefieldcodes/
---
## FindReplaceOptions.IgnoreFieldCodes property

الحصول على أو تعيين قيمة منطقية تشير إما إلى تجاهل النص داخل رموز الحقول . القيمة الافتراضية هي`خاطئة` .

```csharp
public bool IgnoreFieldCodes { get; set; }
```

### ملاحظات

يؤثر هذا الخيار على رموز الحقول فقط (لا يتجاهل العقد بين FieldSeparator وFieldEnd).

لتجاهل الحقل بالكامل ، يرجى استخدام الخيار المقابل[`IgnoreFields`](../ignorefields/).

### أمثلة

يوضح كيفية تجاهل النص داخل رموز الحقول.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("INCLUDETEXT", "Test IT!");

FindReplaceOptions options = new FindReplaceOptions {IgnoreFieldCodes = ignoreFieldCodes};

// استبدل "T" في المستند بتجاهل النص داخل رمز الحقل أم لا.
doc.Range.Replace(new Regex("T"), "*", options);
Console.WriteLine(doc.GetText());

Assert.AreEqual(
    ignoreFieldCodes
        ? "\u0013INCLUDETEXT\u0014*est I*!\u0015"
        : "\u0013INCLUDE*EX*\u0014*est I*!\u0015", doc.GetText().Trim());
```

### أنظر أيضا

* class [FindReplaceOptions](../)
* مساحة الاسم [Aspose.Words.Replacing](../../findreplaceoptions/)
* المجسم [Aspose.Words](../../../)


