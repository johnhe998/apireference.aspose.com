---
title: FieldDate.UseLastFormat
second_title: Aspose.Words لمراجع .NET API
description: FieldDate ملكية. الحصول على أو تحديد ما إذا كان سيتم استخدام تنسيق تم استخدامه مؤخرًا بواسطة تطبيق الاستضافة عند إدراج حقل DATE جديد.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fielddate/uselastformat/
---
## FieldDate.UseLastFormat property

الحصول على أو تحديد ما إذا كان سيتم استخدام تنسيق تم استخدامه مؤخرًا بواسطة تطبيق الاستضافة عند إدراج حقل DATE جديد.

```csharp
public bool UseLastFormat { get; set; }
```

### أمثلة

يوضح كيفية استخدام حقول التاريخ لعرض التواريخ وفقًا لأنواع التقويمات المختلفة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إذا أردنا دائمًا أن يعرض النص الموجود في المستند التاريخ الصحيح ، فيمكننا استخدام حقل التاريخ.
// فيما يلي ثلاثة أنواع من التقاويم الثقافية التي يمكن أن يستخدمها حقل التاريخ لعرض التاريخ.
// 1 - التقويم القمري الإسلامي:
FieldDate field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseLunarCalendar = true;
Assert.AreEqual(" DATE  \\h", field.GetFieldCode());
builder.Writeln();

// 2 - تقويم أم القرى:
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseUmAlQuraCalendar = true;
Assert.AreEqual(" DATE  \\u", field.GetFieldCode());
builder.Writeln();

// 3 - التقويم الوطني الهندي:
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseSakaEraCalendar = true;
Assert.AreEqual(" DATE  \\s", field.GetFieldCode());
builder.Writeln();

// أدخل حقل التاريخ وقم بتعيين نوع التقويم الخاص به على آخر نوع استخدمه التطبيق المضيف.
// في Microsoft Word ، سيكون النوع هو الأحدث استخدامًا في Insert - > نص - >. مربع حوار التاريخ والوقت.
field = (FieldDate)builder.InsertField(FieldType.FieldDate, true);
field.UseLastFormat = true;
Assert.AreEqual(" DATE  \\l", field.GetFieldCode());
builder.Writeln();

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.DATE.docx");
```

### أنظر أيضا

* class [FieldDate](../)
* مساحة الاسم [Aspose.Words.Fields](../../fielddate/)
* المجسم [Aspose.Words](../../../)


