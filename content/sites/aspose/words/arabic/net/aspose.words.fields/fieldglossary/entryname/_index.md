---
title: FieldGlossary.EntryName
second_title: Aspose.Words لمراجع .NET API
description: FieldGlossary ملكية. الحصول على أو تحديد اسم إدخال المسرد لإدراجه .
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldglossary/entryname/
---
## FieldGlossary.EntryName property

الحصول على أو تحديد اسم إدخال المسرد لإدراجه .

```csharp
public string EntryName { get; set; }
```

### أمثلة

يوضح كيفية عرض الكتلة البرمجية الإنشائية باستخدام حقلي AUTOTEXT ومسرد المصطلحات.

```csharp
Document doc = new Document();

// قم بإنشاء مستند قاموس المصطلحات وأضف كتلة إنشاء نص تلقائي إليه.
doc.GlossaryDocument = new GlossaryDocument();
BuildingBlock buildingBlock = new BuildingBlock(doc.GlossaryDocument);
buildingBlock.Name = "MyBlock";
buildingBlock.Gallery = BuildingBlockGallery.AutoText;
buildingBlock.Category = "General";
buildingBlock.Description = "MyBlock description";
buildingBlock.Behavior = BuildingBlockBehavior.Paragraph;
doc.GlossaryDocument.AppendChild(buildingBlock);

// أنشئ مصدرًا وأضفه كنص إلى لبنة البناء لدينا.
Document buildingBlockSource = new Document();
DocumentBuilder buildingBlockSourceBuilder = new DocumentBuilder(buildingBlockSource);
buildingBlockSourceBuilder.Writeln("Hello World!");

Node buildingBlockContent = doc.GlossaryDocument.ImportNode(buildingBlockSource.FirstSection, true);
buildingBlock.AppendChild(buildingBlockContent);

// تعيين ملف يحتوي على أجزاء قد لا تحتوي وثيقتنا أو النموذج المرفق بها.
doc.FieldOptions.BuiltInTemplatesPaths = new[] { MyDir + "Busniess brochure.dotx" };

DocumentBuilder builder = new DocumentBuilder(doc);

// فيما يلي طريقتان لاستخدام الحقول لعرض محتويات الكتلة البرمجية الإنشائية الخاصة بنا.
// 1 - استخدام حقل AUTOTEXT:
FieldAutoText fieldAutoText = (FieldAutoText)builder.InsertField(FieldType.FieldAutoText, true);
fieldAutoText.EntryName = "MyBlock";

Assert.AreEqual(" AUTOTEXT  MyBlock", fieldAutoText.GetFieldCode());

// 2 - استخدام حقل مسرد المصطلحات:
FieldGlossary fieldGlossary = (FieldGlossary)builder.InsertField(FieldType.FieldGlossary, true);
fieldGlossary.EntryName = "MyBlock";

Assert.AreEqual(" GLOSSARY  MyBlock", fieldGlossary.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.AUTOTEXT.GLOSSARY.dotx");
```

### أنظر أيضا

* class [FieldGlossary](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldglossary/)
* المجسم [Aspose.Words](../../../)


