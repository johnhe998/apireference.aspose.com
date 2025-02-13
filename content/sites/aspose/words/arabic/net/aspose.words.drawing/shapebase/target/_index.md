---
title: ShapeBase.Target
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase ملكية. الحصول على أو تعيين الإطار الهدف للارتباط التشعبي للشكل.
type: docs
weight: 480
url: /ar/net/aspose.words.drawing/shapebase/target/
---
## ShapeBase.Target property

الحصول على أو تعيين الإطار الهدف للارتباط التشعبي للشكل.

```csharp
public string Target { get; set; }
```

### ملاحظات

القيمة الافتراضية هي سلسلة فارغة.

### أمثلة

يوضح كيفية إدراج شكل يحتوي على صورة ، وهو أيضًا ارتباط تشعبي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.HRef = "https://forum.aspose.com/ ";
shape.Target = "New Window";
shape.ScreenTip = "Aspose.Words Support Forums";

// Ctrl + النقر بزر الماوس الأيسر على الشكل في Microsoft Word سيفتح نافذة متصفح ويب جديدة
// وانتقل بنا إلى الارتباط التشعبي في خاصية "HRef".
doc.Save(ArtifactsDir + "Image.InsertImageWithHyperlink.docx");
```

### أنظر أيضا

* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


