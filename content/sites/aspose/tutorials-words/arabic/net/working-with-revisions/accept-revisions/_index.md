---
title: قبول المراجعات
linktitle: قبول المراجعات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية قبول المراجعات على مستند Word باستخدام Aspose.Words for .NET
type: docs
weight: 10
url: /ar/net/working-with-revisions/accept-revisions/
---

في هذا البرنامج التعليمي ، سنرشدك خلال قبول المراجعات على مستند Word باستخدام ميزة قبول التنقيحات في Aspose.Words for .NET. اتبع الخطوات أدناه لفهم كود المصدر وقبول التغييرات على المستند.

## الخطوة 1: إضافة وتحرير محتوى المستند

في هذا المثال ، نقوم بإنشاء مستند وإضافة محتوى. نستخدم عدة فقرات لتوضيح التغييرات والمراجعات. إليك الطريقة:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//أضف نصًا إلى الفقرة الأولى ، ثم أضف فقرتين أخريين.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## الخطوة 2: تتبع المراجعات وإضافة التعليقات

نقوم بتمكين تتبع المراجعة وإضافة مراجعة إلى المستند. إليك الطريقة:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// هذه الفقرة هي مراجعة وسيكون لها مجموعة إشارة "IsInsertRevision" المطابقة.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## الخطوة 3: حذف فقرة وإدارة المراجعات

نحذف فقرة ونبحث عن المراجعات المحفوظة. إليك الطريقة:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// نظرًا لأننا نتتبع المراجعات ، لا تزال الفقرة موجودة في المستند ، وستحتوي على مجموعة علامة "IsDeleteRevision"
// وسيتم عرضها كمراجعة في Microsoft Word ، حتى نقبل أو نرفض جميع المراجعات.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## الخطوة 4: قبول التغييرات

نحن نقبل جميع التغييرات على الوثيقة. إليك الطريقة:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## الخطوة الخامسة: التوقف عن تتبع المراجعات

سنقوم بإيقاف تعقب المراجعات حتى لا تظهر التغييرات التي تم إجراؤها على المستند كمراجعات. إليك الطريقة:

```csharp
doc.StopTrackRevisions();
```
## الخطوة 6: حفظ المستند

 بعد إدخال حقل نموذج إدخال النص ، احفظ المستند في الموقع المطلوب باستخدام ملف`Save` طريقة. تأكد من توفير مسار الملف المناسب:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### مثال على شفرة المصدر لقبول المراجعات باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لقبول التغييرات في مستند باستخدام Aspose.Words for .NET:


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//أضف نصًا إلى الفقرة الأولى ، ثم أضف فقرتين أخريين.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// لدينا ثلاث فقرات ، لم يتم تسجيل أي منها كأي نوع من المراجعة
// إذا أضفنا / أزلنا أي محتوى في المستند أثناء تتبع المراجعات ،
// سيتم عرضها على هذا النحو في المستند ويمكن قبولها / رفضها.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// هذه الفقرة هي مراجعة وستحتوي على مجموعة الرايات "IsInsertRevision".
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// احصل على مجموعة فقرات المستند وقم بإزالة فقرة.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// نظرًا لأننا نتتبع المراجعات ، فلا تزال الفقرة موجودة في المستند ، وستحتوي على مجموعة "IsDeleteRevision"
// وسيتم عرضها كمراجعة في Microsoft Word ، حتى نقبل أو نرفض جميع المراجعات.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// تتم إزالة فقرة مراجعة الحذف بمجرد قبول التغييرات.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// يؤدي إيقاف تتبع المراجعات إلى ظهور هذا النص كنص عادي.
//لا يتم احتساب المراجعات عند تغيير المستند.
doc.StopTrackRevisions();

// احفظ المستند.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية قبول المراجعات في مستند Word باستخدام ميزة قبول التنقيحات في Aspose.Words for .NET. لقد اتبعنا الخطوات لإضافة محتوى المستند وتحريره ، وتتبع المراجعات ، وحذف فقرة تمت مراجعتها ، وقبول جميع التغييرات ، وإيقاف تتبع المراجعات. يمكنك الآن تطبيق هذه المعرفة لإدارة المراجعات بشكل فعال في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

### أسئلة وأجوبة

#### س: كيف يمكنني تمكين تتبع المراجعة في Aspose.Words for .NET؟

#### الحل 1:

 ج: لتمكين تتبع المراجعة في Aspose.Words for .NET ، استخدم`StartTrackRevisions` طريقة`Document` الكائن وحدد اسم المؤلف وتاريخ البدء لتعقب المراجعة.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### الحل 2:

 ج: يمكنك أيضًا تمكين تتبع المراجعة باستخدام ملف`Document` منشئ يقبل`trackRevisions` و`author` حدود.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### س: كيف يتم قبول جميع التغييرات في مستند باستخدام Aspose.Words for .NET؟

 ج: استخدم ملف`AcceptAllRevisions` طريقة`Document` لقبول كافة التغييرات التي تم إجراؤها على المستند.

```csharp
doc.AcceptAllRevisions();
```

#### س: كيف يمكنني حفظ مستند معدل مع المراجعات المقبولة؟

 استخدم ال`Save` طريقة`Document` كائن لحفظ المستند المعدل مع المراجعات المقبولة. تأكد من توفير مسار الملف الصحيح.

```csharp
doc.Save("path/to/the/document.docx");
```

#### س: كيف يمكنني التوقف عن تتبع المراجعات في Aspose.Words for .NET؟

 ج: استخدم ملف`StopTrackRevisions` طريقة`Document` كائن لإيقاف تتبع المراجعات.

```csharp
doc.StopTrackRevisions();
```

#### س: كيف يمكنني حذف فقرة تمت مراجعتها في مستند باستخدام Aspose.Words for .NET؟

 ج: لإزالة فقرة تمت مراجعتها في مستند ، يمكنك استخدام`Remove` طريقة جمع الفقرات.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```