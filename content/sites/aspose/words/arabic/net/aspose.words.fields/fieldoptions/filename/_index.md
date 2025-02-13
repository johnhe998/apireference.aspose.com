---
title: FieldOptions.FileName
second_title: Aspose.Words لمراجع .NET API
description: FieldOptions ملكية. الحصول على أو تحديد اسم ملف المستند.
type: docs
weight: 120
url: /ar/net/aspose.words.fields/fieldoptions/filename/
---
## FieldOptions.FileName property

الحصول على أو تحديد اسم ملف المستند.

```csharp
public string FileName { get; set; }
```

### ملاحظات

يتم استخدام هذه الخاصية من قبل[`FieldFileName`](../../fieldfilename/) ذات أولوية أعلى من[`OriginalFileName`](../../../aspose.words/document/originalfilename/) منشأه.

### أمثلة

يوضح كيفية استخدام FieldOptions لتجاوز القيمة الافتراضية لحقل FILENAME.

```csharp
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToDocumentEnd();
builder.Writeln();

// سيعرض حقل FILENAME هذا اسم ملف النظام المحلي للمستند الذي قمنا بتحميله.
FieldFileName field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.Update();

Assert.AreEqual(" FILENAME ", field.GetFieldCode());
Assert.AreEqual("Document.docx", field.Result);

builder.Writeln();

// بشكل افتراضي ، يعرض حقل FILENAME اسم الملف ، ولكن ليس مسار نظام الملفات المحلي الكامل الخاص به.
// يمكننا تعيين علامة لجعلها تظهر مسار الملف الكامل.
field = (FieldFileName)builder.InsertField(FieldType.FieldFileName, true);
field.IncludeFullPath = true;
field.Update();

Assert.AreEqual(MyDir + "Document.docx", field.Result);

// يمكننا أيضًا تعيين قيمة لهذه الخاصية إلى
// تجاوز القيمة التي يعرضها حقل FILENAME.
doc.FieldOptions.FileName = "FieldOptions.FILENAME.docx";
field.Update();

Assert.AreEqual(" FILENAME  \\p", field.GetFieldCode());
Assert.AreEqual("FieldOptions.FILENAME.docx", field.Result);

doc.UpdateFields();
doc.Save(ArtifactsDir + doc.FieldOptions.FileName);
```

### أنظر أيضا

* class [FieldOptions](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldoptions/)
* المجسم [Aspose.Words](../../../)


