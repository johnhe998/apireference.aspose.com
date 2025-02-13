---
title: OutlineOptions.CreateOutlinesForHeadingsInTables
second_title: Aspose.Words für .NET-API-Referenz
description: OutlineOptions eigendom. Gibt an ob Gliederungen für Überschriften Absätze die mit den Überschriftenstilen formatiert wurden innerhalb von Tabellen erstellt werden sollen oder nicht.
type: docs
weight: 40
url: /de/net/aspose.words.saving/outlineoptions/createoutlinesforheadingsintables/
---
## OutlineOptions.CreateOutlinesForHeadingsInTables property

Gibt an, ob Gliederungen für Überschriften (Absätze, die mit den Überschriftenstilen formatiert wurden) innerhalb von Tabellen erstellt werden sollen oder nicht.

```csharp
public bool CreateOutlinesForHeadingsInTables { get; set; }
```

### Bemerkungen

Standardwert ist **FALSCH**.

### Beispiele

Zeigt, wie Gliederungseinträge in PDF-Dokumenten für Überschriften in Tabellen erstellt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine Tabelle mit drei Zeilen. Die erste Reihe,
// dessen Text wir in einem Überschriftenstil formatieren, dient als Spaltenüberschrift.
builder.StartTable();
builder.InsertCell();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("Customers");
builder.EndRow();
builder.InsertCell();
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Normal;
builder.Write("John Doe");
builder.EndRow();
builder.InsertCell();
builder.Write("Jane Doe");
builder.EndTable();

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();

// Das ausgegebene PDF-Dokument enthält eine Gliederung, die ein Inhaltsverzeichnis ist, das Überschriften im Dokumentkörper auflistet.
// Durch Klicken auf einen Eintrag in dieser Gliederung gelangen wir zur Position der entsprechenden Überschrift.
// Setzen Sie die Eigenschaft "HeadingsOutlineLevels" auf "1", um die Gliederung zu erhalten
// um nur Überschriften mit Überschriftenebenen zu registrieren, die nicht größer als 1 sind.
pdfSaveOptions.OutlineOptions.HeadingsOutlineLevels = 1;

// Setzen Sie die Eigenschaft "CreateOutlinesForHeadingsInTables" auf "false", um alle Überschriften in Tabellen auszuschließen,
// wie die, die wir oben aus der Gliederung erstellt haben.
// Setzen Sie die Eigenschaft "CreateOutlinesForHeadingsInTables" auf "true", um alle Überschriften in Tabellen einzuschließen
// in der Gliederung, sofern sie eine Überschriftenebene haben, die nicht größer ist als der Wert der Eigenschaft "HeadingsOutlineLevels".
pdfSaveOptions.OutlineOptions.CreateOutlinesForHeadingsInTables = createOutlinesForHeadingsInTables;

doc.Save(ArtifactsDir + "PdfSaveOptions.TableHeadingOutlines.pdf", pdfSaveOptions);
```

### Siehe auch

* class [OutlineOptions](../)
* namensraum [Aspose.Words.Saving](../../outlineoptions/)
* Montage [Aspose.Words](../../../)


