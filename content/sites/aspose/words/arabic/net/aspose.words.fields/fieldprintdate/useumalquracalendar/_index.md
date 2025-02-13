---
title: FieldPrintDate.UseUmAlQuraCalendar
second_title: Aspose.Words لمراجع .NET API
description: FieldPrintDate ملكية. الحصول على أو تحديد ما إذا كان سيتم استخدام تقويم أم القرى.
type: docs
weight: 40
url: /ar/net/aspose.words.fields/fieldprintdate/useumalquracalendar/
---
## FieldPrintDate.UseUmAlQuraCalendar property

الحصول على أو تحديد ما إذا كان سيتم استخدام تقويم أم القرى.

```csharp
public bool UseUmAlQuraCalendar { get; set; }
```

### أمثلة

يظهر قراءة حقول PRINTDATE.

```csharp
Document doc = new Document(MyDir + "Field sample - PRINTDATE.docx");

// عند طباعة مستند بواسطة طابعة أو طباعته كملف PDF (لكن لا يتم تصديره إلى PDF) ،
// ستعرض حقول PRINTDATE تاريخ / وقت عملية الطباعة.
// في حالة عدم إجراء طباعة ، ستعرض هذه الحقول "0/0/0000".
FieldPrintDate field = (FieldPrintDate)doc.Range.Fields[0];

Assert.AreEqual("3/25/2020 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE ", field.GetFieldCode());

// فيما يلي ثلاثة أنواع تقويم مختلفة وفقًا لحقل PRINTDATE
// يمكنه عرض تاريخ ووقت آخر عملية طباعة.
// 1 - التقويم القمري الإسلامي:
field = (FieldPrintDate)doc.Range.Fields[1];

Assert.True(field.UseLunarCalendar);
Assert.AreEqual("8/1/1441 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\h", field.GetFieldCode());

field = (FieldPrintDate)doc.Range.Fields[2];

// 2 - تقويم أم القرى:
Assert.True(field.UseUmAlQuraCalendar);
Assert.AreEqual("8/1/1441 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\u", field.GetFieldCode());

field = (FieldPrintDate)doc.Range.Fields[3];

// 3 - التقويم الوطني الهندي:
Assert.True(field.UseSakaEraCalendar);
Assert.AreEqual("1/5/1942 12:00:00 AM", field.Result);
Assert.AreEqual(" PRINTDATE  \\s", field.GetFieldCode());
```

### أنظر أيضا

* class [FieldPrintDate](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldprintdate/)
* المجسم [Aspose.Words](../../../)


