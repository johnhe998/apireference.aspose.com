---
title: StyleCollection.Document
second_title: Aspose.Words för .NET API Referens
description: StyleCollection fast egendom. Hämtar ägardokumentet.
type: docs
weight: 40
url: /sv/net/aspose.words/stylecollection/document/
---
## StyleCollection.Document property

Hämtar ägardokumentet.

```csharp
public DocumentBase Document { get; }
```

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

* class [DocumentBase](../../documentbase/)
* class [StyleCollection](../)
* namnutrymme [Aspose.Words](../../stylecollection/)
* hopsättning [Aspose.Words](../../../)


