---
title: BorderCollection.Equals
second_title: Aspose.Words لمراجع .NET API
description: BorderCollection طريقة. مقارنة مجموعات الحدود .
type: docs
weight: 150
url: /ar/net/aspose.words/bordercollection/equals/
---
## BorderCollection.Equals method

مقارنة مجموعات الحدود .

```csharp
public bool Equals(BorderCollection brColl)
```

### أمثلة

يوضح كيف يمكن لمجموعات الحدود مشاركة العناصر.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Paragraph 1.");
builder.Write("Paragraph 2.");

// نظرًا لأننا استخدمنا نفس تكوين الحدود أثناء الإنشاء
// هذه الفقرات ، تشترك مجموعاتها الحدودية في نفس العناصر.
BorderCollection firstParagraphBorders = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Borders;
BorderCollection secondParagraphBorders = builder.CurrentParagraph.ParagraphFormat.Borders;

for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsTrue(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());
    Assert.False(firstParagraphBorders[i].IsVisible);
}

foreach (Border border in secondParagraphBorders)
    border.LineStyle = LineStyle.DotDash;

// بعد تغيير نمط خط الحدود في الفقرة الثانية فقط ،
// لم تعد مجموعات الحدود تشترك في نفس العناصر.
for (int i = 0; i < firstParagraphBorders.Count; i++)
{
    Assert.IsFalse(firstParagraphBorders[i].Equals(secondParagraphBorders[i]));
    Assert.AreNotEqual(firstParagraphBorders[i].GetHashCode(), secondParagraphBorders[i].GetHashCode());

    // تغيير مظهر حد فارغ يجعله مرئيًا.
    Assert.True(secondParagraphBorders[i].IsVisible);
}

doc.Save(ArtifactsDir + "Border.SharedElements.docx");
```

### أنظر أيضا

* class [BorderCollection](../)
* مساحة الاسم [Aspose.Words](../../bordercollection/)
* المجسم [Aspose.Words](../../../)


