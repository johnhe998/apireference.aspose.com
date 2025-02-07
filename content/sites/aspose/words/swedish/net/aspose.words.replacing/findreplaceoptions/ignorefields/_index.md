---
title: FindReplaceOptions.IgnoreFields
second_title: Aspose.Words för .NET API Referens
description: FindReplaceOptions fast egendom. Hämtar eller ställer in ett booleskt värde som anger att texten i fält ska ignoreras. Standardvärdet ärfalsk .
type: docs
weight: 80
url: /sv/net/aspose.words.replacing/findreplaceoptions/ignorefields/
---
## FindReplaceOptions.IgnoreFields property

Hämtar eller ställer in ett booleskt värde som anger att texten i fält ska ignoreras. Standardvärdet är`falsk` .

```csharp
public bool IgnoreFields { get; set; }
```

### Anmärkningar

Det här alternativet påverkar hela fältet (alla noder between FieldStart ochFieldEnd).

För att ignorera endast fältkoder, använd motsvarande alternativ[`IgnoreFieldCodes`](../ignorefieldcodes/).

### Exempel

Visar hur man ignorerar text i fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.InsertField("QUOTE", "Hello again!");

// Vi kan använda ett "FindReplaceOptions"-objekt för att ändra sök-och-ersätt-processen.
FindReplaceOptions options = new FindReplaceOptions();

// Ställ in "IgnoreFields"-flaggan till "true" för att få sök-och-ersätt
// operation för att ignorera text i fält.
// Ställ in "IgnoreFields"-flaggan till "false" för att få sök-och-ersätt
// operation för att även söka efter text i fält.
options.IgnoreFields = ignoreTextInsideFields;

doc.Range.Replace("Hello", "Greetings", options);

Assert.AreEqual(
    ignoreTextInsideFields
        ? "Greetings world!\r\u0013QUOTE\u0014Hello again!\u0015"
        : "Greetings world!\r\u0013QUOTE\u0014Greetings again!\u0015", doc.GetText().Trim());
```

### Se även

* class [FindReplaceOptions](../)
* namnutrymme [Aspose.Words.Replacing](../../findreplaceoptions/)
* hopsättning [Aspose.Words](../../../)


