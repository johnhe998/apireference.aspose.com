---
title: FieldDocVariable.VariableName
second_title: Aspose.Words لمراجع .NET API
description: FieldDocVariable ملكية. الحصول على أو تحديد اسم متغير المستند المطلوب استرداده.
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fielddocvariable/variablename/
---
## FieldDocVariable.VariableName property

الحصول على أو تحديد اسم متغير المستند المطلوب استرداده.

```csharp
public string VariableName { get; set; }
```

### أمثلة

يوضح كيفية استخدام حقول DOCPROPERTY لعرض خصائص المستند ومتغيراته.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// فيما يلي طريقتان لاستخدام حقول DOCPROPERTY.
// 1 - عرض خاصية مضمنة:
// قم بتعيين قيمة مخصصة للخاصية المضمنة في "الفئة" ، ثم أدخل حقل DOCPROPERTY الذي يشير إليها.
doc.BuiltInDocumentProperties.Category = "My category";

FieldDocProperty fieldDocProperty = (FieldDocProperty)builder.InsertField(" DOCPROPERTY Category ");
fieldDocProperty.Update();

Assert.AreEqual(" DOCPROPERTY Category ", fieldDocProperty.GetFieldCode());
Assert.AreEqual("My category", fieldDocProperty.Result);

builder.InsertParagraph();

// 2 - عرض متغير مستند مخصص:
// حدد متغيرًا مخصصًا ، ثم قم بالإشارة إلى هذا المتغير باستخدام حقل DOCPROPERTY.
Assert.That(doc.Variables, Is.Empty);
doc.Variables.Add("My variable", "My variable's value");

FieldDocVariable fieldDocVariable = (FieldDocVariable)builder.InsertField(FieldType.FieldDocVariable, true);
fieldDocVariable.VariableName = "My Variable";
fieldDocVariable.Update();

Assert.AreEqual(" DOCVARIABLE  \"My Variable\"", fieldDocVariable.GetFieldCode());
Assert.AreEqual("My variable's value", fieldDocVariable.Result);

doc.Save(ArtifactsDir + "Field.DOCPROPERTY.DOCVARIABLE.docx");
```

### أنظر أيضا

* class [FieldDocVariable](../)
* مساحة الاسم [Aspose.Words.Fields](../../fielddocvariable/)
* المجسم [Aspose.Words](../../../)


