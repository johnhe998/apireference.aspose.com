---
title: PdfSaveOptions.UseBookFoldPrintingSettings
second_title: Aspose.Words für .NET-API-Referenz
description: PdfSaveOptions eigendom. Erhält oder setzt einen booleschen Wert der angibt ob das Dokument mit einem Broschürendrucklayout gespeichert werden soll  wenn dies über angegeben wirdMultiplePages .
type: docs
weight: 270
url: /de/net/aspose.words.saving/pdfsaveoptions/usebookfoldprintingsettings/
---
## PdfSaveOptions.UseBookFoldPrintingSettings property

Erhält oder setzt einen booleschen Wert, der angibt, ob das Dokument mit einem Broschürendrucklayout gespeichert werden soll, , wenn dies über angegeben wird[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### Bemerkungen

Wenn diese Option angegeben ist,[`PageSet`](../../fixedpagesaveoptions/pageset/) wird beim Speichern ignoriert. Dieses Verhalten entspricht MS Word. Wenn in der Seiteneinrichtung keine Buchfalzdruckeinstellungen angegeben sind, hat diese Option keine Auswirkung.

### Beispiele

Zeigt, wie ein Dokument im PDF-Format in Form einer Buchfaltung gespeichert wird.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Erstellen Sie ein "PdfSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .PDF konvertiert.
PdfSaveOptions options = new PdfSaveOptions();

// Setzen Sie die Eigenschaft "UseBookFoldPrintingSettings" auf "true", um den Inhalt anzuordnen
// in der Ausgabe-PDF so, dass wir daraus eine Broschüre erstellen können.
// Legen Sie die Eigenschaft "UseBookFoldPrintingSettings" auf "false" fest, um das PDF normal zu rendern.
options.UseBookFoldPrintingSettings = renderTextAsBookfold;

// Wenn wir das Dokument als Booklet rendern, müssen wir "MultiplePages" setzen
// Eigenschaften der Seiteneinrichtungsobjekte aller Abschnitte auf "MultiplePagesType.BookFoldPrinting".
if (renderTextAsBookfold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// Sobald wir dieses Dokument auf beiden Seiten der Seiten drucken, können wir alle Seiten auf einmal in der Mitte falten,
// und der Inhalt wird so ausgerichtet, dass eine Broschüre entsteht.
doc.Save(ArtifactsDir + "PdfSaveOptions.SaveAsPdfBookFold.pdf", options);
```

### Siehe auch

* class [PdfSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../pdfsaveoptions/)
* Montage [Aspose.Words](../../../)


