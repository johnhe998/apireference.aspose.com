---
title: XpsSaveOptions.UseBookFoldPrintingSettings
second_title: Aspose.Words für .NET-API-Referenz
description: XpsSaveOptions eigendom. Erhält oder setzt einen booleschen Wert der angibt ob das Dokument mit einem Broschürendrucklayout gespeichert werden soll  wenn dies über angegeben wirdMultiplePages .
type: docs
weight: 40
url: /de/net/aspose.words.saving/xpssaveoptions/usebookfoldprintingsettings/
---
## XpsSaveOptions.UseBookFoldPrintingSettings property

Erhält oder setzt einen booleschen Wert, der angibt, ob das Dokument mit einem Broschürendrucklayout gespeichert werden soll, , wenn dies über angegeben wird[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### Bemerkungen

Wenn diese Option angegeben ist,[`PageSet`](../../fixedpagesaveoptions/pageset/) wird beim Speichern ignoriert. Dieses Verhalten entspricht MS Word. Wenn in der Seiteneinrichtung keine Buchfalzdruckeinstellungen angegeben sind, hat diese Option keine Auswirkung.

### Beispiele

Zeigt, wie ein Dokument im XPS-Format in Form einer Buchfaltung gespeichert wird.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Erstellen Sie ein "XpsSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
// um zu ändern, wie diese Methode das Dokument in .XPS konvertiert.
XpsSaveOptions xpsOptions = new XpsSaveOptions(SaveFormat.Xps);

// Setzen Sie die Eigenschaft "UseBookFoldPrintingSettings" auf "true", um den Inhalt anzuordnen
// im Ausgabe-XPS so, dass wir daraus eine Broschüre erstellen können.
// Legen Sie die Eigenschaft "UseBookFoldPrintingSettings" auf "false" fest, um das XPS normal zu rendern.
xpsOptions.UseBookFoldPrintingSettings = renderTextAsBookFold;

// Wenn wir das Dokument als Booklet rendern, müssen wir "MultiplePages" setzen
// Eigenschaften der Seiteneinrichtungsobjekte aller Abschnitte auf "MultiplePagesType.BookFoldPrinting".
if (renderTextAsBookFold)
    foreach (Section s in doc.Sections)
    {
        s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
    }

// Sobald wir dieses Dokument gedruckt haben, können wir es in eine Broschüre verwandeln, indem wir die Seiten stapeln
// aus dem Drucker kommen und in der Mitte falten.
doc.Save(ArtifactsDir + "XpsSaveOptions.BookFold.xps", xpsOptions);
```

### Siehe auch

* class [XpsSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../xpssaveoptions/)
* Montage [Aspose.Words](../../../)


