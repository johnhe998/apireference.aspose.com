---
title: Fill.TextureAlignment
second_title: Aspose.Words لمراجع .NET API
description: Fill ملكية. الحصول على أو تعيين المحاذاة لتعبئة نسيج التجانب.
type: docs
weight: 130
url: /ar/net/aspose.words.drawing/fill/texturealignment/
---
## Fill.TextureAlignment property

الحصول على أو تعيين المحاذاة لتعبئة نسيج التجانب.

```csharp
public TextureAlignment TextureAlignment { get; set; }
```

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

* enum [TextureAlignment](../../texturealignment/)
* class [Fill](../)
* مساحة الاسم [Aspose.Words.Drawing](../../fill/)
* المجسم [Aspose.Words](../../../)


