---
title: TableSubstitutionRule.Save
second_title: Aspose.Words per .NET API Reference
description: TableSubstitutionRule metodo. Salva le impostazioni di sostituzione della tabella correnti su file.
type: docs
weight: 70
url: /it/net/aspose.words.fonts/tablesubstitutionrule/save/
---
## Save(string) {#save_1}

Salva le impostazioni di sostituzione della tabella correnti su file.

```csharp
public void Save(string fileName)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| fileName | String | Nome del file di output. |

### Esempi

Mostra come accedere alle tabelle di sostituzione dei caratteri per Windows e Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Crea una nuova regola di sostituzione delle tabelle e carica la tabella di sostituzione dei caratteri predefinita di Microsoft Windows.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// In Windows, il sostituto predefinito del carattere "Times New Roman CE" è "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Possiamo salvare la tabella sotto forma di documento XML.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// Linux ha la sua tabella di sostituzione.
// Ci sono più font sostitutivi per "Times New Roman CE".
// Se anche il primo sostituto, "FreeSerif", non è disponibile,
// questa regola scorrerà le altre nell'array finché non ne troverà una disponibile.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Salva la tabella di sostituzione di Linux sotto forma di documento XML utilizzando uno stream.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Guarda anche

* class [TableSubstitutionRule](../)
* spazio dei nomi [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* assemblea [Aspose.Words](../../../)

---

## Save(Stream) {#save}

Salva le impostazioni di sostituzione della tabella correnti nello stream.

```csharp
public void Save(Stream outputStream)
```

| Parametro | Tipo | Descrizione |
| --- | --- | --- |
| outputStream | Stream | Flusso di uscita. |

### Esempi

Mostra come accedere alle tabelle di sostituzione dei caratteri per Windows e Linux.

```csharp
Document doc = new Document();
FontSettings fontSettings = new FontSettings();
doc.FontSettings = fontSettings;

// Crea una nuova regola di sostituzione delle tabelle e carica la tabella di sostituzione dei caratteri predefinita di Microsoft Windows.
TableSubstitutionRule tableSubstitutionRule = fontSettings.SubstitutionSettings.TableSubstitution;
tableSubstitutionRule.LoadWindowsSettings();

// In Windows, il sostituto predefinito del carattere "Times New Roman CE" è "Times New Roman".
Assert.AreEqual(new[] {"Times New Roman"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Possiamo salvare la tabella sotto forma di documento XML.
tableSubstitutionRule.Save(ArtifactsDir + "FontSettings.TableSubstitutionRule.Windows.xml");

// Linux ha la sua tabella di sostituzione.
// Ci sono più font sostitutivi per "Times New Roman CE".
// Se anche il primo sostituto, "FreeSerif", non è disponibile,
// questa regola scorrerà le altre nell'array finché non ne troverà una disponibile.
tableSubstitutionRule.LoadLinuxSettings();
Assert.AreEqual(new[] {"FreeSerif", "Liberation Serif", "DejaVu Serif"},
    tableSubstitutionRule.GetSubstitutes("Times New Roman CE").ToArray());

// Salva la tabella di sostituzione di Linux sotto forma di documento XML utilizzando uno stream.
using (FileStream fileStream = new FileStream(ArtifactsDir + "FontSettings.TableSubstitutionRule.Linux.xml",
    FileMode.Create))
{
    tableSubstitutionRule.Save(fileStream);
}
```

### Guarda anche

* class [TableSubstitutionRule](../)
* spazio dei nomi [Aspose.Words.Fonts](../../tablesubstitutionrule/)
* assemblea [Aspose.Words](../../../)


