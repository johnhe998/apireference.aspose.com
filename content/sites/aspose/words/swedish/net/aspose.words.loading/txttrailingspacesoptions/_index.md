---
title: Enum TxtTrailingSpacesOptions
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Loading.TxtTrailingSpacesOptions uppräkning. Anger tillgängliga alternativ för hantering av efterföljande utrymmen under import frånText fil.
type: docs
weight: 3540
url: /sv/net/aspose.words.loading/txttrailingspacesoptions/
---
## TxtTrailingSpacesOptions enumeration

Anger tillgängliga alternativ för hantering av efterföljande utrymmen under import frånText fil.

```csharp
public enum TxtTrailingSpacesOptions
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Trim | `0` |  |
| Preserve | `1` |  |

### Exempel

Visar hur man beskär blanktecken när du laddar dokument i klartext.

```csharp
string textDoc = "      Line 1 \n" +
                 "    Line 2   \n" +
                 " Line 3       ";

// Skapa ett "TxtLoadOptions"-objekt, som vi kan skicka till ett dokuments konstruktor
// för att ändra hur vi laddar ett dokument i klartext.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Ställ in egenskapen "LeadingSpacesOptions" till "TxtLeadingSpacesOptions.Preserve"
// för att bevara alla blanksteg i början av varje rad.
// Ställ in egenskapen "LeadingSpacesOptions" till "TxtLeadingSpacesOptions.ConvertToIndent"
// för att ta bort alla blanksteg från början av varje rad,
// och använd sedan en vänster första rad indrag på stycket för att simulera effekten av blanksteg.
// Ställ in egenskapen "LeadingSpacesOptions" till "TxtLeadingSpacesOptions.Trim"
// för att ta bort alla blanksteg från varje rads början.
loadOptions.LeadingSpacesOptions = txtLeadingSpacesOptions;

// Ställ in egenskapen "TrailingSpacesOptions" till "TxtTrailingSpacesOptions.Preserve"
// för att bevara alla blanksteg i slutet av varje rad. 
// Ställ in egenskapen "TrailingSpacesOptions" till "TxtTrailingSpacesOptions.Trim" till 
// ta bort alla blanksteg från slutet av varje rad.
loadOptions.TrailingSpacesOptions = txtTrailingSpacesOptions;

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

switch (txtLeadingSpacesOptions)
{
    case TxtLeadingSpacesOptions.ConvertToIndent:
        Assert.AreEqual(37.8d, paragraphs[0].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(25.2d, paragraphs[1].ParagraphFormat.FirstLineIndent);
        Assert.AreEqual(6.3d, paragraphs[2].ParagraphFormat.FirstLineIndent);

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
    case TxtLeadingSpacesOptions.Preserve:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("      Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("    Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith(" Line 3"));
        break;
    case TxtLeadingSpacesOptions.Trim:
        Assert.True(paragraphs.All(p => ((Paragraph)p).ParagraphFormat.FirstLineIndent == 0.0d));

        Assert.True(paragraphs[0].GetText().StartsWith("Line 1"));
        Assert.True(paragraphs[1].GetText().StartsWith("Line 2"));
        Assert.True(paragraphs[2].GetText().StartsWith("Line 3"));
        break;
}

switch (txtTrailingSpacesOptions)
{
    case TxtTrailingSpacesOptions.Preserve:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1 \r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2   \r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3       \f"));
        break;
    case TxtTrailingSpacesOptions.Trim:
        Assert.True(paragraphs[0].GetText().EndsWith("Line 1\r"));
        Assert.True(paragraphs[1].GetText().EndsWith("Line 2\r"));
        Assert.True(paragraphs[2].GetText().EndsWith("Line 3\f"));
        break;
}
```

### Se även

* namnutrymme [Aspose.Words.Loading](../../aspose.words.loading/)
* hopsättning [Aspose.Words](../../)


