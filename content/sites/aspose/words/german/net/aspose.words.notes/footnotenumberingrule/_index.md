---
title: Enum FootnoteNumberingRule
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Notes.FootnoteNumberingRule opsomming. Legt fest wann die automatische Fußnoten oder Endnotennummerierung neu gestartet wird.
type: docs
weight: 4030
url: /de/net/aspose.words.notes/footnotenumberingrule/
---
## FootnoteNumberingRule enumeration

Legt fest, wann die automatische Fußnoten- oder Endnotennummerierung neu gestartet wird.

```csharp
public enum FootnoteNumberingRule
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Continuous | `0` | Durchgehende Nummerierung im gesamten Dokument. |
| RestartSection | `1` | Die Nummerierung beginnt bei jedem Abschnitt neu. |
| RestartPage | `2` | Die Nummerierung beginnt auf jeder Seite neu. Nur für Fußnoten gültig. |
| Default | `0` | GleichContinuous . |

### Beispiele

Zeigt, wie Sie die Fußnoten-/Endnotennummerierung an bestimmten Stellen im Dokument neu starten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fußnoten und Endnoten sind eine Möglichkeit, eine Referenz oder einen Nebenkommentar an Text anzuhängen
// das den Fluss des Haupttextes nicht stört. 
// Das Einfügen einer Fußnote/Endnote fügt ein kleines hochgestelltes Referenzsymbol hinzu
// am Haupttext, wo wir die Fußnote/Endnote einfügen.
// Jede Fußnote/Endnote erzeugt auch einen Eintrag, der aus einem zur Referenz passenden Symbol besteht
// Symbol im Haupttext. Der Referenztext, den wir an die „InsertEndnote“-Methode des Dokumenterstellers übergeben.
// Fußnoteneinträge werden standardmäßig unten auf jeder Seite angezeigt, die enthält
// ihre Referenzsymbole und Endnoten erscheinen am Ende des Dokuments.
builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 2.");
builder.InsertBreak(BreakType.PageBreak);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Footnote, "Footnote 4.");

builder.InsertBreak(BreakType.PageBreak);

builder.Write("Text 1. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 1.");
builder.Write("Text 2. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 2.");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Text 3. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 3.");
builder.Write("Text 4. ");
builder.InsertFootnote(FootnoteType.Endnote, "Endnote 4.");

// Standardmäßig ist das Referenzsymbol für jede Fußnote und Endnote ihr Index
// unter allen Fußnoten/Endnoten des Dokuments. Jedes Dokument behält separate Zählungen bei
// für Fußnoten und Endnoten und startet diese Zählungen an keiner Stelle neu.
Assert.AreEqual(doc.FootnoteOptions.RestartRule, FootnoteNumberingRule.Default);
Assert.AreEqual(FootnoteNumberingRule.Default, FootnoteNumberingRule.Continuous);

// Wir können die Eigenschaft "RestartRule" verwenden, um das Dokument neu zu starten
// die Fußnote/Endnote zählt auf einer neuen Seite oder einem neuen Abschnitt.
doc.FootnoteOptions.RestartRule = FootnoteNumberingRule.RestartPage;
doc.EndnoteOptions.RestartRule = FootnoteNumberingRule.RestartSection;

doc.Save(ArtifactsDir + "InlineStory.NumberingRule.docx");
```

### Siehe auch

* class [FootnoteOptions](../footnoteoptions/)
* class [EndnoteOptions](../endnoteoptions/)
* namensraum [Aspose.Words.Notes](../../aspose.words.notes/)
* Montage [Aspose.Words](../../)


