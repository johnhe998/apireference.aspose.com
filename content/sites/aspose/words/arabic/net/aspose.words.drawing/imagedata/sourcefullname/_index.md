---
title: ImageData.SourceFullName
second_title: Aspose.Words لمراجع .NET API
description: ImageData ملكية. الحصول على أو تحديد مسار واسم الملف المصدر للصورة المرتبطة.
type: docs
weight: 170
url: /ar/net/aspose.words.drawing/imagedata/sourcefullname/
---
## ImageData.SourceFullName property

الحصول على أو تحديد مسار واسم الملف المصدر للصورة المرتبطة.

```csharp
public string SourceFullName { get; set; }
```

### ملاحظات

القيمة الافتراضية هي سلسلة فارغة.

إذا`SourceFullName` ليست سلسلة فارغة ، الصورة مرتبطة.

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

* class [ImageData](../)
* مساحة الاسم [Aspose.Words.Drawing](../../imagedata/)
* المجسم [Aspose.Words](../../../)


