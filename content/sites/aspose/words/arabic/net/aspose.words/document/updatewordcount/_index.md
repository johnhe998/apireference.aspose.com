---
title: Document.UpdateWordCount
second_title: Aspose.Words لمراجع .NET API
description: Document طريقة. يقوم بتحديث خصائص عدد الكلمات الخاصة بالمستند.
type: docs
weight: 770
url: /ar/net/aspose.words/document/updatewordcount/
---
## UpdateWordCount() {#updatewordcount}

يقوم بتحديث خصائص عدد الكلمات الخاصة بالمستند.

```csharp
public void UpdateWordCount()
```

### ملاحظات

**UpdateWordCount** يعيد حساب وتحديث خصائص الأحرف والكلمات والفقرات_ في ملف[`BuiltInDocumentProperties`](../builtindocumentproperties/) جمع **وثيقة**.

لاحظ أن **UpdateWordCount** لا يقوم بتحديث عدد الأسطر وخصائص الصفحات. استخدم ملف`UpdateWordCount` الزائد وتمرير القيمة الحقيقية كمعامل للقيام بذلك.

عند استخدام إصدار تقييم ، سيتم أيضًا تضمين العلامة المائية للتقييم_ في عدد الكلمات.

### أمثلة

يوضح كيفية تحديث كافة تسميات القائمة في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
builder.Write("Ut enim ad minim veniam, " +
                "quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Aspose.Words لا تتعقب مقاييس المستندات مثل هذه في الوقت الفعلي.
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Paragraphs);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

// للحصول على قيم دقيقة لثلاث من هذه الخصائص ، سنحتاج إلى تحديثها يدويًا.
doc.UpdateWordCount();

Assert.AreEqual(196, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(36, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(2, doc.BuiltInDocumentProperties.Paragraphs);

// بالنسبة لعدد الأسطر ، سنحتاج إلى استدعاء حمل زائد محدد لطريقة التحديث.
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

doc.UpdateWordCount(true);

Assert.AreEqual(4, doc.BuiltInDocumentProperties.Lines);
```

### أنظر أيضا

* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)

---

## UpdateWordCount(bool) {#updatewordcount_1}

يحدّث خصائص عدد الكلمات في المستند ، ويتم تحديثه اختياريًا[`Lines`](../../../aspose.words.properties/builtindocumentproperties/lines/) الملكية .

```csharp
public void UpdateWordCount(bool updateLinesCount)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| updateLinesCount | Boolean | صحيح إذا تم حساب عدد الأسطر في المستند. |

### ملاحظات

ستعيد هذه الطريقة بناء تخطيط صفحة المستند.

### أمثلة

يوضح كيفية تحديث كافة تسميات القائمة في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
builder.Write("Ut enim ad minim veniam, " +
                "quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Aspose.Words لا تتعقب مقاييس المستندات مثل هذه في الوقت الفعلي.
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(0, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Paragraphs);
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

// للحصول على قيم دقيقة لثلاث من هذه الخصائص ، سنحتاج إلى تحديثها يدويًا.
doc.UpdateWordCount();

Assert.AreEqual(196, doc.BuiltInDocumentProperties.Characters);
Assert.AreEqual(36, doc.BuiltInDocumentProperties.Words);
Assert.AreEqual(2, doc.BuiltInDocumentProperties.Paragraphs);

// بالنسبة لعدد الأسطر ، سنحتاج إلى استدعاء حمل زائد محدد لطريقة التحديث.
Assert.AreEqual(1, doc.BuiltInDocumentProperties.Lines);

doc.UpdateWordCount(true);

Assert.AreEqual(4, doc.BuiltInDocumentProperties.Lines);
```

### أنظر أيضا

* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


