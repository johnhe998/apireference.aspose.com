---
title: Table.AllowOverlap
second_title: Aspose.Words لمراجع .NET API
description: Table ملكية. التعرف على ما إذا كان الجدول العائم سيسمح للكائنات العائمة الأخرى في document بتداخل نطاقاتها عند عرضها. القيمة الافتراضية هيحقيقي .
type: docs
weight: 70
url: /ar/net/aspose.words.tables/table/allowoverlap/
---
## Table.AllowOverlap property

التعرف على ما إذا كان الجدول العائم سيسمح للكائنات العائمة الأخرى في document بتداخل نطاقاتها عند عرضها. القيمة الافتراضية هي`حقيقي` .

```csharp
public bool AllowOverlap { get; }
```

### أمثلة

يوضح كيفية استخدام خصائص الجداول العائمة.

```csharp
Document doc = new Document(MyDir + "Table wrapped by text.docx");

Table table = doc.FirstSection.Body.Tables[0];

if (table.TextWrapping == TextWrapping.Around)
{
    Assert.AreEqual(RelativeHorizontalPosition.Margin, table.HorizontalAnchor);
    Assert.AreEqual(RelativeVerticalPosition.Paragraph, table.VerticalAnchor);
    Assert.AreEqual(false, table.AllowOverlap);

    // فقط الهامش والصفحة والعمود متاحان في RelativeHorizontalPosition for HorizontalAnchor setter.
    // سيتم طرح ArgumentException لأية قيم أخرى.
    table.HorizontalAnchor = RelativeHorizontalPosition.Column;

    // فقط الهامش والصفحة والفقرة المتوفرة في RelativeVerticalPosition لـ VerticalAnchor setter.
    // سيتم طرح ArgumentException لأية قيم أخرى.
    table.VerticalAnchor = RelativeVerticalPosition.Page;
}
```

### أنظر أيضا

* class [Table](../)
* مساحة الاسم [Aspose.Words.Tables](../../table/)
* المجسم [Aspose.Words](../../../)


