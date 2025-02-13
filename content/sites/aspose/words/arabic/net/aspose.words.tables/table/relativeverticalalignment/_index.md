---
title: Table.RelativeVerticalAlignment
second_title: Aspose.Words لمراجع .NET API
description: Table ملكية. الحصول على أو تعيين المحاذاة الرأسية النسبية للجدول العائم.
type: docs
weight: 240
url: /ar/net/aspose.words.tables/table/relativeverticalalignment/
---
## Table.RelativeVerticalAlignment property

الحصول على أو تعيين المحاذاة الرأسية النسبية للجدول العائم.

```csharp
public VerticalAlignment RelativeVerticalAlignment { get; set; }
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

* enum [VerticalAlignment](../../../aspose.words.drawing/verticalalignment/)
* class [Table](../)
* مساحة الاسم [Aspose.Words.Tables](../../table/)
* المجسم [Aspose.Words](../../../)


