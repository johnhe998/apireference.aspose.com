---
title: Enum RevisionColor
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Layout.RevisionColor opsomming. Ermöglicht die Angabe der Farbe von Dokumentrevisionen.
type: docs
weight: 3180
url: /de/net/aspose.words.layout/revisioncolor/
---
## RevisionColor enumeration

Ermöglicht die Angabe der Farbe von Dokumentrevisionen.

```csharp
public enum RevisionColor
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| Auto | `0` | Standard. |
| Black | `1` | Repräsentiert 000000 Farbe. |
| Blue | `2` | steht für die Farbe 2e97d3. |
| BrightGreen | `3` | Steht für die Farbe 84a35b. |
| ClassicBlue | `4` | Steht für die Farbe 0000ff. |
| ClassicRed | `5` | Repräsentiert die Farbe ff0000. |
| DarkBlue | `6` | Repräsentiert die Farbe 376e96. |
| DarkRed | `7` | Repräsentiert 881824 Farbe. |
| DarkYellow | `8` | Steht für die Farbe e09a2b. |
| Gray25 | `9` | Repräsentiert die Farbe a0a3a9. |
| Gray50 | `10` | Repräsentiert die Farbe 50565e. |
| Green | `11` | Repräsentiert die Farbe 2c6234. |
| Pink | `12` | Steht für ce338f-Farbe. |
| Red | `13` | Steht für b5082e-Farbe. |
| Teal | `14` | Steht für 1b9cab-Farbe. |
| Turquoise | `15` | Repräsentiert 3eafc2-Farbe. |
| Violet | `16` | Repräsentiert 633277 Farbe. |
| White | `17` | Steht für ffffff-Farbe. |
| Yellow | `18` | Repräsentiert die Modefarbe 272. |
| NoHighlight | `19` | Es wird keine Farbe verwendet, um Revisionsänderungen hervorzuheben. |
| ByAuthor | `20` | Überarbeitungen jedes Autors erhalten ihre eigene Farbe zum Hervorheben aus einem vordefinierten Satz kontrastreicher Farben. |

### Beispiele

Zeigt, wie das Erscheinungsbild von Revisionen in einem gerenderten Ausgabedokument geändert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Eine Revision einfügen, dann die Farbe aller Revisionen auf Grün ändern.
builder.Writeln("This is not a revision.");
doc.StartTrackRevisions("John Doe", DateTime.Now);
builder.Writeln("This is a revision.");
doc.StopTrackRevisions();
builder.Writeln("This is not a revision.");

// Entfernen Sie den Balken, der links von jeder überarbeiteten Zeile erscheint.
doc.LayoutOptions.RevisionOptions.InsertedTextColor = RevisionColor.BrightGreen;
doc.LayoutOptions.RevisionOptions.ShowRevisionBars = false;

doc.Save(ArtifactsDir + "Document.LayoutOptionsRevisions.pdf");
```

### Siehe auch

* namensraum [Aspose.Words.Layout](../../aspose.words.layout/)
* Montage [Aspose.Words](../../)


