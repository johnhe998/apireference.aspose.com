---
title: صورة
linktitle: صورة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج الصورة وتخصيصها باستخدام دليل Aspose.Words for .NET خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-markdown/image/
---

في هذا المثال ، سنشرح كيفية استخدام ميزة الصورة مع Aspose.Words for .NET. تسمح لك الصور بإدراج الرسوم التوضيحية والرسومات في المستند.

## الخطوة 1: استخدام منشئ المستندات

أولاً ، سنستخدم منشئ المستندات لإضافة محتوى إلى وثيقتنا.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## الخطوة الثانية: إدخال صورة

 يمكننا إدراج صورة باستخدام ملف`Shape` فئة وتحديد نوع الصورة هنا`ShapeType.Image` . قمنا أيضًا بتعيين نوع التفاف الصورة على`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## الخطوة 3: تخصيص الصورة

 نقوم بتخصيص الصورة من خلال تحديد مسارها الكامل ، على سبيل المثال`"/attachment/1456/pic001.png"`وإضافة عنوان للصورة.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### مثال على شفرة المصدر للصور باستخدام Aspose.Words for .NET

```csharp
// استخدم منشئ المستندات لإضافة محتوى إلى المستند.
DocumentBuilder builder = new DocumentBuilder();

// إدراج صورة.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

تهنئة ! لقد تعلمت الآن كيفية استخدام ميزة الصور مع Aspose.Words for .NET.


### التعليمات

#### س: كيف يمكنني إدراج صورة من ملف محلي في Aspose.Words؟

 ج: لإدراج صورة من ملف محلي في Aspose.Words ، يمكنك استخدام ملحق`Shape` الطبقة و`InsertImage` طريقة.

#### س: هل يمكنني إدراج صورة من عنوان URL في Aspose.Words؟

 ج: نعم ، يمكنك إدراج صورة من عنوان URL في Aspose.Words. يمكنك استخدام نفس الشيء`InsertImage`الطريقة وحدد عنوان URL للصورة بدلاً من مسار الملف المحلي.

#### س: كيف يمكنني تغيير حجم الصورة في Aspose.Words؟

 ج: لتغيير حجم الصورة في Aspose.Words ، يمكنك استخدام`Width` و`Height` خصائص`Shape` هدف.

#### س: هل يمكنني تطبيق المرشحات على الصور في Aspose.Words؟

 ج: نعم ، يمكنك تطبيق المرشحات على الصور في Aspose.Words. على سبيل المثال ، يمكنك تطبيق مرشح تمويه على صورة باستخدام امتداد`ApplyGaussianBlur` طريقة`Shape` هدف.

#### س: كيف يمكنني استبدال صورة بأخرى في Aspose.Words؟

 ج: لاستبدال صورة بأخرى في Aspose.Words ، يمكنك استخدام`Replace` طريقة`Shape` فصل. تأخذ هذه الطريقة كمعامل`Shape` موضوع الصورة المراد استبدالها و`Shape` موضوع الصورة الجديدة.