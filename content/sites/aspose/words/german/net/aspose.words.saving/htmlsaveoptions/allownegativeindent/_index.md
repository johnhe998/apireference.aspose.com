---
title: HtmlSaveOptions.AllowNegativeIndent
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlSaveOptions eigendom. Gibt an ob negative linke und rechte Einzüge von Absätzen beim Speichern in HTML MHTML oder EPUB normalisiert werden. Standardwert istFALSCH .
type: docs
weight: 20
url: /de/net/aspose.words.saving/htmlsaveoptions/allownegativeindent/
---
## HtmlSaveOptions.AllowNegativeIndent property

Gibt an, ob negative linke und rechte Einzüge von Absätzen beim Speichern in HTML, MHTML oder EPUB normalisiert werden. Standardwert ist`FALSCH` .

```csharp
public bool AllowNegativeIndent { get; set; }
```

### Bemerkungen

Wenn ein negativer Einzug nicht zulässig ist, wird er als Nullrand nach HTML exportiert. Wenn ein negativer Einzug zulässig ist, wird ein Absatz möglicherweise teilweise außerhalb des -Browserfensters angezeigt.

### Beispiele

Zeigt, wie negative Einzüge in der HTML-Ausgabe beibehalten werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügt eine Tabelle mit negativem Einzug ein, wodurch sie nach links über die linke Seitengrenze hinaus verschoben wird.
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, Cell 1");
builder.InsertCell();
builder.Write("Row 1, Cell 2");
builder.EndTable();
table.LeftIndent = -36;
table.PreferredWidth = PreferredWidth.FromPoints(144);

builder.InsertBreak(BreakType.ParagraphBreak);

// Füge eine Tabelle mit positivem Einzug ein, wodurch die Tabelle nach rechts verschoben wird.
table = builder.StartTable();
builder.InsertCell();
builder.Write("Row 1, Cell 1");
builder.InsertCell();
builder.Write("Row 1, Cell 2");
builder.EndTable();
table.LeftIndent = 36;
table.PreferredWidth = PreferredWidth.FromPoints(144);

// Wenn wir ein Dokument in HTML speichern, behält Aspose.Words nur negative Einzüge bei
// wie die, die wir auf die erste Tabelle angewendet haben, wenn wir das "AllowNegativeIndent"-Flag gesetzt haben
// in einem SaveOptions-Objekt, das wir an "true" übergeben.
HtmlSaveOptions options = new HtmlSaveOptions(SaveFormat.Html)
{
    AllowNegativeIndent = allowNegativeIndent,
    TableWidthOutputMode = HtmlElementSizeOutputMode.RelativeOnly
};

doc.Save(ArtifactsDir + "HtmlSaveOptions.NegativeIndent.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.NegativeIndent.html");

if (allowNegativeIndent)
{
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:-41.65pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:30.35pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
    Assert.True(outDocContents.Contains(
        "<table cellspacing=\"0\" cellpadding=\"0\" style=\"margin-left:30.35pt; border:0.75pt solid #000000; -aw-border:0.5pt single; -aw-border-insideh:0.5pt single #000000; -aw-border-insidev:0.5pt single #000000; border-collapse:collapse\">"));
}
```

### Siehe auch

* class [HtmlSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlsaveoptions/)
* Montage [Aspose.Words](../../../)


