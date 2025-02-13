---
title: Enum TextureAlignment
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Drawing.TextureAlignment تعداد. يحدد المحاذاة لتجانب تعبئة النسيج.
type: docs
weight: 1220
url: /ar/net/aspose.words.drawing/texturealignment/
---
## TextureAlignment enumeration

يحدد المحاذاة لتجانب تعبئة النسيج.

```csharp
public enum TextureAlignment
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| TopLeft | `0` | محاذاة النسيج العلوية اليسرى . |
| Top | `1` | محاذاة النسيج العلوي . |
| TopRight | `2` | محاذاة النسيج العلوية اليمنى . |
| Left | `3` | محاذاة النسيج الأيسر . |
| Center | `4` | توسيط محاذاة النسيج . |
| Right | `5` | محاذاة الملمس الأيمن . |
| BottomLeft | `6` | محاذاة النسيج السفلي الأيسر . |
| Bottom | `7` | محاذاة النسيج السفلي . |
| BottomRight | `8` | محاذاة النسيج السفلي الأيمن . |
| None | `9` | محاذاة بلا نسيج . |

### أمثلة

يوضح كيفية تعبئة وتبليط النسيج داخل الشكل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertShape(ShapeType.Rectangle, 80, 80);

// تطبيق محاذاة النسيج على تعبئة الشكل.
shape.Fill.PresetTextured(PresetTexture.Canvas);
shape.Fill.TextureAlignment = TextureAlignment.TopRight;

// استخدم خيار التوافق لتحديد الشكل باستخدام DML إذا كنت تريد الحصول على "TextureAlignment"
// خاصية بعد حفظ المستند.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(ArtifactsDir + "Shape.TextureFill.docx", saveOptions);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Drawing](../../aspose.words.drawing/)
* المجسم [Aspose.Words](../../)


