---
title: Border.IsVisible
second_title: Aspose.Words لمراجع .NET API
description: Border ملكية. إرجاع صحيح إذا لم يكن LineStyle ليس LineStyle.
type: docs
weight: 30
url: /ar/net/aspose.words/border/isvisible/
---
## Border.IsVisible property

إرجاع صحيح إذا لم يكن LineStyle ليس LineStyle.

```csharp
public bool IsVisible { get; }
```

### أمثلة

يوضح كيفية إزالة الحدود من فقرة.

```csharp
Document doc = new Document(MyDir + "Borders.docx");

// لكل فقرة مجموعة فردية من الحدود.
// يمكننا الوصول إلى إعدادات ظهور هذه الحدود عبر كائن تنسيق الفقرة.
BorderCollection borders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;

Assert.AreEqual(Color.Red.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(3.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.Single, borders[0].LineStyle);
Assert.True(borders[0].IsVisible);

// يمكننا إزالة حد مرة واحدة عن طريق تشغيل طريقة ClearFormatting. 
// سيؤدي تشغيل هذه الطريقة على كل حدود الفقرة إلى إزالة كل حدودها.
foreach (Border border in borders)
    border.ClearFormatting();

Assert.AreEqual(Color.Empty.ToArgb(), borders[0].Color.ToArgb());
Assert.AreEqual(0.0d, borders[0].LineWidth);
Assert.AreEqual(LineStyle.None, borders[0].LineStyle);
Assert.IsFalse(borders[0].IsVisible);

doc.Save(ArtifactsDir + "Border.ClearFormatting.docx");
```

### أنظر أيضا

* class [Border](../)
* مساحة الاسم [Aspose.Words](../../border/)
* المجسم [Aspose.Words](../../../)


