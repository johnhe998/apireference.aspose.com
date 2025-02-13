---
title: ShapeBase.AllowOverlap
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. الحصول على أو تعيين قيمة تحدد ما إذا كان هذا الشكل يمكن أن يتداخل مع الأشكال الأخرى.
type: docs
weight: 10
url: /ar/net/aspose.words.drawing/shapebase/allowoverlap/
---
## ShapeBase.AllowOverlap property

الحصول على أو تعيين قيمة تحدد ما إذا كان هذا الشكل يمكن أن يتداخل مع الأشكال الأخرى.

```csharp
public bool AllowOverlap { get; set; }
```

### ملاحظات

تؤثر هذه الخاصية على سلوك الشكل في Microsoft Word. Aspose.Words يتجاهل قيمة هذه الخاصية.

هذه الخاصية قابلة للتطبيق فقط لأشكال المستوى الأعلى.

النظام الأساسي **حقيقي**.

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

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


