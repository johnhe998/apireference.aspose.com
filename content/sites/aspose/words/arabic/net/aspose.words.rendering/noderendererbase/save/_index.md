---
title: NodeRendererBase.Save
second_title: Aspose.Words لمراجع .NET API
description: NodeRendererBase طريقة. يعرض الشكل في صورة وحفظه في ملف.
type: docs
weight: 90
url: /ar/net/aspose.words.rendering/noderendererbase/save/
---
## Save(string, ImageSaveOptions) {#save_1}

يعرض الشكل في صورة وحفظه في ملف.

```csharp
public void Save(string fileName, ImageSaveOptions saveOptions)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| fileName | String | اسم ملف الصورة. إذا كان هناك ملف بالاسم المحدد موجودًا بالفعل ، فسيتم استبدال الملف الحالي. |
| saveOptions | ImageSaveOptions | يحدد الخيارات التي تتحكم في كيفية عرض الشكل وحفظه. يمكن أن تكون خالية. |

### أمثلة

يوضح كيفية تحويل كائن Office Math إلى ملف صورة في نظام الملفات المحلي.

```csharp
Document doc = new Document(MyDir + "Office math.docx");

OfficeMath math = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

// قم بإنشاء كائن "ImageSaveOptions" لتمريره إلى طريقة "Save" لتعديل طريقة عرض العقدة
// كيف يعرض عقدة OfficeMath في صورة.
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png);

// اضبط خاصية "Scale" على 5 لجعل الكائن خمسة أضعاف حجمه الأصلي.
saveOptions.Scale = 5;

math.GetMathRenderer().Save(ArtifactsDir + "Shape.RenderOfficeMath.png", saveOptions);
```

### أنظر أيضا

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* مساحة الاسم [Aspose.Words.Rendering](../../noderendererbase/)
* المجسم [Aspose.Words](../../../)

---

## Save(Stream, ImageSaveOptions) {#save}

يجسد الشكل في صورة ويحفظ في تدفق .

```csharp
public void Save(Stream stream, ImageSaveOptions saveOptions)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| stream | Stream | الدفق حيث يتم حفظ صورة الشكل. |
| saveOptions | ImageSaveOptions | يحدد الخيارات التي تتحكم في كيفية عرض الشكل وحفظه. يمكن أن يكون فارغًا. إذا كان هذا فارغًا ، فسيتم حفظ الصورة بتنسيق PNG. |

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

* class [ImageSaveOptions](../../../aspose.words.saving/imagesaveoptions/)
* class [NodeRendererBase](../)
* مساحة الاسم [Aspose.Words.Rendering](../../noderendererbase/)
* المجسم [Aspose.Words](../../../)


