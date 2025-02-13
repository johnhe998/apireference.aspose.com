---
title: Enum TableAlignment
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Tables.TableAlignment تعداد. تحديد محاذاة لجدول مضمن .
type: docs
weight: 6050
url: /ar/net/aspose.words.tables/tablealignment/
---
## TableAlignment enumeration

تحديد محاذاة لجدول مضمن .

```csharp
public enum TableAlignment
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Left | `0` | الجدول محاذي لليسار . |
| Center | `1` | يتم توسيط الجدول . |
| Right | `2` | يتم محاذاة الجدول إلى اليمين. |

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

* مساحة الاسم [Aspose.Words.Tables](../../aspose.words.tables/)
* المجسم [Aspose.Words](../../)


