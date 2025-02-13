---
title: Enum DropCapPosition
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.DropCapPosition opsomming. Gibt die Position für einen Initialtext an.
type: docs
weight: 1260
url: /de/net/aspose.words/dropcapposition/
---
## DropCapPosition enumeration

Gibt die Position für einen Initialtext an.

```csharp
public enum DropCapPosition
```

### Werte

| Name | Wert | Beschreibung |
| --- | --- | --- |
| None | `0` | Der Absatz hat kein Initial. |
| Normal | `1` | Die Initiale wird innerhalb des Textrandes des Ankerabsatzes positioniert. |
| Margin | `2` | Die Initiale wird außerhalb des Textrandes im Ankerabsatz positioniert. |

### Beispiele

Zeigt, wie eine Initiale erstellt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Einen Absatz mit einem großen Buchstaben einfügen, mit dem der Text im zweiten und dritten Absatz beginnt.
builder.Font.Size = 54;
builder.Writeln("L");

builder.Font.Size = 18;
builder.Writeln("orem ipsum dolor sit amet, consectetur adipiscing elit, " +
                "sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. ");
builder.Writeln("Ut enim ad minim veniam, quis nostrud exercitation " +
                "ullamco laboris nisi ut aliquip ex ea commodo consequat.");

// Derzeit erscheinen der zweite und der dritte Absatz unter dem ersten.
// Wir können den ersten Absatz über sein "ParagraphFormat"-Objekt als Initiale für die anderen Absätze konvertieren.
// Legen Sie die Eigenschaft "DropCapPosition" auf "DropCapPosition.Margin" fest, um die Initiale zu platzieren
// außerhalb des linken Seitenrandes, wenn unser Text von links nach rechts geschrieben wird.
// Legen Sie die Eigenschaft "DropCapPosition" auf "DropCapPosition.Normal" fest, um die Initiale innerhalb der Seitenränder zu platzieren
// und um den Rest des Textes darum zu wickeln.
// "DropCapPosition.None" ist der Standardzustand für alle Absätze.
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.DropCapPosition = dropCapPosition;

doc.Save(ArtifactsDir + "ParagraphFormat.DropCap.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


