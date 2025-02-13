---
title: FieldFileSize.IsInKilobytes
second_title: Aspose.Words لمراجع .NET API
description: FieldFileSize ملكية. الحصول على أو تحديد ما إذا كان سيتم عرض حجم الملف بالكيلو بايت.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldfilesize/isinkilobytes/
---
## FieldFileSize.IsInKilobytes property

الحصول على أو تحديد ما إذا كان سيتم عرض حجم الملف بالكيلو بايت.

```csharp
public bool IsInKilobytes { get; set; }
```

### أمثلة

يوضح كيفية عرض حجم ملف مستند مع حقل FILESIZE.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(18105, doc.BuiltInDocumentProperties.Bytes);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.InsertParagraph();

// فيما يلي ثلاث وحدات قياس مختلفة
// التي يمكن أن تعرض بها حقول FILESIZE حجم ملف المستند.
// 1 - بايت:
FieldFileSize field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.Update();

Assert.AreEqual(" FILESIZE ", field.GetFieldCode());
Assert.AreEqual("18105", field.Result);

// 2 - كيلو بايت:
builder.InsertParagraph();
field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.IsInKilobytes = true;
field.Update();

Assert.AreEqual(" FILESIZE  \\k", field.GetFieldCode());
Assert.AreEqual("18", field.Result);

// 3 - ميغا بايت:
builder.InsertParagraph();
field = (FieldFileSize)builder.InsertField(FieldType.FieldFileSize, true);
field.IsInMegabytes = true;
field.Update();

Assert.AreEqual(" FILESIZE  \\m", field.GetFieldCode());
Assert.AreEqual("0", field.Result);

// لتحديث قيم هذه الحقول أثناء التحرير في Microsoft Word ،
// يجب أولاً حفظ التغييرات ، ثم تحديث هذه الحقول يدويًا.
doc.Save(ArtifactsDir + "Field.FILESIZE.docx");
```

### أنظر أيضا

* class [FieldFileSize](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldfilesize/)
* المجسم [Aspose.Words](../../../)


