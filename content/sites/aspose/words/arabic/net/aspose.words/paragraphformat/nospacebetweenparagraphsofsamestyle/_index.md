---
title: ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. عندما يكون صحيحًا SpaceBefore وSpaceAfter سيتم تجاهله_ بين فقرات نفس النمط.
type: docs
weight: 230
url: /ar/net/aspose.words/paragraphformat/nospacebetweenparagraphsofsamestyle/
---
## ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle property

عندما يكون صحيحًا ،[`SpaceBefore`](../spacebefore/) و[`SpaceAfter`](../spaceafter/) سيتم تجاهله_ بين فقرات نفس النمط.

```csharp
public bool NoSpaceBetweenParagraphsOfSameStyle { get; set; }
```

### ملاحظات

لا يسري هذا الإعداد إلا عند تطبيقه على نمط فقرة. إذا تم تطبيقه على فقرة مباشرة ، فلن يكون لها أي تأثير.

### أمثلة

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


