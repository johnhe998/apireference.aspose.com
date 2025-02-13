---
title: Table.Alignment
second_title: Aspose.Words لمراجع .NET API
description: Table ملكية. يحدد كيفية محاذاة الجدول المضمن في المستند.
type: docs
weight: 40
url: /ar/net/aspose.words.tables/table/alignment/
---
## Table.Alignment property

يحدد كيفية محاذاة الجدول المضمن في المستند.

```csharp
public TableAlignment Alignment { get; set; }
```

### ملاحظات

النظام الأساسيLeft.

### أمثلة

يوضح كيفية تطبيق حد مخطط تفصيلي على جدول.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// محاذاة الجدول إلى وسط الصفحة.
table.Alignment = TableAlignment.Center;

// امسح أي حدود وتظليل موجود من الجدول.
table.ClearBorders();
table.ClearShading();

// أضف حدودًا خضراء إلى مخطط الجدول.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// املأ الخلايا بلون أخضر فاتح.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

### أنظر أيضا

* enum [TableAlignment](../../tablealignment/)
* class [Table](../)
* مساحة الاسم [Aspose.Words.Tables](../../table/)
* المجسم [Aspose.Words](../../../)


