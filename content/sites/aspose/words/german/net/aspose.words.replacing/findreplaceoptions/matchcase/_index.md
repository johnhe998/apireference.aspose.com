---
title: FindReplaceOptions.MatchCase
second_title: Aspose.Words für .NET-API-Referenz
description: FindReplaceOptions eigendom. True gibt die Groß/Kleinschreibung an false gibt die Groß und Kleinschreibung an.
type: docs
weight: 120
url: /de/net/aspose.words.replacing/findreplaceoptions/matchcase/
---
## FindReplaceOptions.MatchCase property

„True“ gibt die Groß-/Kleinschreibung an, „false“ gibt die Groß- und Kleinschreibung an.

```csharp
public bool MatchCase { get; set; }
```

### Beispiele

Zeigt, wie die Groß-/Kleinschreibung beim Ausführen eines Suchen-und-Ersetzen-Vorgangs umgeschaltet wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Ruby bought a ruby necklace.");

// Wir können ein "FindReplaceOptions"-Objekt verwenden, um den Suchen-und-Ersetzen-Prozess zu ändern.
FindReplaceOptions options = new FindReplaceOptions();

// Setzen Sie das "MatchCase"-Flag auf "true", um die Groß-/Kleinschreibung beim Suchen von zu ersetzenden Zeichenfolgen anzuwenden.
// Setzen Sie das "MatchCase"-Flag auf "false", um die Groß-/Kleinschreibung bei der Suche nach zu ersetzendem Text zu ignorieren.
options.MatchCase = matchCase;

doc.Range.Replace("Ruby", "Jade", options);

Assert.AreEqual(matchCase ? "Jade bought a ruby necklace." : "Jade bought a Jade necklace.",
    doc.GetText().Trim());
```

### Siehe auch

* class [FindReplaceOptions](../)
* namensraum [Aspose.Words.Replacing](../../findreplaceoptions/)
* Montage [Aspose.Words](../../../)


