---
title: Enum TxtLeadingSpacesOptions
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Loading.TxtLeadingSpacesOptions opsomming. Gibt verfügbare Optionen für die Behandlung von führenden Leerzeichen während des Imports von anText Datei.
type: docs
weight: 3520
url: /de/net/aspose.words.loading/txtleadingspacesoptions/
---
## TxtLeadingSpacesOptions enumeration

Gibt verfügbare Optionen für die Behandlung von führenden Leerzeichen während des Imports von anText Datei.

```csharp
public enum TxtLeadingSpacesOptions
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| ConvertToIndent | `0` |  |
| Trim | `1` |  |
| Preserve | `2` |  |

### Beispiele

Zeigt, wie Leerzeichen beim Laden von Klartextdokumenten entfernt werden.

```csharp
string textDoc = "      Line 1 \n" +
                 "    Line 2   \n" +
                 " Line 3       ";

// Erstellen Sie ein "TxtLoadOptions"-Objekt, das wir an den Konstruktor eines Dokuments übergeben können
// um zu ändern, wie wir ein Klartextdokument laden.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Setzen Sie die Eigenschaft "LeadingSpacesOptions" auf "TxtLeadingSpacesOptions.Preserve"
// um alle Leerzeichen am Anfang jeder Zeile beizubehalten.
// Setzen Sie die Eigenschaft "LeadingSpacesOptions" auf "TxtLeadingSpacesOptions.ConvertToIndent"
// um alle Leerzeichen am Anfang jeder Zeile zu entfernen,
// und wenden Sie dann einen linken ersten Zeileneinzug auf den Absatz an, um die Wirkung der Leerzeichen zu simulieren.
// Setzen Sie die Eigenschaft "LeadingSpacesOptions" auf "TxtLeadingSpacesOptions.Trim"
// um alle Leerzeichen am Anfang jeder Zeile zu entfernen.
loadOptions.LeadingSpacesOptions = txtLeadingSpacesOptions;

// Setzen Sie die Eigenschaft "TrailingSpacesOptions" auf "TxtTrailingSpacesOptions.Preserve"
// um alle Leerzeichen am Ende jeder Zeile beizubehalten. 
// Legen Sie die Eigenschaft „TrailingSpacesOptions“ auf „TxtTrailingSpacesOptions.Trim“ fest 
// Alle Leerzeichen am Ende jeder Zeile entfernen.
loadOptions.TrailingSpacesOptions = txtTrailingSpacesOptions;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

switch (txtLeadingSpacesOptions)
{
    case TxtLeadingSpacesOptions.ConvertToIndent:
        Assert.AreEqual(37.8d, paragraphs[0].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(25.2d, paragraphs[1].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(6.3d, paragraphs[2].ParagraphFormat.FirstLineIndent);

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
    case TxtLeadingSpacesOptions.Preserve:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("      Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("    Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith(" Line 3"));
        break;
    case TxtLeadingSpacesOptions.Trim:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
}

switch (txtTrailingSpacesOptions)
{
    case TxtTrailingSpacesOptions.Preserve:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1 \r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2   \r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3       \f"));
        break;
    case TxtTrailingSpacesOptions.Trim:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1\r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2\r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3\f"));
        break;
}
```

### Siehe auch

* namensraum [Aspose.Words.Loading](../../aspose.words.loading/)
* Montage [Aspose.Words](../../)


