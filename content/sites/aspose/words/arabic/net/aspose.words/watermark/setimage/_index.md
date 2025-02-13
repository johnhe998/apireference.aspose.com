---
title: Watermark.SetImage
second_title: Aspose.Words لمراجع .NET API
description: Watermark طريقة. يضيف علامة مائية للصورة إلى المستند.
type: docs
weight: 30
url: /ar/net/aspose.words/watermark/setimage/
---
## SetImage(Image) {#setimage}

يضيف علامة مائية للصورة إلى المستند.

```csharp
public void SetImage(Image image)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| image | Image | الصورة التي يتم عرضها كعلامة مائية. |

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentNullException | يتم إلقاؤه عندما تكون الصورة فارغة . |

### أنظر أيضا

* class [Watermark](../)
* مساحة الاسم [Aspose.Words](../../watermark/)
* المجسم [Aspose.Words](../../../)

---

## SetImage(Image, ImageWatermarkOptions) {#setimage_1}

يضيف علامة مائية للصورة إلى المستند.

```csharp
public void SetImage(Image image, ImageWatermarkOptions options)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| image | Image | الصورة التي يتم عرضها كعلامة مائية. |
| options | ImageWatermarkOptions | يحدد خيارات إضافية للعلامة المائية للصورة. |

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentNullException | يتم إلقاؤه عندما تكون الصورة فارغة . |

### ملاحظات

إذا[`ImageWatermarkOptions`](../../imagewatermarkoptions/) فارغة ، سيتم تعيين العلامة المائية مع الخيارات الافتراضية.

### أمثلة

يوضح كيفية إنشاء علامة مائية من صورة في نظام الملفات المحلي.

```csharp
Document doc = new Document();

            // قم بتعديل مظهر العلامة المائية للصورة باستخدام كائن ImageWatermarkOptions ،
            // ثم مررها أثناء إنشاء علامة مائية من ملف صورة.
            ImageWatermarkOptions imageWatermarkOptions = new ImageWatermarkOptions();
            imageWatermarkOptions.Scale = 5;
            imageWatermarkOptions.IsWashout = false;

#if NET48 || JAVA
            doc.Watermark.SetImage(Image.FromFile(ImageDir + "Logo.jpg"), imageWatermarkOptions);
#elif NET5_0_OR_GREATER || __MOBILE__
            using (SKBitmap image = SKBitmap.Decode(ImageDir + "Logo.jpg"))
            {
                doc.Watermark.SetImage(image, imageWatermarkOptions);
            }
#endif

            doc.Save(ArtifactsDir + "Document.ImageWatermark.docx");
```

### أنظر أيضا

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* مساحة الاسم [Aspose.Words](../../watermark/)
* المجسم [Aspose.Words](../../../)

---

## SetImage(string, ImageWatermarkOptions) {#setimage_2}

يضيف علامة مائية للصورة إلى المستند.

```csharp
public void SetImage(string imagePath, ImageWatermarkOptions options)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| imagePath | String | المسار إلى ملف الصورة الذي يتم عرضه كعلامة مائية. |
| options | ImageWatermarkOptions | يحدد خيارات إضافية للعلامة المائية للصورة. |

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentNullException | يتم رميه عندما يكون المسار فارغًا . |

### ملاحظات

إذا[`ImageWatermarkOptions`](../../imagewatermarkoptions/) فارغة ، سيتم تعيين العلامة المائية مع الخيارات الافتراضية.

### أنظر أيضا

* class [ImageWatermarkOptions](../../imagewatermarkoptions/)
* class [Watermark](../)
* مساحة الاسم [Aspose.Words](../../watermark/)
* المجسم [Aspose.Words](../../../)


