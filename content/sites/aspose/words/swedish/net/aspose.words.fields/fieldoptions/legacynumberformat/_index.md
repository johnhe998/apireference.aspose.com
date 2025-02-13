---
title: FieldOptions.LegacyNumberFormat
second_title: Aspose.Words för .NET API Referens
description: FieldOptions fast egendom. Hämtar eller ställer in värdet som anger om äldre tidigt än AW 13.10 nummerformat för fält är aktiverat eller inte.
type: docs
weight: 140
url: /sv/net/aspose.words.fields/fieldoptions/legacynumberformat/
---
## FieldOptions.LegacyNumberFormat property

Hämtar eller ställer in värdet som anger om äldre (tidigt än AW 13.10) nummerformat för fält är aktiverat eller inte.

```csharp
public bool LegacyNumberFormat { get; set; }
```

### Anmärkningar

När den här egenskapen är inställd på **Sann**, mallsymbol "#" fungerade som i .net: Ersätter pundtecknet med motsvarande siffra om en sådan finns; annars visas inga symboler i resultatsträngen.

När den här egenskapen är inställd på **falsk**, mallsymbol "#" fungerar som MS Word: Det här formatobjektet anger de nödvändiga numeriska platserna som ska visas i resultatet. Om resultatet inte innehåller en siffra på den platsen, visar MS Word ett mellanslag. Till exempel, { = 9 + 6 \# $### } visar $15.

Standardvärdet är **falsk**.

### Exempel

Visar hur man aktiverar äldre nummerformatering för fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Field field = builder.InsertField("= 2 + 3 \\# $##");

Assert.AreEqual("$ 5", field.Result);

doc.FieldOptions.LegacyNumberFormat = true;
field.Update();

Assert.AreEqual("$5", field.Result);
```

### Se även

* class [FieldOptions](../)
* namnutrymme [Aspose.Words.Fields](../../fieldoptions/)
* hopsättning [Aspose.Words](../../../)


