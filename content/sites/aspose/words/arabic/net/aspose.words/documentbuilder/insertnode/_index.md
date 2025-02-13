---
title: DocumentBuilder.InsertNode
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. إدراج عقدة على مستوى النص داخل الفقرة الحالية قبل المؤشر.
type: docs
weight: 360
url: /ar/net/aspose.words/documentbuilder/insertnode/
---
## DocumentBuilder.InsertNode method

إدراج عقدة على مستوى النص داخل الفقرة الحالية قبل المؤشر.

```csharp
public void InsertNode(Node node)
```

### أمثلة

يوضح كيفية إدراج صورة مرتبطة في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string imageFileName = ImageDir + "Windows MetaFile.wmf";

// فيما يلي طريقتان لتطبيق صورة على شكل بحيث يمكن عرضها.
// 1 - اضبط الشكل ليحتوي على الصورة.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SetImage(imageFileName);

builder.InsertNode(shape);

doc.Save(ArtifactsDir + "Image.CreateLinkedImage.Embedded.docx");

// كل صورة نقوم بتخزينها بالشكل ستزيد من حجم وثيقتنا.
Assert.True(70000 < new FileInfo(ArtifactsDir + "Image.CreateLinkedImage.Embedded.docx").Length);

doc.FirstSection.Body.FirstParagraph.RemoveAllChildren();

// 2 - اضبط الشكل للارتباط بملف صورة في نظام الملفات المحلي.
shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = imageFileName;

builder.InsertNode(shape);
doc.Save(ArtifactsDir + "Image.CreateLinkedImage.Linked.docx");

// سيوفر الارتباط بالصور مساحة وينتج عنه مستند أصغر.
// ومع ذلك ، يمكن للمستند فقط عرض الصورة بشكل صحيح أثناء
// ملف الصورة موجود في الموقع الذي تشير إليه خاصية "SourceFullName" للشكل.
Assert.True(10000 > new FileInfo(ArtifactsDir + "Image.CreateLinkedImage.Linked.docx").Length);
```

### أنظر أيضا

* class [Node](../../node/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


