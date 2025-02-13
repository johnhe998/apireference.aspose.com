---
title: PageSetup.EndnoteOptions
second_title: Aspose.Words für .NET-API-Referenz
description: PageSetup eigendom. Stellt Optionen bereit die die Nummerierung und Positionierung von Endnoten in diesem Abschnitt steuern.
type: docs
weight: 120
url: /de/net/aspose.words/pagesetup/endnoteoptions/
---
## PageSetup.EndnoteOptions property

Stellt Optionen bereit, die die Nummerierung und Positionierung von Endnoten in diesem Abschnitt steuern.

```csharp
public EndnoteOptions EndnoteOptions { get; }
```

### Beispiele

Zeigt, wie Optionen konfiguriert werden, die sich auf Fußnoten/Endnoten in einem Abschnitt auswirken.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Hello world!");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote reference text.");

// Konfigurieren Sie alle Fußnoten im ersten Abschnitt, um die Nummerierung wieder bei 1 zu beginnen
// auf jeder neuen Seite und zeigen sich auf jeder Seite direkt unter dem Text an.
FootnoteOptions footnoteOptions = doc.Sections[0].PageSetup.FootnoteOptions;
footnoteOptions.Position = FootnotePosition.BeneathText;
footnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
footnoteOptions.StartNumber = 1;

builder.Write(" Hello again.");
builder.InsertFootnote(FootnoteType.Footnote, "Endnote reference text.");

// Alle Endnoten im ersten Abschnitt konfigurieren, um eine kontinuierliche Zählung im gesamten Abschnitt beizubehalten,
// beginnend bei 1. Stellen Sie außerdem ein, dass alle gesammelt am Ende des Dokuments angezeigt werden.
EndnoteOptions endnoteOptions = doc.Sections[0].PageSetup.EndnoteOptions;
endnoteOptions.Position = EndnotePosition.EndOfDocument;
endnoteOptions.RestartRule = FootnoteNumberingRule.Continuous;
endnoteOptions.StartNumber = 1;

doc.Save(ArtifactsDir + "PageSetup.FootnoteOptions.docx");
```

### Siehe auch

* class [EndnoteOptions](../../../aspose.words.notes/endnoteoptions/)
* class [PageSetup](../)
* namensraum [Aspose.Words](../../pagesetup/)
* Montage [Aspose.Words](../../../)


