---
title: Table.DistanceBottom
second_title: Aspose.Words لمراجع .NET API
description: Table ملكية. تحصل على المسافة بين أسفل الجدول والنص المحيط بالنقاط .
type: docs
weight: 120
url: /ar/net/aspose.words.tables/table/distancebottom/
---
## Table.DistanceBottom property

تحصل على المسافة بين أسفل الجدول والنص المحيط بالنقاط .

```csharp
public double DistanceBottom { get; }
```

### أمثلة

يظهر الحد الأدنى من عمليات المسافة بين حدود الجدول والنص.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

Assert.AreEqual(25.9d, table.DistanceTop);
Assert.AreEqual(25.9d, table.DistanceBottom);
Assert.AreEqual(17.3d, table.DistanceLeft);
Assert.AreEqual(17.3d, table.DistanceRight);
```

### أنظر أيضا

* class [Table](../)
* مساحة الاسم [Aspose.Words.Tables](../../table/)
* المجسم [Aspose.Words](../../../)


