---
title: Enum RevisionColor
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Layout.RevisionColor uppräkning. Gör det möjligt att ange färg på dokumentrevisioner.
type: docs
weight: 3180
url: /sv/net/aspose.words.layout/revisioncolor/
---
## RevisionColor enumeration

Gör det möjligt att ange färg på dokumentrevisioner.

```csharp
public enum RevisionColor
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Auto | `0` | Standard. |
| Black | `1` | Representerar 000000 färg. |
| Blue | `2` | Representerar 2e97d3 färg. |
| BrightGreen | `3` | Representerar 84a35b färg. |
| ClassicBlue | `4` | Representerar 0000ff färg. |
| ClassicRed | `5` | Representerar ff0000 färg. |
| DarkBlue | `6` | Representerar 376e96 färg. |
| DarkRed | `7` | Representerar 881824 färg. |
| DarkYellow | `8` | Representerar e09a2b färg. |
| Gray25 | `9` | Representerar a0a3a9 färg. |
| Gray50 | `10` | Representerar 50565e färg. |
| Green | `11` | Representerar 2c6234 färg. |
| Pink | `12` | Representerar ce338f färg. |
| Red | `13` | Representerar b5082e color. |
| Teal | `14` | Representerar 1b9cab-färg. |
| Turquoise | `15` | Representerar 3eafc2 färg. |
| Violet | `16` | Representerar 633277 färg. |
| White | `17` | Representerar ffffff färg. |
| Yellow | `18` | Representerar fad272-färg. |
| NoHighlight | `19` | Ingen färg används för att markera revisionsändringar. |
| ByAuthor | `20` | Revisioner av varje författare får sin egen färg för framhävning från en fördefinierad uppsättning högkontrastfärger. |

### Exempel

Visar hur man ändrar utseendet på revisioner i ett renderat utdatadokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en revision och ändra sedan färgen på alla versioner till grön.
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// Ta bort stapeln som visas till vänster om varje reviderad rad.
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### Se även

* namnutrymme [Aspose.Words.Layout](../../aspose.words.layout/)
* hopsättning [Aspose.Words](../../)


