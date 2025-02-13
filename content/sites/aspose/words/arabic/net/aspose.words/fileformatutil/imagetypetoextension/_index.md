---
title: FileFormatUtil.ImageTypeToExtension
second_title: Aspose.Words لمراجع .NET API
description: FileFormatUtil طريقة. تحويل قيمة تعداد نوع صورة Aspose.Words إلى امتداد ملف. الامتداد الذي تم إرجاعه عبارة عن سلسلة أحرف صغيرة بنقطة بادئة.
type: docs
weight: 50
url: /ar/net/aspose.words/fileformatutil/imagetypetoextension/
---
## FileFormatUtil.ImageTypeToExtension method

تحويل قيمة تعداد نوع صورة Aspose.Words إلى امتداد ملف. الامتداد الذي تم إرجاعه عبارة عن سلسلة أحرف صغيرة بنقطة بادئة.

```csharp
public static string ImageTypeToExtension(ImageType imageType)
```

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentException | رمى عندما لا تستطيع التحويل. |

### أمثلة

يوضح كيفية استخراج الصور من مستند ، وحفظها في نظام الملفات المحلي كملفات فردية.

```csharp
Document doc = new Document(MyDir + "Images.docx");

// احصل على مجموعة الأشكال من المستند ،
// وحفظ بيانات الصورة لكل شكل مع صورة كملف في نظام الملفات المحلي.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);

Assert.AreEqual(9, shapes.Count(s => ((Shape)s).HasImage));

int imageIndex = 0;
foreach (Shape shape in shapes.OfType<Shape>())
{
    if (shape.HasImage)
    {
        // قد تحتوي بيانات صور الأشكال على صور للعديد من تنسيقات الصور الممكنة. 
        // يمكننا تحديد امتداد ملف لكل صورة تلقائيًا ، بناءً على تنسيقها.
        string imageFileName =
            $"File.ExtractImages.{imageIndex}{FileFormatUtil.ImageTypeToExtension(shape.ImageData.ImageType)}";
        shape.ImageData.Save(ArtifactsDir + imageFileName);
        imageIndex++;
    }
}
```

### أنظر أيضا

* enum [ImageType](../../../aspose.words.drawing/imagetype/)
* class [FileFormatUtil](../)
* مساحة الاسم [Aspose.Words](../../fileformatutil/)
* المجسم [Aspose.Words](../../../)


