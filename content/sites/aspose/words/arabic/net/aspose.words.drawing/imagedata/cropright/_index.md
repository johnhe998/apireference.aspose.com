---
title: ImageData.CropRight
second_title: Aspose.Words لمراجع .NET API
description: ImageData ملكية. يحدد جزء إزالة الصورة من الجانب الأيمن.
type: docs
weight: 80
url: /ar/net/aspose.words.drawing/imagedata/cropright/
---
## ImageData.CropRight property

يحدد جزء إزالة الصورة من الجانب الأيمن.

```csharp
public double CropRight { get; set; }
```

### ملاحظات

يمكن أن تتراوح كمية الاقتصاص من -1.0 إلى 1.0. القيمة الافتراضية هي 0. لاحظ أن القيمة 1 لن تعرض أي صورة على الإطلاق. ستؤدي القيم السالبة إلى ضغط الصورة للداخل من الحافة التي يتم اقتصاصها (سيتم ملء المساحة الفارغة بين الصورة والحافة المقصوصة بلون التعبئة للشكل ). القيم الموجبة الأقل من 1 ستؤدي إلى تمديد الصورة المتبقية لتلائم الشكل.

القيمة الافتراضية هي 0.

### أمثلة

يوضح كيفية تحرير بيانات صورة الشكل.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");
Shape sourceShape = (Shape)imgSourceDoc.GetChildNodes(NodeType.Shape, true)[0];

Document dstDoc = new Document();

// استيراد شكل من المستند المصدر وإلحاقه بالفقرة الأولى.
Shape importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

// يحتوي الشكل المستورد على صورة. يمكننا الوصول إلى خصائص الصورة والبيانات الأولية عبر كائن ImageData.
ImageData imageData = importedShape.ImageData;
imageData.Title = "Imported Image";

Assert.True(imageData.HasImage);

// إذا كانت الصورة بلا حدود ، فسيقوم كائن ImageData بتعريف لون الحدود على أنه فارغ.
Assert.AreEqual(4, imageData.Borders.Count);
Assert.AreEqual(Color.Empty, imageData.Borders[0].Color);

// لا ترتبط هذه الصورة بشكل أو ملف صورة آخر في نظام الملفات المحلي.
Assert.False(imageData.IsLink);
Assert.False(imageData.IsLinkOnly);

// تحدد خصائص "السطوع" و "التباين" سطوع الصورة والتباين
// على مقياس 0-1 ، مع القيمة الافتراضية 0.5.
imageData.Brightness = 0.8;
imageData.Contrast = 1.0;

// لقد خلقت قيم السطوع والتباين أعلاه صورة بها الكثير من اللون الأبيض.
// يمكننا تحديد لون بخاصية ChromaKey لاستبداله بالشفافية ، مثل الأبيض.
imageData.ChromaKey = Color.White;

// قم باستيراد شكل المصدر مرة أخرى واضبط الصورة على أحادية اللون.
importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

importedShape.ImageData.GrayScale = true;

// قم باستيراد الشكل المصدر مرة أخرى لإنشاء صورة ثالثة وضبطها على BiLevel.
// يقوم BiLevel بتعيين كل بكسل إما باللون الأسود أو الأبيض ، أيهما أقرب إلى اللون الأصلي.
importedShape = (Shape)dstDoc.ImportNode(sourceShape, true);
dstDoc.FirstSection.Body.FirstParagraph.AppendChild(importedShape);

importedShape.ImageData.BiLevel = true;

// يتم تحديد الاقتصاص على مقياس 0-1. قص جانب بمقدار 0.3
// سيقص 30٪ من الصورة في الجانب الذي تم اقتصاصه.
importedShape.ImageData.CropBottom = 0.3;
importedShape.ImageData.CropLeft = 0.3;
importedShape.ImageData.CropTop = 0.3;
importedShape.ImageData.CropRight = 0.3;

dstDoc.Save(ArtifactsDir + "Drawing.ImageData.docx");
```

### أنظر أيضا

* class [ImageData](../)
* مساحة الاسم [Aspose.Words.Drawing](../../imagedata/)
* المجسم [Aspose.Words](../../../)


