---
title: ImageData.HasImage
second_title: Aspose.Words لمراجع .NET API
description: ImageData ملكية. إرجاع صحيح إذا كان للشكل بايت صورة أو ربط صورة.
type: docs
weight: 110
url: /ar/net/aspose.words.drawing/imagedata/hasimage/
---
## ImageData.HasImage property

إرجاع صحيح إذا كان للشكل بايت صورة أو ربط صورة.

```csharp
public bool HasImage { get; }
```

### أمثلة

يوضح كيفية حفظ جميع الصور من مستند إلى نظام الملفات.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");

// الأشكال مع مخزن مجموعة العلامات "HasImage" وعرض جميع صور المستند.
IEnumerable<Shape> shapesWithImages = 
    imgSourceDoc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Where(s => s.HasImage);

// اذهب من خلال كل شكل واحفظ صورته.
ImageFormatConverter formatConverter = new ImageFormatConverter();

using (IEnumerator<Shape> enumerator = shapesWithImages.GetEnumerator())
{
    int shapeIndex = 0;

    while (enumerator.MoveNext())
    {
        ImageData imageData = enumerator.Current.ImageData;
        ImageFormat format = imageData.ToImage().RawFormat;
        string fileExtension = formatConverter.ConvertToString(format);

        using (FileStream fileStream = File.Create(ArtifactsDir + $"Drawing.SaveAllImages.{++shapeIndex}.{fileExtension}"))
            imageData.Save(fileStream);
    }
}
```

### أنظر أيضا

* class [ImageData](../)
* مساحة الاسم [Aspose.Words.Drawing](../../imagedata/)
* المجسم [Aspose.Words](../../../)


