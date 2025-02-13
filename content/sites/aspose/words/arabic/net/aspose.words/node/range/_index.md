---
title: Node.Range
second_title: Aspose.Words لمراجع .NET API
description: Node ملكية. إرجاع أ نطاق الكائن الذي يمثل جزء المستند الموجود في هذه العقدة.
type: docs
weight: 80
url: /ar/net/aspose.words/node/range/
---
## Node.Range property

إرجاع أ **نطاق** الكائن الذي يمثل جزء المستند الموجود في هذه العقدة.

```csharp
public Range Range { get; }
```

### أمثلة

يوضح كيفية حذف جميع العقد من نطاق.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أضف نصًا إلى القسم الأول في المستند ، ثم أضف قسمًا آخر.
builder.Write("Section 1. ");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Write("Section 2.");

Assert.AreEqual("Section 1. \fSection 2.", doc.GetText().Trim());

// قم بإزالة القسم الأول بالكامل عن طريق إزالة جميع العقد
// ضمن مداها ، بما في ذلك القسم نفسه.
doc.Sections[0].Range.Delete();

Assert.AreEqual(1, doc.Sections.Count);
Assert.AreEqual("Section 2.", doc.GetText().Trim());
```

### أنظر أيضا

* class [Range](../../range/)
* class [Node](../)
* مساحة الاسم [Aspose.Words](../../node/)
* المجسم [Aspose.Words](../../../)


