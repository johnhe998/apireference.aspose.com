---
title: Class NodeRendererBase
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Rendering.NodeRendererBase فصل. الفئة الأساسية لـShapeRenderer وOfficeMathRenderer .
type: docs
weight: 4290
url: /ar/net/aspose.words.rendering/noderendererbase/
---
## NodeRendererBase class

الفئة الأساسية لـ[`ShapeRenderer`](../shaperenderer/) و[`OfficeMathRenderer`](../officemathrenderer/) .

```csharp
public abstract class NodeRendererBase
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [BoundsInPoints](../../aspose.words.rendering/noderendererbase/boundsinpoints/) { get; } | يحصل على الحدود الفعلية للشكل بالنقاط . |
| [OpaqueBoundsInPoints](../../aspose.words.rendering/noderendererbase/opaqueboundsinpoints/) { get; } | يحصل على الحدود المعتمة للشكل بالنقاط . |
| [SizeInPoints](../../aspose.words.rendering/noderendererbase/sizeinpoints/) { get; } | الحصول على الحجم الفعلي للشكل بالنقاط . |

## طُرق

| اسم | وصف |
| --- | --- |
| [GetBoundsInPixels](../../aspose.words.rendering/noderendererbase/getboundsinpixels/#getboundsinpixels)(float, float) | حساب حدود الشكل بالبكسل لعامل تكبير ودقة محددين . |
| [GetBoundsInPixels](../../aspose.words.rendering/noderendererbase/getboundsinpixels/#getboundsinpixels_1)(float, float, float) | حساب حدود الشكل بالبكسل لعامل تكبير ودقة محددين . |
| [GetOpaqueBoundsInPixels](../../aspose.words.rendering/noderendererbase/getopaqueboundsinpixels/#getopaqueboundsinpixels)(float, float) | لحساب الحدود المعتمة للشكل بالبكسل لعامل تكبير ودقة محددين . |
| [GetOpaqueBoundsInPixels](../../aspose.words.rendering/noderendererbase/getopaqueboundsinpixels/#getopaqueboundsinpixels_1)(float, float, float) | لحساب الحدود المعتمة للشكل بالبكسل لعامل تكبير ودقة محددين . |
| [GetSizeInPixels](../../aspose.words.rendering/noderendererbase/getsizeinpixels/#getsizeinpixels)(float, float) | حساب حجم الشكل بالبكسل لعامل تكبير ودقة محددين . |
| [GetSizeInPixels](../../aspose.words.rendering/noderendererbase/getsizeinpixels/#getsizeinpixels_1)(float, float, float) | حساب حجم الشكل بالبكسل لعامل تكبير ودقة محددين . |
| [RenderToScale](../../aspose.words.rendering/noderendererbase/rendertoscale/)(Graphics, float, float, float) | يجعل الشكل في ملفGraphics كائن إلى مقياس محدد . |
| [RenderToSize](../../aspose.words.rendering/noderendererbase/rendertosize/)(Graphics, float, float, float, float) | يجعل الشكل في ملفGraphics كائن لحجم محدد . |
| [Save](../../aspose.words.rendering/noderendererbase/save/#save)(Stream, ImageSaveOptions) | يجسد الشكل في صورة ويحفظ في تدفق . |
| [Save](../../aspose.words.rendering/noderendererbase/save/#save_1)(string, ImageSaveOptions) | يعرض الشكل في صورة وحفظه في ملف. |

### أمثلة

يوضح كيفية قياس الأشكال وقياسها.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
OfficeMathRenderer renderer = new OfficeMathRenderer(officeMath);

// تحقق من حجم الصورة التي سينشئها كائن OfficeMath عند عرضها.
Assert.AreEqual(119.0f, renderer.SizeInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.SizeInPoints.Height, 0.1f);

Assert.AreEqual(119.0f, renderer.BoundsInPoints.Width, 0.2f);
Assert.AreEqual(13.0f, renderer.BoundsInPoints.Height, 0.1f);

// قد تحتوي الأشكال ذات الأجزاء الشفافة على قيم مختلفة في خصائص "OpaqueBoundsInPoints".
Assert.AreEqual(119.0f, renderer.OpaqueBoundsInPoints.Width, 0.2f);
Assert.AreEqual(14.2f, renderer.OpaqueBoundsInPoints.Height, 0.1f);

// احصل على حجم الشكل بالبكسل ، مع تغيير الحجم الخطي إلى DPI محدد.
Rectangle bounds = renderer.GetBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

// احصل على حجم الشكل بالبكسل ، ولكن باستخدام DPI مختلف للأبعاد الأفقية والرأسية.
bounds = renderer.GetBoundsInPixels(1.0f, 96.0f, 150.0f);
Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(28, bounds.Height);

// قد تختلف الحدود المعتمة هنا أيضًا.
bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(18, bounds.Height);

bounds = renderer.GetOpaqueBoundsInPixels(1.0f, 96.0f, 150.0f);

Assert.AreEqual(159, bounds.Width);
Assert.AreEqual(30, bounds.Height);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Rendering](../../aspose.words.rendering/)
* المجسم [Aspose.Words](../../)


