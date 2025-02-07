---
title: Document.LastSection
second_title: Aspose.Words لمراجع .NET API
description: Document ملكية. يحصل على القسم الأخير في المستند.
type: docs
weight: 220
url: /ar/net/aspose.words/document/lastsection/
---
## Document.LastSection property

يحصل على القسم الأخير في المستند.

```csharp
public Section LastSection { get; }
```

### ملاحظات

عوائد`لا شيء` إذا لم يكن هناك أقسام.

### أمثلة

يوضح كيفية إنشاء قسم جديد باستخدام منشئ المستندات.

```csharp
Document doc = new Document();

// يحتوي المستند الفارغ على قسم واحد افتراضيًا ،
// التي تحتوي على عقد فرعية يمكننا تعديلها.
Assert.AreEqual(1, doc.Sections.Count);

// استخدم منشئ المستندات لإضافة نص إلى القسم الأول.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// أنشئ قسمًا ثانيًا عن طريق إدخال فاصل مقطعي.
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(2, doc.Sections.Count);

// لكل قسم إعدادات إعداد الصفحة الخاصة به.
// يمكننا تقسيم النص في القسم الثاني إلى عمودين.
// لن يؤثر هذا على النص في القسم الأول.
doc.LastSection.PageSetup.TextColumns.SetCount(2);
builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

Assert.AreEqual(1, doc.FirstSection.PageSetup.TextColumns.Count);
Assert.AreEqual(2, doc.LastSection.PageSetup.TextColumns.Count);

doc.Save(ArtifactsDir + "Section.Create.docx");
```

### أنظر أيضا

* class [Section](../../section/)
* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


