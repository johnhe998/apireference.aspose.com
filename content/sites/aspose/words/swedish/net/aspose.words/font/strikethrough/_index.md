---
title: Font.StrikeThrough
second_title: Aspose.Words för .NET API Referens
description: Font fast egendom. Sant om teckensnittet är formaterat som genomstruken text.
type: docs
weight: 390
url: /sv/net/aspose.words/font/strikethrough/
---
## Font.StrikeThrough property

Sant om teckensnittet är formaterat som genomstruken text.

```csharp
public bool StrikeThrough { get; set; }
```

### Exempel

Visar hur man lägger till en rad genomstruken i text.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

Run run = new Run(doc, "Text with a single-line strikethrough.");
run.Font.StrikeThrough = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

run = new Run(doc, "Text with a double-line strikethrough.");
run.Font.DoubleStrikeThrough = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.StrikeThrough.docx");
```

### Se även

* class [Font](../)
* namnutrymme [Aspose.Words](../../font/)
* hopsättning [Aspose.Words](../../../)


