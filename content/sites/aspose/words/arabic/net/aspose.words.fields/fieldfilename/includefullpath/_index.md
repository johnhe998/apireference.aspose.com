---
title: FieldFileName.IncludeFullPath
second_title: Aspose.Words لمراجع .NET API
description: FieldFileName ملكية. يحصل أو يحدد ما إذا كان سيتم تضمين اسم مسار الملف الكامل.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldfilename/includefullpath/
---
## FieldFileName.IncludeFullPath property

يحصل أو يحدد ما إذا كان سيتم تضمين اسم مسار الملف الكامل.

```csharp
public bool IncludeFullPath { get; set; }
```

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

* class [FieldFileName](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldfilename/)
* المجسم [Aspose.Words](../../../)


