---
title: ParagraphFormat.SpaceAfter
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. الحصول على أو تحديد مقدار التباعد بالنقاط بعد الفقرة.
type: docs
weight: 290
url: /ar/net/aspose.words/paragraphformat/spaceafter/
---
## ParagraphFormat.SpaceAfter property

الحصول على أو تحديد مقدار التباعد (بالنقاط) بعد الفقرة.

```csharp
public double SpaceAfter { get; set; }
```

### استثناءات

| استثناء | حالة |
| --- | --- |
| ArgumentOutOfRangeException | يظهر عندما تكون الوسيطة خارج نطاق القيم الصالحة. |

### ملاحظات

ليس له تأثير عندما[`SpaceAfterAuto`](../spaceafterauto/) صحيح.

تتراوح القيم الصالحة من 0 إلى 1584 ضمناً.

### أمثلة

يوضح كيفية تعيين التباعد التلقائي بين الفقرات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بتطبيق قدر كبير من المسافات قبل وبعد الفقرات التي سينشئها هذا المنشئ.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// اضبط هذه العلامات على "صواب" لتطبيق تباعد تلقائي ،
// يتجاهل التباعد في الخصائص التي حددناها أعلاه بشكل فعال.
// اتركها على أنها "خطأ" ستطبق تباعد الفقرات المخصص.
builder.ParagraphFormat.SpaceAfterAuto = autoSpacing;
builder.ParagraphFormat.SpaceBeforeAuto = autoSpacing;

// أدخل فقرتين تحتوي على مسافات أعلى وأسفلهما واحفظ المستند.
builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingAuto.docx");
```

يوضح كيفية تطبيق عدم وجود مسافات بين الفقرات بنفس النمط.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بتطبيق قدر كبير من المسافات قبل وبعد الفقرات التي سينشئها هذا المنشئ.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// اضبط علامة "NoSpaceBetweenParagraphsOfSameStyle" على "true" لتطبيقها
// لا توجد مسافات بين الفقرات بنفس النمط ، والتي ستجمع الفقرات المتشابهة.
// اترك علامة "NoSpaceBetweenParagraphsOfSameStyle" على أنها "خطأ"
// لتطبيق التباعد بالتساوي على كل فقرة.
builder.ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle = noSpaceBetweenParagraphsOfSameStyle;

builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingSameStyle.docx");
```

### أنظر أيضا

* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


