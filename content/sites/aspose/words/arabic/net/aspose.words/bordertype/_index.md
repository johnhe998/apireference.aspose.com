---
title: Enum BorderType
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.BorderType تعداد. تحديد جوانب الحد .
type: docs
weight: 90
url: /ar/net/aspose.words/bordertype/
---
## BorderType enumeration

تحديد جوانب الحد .

```csharp
public enum BorderType
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `-1` | القيمة الافتراضية . |
| Bottom | `0` | تحديد الحد السفلي للفقرة أو خلية الجدول. |
| Left | `1` | تحديد الحد الأيسر للفقرة أو خلية الجدول. |
| Right | `2` | تحديد الحد الأيمن للفقرة أو خلية الجدول. |
| Top | `3` | تحديد الحد العلوي للفقرة أو خلية الجدول. |
| Horizontal | `4` | تحديد الحد الأفقي بين الخلايا في جدول أو بين الفقرات المتوافقة. |
| Vertical | `5` | تحديد الحد الرأسي بين الخلايا في جدول . |
| DiagonalDown | `6` | يحدد الحد القطري في خلية جدول. |
| DiagonalUp | `7` | يحدد الحد القطري في خلية جدول. |

### أمثلة

يوضح كيفية إدراج فقرة بحد علوي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


