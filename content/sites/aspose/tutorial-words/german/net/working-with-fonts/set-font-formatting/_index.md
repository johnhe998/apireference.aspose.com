---
title: Legen Sie die Schriftartformatierung fest
linktitle: Legen Sie die Schriftartformatierung fest
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Schriftartformatierung in Word-Dokumenten festlegen und attraktive Dokumente erstellen.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-font-formatting/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Schriftartformatierung in einem Word-Dokument festlegen. Sie erfahren, wie Sie Stile wie Fettdruck, Farbe, Kursivschrift, Schriftart, Größe, Abstand und Unterstreichung anwenden.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Legen Sie zunächst den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments fest. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen und formatieren Sie das Dokument
 Erstellen Sie eine Instanz von`Document` Klasse und die`DocumentBuilder` Klasse zum Erstellen des Dokuments. Benutzen Sie die`Font` Eigentum der`DocumentBuilder` , um auf die Eigenschaften der Schriftartformatierung zuzugreifen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## Schritt 3: Speichern Sie das Dokument
 Benutzen Sie die`Save` Methode zum Speichern des Dokuments mit der angewendeten Schriftartformatierung. Ersetzen`"WorkingWithFonts.SetFontFormatting.docx"` mit dem gewünschten Dateinamen.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### Beispielquellcode zum Festlegen der Schriftartformatierung mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## Abschluss
Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie mit Aspose.Words für .NET die Schriftartformatierung in einem Word-Dokument festlegen. Sie können weitere Schriftartformatierungsoptionen erkunden und personalisierte und attraktive Word-Dokumente erstellen.
