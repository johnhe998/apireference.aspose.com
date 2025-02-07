---
title: FindReplaceOptions.IgnoreFieldCodes
second_title: Aspose.Words für .NET-API-Referenz
description: FindReplaceOptions eigendom. Ruft einen booleschen Wert ab oder legt ihn fest der angibt ob Text in Feldcodes ignoriert werden soll. Der Standardwert istFALSCH .
type: docs
weight: 70
url: /de/net/aspose.words.replacing/findreplaceoptions/ignorefieldcodes/
---
## FindReplaceOptions.IgnoreFieldCodes property

Ruft einen booleschen Wert ab oder legt ihn fest, der angibt, ob Text in Feldcodes ignoriert werden soll. Der Standardwert ist`FALSCH` .

```csharp
public bool IgnoreFieldCodes { get; set; }
```

### Bemerkungen

Diese Option wirkt sich nur auf Feldcodes aus (sie ignoriert keine Knoten zwischen FieldSeparator undFieldEnd).

Um das gesamte Feld zu ignorieren, verwenden Sie bitte die entsprechende Option[`IgnoreFields`](../ignorefields/).

### Beispiele

Zeigt, wie Text in Feldcodes ignoriert wird.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("INCLUDETEXT", "Test IT!");

FindReplaceOptions options = new FindReplaceOptions {IgnoreFieldCodes = ignoreFieldCodes};

// 'T' im Dokument ersetzen, Text im Feldcode ignorieren oder nicht.
doc.Range.Replace(new Regex("T"), "*", options);
Console.WriteLine(doc.GetText());

Assert.AreEqual(
    ignoreFieldCodes
        ? "\u0013INCLUDETEXT\u0014*est I*!\u0015"
        : "\u0013INCLUDE*EX*\u0014*est I*!\u0015", doc.GetText().Trim());
```

### Siehe auch

* class [FindReplaceOptions](../)
* namensraum [Aspose.Words.Replacing](../../findreplaceoptions/)
* Montage [Aspose.Words](../../../)


