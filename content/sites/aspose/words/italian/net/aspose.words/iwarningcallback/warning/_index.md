---
title: IWarningCallback.Warning
second_title: Aspose.Words per .NET API Reference
description: IWarningCallback metodo. Aspose.Words richiama questo metodo quando incontra qualche problema durante il caricamento del documento o il salvataggio che potrebbe comportare la perdita di formattazione o fedeltà dei dati.
type: docs
weight: 10
url: /it/net/aspose.words/iwarningcallback/warning/
---
## IWarningCallback.Warning method

Aspose.Words richiama questo metodo quando incontra qualche problema durante il caricamento del documento o il salvataggio che potrebbe comportare la perdita di formattazione o fedeltà dei dati.

```csharp
public void Warning(WarningInfo info)
```

### Esempi

Mostra come impostare la proprietà per trovare la corrispondenza più vicina per un carattere mancante dalle fonti di carattere disponibili.

```csharp
[Test]
public void EnableFontSubstitution()
{
    // Apri un documento che contiene testo formattato con un font che non esiste in nessuna delle nostre fonti di font.
    Document doc = new Document(MyDir + "Missing font.docx");

    // Assegna una richiamata per la gestione degli avvisi di sostituzione dei caratteri.
    HandleDocumentSubstitutionWarnings substitutionWarningHandler = new HandleDocumentSubstitutionWarnings();
    doc.WarningCallback = substitutionWarningHandler;

    // Imposta un nome di carattere predefinito e abilita la sostituzione dei caratteri.
    FontSettings fontSettings = new FontSettings();
    fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
    ;
    fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = true;

    // Riceveremo un avviso di sostituzione del carattere se salviamo un documento con un carattere mancante.
    doc.FontSettings = fontSettings;
    doc.Save(ArtifactsDir + "FontSettings.EnableFontSubstitution.pdf");

    using (IEnumerator<WarningInfo> warnings = substitutionWarningHandler.FontWarnings.GetEnumerator())
        while (warnings.MoveNext())
            Console.WriteLine(warnings.Current.Description);

    // Possiamo anche verificare gli avvisi nella raccolta e cancellarli.
    Assert.AreEqual(WarningSource.Layout, substitutionWarningHandler.FontWarnings[0].Source);
    Assert.AreEqual(
        "Font '28 Days Later' has not been found. Using 'Calibri' font instead. Reason: alternative name from document.",
        substitutionWarningHandler.FontWarnings[0].Description);

    substitutionWarningHandler.FontWarnings.Clear();

    Assert.That(substitutionWarningHandler.FontWarnings, Is.Empty);
}

public class HandleDocumentSubstitutionWarnings : IWarningCallback
{
    /// <summary>
    /// Chiamato ogni volta che si verifica un avviso durante il caricamento/salvataggio.
    /// </summary>
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

### Guarda anche

* class [WarningInfo](../../warninginfo/)
* interface [IWarningCallback](../)
* spazio dei nomi [Aspose.Words](../../iwarningcallback/)
* assemblea [Aspose.Words](../../../)


