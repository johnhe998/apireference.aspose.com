---
title: Table.AbsoluteVerticalDistance
second_title: Aspose.Words لمراجع .NET API
description: Table ملكية. الحصول على أو تعيين موضع الجدول العائم العمودي المطلق المحدد بواسطة خصائص الجدول  بالنقاط . القيمة الافتراضية هي 0.
type: docs
weight: 30
url: /ar/net/aspose.words.tables/table/absoluteverticaldistance/
---
## Table.AbsoluteVerticalDistance property

الحصول على أو تعيين موضع الجدول العائم العمودي المطلق المحدد بواسطة خصائص الجدول ، بالنقاط . القيمة الافتراضية هي 0.

```csharp
public double AbsoluteVerticalDistance { get; set; }
```

### أمثلة

يوضح كيفية تعيين موقع الجداول العائمة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 1, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// اضبط موقع الجدول على مكان ما على الصفحة ، مثل ، في هذه الحالة ، الركن الأيمن السفلي.
table.RelativeVerticalAlignment = VerticalAlignment.Bottom;
table.RelativeHorizontalAlignment = HorizontalAlignment.Right;

table = builder.StartTable();
builder.InsertCell();
builder.Write("Table 2, cell 1");
builder.EndTable();
table.PreferredWidth = PreferredWidth.FromPoints(300);

// يمكننا أيضًا تعيين إزاحة أفقية ورأسية في نقاط من موقع الفقرة حيث أدخلنا الجدول. 
table.AbsoluteVerticalDistance = 50;
table.AbsoluteHorizontalDistance = 100;

doc.Save(ArtifactsDir + "Table.ChangeFloatingTableProperties.docx");
```

### أنظر أيضا

* class [Table](../)
* مساحة الاسم [Aspose.Words.Tables](../../table/)
* المجسم [Aspose.Words](../../../)


