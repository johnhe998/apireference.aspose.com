---
title: Enum HorizontalAlignment
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.HorizontalAlignment تعداد. يحدد المحاذاة الأفقية لشكل عائم أو إطار نص أو جدول عائم.
type: docs
weight: 900
url: /ar/net/aspose.words.drawing/horizontalalignment/
---
## HorizontalAlignment enumeration

يحدد المحاذاة الأفقية لشكل عائم أو إطار نص أو جدول عائم.

```csharp
public enum HorizontalAlignment
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| None | `0` | يتم وضع الكائن بشكل صريح ، وعادة ما يستخدمه **اليسار** الملكية . |
| Default | `0` | نفسNone . |
| Left | `1` | تحديد أنه يجب ترك الكائن بمحاذاة قاعدة المحاذاة الأفقية. |
| Center | `2` | يحدد أن الكائن يجب أن يتم توسيطه فيما يتعلق بقاعدة المحاذاة الأفقية. |
| Right | `3` | يحدد أن الكائن يجب أن يكون محاذيًا لليمين لقاعدة المحاذاة الأفقية. |
| Inside | `4` | تحديد أن الكائن يجب أن يكون داخل قاعدة المحاذاة الأفقية. |
| Outside | `5` | تحديد أن الكائن يجب أن يكون خارج قاعدة المحاذاة الأفقية. |

### أمثلة

يوضح كيفية إدراج صورة عائمة في وسط الصفحة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل صورة عائمة ستظهر خلف النص المتداخل وقم بمحاذاة مركز الصفحة.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### أنظر أيضا

* property [HorizontalAlignment](../shapebase/horizontalalignment/)
* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


