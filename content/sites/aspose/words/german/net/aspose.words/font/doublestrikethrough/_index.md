---
title: Font.DoubleStrikeThrough
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. True wenn die Schriftart als doppelt durchgestrichener Text formatiert ist.
type: docs
weight: 90
url: /de/net/aspose.words/font/doublestrikethrough/
---
## Font.DoubleStrikeThrough property

True, wenn die Schriftart als doppelt durchgestrichener Text formatiert ist.

```csharp
public bool DoubleStrikeThrough { get; set; }
```

### Beispiele

Zeigt, wie Text durchgestrichen wird.

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

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


