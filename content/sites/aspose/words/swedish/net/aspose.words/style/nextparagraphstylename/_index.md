---
title: Style.NextParagraphStyleName
second_title: Aspose.Words för .NET API Referens
description: Style fast egendom. Hämtar/ställer in namnet på formatet som ska tillämpas automatiskt på ett nytt stycke som infogas efter a stycke formaterat med det angivna formatet.
type: docs
weight: 120
url: /sv/net/aspose.words/style/nextparagraphstylename/
---
## Style.NextParagraphStyleName property

Hämtar/ställer in namnet på formatet som ska tillämpas automatiskt på ett nytt stycke som infogas efter a stycke formaterat med det angivna formatet.

```csharp
public string NextParagraphStyleName { get; set; }
```

### Anmärkningar

Den här egenskapen används inte av Aspose.Words. Nästa styckestil kommer endast att tillämpas automatiskt när du redigerar dokumentet i MS Word.

### Exempel

Visar hur du kommer åt ett dokuments stilsamling.

```csharp
Document doc = new Document();

Assert.AreEqual(4, doc.Styles.Count);

// Räkna upp och lista alla stilar som ett dokument skapat med Aspose.Words innehåller som standard.
using (IEnumerator<Style> stylesEnum = doc.Styles.GetEnumerator())
{
    while (stylesEnum.MoveNext())
    {
        Style curStyle = stylesEnum.Current;
        Console.WriteLine($"Style name:\t\"{curStyle.Name}\", of type \"{curStyle.Type}\"");
        Console.WriteLine($"\tSubsequent style:\t{curStyle.NextParagraphStyleName}");
        Console.WriteLine($"\tIs heading:\t\t\t{curStyle.IsHeading}");
        Console.WriteLine($"\tIs QuickStyle:\t\t{curStyle.IsQuickStyle}");

        Assert.AreEqual(doc, curStyle.Document);
    }
}
```

### Se även

* class [Style](../)
* namnutrymme [Aspose.Words](../../style/)
* hopsättning [Aspose.Words](../../../)


