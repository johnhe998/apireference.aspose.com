---
title: ParagraphFormat.HangingPunctuation
linktitle: HangingPunctuation
articleTitle: HangingPunctuation
second_title: Aspose.Words for .NET
description: ParagraphFormat HangingPunctuation property. Gets or sets a flag indicating whether hanging punctuation is enabled for the current paragraph in C#.
type: docs
weight: 120
url: /net/aspose.words/paragraphformat/hangingpunctuation/
---
## ParagraphFormat.HangingPunctuation property

Gets or sets a flag indicating whether hanging punctuation is enabled for the current paragraph.

```csharp
public bool HangingPunctuation { get; set; }
```

## Examples

Shows how to set special properties for Asian typography.

```csharp
Document doc = new Document(MyDir + "Document.docx");

ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.FarEastLineBreakControl = true;
format.WordWrap = false;
format.HangingPunctuation = true;

doc.Save(ArtifactsDir + "ParagraphFormat.AsianTypographyProperties.docx");
```

### See Also

* class [ParagraphFormat](../)
* namespace [Aspose.Words](../../../aspose.words/)
* assembly [Aspose.Words](../../../)
