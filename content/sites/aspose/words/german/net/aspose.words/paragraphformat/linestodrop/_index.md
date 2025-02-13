---
title: ParagraphFormat.LinesToDrop
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Ruft die Anzahl der Zeilen des Absatztexts ab oder legt sie fest die zum Berechnen der Initialhöhe verwendet werden.
type: docs
weight: 200
url: /de/net/aspose.words/paragraphformat/linestodrop/
---
## ParagraphFormat.LinesToDrop property

Ruft die Anzahl der Zeilen des Absatztexts ab oder legt sie fest, die zum Berechnen der Initialhöhe verwendet werden.

```csharp
public int LinesToDrop { get; set; }
```

### Beispiele

Zeigt, wie die Größe einer Initiale festgelegt wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ändern Sie die Eigenschaft "LinesToDrop", um einen Absatz als Initiale festzulegen,
// wodurch daraus ein großer Großbuchstabe wird, der den nächsten Absatz schmückt.
// Geben Sie dieser Eigenschaft den Wert 4, um der Initiale die Höhe von vier Textzeilen zu geben.
builder.ParagraphFormat.LinesToDrop = 4;
builder.Writeln("H");

// Setzen Sie die Eigenschaft "LinesToDrop" auf 0 zurück, um den nächsten Absatz in einen normalen Absatz umzuwandeln.
// Der Text in diesem Absatz wird um die Initiale herumgeführt.
builder.ParagraphFormat.LinesToDrop = 0;
builder.Writeln("ello world!");

doc.Save(ArtifactsDir + "ParagraphFormat.LinesToDrop.odt");
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


