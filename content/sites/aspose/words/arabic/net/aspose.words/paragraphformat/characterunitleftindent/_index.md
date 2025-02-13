---
title: ParagraphFormat.CharacterUnitLeftIndent
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. الحصول على أو تعيين قيمة المسافة البادئة اليسرى بالأحرف للفقرات المحددة.
type: docs
weight: 70
url: /ar/net/aspose.words/paragraphformat/characterunitleftindent/
---
## ParagraphFormat.CharacterUnitLeftIndent property

الحصول على أو تعيين قيمة المسافة البادئة اليسرى (بالأحرف) للفقرات المحددة.

```csharp
public double CharacterUnitLeftIndent { get; set; }
```

### أمثلة

يوضح كيفية تغيير تباعد الفقرات والمسافات البادئة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;

// يوجد أدناه خمسة خيارات مسافات مختلفة ، إلى جانب الخصائص التي يؤثر تكوينها بشكل غير مباشر.
// 1 - مسافة بادئة يسرى:
Assert.AreEqual(format.LeftIndent, 0.0d);

format.CharacterUnitLeftIndent = 10.0;

Assert.AreEqual(format.LeftIndent, 120.0d);

// 2 - مسافة بادئة يمنى:
Assert.AreEqual(format.RightIndent, 0.0d); 

format.CharacterUnitRightIndent = -5.5;

Assert.AreEqual(format.RightIndent, -66.0d);

// 3 - مسافة بادئة معلقة:
Assert.AreEqual(format.FirstLineIndent, 0.0d);

format.CharacterUnitFirstLineIndent = 20.3;

Assert.AreEqual(format.FirstLineIndent, 243.59d, 0.1d);

// 4 - تباعد الأسطر قبل الفقرات:
Assert.AreEqual(format.SpaceBefore, 0.0d);

format.LineUnitBefore = 5.1;

Assert.AreEqual(format.SpaceBefore, 61.1d, 0.1d);

// 5 - تباعد الأسطر بعد الفقرات:
Assert.AreEqual(format.SpaceAfter, 0.0d);

format.LineUnitAfter = 10.9;

Assert.AreEqual(format.SpaceAfter, 130.8d, 0.1d);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");
builder.Write("测试文档测试文档测试文档测试文档测试文档测试文档测试文档测试文档测试" +
              "文档测试文档测试文档测试文档测试文档测试文档测试文档测试文档测试文档测试文档");
```

### أنظر أيضا

* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


