---
title: ParagraphFormat.OutlineLevel
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. يحدد مستوى المخطط التفصيلي للفقرة في المستند.
type: docs
weight: 240
url: /ar/net/aspose.words/paragraphformat/outlinelevel/
---
## ParagraphFormat.OutlineLevel property

يحدد مستوى المخطط التفصيلي للفقرة في المستند.

```csharp
public OutlineLevel OutlineLevel { get; set; }
```

### أمثلة

يوضح كيفية تكوين مستويات المخطط التفصيلي للفقرة لإنشاء نص قابل للطي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// تحتوي كل فقرة على OutlineLevel ، والذي يمكن أن يكون أي رقم من 1 إلى 9 ، أو عند القيمة الافتراضية "BodyText".
// سيؤدي تعيين الخاصية إلى إحدى القيم المرقمة إلى إظهار سهم إلى اليسار
// من بداية الفقرة.
builder.ParagraphFormat.OutlineLevel = OutlineLevel.Level1;
builder.Writeln("Paragraph outline level 1.");

// المستوى 1 هو المستوى الأعلى. إذا كانت هناك فقرة ذات مستوى أدنى أسفل فقرة ذات مستوى أعلى ،
// سيؤدي طي الفقرة ذات المستوى الأعلى إلى انهيار فقرة المستوى السفلي.
builder.ParagraphFormat.OutlineLevel = OutlineLevel.Level2;
builder.Writeln("Paragraph outline level 2.");

// فقرتان من نفس المستوى لن تنهار بعضهما البعض ،
// والأسهم لا تطوي الفقرات التي تشير إليها.
builder.ParagraphFormat.OutlineLevel = OutlineLevel.Level3;
builder.Writeln("Paragraph outline level 3.");
builder.Writeln("Paragraph outline level 3.");

// القيمة الافتراضية "BodyText" هي الأدنى ، والتي يمكن أن تنهار فقرة من أي مستوى.
builder.ParagraphFormat.OutlineLevel = OutlineLevel.BodyText;
builder.Writeln("Paragraph at main text level.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphOutlineLevel.docx");
```

### أنظر أيضا

* enum [OutlineLevel](../../outlinelevel/)
* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


