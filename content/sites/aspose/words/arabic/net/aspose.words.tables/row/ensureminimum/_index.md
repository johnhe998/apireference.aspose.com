---
title: Row.EnsureMinimum
second_title: Aspose.Words لمراجع .NET API
description: Row طريقة. إذا كان ملف صف لا يحتوي على خلايا  يقوم بإنشاء وإلحاق خلية واحدة خلية .
type: docs
weight: 110
url: /ar/net/aspose.words.tables/row/ensureminimum/
---
## Row.EnsureMinimum method

إذا كان ملف **صف** لا يحتوي على خلايا ، يقوم بإنشاء وإلحاق خلية واحدة **خلية** .

```csharp
public void EnsureMinimum()
```

### أمثلة

يوضح كيفية التأكد من احتواء عقدة الصف على العقد التي نحتاجها لبدء إضافة محتوى إليها.

```csharp
Document doc = new Document();
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
Row row = new Row(doc);
table.AppendChild(row);

// تحتوي الصفوف على خلايا تحتوي على فقرات تحتوي على عناصر نموذجية مثل عمليات التشغيل والأشكال وحتى الجداول الأخرى.
// لا يحتوي صفنا الجديد على أي من هذه العقد ، ولا يمكننا إضافة محتويات إليه حتى يحدث ذلك.
Assert.AreEqual(0, row.GetChildNodes(NodeType.Any, true).Count);

// استدعاء طريقة "ضمان الحد الأدنى" على الطاولة سيضمن ذلك
// يحتوي الجدول على خلية واحدة على الأقل بها فقرة فارغة.
row.EnsureMinimum();
row.FirstCell.FirstParagraph.AppendChild(new Run(doc, "Hello world!"));
```

### أنظر أيضا

* class [Row](../)
* مساحة الاسم [Aspose.Words.Tables](../../row/)
* المجسم [Aspose.Words](../../../)


