---
title: PageSetup.CharactersPerLine
second_title: Aspose.Words für .NET-API-Referenz
description: PageSetup eigendom. Ruft die Anzahl der Zeichen pro Zeile im Dokumentraster ab oder legt sie fest.
type: docs
weight: 100
url: /de/net/aspose.words/pagesetup/charactersperline/
---
## PageSetup.CharactersPerLine property

Ruft die Anzahl der Zeichen pro Zeile im Dokumentraster ab oder legt sie fest.

```csharp
public int CharactersPerLine { get; set; }
```

### Bemerkungen

Der Mindestwert der Eigenschaft ist 1. Der Höchstwert hängt von der Seitenbreite und der Schriftgröße des Stils Normal ab. Der minimale Zeichenabstand beträgt 90 Prozent der Schriftgröße. Beispielsweise beträgt die maximale Anzahl von Zeichen pro Zeile einer Letter-Seite mit 1-Zoll-Rändern 43.

Standardmäßig hat die Eigenschaft einen Wert, bei dem der Zeichenabstand gleich der Schriftgröße des Stils Normal ist.

### Beispiele

Zeigt, wie man a für die Anzahl der Zeichen angibt, die jede Zeile haben darf.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Aktivieren Sie Pitching und verwenden Sie es dann, um die Anzahl der Zeichen pro Zeile in diesem Abschnitt festzulegen.
builder.PageSetup.LayoutMode = SectionLayoutMode.Grid;
builder.PageSetup.CharactersPerLine = 10;

// Die Anzahl der Zeichen hängt auch von der Schriftgröße ab.
doc.Styles["Normal"].Font.Size = 20;

Assert.AreEqual(8, doc.FirstSection.PageSetup.CharactersPerLine);

builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.");

doc.Save(ArtifactsDir + "PageSetup.CharactersPerLine.docx");
```

### Siehe auch

* class [PageSetup](../)
* namensraum [Aspose.Words](../../pagesetup/)
* Montage [Aspose.Words](../../../)


