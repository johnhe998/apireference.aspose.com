---
title: Field.DisplayResult
second_title: Aspose.Words لمراجع .NET API
description: Field ملكية. يحصل على النص الذي يمثل نتيجة الحقل المعروض.
type: docs
weight: 10
url: /ar/net/aspose.words.fields/field/displayresult/
---
## Field.DisplayResult property

يحصل على النص الذي يمثل نتيجة الحقل المعروض.

```csharp
public string DisplayResult { get; }
```

### ملاحظات

ملف[`UpdateListLabels`](../../../aspose.words/document/updatelistlabels/) يجب استدعاء الطريقة للحصول على القيمة الصحيحة لـ the [`FieldListNum`](../../fieldlistnum/) و[`FieldAutoNum`](../../fieldautonum/) و[`FieldAutoNumOut`](../../fieldautonumout/) و[`FieldAutoNumLgl`](../../fieldautonumlgl/) الحقول.

### أمثلة

يوضح كيفية الحصول على النص الحقيقي الذي يعرضه أحد الحقول في المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This document was written by ");
FieldAuthor fieldAuthor = (FieldAuthor)builder.InsertField(FieldType.FieldAuthor, true);
fieldAuthor.AuthorName = "John Doe";

// يمكننا استخدام خاصية DisplayResult للتحقق من النص الدقيق
// سيعرض الحقل في مكانه في المستند.
Assert.AreEqual(string.Empty, fieldAuthor.DisplayResult);

 // لا تحتفظ الحقول بقيم نتائج دقيقة في الوقت الفعلي.
// للتأكد من أن حقولنا تعرض نتائج دقيقة في أي وقت ،
// مثل قبل عملية الحفظ مباشرة ، نحتاج إلى تحديثها يدويًا.
fieldAuthor.Update();

Assert.AreEqual("John Doe", fieldAuthor.DisplayResult);

doc.Save(ArtifactsDir + "Field.DisplayResult.docx");
```

### أنظر أيضا

* class [Field](../)
* مساحة الاسم [Aspose.Words.Fields](../../field/)
* المجسم [Aspose.Words](../../../)


