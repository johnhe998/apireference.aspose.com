---
title: FieldAdvance.RightOffset
second_title: Aspose.Words لمراجع .NET API
description: FieldAdvance ملكية. الحصول على أو تحديد عدد النقاط التي يجب نقل النص الذي يتبع الحقل إلى اليمين .
type: docs
weight: 50
url: /ar/net/aspose.words.fields/fieldadvance/rightoffset/
---
## FieldAdvance.RightOffset property

الحصول على أو تحديد عدد النقاط التي يجب نقل النص الذي يتبع الحقل إلى اليمين .

```csharp
public string RightOffset { get; set; }
```

### أمثلة

يوضح كيفية إدراج حقل ADVANCE وتحرير خصائصه.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("This text is in its normal place.");

// فيما يلي طريقتان لاستخدام حقل ADVANCE لضبط موضع النص الذي يليه.
// يستمر تطبيق تأثيرات حقل ADVANCE حتى تنتهي الفقرة ،
// أو يقوم حقل ADVANCE آخر بتحديث قيم الإزاحة / الإحداثيات.
// 1 - حدد إزاحة اتجاهية:
FieldAdvance field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.RightOffset = "5";
field.UpOffset = "5";

Assert.AreEqual(" ADVANCE  \\r 5 \\u 5", field.GetFieldCode());

builder.Write("This text will be moved up and to the right.");

field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.DownOffset = "5";
field.LeftOffset = "100";

Assert.AreEqual(" ADVANCE  \\d 5 \\l 100", field.GetFieldCode());

builder.Writeln("This text is moved down and to the left, overlapping the previous text.");

// 2 - نقل النص إلى الموضع المحدد بالإحداثيات:
field = (FieldAdvance)builder.InsertField(FieldType.FieldAdvance, true);
field.HorizontalPosition = "-100";
field.VerticalPosition = "200";

Assert.AreEqual(" ADVANCE  \\x -100 \\y 200", field.GetFieldCode());

builder.Write("This text is in a custom position.");

doc.Save(ArtifactsDir + "Field.ADVANCE.docx");
```

### أنظر أيضا

* class [FieldAdvance](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldadvance/)
* المجسم [Aspose.Words](../../../)


