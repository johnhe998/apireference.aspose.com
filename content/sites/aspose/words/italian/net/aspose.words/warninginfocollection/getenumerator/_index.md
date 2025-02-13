---
title: WarningInfoCollection.GetEnumerator
second_title: Aspose.Words per .NET API Reference
description: WarningInfoCollection metodo. Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta.
type: docs
weight: 50
url: /it/net/aspose.words/warninginfocollection/getenumerator/
---
## WarningInfoCollection.GetEnumerator method

Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta.

```csharp
public IEnumerator<WarningInfo> GetEnumerator()
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
* class [WarningInfoCollection](../)
* spazio dei nomi [Aspose.Words](../../warninginfocollection/)
* assemblea [Aspose.Words](../../../)


