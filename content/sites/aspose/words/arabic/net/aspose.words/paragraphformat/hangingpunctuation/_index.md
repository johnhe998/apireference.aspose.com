---
title: ParagraphFormat.HangingPunctuation
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. الحصول على أو تعيين علامة تشير إلى ما إذا كان الترقيم المعلق ممكّنًا للفقرة الحالية.
type: docs
weight: 120
url: /ar/net/aspose.words/paragraphformat/hangingpunctuation/
---
## ParagraphFormat.HangingPunctuation property

الحصول على أو تعيين علامة تشير إلى ما إذا كان الترقيم المعلق ممكّنًا للفقرة الحالية.

```csharp
public bool HangingPunctuation { get; set; }
```

### أمثلة

يوضح كيفية تعيين خصائص خاصة للطباعة الآسيوية.

```csharp
Document doc = new Document(MyDir + "Document.docx");

ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.FarEastLineBreakControl = true;
format.WordWrap = false;
format.HangingPunctuation = true;

doc.Save(ArtifactsDir + "ParagraphFormat.AsianTypographyProperties.docx");
```

### أنظر أيضا

* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


