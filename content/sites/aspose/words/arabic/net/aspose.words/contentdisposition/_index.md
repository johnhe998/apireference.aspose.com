---
title: Enum ContentDisposition
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.ContentDisposition تعداد. يعدّد طرقًا مختلفة لتقديم المستند في مستعرض العميل.
type: docs
weight: 330
url: /ar/net/aspose.words/contentdisposition/
---
## ContentDisposition enumeration

يعدّد طرقًا مختلفة لتقديم المستند في مستعرض العميل.

```csharp
public enum ContentDisposition
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Attachment | `0` | أرسل المستند إلى المستعرض وقدم خيارًا لحفظ المستند على القرص أو فتحه في application المرتبط بامتداد المستند. |
| Inline | `1` | أرسل المستند إلى المستعرض ويقدم خيارًا لحفظ المستند على القرص أو فتحه داخل المستعرض. |

### ملاحظات

لاحظ أن السلوك الفعلي لمتصفح العميل قد يتأثر بتكوين الأمان للمتصفح.

### أمثلة

يوضح كيفية إجراء دمج المراسلات ، ثم حفظ المستند في مستعرض العميل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(" MERGEFIELD FullName ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Company ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD Address ");
builder.InsertParagraph();
builder.InsertField(" MERGEFIELD City ");

doc.MailMerge.Execute(new string[] { "FullName", "Company", "Address", "City" },
    new object[] { "James Bond", "MI5 Headquarters", "Milbank", "London" });

// أرسل المستند إلى متصفح العميل.
Assert.That(() => doc.Save(response, "Artifacts/MailMerge.ExecuteArray.docx", ContentDisposition.Inline, null),
    Throws.TypeOf<ArgumentNullException>()); // تم الإلقاء لأن HttpResponse فارغ في الاختبار.

// سنحتاج إلى إغلاق هذه الاستجابة يدويًا للتأكد من أننا لا نضيف أي محتوى غير ضروري إلى المستند بعد الحفظ.
Assert.That(() => response.End(), Throws.TypeOf<NullReferenceException>());
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


