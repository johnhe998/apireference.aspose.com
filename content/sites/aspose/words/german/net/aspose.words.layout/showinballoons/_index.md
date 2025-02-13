---
title: Enum ShowInBalloons
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Layout.ShowInBalloons opsomming. Gibt an welche Revisionen in Sprechblasen gerendert werden.
type: docs
weight: 3210
url: /de/net/aspose.words.layout/showinballoons/
---
## ShowInBalloons enumeration

Gibt an, welche Revisionen in Sprechblasen gerendert werden.

```csharp
public enum ShowInBalloons
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Rendert eingefügte, gelöschte und formatierte Überarbeitungen inline. |
| Format | `1` | Rendert eingefügte und gelöschte Überarbeitungen inline, formatiert Überarbeitungen in Sprechblasen. |
| FormatAndDelete | `2` | Rendert eingefügte Überarbeitungen inline, löscht und formatiert Überarbeitungen in Sprechblasen. |

### Bemerkungen

Beachten Sie, dass Überarbeitungen nicht in Sprechblasen für gerendert werdenShowInAnnotations .

### Beispiele

Zeigt, wie das Erscheinungsbild von Revisionen geändert wird.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

// Abrufen des RevisionOptions-Objekts, das die Darstellung von Revisionen steuert.
RevisionOptions revisionOptions = doc.LayoutOptions.RevisionOptions;

// Einfügungsrevisionen in grün und kursiv darstellen.
revisionOptions.InsertedTextColor = RevisionColor.Green;
revisionOptions.InsertedTextEffect = RevisionTextEffect.Italic;

// Löschrevisionen rot und fett darstellen.
revisionOptions.DeletedTextColor = RevisionColor.Red;
revisionOptions.DeletedTextEffect = RevisionTextEffect.Bold;

// Derselbe Text erscheint zweimal in einer Bewegungsrevision:
// einmal am Abfahrtsort und einmal am Zielort.
// Rendern Sie den Text an der verschobenen Revision gelb mit einem doppelten Durchstrich
// und doppelt unterstrichen blau bei der verschobenen Revision.
revisionOptions.MovedFromTextColor = RevisionColor.Yellow;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleStrikeThrough;
revisionOptions.MovedToTextColor = RevisionColor.Blue;
revisionOptions.MovedFromTextEffect = RevisionTextEffect.DoubleUnderline;

// Überarbeitungen des Formats in dunkelrot und fett darstellen.
revisionOptions.RevisedPropertiesColor = RevisionColor.DarkRed;
revisionOptions.RevisedPropertiesEffect = RevisionTextEffect.Bold;

// Platzieren Sie einen dicken dunkelblauen Balken auf der linken Seite der Seite neben Zeilen, die von Überarbeitungen betroffen sind.
revisionOptions.RevisionBarsColor = RevisionColor.DarkBlue;
revisionOptions.RevisionBarsWidth = 15.0f;

// Überarbeitungsmarkierungen und Originaltext anzeigen.
revisionOptions.ShowOriginalRevision = true;
revisionOptions.ShowRevisionMarks = true;

// Erhalten Sie Verschiebungen, Löschungen, Formatierungsüberarbeitungen und Kommentare, die in grünen Sprechblasen angezeigt werden
// auf der rechten Seite der Seite.
revisionOptions.ShowInBalloons = ShowInBalloons.Format;
revisionOptions.CommentColor = RevisionColor.BrightGreen;

// Diese Funktionen gelten nur für Formate wie .pdf oder .jpg.
doc.Save(ArtifactsDir + "Revision.RevisionOptions.pdf");
```

### Siehe auch

* namensraum [Aspose.Words.Layout](../../aspose.words.layout/)
* Montage [Aspose.Words](../../)


