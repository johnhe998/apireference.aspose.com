---
title: PageSetup.CharactersPerLine
second_title: Aspose.Words لمراجع .NET API
description: PageSetup ملكية. الحصول على أو تحديد عدد الأحرف في كل سطر في شبكة المستند.
type: docs
weight: 100
url: /ar/net/aspose.words/pagesetup/charactersperline/
---
## PageSetup.CharactersPerLine property

الحصول على أو تحديد عدد الأحرف في كل سطر في شبكة المستند.

```csharp
public int CharactersPerLine { get; set; }
```

### ملاحظات

الحد الأدنى لقيمة الخاصية هو 1. تعتمد القيمة القصوى على عرض الصفحة وحجم الخط للنمط Normal . الحد الأدنى لمسافة الأحرف 90 بالمائة من حجم الخط. على سبيل المثال ، الحد الأقصى لعدد الأحرف_ لكل سطر من صفحة Letter بهوامش بوصة واحدة هو 43.

بشكل افتراضي ، تحتوي الخاصية على قيمة ، حيث تساوي خطوة الأحرف حجم خط النمط Normal .

### أمثلة

يوضح كيفية تحديد عدد الأحرف التي قد يحتوي عليها كل سطر.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بتمكين التدوير ، ثم استخدمه لتعيين عدد الأحرف في كل سطر في هذا القسم.
builder.PageSetup.LayoutMode = SectionLayoutMode.Grid;
builder.PageSetup.CharactersPerLine = 10;

// يعتمد عدد الأحرف أيضًا على حجم الخط.
doc.Styles["Normal"].Font.Size = 20;

Assert.AreEqual(8, doc.FirstSection.PageSetup.CharactersPerLine);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "PageSetup.CharactersPerLine.docx");
```

### أنظر أيضا

* class [PageSetup](../)
* مساحة الاسم [Aspose.Words](../../pagesetup/)
* المجسم [Aspose.Words](../../../)


