---
title: ShapeBase.GetShapeRenderer
second_title: Aspose.Words لمراجع .NET API
description: ShapeBase طريقة. إنشاء وإرجاع كائن يمكن استخدامه لتحويل هذا الشكل إلى صورة.
type: docs
weight: 600
url: /ar/net/aspose.words.drawing/shapebase/getshaperenderer/
---
## ShapeBase.GetShapeRenderer method

إنشاء وإرجاع كائن يمكن استخدامه لتحويل هذا الشكل إلى صورة.

```csharp
public ShapeRenderer GetShapeRenderer()
```

### قيمة الإرجاع

كائن العارض لهذا الشكل.

### ملاحظات

تستدعي هذه الطريقة فقط[`ShapeRenderer`](../../../aspose.words.rendering/shaperenderer/) المُنشئ ويمرر هذا الكائن كمعامل.

### أمثلة

يوضح كيفية استخدام عارض الأشكال لتصدير الأشكال إلى الملفات في نظام الملفات المحلي.

```csharp
Document doc = new Document(MyDir + "Various shapes.docx");
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(7, shapes.Length);

// هناك 7 أشكال في المستند ، بما في ذلك شكل مجموعة واحد مع شكلين فرعيين.
// سنقدم كل شكل إلى ملف صورة في نظام الملفات المحلي
// أثناء تجاهل أشكال المجموعة نظرًا لعدم ظهورها.
// هذا سينتج 6 ملفات صور.
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>())
{
    ShapeRenderer renderer = shape.GetShapeRenderer();
    ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Png);
    renderer.Save(ArtifactsDir + $"Shape.RenderAllShapes.{shape.Name}.png", options);
}
```

### أنظر أيضا

* class [ShapeRenderer](../../../aspose.words.rendering/shaperenderer/)
* class [ShapeBase](../)
* مساحة الاسم [Aspose.Words.Drawing](../../shapebase/)
* المجسم [Aspose.Words](../../../)


