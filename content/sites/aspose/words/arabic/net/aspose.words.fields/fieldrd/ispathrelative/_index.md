---
title: FieldRD.IsPathRelative
second_title: Aspose.Words لمراجع .NET API
description: FieldRD ملكية. الحصول على أو تحديد ما إذا كان المسار متعلقًا بالمستند الحالي.
type: docs
weight: 30
url: /ar/net/aspose.words.fields/fieldrd/ispathrelative/
---
## FieldRD.IsPathRelative property

الحصول على أو تحديد ما إذا كان المسار متعلقًا بالمستند الحالي.

```csharp
public bool IsPathRelative { get; set; }
```

### أمثلة

يظهر استخدام حقل RD لإنشاء مدخلات جدول محتويات من عناوين في مستندات أخرى.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// استخدم منشئ المستندات لإدراج جدول محتويات ،
// ثم قم بإضافة إدخال واحد لجدول المحتويات في الصفحة التالية.
builder.InsertField(FieldType.FieldTOC, true);
builder.InsertBreak(BreakType.PageBreak);
builder.CurrentParagraph.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("TOC entry from within this document");

// أدخل حقل RD ، والذي يشير إلى مستند نظام ملفات محلي آخر في خاصية FileName الخاصة به.
// سيقبل جدول المحتويات أيضًا جميع العناوين من المستند المرجعي كمدخلات لجدوله.
FieldRD field = (FieldRD)builder.InsertField(FieldType.FieldRefDoc, true);
field.FileName = "ReferencedDocument.docx";
field.IsPathRelative = true;

Assert.AreEqual(" RD  ReferencedDocument.docx \\f", field.GetFieldCode());

 // قم بإنشاء المستند الذي يشير إليه حقل RD وأدخل عنوانًا.
// سيظهر هذا العنوان كإدخال في حقل جدول المحتويات في مستندنا الأول.
Document referencedDoc = new Document();
DocumentBuilder refDocBuilder = new DocumentBuilder(referencedDoc);
refDocBuilder.CurrentParagraph.ParagraphFormat.StyleName = "Heading 1";
refDocBuilder.Writeln("TOC entry from referenced document");
referencedDoc.Save(ArtifactsDir + "ReferencedDocument.docx");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.RD.docx");
```

### أنظر أيضا

* class [FieldRD](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldrd/)
* المجسم [Aspose.Words](../../../)


