---
title: PageSavingArgs.KeepPageStreamOpen
second_title: Aspose.Words für .NET-API-Referenz
description: PageSavingArgs eigendom. Gibt an ob Aspose.Words den Stream offen halten oder nach dem Speichern einer Dokumentseite schließen soll.
type: docs
weight: 20
url: /de/net/aspose.words.saving/pagesavingargs/keeppagestreamopen/
---
## PageSavingArgs.KeepPageStreamOpen property

Gibt an, ob Aspose.Words den Stream offen halten oder nach dem Speichern einer Dokumentseite schließen soll.

```csharp
public bool KeepPageStreamOpen { get; set; }
```

### Bemerkungen

Standard ist`FALSCH` und Aspose.Words schließt den von Ihnen bereitgestellten Stream in der[`PageStream`](../pagestream/) Eigenschaft, nachdem eine Dokumentseite hineingeschrieben wurde. Angeben`Stimmt` um den Strom offen zu halten.

### Beispiele

Zeigt, wie ein Callback verwendet wird, um ein Dokument Seite für Seite im HTML-Format zu speichern.

```csharp
public void PageFileNames()
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    builder.Writeln("Page 1.");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 2.");
    builder.InsertImage(ImageDir + "Logo.jpg");
    builder.InsertBreak(BreakType.PageBreak);
    builder.Writeln("Page 3.");

    // Erstellen Sie ein "HtmlFixedSaveOptions"-Objekt, das wir an die "Save"-Methode des Dokuments übergeben können
    // um zu ändern, wie wir das Dokument in HTML konvertieren.
    HtmlFixedSaveOptions htmlFixedSaveOptions = new HtmlFixedSaveOptions();

    // Wir speichern jede Seite in diesem Dokument in einer separaten HTML-Datei im lokalen Dateisystem.
    // Setzen Sie einen Rückruf, der es uns ermöglicht, jedes ausgegebene HTML-Dokument zu benennen.
    htmlFixedSaveOptions.PageSavingCallback = new CustomFileNamePageSavingCallback();

    doc.Save(ArtifactsDir + "SavingCallback.PageFileNames.html", htmlFixedSaveOptions);

    string[] filePaths = Directory.GetFiles(ArtifactsDir).Where(
        s => s.StartsWith(ArtifactsDir + "SavingCallback.PageFileNames.Page_")).OrderBy(s => s).ToArray();

    Assert.AreEqual(3, filePaths.Length);
}

/// <summary>
/// Speichert alle Seiten in einer Datei und einem darin angegebenen Verzeichnis.
/// </summary>
private class CustomFileNamePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        string outFileName = $"{ArtifactsDir}SavingCallback.PageFileNames.Page_{args.PageIndex}.html";

        // Im Folgenden finden Sie zwei Möglichkeiten, um anzugeben, wo Aspose.Words jede Seite des Dokuments speichern wird.
        // 1 - Legen Sie einen Dateinamen für die Ausgabeseitendatei fest:
        args.PageFileName = outFileName;

        // 2 - Erstellen Sie einen benutzerdefinierten Stream für die Ausgabeseitendatei:
        args.PageStream = new FileStream(outFileName, FileMode.Create);

        Assert.False(args.KeepPageStreamOpen);
    }
}
```

### Siehe auch

* class [PageSavingArgs](../)
* namensraum [Aspose.Words.Saving](../../pagesavingargs/)
* Montage [Aspose.Words](../../../)


