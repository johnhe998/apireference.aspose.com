---
title: ImageData.ToStream
second_title: Aspose.Words لمراجع .NET API
description: ImageData طريقة. إنشاء وإرجاع دفق يحتوي على بايت الصورة.
type: docs
weight: 230
url: /ar/net/aspose.words.drawing/imagedata/tostream/
---
## ImageData.ToStream method

إنشاء وإرجاع دفق يحتوي على بايت الصورة.

```csharp
public Stream ToStream()
```

### ملاحظات

إذا تم تخزين وحدات بايت الصورة في الشكل ، فسيتم إنشاء وإرجاع ملفMemoryStream هدف.

إذا كانت الصورة مرتبطة ومخزنة في ملف ، يفتح الملف ويعيد ملفFileStream هدف.

إذا تم ربط الصورة وتخزينها في عنوان URL خارجي ، فقم بتنزيل الملف وإرجاع ملفMemoryStream هدف.

هل من مسؤولية المتصل التخلص من كائن الدفق.

### أمثلة

يوضح كيفية إنشاء ملف صورة من بيانات الصورة الأولية للشكل.

```csharp
Document imgSourceDoc = new Document(MyDir + "Images.docx");

Shape imgShape = (Shape) imgSourceDoc.GetChild(NodeType.Shape, 0, true);

Assert.True(imgShape.HasImage);

// يُرجع ToByteArray () الصفيف المخزن في خاصية ImageBytes.
Assert.AreEqual(imgShape.ImageData.ImageBytes, imgShape.ImageData.ToByteArray());

// حفظ بيانات صورة الشكل في ملف صورة في نظام الملفات المحلي.
using (Stream imgStream = imgShape.ImageData.ToStream())
{
    using (FileStream outStream = new FileStream(ArtifactsDir + "Drawing.GetDataFromImage.png",
        FileMode.Create, FileAccess.ReadWrite))
    {
        imgStream.CopyTo(outStream);
    }
}
```

### أنظر أيضا

* class [ImageData](../)
* مساحة الاسم [Aspose.Words.Drawing](../../imagedata/)
* المجسم [Aspose.Words](../../../)


