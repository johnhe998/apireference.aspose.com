---
title: FieldAddressBlock.IncludeCountryOrRegionName
second_title: Aspose.Words för .NET API Referens
description: FieldAddressBlock fast egendom. Hämtar eller ställer in om namnet på landet/regionen ska inkluderas.
type: docs
weight: 40
url: /sv/net/aspose.words.fields/fieldaddressblock/includecountryorregionname/
---
## FieldAddressBlock.IncludeCountryOrRegionName property

Hämtar eller ställer in om namnet på landet/regionen ska inkluderas.

```csharp
public string IncludeCountryOrRegionName { get; set; }
```

### Exempel

Visar hur man infogar ett ADDRESSBLOCK-fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, true);

Assert.AreEqual(" ADDRESSBLOCK ", field.GetFieldCode());

// Om du ställer in detta till "2" kommer alla länder och regioner att inkluderas,
// om det inte är den som anges i egenskapen ExcludedCountryOrRegionName.
field.IncludeCountryOrRegionName = "2";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "United States";
field.NameAndAddressFormat = "<Title> <Forename> <Surname> <Address Line 1> <Region> <Postcode> <Country>";

// Som standard kommer den här egenskapen att innehålla språk-ID:t för det första tecknet i dokumentet.
// Vi kan ställa in en annan kultur för fältet att formatera resultatet med så här.
field.LanguageId = new CultureInfo("en-US").LCID.ToString();

Assert.AreEqual(
    " ADDRESSBLOCK  \\c 2 \\d \\e \"United States\" \\f \"<Title> <Forename> <Surname> <Address Line 1> <Region> <Postcode> <Country>\" \\l 1033",
    field.GetFieldCode());
```

### Se även

* class [FieldAddressBlock](../)
* namnutrymme [Aspose.Words.Fields](../../fieldaddressblock/)
* hopsättning [Aspose.Words](../../../)


