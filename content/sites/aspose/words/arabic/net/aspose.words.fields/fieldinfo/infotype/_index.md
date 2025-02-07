---
title: FieldInfo.InfoType
second_title: Aspose.Words لمراجع .NET API
description: FieldInfo ملكية. الحصول على أو تحديد نوع خاصية المستند المراد إدراجها .
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldinfo/infotype/
---
## FieldInfo.InfoType property

الحصول على أو تحديد نوع خاصية المستند المراد إدراجها .

```csharp
public string InfoType { get; set; }
```

### أمثلة

يوضح كيفية العمل مع حقول INFO.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بتعيين قيمة للخاصية المضمنة "التعليقات" ثم أدخل حقل INFO لعرض قيمة هذه الخاصية.
doc.BuiltInDocumentProperties.Comments = "My comment";
FieldInfo field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.Update();

Assert.AreEqual(" INFO  Comments", field.GetFieldCode());
Assert.AreEqual("My comment", field.Result);

builder.Writeln();

// تعيين قيمة لخاصية NewValue للحقل وتحديثها
// سيقوم الحقل أيضًا بالكتابة فوق الخاصية المضمنة المقابلة بالقيمة الجديدة.
field = (FieldInfo)builder.InsertField(FieldType.FieldInfo, true);
field.InfoType = "Comments";
field.NewValue = "New comment";
field.Update();

Assert.AreEqual(" INFO  Comments \"New comment\"", field.GetFieldCode());
Assert.AreEqual("New comment", field.Result);
Assert.AreEqual("New comment", doc.BuiltInDocumentProperties.Comments);

doc.Save(ArtifactsDir + "Field.INFO.docx");
```

### أنظر أيضا

* class [FieldInfo](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldinfo/)
* المجسم [Aspose.Words](../../../)


