---
title: Cell.EnsureMinimum
second_title: Aspose.Words لمراجع .NET API
description: Cell طريقة. إذا لم يكن الطفل الأخير فقرة  فسيتم إنشاء وإلحاق فقرة واحدة فارغة.
type: docs
weight: 120
url: /ar/net/aspose.words.tables/cell/ensureminimum/
---
## Cell.EnsureMinimum method

إذا لم يكن الطفل الأخير فقرة ، فسيتم إنشاء وإلحاق فقرة واحدة فارغة.

```csharp
public void EnsureMinimum()
```

### أمثلة

يوضح كيفية التأكد من احتواء عقدة الخلية على العقد التي نحتاجها لبدء إضافة محتوى إليها.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
Row row = new Row(doc);
table.AppendChild(row);
Cell cell = new Cell(doc);
row.AppendChild(cell);

// قد تحتوي الخلايا على فقرات تحتوي على عناصر نموذجية مثل عمليات التشغيل والأشكال وحتى الجداول الأخرى.
// لا تحتوي خليتنا الجديدة على أي فقرات ، ولا يمكننا إضافة محتويات مثل عقد التشغيل والشكل إليها حتى يتم ذلك.
Assert.AreEqual(0, cell.GetChildNodes(NodeType.Any, true).Count);

// استدعاء طريقة "ضمان الحد الأدنى" في الخلية سيضمن ذلك
// تحتوي الخلية على فقرة فارغة واحدة على الأقل ، يمكننا بعد ذلك إضافة محتويات إليها.
cell.EnsureMinimum();
cell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### أنظر أيضا

* class [Cell](../)
* مساحة الاسم [Aspose.Words.Tables](../../cell/)
* المجسم [Aspose.Words](../../../)


