---
title: Inline.IsInsertRevision
second_title: Aspose.Words لمراجع .NET API
description: Inline ملكية. إرجاع صحيح إذا تم إدراج هذا الكائن في Microsoft Word أثناء تمكين تعقب التغييرات.
type: docs
weight: 40
url: /ar/net/aspose.words/inline/isinsertrevision/
---
## Inline.IsInsertRevision property

إرجاع صحيح إذا تم إدراج هذا الكائن في Microsoft Word أثناء تمكين تعقب التغييرات.

```csharp
public bool IsInsertRevision { get; }
```

### أمثلة

يوضح كيفية تحديد نوع المراجعة لعقدة مضمنة.

```csharp
Document doc = new Document(MyDir + "Revision runs.docx");

// عندما نقوم بتحرير المستند أثناء وجود خيار "تتبع التغييرات" ، الموجود في مراجعة - >; تتبع ،
// قيد التشغيل في Microsoft Word ، التغييرات التي نطبقها تعد مراجعات.
// عند تحرير مستند باستخدام Aspose.Words ، يمكننا البدء في تتبع المراجعات بواسطة
// استدعاء طريقة "StartTrackRevisions" الخاصة بالمستند وإيقاف التتبع باستخدام طريقة "StopTrackRevisions".
// يمكننا إما قبول المراجعات لاستيعابها في المستند
// أو رفضها لتغيير التغيير المقترح بشكل فعال.
Assert.AreEqual(6, doc.Revisions.Count);

// العقدة الأصلية للمراجعة هي المدى الذي تهتم به المراجعة. التشغيل هو عقدة مضمنة.
Run run = (Run)doc.Revisions[0].ParentNode;

Paragraph firstParagraph = run.ParentParagraph;
RunCollection runs = firstParagraph.Runs;

Assert.AreEqual(6, runs.ToArray().Length);

// فيما يلي خمسة أنواع من المراجعات التي يمكنها وضع علامة على عقدة مضمنة.
// 1 - مراجعة "إدراج":
// تحدث هذه المراجعة عندما نقوم بإدخال نص أثناء تتبع التغييرات.
Assert.IsTrue(runs[2].IsInsertRevision);

// 2 - مراجعة "تنسيق":
// تحدث هذه المراجعة عندما نغير تنسيق النص أثناء تتبع التغييرات.
Assert.IsTrue(runs[2].IsFormatRevision);

// 3 - مراجعة "الانتقال من":
// عندما نقوم بتمييز النص في Microsoft Word ، ثم اسحبه إلى مكان مختلف في المستند
// أثناء تعقب التغييرات ، تظهر مراجعتان.
// مراجعة "الانتقال من" هي نسخة من النص في الأصل قبل نقله.
Assert.IsTrue(runs[4].IsMoveFromRevision);

// 4 - مراجعة "الانتقال إلى":
// مراجعة "الانتقال إلى" هي النص الذي نقلناه في موضعه الجديد في المستند.
تظهر المراجعات "الانتقال من" و "الانتقال إلى" في أزواج لكل مراجعة حركة نقوم بها.
// قبول مراجعة النقل يحذف مراجعة "الانتقال من" ونصها ،
// ويحافظ على النص من مراجعة "الانتقال إلى".
// رفض مراجعة الخطوة على العكس من ذلك يحافظ على "الانتقال من" المراجعة ويحذف مراجعة "الانتقال إلى".
Assert.IsTrue(runs[1].IsMoveToRevision);

// 5 - مراجعة "حذف":
// تحدث هذه المراجعة عندما نحذف النص أثناء تتبع التغييرات. عندما نحذف نصًا مثل هذا ،
// سيبقى في المستند كمراجعة حتى نقبل المراجعة ،
// التي ستحذف النص نهائيًا ، أو ترفض المراجعة ، مما سيبقي النص الذي حذفناه في مكانه.
Assert.IsTrue(runs[5].IsDeleteRevision);
```

### أنظر أيضا

* class [Inline](../)
* مساحة الاسم [Aspose.Words](../../inline/)
* المجسم [Aspose.Words](../../../)


