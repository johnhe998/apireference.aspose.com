---
title: FindReplaceOptions.IgnoreFieldCodes
second_title: Aspose.Words för .NET API Referens
description: FindReplaceOptions fast egendom. Hämtar eller ställer in ett booleskt värde som anger att text i fältkoder ska ignoreras. Standardvärdet ärfalsk .
type: docs
weight: 70
url: /sv/net/aspose.words.replacing/findreplaceoptions/ignorefieldcodes/
---
## FindReplaceOptions.IgnoreFieldCodes property

Hämtar eller ställer in ett booleskt värde som anger att text i fältkoder ska ignoreras. Standardvärdet är`falsk` .

```csharp
public bool IgnoreFieldCodes { get; set; }
```

### Anmärkningar

Det här alternativet påverkar endast fältkoder (det ignorerar inte noder between FieldSeparator ochFieldEnd).

För att ignorera hela fältet, använd motsvarande alternativ[`IgnoreFields`](../ignorefields/).

### Exempel

Visar hur man ignorerar text i fältkoder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("INCLUDETEXT", "Test IT!");

FindReplaceOptions options = new FindReplaceOptions {IgnoreFieldCodes = ignoreFieldCodes};

// Ersätt 'T' i dokumentet ignorera text i fältkoden eller inte.
doc.Range.Replace(new Regex("T"), "*", options);
Console.WriteLine(doc.GetText());

Assert.AreEqual(
    ignoreFieldCodes
        ? "\u0013INCLUDETEXT\u0014*est I*!\u0015"
        : "\u0013INCLUDE*EX*\u0014*est I*!\u0015", doc.GetText().Trim());
```

### Se även

* class [FindReplaceOptions](../)
* namnutrymme [Aspose.Words.Replacing](../../findreplaceoptions/)
* hopsättning [Aspose.Words](../../../)


