---
title: Font.AllCaps
second_title: Aspose.Words für .NET-API-Referenz
description: Font eigendom. Wahr wenn die Schriftart ausschließlich in Großbuchstaben formatiert ist.
type: docs
weight: 10
url: /de/net/aspose.words/font/allcaps/
---
## Font.AllCaps property

Wahr, wenn die Schriftart ausschließlich in Großbuchstaben formatiert ist.

```csharp
public bool AllCaps { get; set; }
```

### Beispiele

Zeigt, wie ein Lauf formatiert wird, um seinen Inhalt in Großbuchstaben anzuzeigen.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// Es gibt zwei Möglichkeiten, einen Lauf dazu zu bringen, seinen Kleinbuchstaben in Großbuchstaben anzuzeigen, ohne den Inhalt zu ändern.
// 1 - Setzen Sie das AllCaps-Flag, um alle Zeichen in normalen Großbuchstaben anzuzeigen:
Run run = new Run(doc, "all capitals");
run.Font.AllCaps = true;
para.AppendChild(run);

para = (Paragraph)para.ParentNode.AppendChild(new Paragraph(doc));

// 2 - Setzen Sie das SmallCaps-Flag, um alle Zeichen in Kapitälchen anzuzeigen:
// Wenn ein Zeichen klein geschrieben ist, wird es in seiner Großbuchstabenform angezeigt
// hat aber dieselbe Höhe wie der Kleinbuchstabe (die x-Höhe der Schriftart).
// Zeichen, die ursprünglich in Großbuchstaben geschrieben waren, sehen gleich aus.
run = new Run(doc, "Small Capitals");
run.Font.SmallCaps = true;
para.AppendChild(run);

doc.Save(ArtifactsDir + "Font.Caps.docx");
```

### Siehe auch

* class [Font](../)
* namensraum [Aspose.Words](../../font/)
* Montage [Aspose.Words](../../../)


